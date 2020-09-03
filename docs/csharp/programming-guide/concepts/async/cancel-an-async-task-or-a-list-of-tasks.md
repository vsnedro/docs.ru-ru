---
title: Отмена списка задач (C#)
description: Узнайте, как использовать токены отмены для подачи запроса на отмену в список задач.
ms.date: 08/19/2020
ms.topic: tutorial
ms.assetid: eec32dbb-70ea-4c88-bd27-fa2e34546914
ms.openlocfilehash: 30bef5d1a5082fbd3757377dbedb8f9b9d17e218
ms.sourcegitcommit: 2560a355c76b0a04cba0d34da870df9ad94ceca3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/28/2020
ms.locfileid: "89053097"
---
# <a name="cancel-a-list-of-tasks-c"></a>Отмена списка задач (C#)

Вы можете отменить асинхронное консольное приложение, если не хотите дожидаться его завершения. Выполнив код в приведенных ниже примерах, вы сможете добавить в приложение возможность отмены, загружающую содержимое списка веб-сайтов. Можно отменить множество задач, связав экземпляр <xref:System.Threading.CancellationTokenSource> с каждой задачей. В этом случае нажатие клавиши <kbd>ВВОД</kbd> отменяет сразу все незавершенные задачи.

Темы, рассматриваемые в этом руководстве:

> [!div class="checklist"]
>
> - Создание консольного приложения .NET
> - Создание асинхронного приложения, поддерживающего отмену
> - Демонстрация отмены сигнализации

## <a name="prerequisites"></a>Предварительные требования

Для работы с данным учебником требуется следующее:

- [Пакет SDK для .NET 5.0 или более поздней версии](https://dotnet.microsoft.com/download/dotnet/5.0)
- Интегрированная среда разработки (IDE)
  - [Мы рекомендуем Visual Studio, Visual Studio Code или Visual Studio для Mac](https://visualstudio.microsoft.com)

### <a name="create-example-application"></a>Создание примера приложения

Создайте новое консольное приложение .NET Core. Его можно создать с помощью команды [`dotnet new console`](../../../../core/tools/dotnet-new.md#console) или в [Visual Studio](/visualstudio/install/install-visual-studio). Откройте файл *Program.cs* в любом редакторе кода.

### <a name="replace-using-statements"></a>Замена операторов using

Замените существующие операторы using следующими объявлениями.

```csharp
using System;
using System.Collections.Generic;
using System.Diagnostics;
using System.Net.Http;
using System.Threading;
using System.Threading.Tasks;
```

## <a name="add-fields"></a>Добавить поля

В определении класса `Program` добавьте следующие три поля.

```csharp
static readonly CancellationTokenSource s_cts = new CancellationTokenSource();

static readonly HttpClient s_client = new HttpClient
{
    MaxResponseContentBufferSize = 1_000_000
};

static readonly IEnumerable<string> s_urlList = new string[]
{
    "https://docs.microsoft.com",
    "https://docs.microsoft.com/aspnet/core",
    "https://docs.microsoft.com/azure",
    "https://docs.microsoft.com/azure/devops",
    "https://docs.microsoft.com/dotnet",
    "https://docs.microsoft.com/dynamics365",
    "https://docs.microsoft.com/education",
    "https://docs.microsoft.com/enterprise-mobility-security",
    "https://docs.microsoft.com/gaming",
    "https://docs.microsoft.com/graph",
    "https://docs.microsoft.com/microsoft-365",
    "https://docs.microsoft.com/office",
    "https://docs.microsoft.com/powershell",
    "https://docs.microsoft.com/sql",
    "https://docs.microsoft.com/surface",
    "https://docs.microsoft.com/system-center",
    "https://docs.microsoft.com/visualstudio",
    "https://docs.microsoft.com/windows",
    "https://docs.microsoft.com/xamarin"
};
```

<xref:System.Threading.CancellationTokenSource> используется для сигнализации запрошенной отмены <xref:System.Threading.CancellationToken>. `HttpClient` предоставляет возможность отправлять HTTP-запросы и получать HTTP-ответы. `s_urlList` содержит все URL-адреса, которые планируется обработать приложением.

## <a name="update-application-entry-point"></a>Обновление точки входа приложения

Главной точкой входа в консольное приложение является метод `Main`. Замените существующий метод следующим кодом.

```csharp
static async Task Main()
{
    Console.WriteLine("Application started.");
    Console.WriteLine("Press the ENTER key to cancel...\n");

    Task cancelTask = Task.Run(() =>
    {
        while (Console.ReadKey().Key != ConsoleKey.Enter)
        {
            Console.WriteLine("Press the ENTER key to cancel...");
        }

        Console.WriteLine("\nENTER key pressed: cancelling downloads.\n");
        s_cts.Cancel();
    });

    Task sumPageSizesTask = SumPageSizesAsync();

    await Task.WhenAny(new[] { cancelTask, sumPageSizesTask });

    Console.WriteLine("Application ending.");
}
```

Обновленный метод `Main` теперь считается [асинхронным методом main](../../../whats-new/csharp-7-1.md#async-main), который позволяет использовать асинхронную точку входа в исполняемом файле. Он записывает в консоль несколько сообщений с инструкциями, а затем объявляет экземпляр <xref:System.Threading.Tasks.Task> с именем `cancelTask`, который будет считывать нажатия клавиш в консоли. Если нажата клавиша <kbd>ВВОД</kbd>, выполняется вызов <xref:System.Threading.CancellationTokenSource.Cancel?displayProperty=nameWithType>. Это приведет к отмене сигнала. Затем переменная `sumPageSizesTask` назначается методом `SumPageSizesAsync`. Затем обе задачи передаются в <xref:System.Threading.Tasks.Task.WhenAny(System.Threading.Tasks.Task[])?displayProperty=nameWithType>, что будет продолжено после завершения любой из этих задач.

## <a name="create-the-asynchronous-sum-page-sizes-method"></a>Создание метода асинхронного суммирования размеров страниц

Добавьте метод `Main` под методом `SumPageSizesAsync`.

```csharp
static async Task SumPageSizesAsync()
{
    var stopwatch = Stopwatch.StartNew();

    int total = 0;
    foreach (string url in s_urlList)
    {
        int contentLength = await ProcessUrlAsync(url, s_client, s_cts.Token);
        total += contentLength;
    }

    stopwatch.Stop();

    Console.WriteLine($"\nTotal bytes returned:  {total:#,#}");
    Console.WriteLine($"Elapsed time:          {stopwatch.Elapsed}\n");
}
```

Метод начинается с создания экземпляра и запуска <xref:System.Diagnostics.Stopwatch>. Затем он просматривает каждый URL-адрес в `s_urlList` и вызывает `ProcessUrlAsync`. При каждой итерации в метод `ProcessUrlAsync` передается `s_cts.Token`, а код возвращает <xref:System.Threading.Tasks.Task%601>, где `TResult` является целым числом.

```csharp
int total = 0;
foreach (string url in s_urlList)
{
    int contentLength = await ProcessUrlAsync(url, s_client, s_cts.Token);
    total += contentLength;
}
```

## <a name="add-process-method"></a>Добавление метода обработки

Добавьте приведенный ниже метод `ProcessUrlAsync` после метода `SumPageSizesAsync`.

```csharp
static async Task<int> ProcessUrlAsync(string url, HttpClient client, CancellationToken token)
{
    HttpResponseMessage response = await client.GetAsync(url, token);
    byte[] content = await response.Content.ReadAsByteArrayAsync(token);
    Console.WriteLine($"{url,-60} {content.Length,10:#,#}");

    return content.Length;
}
```

Для любого заданного URL-адреса метод будет использовать экземпляр `client`, предоставленный для получения ответа в качестве `byte[]`. <xref:System.Threading.CancellationToken> экземпляр передается в методы <xref:System.Net.Http.HttpClient.GetAsync(System.String,System.Threading.CancellationToken)?displayProperty=nameWithType> и <xref:System.Net.Http.HttpContent.ReadAsByteArrayAsync(System.Threading.CancellationToken)?displayProperty=nameWithType>. `token` используется для регистрации запрошенной отмены. Длина возвращается после того, как URL-адрес и длина записываются в консоль.

### <a name="example-application-output"></a>Пример выходных данных приложения

```console
Application started.
Press the ENTER key to cancel...

https://docs.microsoft.com                                       37,357
https://docs.microsoft.com/aspnet/core                           85,589
https://docs.microsoft.com/azure                                398,939
https://docs.microsoft.com/azure/devops                          73,663
https://docs.microsoft.com/dotnet                                67,452
https://docs.microsoft.com/dynamics365                           48,582
https://docs.microsoft.com/education                             22,924

ENTER key pressed: cancelling downloads.

Application ending.
```

## <a name="complete-example"></a>Полный пример

Приведенный ниже код — это полный текст файла *Program.cs* для примера.

:::code language="csharp" source="snippets/cancel-tasks/cancel-tasks/Program.cs":::

## <a name="see-also"></a>См. также раздел

- <xref:System.Threading.CancellationToken>
- <xref:System.Threading.CancellationTokenSource>
- [Асинхронное программирование с использованием ключевых слов Async и Await (C#)](index.md)

## <a name="next-steps"></a>Дальнейшие действия

> [!div class="nextstepaction"]
> [Отмена асинхронных задач после определенного периода времени (C#)](cancel-async-tasks-after-a-period-of-time.md)
