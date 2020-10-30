---
ms.openlocfilehash: a93856aac97af5c392a2e4698d2da42413cfc3c8
ms.sourcegitcommit: 98d20cb038669dca4a195eb39af37d22ea9d008e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2020
ms.locfileid: "92435001"
---
### <a name="aspnet-core-apps-allow-deserializing-quoted-numbers"></a><span data-ttu-id="685f9-101">Приложения ASP.NET Core поддерживают десериализацию заключенных в кавычки чисел</span><span class="sxs-lookup"><span data-stu-id="685f9-101">ASP.NET Core apps allow deserializing quoted numbers</span></span>

<span data-ttu-id="685f9-102">Начиная с версии .NET 5.0, приложения ASP.NET Core используют параметры десериализации по умолчанию, которые задаются в <xref:System.Text.Json.JsonSerializerDefaults.Web?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="685f9-102">Starting in .NET 5.0, ASP.NET Core apps use the default deserialization options as specified by <xref:System.Text.Json.JsonSerializerDefaults.Web?displayProperty=nameWithType>.</span></span> <span data-ttu-id="685f9-103">Набор параметров <xref:System.Text.Json.JsonSerializerDefaults.Web> включает параметр <xref:System.Text.Json.JsonSerializerOptions.NumberHandling> для <xref:System.Text.Json.Serialization.JsonNumberHandling.AllowReadingFromString?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="685f9-103">The <xref:System.Text.Json.JsonSerializerDefaults.Web> set of options includes setting <xref:System.Text.Json.JsonSerializerOptions.NumberHandling> to <xref:System.Text.Json.Serialization.JsonNumberHandling.AllowReadingFromString?displayProperty=nameWithType>.</span></span> <span data-ttu-id="685f9-104">Это изменение означает, что приложения ASP.NET Core будут успешно выполнять десериализацию чисел, представленных в виде строк JSON, вместо того, чтобы создавать исключение.</span><span class="sxs-lookup"><span data-stu-id="685f9-104">This change means that ASP.NET Core apps will successfully deserialize numbers that are represented as JSON strings, instead of throwing an exception.</span></span>

#### <a name="change-description"></a><span data-ttu-id="685f9-105">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="685f9-105">Change description</span></span>

<span data-ttu-id="685f9-106">В .NET Core версий с 3.0 по 3.1 <xref:System.Text.Json.JsonSerializer> во время десериализации вызывает исключение <xref:System.Text.Json.JsonException>, если в полезных данных JSON обнаруживается число в кавычках.</span><span class="sxs-lookup"><span data-stu-id="685f9-106">In .NET Core 3.0 - 3.1, <xref:System.Text.Json.JsonSerializer> throws a <xref:System.Text.Json.JsonException> during deserialization if it encounters a quoted number in a JSON payload.</span></span> <span data-ttu-id="685f9-107">Заключенные в кавычки числа используются для сопоставления с числовыми свойствами в графах объектов.</span><span class="sxs-lookup"><span data-stu-id="685f9-107">The quoted numbers are used to map with number properties in object graphs.</span></span> <span data-ttu-id="685f9-108">В .NET Core версий с 3.0 по 3.1 числа считываются только из токенов <xref:System.Text.Json.JsonTokenType.Number?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="685f9-108">In .NET Core 3.0 - 3.1, numbers are only read from <xref:System.Text.Json.JsonTokenType.Number?displayProperty=nameWithType> tokens.</span></span>

<span data-ttu-id="685f9-109">Начиная с версии .NET 5.0, заключенные в кавычки числа в полезных данных JSON считаются допустимыми по умолчанию для приложений ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="685f9-109">Starting in .NET 5.0, quoted numbers in JSON payloads are considered valid, by default, for ASP.NET Core apps.</span></span> <span data-ttu-id="685f9-110">Во время десериализации заключенных в кавычки чисел исключение не создается.</span><span class="sxs-lookup"><span data-stu-id="685f9-110">No exception is thrown during deserialization of quoted numbers.</span></span>

> [!TIP]
>
> - <span data-ttu-id="685f9-111">При этом не изменяется поведение для заданного по умолчанию изолированного <xref:System.Text.Json.JsonSerializer> или <xref:System.Text.Json.JsonSerializerOptions>.</span><span class="sxs-lookup"><span data-stu-id="685f9-111">There is no behavior change for the default, standalone <xref:System.Text.Json.JsonSerializer> or <xref:System.Text.Json.JsonSerializerOptions>.</span></span>
> - <span data-ttu-id="685f9-112">С технической точки зрения это изменение не является критическим, поскольку оно снижает, а не повышает степень строгости сценария (т. е. в результате этого изменения приведение числа из строки JSON завершается успешно и не приводит к созданию исключения).</span><span class="sxs-lookup"><span data-stu-id="685f9-112">This is technically not a breaking change, since it makes a scenario more permissive instead of more restrictive (that is, it succeeds in coercing a number from a JSON string instead of throwing an exception).</span></span> <span data-ttu-id="685f9-113">Тем не менее, это изменение поведения является существенным и затрагивает многие приложения ASP.NET Core, в связи с чем мы приводим его описание.</span><span class="sxs-lookup"><span data-stu-id="685f9-113">However, since this is a significant behavioral change that affects many ASP.NET Core apps, it is documented here.</span></span>
> - <span data-ttu-id="685f9-114">Методы расширения <xref:System.Net.Http.Json.HttpClientJsonExtensions.GetFromJsonAsync%2A?displayProperty=nameWithType> и <xref:System.Net.Http.Json.HttpContentJsonExtensions.ReadFromJsonAsync%2A?displayProperty=nameWithType> также используют набор параметров сериализации <xref:System.Text.Json.JsonSerializerDefaults.Web>.</span><span class="sxs-lookup"><span data-stu-id="685f9-114">The <xref:System.Net.Http.Json.HttpClientJsonExtensions.GetFromJsonAsync%2A?displayProperty=nameWithType> and <xref:System.Net.Http.Json.HttpContentJsonExtensions.ReadFromJsonAsync%2A?displayProperty=nameWithType> extension methods also use the <xref:System.Text.Json.JsonSerializerDefaults.Web> set of serialization options.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="685f9-115">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="685f9-115">Version introduced</span></span>

<span data-ttu-id="685f9-116">5.0</span><span class="sxs-lookup"><span data-stu-id="685f9-116">5.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="685f9-117">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="685f9-117">Reason for change</span></span>

<span data-ttu-id="685f9-118">Несколько пользователей запросили возможность менее ограничивающей обработки чисел в <xref:System.Text.Json.JsonSerializer>.</span><span class="sxs-lookup"><span data-stu-id="685f9-118">Multiple users have requested an option for more permissive number handling in <xref:System.Text.Json.JsonSerializer>.</span></span> <span data-ttu-id="685f9-119">Это указывает на то, что многие поставщики объектов JSON (например, служб в Интернете) используют заключенные в кавычки числа.</span><span class="sxs-lookup"><span data-stu-id="685f9-119">This feedback indicates that many JSON producers (for example, services across the web) emit quoted numbers.</span></span> <span data-ttu-id="685f9-120">Поддержка чтения (десериализации) заключенных в кавычки чисел в приложениях .NET позволяет по умолчанию успешно анализировать эти полезные данные в веб-контексте.</span><span class="sxs-lookup"><span data-stu-id="685f9-120">By allowing quoted numbers to be read (deserialized), .NET apps can successfully parse these payloads, by default, in web contexts.</span></span> <span data-ttu-id="685f9-121">Эта конфигурация предоставляется с помощью <xref:System.Text.Json.JsonSerializerDefaults.Web?displayProperty=nameWithType>, что позволяет указывать одни и те же параметры на разных уровнях приложения, например для клиента, сервера и общедоступного уровня.</span><span class="sxs-lookup"><span data-stu-id="685f9-121">The configuration is exposed via <xref:System.Text.Json.JsonSerializerDefaults.Web?displayProperty=nameWithType> so that you can specify the same options across different application layers, for example, client, server, and shared.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="685f9-122">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="685f9-122">Recommended action</span></span>

<span data-ttu-id="685f9-123">Если это изменение приводит к нарушениям в работе, например, если в вашем приложении используется строгая обработка чисел для проверки, вы можете включить предыдущее поведение.</span><span class="sxs-lookup"><span data-stu-id="685f9-123">If this change is disruptive, for example, if you depend on the strict number handling for validation, you can re-enable the previous behavior.</span></span> <span data-ttu-id="685f9-124">Присвойте параметру <xref:System.Text.Json.JsonSerializerOptions.NumberHandling?displayProperty=nameWithType> значение <xref:System.Text.Json.Serialization.JsonNumberHandling.Strict?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="685f9-124">Set the <xref:System.Text.Json.JsonSerializerOptions.NumberHandling?displayProperty=nameWithType> option to <xref:System.Text.Json.Serialization.JsonNumberHandling.Strict?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="685f9-125">Для приложений MVC и приложений веб-API ASP.NET Core этот параметр можно настроить в `Startup` с помощью следующего кода:</span><span class="sxs-lookup"><span data-stu-id="685f9-125">For ASP.NET Core MVC and web API apps, you can configure the option in `Startup` by using the following code:</span></span>

```csharp
services.AddControllers()
   .AddJsonOptions(options.NumberHandling = JsonNumberHandling.Strict);
```

#### <a name="category"></a><span data-ttu-id="685f9-126">Категория</span><span class="sxs-lookup"><span data-stu-id="685f9-126">Category</span></span>

- <span data-ttu-id="685f9-127">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="685f9-127">ASP.NET Core</span></span>
- <span data-ttu-id="685f9-128">Сериализация</span><span class="sxs-lookup"><span data-stu-id="685f9-128">Serialization</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="685f9-129">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="685f9-129">Affected APIs</span></span>

- <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A?displayProperty=fullName>

<!--

#### Affected APIs

- `Overload:System.Text.Json.JsonSerializer.Deserialize`
- `Overload:System.Text.Json.JsonSerializer.DeserializeAsync`

-->
