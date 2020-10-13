---
title: Обработка асинхронных задач по мере завершения
description: В этом примере показано, как использовать Task.WhenAny в C# для запуска нескольких задач и обработки их результатов по мере завершения, а не в порядке запуска.
ms.date: 08/19/2020
ms.assetid: 25331850-35a7-43b3-ab76-3908e4346b9d
ms.openlocfilehash: 860e94a9c3973ce56e7321741a1136f752aa3d18
ms.sourcegitcommit: 636af37170ae75a11c4f7d1ecd770820e7dfe7bd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2020
ms.locfileid: "91805243"
---
# <a name="process-asynchronous-tasks-as-they-complete-c"></a>Обработка асинхронных задач по мере завершения (C#)

С помощью <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> можно запускать несколько задач одновременно и обрабатывать их по одной по мере завершения, а не в порядке их запуска.

В следующем примере используется запрос для создания коллекции задач. Каждая задача загружает содержимое указанного веб-сайта. В каждой итерации цикла while ожидаемый вызов <xref:System.Threading.Tasks.Task.WhenAny%2A> возвращает задачу из коллекции задач, которая первой завершает свою загрузку. Эта задача удаляется из коллекции и обрабатывается. Цикл выполняется до тех пор, пока в коллекции еще есть задачи.

## <a name="create-example-application"></a>Создание примера приложения

Создайте новое консольное приложение .NET Core. Его можно создать с помощью команды [dotnet new console](../../../../core/tools/dotnet-new.md#console) или в [Visual Studio](/visualstudio/install/install-visual-studio). Откройте файл *Program.cs* в любом редакторе кода.

### <a name="replace-using-statements"></a>Замена операторов using

Замените существующие операторы using следующими объявлениями.

```csharp
using System;
using System.Collections.Generic;
using System.Diagnostics;
using System.Linq;
using System.Net.Http;
using System.Threading.Tasks;
```

## <a name="add-fields"></a>Добавить поля

Добавьте в определение класса `Program` следующие два поля.

```csharp
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

`HttpClient` предоставляет возможность отправлять HTTP-запросы и получать HTTP-ответы. `s_urlList` содержит все URL-адреса, которые планируется обработать приложением.

## <a name="update-application-entry-point"></a>Обновление точки входа приложения

Главной точкой входа в консольное приложение является метод `Main`. Замените существующий метод следующим кодом.

```csharp
static Task Main() => SumPageSizesAsync();
```

Обновленный метод `Main` теперь считается [асинхронным методом main](../../../whats-new/csharp-7.md#async-main), который позволяет использовать асинхронную точку входа в исполняемом файле. Он выражается вызовом `SumPageSizesAsync`.

## <a name="create-the-asynchronous-sum-page-sizes-method"></a>Создание метода асинхронного суммирования размеров страниц

Добавьте метод `Main` под методом `SumPageSizesAsync`.

```csharp
static async Task SumPageSizesAsync()
{
    var stopwatch = Stopwatch.StartNew();

    IEnumerable<Task<int>> downloadTasksQuery =
        from url in s_urlList
        select ProcessUrlAsync(url, s_client);

    List<Task<int>> downloadTasks = downloadTasksQuery.ToList();

    int total = 0;
    while (downloadTasks.Any())
    {
        Task<int> finishedTask = await Task.WhenAny(downloadTasks);
        downloadTasks.Remove(finishedTask);
        total += await finishedTask;
    }

    stopwatch.Stop();

    Console.WriteLine($"\nTotal bytes returned:  {total:#,#}");
    Console.WriteLine($"Elapsed time:          {stopwatch.Elapsed}\n");
}
```

Метод начинается с создания экземпляра и запуска <xref:System.Diagnostics.Stopwatch>. Затем он включает запрос, который при выполнении создает коллекцию задач. Каждый вызов `ProcessUrlAsync` в следующем коде возвращает <xref:System.Threading.Tasks.Task%601>, где `TResult` — целое число.

```csharp
IEnumerable<Task<int>> downloadTasksQuery =
    from url in s_urlList
    select ProcessUrlAsync(url, s_client);
```

Из-за [отложенного выполнения](../../../../standard/linq/deferred-execution-example.md) с помощью LINQ для запуска каждой задачи вызывается <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType>.

```csharp
List<Task<int>> downloadTasks = downloadTasksQuery.ToList();
```

Цикл `while` выполняет следующие действия для каждой задачи в коллекции.

1. Ожидает вызов `WhenAny` для определения первой задачи в коллекции, чтобы завершить ее загрузку.

    ```csharp
    Task<int> firstFinishedTask = await Task.WhenAny(downloadTasks);
    ```

1. Удаляет эту задачу из коллекции.

    ```csharp
    downloadTasks.Remove(firstFinishedTask);
    ```

1. Ожидает `finishedTask`, возвращаемый при вызове `ProcessUrlAsync`. Переменная `finishedTask` представляет собой <xref:System.Threading.Tasks.Task%601>, где `TResult` — целое число. Задача уже завершена, но она ожидается для получения размера загруженного веб-сайта, как показано в следующем примере. В случае сбоя задачи `await` выдаст первое исключение дочернего элемента, хранящееся в `AggregateException`, в отличие от считывания свойства <xref:System.Threading.Tasks.Task%601.Result?displayProperty=nameWithType>, которое выдаст `AggregateException`.

    ```csharp
    total += await finishedTask;
    ```

## <a name="add-process-method"></a>Добавление метода обработки

Добавьте приведенный ниже метод `ProcessUrlAsync` после метода `SumPageSizesAsync`.

```csharp
static async Task<int> ProcessUrlAsync(string url, HttpClient client)
{
    byte[] content = await client.GetByteArrayAsync(url);
    Console.WriteLine($"{url,-60} {content.Length,10:#,#}");

    return content.Length;
}
```

Для любого заданного URL-адреса метод будет использовать экземпляр `client`, предоставленный для получения ответа в качестве `byte[]`. Длина возвращается после того, как URL-адрес и длина записываются в консоль.

Запустите проект несколько раз и убедитесь, что размеры скачанных файлов не всегда отображаются в одном и том же порядке.

> [!CAUTION]
> Можно использовать `WhenAny` в цикле, как описано в примере, для решения проблем, которые включают небольшое число задач. Однако когда требуется обработка большого числа задач, другие методы будут более эффективны. Дополнительные сведения и примеры см. в разделе [Обработка задач по мере их завершения](https://devblogs.microsoft.com/pfxteam/processing-tasks-as-they-complete).

## <a name="complete-example"></a>Полный пример

Приведенный ниже код — это полный текст файла *Program.cs* для примера.

:::code language="csharp" source="snippets/multiple-tasks/Program.cs":::

## <a name="see-also"></a>См. также раздел

- <xref:System.Threading.Tasks.Task.WhenAny%2A>
- [Асинхронное программирование с использованием ключевых слов Async и Await (C#)](index.md)
