---
title: Регистрация с Azure SDK для .NET
description: Узнайте, как включить журнал с помощью SDK Azure для библиотек клиентов .NET
ms.date: 03/20/2020
ms.custom: azure-sdk-dotnet
ms.author: casoper
author: camsoper
ms.openlocfilehash: b277045a60ef5cc065d77dad84878872dedc963e
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "81433226"
---
# <a name="logging-with-the-azure-sdk-for-net"></a><span data-ttu-id="45cb4-103">Регистрация с Azure SDK для .NET</span><span class="sxs-lookup"><span data-stu-id="45cb4-103">Logging with the Azure SDK for .NET</span></span>

<span data-ttu-id="45cb4-104">[SDK Azure](https://azure.microsoft.com/downloads/) для клиентских библиотек .NET включает в себя возможность регистрации операций библиотеки клиентов.</span><span class="sxs-lookup"><span data-stu-id="45cb4-104">The [Azure SDK](https://azure.microsoft.com/downloads/) for .NET client libraries includes the ability to log client library operations.</span></span> <span data-ttu-id="45cb4-105">Это позволяет отслеживать запросы на ввог/ои и ответы, которые библиотеки клиентов делают для служб Azure.</span><span class="sxs-lookup"><span data-stu-id="45cb4-105">This allows you to monitor I/O requests and responses that client libraries are making to Azure services.</span></span> <span data-ttu-id="45cb4-106">Как правило, журналы используются для отладки или диагностики проблем связи.</span><span class="sxs-lookup"><span data-stu-id="45cb4-106">Typically, the logs are used to debug or diagnose communication issues.</span></span> <span data-ttu-id="45cb4-107">В этой статье описаны три подхода, позволяющие вести журнал с Azure SDK для .NET:</span><span class="sxs-lookup"><span data-stu-id="45cb4-107">This article describes three approaches to enable logging with the Azure SDK for .NET:</span></span>

- <span data-ttu-id="45cb4-108">Вход в окно консоли</span><span class="sxs-lookup"><span data-stu-id="45cb4-108">Log to the console window</span></span>
- <span data-ttu-id="45cb4-109">Следы диагностики входа в .NET</span><span class="sxs-lookup"><span data-stu-id="45cb4-109">Log to .NET diagnostics traces</span></span>
- <span data-ttu-id="45cb4-110">Настройка пользовательских журналов</span><span class="sxs-lookup"><span data-stu-id="45cb4-110">Configure custom logging</span></span>

> [!IMPORTANT]
> <span data-ttu-id="45cb4-111">Эта статья распространяется на клиентские библиотеки, в которых используются самые последние версии SDK Azure для .NET.</span><span class="sxs-lookup"><span data-stu-id="45cb4-111">This article applies to client libraries that use the most recent versions of the Azure SDK for .NET.</span></span> <span data-ttu-id="45cb4-112">Чтобы узнать, поддерживается ли библиотека, обратитесь к списку [последних релизов Azure SDK.](https://azure.github.io/azure-sdk/releases/latest/index.html)</span><span class="sxs-lookup"><span data-stu-id="45cb4-112">To see if a library is supported, refer to the list of [Azure SDK latest releases](https://azure.github.io/azure-sdk/releases/latest/index.html).</span></span> <span data-ttu-id="45cb4-113">Если приложение использует старую версию библиотек клиентов Azure SDK, обратитесь к конкретным инструкциям в соответствующей документации службы.</span><span class="sxs-lookup"><span data-stu-id="45cb4-113">If your application is using an older version of the Azure SDK client libraries, refer to specific instructions in the applicable service documentation.</span></span>

## <a name="log-information"></a><span data-ttu-id="45cb4-114">Сведения о журнале</span><span class="sxs-lookup"><span data-stu-id="45cb4-114">Log information</span></span>

<span data-ttu-id="45cb4-115">SDK регистрирует следующую информацию, дезинфицируя параметры запроса и значения заголовка для удаления личных данных.</span><span class="sxs-lookup"><span data-stu-id="45cb4-115">The SDK logs the following information, sanitizing parameter query and header values to remove personal data.</span></span>

<span data-ttu-id="45cb4-116">Запись журнала запроса HTTP:</span><span class="sxs-lookup"><span data-stu-id="45cb4-116">HTTP request log entry:</span></span>

- <span data-ttu-id="45cb4-117">Уникальный ИД</span><span class="sxs-lookup"><span data-stu-id="45cb4-117">Unique ID</span></span>
- <span data-ttu-id="45cb4-118">Метод HTTP</span><span class="sxs-lookup"><span data-stu-id="45cb4-118">HTTP method</span></span>
- <span data-ttu-id="45cb4-119">URI</span><span class="sxs-lookup"><span data-stu-id="45cb4-119">URI</span></span>
- <span data-ttu-id="45cb4-120">Исходящие заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="45cb4-120">Outgoing request headers</span></span>

<span data-ttu-id="45cb4-121">Запись журнала ответов HTTP:</span><span class="sxs-lookup"><span data-stu-id="45cb4-121">HTTP response log entry:</span></span>

- <span data-ttu-id="45cb4-122">Продолжительность операции ввоза/о (время истечения)</span><span class="sxs-lookup"><span data-stu-id="45cb4-122">Duration of I/O operation (time elapsed)</span></span>
- <span data-ttu-id="45cb4-123">Request ID (ИД запроса)</span><span class="sxs-lookup"><span data-stu-id="45cb4-123">Request ID</span></span>
- <span data-ttu-id="45cb4-124">HTTP status code (Код состояния HTTP)</span><span class="sxs-lookup"><span data-stu-id="45cb4-124">HTTP status code</span></span>
- <span data-ttu-id="45cb4-125">Фраза причины HTTP</span><span class="sxs-lookup"><span data-stu-id="45cb4-125">HTTP reason phrase</span></span>
- <span data-ttu-id="45cb4-126">Заголовки ответов</span><span class="sxs-lookup"><span data-stu-id="45cb4-126">Response headers</span></span>
- <span data-ttu-id="45cb4-127">Информация об ошибке, когда это применимо</span><span class="sxs-lookup"><span data-stu-id="45cb4-127">Error information, when applicable</span></span>

<span data-ttu-id="45cb4-128">Для содержания запроса и ответа:</span><span class="sxs-lookup"><span data-stu-id="45cb4-128">For request and response content:</span></span>

- <span data-ttu-id="45cb4-129">Поток содержимого как текст или байты в зависимости от заголовка Content-Type.</span><span class="sxs-lookup"><span data-stu-id="45cb4-129">Content stream as text or bytes depending on the Content-Type header.</span></span>
     > <span data-ttu-id="45cb4-130">[! ПРИМЕЧАНИЕ- Запись контента отключена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="45cb4-130">[!NOTE} Content logging is disabled by default.</span></span> <span data-ttu-id="45cb4-131">Для включения, `Diagnostics.IsLoggingContentEnabled` `true` установить `ClientOptions`в .</span><span class="sxs-lookup"><span data-stu-id="45cb4-131">To enable it, set `Diagnostics.IsLoggingContentEnabled` to `true` in `ClientOptions`.</span></span>

<span data-ttu-id="45cb4-132">Регистры событий выходят обычно на одном из этих трех уровней:</span><span class="sxs-lookup"><span data-stu-id="45cb4-132">Event logs are output usually at one of these three levels:</span></span>

- <span data-ttu-id="45cb4-133">Информационные для событий запроса и ответа</span><span class="sxs-lookup"><span data-stu-id="45cb4-133">Informational for request and response events</span></span>
- <span data-ttu-id="45cb4-134">Предупреждение об ошибках</span><span class="sxs-lookup"><span data-stu-id="45cb4-134">Warning for errors</span></span>
- <span data-ttu-id="45cb4-135">Verbose для подробных сообщений и регистрации контента</span><span class="sxs-lookup"><span data-stu-id="45cb4-135">Verbose for detailed messages and content logging</span></span>

## <a name="enable-logging-with-built-in-methods"></a><span data-ttu-id="45cb4-136">Включить вход с помощью встроенных методов</span><span class="sxs-lookup"><span data-stu-id="45cb4-136">Enable logging with built-in methods</span></span>

<span data-ttu-id="45cb4-137">Azure SDK для библиотек клиентов .NET регистрирует события в отслеживании событий для Windows (ETW) через [ `EventSource` класс,](/dotnet/api/system.diagnostics.tracing.eventsource)что характерно для .NET.</span><span class="sxs-lookup"><span data-stu-id="45cb4-137">The Azure SDK for .NET client libraries log events to Event Tracing for Windows (ETW) via the [`EventSource` class](/dotnet/api/system.diagnostics.tracing.eventsource), which is typical for .NET.</span></span> <span data-ttu-id="45cb4-138">Источники событий позволяют использовать структурированную систему в коде приложения с минимальными накладными затратами на производительность.</span><span class="sxs-lookup"><span data-stu-id="45cb4-138">Event sources allow you to use structured logging in your application code with a minimal performance overhead.</span></span> <span data-ttu-id="45cb4-139">Чтобы получить доступ к этим журналам событий, необходимо зарегистрировать слушателей событий.</span><span class="sxs-lookup"><span data-stu-id="45cb4-139">To gain access to these event logs, you need to register event listeners.</span></span>

<span data-ttu-id="45cb4-140">SDK включает `Azure.Core.Diagnostics.AzureEventSourceListener` в себя класс (определенный в пакете Azure.Core NuGet), который содержит два `CreateConsoleLogger` `CreateTraceLogger`статических метода, которые упрощают всеобъемлющий журнал для вашего приложения .NET: и .</span><span class="sxs-lookup"><span data-stu-id="45cb4-140">The SDK includes the `Azure.Core.Diagnostics.AzureEventSourceListener` class (defined in the Azure.Core NuGet package), which contains two static methods that simplify comprehensive logging for your .NET application: `CreateConsoleLogger` and `CreateTraceLogger`.</span></span> <span data-ttu-id="45cb4-141">Эти методы принимают дополнительный параметр, который определяет уровень журнала.</span><span class="sxs-lookup"><span data-stu-id="45cb4-141">These methods take an optional parameter that specifies a log level.</span></span>

### <a name="log-to-the-console-window"></a><span data-ttu-id="45cb4-142">Вход в окно консоли</span><span class="sxs-lookup"><span data-stu-id="45cb4-142">Log to the console window</span></span>

<span data-ttu-id="45cb4-143">Основным принципом SDK Azure для клиентских библиотек .NET является упрощение возможности просмотра всеобъемлющих журналов в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="45cb4-143">A core tenet of the Azure SDK for .NET client libraries is to simplify the ability to view comprehensive logs in real time.</span></span> <span data-ttu-id="45cb4-144">Метод `CreateConsoleLogger` позволяет отправлять журналы в окно консоли с одной строкой кода:</span><span class="sxs-lookup"><span data-stu-id="45cb4-144">The `CreateConsoleLogger` method allows you to send logs to the console window with a single line of code:</span></span>

```csharp
using AzureEventSourceListener listener = AzureEventSourceListener.CreateConsoleLogger();
```

### <a name="log-to-diagnostic-traces"></a><span data-ttu-id="45cb4-145">Вход в диагностические следы</span><span class="sxs-lookup"><span data-stu-id="45cb4-145">Log to diagnostic traces</span></span>

<span data-ttu-id="45cb4-146">При реализации отслеживания трассировки можно использовать `CreateTraceLogger` метод для входа в[`System.Diagnostics.Tracing`](https://docs.microsoft.com/dotnet/api/system.diagnostics.tracing)стандартный механизм отслеживания событий .NET ().</span><span class="sxs-lookup"><span data-stu-id="45cb4-146">If you implement trace listeners, you can use the `CreateTraceLogger` method to log to the standard .NET event tracing mechanism ([`System.Diagnostics.Tracing`](https://docs.microsoft.com/dotnet/api/system.diagnostics.tracing)).</span></span> <span data-ttu-id="45cb4-147">Для получения дополнительной информации о отслеживании событий в .NET, [см.](https://docs.microsoft.com/dotnet/framework/debug-trace-profile/trace-listeners)</span><span class="sxs-lookup"><span data-stu-id="45cb4-147">For more information on event tracing in .NET, see [Trace Listeners](https://docs.microsoft.com/dotnet/framework/debug-trace-profile/trace-listeners).</span></span> <span data-ttu-id="45cb4-148">Этот пример определяет уровень многословного регистра:</span><span class="sxs-lookup"><span data-stu-id="45cb4-148">This example specifies a log level of verbose:</span></span>

```csharp
using AzureEventSourceListener listener = AzureEventSourceListener.CreateTraceLogger(EventLevel.Verbose);
```

## <a name="configure-custom-logging"></a><span data-ttu-id="45cb4-149">Настройка пользовательских журналов</span><span class="sxs-lookup"><span data-stu-id="45cb4-149">Configure custom logging</span></span>

<span data-ttu-id="45cb4-150">Как уже упоминалось выше, необходимо зарегистрировать слушателей событий для получения сообщений журнала от Azure SDK для .NET.</span><span class="sxs-lookup"><span data-stu-id="45cb4-150">As mentioned above, you need to register event listeners to receive log messages from the Azure SDK for .NET.</span></span> <span data-ttu-id="45cb4-151">Если вы не хотите осуществлять всеобъемлющую систему регистрации, используя один из `AzureEventSourceListener` приведенных выше упрощенных методов, можно построить экземпляр класса и передать ему функцию обратного вызова, которую вы пишете.</span><span class="sxs-lookup"><span data-stu-id="45cb4-151">If you don’t want to implement comprehensive logging using one the simplified methods above, you can construct an instance of the `AzureEventSourceListener` class and pass it a callback function that you write.</span></span> <span data-ttu-id="45cb4-152">Этот метод будет получать сообщения журнала, которые вы можете обработать, как вам нужно.</span><span class="sxs-lookup"><span data-stu-id="45cb4-152">This method will receive log messages that you can process however you need to.</span></span> <span data-ttu-id="45cb4-153">Кроме того, при построении экземпляра можно указать уровни журнала для включения.</span><span class="sxs-lookup"><span data-stu-id="45cb4-153">In addition, when you construct the instance, you can specify the log levels to include.</span></span>

<span data-ttu-id="45cb4-154">Следующий пример создает слушателя событий, который регистрируется на консоли с пользовательским сообщением и фильтруется в основные события Azure многословного уровня.</span><span class="sxs-lookup"><span data-stu-id="45cb4-154">The following example creates an event listener that logs to the console with a custom message, and is filtered to Azure core events of the level verbose.</span></span>

```csharp
using AzureEventSourceListener listener = new AzureEventSourceListener((e, message) =>
    {
        // Only log messages from Azure-Core event source
        if (e.EventSource.Name == "Azure-Core")
        {
            Console.WriteLine($"{DateTime.Now} {message}");
        }
    },
    level: EventLevel.Verbose);
```

## <a name="next-steps"></a><span data-ttu-id="45cb4-155">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="45cb4-155">Next steps</span></span>

- [<span data-ttu-id="45cb4-156">Включить журнал диагностики для приложений в службе приложений Azure</span><span class="sxs-lookup"><span data-stu-id="45cb4-156">Enable diagnostics logging for apps in Azure App Service</span></span>](https://docs.microsoft.com/azure/app-service/troubleshoot-diagnostic-logs)
- <span data-ttu-id="45cb4-157">Просмотрите параметры [регистрации и аудита безопасности Azure](https://docs.microsoft.com/azure/security/fundamentals/log-audit)</span><span class="sxs-lookup"><span data-stu-id="45cb4-157">Review [Azure security logging and auditing](https://docs.microsoft.com/azure/security/fundamentals/log-audit) options</span></span>
- <span data-ttu-id="45cb4-158">Узнайте, как работать с [журналами платформы Azure](https://docs.microsoft.com/azure/azure-monitor/platform/platform-logs-overview)</span><span class="sxs-lookup"><span data-stu-id="45cb4-158">Learn how to work with [Azure platform logs](https://docs.microsoft.com/azure/azure-monitor/platform/platform-logs-overview)</span></span>
- <span data-ttu-id="45cb4-159">Подробнее о [журнале и отслеживании ядра .NET Core](https://docs.microsoft.com/dotnet/core/diagnostics/logging-tracing)</span><span class="sxs-lookup"><span data-stu-id="45cb4-159">Read more about [.NET Core logging and tracing](https://docs.microsoft.com/dotnet/core/diagnostics/logging-tracing)</span></span>
