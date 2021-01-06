---
title: Перенос служб дуплексной службы WCF в gRPC-gRPC для разработчиков WCF
description: Узнайте, как перенести различные формы служб дуплексной службы WCF в gRPC Streaming Services.
ms.date: 12/15/2020
ms.openlocfilehash: 4741e5ad5c12fa358853381d4f2c286add14f8f5
ms.sourcegitcommit: 655f8a16c488567dfa696fc0b293b34d3c81e3df
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/06/2021
ms.locfileid: "97938030"
---
# <a name="migrate-wcf-duplex-services-to-grpc"></a>Перенос дуплексных служб WCF в gRPC

Теперь, когда у вас есть смысл основных концепций, в этом разделе вы узнаете о более сложных *потоковых* gRPC службах.

Существует несколько способов использования дуплексных служб в Windows Communication Foundation (WCF). Некоторые службы инициируются клиентом, а затем потоковая передача данных с сервера. Другие Дуплексные службы могут содержать более интерактивное двустороннее взаимодействие, например классический калькулятор в документации по WCF. В этой главе вы получите две возможные реализации биржевых средств WCF и перенесите их в gRPC: один использует потоковую передачу RPC на сервере и другой, использующий двунаправленный потоковую передачу RPC.

## <a name="server-streaming-rpc"></a>Потоковая передача RPC сервера

В [примере решения WCF симплестокктиккер](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/SimpleStockTickerSample/wcf/SimpleStockTicker), симплестоккприцетиккер, существует дуплексная служба, для которой клиент запускает подключение со списком стандартных символов, а сервер использует *интерфейс обратного вызова* для отправки обновлений по мере их появления. Клиент реализует этот интерфейс для реагирования на вызовы с сервера.

### <a name="the-wcf-solution"></a>Решение WCF

Решение WCF реализовано как локально размещенный сервер NET. TCP в .NET Framework 4. консольное приложение *x* .

#### <a name="servicecontract"></a>ServiceContract

```csharp
[ServiceContract(SessionMode = SessionMode.Required, CallbackContract = typeof(ISimpleStockTickerCallback))]
public interface ISimpleStockTickerService
{
    [OperationContract(IsOneWay = true)]
    void Subscribe(string[] symbols);
}
```

Служба имеет один метод без типа возвращаемого значения, так как он использует интерфейс обратного вызова `ISimpleStockTickerCallback` для отправки данных клиенту в режиме реального времени.

#### <a name="the-callback-interface"></a>Интерфейс обратного вызова

```csharp
[ServiceContract]
public interface ISimpleStockTickerCallback
{
    [OperationContract(IsOneWay = true)]
    void Update(string symbol, decimal price);
}
```

Реализации этих интерфейсов можно найти в решении, а также с фиктивными внешними зависимостями для предоставления тестовых данных.

### <a name="grpc-streaming"></a>Потоковая передача gRPC

Процесс gRPC для обработки данных в режиме реального времени отличается от процесса WCF. Вызов от клиента к серверу может создать постоянный поток, который можно отслеживать для сообщений, поступивших асинхронно. Несмотря на различие, потоки могут быть более интуитивно понятным способом работы с этими данными и более актуальны в современном программировании, что акцентирует внимание на LINQ, реактивные потоки, функциональное программирование и т. д.

Определение службы должно иметь два сообщения: одно для запроса и одно для потока. Служба возвращает поток `StockTickerUpdate` сообщения с `stream` ключевым словом в его `return` объявлении. Рекомендуется добавить `Timestamp` к обновлению, чтобы отобразить точное время изменения цены.

#### <a name="simple_stock_tickerproto"></a>simple_stock_ticker.

```protobuf
syntax = "proto3";

option csharp_namespace = "TraderSys.SimpleStockTickerServer.Protos";

import "google/protobuf/timestamp.proto";

package SimpleStockTickerServer;

service SimpleStockTicker {
  rpc Subscribe (SubscribeRequest) returns (stream StockTickerUpdate);
}

message SubscribeRequest {
  repeated string symbols = 1;
}

message StockTickerUpdate {
  string symbol = 1;
  int32 price_cents = 2;
  google.protobuf.Timestamp time = 3;
}
```

### <a name="implement-simplestockticker"></a>Реализация Симплестокктиккер

Повторно используйте имитацию `StockPriceSubscriber` из проекта WCF, скопировав три класса из `TraderSys.StockMarket` библиотеки классов в новую библиотеку классов .NET Standard в целевом решении. Чтобы лучше следовать рекомендациям, добавьте `Factory` тип для создания экземпляров и зарегистрируйте его `IStockPriceSubscriberFactory` с помощью ASP.NET Core служб внедрения зависимостей.

#### <a name="the-factory-implementation"></a>Реализация фабрики

```csharp
public interface IStockPriceSubscriberFactory
{
    IStockPriceSubscriber GetSubscriber(string[] symbols);
}

public class StockPriceSubscriberFactory : IStockPriceSubscriberFactory
{
    public IStockPriceSubscriber GetSubscriber(string[] symbols)
    {
        return new StockPriceSubscriber(symbols);
    }
}
```

#### <a name="register-the-factory"></a>Регистрация фабрики

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddGrpc();
    services.AddSingleton<IStockPriceSubscriberFactory, StockPriceSubscriberFactory>();
}
```

Теперь этот класс можно использовать для реализации gRPC `StockTickerService` .

#### <a name="stocktickerservicecs"></a>StockTickerService.cs

```csharp
public class StockTickerService : Protos.SimpleStockTicker.SimpleStockTickerBase
{
    private readonly IStockPriceSubscriberFactory _subscriberFactory;

    public StockTickerService(IStockPriceSubscriberFactory subscriberFactory)
    {
        _subscriberFactory = subscriberFactory;
    }

    public override async Task Subscribe(SubscribeRequest request, IServerStreamWriter<StockTickerUpdate> responseStream, ServerCallContext context)
    {
        var subscriber = _subscriberFactory.GetSubscriber(request.Symbols.ToArray());

        subscriber.Update += async (sender, args) =>
            await WriteUpdateAsync(responseStream, args.Symbol, args.Price);

        await AwaitCancellation(context.CancellationToken);
    }

    private async Task WriteUpdateAsync(IServerStreamWriter<StockTickerUpdate> stream, string symbol, decimal price)
    {
        try
        {
            await stream.WriteAsync(new StockTickerUpdate
            {
                Symbol = symbol,
                PriceCents = (int)(price * 100),
                Time = Timestamp.FromDateTimeOffset(DateTimeOffset.UtcNow)
            });
        }
        catch (Exception e)
        {
            // Handle any errors caused by broken connection, etc.
            _logger.LogError($"Failed to write message: {e.Message}");
        }
    }

    private static Task AwaitCancellation(CancellationToken token)
    {
        var completion = new TaskCompletionSource<object>();
        token.Register(() => completion.SetResult(null));
        return completion.Task;
    }
}
```

Как видите, хотя объявление в `.proto` файле говорит, что метод возвращает поток `StockTickerUpdate` сообщений, он фактически возвращает `Task` . Задание создания потока обрабатывается созданным кодом и библиотеками времени выполнения gRPC, которые предоставляют `IServerStreamWriter<StockTickerUpdate>` поток ответов, готовый к использованию.

В отличие от двусторонней службы WCF, где экземпляр класса службы хранится в активном состоянии при открытом соединении, служба gRPC использует возвращенную задачу для поддержания активности службы. Задача не должна завершаться, пока соединение не будет закрыто.

Служба может определить, когда клиент закрыл соединение с помощью `CancellationToken` из `ServerCallContext` . Простой статический метод, `AwaitCancellation` , используется для создания задачи, которая завершается при отмене маркера.

В `Subscribe` методе получите `StockPriceSubscriber` и добавьте обработчик событий, записывающий данные в поток ответа. Затем дождитесь закрытия соединения, прежде чем сразу же удаляется, `subscriber` чтобы предотвратить попытку записи данных в закрытый поток.

`WriteUpdateAsync`Метод имеет `try` / `catch` блок для выполнения любых ошибок, которые могут произойти при запись сообщения в поток. Это важно в постоянных подключениях по сетям, которые могут быть нарушены в любой миллисекунде, как намеренно, так и из-за сбоя в любом месте.

### <a name="use-stocktickerservice-from-a-client-application"></a>Использование Стокктиккерсервице из клиентского приложения

Выполните те же действия из предыдущего раздела, чтобы создать общую библиотеку классов клиента из `.proto` файла. В этом примере имеется консольное приложение .NET, которое демонстрирует использование клиента.

#### <a name="example-programcs"></a>Пример Program.cs

```csharp
class Program
{
    static async Task Main(string[] args)
    {
        using var channel = GrpcChannel.ForAddress("https://localhost:5001");
        var client = new SimpleStockTicker.SimpleStockTickerClient(channel);

        var request = new SubscribeRequest();
        request.Symbols.AddRange(args);

        using var stream = client.Subscribe(request);

        var tokenSource = new CancellationTokenSource();

        var task = DisplayAsync(stream.ResponseStream, tokenSource.Token);

        WaitForExitKey();

        tokenSource.Cancel();
        await task;
    }
}
```

В этом случае `Subscribe` метод созданного клиента не является асинхронным. Поток создается и пригоден к использованию, так как его `MoveNext` метод асинхронен и первый раз его вызов не завершается до тех пор, пока соединение не будет активно.

Поток передается асинхронному `DisplayAsync` методу. Затем приложение ожидает нажатия пользователем клавиши, а затем отменяет `DisplayAsync` метод и ожидает завершения задачи перед выходом.

> [!NOTE]
> Этот код использует новый `using` синтаксис объявления C# 8 для удаления потока и канала при `Main` выходе из метода. Это небольшое изменение, но хорошо, что сокращает отступы и пустые строки.

#### <a name="consume-the-stream"></a>Использование потока

WCF использует интерфейсы обратного вызова, чтобы разрешить серверу вызывать методы непосредственно на клиенте. потоки gRPC работают по-разному. Клиент проходит по возвращенному потоку и обрабатывает сообщения так, как будто они были возвращены из локального метода, возвращающего `IEnumerable` .

`IAsyncStreamReader<T>`Тип работает во многом подобно `IEnumerator<T>` . Существует `MoveNext` метод, возвращающий значение true, если есть больше данных, и `Current` свойство, которое возвращает последнее значение. Единственное отличие заключается в том, что `MoveNext` метод возвращает, `Task<bool>` а не просто `bool` . `ReadAllAsync`Метод расширения создает оболочку для потока в стандартном C# 8 `IAsyncEnumerable` , который можно использовать с новым `await foreach` синтаксисом.

```csharp
static async Task DisplayAsync(IAsyncStreamReader<StockTickerUpdate> stream, CancellationToken token)
{
    try
    {
        await foreach (var update in stream.ReadAllAsync(token))
        {
            Console.WriteLine($"{update.Symbol}: {update.Price}");
        }
    }
    catch (RpcException e) when (e.StatusCode == StatusCode.Cancelled)
    {
        return;
    }
    catch (OperationCanceledException)
    {
        Console.WriteLine("Finished.");
    }
}
```

> [!TIP]
> Для разработчиков, использующих реактивные шаблоны программирования, в разделе, посвященном [клиентским библиотекам](client-libraries.md#iobservable) в конце этой главы, показано, как добавить метод расширения и классы для переноса `IAsyncStreamReader<T>` в `IObservable<T>` .

Опять же, не забудьте перехватывать исключения из-за возможности сбоя в сети и из-за того <xref:System.OperationCanceledException> , что неизбежно будет вызываться, так как код использует <xref:System.Threading.CancellationToken> для разбиения цикла. `RpcException`Тип имеет много полезной информации об ошибках среды выполнения gRPC, включая `StatusCode` . Дополнительные сведения см. в разделе [ *Обработка ошибок* в главе 4](error-handling.md).

## <a name="bidirectional-streaming"></a>Двунаправленная потоковая передача

Высокодуплексная служба WCF обеспечивает асинхронный обмен сообщениями в режиме реального времени в обоих направлениях. В примере потоковой передачи сервера клиент запускает запрос, а затем получает поток обновлений. Более новая версия этой службы позволит клиенту добавлять и удалять акции из списка без необходимости приостанавливаться и создавать новую подписку. Эта функциональность реализована в [примере решения фуллстокктиккер](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/wcf/FullStockTicker).

`IFullStockTickerService`Интерфейс предоставляет три метода:

- `Subscribe` запускает подключение.
- `AddSymbol` Добавляет символ акции для просмотра.
- `RemoveSymbol` Удаляет символ из наблюдаемого списка.

```csharp
[ServiceContract(SessionMode = SessionMode.Required, CallbackContract = typeof(IFullStockTickerCallback))]
public interface IFullStockTickerService
{
    [OperationContract(IsOneWay = true)]
    void Subscribe();

    [OperationContract(IsOneWay = true)]
    void AddSymbol(string symbol);

    [OperationContract(IsOneWay = true)]
    void RemoveSymbol(string symbol);
}
```

Интерфейс обратного вызова остается прежним.

Реализация этого шаблона в gRPC менее проста, так как теперь существует два потока данных с передачей сообщений: от клиента к серверу и от сервера к клиенту. Невозможно использовать несколько методов для реализации операций добавления и удаления, но можно передать более одного типа сообщений в одном потоке с помощью `Any` `oneof` ключевого слова Type или, которое было рассмотрено в [главе 3](protobuf-any-oneof.md).

Если существует конкретный набор допустимых типов, `oneof` лучше всего сделать это. Используйте объект `ActionMessage` , который может содержать либо `AddSymbolRequest` `RemoveSymbolRequest` :

```protobuf
message ActionMessage {
  oneof action {
    AddSymbolRequest add = 1;
    RemoveSymbolRequest remove = 2;
  }
}

message AddSymbolRequest {
  string symbol = 1;
}

message RemoveSymbolRequest {
  string symbol = 1;
}
```

Объявите службу двунаправленной потоковой передачи, которая принимает поток `ActionMessage` сообщений:

```protobuf
service FullStockTicker {
  rpc Subscribe (stream ActionMessage) returns (stream StockTickerUpdate);
}
```

Реализация для этой службы аналогична предыдущему примеру, за исключением того, что первый параметр `Subscribe` метода теперь является `IAsyncStreamReader<ActionMessage>` , который можно использовать для обработки `Add` `Remove` запросов и.

```csharp
public override async Task Subscribe(IAsyncStreamReader<ActionMessage> requestStream, IServerStreamWriter<StockTickerUpdate> responseStream, ServerCallContext context)
{
    using var subscriber = _subscriberFactory.GetSubscriber();

    subscriber.Update += async (sender, args) =>
        await WriteUpdateAsync(responseStream, args.Symbol, args.Price);

    var actionsTask = HandleActions(requestStream, subscriber, context.CancellationToken);

    _logger.LogInformation("Subscription started.");
    await AwaitCancellation(context.CancellationToken);

    try { await actionsTask; } catch { /* Ignored */ }

    _logger.LogInformation("Subscription finished.");
}

private async Task WriteUpdateAsync(IServerStreamWriter<StockTickerUpdate> stream, string symbol, decimal price)
{
    try
    {
        await stream.WriteAsync(new StockTickerUpdate
        {
            Symbol = symbol,
            PriceCents = (int)(price * 100),
            Time = Timestamp.FromDateTimeOffset(DateTimeOffset.UtcNow)
        });
    }
    catch (Exception e)
    {
        // Handle any errors caused by broken connection, etc.
        _logger.LogError($"Failed to write message: {e.Message}");
    }
}

private static Task AwaitCancellation(CancellationToken token)
{
    var completion = new TaskCompletionSource<object>();
    token.Register(() => completion.SetResult(null));
    return completion.Task;
}
```

`ActionMessage`Класс, созданный gRPC, гарантирует, что можно установить только одно `Add` из `Remove` свойств и. Определить, какой `null` тип сообщения использовать не является допустимым способом, но есть и лучший способ. Создание кода также создает `enum ActionOneOfCase` в `ActionMessage` классе, который выглядит следующим образом:

```csharp
public enum ActionOneofCase {
    None = 0,
    Add = 1,
    Remove = 2,
}
```

Свойство `ActionCase` `ActionMessage` объекта может использоваться с `switch` инструкцией для определения того, какое поле задается:

```csharp
private async Task HandleActions(IAsyncStreamReader<ActionMessage> requestStream, IFullStockPriceSubscriber subscriber, CancellationToken token)
{
    await foreach (var action in requestStream.ReadAllAsync(token))
    {
        switch (action.ActionCase)
        {
            case ActionMessage.ActionOneofCase.None:
                _logger.LogWarning("No Action specified.");
                break;
            case ActionMessage.ActionOneofCase.Add:
                subscriber.Add(action.Add.Symbol);
                break;
            case ActionMessage.ActionOneofCase.Remove:
                subscriber.Remove(action.Remove.Symbol);
                break;
            default:
                _logger.LogWarning($"Unknown Action '{action.ActionCase}'.");
                break;
        }
    }
}
```

> [!TIP]
> В `switch` инструкции есть `default` вариант, который регистрирует предупреждение при обнаружении неизвестного `ActionOneOfCase` значения. Это может быть полезно для указания того, что клиент использует более позднюю версию файла с `.proto` дополнительными действиями. Это одна из причин того, почему использование объекта `switch` лучше, чем тестирование `null` на наличие известных полей.

### <a name="use-fullstocktickerservice-from-a-client-application"></a>Использование Фуллстокктиккерсервице из клиентского приложения

Существует простое приложение .NET WPF, которое демонстрирует использование этого более сложного клиента. Полное приложение можно найти на сайте [GitHub](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/grpc/FullStockTicker).

Клиент используется в `MainWindowViewModel` классе, который получает экземпляр `FullStockTicker.FullStockTickerClient` типа из внедрения зависимостей:

```csharp
public class MainWindowViewModel : IAsyncDisposable, INotifyPropertyChanged
{
    private readonly FullStockTicker.FullStockTickerClient _client;
    private readonly AsyncDuplexStreamingCall<ActionMessage, StockTickerUpdate> _duplexStream;
    private readonly CancellationTokenSource _cancellationTokenSource;
    private readonly Task _responseTask;
    private string _addSymbol;

    public MainWindowViewModel(FullStockTicker.FullStockTickerClient client)
    {
        _cancellationTokenSource = new CancellationTokenSource();
        _client = client;
        _duplexStream = _client.Subscribe();
        _responseTask = HandleResponsesAsync(_cancellationTokenSource.Token);

        AddCommand = new AsyncCommand(Add, CanAdd);
    }
```

Объект, возвращаемый `client.Subscribe()` методом, теперь является экземпляром типа библиотеки gRPC `AsyncDuplexStreamingCall<TRequest, TResponse>` , который предоставляет `RequestStream` для отправки запросов на сервер и `ResponseStream` для обработки ответов.

Поток запроса используется из некоторых `ICommand` методов WPF для добавления и удаления символов. Для каждой операции задайте соответствующее поле для `ActionMessage` объекта:

```csharp
private async Task Add()
{
    if (CanAdd())
    {
        await _duplexStream.RequestStream.WriteAsync(new ActionMessage {Add = new AddSymbolRequest {Symbol = AddSymbol}});
    }
}

public async Task Remove(PriceViewModel priceViewModel)
{
    await _duplexStream.RequestStream.WriteAsync(new ActionMessage {Remove = new RemoveSymbolRequest {Symbol = priceViewModel.Symbol}});
    Prices.Remove(priceViewModel);
}
```

> [!IMPORTANT]
> При установке `oneof` значения поля в сообщении автоматически очищаются все поля, которые были заданы ранее.

Поток ответов обрабатывается в `async` методе. `Task`Он возвращается для удаления при закрытии окна:

```csharp
private async Task HandleResponsesAsync(CancellationToken token)
{
    var stream = _duplexStream.ResponseStream;

    try
    {
        await foreach (var update in stream.ReadAllAsync(token))
        {
            var price = Prices.FirstOrDefault(p => p.Symbol.Equals(update.Symbol));
            if (price == null)
            {
                price = new PriceViewModel(this) {Symbol = update.Symbol, Price = update.PriceCents / 100m};
                Prices.Add(price);
            }
            else
            {
                price.Price = update.PriceCents / 100m;
            }
        }
    }
    catch (OperationCancelledException) { }
}
```

### <a name="client-cleanup"></a>Очистка клиента

Когда окно закрывается и `MainWindowViewModel` удаляется (из `Closed` события `MainWindow` ), рекомендуется правильно ликвидировать `AsyncDuplexStreamingCall` объект. В частности, `CompleteAsync` метод `RequestStream` должен вызываться для корректного закрытия потока на сервере. В этом примере показан `DisposeAsync` метод из примера модели представления:

```csharp
public async ValueTask DisposeAsync()
{
    try
    {
        await _duplexStream.RequestStream.CompleteAsync().ConfigureAwait(false);
        await _responseTask.ConfigureAwait(false);
    }
    finally
    {
        _duplexStream.Dispose();
    }
}
```

Закрытие потоков запросов позволяет серверу своевременно удалять собственные ресурсы. Это повышает эффективность и масштабируемость служб и предотвращает исключения.

>[!div class="step-by-step"]
>[Назад](migrate-request-reply.md)
>[Вперед](streaming-versus-repeated.md)
