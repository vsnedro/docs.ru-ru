---
title: Создание клиентских библиотек gRPC — gRPC для разработчиков WCF
description: Обсуждение общих клиентских библиотек или пакетов для служб gRPC Services.
ms.date: 12/15/2020
ms.openlocfilehash: b1233bb40a5fa2119a325be2657b500a4c626c18
ms.sourcegitcommit: 655f8a16c488567dfa696fc0b293b34d3c81e3df
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/06/2021
ms.locfileid: "97938433"
---
# <a name="create-grpc-client-libraries"></a>Создание клиентских библиотек gRPC

Нет необходимости распространять клиентские библиотеки для приложения gRPC. Вы можете создать общую библиотеку `.proto` файлов в Организации, и другие команды смогут использовать эти файлы для создания клиентского кода в своих проектах. Но если у вас есть частный репозиторий NuGet и многие другие команды используют .NET, вы можете создавать и публиковать клиентские пакеты NuGet в рамках проекта службы. Такой подход может быть хорошим способом совместного использования и повышения уровня службы.

Одним из преимуществ распространения клиентской библиотеки является то, что вы можете усовершенствовать созданные классы gRPC и protobuf с помощью полезных "удобных" методов и свойств. В клиентском коде, как и на сервере, все классы объявляются как `partial` , поэтому их можно расширить, не редактируя созданный код. Такое поведение означает простоту добавления конструкторов, методов и вычисляемых свойств к базовым типам.

> [!CAUTION]
> Не следует использовать пользовательский код для предоставления необходимых функциональных возможностей. Вы не хотите ограничивать эту функциональность командам .NET, которые используют общую библиотеку, и не предоставлять ее группам, использующим другие языки или платформы, такие как Python или Java.

Убедитесь, что максимально возможное количество команд может получить доступ к службе gRPC. Лучший способ выполнить эту функцию — предоставить общий доступ к `.proto` файлам, чтобы разработчики могли создавать собственные клиенты. Этот подход особенно относится к многоплатформенной среде, в которой разные группы часто используют разные языки программирования и платформы, или если ваш API доступен извне.

## <a name="useful-extensions"></a>Полезные расширения

Существует два часто используемых интерфейса .NET для работы с потоками объектов: <xref:System.Collections.Generic.IEnumerable%601> и <xref:System.IObservable%601> . Начиная с .NET Core 3,0 и C# 8,0, существует <xref:System.Collections.Generic.IAsyncEnumerable%601> интерфейс для асинхронной обработки потоков и `await foreach` синтаксис для использования интерфейса. В этом разделе представлен многократно используемый код для применения этих интерфейсов к gRPC потокам.

В клиентских библиотеках .NET gRPC существует `ReadAllAsync` метод расширения `IAsyncStreamReader<T>` , который создает `IAsyncEnumerable<T>` интерфейс. Для разработчиков, использующих реактивное программирование, эквивалентный метод расширения для создания `IObservable<T>` интерфейса может выглядеть как пример в следующем разделе.

### <a name="iobservable"></a>IObservable

`IObservable<T>`Интерфейс является обратным инверсией `IEnumerable<T>` . Вместо того чтобы извлекать элементы из потока, реактивный подход позволяет потоку отправлять элементы подписчику. Такое поведение очень похоже на потоки gRPC, и вы можете легко обернуть `IObservable<T>` интерфейс вокруг `IAsyncStreamReader<T>` интерфейса.

Этот код длиннее, чем `IAsyncEnumerable<T>` код, поскольку в C# нет встроенной поддержки для работы с observable. Класс реализации необходимо создать вручную. Однако это универсальный класс, поэтому одна реализация работает для всех типов.

```csharp
using System;
using System.Diagnostics;
using System.Threading;
using System.Threading.Tasks;

namespace Grpc.Core
{
    public class GrpcStreamObservable<T> : IObservable<T>
    {
        private readonly IAsyncStreamReader<T> _reader;
        private readonly CancellationToken _token;
        private int _used;

        public GrpcStreamObservable(IAsyncStreamReader<T> reader, CancellationToken token = default)
        {
            _reader = reader;
            _token = token;
            _used = 0;
        }

        public IDisposable Subscribe(IObserver<T> observer) =>
            Interlocked.Exchange(ref _used, 1) == 0
                ? new GrpcStreamSubscription(_reader, observer, _token)
                : throw new InvalidOperationException("Subscribe can only be called once.");

    }
}
```

> [!IMPORTANT]
> Эта наблюдаемая реализация позволяет `Subscribe` вызывать метод только один раз, так как наличие нескольких подписчиков, пытающихся выполнить чтение из потока, приведет к Chaos. Существуют операторы, такие как `Replay` в [System. Reactive. LINQ](https://www.nuget.org/packages/System.Reactive.Linq), которые позволяют использовать буферизацию и повторяемый общий доступ к observable, который может использоваться с этой реализацией.

`GrpcStreamSubscription`Класс обрабатывает перечисление `IAsyncStreamReader` :

```csharp
public class GrpcStreamSubscription : IDisposable
{
    private readonly Task _task;
    private readonly CancellationTokenSource _tokenSource;
    private bool _completed;

    public GrpcStreamSubscription(IAsyncStreamReader<T> reader, IObserver<T> observer, CancellationToken token)
    {
        Debug.Assert(reader != null);
        Debug.Assert(observer != null);
        _tokenSource = new CancellationTokenSource();
        token.Register(_tokenSource.Cancel);
        _task = Run(reader, observer, _tokenSource.Token);
    }

    private async Task Run(IAsyncStreamReader<T> reader, IObserver<T> observer, CancellationToken token)
    {
        while (!token.IsCancellationRequested)
        {
            try
            {
                if (!await reader.MoveNext(token)) break;
            }
            catch (RpcException e) when (e.StatusCode == Grpc.Core.StatusCode.NotFound)
            {
                break;
            }
            catch (OperationCanceledException)
            {
                break;
            }
            catch (Exception e)
            {
                observer.OnError(e);
                _completed = true;
                return;
            }

            observer.OnNext(reader.Current);
        }

        _completed = true;
        observer.OnCompleted();
    }

    public void Dispose()
    {
        if (!_completed && !_tokenSource.IsCancellationRequested)
        {
            _tokenSource.Cancel();
        }

        _tokenSource.Dispose();
        _task.Dispose();
    }

}
```

Все, что нужно сделать, это простой метод расширения для создания наблюдаемого элемента из модуля чтения потока.

```csharp
using System;
using System.Diagnostics;
using System.Threading;
using System.Threading.Tasks;

namespace Grpc.Core
{
    public static class AsyncStreamReaderObservableExtensions
    {
        public static IObservable<T> AsObservable<T>(this IAsyncStreamReader<T> reader) =>
            new GrpcStreamObservable<T>(reader);
    }
}
```

## <a name="summary"></a>Итоги

<xref:System.IAsyncDisposable>Модели и <xref:System.IObservable%601> являются хорошо поддерживаемыми и хорошо документированными способами работы с асинхронными потоками данных в .NET. gRPC потоки хорошо сопоставляются с обеими парадигмами, предлагают близкую интеграцию с .NET, а также реактивный и асинхронный стиль программирования.

>[!div class="step-by-step"]
>[Назад](streaming-versus-repeated.md)
>[Вперед](security.md)
