---
ms.openlocfilehash: f1556fac0e8aa79c87cd5e74c1b603582ff5db1b
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160554"
---
### <a name="http-httpclient-instances-created-by-ihttpclientfactory-log-integer-status-codes"></a><span data-ttu-id="cf292-101">HTTP. Экземпляры HttpClient, созданные с помощью целочисленных кодов состояния журнала IHttpClientFactory</span><span class="sxs-lookup"><span data-stu-id="cf292-101">HTTP: HttpClient instances created by IHttpClientFactory log integer status codes</span></span>

<span data-ttu-id="cf292-102">Экземпляры <xref:System.Net.Http.HttpClient>, создаваемые <xref:System.Net.Http.IHttpClientFactory>, регистрируют коды состояния HTTP как целые числа вместо имен кодов состояния.</span><span class="sxs-lookup"><span data-stu-id="cf292-102"><xref:System.Net.Http.HttpClient> instances created by <xref:System.Net.Http.IHttpClientFactory> log HTTP status codes as integers instead of with status code names.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="cf292-103">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="cf292-103">Version introduced</span></span>

<span data-ttu-id="cf292-104">5.0 Предварительная версия 1</span><span class="sxs-lookup"><span data-stu-id="cf292-104">5.0 Preview 1</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="cf292-105">Старое поведение</span><span class="sxs-lookup"><span data-stu-id="cf292-105">Old behavior</span></span>

<span data-ttu-id="cf292-106">Ведение журнала использует текстовые описания кодов состояния HTTP.</span><span class="sxs-lookup"><span data-stu-id="cf292-106">Logging uses the textual descriptions of HTTP status codes.</span></span> <span data-ttu-id="cf292-107">Рассмотрим следующее сообщение журнала:</span><span class="sxs-lookup"><span data-stu-id="cf292-107">Consider the following log messages:</span></span>

```output
Received HTTP response after 56.0044ms - OK
End processing HTTP request after 70.0862ms - OK
```

#### <a name="new-behavior"></a><span data-ttu-id="cf292-108">Новое поведение</span><span class="sxs-lookup"><span data-stu-id="cf292-108">New behavior</span></span>

<span data-ttu-id="cf292-109">Ведение журнала использует целочисленные значения кодов состояния HTTP.</span><span class="sxs-lookup"><span data-stu-id="cf292-109">Logging uses the integer values of HTTP status codes.</span></span> <span data-ttu-id="cf292-110">Рассмотрим следующее сообщение журнала:</span><span class="sxs-lookup"><span data-stu-id="cf292-110">Consider the following log messages:</span></span>

```output
Received HTTP response after 56.0044ms - 200
End processing HTTP request after 70.0862ms - 200
```

#### <a name="reason-for-change"></a><span data-ttu-id="cf292-111">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="cf292-111">Reason for change</span></span>

<span data-ttu-id="cf292-112">Исходная настройка такого ведения журнала не согласуется с другими частями ASP.NET Core, которые всегда использовали целые значения.</span><span class="sxs-lookup"><span data-stu-id="cf292-112">The original behavior of this logging is inconsistent with other parts of ASP.NET Core that have always used integer values.</span></span> <span data-ttu-id="cf292-113">Несогласованность усложняет запросы к журналам с помощью структурированных систем ведения журналов, таких как [Elasticsearch](https://www.elastic.co/elasticsearch/).</span><span class="sxs-lookup"><span data-stu-id="cf292-113">The inconsistency makes logs difficult to query via structured logging systems such as [Elasticsearch](https://www.elastic.co/elasticsearch/).</span></span> <span data-ttu-id="cf292-114">Дополнительный контекст см. в [dotnet/extensions#1549](https://github.com/dotnet/extensions/issues/1549).</span><span class="sxs-lookup"><span data-stu-id="cf292-114">For more context, see [dotnet/extensions#1549](https://github.com/dotnet/extensions/issues/1549).</span></span>

<span data-ttu-id="cf292-115">Целочисленные значения дают больше гибкости по сравнению с текстом, так как позволяют выполнять запросы к диапазонам значений.</span><span class="sxs-lookup"><span data-stu-id="cf292-115">Using integer values is more flexible than text because it allows queries on ranges of values.</span></span>

<span data-ttu-id="cf292-116">Рассматривалось добавление еще одного значения журнала для записи целочисленного кода состояния.</span><span class="sxs-lookup"><span data-stu-id="cf292-116">Adding another log value to capture the integer status code was considered.</span></span> <span data-ttu-id="cf292-117">К сожалению, это могло привести к несогласованности с остальной частью ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="cf292-117">Unfortunately, doing so would introduce another inconsistency with the rest of ASP.NET Core.</span></span> <span data-ttu-id="cf292-118">При ведении журнала HttpClient и сервера/хостинга HTTP уже используется одно и то же имя ключа `StatusCode`.</span><span class="sxs-lookup"><span data-stu-id="cf292-118">HttpClient logging and HTTP server/hosting logging use the same `StatusCode` key name already.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="cf292-119">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="cf292-119">Recommended action</span></span>

<span data-ttu-id="cf292-120">Лучшим вариантом является обновление запросов журнала для использования целочисленных значений кодов состояния.</span><span class="sxs-lookup"><span data-stu-id="cf292-120">The best option is to update logging queries to use the integer values of status codes.</span></span> <span data-ttu-id="cf292-121">Этот вариант может вызвать некоторые трудности при записи запросов в нескольких версиях ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="cf292-121">This option may cause some difficulty writing queries across multiple ASP.NET Core versions.</span></span> <span data-ttu-id="cf292-122">Однако использование целых чисел для этой цели предоставляет больше возможностей для запросов журналов.</span><span class="sxs-lookup"><span data-stu-id="cf292-122">However, using integers for this purpose is much more flexible for querying logs.</span></span>

<span data-ttu-id="cf292-123">Если необходимо обеспечить совместимость со старым поведением и использовать текстовые коды состояния, замените `IHttpClientFactory` собственными:</span><span class="sxs-lookup"><span data-stu-id="cf292-123">If you need to force compatibility with the old behavior and use textual status codes, replace the `IHttpClientFactory` logging with your own:</span></span>

1. <span data-ttu-id="cf292-124">Скопируйте в проект версии .NET Core 3.1 следующих классов:</span><span class="sxs-lookup"><span data-stu-id="cf292-124">Copy the .NET Core 3.1 versions of the following classes into your project:</span></span>

    * [<span data-ttu-id="cf292-125">LoggingHttpMessageHandlerBuilderFilter</span><span class="sxs-lookup"><span data-stu-id="cf292-125">LoggingHttpMessageHandlerBuilderFilter</span></span>](https://github.com/dotnet/extensions/blob/release/3.1/src/HttpClientFactory/Http/src/Logging/LoggingHttpMessageHandlerBuilderFilter.cs)
    * [<span data-ttu-id="cf292-126">LoggingHttpMessageHandler</span><span class="sxs-lookup"><span data-stu-id="cf292-126">LoggingHttpMessageHandler</span></span>](https://github.com/dotnet/extensions/blob/release/3.1/src/HttpClientFactory/Http/src/Logging/LoggingHttpMessageHandler.cs)
    * [<span data-ttu-id="cf292-127">LoggingScopeHttpMessageHandler</span><span class="sxs-lookup"><span data-stu-id="cf292-127">LoggingScopeHttpMessageHandler</span></span>](https://github.com/dotnet/extensions/blob/release/3.1/src/HttpClientFactory/Http/src/Logging/LoggingScopeHttpMessageHandler.cs)
    * [<span data-ttu-id="cf292-128">HttpHeadersLogValue</span><span class="sxs-lookup"><span data-stu-id="cf292-128">HttpHeadersLogValue</span></span>](https://github.com/dotnet/extensions/blob/release/3.1/src/HttpClientFactory/Http/src/Logging/HttpHeadersLogValue.cs)

1. <span data-ttu-id="cf292-129">Переименуйте классы, чтобы избежать конфликтов с открытыми типами в пакете NuGet [Microsoft.Extensions.Http](https://www.nuget.org/packages/Microsoft.Extensions.Http).</span><span class="sxs-lookup"><span data-stu-id="cf292-129">Rename the classes to avoid conflicts with public types in the [Microsoft.Extensions.Http](https://www.nuget.org/packages/Microsoft.Extensions.Http) NuGet package.</span></span>

1. <span data-ttu-id="cf292-130">Замените встроенную реализацию `LoggingHttpMessageHandlerBuilderFilter` собственной в методе `Startup.ConfigureServices` проекта.</span><span class="sxs-lookup"><span data-stu-id="cf292-130">Replace the built-in implementation of `LoggingHttpMessageHandlerBuilderFilter` with your own in the project's `Startup.ConfigureServices` method.</span></span> <span data-ttu-id="cf292-131">Пример:</span><span class="sxs-lookup"><span data-stu-id="cf292-131">For example:</span></span>

    ```csharp
    public void ConfigureServices(IServiceCollection services)
    {
        // Other service registrations go first. Code omitted for brevity.

        // Place the following after all AddHttpClient registrations.
        services.RemoveAll<IHttpMessageHandlerBuilderFilter>();

        services.AddSingleton<IHttpMessageHandlerBuilderFilter,
                              MyLoggingHttpMessageHandlerBuilderFilter>();
    }
    ```

#### <a name="category"></a><span data-ttu-id="cf292-132">Категория</span><span class="sxs-lookup"><span data-stu-id="cf292-132">Category</span></span>

<span data-ttu-id="cf292-133">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="cf292-133">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="cf292-134">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="cf292-134">Affected APIs</span></span>

<xref:System.Net.Http.HttpClient?displayProperty=nameWithType>

<!--

#### Affected APIs

`T:System.Net.Http.HttpClient`

-->
