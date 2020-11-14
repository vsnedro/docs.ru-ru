---
title: Как сериализировать и десериализировать JSON с помощью C# для .NET
description: 'Сведения об использовании пространства имен :::no-loc(System.Text.Json)::: для сериализации и десериализации формата JSON в .NET. Содержит пример кода.'
ms.date: 11/05/2020
no-loc:
- ':::no-loc(System.Text.Json):::'
- ':::no-loc(Newtonsoft.Json):::'
zone_pivot_groups: dotnet-version
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 2c1358b2b63a92cb50b853043adbfaae23ccd897
ms.sourcegitcommit: 6bef8abde346c59771a35f4f76bf037ff61c5ba3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/06/2020
ms.locfileid: "94329876"
---
# <a name="how-to-serialize-and-deserialize-marshal-and-unmarshal-json-in-net"></a><span data-ttu-id="9fcaf-104">Как сериализировать и десериализировать (маршалирование и демаршалирование) JSON в .NET</span><span class="sxs-lookup"><span data-stu-id="9fcaf-104">How to serialize and deserialize (marshal and unmarshal) JSON in .NET</span></span>

<span data-ttu-id="9fcaf-105">Эта статья содержит сведения об использовании пространства имен <xref::::no-loc(System.Text.Json):::?displayProperty=fullName> для сериализации и десериализации в нотации объектов JavaScript (JSON) и из нее.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-105">This article shows how to use the <xref::::no-loc(System.Text.Json):::?displayProperty=fullName> namespace to serialize to and deserialize from JavaScript Object Notation (JSON).</span></span> <span data-ttu-id="9fcaf-106">Если вы переносите существующий код из `:::no-loc(Newtonsoft.Json):::`, ознакомьтесь со статьей [Переход с Newtonsoft.Json на System.Text.Json`:::no-loc(System.Text.Json):::`](system-text-json-migrate-from-newtonsoft-how-to.md).</span><span class="sxs-lookup"><span data-stu-id="9fcaf-106">If you're porting existing code from `:::no-loc(Newtonsoft.Json):::`, see [How to migrate to `:::no-loc(System.Text.Json):::`](system-text-json-migrate-from-newtonsoft-how-to.md).</span></span>

<span data-ttu-id="9fcaf-107">В направлениях и образце кода библиотека используется напрямую, а не с помощью платформы, например [ASP.NET Core](/aspnet/core/).</span><span class="sxs-lookup"><span data-stu-id="9fcaf-107">The directions and sample code use the library directly, not through a framework such as [ASP.NET Core](/aspnet/core/).</span></span>

<span data-ttu-id="9fcaf-108">Большая часть примера кода сериализации устанавливает для параметра <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> значение `true` для структурирования JSON (с отступами и пробелами для удобства чтения).</span><span class="sxs-lookup"><span data-stu-id="9fcaf-108">Most of the serialization sample code sets <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> to `true` to "pretty-print" the JSON (with indentation and whitespace for human readability).</span></span> <span data-ttu-id="9fcaf-109">При использовании в рабочей среде для этого параметра обычно принимается значение по умолчанию `false`.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-109">For production use, you would typically accept the default value of `false` for this setting.</span></span>

<span data-ttu-id="9fcaf-110">Примеры кода относятся к следующему классу и его вариантам:</span><span class="sxs-lookup"><span data-stu-id="9fcaf-110">The code examples refer to the following class and variants of it:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

## <a name="namespaces"></a><span data-ttu-id="9fcaf-111">Пространства имен</span><span class="sxs-lookup"><span data-stu-id="9fcaf-111">Namespaces</span></span>

<span data-ttu-id="9fcaf-112">Пространство имен <xref::::no-loc(System.Text.Json):::> содержит все точки входа и основные типы.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-112">The <xref::::no-loc(System.Text.Json):::> namespace contains all the entry points and the main types.</span></span> <span data-ttu-id="9fcaf-113">Пространство имен <xref::::no-loc(System.Text.Json):::.Serialization> содержит атрибуты и интерфейсы API для сложных сценариев и настройки, характерной для сериализации и десериализации.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-113">The <xref::::no-loc(System.Text.Json):::.Serialization> namespace contains attributes and APIs for advanced scenarios and customization specific to serialization and deserialization.</span></span> <span data-ttu-id="9fcaf-114">В примерах кода, приведенных в этой статье, для одного или обоих пространств имен необходимо добавить директивы `using`:</span><span class="sxs-lookup"><span data-stu-id="9fcaf-114">The code examples shown in this article require `using` directives for one or both of these namespaces:</span></span>

```csharp
using :::no-loc(System.Text.Json):::;
using :::no-loc(System.Text.Json):::.Serialization;
```

<span data-ttu-id="9fcaf-115">Атрибуты из пространства имен <xref:System.Runtime.Serialization> не поддерживаются в `:::no-loc(System.Text.Json):::`.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-115">Attributes from the <xref:System.Runtime.Serialization> namespace aren't supported in `:::no-loc(System.Text.Json):::`.</span></span>

## <a name="how-to-write-net-objects-to-json-serialize"></a><span data-ttu-id="9fcaf-116">Как записать объекты .NET в JSON (сериализация)</span><span class="sxs-lookup"><span data-stu-id="9fcaf-116">How to write .NET objects to JSON (serialize)</span></span>

<span data-ttu-id="9fcaf-117">Чтобы записать JSON в строку или в файл, вызовите метод <xref::::no-loc(System.Text.Json):::.JsonSerializer.Serialize%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-117">To write JSON to a string or to a file, call the <xref::::no-loc(System.Text.Json):::.JsonSerializer.Serialize%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="9fcaf-118">В следующем примере показано создание JSON в виде строки:</span><span class="sxs-lookup"><span data-stu-id="9fcaf-118">The following example creates JSON as a string:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToString.cs?name=SnippetSerialize)]

<span data-ttu-id="9fcaf-119">В примере ниже для создания JSON-файла используется синхронный код:</span><span class="sxs-lookup"><span data-stu-id="9fcaf-119">The following example uses synchronous code to create a JSON file:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToFile.cs?name=SnippetSerialize)]

<span data-ttu-id="9fcaf-120">В следующем примере для создания JSON-файла используется асинхронный код:</span><span class="sxs-lookup"><span data-stu-id="9fcaf-120">The following example uses asynchronous code to create a JSON file:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToFileAsync.cs?name=SnippetSerialize)]

<span data-ttu-id="9fcaf-121">В предыдущих примерах для сериализуемого типа используется определение типа.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-121">The preceding examples use type inference for the type being serialized.</span></span> <span data-ttu-id="9fcaf-122">Перегрузка `Serialize()` принимает параметр универсального типа:</span><span class="sxs-lookup"><span data-stu-id="9fcaf-122">An overload of `Serialize()` takes a generic type parameter:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToString.cs?name=SnippetSerializeWithGenericParameter)]

### <a name="serialization-example"></a><span data-ttu-id="9fcaf-123">Пример сериализации</span><span class="sxs-lookup"><span data-stu-id="9fcaf-123">Serialization example</span></span>

<span data-ttu-id="9fcaf-124">Ниже приведен пример класса, который содержит свойства типа коллекции и определяемый пользователем тип:</span><span class="sxs-lookup"><span data-stu-id="9fcaf-124">Here's an example class that contains collection-type properties and a user-defined type:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPOCOs)]

> [!TIP]
> <span data-ttu-id="9fcaf-125">POCO означает [традиционный объект среды CLR](https://en.wikipedia.org/wiki/Plain_old_CLR_object).</span><span class="sxs-lookup"><span data-stu-id="9fcaf-125">"POCO" stands for [plain old CLR object](https://en.wikipedia.org/wiki/Plain_old_CLR_object).</span></span> <span data-ttu-id="9fcaf-126">POCO — это тип .NET, который не зависит от каких-либо типов платформы, например посредством наследования или атрибутов.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-126">A POCO is a .NET type that doesn't depend on any framework-specific types, for example, through inheritance or attributes.</span></span>

<span data-ttu-id="9fcaf-127">Выходные данные JSON из сериализации экземпляра предыдущего типа выглядят следующим образом.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-127">The JSON output from serializing an instance of the preceding type looks like the following example.</span></span> <span data-ttu-id="9fcaf-128">Выходные данные JSON по умолчанию сокращены:</span><span class="sxs-lookup"><span data-stu-id="9fcaf-128">The JSON output is minified by default:</span></span>

```json
{"Date":"2019-08-01T00:00:00-07:00","TemperatureCelsius":25,"Summary":"Hot","DatesAvailable":["2019-08-01T00:00:00-07:00","2019-08-02T00:00:00-07:00"],"TemperatureRanges":{"Cold":{"High":20,"Low":-10},"Hot":{"High":60,"Low":20}},"SummaryWords":["Cool","Windy","Humid"]}
```

<span data-ttu-id="9fcaf-129">В следующем примере показан тот же объект JSON, но с форматированием (т. е. структурированный с пробелами и отступами):</span><span class="sxs-lookup"><span data-stu-id="9fcaf-129">The following example shows the same JSON, but formatted (that is, pretty-printed with whitespace and indentation):</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "DatesAvailable": [
    "2019-08-01T00:00:00-07:00",
    "2019-08-02T00:00:00-07:00"
  ],
  "TemperatureRanges": {
    "Cold": {
      "High": 20,
      "Low": -10
    },
    "Hot": {
      "High": 60,
      "Low": 20
    }
  },
  "SummaryWords": [
    "Cool",
    "Windy",
    "Humid"
  ]
}
```

### <a name="serialize-to-utf-8"></a><span data-ttu-id="9fcaf-130">Сериализация в UTF-8</span><span class="sxs-lookup"><span data-stu-id="9fcaf-130">Serialize to UTF-8</span></span>

<span data-ttu-id="9fcaf-131">Чтобы выполнить сериализацию в UTF-8, вызовите метод <xref::::no-loc(System.Text.Json):::.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="9fcaf-131">To serialize to UTF-8, call the <xref::::no-loc(System.Text.Json):::.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> method:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToUtf8.cs?name=SnippetSerialize)]

<span data-ttu-id="9fcaf-132">Также доступна перегрузка <xref::::no-loc(System.Text.Json):::.JsonSerializer.Serialize%2A>, которая принимает <xref::::no-loc(System.Text.Json):::.Utf8JsonWriter>.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-132">A <xref::::no-loc(System.Text.Json):::.JsonSerializer.Serialize%2A> overload that takes a <xref::::no-loc(System.Text.Json):::.Utf8JsonWriter> is also available.</span></span>

<span data-ttu-id="9fcaf-133">Сериализация в UTF-8 происходит примерно на 5-10 % быстрее, чем при использовании строковых методов.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-133">Serializing to UTF-8 is about 5-10% faster than using the string-based methods.</span></span> <span data-ttu-id="9fcaf-134">Разница заключается в том, что байты (например, UTF-8) не нужно преобразовывать в строки (UTF-16).</span><span class="sxs-lookup"><span data-stu-id="9fcaf-134">The difference is because the bytes (as UTF-8) don't need to be converted to strings (UTF-16).</span></span>

## <a name="serialization-behavior"></a><span data-ttu-id="9fcaf-135">Поведение сериализации</span><span class="sxs-lookup"><span data-stu-id="9fcaf-135">Serialization behavior</span></span>
::: zone pivot="dotnet-5-0"

* <span data-ttu-id="9fcaf-136">По умолчанию все открытые свойства сериализуются.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-136">By default, all public properties are serialized.</span></span> <span data-ttu-id="9fcaf-137">Вы можете [указать свойства, которые нужно игнорировать](#ignore-properties).</span><span class="sxs-lookup"><span data-stu-id="9fcaf-137">You can [specify properties to ignore](#ignore-properties).</span></span>
* <span data-ttu-id="9fcaf-138">[Кодировщик по умолчанию](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) экранирует символы, не относящиеся к ASCII, символы, учитывающие HTML, в пределах диапазона ASCII и символы, которые должны быть экранированы в соответствии со [спецификацией JSON RFC 8259](https://tools.ietf.org/html/rfc8259#section-7).</span><span class="sxs-lookup"><span data-stu-id="9fcaf-138">The [default encoder](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) escapes non-ASCII characters, HTML-sensitive characters within the ASCII-range, and characters that must be escaped according to [the RFC 8259 JSON spec](https://tools.ietf.org/html/rfc8259#section-7).</span></span>
* <span data-ttu-id="9fcaf-139">По умолчанию JSON сокращается.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-139">By default, JSON is minified.</span></span> <span data-ttu-id="9fcaf-140">Вы можете [структурировать JSON](#serialize-to-formatted-json).</span><span class="sxs-lookup"><span data-stu-id="9fcaf-140">You can [pretty-print the JSON](#serialize-to-formatted-json).</span></span>
* <span data-ttu-id="9fcaf-141">По умолчанию регистр имен JSON соответствует именам в .NET.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-141">By default, casing of JSON names matches the .NET names.</span></span> <span data-ttu-id="9fcaf-142">Вы можете [настроить регистр имен JSON](#customize-json-names-and-values).</span><span class="sxs-lookup"><span data-stu-id="9fcaf-142">You can [customize JSON name casing](#customize-json-names-and-values).</span></span>
* <span data-ttu-id="9fcaf-143">По умолчанию обнаруживаются циклические ссылки и создаются исключения.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-143">By default, circular references are detected and exceptions thrown.</span></span> <span data-ttu-id="9fcaf-144">Вы можете [сохранять ссылки и обрабатывать циклические ссылки](#preserve-references-and-handle-circular-references).</span><span class="sxs-lookup"><span data-stu-id="9fcaf-144">You can [preserve references and handle circular references](#preserve-references-and-handle-circular-references).</span></span>
* <span data-ttu-id="9fcaf-145">По умолчанию [поля](../../csharp/programming-guide/classes-and-structs/fields.md) игнорируются.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-145">By default, [fields](../../csharp/programming-guide/classes-and-structs/fields.md) are ignored.</span></span> <span data-ttu-id="9fcaf-146">Вы можете [включить поля](#include-fields).</span><span class="sxs-lookup"><span data-stu-id="9fcaf-146">You can [include fields](#include-fields).</span></span>

<span data-ttu-id="9fcaf-147">При косвенном использовании :::no-loc(System.Text.Json)::: в приложении ASP.NET Core некоторые поведения по умолчанию отличаются.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-147">When you use :::no-loc(System.Text.Json)::: indirectly in an ASP.NET Core app, some default behaviors are different.</span></span> <span data-ttu-id="9fcaf-148">Дополнительные сведения см. в разделе [Стандартные параметры веб-приложений для JsonSerializerOptions](#web-defaults-for-jsonserializeroptions).</span><span class="sxs-lookup"><span data-stu-id="9fcaf-148">For more information, see [Web defaults for JsonSerializerOptions](#web-defaults-for-jsonserializeroptions).</span></span>
::: zone-end

::: zone pivot="dotnet-core-3-1"

* <span data-ttu-id="9fcaf-149">По умолчанию все открытые свойства сериализуются.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-149">By default, all public properties are serialized.</span></span> <span data-ttu-id="9fcaf-150">Вы можете [указать свойства, которые нужно игнорировать](#ignore-properties).</span><span class="sxs-lookup"><span data-stu-id="9fcaf-150">You can [specify properties to ignore](#ignore-properties).</span></span>
* <span data-ttu-id="9fcaf-151">[Кодировщик по умолчанию](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) экранирует символы, не относящиеся к ASCII, символы, учитывающие HTML, в пределах диапазона ASCII и символы, которые должны быть экранированы в соответствии со [спецификацией JSON RFC 8259](https://tools.ietf.org/html/rfc8259#section-7).</span><span class="sxs-lookup"><span data-stu-id="9fcaf-151">The [default encoder](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) escapes non-ASCII characters, HTML-sensitive characters within the ASCII-range, and characters that must be escaped according to [the RFC 8259 JSON spec](https://tools.ietf.org/html/rfc8259#section-7).</span></span>
* <span data-ttu-id="9fcaf-152">По умолчанию JSON сокращается.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-152">By default, JSON is minified.</span></span> <span data-ttu-id="9fcaf-153">Вы можете [структурировать JSON](#serialize-to-formatted-json).</span><span class="sxs-lookup"><span data-stu-id="9fcaf-153">You can [pretty-print the JSON](#serialize-to-formatted-json).</span></span>
* <span data-ttu-id="9fcaf-154">По умолчанию регистр имен JSON соответствует именам в .NET.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-154">By default, casing of JSON names matches the .NET names.</span></span> <span data-ttu-id="9fcaf-155">Вы можете [настроить регистр имен JSON](#customize-json-names-and-values).</span><span class="sxs-lookup"><span data-stu-id="9fcaf-155">You can [customize JSON name casing](#customize-json-names-and-values).</span></span>
* <span data-ttu-id="9fcaf-156">Обнаруживаются циклические ссылки и создаются исключения.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-156">Circular references are detected and exceptions thrown.</span></span>
* <span data-ttu-id="9fcaf-157">[Поля](../../csharp/programming-guide/classes-and-structs/fields.md) игнорируются.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-157">[Fields](../../csharp/programming-guide/classes-and-structs/fields.md) are ignored.</span></span>
::: zone-end

<span data-ttu-id="9fcaf-158">К поддерживаемым типам относятся:</span><span class="sxs-lookup"><span data-stu-id="9fcaf-158">Supported types include:</span></span>
::: zone pivot="dotnet-5-0"

* <span data-ttu-id="9fcaf-159">Примитивы .NET, которые сопоставляются с примитивами JavaScript, например числовыми типами, строками и логическими значениями.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-159">.NET primitives that map to JavaScript primitives, such as numeric types, strings, and Boolean.</span></span>
* <span data-ttu-id="9fcaf-160">Определяемые пользователем [объекты POCO (традиционные объекты среды CLR)](https://en.wikipedia.org/wiki/Plain_old_CLR_object).</span><span class="sxs-lookup"><span data-stu-id="9fcaf-160">User-defined [plain old CLR objects (POCOs)](https://en.wikipedia.org/wiki/Plain_old_CLR_object).</span></span>
* <span data-ttu-id="9fcaf-161">Одномерные массивы и массивы массивов (`T[][]`).</span><span class="sxs-lookup"><span data-stu-id="9fcaf-161">One-dimensional and jagged arrays (`T[][]`).</span></span>
* <span data-ttu-id="9fcaf-162">Коллекции и словари из следующих пространств имен.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-162">Collections and dictionaries from the following namespaces.</span></span>
  * <xref:System.Collections>
  * <xref:System.Collections.Generic>
  * <xref:System.Collections.Immutable>
  * <xref:System.Collections.Concurrent>
  * <xref:System.Collections.Specialized>
  * <xref:System.Collections.ObjectModel>
::: zone-end

::: zone pivot="dotnet-core-3-1"

* <span data-ttu-id="9fcaf-163">Примитивы .NET, которые сопоставляются с примитивами JavaScript, например числовыми типами, строками и логическими значениями.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-163">.NET primitives that map to JavaScript primitives, such as numeric types, strings, and Boolean.</span></span>
* <span data-ttu-id="9fcaf-164">Определяемые пользователем [объекты POCO (традиционные объекты среды CLR)](https://en.wikipedia.org/wiki/Plain_old_CLR_object).</span><span class="sxs-lookup"><span data-stu-id="9fcaf-164">User-defined [plain old CLR objects (POCOs)](https://en.wikipedia.org/wiki/Plain_old_CLR_object).</span></span>
* <span data-ttu-id="9fcaf-165">Одномерные массивы и массивы массивов (`ArrayName[][]`).</span><span class="sxs-lookup"><span data-stu-id="9fcaf-165">One-dimensional and jagged arrays (`ArrayName[][]`).</span></span>
* <span data-ttu-id="9fcaf-166">`Dictionary<string,TValue>` где `TValue` — это `object`, `JsonElement` или POCO.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-166">`Dictionary<string,TValue>` where `TValue` is `object`, `JsonElement`, or a POCO.</span></span>
* <span data-ttu-id="9fcaf-167">Коллекции из следующих пространств имен.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-167">Collections from the following namespaces.</span></span>
  * <xref:System.Collections>
  * <xref:System.Collections.Generic>
  * <xref:System.Collections.Immutable>
  * <xref:System.Collections.Concurrent>
  * <xref:System.Collections.Specialized>
  * <xref:System.Collections.ObjectModel>
::: zone-end

<span data-ttu-id="9fcaf-168">Для обработки дополнительных типов или для обеспечения функциональности, которая не поддерживается встроенными преобразователями, можно [реализовать пользовательские преобразователи](system-text-json-converters-how-to.md).</span><span class="sxs-lookup"><span data-stu-id="9fcaf-168">You can [implement custom converters](system-text-json-converters-how-to.md) to handle additional types or to provide functionality that isn't supported by the built-in converters.</span></span>

## <a name="how-to-read-json-into-net-objects-deserialize"></a><span data-ttu-id="9fcaf-169">Как считать JSON в объекты .NET (десериализация)</span><span class="sxs-lookup"><span data-stu-id="9fcaf-169">How to read JSON into .NET objects (deserialize)</span></span>

<span data-ttu-id="9fcaf-170">Чтобы выполнить десериализацию из строки или файла, вызовите метод <xref::::no-loc(System.Text.Json):::.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-170">To deserialize from a string or a file, call the <xref::::no-loc(System.Text.Json):::.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="9fcaf-171">В следующем примере показано считывание JSON из строки и создание экземпляра класса `WeatherForecastWithPOCOs`, показанного ранее для [примера сериализации](#serialization-example):</span><span class="sxs-lookup"><span data-stu-id="9fcaf-171">The following example reads JSON from a string and creates an instance of the `WeatherForecastWithPOCOs` class shown earlier for the [serialization example](#serialization-example):</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToString.cs?name=SnippetDeserialize)]

<span data-ttu-id="9fcaf-172">Чтобы выполнить десериализацию из файла с помощью синхронного кода, выполните считывание файла в строку, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="9fcaf-172">To deserialize from a file by using synchronous code, read the file into a string, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToFile.cs?name=SnippetDeserialize)]

<span data-ttu-id="9fcaf-173">Чтобы выполнить десериализацию из файла с помощью асинхронного кода, вызовите метод <xref::::no-loc(System.Text.Json):::.JsonSerializer.DeserializeAsync%2A>:</span><span class="sxs-lookup"><span data-stu-id="9fcaf-173">To deserialize from a file by using asynchronous code, call the <xref::::no-loc(System.Text.Json):::.JsonSerializer.DeserializeAsync%2A> method:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToFileAsync.cs?name=SnippetDeserialize)]

### <a name="deserialize-from-utf-8"></a><span data-ttu-id="9fcaf-174">Десериализация из UTF-8</span><span class="sxs-lookup"><span data-stu-id="9fcaf-174">Deserialize from UTF-8</span></span>

<span data-ttu-id="9fcaf-175">Для десериализации из UTF-8 вызовите перегрузку <xref::::no-loc(System.Text.Json):::.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>, которая принимает значения `Utf8JsonReader` или `ReadOnlySpan<byte>`, как показано в следующих примерах.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-175">To deserialize from UTF-8, call a <xref::::no-loc(System.Text.Json):::.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> overload that takes a `Utf8JsonReader` or a `ReadOnlySpan<byte>`, as shown in the following examples.</span></span> <span data-ttu-id="9fcaf-176">В примерах предполагается, что JSON находится в массиве байтов jsonUtf8Bytes.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-176">The examples assume the JSON is in a byte array named jsonUtf8Bytes.</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToUtf8.cs?name=SnippetDeserialize1)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToUtf8.cs?name=SnippetDeserialize2)]

## <a name="deserialization-behavior"></a><span data-ttu-id="9fcaf-177">Поведение десериализации</span><span class="sxs-lookup"><span data-stu-id="9fcaf-177">Deserialization behavior</span></span>

<span data-ttu-id="9fcaf-178">При десериализации JSON применяются следующие правила поведения:</span><span class="sxs-lookup"><span data-stu-id="9fcaf-178">The following behaviors apply when deserializing JSON:</span></span>

::: zone pivot="dotnet-5-0"

* <span data-ttu-id="9fcaf-179">По умолчанию при сопоставлении имен свойств учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-179">By default, property name matching is case-sensitive.</span></span> <span data-ttu-id="9fcaf-180">Вы можете [указать учет регистра](#case-insensitive-property-matching).</span><span class="sxs-lookup"><span data-stu-id="9fcaf-180">You can [specify case-insensitivity](#case-insensitive-property-matching).</span></span>
* <span data-ttu-id="9fcaf-181">Если JSON содержит значение для свойства, доступного только для чтения, значение игнорируется, а исключение не создается.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-181">If the JSON contains a value for a read-only property, the value is ignored and no exception is thrown.</span></span>
* <span data-ttu-id="9fcaf-182">Сериализатор не учитывает конструкторы, которые не являются открытыми.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-182">Non-public constructors are ignored by the serializer.</span></span>
* <span data-ttu-id="9fcaf-183">Поддерживается десериализация в неизменяемые объекты или свойства "только для чтения".</span><span class="sxs-lookup"><span data-stu-id="9fcaf-183">Deserialization to immutable objects or read-only properties is supported.</span></span> <span data-ttu-id="9fcaf-184">См. статью [Неизменяемые типы и записи](#immutable-types-and-records).</span><span class="sxs-lookup"><span data-stu-id="9fcaf-184">See [Immutable types and Records](#immutable-types-and-records).</span></span>
* <span data-ttu-id="9fcaf-185">По умолчанию перечисления поддерживаются в виде чисел.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-185">By default, enums are supported as numbers.</span></span> <span data-ttu-id="9fcaf-186">Вы можете [сериализовать имена перечислений в качестве строк](#enums-as-strings).</span><span class="sxs-lookup"><span data-stu-id="9fcaf-186">You can [serialize enum names as strings](#enums-as-strings).</span></span>
* <span data-ttu-id="9fcaf-187">По умолчанию поля игнорируются.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-187">By default, fields are ignored.</span></span> <span data-ttu-id="9fcaf-188">Вы можете [включить поля](#include-fields).</span><span class="sxs-lookup"><span data-stu-id="9fcaf-188">You can [include fields](#include-fields).</span></span>
* <span data-ttu-id="9fcaf-189">По умолчанию комментарии или завершающие запятые в JSON вызывают исключения.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-189">By default, comments or trailing commas in the JSON throw exceptions.</span></span> <span data-ttu-id="9fcaf-190">Вы можете разрешить [комментарии и завершающие запятые](#allow-comments-and-trailing-commas).</span><span class="sxs-lookup"><span data-stu-id="9fcaf-190">You can [allow comments and trailing commas](#allow-comments-and-trailing-commas).</span></span>
* <span data-ttu-id="9fcaf-191">Максимальная глубина [по умолчанию](xref::::no-loc(System.Text.Json):::.JsonReaderOptions.MaxDepth) равна 64.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-191">The [default maximum depth](xref::::no-loc(System.Text.Json):::.JsonReaderOptions.MaxDepth) is 64.</span></span>

<span data-ttu-id="9fcaf-192">При косвенном использовании :::no-loc(System.Text.Json)::: в приложении ASP.NET Core некоторые поведения по умолчанию отличаются.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-192">When you use :::no-loc(System.Text.Json)::: indirectly in an ASP.NET Core app, some default behaviors are different.</span></span> <span data-ttu-id="9fcaf-193">Дополнительные сведения см. в разделе [Стандартные параметры веб-приложений для JsonSerializerOptions](#web-defaults-for-jsonserializeroptions).</span><span class="sxs-lookup"><span data-stu-id="9fcaf-193">For more information, see [Web defaults for JsonSerializerOptions](#web-defaults-for-jsonserializeroptions).</span></span>
::: zone-end

::: zone pivot="dotnet-core-3-1"

* <span data-ttu-id="9fcaf-194">По умолчанию при сопоставлении имен свойств учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-194">By default, property name matching is case-sensitive.</span></span> <span data-ttu-id="9fcaf-195">Вы можете [указать учет регистра](#case-insensitive-property-matching).</span><span class="sxs-lookup"><span data-stu-id="9fcaf-195">You can [specify case-insensitivity](#case-insensitive-property-matching).</span></span> <span data-ttu-id="9fcaf-196">Приложения ASP.NET Core [указывают учет регистра по умолчанию](#web-defaults-for-jsonserializeroptions).</span><span class="sxs-lookup"><span data-stu-id="9fcaf-196">ASP.NET Core apps [specify case-insensitivity by default](#web-defaults-for-jsonserializeroptions).</span></span>
* <span data-ttu-id="9fcaf-197">Если JSON содержит значение для свойства, доступного только для чтения, значение игнорируется, а исключение не создается.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-197">If the JSON contains a value for a read-only property, the value is ignored and no exception is thrown.</span></span>
* <span data-ttu-id="9fcaf-198">Для десериализации используется конструктор без параметров, который может быть общедоступным, внутренним или частным.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-198">A parameterless constructor, which can be public, internal, or private, is used for deserialization.</span></span>
* <span data-ttu-id="9fcaf-199">Десериализация в неизменяемые объекты или свойства только для чтения не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-199">Deserialization to immutable objects or read-only properties isn't supported.</span></span>
* <span data-ttu-id="9fcaf-200">По умолчанию перечисления поддерживаются в виде чисел.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-200">By default, enums are supported as numbers.</span></span> <span data-ttu-id="9fcaf-201">Вы можете [сериализовать имена перечислений в качестве строк](#enums-as-strings).</span><span class="sxs-lookup"><span data-stu-id="9fcaf-201">You can [serialize enum names as strings](#enums-as-strings).</span></span>
* <span data-ttu-id="9fcaf-202">Поля не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-202">Fields aren't supported.</span></span>
* <span data-ttu-id="9fcaf-203">По умолчанию комментарии или завершающие запятые в JSON вызывают исключения.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-203">By default, comments or trailing commas in the JSON throw exceptions.</span></span> <span data-ttu-id="9fcaf-204">Вы можете разрешить [комментарии и завершающие запятые](#allow-comments-and-trailing-commas).</span><span class="sxs-lookup"><span data-stu-id="9fcaf-204">You can [allow comments and trailing commas](#allow-comments-and-trailing-commas).</span></span>
* <span data-ttu-id="9fcaf-205">Максимальная глубина [по умолчанию](xref::::no-loc(System.Text.Json):::.JsonReaderOptions.MaxDepth) равна 64.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-205">The [default maximum depth](xref::::no-loc(System.Text.Json):::.JsonReaderOptions.MaxDepth) is 64.</span></span>

<span data-ttu-id="9fcaf-206">При косвенном использовании :::no-loc(System.Text.Json)::: в приложении ASP.NET Core некоторые поведения по умолчанию отличаются.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-206">When you use :::no-loc(System.Text.Json)::: indirectly in an ASP.NET Core app, some default behaviors are different.</span></span> <span data-ttu-id="9fcaf-207">Дополнительные сведения см. в разделе [Стандартные параметры веб-приложений для JsonSerializerOptions](#web-defaults-for-jsonserializeroptions).</span><span class="sxs-lookup"><span data-stu-id="9fcaf-207">For more information, see [Web defaults for JsonSerializerOptions](#web-defaults-for-jsonserializeroptions).</span></span>
::: zone-end

<span data-ttu-id="9fcaf-208">Для обеспечения функциональности, которая не поддерживается встроенными преобразователями, можно [реализовать пользовательские преобразователи](system-text-json-converters-how-to.md).</span><span class="sxs-lookup"><span data-stu-id="9fcaf-208">You can [implement custom converters](system-text-json-converters-how-to.md) to provide functionality that isn't supported by the built-in converters.</span></span>

## <a name="serialize-to-formatted-json"></a><span data-ttu-id="9fcaf-209">Сериализация в форматированный JSON</span><span class="sxs-lookup"><span data-stu-id="9fcaf-209">Serialize to formatted JSON</span></span>

<span data-ttu-id="9fcaf-210">Чтобы структурировать выходные данные JSON, задайте для <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> значение `true`.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-210">To pretty-print the JSON output, set <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> to `true`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToString.cs?name=SnippetSerializePrettyPrint)]

<span data-ttu-id="9fcaf-211">Ниже приведен пример типа для сериализации и структурирования данных JSON:</span><span class="sxs-lookup"><span data-stu-id="9fcaf-211">Here's an example type to be serialized and pretty-printed JSON output:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

## <a name="include-fields"></a><span data-ttu-id="9fcaf-212">Включение полей</span><span class="sxs-lookup"><span data-stu-id="9fcaf-212">Include fields</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="9fcaf-213">Используйте глобальный параметр <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.IncludeFields?displayProperty=nameWithType> или атрибут [[JsonInclude]](xref::::no-loc(System.Text.Json):::.Serialization.JsonIncludeAttribute) для включения поля при сериализации или десериализации, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="9fcaf-213">Use the <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.IncludeFields?displayProperty=nameWithType> global setting or the [[JsonInclude]](xref::::no-loc(System.Text.Json):::.Serialization.JsonIncludeAttribute) attribute to include fields when serializing or deserializing, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/Fields.cs" highlight="15,17,19,31":::

<span data-ttu-id="9fcaf-214">Чтобы пропустить поля, предназначенные только для чтения, используйте глобальный параметр <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.IgnoreReadOnlyFields%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-214">To ignore read-only fields, use the <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.IgnoreReadOnlyFields%2A?displayProperty=nameWithType> global setting.</span></span>
::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="9fcaf-215">Поля не поддерживаются в :::no-loc(System.Text.Json)::: в .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-215">Fields are not supported in :::no-loc(System.Text.Json)::: in .NET Core 3.1.</span></span> <span data-ttu-id="9fcaf-216">Эта функция может быть предоставлена [пользовательскими преобразователями](system-text-json-converters-how-to.md).</span><span class="sxs-lookup"><span data-stu-id="9fcaf-216">[Custom converters](system-text-json-converters-how-to.md) can provide this functionality.</span></span>
::: zone-end

## <a name="customize-json-names-and-values"></a><span data-ttu-id="9fcaf-217">Настройка имен и значений JSON</span><span class="sxs-lookup"><span data-stu-id="9fcaf-217">Customize JSON names and values</span></span>

<span data-ttu-id="9fcaf-218">По умолчанию имена и ключи словарей не изменяются в выходных данных JSON, включая регистр.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-218">By default, property names and dictionary keys are unchanged in the JSON output, including case.</span></span> <span data-ttu-id="9fcaf-219">Значения перечисления представлены в виде чисел.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-219">Enum values are represented as numbers.</span></span> <span data-ttu-id="9fcaf-220">В этом разделе объясняется, как выполнить такие задачи:</span><span class="sxs-lookup"><span data-stu-id="9fcaf-220">This section explains how to:</span></span>

* <span data-ttu-id="9fcaf-221">[Настраивать отдельные имена свойств](#customize-individual-property-names).</span><span class="sxs-lookup"><span data-stu-id="9fcaf-221">[Customize individual property names](#customize-individual-property-names)</span></span>
* <span data-ttu-id="9fcaf-222">[Преобразовывать все имена свойств в неоднородный регистр](#use-camel-case-for-all-json-property-names).</span><span class="sxs-lookup"><span data-stu-id="9fcaf-222">[Convert all property names to camel case](#use-camel-case-for-all-json-property-names)</span></span>
* <span data-ttu-id="9fcaf-223">[Реализовывать политики именования пользовательских свойств](#use-a-custom-json-property-naming-policy).</span><span class="sxs-lookup"><span data-stu-id="9fcaf-223">[Implement a custom property naming policy](#use-a-custom-json-property-naming-policy)</span></span>
* <span data-ttu-id="9fcaf-224">[Преобразовывать ключи словаря в "верблюжий" стиль](#camel-case-dictionary-keys).</span><span class="sxs-lookup"><span data-stu-id="9fcaf-224">[Convert dictionary keys to camel case](#camel-case-dictionary-keys)</span></span>
* <span data-ttu-id="9fcaf-225">[Преобразовывать перечисления в строки и "верблюжий" стиль](#enums-as-strings).</span><span class="sxs-lookup"><span data-stu-id="9fcaf-225">[Convert enums to strings and camel case](#enums-as-strings)</span></span>

<span data-ttu-id="9fcaf-226">Для других сценариев, требующих специальной обработки имен и значений свойств JSON, можно [реализовать пользовательские преобразователи](system-text-json-converters-how-to.md).</span><span class="sxs-lookup"><span data-stu-id="9fcaf-226">For other scenarios that require special handling of JSON property names and values, you can [implement custom converters](system-text-json-converters-how-to.md).</span></span>

### <a name="customize-individual-property-names"></a><span data-ttu-id="9fcaf-227">Настройка отдельных имен свойств</span><span class="sxs-lookup"><span data-stu-id="9fcaf-227">Customize individual property names</span></span>

<span data-ttu-id="9fcaf-228">Чтобы задать имена отдельных свойств, используйте атрибут [[JsonPropertyName]](xref::::no-loc(System.Text.Json):::.Serialization.JsonPropertyNameAttribute).</span><span class="sxs-lookup"><span data-stu-id="9fcaf-228">To set the name of individual properties, use the [[JsonPropertyName]](xref::::no-loc(System.Text.Json):::.Serialization.JsonPropertyNameAttribute) attribute.</span></span>

<span data-ttu-id="9fcaf-229">Ниже приведен пример типа для сериализации и полученный код JSON:</span><span class="sxs-lookup"><span data-stu-id="9fcaf-229">Here's an example type to serialize and resulting JSON:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="9fcaf-230">Имя свойства, заданное этим атрибутом:</span><span class="sxs-lookup"><span data-stu-id="9fcaf-230">The property name set by this attribute:</span></span>

* <span data-ttu-id="9fcaf-231">Применяется в обоих направлениях для сериализации и десериализации.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-231">Applies in both directions, for serialization and deserialization.</span></span>
* <span data-ttu-id="9fcaf-232">Имеет приоритет над политиками именования свойств.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-232">Takes precedence over property naming policies.</span></span>

### <a name="use-camel-case-for-all-json-property-names"></a><span data-ttu-id="9fcaf-233">Использование "верблюжьего" стиля для всех имен свойств JSON</span><span class="sxs-lookup"><span data-stu-id="9fcaf-233">Use camel case for all JSON property names</span></span>

<span data-ttu-id="9fcaf-234">Чтобы использовать "верблюжий" стиль для всех имен свойств JSON, задайте для параметра <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> значение `JsonNamingPolicy.CamelCase`, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="9fcaf-234">To use camel case for all JSON property names, set <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> to `JsonNamingPolicy.CamelCase`, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundTripCamelCasePropertyNames.cs?name=Serialize)]

<span data-ttu-id="9fcaf-235">Ниже приведен пример класса для сериализации и вывода JSON.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-235">Here's an example class to serialize and JSON output:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="9fcaf-236">Политика именования свойств "верблюжьего" стиля:</span><span class="sxs-lookup"><span data-stu-id="9fcaf-236">The camel case property naming policy:</span></span>

* <span data-ttu-id="9fcaf-237">Применяется к сериализации и десериализации.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-237">Applies to serialization and deserialization.</span></span>
* <span data-ttu-id="9fcaf-238">Переопределяется атрибутами `[JsonPropertyName]`.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-238">Is overridden by `[JsonPropertyName]` attributes.</span></span> <span data-ttu-id="9fcaf-239">Именно поэтому имя свойства JSON, `Wind` в примере, не указано в "верблюжьем" стиле.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-239">This is why the JSON property name `Wind` in the example is not camel case.</span></span>

### <a name="use-a-custom-json-property-naming-policy"></a><span data-ttu-id="9fcaf-240">Использование настраиваемой политики именования свойств JSON</span><span class="sxs-lookup"><span data-stu-id="9fcaf-240">Use a custom JSON property naming policy</span></span>

<span data-ttu-id="9fcaf-241">Чтобы использовать настраиваемую политику именования свойств JSON, создайте класс, производный от <xref::::no-loc(System.Text.Json):::.JsonNamingPolicy>, и переопределите метод <xref::::no-loc(System.Text.Json):::.JsonNamingPolicy.ConvertName%2A>, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="9fcaf-241">To use a custom JSON property naming policy, create a class that derives from <xref::::no-loc(System.Text.Json):::.JsonNamingPolicy> and override the <xref::::no-loc(System.Text.Json):::.JsonNamingPolicy.ConvertName%2A> method, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/UpperCaseNamingPolicy.cs)]

<span data-ttu-id="9fcaf-242">Затем задайте для свойства <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> экземпляр класса политики именования:</span><span class="sxs-lookup"><span data-stu-id="9fcaf-242">Then set the <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> property to an instance of your naming policy class:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripPropertyNamingPolicy.cs?name=SnippetSerialize)]

<span data-ttu-id="9fcaf-243">Ниже приведен пример класса для сериализации и вывода JSON.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-243">Here's an example class to serialize and JSON output:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "DATE": "2019-08-01T00:00:00-07:00",
  "TEMPERATURECELSIUS": 25,
  "SUMMARY": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="9fcaf-244">Политика именования свойств JSON:</span><span class="sxs-lookup"><span data-stu-id="9fcaf-244">The JSON property naming policy:</span></span>

* <span data-ttu-id="9fcaf-245">Применяется к сериализации и десериализации.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-245">Applies to serialization and deserialization.</span></span>
* <span data-ttu-id="9fcaf-246">Переопределяется атрибутами `[JsonPropertyName]`.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-246">Is overridden by `[JsonPropertyName]` attributes.</span></span> <span data-ttu-id="9fcaf-247">Именно поэтому имя свойства JSON, `Wind` в примере, не указано в верхнем регистре.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-247">This is why the JSON property name `Wind` in the example is not upper case.</span></span>

### <a name="camel-case-dictionary-keys"></a><span data-ttu-id="9fcaf-248">Ключи словаря в "верблюжьем" стиле.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-248">Camel case dictionary keys</span></span>

<span data-ttu-id="9fcaf-249">Если свойство сериализуемого объекта имеет тип `Dictionary<string,TValue>`, ключи `string` можно преобразовать в "верблюжий" стиль.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-249">If a property of an object to be serialized is of type `Dictionary<string,TValue>`, the `string` keys can be converted to camel case.</span></span> <span data-ttu-id="9fcaf-250">Для этого задайте для параметра <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.DictionaryKeyPolicy> значение `JsonNamingPolicy.CamelCase`, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="9fcaf-250">To do that, set <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.DictionaryKeyPolicy> to `JsonNamingPolicy.CamelCase`, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCamelCaseDictionaryKeys.cs?name=SnippetSerialize)]

<span data-ttu-id="9fcaf-251">Сериализация объекта с помощью словаря с именем `TemperatureRanges`, имеющего пары "ключ-значение" `"ColdMinTemp", 20` и `"HotMinTemp", 40`, приведет к выходным данным JSON, как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="9fcaf-251">Serializing an object with a dictionary named `TemperatureRanges` that has key-value pairs `"ColdMinTemp", 20` and `"HotMinTemp", 40` would result in JSON output like the following example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "TemperatureRanges": {
    "coldMinTemp": 20,
    "hotMinTemp": 40
  }
}
```

<span data-ttu-id="9fcaf-252">Политика именования в "верблюжьем" стиле для ключей словаря применяется только к сериализации.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-252">The camel case naming policy for dictionary keys applies to serialization only.</span></span> <span data-ttu-id="9fcaf-253">При десериализации словаря ключи будут соответствовать JSON-файлу, даже если для параметра `DictionaryKeyPolicy` указано значение `JsonNamingPolicy.CamelCase`.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-253">If you deserialize a dictionary, the keys will match the JSON file even if you specify `JsonNamingPolicy.CamelCase` for the `DictionaryKeyPolicy`.</span></span>

### <a name="enums-as-strings"></a><span data-ttu-id="9fcaf-254">Перечисление в виде строк</span><span class="sxs-lookup"><span data-stu-id="9fcaf-254">Enums as strings</span></span>

<span data-ttu-id="9fcaf-255">По умолчанию перечисления сериализуются как числа.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-255">By default, enums are serialized as numbers.</span></span> <span data-ttu-id="9fcaf-256">Чтобы сериализовать имена перечислений как строки, используйте <xref::::no-loc(System.Text.Json):::.Serialization.JsonStringEnumConverter>.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-256">To serialize enum names as strings, use the <xref::::no-loc(System.Text.Json):::.Serialization.JsonStringEnumConverter>.</span></span>

<span data-ttu-id="9fcaf-257">Например, предположим, что необходимо сериализовать следующий класс, имеющий перечисление:</span><span class="sxs-lookup"><span data-stu-id="9fcaf-257">For example, suppose you need to serialize the following class that has an enum:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithEnum)]

<span data-ttu-id="9fcaf-258">Если параметр "Сводка" имеет значение `Hot`, то по умолчанию сериализованный код JSON имеет числовое значение 3:</span><span class="sxs-lookup"><span data-stu-id="9fcaf-258">If the Summary is `Hot`, by default the serialized JSON has the numeric value 3:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": 3
}
```

<span data-ttu-id="9fcaf-259">Следующий пример кода сериализует имена перечислений вместо числовых значений и преобразует имена в "верблюжий" стиль:</span><span class="sxs-lookup"><span data-stu-id="9fcaf-259">The following sample code serializes the enum names instead of the numeric values, and converts the names to camel case:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripEnumAsString.cs?name=SnippetSerialize)]

<span data-ttu-id="9fcaf-260">Итоговый код JSON выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="9fcaf-260">The resulting JSON looks like the following example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "hot"
}
```

<span data-ttu-id="9fcaf-261">Имена строк перечисления можно также десериализовать, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="9fcaf-261">Enum string names can be deserialized as well, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripEnumAsString.cs?name=SnippetDeserialize)]

## <a name="ignore-properties"></a><span data-ttu-id="9fcaf-262">Игнорирование свойств</span><span class="sxs-lookup"><span data-stu-id="9fcaf-262">Ignore properties</span></span>

<span data-ttu-id="9fcaf-263">По умолчанию все открытые свойства сериализуются.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-263">By default, all public properties are serialized.</span></span> <span data-ttu-id="9fcaf-264">Если вы не хотите, чтобы некоторые из них отображались в выходных данных JSON, у вас есть несколько вариантов.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-264">If you don't want some of them to appear in the JSON output, you have several options.</span></span> <span data-ttu-id="9fcaf-265">В этом разделе объясняется, как выполнить игнорирование:</span><span class="sxs-lookup"><span data-stu-id="9fcaf-265">This section explains how to ignore:</span></span>

::: zone pivot="dotnet-5-0"

* <span data-ttu-id="9fcaf-266">[отдельных свойств](#ignore-individual-properties);</span><span class="sxs-lookup"><span data-stu-id="9fcaf-266">[Individual properties](#ignore-individual-properties)</span></span>
* <span data-ttu-id="9fcaf-267">[всех свойств только для чтения](#ignore-all-read-only-properties);</span><span class="sxs-lookup"><span data-stu-id="9fcaf-267">[All read-only properties](#ignore-all-read-only-properties)</span></span>
* <span data-ttu-id="9fcaf-268">[всех свойств со значением NULL](#ignore-all-null-value-properties).</span><span class="sxs-lookup"><span data-stu-id="9fcaf-268">[All null-value properties](#ignore-all-null-value-properties)</span></span>
* <span data-ttu-id="9fcaf-269">[всех свойств значений по умолчанию](#ignore-all-default-value-properties);</span><span class="sxs-lookup"><span data-stu-id="9fcaf-269">[All default-value properties](#ignore-all-default-value-properties)</span></span>
::: zone-end

::: zone pivot="dotnet-core-3-1"

* <span data-ttu-id="9fcaf-270">[отдельных свойств](#ignore-individual-properties);</span><span class="sxs-lookup"><span data-stu-id="9fcaf-270">[Individual properties](#ignore-individual-properties)</span></span>
* <span data-ttu-id="9fcaf-271">[всех свойств только для чтения](#ignore-all-read-only-properties);</span><span class="sxs-lookup"><span data-stu-id="9fcaf-271">[All read-only properties](#ignore-all-read-only-properties)</span></span>
* <span data-ttu-id="9fcaf-272">[всех свойств со значением NULL](#ignore-all-null-value-properties).</span><span class="sxs-lookup"><span data-stu-id="9fcaf-272">[All null-value properties](#ignore-all-null-value-properties)</span></span>
::: zone-end

### <a name="ignore-individual-properties"></a><span data-ttu-id="9fcaf-273">Игнорирование индивидуальных свойств</span><span class="sxs-lookup"><span data-stu-id="9fcaf-273">Ignore individual properties</span></span>

<span data-ttu-id="9fcaf-274">Чтобы игнорировать отдельные свойства, используйте атрибут [[JsonIgnore]](xref::::no-loc(System.Text.Json):::.Serialization.JsonIgnoreAttribute).</span><span class="sxs-lookup"><span data-stu-id="9fcaf-274">To ignore individual properties, use the [[JsonIgnore]](xref::::no-loc(System.Text.Json):::.Serialization.JsonIgnoreAttribute) attribute.</span></span>

<span data-ttu-id="9fcaf-275">Ниже приведен пример типа для сериализации и вывода JSON.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-275">Here's an example type to serialize and JSON output:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithIgnoreAttribute)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
}
```

::: zone pivot="dotnet-5-0"
<span data-ttu-id="9fcaf-276">Можно указать условное исключение, задав свойство `Condition` атрибута [ [JsonIgnore] ](xref::::no-loc(System.Text.Json):::.Serialization.JsonIgnoreAttribute).</span><span class="sxs-lookup"><span data-stu-id="9fcaf-276">You can specify conditional exclusion by setting the [[JsonIgnore]](xref::::no-loc(System.Text.Json):::.Serialization.JsonIgnoreAttribute) attribute's `Condition` property.</span></span> <span data-ttu-id="9fcaf-277">Перечисление <xref::::no-loc(System.Text.Json):::.Serialization.JsonIgnoreCondition> предоставляет следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="9fcaf-277">The <xref::::no-loc(System.Text.Json):::.Serialization.JsonIgnoreCondition> enum provides the following options:</span></span>

* <span data-ttu-id="9fcaf-278">`Always` — свойство всегда игнорируется.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-278">`Always` - The property is always ignored.</span></span> <span data-ttu-id="9fcaf-279">Если свойство `Condition` не указано, предполагается этот параметр.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-279">If no `Condition` is specified, this option is assumed.</span></span>
* <span data-ttu-id="9fcaf-280">`Never` — свойство всегда сериализуется и десериализуется, независимо от глобальных параметров `DefaultIgnoreCondition`, `IgnoreReadOnlyProperties` и `IgnoreReadOnlyFields`.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-280">`Never` - The property is always serialized and deserialized, regardless of the `DefaultIgnoreCondition`, `IgnoreReadOnlyProperties`, and `IgnoreReadOnlyFields` global settings.</span></span>
* <span data-ttu-id="9fcaf-281">`WhenWritingDefault` — свойство не учитывается при сериализации, если оно является ссылочным типом `null` или типом значения `default`.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-281">`WhenWritingDefault` - The property is ignored on serialization if it's a reference type `null` or a value type `default`.</span></span>
* <span data-ttu-id="9fcaf-282">`WhenWritingNull` — свойство не учитывается при сериализации, если оно является ссылочным типом `null`.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-282">`WhenWritingNull` - The property is ignored on serialization if it's a reference type `null`.</span></span>

<span data-ttu-id="9fcaf-283">В следующем примере показано использование свойства `Condition` атрибута [[JsonIgnore]](xref::::no-loc(System.Text.Json):::.Serialization.JsonIgnoreAttribute):</span><span class="sxs-lookup"><span data-stu-id="9fcaf-283">The following example illustrates use of the [[JsonIgnore]](xref::::no-loc(System.Text.Json):::.Serialization.JsonIgnoreAttribute) attribute's `Condition` property:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/JsonIgnoreAttributeExample.cs" highlight="10,13,16":::
::: zone-end

### <a name="ignore-all-read-only-properties"></a><span data-ttu-id="9fcaf-284">Игнорирование всех свойств "только для чтения"</span><span class="sxs-lookup"><span data-stu-id="9fcaf-284">Ignore all read-only properties</span></span>

<span data-ttu-id="9fcaf-285">Свойство доступно только для чтения, если оно содержит открытый метод получения, но не является общим методом задания.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-285">A property is read-only if it contains a public getter but not a public setter.</span></span> <span data-ttu-id="9fcaf-286">Чтобы игнорировать при сериализации все свойства "только для чтения", задайте для параметра <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> значение `true`, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="9fcaf-286">To ignore all read-only properties when serializing, set the <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> to `true`, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeExcludeReadOnlyProperties.cs?name=SnippetSerialize)]

<span data-ttu-id="9fcaf-287">Ниже приведен пример типа для сериализации и вывода JSON.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-287">Here's an example type to serialize and JSON output:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithROProperty)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
}
```

<span data-ttu-id="9fcaf-288">Этот параметр применяется только к сериализации.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-288">This option applies only to serialization.</span></span> <span data-ttu-id="9fcaf-289">Во время десериализации свойства, доступные только для чтения, по умолчанию игнорируются.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-289">During deserialization, read-only properties are ignored by default.</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="9fcaf-290">Этот параметр применяется только к свойствам.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-290">This option applies only to properties.</span></span> <span data-ttu-id="9fcaf-291">Чтобы пропустить при [сериализации полей](#include-fields) поля, предназначенные только для чтения, используйте глобальный параметр <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.IgnoreReadOnlyFields%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-291">To ignore read-only fields when [serializing fields](#include-fields), use the <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.IgnoreReadOnlyFields%2A?displayProperty=nameWithType> global setting.</span></span>
::: zone-end

### <a name="ignore-all-null-value-properties"></a><span data-ttu-id="9fcaf-292">Игнорировать все свойства со значением NULL</span><span class="sxs-lookup"><span data-stu-id="9fcaf-292">Ignore all null-value properties</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="9fcaf-293">Чтобы игнорировать все свойства со значением NULL, задайте для параметра <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.DefaultIgnoreCondition> значение <xref::::no-loc(System.Text.Json):::.Serialization.JsonIgnoreCondition.WhenWritingNull>, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="9fcaf-293">To ignore all null-value properties, set the <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.DefaultIgnoreCondition> property to <xref::::no-loc(System.Text.Json):::.Serialization.JsonIgnoreCondition.WhenWritingNull>, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/IgnoreNullOnSerialize.cs" highlight="28":::

::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="9fcaf-294">Чтобы игнорировать при сериализации все свойства со значением NULL, задайте для параметра <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.IgnoreNullValues> значение `true`, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="9fcaf-294">To ignore all null-value properties when serializing, set the <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.IgnoreNullValues> property to `true`, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeExcludeNullValueProperties.cs?name=SnippetSerialize)]

<span data-ttu-id="9fcaf-295">Ниже приведен пример объекта для сериализации и вывода JSON.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-295">Here's an example object to serialize and JSON output:</span></span>

|<span data-ttu-id="9fcaf-296">Свойство.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-296">Property</span></span> |<span data-ttu-id="9fcaf-297">Значение</span><span class="sxs-lookup"><span data-stu-id="9fcaf-297">Value</span></span>  |
|---------|---------|
| <span data-ttu-id="9fcaf-298">Дата</span><span class="sxs-lookup"><span data-stu-id="9fcaf-298">Date</span></span>    | <span data-ttu-id="9fcaf-299">01.08.2019 г. 00:00:00 – 7:00</span><span class="sxs-lookup"><span data-stu-id="9fcaf-299">8/1/2019 12:00:00 AM -07:00</span></span>|
| <span data-ttu-id="9fcaf-300">TemperatureCelsius</span><span class="sxs-lookup"><span data-stu-id="9fcaf-300">TemperatureCelsius</span></span>| <span data-ttu-id="9fcaf-301">25</span><span class="sxs-lookup"><span data-stu-id="9fcaf-301">25</span></span> |
| <span data-ttu-id="9fcaf-302">Сводка</span><span class="sxs-lookup"><span data-stu-id="9fcaf-302">Summary</span></span>| <span data-ttu-id="9fcaf-303">null</span><span class="sxs-lookup"><span data-stu-id="9fcaf-303">null</span></span>|

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25
}
```

::: zone-end

### <a name="ignore-all-default-value-properties"></a><span data-ttu-id="9fcaf-304">Игнорирование всех свойств со значениями по умолчанию</span><span class="sxs-lookup"><span data-stu-id="9fcaf-304">Ignore all default-value properties</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="9fcaf-305">Чтобы предотвратить сериализацию значений по умолчанию в свойствах типа значения, присвойте свойству <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.DefaultIgnoreCondition> значение <xref::::no-loc(System.Text.Json):::.Serialization.JsonIgnoreCondition.WhenWritingDefault>, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="9fcaf-305">To prevent serialization of default values in value type properties, set the <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.DefaultIgnoreCondition> property to <xref::::no-loc(System.Text.Json):::.Serialization.JsonIgnoreCondition.WhenWritingDefault>, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/IgnoreValueDefaultOnSerialize.cs" highlight="28":::
::: zone-end

<span data-ttu-id="9fcaf-306">Параметр `WhenWritingDefault` также предотвращает сериализацию свойств ссылочного типа со значением NULL.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-306">The `WhenWritingDefault` setting also prevents serialization of null-value reference type properties.</span></span>

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="9fcaf-307">Для .NET Core 3.1. не существует встроенного способа предотвращения сериализации свойств с типом значения "по умолчанию" в :::no-loc(System.Text.Json):::.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-307">There is no built-in way to prevent serialization of properties with value type defaults in :::no-loc(System.Text.Json)::: in .NET Core 3.1.</span></span>
::: zone-end

## <a name="customize-character-encoding"></a><span data-ttu-id="9fcaf-308">Настройка кодировки символов</span><span class="sxs-lookup"><span data-stu-id="9fcaf-308">Customize character encoding</span></span>

<span data-ttu-id="9fcaf-309">По умолчанию сериализатор экранирует символы, отличные от ASCII.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-309">By default, the serializer escapes all non-ASCII characters.</span></span>  <span data-ttu-id="9fcaf-310">То есть он заменяет их на `\uxxxx`, где `xxxx` является кодом в кодировке Юникода символа.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-310">That is, it replaces them with `\uxxxx` where `xxxx` is the Unicode code of the character.</span></span>  <span data-ttu-id="9fcaf-311">Например, если свойству `Summary` присвоено кириллическое значение "жарко", то объект `WeatherForecast` сериализуется, как показано в этом примере:</span><span class="sxs-lookup"><span data-stu-id="9fcaf-311">For example, if the `Summary` property is set to Cyrillic жарко, the `WeatherForecast` object is serialized as shown in this example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "\u0436\u0430\u0440\u043A\u043E"
}
```

### <a name="serialize-language-character-sets"></a><span data-ttu-id="9fcaf-312">Сериализация кодировки языка</span><span class="sxs-lookup"><span data-stu-id="9fcaf-312">Serialize language character sets</span></span>

<span data-ttu-id="9fcaf-313">Чтобы сериализовать кодировки одного или нескольких языков без экранирования, укажите [диапазон символов Юникода](xref:System.Text.Unicode.UnicodeRanges) при создании экземпляра <xref:System.Text.Encodings.Web.JavaScriptEncoder?displayProperty=fullName>, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="9fcaf-313">To serialize the character set(s) of one or more languages without escaping, specify [Unicode range(s)](xref:System.Text.Unicode.UnicodeRanges) when creating an instance of <xref:System.Text.Encodings.Web.JavaScriptEncoder?displayProperty=fullName>, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetLanguageSets)]

<span data-ttu-id="9fcaf-314">Этот код не поддерживает символы кириллицы или греческого языка.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-314">This code doesn't escape Cyrillic or Greek characters.</span></span> <span data-ttu-id="9fcaf-315">Если свойству `Summary` присвоено кириллическое значение "жарко", то объект `WeatherForecast` сериализуется, как показано в этом примере:</span><span class="sxs-lookup"><span data-stu-id="9fcaf-315">If the `Summary` property is set to Cyrillic жарко, the `WeatherForecast` object is serialized as shown in this example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жарко"
}
```

<span data-ttu-id="9fcaf-316">Чтобы сериализовать все кодировки языка без экранирования, используйте <xref:System.Text.Unicode.UnicodeRanges.All?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-316">To serialize all language sets without escaping, use <xref:System.Text.Unicode.UnicodeRanges.All?displayProperty=nameWithType>.</span></span>

### <a name="serialize-specific-characters"></a><span data-ttu-id="9fcaf-317">Сериализация определенных символов</span><span class="sxs-lookup"><span data-stu-id="9fcaf-317">Serialize specific characters</span></span>

<span data-ttu-id="9fcaf-318">В качестве альтернативного способа вы можете указать отдельные символы, которые нужно разрешить, без экранирования.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-318">An alternative is to specify individual characters that you want to allow through without being escaped.</span></span> <span data-ttu-id="9fcaf-319">В следующем примере сериализуются только первые два символа слова "жарко":</span><span class="sxs-lookup"><span data-stu-id="9fcaf-319">The following example serializes only the first two characters of жарко:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetSelectedCharacters)]

<span data-ttu-id="9fcaf-320">Ниже приведен пример JSON, созданный с помощью приведенного выше кода.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-320">Here's an example of JSON produced by the preceding code:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жа\u0440\u043A\u043E"
}
```

### <a name="serialize-all-characters"></a><span data-ttu-id="9fcaf-321">Сериализация всех символов</span><span class="sxs-lookup"><span data-stu-id="9fcaf-321">Serialize all characters</span></span>

<span data-ttu-id="9fcaf-322">Чтобы минимизировать экранирование, можно использовать <xref:System.Text.Encodings.Web.JavaScriptEncoder.UnsafeRelaxedJsonEscaping?displayProperty=nameWithType>, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="9fcaf-322">To minimize escaping you can use <xref:System.Text.Encodings.Web.JavaScriptEncoder.UnsafeRelaxedJsonEscaping?displayProperty=nameWithType>, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetUnsafeRelaxed)]

> [!CAUTION]
> <span data-ttu-id="9fcaf-323">По сравнению с кодировщиком по умолчанию, кодировщик `UnsafeRelaxedJsonEscaping` более предпочтителен в отношении передачи символов без экранирования:</span><span class="sxs-lookup"><span data-stu-id="9fcaf-323">Compared to the default encoder, the `UnsafeRelaxedJsonEscaping` encoder is more permissive about allowing characters to pass through unescaped:</span></span>
>
> * <span data-ttu-id="9fcaf-324">Он не выполняет экранирование символов, учитывающих HTML, например `<`, `>`, `&` и `'`.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-324">It doesn't escape HTML-sensitive characters such as `<`, `>`, `&`, and `'`.</span></span>
> * <span data-ttu-id="9fcaf-325">Он не предоставляет никаких дополнительных средств защиты от атак с помощью XSS или раскрытия информации, которые, например, могут возникать из-за того, что клиент и сервер не согласны с *кодировкой*.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-325">It doesn't offer any additional defense-in-depth protections against XSS or information disclosure attacks, such as those which might result from the client and server disagreeing on the *charset*.</span></span>
>
> <span data-ttu-id="9fcaf-326">Используйте ненадежный кодировщик, только если известно, что клиент будет интерпретировать полученные полезные данные как JSON в кодировке UTF-8.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-326">Use the unsafe encoder only when it's known that the client will be interpreting the resulting payload as UTF-8 encoded JSON.</span></span> <span data-ttu-id="9fcaf-327">Например, его можно использовать, если сервер отправляет заголовок ответа `Content-Type: application/json; charset=utf-8`.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-327">For example, you can use it if the server is sending the response header `Content-Type: application/json; charset=utf-8`.</span></span> <span data-ttu-id="9fcaf-328">Никогда не допускайте, чтобы необработанные выходные данные `UnsafeRelaxedJsonEscaping` выводились на HTML-страницу или в элемент `<script>`.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-328">Never allow the raw `UnsafeRelaxedJsonEscaping` output to be emitted into an HTML page or a `<script>` element.</span></span>

## <a name="serialize-properties-of-derived-classes"></a><span data-ttu-id="9fcaf-329">Сериализация свойств производных классов</span><span class="sxs-lookup"><span data-stu-id="9fcaf-329">Serialize properties of derived classes</span></span>

<span data-ttu-id="9fcaf-330">Сериализация иерархии полиморфных типов не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-330">Serialization of a polymorphic type hierarchy is not supported.</span></span> <span data-ttu-id="9fcaf-331">Например, если свойство определено как интерфейс или абстрактный класс, сериализуются только свойства, определенные в интерфейсе или абстрактном классе, даже если тип среды выполнения имеет дополнительные свойства.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-331">For example, if a property is defined as an interface or an abstract class, only the properties defined on the interface or abstract class are serialized, even if the runtime type has additional properties.</span></span> <span data-ttu-id="9fcaf-332">В этом разделе описаны исключения из этого поведения.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-332">The exceptions to this behavior are explained in this section.</span></span>

<span data-ttu-id="9fcaf-333">Например, предположим, что у вас есть класс `WeatherForecast` и производный класс `WeatherForecastDerived`:</span><span class="sxs-lookup"><span data-stu-id="9fcaf-333">For example, suppose you have a `WeatherForecast` class and a derived class `WeatherForecastDerived`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFDerived)]

<span data-ttu-id="9fcaf-334">Предположим также, что аргумент типа метода `Serialize` во время компиляции `WeatherForecast`:</span><span class="sxs-lookup"><span data-stu-id="9fcaf-334">And suppose the type argument of the `Serialize` method at compile time is `WeatherForecast`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs?name=SnippetSerializeDefault)]

<span data-ttu-id="9fcaf-335">В этом сценарии свойство `WindSpeed` не сериализуется, даже если объект `weatherForecast` фактически является объектом `WeatherForecastDerived`.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-335">In this scenario, the `WindSpeed` property is not serialized even if the `weatherForecast` object is actually a `WeatherForecastDerived` object.</span></span> <span data-ttu-id="9fcaf-336">Сериализуются только свойства базового класса:</span><span class="sxs-lookup"><span data-stu-id="9fcaf-336">Only the base class properties are serialized:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

<span data-ttu-id="9fcaf-337">Это поведение предназначено для предотвращения случайного доступа к данным в производном типе, созданном во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-337">This behavior is intended to help prevent accidental exposure of data in a derived runtime-created type.</span></span>

<span data-ttu-id="9fcaf-338">Чтобы сериализовать свойства производного типа в предыдущем примере, используйте один из следующих подходов:</span><span class="sxs-lookup"><span data-stu-id="9fcaf-338">To serialize the properties of the derived type in the preceding example, use one of the following approaches:</span></span>

* <span data-ttu-id="9fcaf-339">Вызовите перегрузку <xref::::no-loc(System.Text.Json):::.JsonSerializer.Serialize%2A>, которая позволяет указать тип во время выполнения:</span><span class="sxs-lookup"><span data-stu-id="9fcaf-339">Call an overload of <xref::::no-loc(System.Text.Json):::.JsonSerializer.Serialize%2A> that lets you specify the type at run time:</span></span>

  [!code-csharp[](snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs?name=SnippetSerializeGetType)]

* <span data-ttu-id="9fcaf-340">Объявите объект, который должен быть сериализован как `object`.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-340">Declare the object to be serialized as `object`.</span></span>

  [!code-csharp[](snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs?name=SnippetSerializeObject)]

<span data-ttu-id="9fcaf-341">В предыдущем примере сценария оба подхода приводят к тому, что `WindSpeed` свойство включается в выходные данные JSON:</span><span class="sxs-lookup"><span data-stu-id="9fcaf-341">In the preceding example scenario, both approaches cause the `WindSpeed` property to be included in the JSON output:</span></span>

```json
{
  "WindSpeed": 35,
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

> [!IMPORTANT]
> <span data-ttu-id="9fcaf-342">Эти подходы обеспечивают одноэлементную сериализацию только для сериализации корневого объекта, а не для его свойств.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-342">These approaches provide polymorphic serialization only for the root object to be serialized, not for properties of that root object.</span></span>

<span data-ttu-id="9fcaf-343">Вы можете выполнить полиморфную сериализацию для объектов более низкого уровня, если вы определите их как тип `object`.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-343">You can get polymorphic serialization for lower-level objects if you define them as type `object`.</span></span> <span data-ttu-id="9fcaf-344">Например, предположим, что у класса `WeatherForecast` есть свойство `PreviousForecast`, которое может быть определено как тип `WeatherForecast` или `object`:</span><span class="sxs-lookup"><span data-stu-id="9fcaf-344">For example, suppose your `WeatherForecast` class has a property named `PreviousForecast` that can be defined as type `WeatherForecast` or `object`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPrevious)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPreviousAsObject)]

<span data-ttu-id="9fcaf-345">Если свойство `PreviousForecast` содержит экземпляр `WeatherForecastDerived`:</span><span class="sxs-lookup"><span data-stu-id="9fcaf-345">If the `PreviousForecast` property contains an instance of `WeatherForecastDerived`:</span></span>

* <span data-ttu-id="9fcaf-346">Выходные данные JSON из сериализации `WeatherForecastWithPrevious` **не содержат** `WindSpeed`.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-346">The JSON output from serializing `WeatherForecastWithPrevious` **doesn't include** `WindSpeed`.</span></span>
* <span data-ttu-id="9fcaf-347">Выходные данные JSON из сериализации `WeatherForecastWithPreviousAsObject` **включают в себя** `WindSpeed`.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-347">The JSON output from serializing `WeatherForecastWithPreviousAsObject` **includes** `WindSpeed`.</span></span>

<span data-ttu-id="9fcaf-348">Чтобы сериализовать `WeatherForecastWithPreviousAsObject`, не нужно вызывать `Serialize<object>` или `GetType`, потому что корневой объект не является объектом, который может иметь производный тип.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-348">To serialize `WeatherForecastWithPreviousAsObject`, it isn't necessary to call `Serialize<object>` or `GetType` because the root object isn't the one that may be of a derived type.</span></span> <span data-ttu-id="9fcaf-349">В следующем примере кода не вызывается `Serialize<object>` или `GetType`:</span><span class="sxs-lookup"><span data-stu-id="9fcaf-349">The following code example doesn't call `Serialize<object>` or `GetType`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs?name=SnippetSerializeSecondLevel)]

<span data-ttu-id="9fcaf-350">Приведенный выше код правильно сериализует `WeatherForecastWithPreviousAsObject`:</span><span class="sxs-lookup"><span data-stu-id="9fcaf-350">The preceding code correctly serializes `WeatherForecastWithPreviousAsObject`:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "PreviousForecast": {
    "WindSpeed": 35,
    "Date": "2019-08-01T00:00:00-07:00",
    "TemperatureCelsius": 25,
    "Summary": "Hot"
  }
}
```

<span data-ttu-id="9fcaf-351">Аналогичный подход к определению свойств `object` работает с интерфейсами.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-351">The same approach of defining properties as `object` works with interfaces.</span></span> <span data-ttu-id="9fcaf-352">Предположим, что у вас есть следующий интерфейс и реализация и вы хотите сериализовать класс со свойствами, содержащими экземпляры реализации:</span><span class="sxs-lookup"><span data-stu-id="9fcaf-352">Suppose you have the following interface and implementation, and you want to serialize a class with properties that contain implementation instances:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/IForecast.cs)]

<span data-ttu-id="9fcaf-353">Когда вы сериализуете экземпляр `Forecasts`, только `Tuesday` отображает свойство `WindSpeed`, так как `Tuesday` определяется как `object`:</span><span class="sxs-lookup"><span data-stu-id="9fcaf-353">When you serialize an instance of `Forecasts`, only `Tuesday` shows the `WindSpeed` property, because `Tuesday` is defined as `object`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs?name=SnippetSerializeInterface)]

<span data-ttu-id="9fcaf-354">В следующем примере показан код JSON, который является результатом предыдущего кода:</span><span class="sxs-lookup"><span data-stu-id="9fcaf-354">The following example shows the JSON that results from the preceding code:</span></span>

```json
{
  "Monday": {
    "Date": "2020-01-06T00:00:00-08:00",
    "TemperatureCelsius": 10,
    "Summary": "Cool"
  },
  "Tuesday": {
    "Date": "2020-01-07T00:00:00-08:00",
    "TemperatureCelsius": 11,
    "Summary": "Rainy",
    "WindSpeed": 10
  }
}
```

<span data-ttu-id="9fcaf-355">Дополнительные сведения о полиморфной **сериализации** и **десериализации** см. в статье [Миграция из :::no-loc(Newtonsoft.Json)::: в :::no-loc(System.Text.Json):::](system-text-json-migrate-from-newtonsoft-how-to.md#polymorphic-serialization).</span><span class="sxs-lookup"><span data-stu-id="9fcaf-355">For more information about polymorphic **serialization** , and for information about **deserialization** , see [How to migrate from :::no-loc(Newtonsoft.Json)::: to :::no-loc(System.Text.Json):::](system-text-json-migrate-from-newtonsoft-how-to.md#polymorphic-serialization).</span></span>

## <a name="allow-comments-and-trailing-commas"></a><span data-ttu-id="9fcaf-356">Разрешение комментариев и завершающих запятых</span><span class="sxs-lookup"><span data-stu-id="9fcaf-356">Allow comments and trailing commas</span></span>

<span data-ttu-id="9fcaf-357">По умолчанию комментарии и завершающие запятые в JSON не допускаются.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-357">By default, comments and trailing commas are not allowed in JSON.</span></span> <span data-ttu-id="9fcaf-358">Чтобы разрешить комментарии в JSON, задайте для свойства <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> значение `JsonCommentHandling.Skip`.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-358">To allow comments in the JSON, set the <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> property to `JsonCommentHandling.Skip`.</span></span>
<span data-ttu-id="9fcaf-359">Чтобы разрешить завершающие запятые, задайте для свойства <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> значение `true`.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-359">And to allow trailing commas, set the <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> property to `true`.</span></span> <span data-ttu-id="9fcaf-360">В следующем примере показано, как разрешить оба варианта:</span><span class="sxs-lookup"><span data-stu-id="9fcaf-360">The following example shows how to allow both:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/DeserializeCommasComments.cs?name=SnippetDeserialize)]

<span data-ttu-id="9fcaf-361">Ниже приведен пример JSON с комментариями и завершающей запятой:</span><span class="sxs-lookup"><span data-stu-id="9fcaf-361">Here's example JSON with comments and a trailing comma:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25, // Fahrenheit 77
  "Summary": "Hot", /* Zharko */
}
```

## <a name="case-insensitive-property-matching"></a><span data-ttu-id="9fcaf-362">Сопоставление свойств без учета регистра</span><span class="sxs-lookup"><span data-stu-id="9fcaf-362">Case-insensitive property matching</span></span>

<span data-ttu-id="9fcaf-363">По умолчанию десериализация выполняет поиск совпадения имен свойств с учетом регистра между кодом JSON и свойствами целевого объекта.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-363">By default, deserialization looks for case-sensitive property name matches between JSON and the target object properties.</span></span> <span data-ttu-id="9fcaf-364">Чтобы изменить это поведение, задайте для параметра <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> значение `true`.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-364">To change that behavior, set <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> to `true`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/DeserializeCaseInsensitive.cs?name=SnippetDeserialize)]

<span data-ttu-id="9fcaf-365">Ниже приведен пример JSON с именами свойств в "верблюжьем" стиле.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-365">Here's example JSON with camel case property names.</span></span> <span data-ttu-id="9fcaf-366">Его можно десериализовать в следующий тип, который содержит имена свойств в регистре Pascal.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-366">It can be deserialized into the following type that has Pascal case property names.</span></span>

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
}
```

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

## <a name="handle-overflow-json"></a><span data-ttu-id="9fcaf-367">Обработка переполнения JSON</span><span class="sxs-lookup"><span data-stu-id="9fcaf-367">Handle overflow JSON</span></span>

<span data-ttu-id="9fcaf-368">При десериализации в JSON могут быть получены данные, которые не представлены свойствами целевого типа.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-368">While deserializing, you might receive data in the JSON that is not represented by properties of the target type.</span></span> <span data-ttu-id="9fcaf-369">Предположим у вас есть следующий целевой тип:</span><span class="sxs-lookup"><span data-stu-id="9fcaf-369">For example, suppose your target type is this:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

<span data-ttu-id="9fcaf-370">А десериализируемым кодом JSON является:</span><span class="sxs-lookup"><span data-stu-id="9fcaf-370">And the JSON to be deserialized is this:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "Summary": "Hot",
  "DatesAvailable": [
    "2019-08-01T00:00:00-07:00",
    "2019-08-02T00:00:00-07:00"
  ],
  "SummaryWords": [
    "Cool",
    "Windy",
    "Humid"
  ]
}
```

<span data-ttu-id="9fcaf-371">При десериализации кода JSON, показанного в указанном типе, свойства `DatesAvailable` и `SummaryWords` никуда не переходят и будут потеряны.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-371">If you deserialize the JSON shown into the type shown, the `DatesAvailable` and `SummaryWords` properties have nowhere to go and are lost.</span></span> <span data-ttu-id="9fcaf-372">Для записи дополнительных данных, таких как эти свойства, примените атрибут [[JsonExtensionData]](xref::::no-loc(System.Text.Json):::.Serialization.JsonExtensionDataAttribute) к свойству типа `Dictionary<string,object>` или `Dictionary<string,JsonElement>`:</span><span class="sxs-lookup"><span data-stu-id="9fcaf-372">To capture extra data such as these properties, apply the [[JsonExtensionData]](xref::::no-loc(System.Text.Json):::.Serialization.JsonExtensionDataAttribute) attribute to a property of type `Dictionary<string,object>` or `Dictionary<string,JsonElement>`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithExtensionData)]

<span data-ttu-id="9fcaf-373">При десериализации показанного ранее JSON в этот тип данных дополнительные данные становятся парами "ключ-значение" свойства `ExtensionData`:</span><span class="sxs-lookup"><span data-stu-id="9fcaf-373">When you deserialize the JSON shown earlier into this sample type, the extra data becomes key-value pairs of the `ExtensionData` property:</span></span>

|<span data-ttu-id="9fcaf-374">Свойство.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-374">Property</span></span> |<span data-ttu-id="9fcaf-375">Значение</span><span class="sxs-lookup"><span data-stu-id="9fcaf-375">Value</span></span>  |<span data-ttu-id="9fcaf-376">Примечания</span><span class="sxs-lookup"><span data-stu-id="9fcaf-376">Notes</span></span>  |
|---------|---------|---------|
| <span data-ttu-id="9fcaf-377">Дата</span><span class="sxs-lookup"><span data-stu-id="9fcaf-377">Date</span></span>    | <span data-ttu-id="9fcaf-378">01.08.2019 г. 00:00:00 – 7:00</span><span class="sxs-lookup"><span data-stu-id="9fcaf-378">8/1/2019 12:00:00 AM -07:00</span></span>||
| <span data-ttu-id="9fcaf-379">TemperatureCelsius</span><span class="sxs-lookup"><span data-stu-id="9fcaf-379">TemperatureCelsius</span></span>| <span data-ttu-id="9fcaf-380">0</span><span class="sxs-lookup"><span data-stu-id="9fcaf-380">0</span></span> | <span data-ttu-id="9fcaf-381">Несовпадение с учетом регистра (`temperatureCelsius` в коде JSON), поэтому свойство не задано.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-381">Case-sensitive mismatch (`temperatureCelsius` in the JSON), so the property isn't set.</span></span> |
| <span data-ttu-id="9fcaf-382">Сводка</span><span class="sxs-lookup"><span data-stu-id="9fcaf-382">Summary</span></span> | <span data-ttu-id="9fcaf-383">Горячий</span><span class="sxs-lookup"><span data-stu-id="9fcaf-383">Hot</span></span> ||
| <span data-ttu-id="9fcaf-384">ExtensionData</span><span class="sxs-lookup"><span data-stu-id="9fcaf-384">ExtensionData</span></span> | <span data-ttu-id="9fcaf-385">temperatureCelsius: 25</span><span class="sxs-lookup"><span data-stu-id="9fcaf-385">temperatureCelsius: 25</span></span> |<span data-ttu-id="9fcaf-386">Так как регистр не совпадает, это свойство JSON является лишним и становится парой "ключ-значение" в словаре.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-386">Since the case didn't match, this JSON property is an extra and becomes a key-value pair in the dictionary.</span></span>|
|| <span data-ttu-id="9fcaf-387">DatesAvailable:</span><span class="sxs-lookup"><span data-stu-id="9fcaf-387">DatesAvailable:</span></span><br>  <span data-ttu-id="9fcaf-388">01.08.2019 г. 00:00:00 – 7:00</span><span class="sxs-lookup"><span data-stu-id="9fcaf-388">8/1/2019 12:00:00 AM -07:00</span></span><br><span data-ttu-id="9fcaf-389">02.08.2019 г. 00:00:00 – 7:00</span><span class="sxs-lookup"><span data-stu-id="9fcaf-389">8/2/2019 12:00:00 AM -07:00</span></span> |<span data-ttu-id="9fcaf-390">Дополнительное свойство из кода JSON преобразуется в пару "ключ-значение" с массивом в качестве объекта значения.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-390">Extra property from the JSON becomes a key-value pair, with an array as the value object.</span></span>|
| |<span data-ttu-id="9fcaf-391">SummaryWords:</span><span class="sxs-lookup"><span data-stu-id="9fcaf-391">SummaryWords:</span></span><br><span data-ttu-id="9fcaf-392">Здорово</span><span class="sxs-lookup"><span data-stu-id="9fcaf-392">Cool</span></span><br><span data-ttu-id="9fcaf-393">Ветрено</span><span class="sxs-lookup"><span data-stu-id="9fcaf-393">Windy</span></span><br><span data-ttu-id="9fcaf-394">Влажно</span><span class="sxs-lookup"><span data-stu-id="9fcaf-394">Humid</span></span> |<span data-ttu-id="9fcaf-395">Дополнительное свойство из кода JSON преобразуется в пару "ключ-значение" с массивом в качестве объекта значения.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-395">Extra property from the JSON becomes a key-value pair, with an array as the value object.</span></span>|

<span data-ttu-id="9fcaf-396">Когда целевой объект сериализуется, пары "ключ-значение" данных расширения становятся свойствами JSON точно так же, как они были во входящем коде JSON:</span><span class="sxs-lookup"><span data-stu-id="9fcaf-396">When the target object is serialized, the extension data key value pairs become JSON properties just as they were in the incoming JSON:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 0,
  "Summary": "Hot",
  "temperatureCelsius": 25,
  "DatesAvailable": [
    "2019-08-01T00:00:00-07:00",
    "2019-08-02T00:00:00-07:00"
  ],
  "SummaryWords": [
    "Cool",
    "Windy",
    "Humid"
  ]
}
```

<span data-ttu-id="9fcaf-397">Обратите внимание, что имя свойства `ExtensionData` не отображается в коде JSON.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-397">Notice that the `ExtensionData` property name doesn't appear in the JSON.</span></span> <span data-ttu-id="9fcaf-398">Такое поведение позволяет JSON выполнить круговой путь без потери дополнительных данных, которые в противном случае не будут десериализованы.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-398">This behavior lets the JSON make a round trip without losing any extra data that otherwise wouldn't be deserialized.</span></span>

## <a name="preserve-references-and-handle-circular-references"></a><span data-ttu-id="9fcaf-399">Сохранение ссылок и обработка циклических ссылок</span><span class="sxs-lookup"><span data-stu-id="9fcaf-399">Preserve references and handle circular references</span></span>

::: zone pivot="dotnet-5-0"

<span data-ttu-id="9fcaf-400">Для сохранения ссылок и обработки циклических ссылок задайте для свойства <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.ReferenceHandler%2A> значение <xref::::no-loc(System.Text.Json):::.Serialization.ReferenceHandler.Preserve%2A>.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-400">To preserve references and handle circular references, set <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.ReferenceHandler%2A> to <xref::::no-loc(System.Text.Json):::.Serialization.ReferenceHandler.Preserve%2A>.</span></span> <span data-ttu-id="9fcaf-401">Этот параметр приводит к следующему поведению:</span><span class="sxs-lookup"><span data-stu-id="9fcaf-401">This setting causes the following behavior:</span></span>

* <span data-ttu-id="9fcaf-402">При сериализации:</span><span class="sxs-lookup"><span data-stu-id="9fcaf-402">On serialize:</span></span>

  <span data-ttu-id="9fcaf-403">При написании сложных типов сериализатор также записывает свойства метаданных (`$id`, `$values`, а также `$ref`).</span><span class="sxs-lookup"><span data-stu-id="9fcaf-403">When writing complex types, the serializer also writes metadata properties (`$id`, `$values`, and `$ref`).</span></span>

* <span data-ttu-id="9fcaf-404">При десериализации:</span><span class="sxs-lookup"><span data-stu-id="9fcaf-404">On deserialize:</span></span>

  <span data-ttu-id="9fcaf-405">Ожидаются метаданные (не обязательно), и десериализатор пытается их распознать.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-405">Metadata is expected (although not mandatory), and the deserializer tries to understand it.</span></span>

<span data-ttu-id="9fcaf-406">В следующем коде показано использование параметра `Preserve`.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-406">The following code illustrates use of the `Preserve` setting.</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/PreserveReferences.cs" highlight="34":::

<span data-ttu-id="9fcaf-407">Эту функцию нельзя использовать для сохранения типов значений или неизменяемых типов.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-407">This feature can't be used to preserve value types or immutable types.</span></span> <span data-ttu-id="9fcaf-408">При десериализации экземпляр неизменяемого типа создается после считывания всех полезных данных.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-408">On deserialization, the instance of an immutable type is created after the entire payload is read.</span></span> <span data-ttu-id="9fcaf-409">Поэтому для того же экземпляра невозможно будет выполнить десериализацию, если в полезных данных JSON появляется ссылка на него.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-409">So it would be impossible to deserialize the same instance if a reference to it appears within the JSON payload.</span></span>

<span data-ttu-id="9fcaf-410">Для типов значений, неизменяемых типов и массивов ссылочные метаданные не сериализуются.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-410">For value types, immutable types, and arrays, no reference metadata is serialized.</span></span> <span data-ttu-id="9fcaf-411">Если при десериализации было найдено `$ref` или `$id`, создается исключение.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-411">On deserialization, an exception is thrown if `$ref` or `$id` is found.</span></span> <span data-ttu-id="9fcaf-412">Однако типы значений игнорируют `$id` (и `$values` для коллекций), чтобы позволить десериализацию полезных данных, сериализованных с помощью :::no-loc(Newtonsoft.Json):::.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-412">However, value types ignore `$id` (and `$values` in the case of collections) to make it possible to deserialize payloads that were serialized by using :::no-loc(Newtonsoft.Json):::.</span></span>  <span data-ttu-id="9fcaf-413">:::no-loc(Newtonsoft.Json)::: выполняет сериализацию метаданных для таких типов.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-413">:::no-loc(Newtonsoft.Json)::: does serialize metadata for such types.</span></span>

<span data-ttu-id="9fcaf-414">Для определения равенства объектов :::no-loc(System.Text.Json)::: использует свойство <xref:System.Collections.Generic.ReferenceEqualityComparer.Instance%2A?displayProperty=nameWithType>, которое при сравнении двух экземпляров объекта использует эквивалентность ссылок (<xref:System.Object.ReferenceEquals(System.Object,System.Object)?displayProperty=nameWithType>), а не эквивалентность значений (<xref:System.Object.Equals(System.Object)?displayProperty=nameWithType>).</span><span class="sxs-lookup"><span data-stu-id="9fcaf-414">To determine if objects are equal, :::no-loc(System.Text.Json)::: uses <xref:System.Collections.Generic.ReferenceEqualityComparer.Instance%2A?displayProperty=nameWithType>, which uses reference equality (<xref:System.Object.ReferenceEquals(System.Object,System.Object)?displayProperty=nameWithType>) instead of value equality (<xref:System.Object.Equals(System.Object)?displayProperty=nameWithType> when comparing two object instances.</span></span>

<span data-ttu-id="9fcaf-415">Больше о сериализации и десериализации ссылок см. в статье <xref::::no-loc(System.Text.Json):::.Serialization.ReferenceHandler.Preserve%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-415">For more information about how references are serialized and deserialized, see <xref::::no-loc(System.Text.Json):::.Serialization.ReferenceHandler.Preserve%2A?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="9fcaf-416">Класс <xref::::no-loc(System.Text.Json):::.Serialization.ReferenceResolver> определяет поведение сохранения ссылок при сериализации и десериализации.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-416">The <xref::::no-loc(System.Text.Json):::.Serialization.ReferenceResolver> class defines the behavior of preserving references on serialization and deserialization.</span></span> <span data-ttu-id="9fcaf-417">Создайте производный класс, чтобы указать настраиваемое поведение.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-417">Create a derived class to specify custom behavior.</span></span> <span data-ttu-id="9fcaf-418">Пример см. в статье [GuidReferenceResolver](https://github.com/dotnet/docs/blob/9d5e88edbd7f12be463775ffebbf07ac8415fe18/docs/standard/serialization/snippets/system-text-json-how-to-5-0/csharp/GuidReferenceResolverExample.cs).</span><span class="sxs-lookup"><span data-stu-id="9fcaf-418">For an example, see [GuidReferenceResolver](https://github.com/dotnet/docs/blob/9d5e88edbd7f12be463775ffebbf07ac8415fe18/docs/standard/serialization/snippets/system-text-json-how-to-5-0/csharp/GuidReferenceResolverExample.cs).</span></span>

::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="9fcaf-419">:::no-loc(System.Text.Json)::: в .NET Core 3.1 поддерживает сериализацию только по значению и вызывает исключение для циклических ссылок.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-419">:::no-loc(System.Text.Json)::: in .NET Core 3.1 only supports serialization by value and throws an exception for circular references.</span></span>
::: zone-end

## <a name="allow-or-write-numbers-in-quotes"></a><span data-ttu-id="9fcaf-420">Разрешение или запись чисел в кавычках</span><span class="sxs-lookup"><span data-stu-id="9fcaf-420">Allow or write numbers in quotes</span></span>

::: zone pivot="dotnet-5-0"

<span data-ttu-id="9fcaf-421">Некоторые сериализаторы кодируют числа в виде строк JSON (заключены в кавычки).</span><span class="sxs-lookup"><span data-stu-id="9fcaf-421">Some serializers encode numbers as JSON strings (surrounded by quotes).</span></span> <span data-ttu-id="9fcaf-422">Например: `{"DegreesCelsius":"23"}` вместо `{"DegreesCelsius":23}`.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-422">For example: `{"DegreesCelsius":"23"}` instead of `{"DegreesCelsius":23}`.</span></span> <span data-ttu-id="9fcaf-423">Для сериализации или принятия чисел в кавычках во всех входных данных графа объектов задайте свойство <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.NumberHandling%2A?displayProperty=nameWithType>, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="9fcaf-423">To serialize numbers in quotes or accept numbers in quotes across the entire input object graph, set <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.NumberHandling%2A?displayProperty=nameWithType> as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/QuotedNumbers.cs" highlight="27-28":::

<span data-ttu-id="9fcaf-424">Если вы используете :::no-loc(System.Text.Json)::: косвенно через ASP.NET Core, тогда заключенные в кавычки числа будут разрешены при десериализации, поскольку ASP.NET Core определяет [стандартные параметры веб-приложений](xref::::no-loc(System.Text.Json):::.JsonSerializerDefaults.Web).</span><span class="sxs-lookup"><span data-stu-id="9fcaf-424">When you use :::no-loc(System.Text.Json)::: indirectly through ASP.NET Core, quoted numbers are allowed when deserializing because ASP.NET Core specifies [web default options](xref::::no-loc(System.Text.Json):::.JsonSerializerDefaults.Web).</span></span>

<span data-ttu-id="9fcaf-425">Чтобы разрешить или записать заключенные в кавычки числа для конкретных свойств, полей или типов, используйте атрибут [[JsonNumberHandling]](xref::::no-loc(System.Text.Json):::.Serialization.JsonNumberHandlingAttribute).</span><span class="sxs-lookup"><span data-stu-id="9fcaf-425">To allow or write quoted numbers for specific properties, fields, or types, use the [[JsonNumberHandling]](xref::::no-loc(System.Text.Json):::.Serialization.JsonNumberHandlingAttribute) attribute.</span></span>
::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="9fcaf-426">:::no-loc(System.Text.Json)::: в .NET Core 3.1 не поддерживает сериализацию или десериализацию чисел, заключенных в кавычки.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-426">:::no-loc(System.Text.Json)::: in .NET Core 3.1 doesn't support serializing or deserializing numbers surrounded by quotation marks.</span></span> <span data-ttu-id="9fcaf-427">Дополнительные сведения см. в разделе [Разрешение или запись чисел в кавычках](system-text-json-migrate-from-newtonsoft-how-to.md#allow-or-write-numbers-in-quotes).</span><span class="sxs-lookup"><span data-stu-id="9fcaf-427">For more information, see [Allow or write numbers in quotes](system-text-json-migrate-from-newtonsoft-how-to.md#allow-or-write-numbers-in-quotes).</span></span>
::: zone-end

## <a name="immutable-types-and-records"></a><span data-ttu-id="9fcaf-428">Неизменяемые типы и записи</span><span class="sxs-lookup"><span data-stu-id="9fcaf-428">Immutable types and Records</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="9fcaf-429">:::no-loc(System.Text.Json)::: может использовать параметризованный конструктор, позволяющий десериализовать неизменяемый класс или структуру.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-429">:::no-loc(System.Text.Json)::: can use a parameterized constructor, which makes it possible to deserialize an immutable class or struct.</span></span> <span data-ttu-id="9fcaf-430">Если для класса существует только параметризованный конструктор, тогда будет использован этот конструктор.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-430">For a class, if the only constructor is a parameterized one, that constructor will be used.</span></span> <span data-ttu-id="9fcaf-431">Для структуры или класса с несколькими конструкторами укажите необходимый, применив атрибут [[JsonConstructor]](xref::::no-loc(System.Text.Json):::.Serialization.JsonConstructorAttribute.%23ctor%2A).</span><span class="sxs-lookup"><span data-stu-id="9fcaf-431">For a struct, or a class with multiple constructors, specify the one to use by applying the [[JsonConstructor]](xref::::no-loc(System.Text.Json):::.Serialization.JsonConstructorAttribute.%23ctor%2A) attribute.</span></span> <span data-ttu-id="9fcaf-432">Если атрибут не используется, тогда всегда применяется общедоступный конструктор без параметров.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-432">When the attribute is not used, a public parameterless constructor is always used if present.</span></span> <span data-ttu-id="9fcaf-433">Атрибут используется только с общедоступными конструкторами.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-433">The attribute can only be used with public constructors.</span></span> <span data-ttu-id="9fcaf-434">В следующем примере используется атрибут `[JsonConstructor]`.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-434">The following example uses the `[JsonConstructor]` attribute:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/ImmutableTypes.cs" highlight="13":::

<span data-ttu-id="9fcaf-435">Записи в C# 9 поддерживаются, как показано в примере:</span><span class="sxs-lookup"><span data-stu-id="9fcaf-435">Records in C# 9 are also supported, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/Records.cs":::

<span data-ttu-id="9fcaf-436">Подробнее о неизменяемых типах, чьи методы задания не являются общедоступными, см. в разделе о [методах доступа к свойствам, не являющимся общедоступными](#non-public-property-accessors).</span><span class="sxs-lookup"><span data-stu-id="9fcaf-436">For types that are immutable because all their property setters are non-public, see the following section about [non-public property accessors](#non-public-property-accessors).</span></span>
::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="9fcaf-437">`JsonConstructorAttribute` и поддержка записи C# 9 недоступны в .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-437">`JsonConstructorAttribute` and C# 9 Record support aren't available in .NET Core 3.1.</span></span>
::: zone-end

## <a name="non-public-property-accessors"></a><span data-ttu-id="9fcaf-438">Методы доступа к свойствам, не являющимся общедоступными</span><span class="sxs-lookup"><span data-stu-id="9fcaf-438">Non-public property accessors</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="9fcaf-439">Для включения метода доступа к свойству, не являющемуся общедоступным, используйте атрибут [[JsonInclude]](xref::::no-loc(System.Text.Json):::.Serialization.JsonIncludeAttribute), как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="9fcaf-439">To enable use of a non-public property accessor, use the [[JsonInclude]](xref::::no-loc(System.Text.Json):::.Serialization.JsonIncludeAttribute) attribute, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/NonPublicAccessors.cs" highlight="12,15":::
::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="9fcaf-440">Методы доступа к свойству, не являющемуся общедоступным, не поддерживаются в .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-440">Non-public property accessors are not supported in .NET Core 3.1.</span></span> <span data-ttu-id="9fcaf-441">Дополнительные сведения см. в статье [о переходе с :::no-loc(Newtonsoft.Json):::](system-text-json-migrate-from-newtonsoft-how-to.md#non-public-property-setters-and-getters).</span><span class="sxs-lookup"><span data-stu-id="9fcaf-441">For more information, see [the Migrate from :::no-loc(Newtonsoft.Json)::: article](system-text-json-migrate-from-newtonsoft-how-to.md#non-public-property-setters-and-getters).</span></span>
::: zone-end

## <a name="copy-jsonserializeroptions"></a><span data-ttu-id="9fcaf-442">Копирование JsonSerializerOptions</span><span class="sxs-lookup"><span data-stu-id="9fcaf-442">Copy JsonSerializerOptions</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="9fcaf-443">Существует [конструктор JsonSerializerOptions](xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.%23ctor(:::no-loc(System.Text.Json):::.JsonSerializerOptions)), который позволяет создавать новый экземпляр с параметрами, использованными для существующего экземпляра:</span><span class="sxs-lookup"><span data-stu-id="9fcaf-443">There is a [JsonSerializerOptions constructor](xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.%23ctor(:::no-loc(System.Text.Json):::.JsonSerializerOptions)) that lets you create a new instance with the same options as an existing instance, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/CopyOptions.cs" highlight="29":::
::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="9fcaf-444">Конструктор `JsonSerializerOptions`, который принимает существующий экземпляр, недоступен в .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-444">A `JsonSerializerOptions` constructor that takes an existing instance is not available in .NET Core 3.1.</span></span>
::: zone-end

## <a name="web-defaults-for-jsonserializeroptions"></a><span data-ttu-id="9fcaf-445">Стандартные параметры веб-приложений для JsonSerializerOptions</span><span class="sxs-lookup"><span data-stu-id="9fcaf-445">Web defaults for JsonSerializerOptions</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="9fcaf-446">Ниже приведены параметры с различными значениями по умолчанию для веб-приложений:</span><span class="sxs-lookup"><span data-stu-id="9fcaf-446">Here are the options that have different defaults for web apps:</span></span>

* <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.PropertyNameCaseInsensitive%2A> = `true`
* <xref::::no-loc(System.Text.Json):::.JsonNamingPolicy> = <xref::::no-loc(System.Text.Json):::.JsonNamingPolicy.CamelCase>
* <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.NumberHandling%2A> = <xref::::no-loc(System.Text.Json):::.Serialization.JsonNumberHandling.AllowReadingFromString>

<span data-ttu-id="9fcaf-447">Существует [конструктор JsonSerializerOptions](xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.%23ctor(:::no-loc(System.Text.Json):::.JsonSerializerDefaults)?view=net-5.0&preserve-view=true), который позволяет создавать новый экземпляр со стандартными параметрами, которые ASP.NET Core использует для веб-приложений, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="9fcaf-447">There's a [JsonSerializerOptions constructor](xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.%23ctor(:::no-loc(System.Text.Json):::.JsonSerializerDefaults)?view=net-5.0&preserve-view=true) that lets you create a new instance with the default options that ASP.NET Core uses for web apps, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/OptionsDefaults.cs" highlight="24":::
::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="9fcaf-448">Ниже приведены параметры с различными значениями по умолчанию для веб-приложений:</span><span class="sxs-lookup"><span data-stu-id="9fcaf-448">Here are the options that have different defaults for web apps:</span></span>

* <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.PropertyNameCaseInsensitive%2A> = `true`
* <xref::::no-loc(System.Text.Json):::.JsonNamingPolicy> = <xref::::no-loc(System.Text.Json):::.JsonNamingPolicy.CamelCase>

<span data-ttu-id="9fcaf-449">Конструктор `JsonSerializerOptions`, указывающий набор значений по умолчанию, недоступен в .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-449">A `JsonSerializerOptions` constructor that specifies a set of defaults is not available in .NET Core 3.1.</span></span>
::: zone-end

## <a name="httpclient-and-httpcontent-extension-methods"></a><span data-ttu-id="9fcaf-450">Методы расширения HttpClient и HttpContent</span><span class="sxs-lookup"><span data-stu-id="9fcaf-450">HttpClient and HttpContent extension methods</span></span>

::: zone pivot="dotnet-5-0"

<span data-ttu-id="9fcaf-451">Сериализация и десериализация полезных данных JSON из сети являются обычными операциями.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-451">Serializing and deserializing JSON payloads from the network are common operations.</span></span> <span data-ttu-id="9fcaf-452">Методы расширения в [HttpClient](xref:System.Net.Http.Json.HttpClientJsonExtensions) и [HttpContent](xref:System.Net.Http.Json.HttpContentJsonExtensions) позволяют выполнять эти операции в одной строке кода.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-452">Extension methods on [HttpClient](xref:System.Net.Http.Json.HttpClientJsonExtensions) and [HttpContent](xref:System.Net.Http.Json.HttpContentJsonExtensions) let you do these operations in a single line of code.</span></span> <span data-ttu-id="9fcaf-453">Эти методы расширения используют [стандартные параметры веб-приложений для JsonSerializerOptions](#web-defaults-for-jsonserializeroptions).</span><span class="sxs-lookup"><span data-stu-id="9fcaf-453">These extension methods use [web defaults for JsonSerializerOptions](#web-defaults-for-jsonserializeroptions).</span></span>

<span data-ttu-id="9fcaf-454">В следующем примере демонстрируется применение <xref:System.Net.Http.Json.HttpClientJsonExtensions.GetFromJsonAsync%2A?displayProperty=nameWithType> и <xref:System.Net.Http.Json.HttpClientJsonExtensions.PostAsJsonAsync%2A?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="9fcaf-454">The following example illustrates use of <xref:System.Net.Http.Json.HttpClientJsonExtensions.GetFromJsonAsync%2A?displayProperty=nameWithType> and <xref:System.Net.Http.Json.HttpClientJsonExtensions.PostAsJsonAsync%2A?displayProperty=nameWithType>:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/HttpClientExtensionMethods.cs" highlight="23,30":::

<span data-ttu-id="9fcaf-455">Для :::no-loc(System.Text.Json)::: существуют также методы расширения на [HttpContent](xref:System.Net.Http.Json.HttpContentJsonExtensions).</span><span class="sxs-lookup"><span data-stu-id="9fcaf-455">There are also extension methods for :::no-loc(System.Text.Json)::: on [HttpContent](xref:System.Net.Http.Json.HttpContentJsonExtensions).</span></span>
::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="9fcaf-456">Методы расширения на `HttpClient` и `HttpContent` недоступны в :::no-loc(System.Text.Json)::: для .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-456">Extension methods on `HttpClient` and `HttpContent` are not available in :::no-loc(System.Text.Json)::: in .NET Core 3.1.</span></span>
::: zone-end

## <a name="utf8jsonreader-utf8jsonwriter-and-jsondocument"></a><span data-ttu-id="9fcaf-457">Utf8JsonReader, Utf8JsonWriter и JsonDocument</span><span class="sxs-lookup"><span data-stu-id="9fcaf-457">Utf8JsonReader, Utf8JsonWriter, and JsonDocument</span></span>

<span data-ttu-id="9fcaf-458"><xref::::no-loc(System.Text.Json):::.Utf8JsonReader?displayProperty=fullName> — это последовательный модуль чтения текста JSON в кодировке UTF-8 из `ReadOnlySpan<byte>` или `ReadOnlySequence<byte>` с высокой производительностью и низким уровнем распределения.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-458"><xref::::no-loc(System.Text.Json):::.Utf8JsonReader?displayProperty=fullName> is a high-performance, low allocation, forward-only reader for UTF-8 encoded JSON text, read from a `ReadOnlySpan<byte>` or `ReadOnlySequence<byte>`.</span></span> <span data-ttu-id="9fcaf-459">`Utf8JsonReader` — это низкоуровневый тип, с помощью которого можно создавать пользовательские средства синтаксического анализа и десериализаторы.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-459">The `Utf8JsonReader` is a low-level type that can be used to build custom parsers and deserializers.</span></span> <span data-ttu-id="9fcaf-460">Метод <xref::::no-loc(System.Text.Json):::.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> использует `Utf8JsonReader`, как описано выше.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-460">The <xref::::no-loc(System.Text.Json):::.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> method uses `Utf8JsonReader` under the covers.</span></span>

<span data-ttu-id="9fcaf-461"><xref::::no-loc(System.Text.Json):::.Utf8JsonWriter?displayProperty=fullName> — это высокопроизводительный способ записать текст JSON в кодировке UTF-8 из распространенных типов .NET, например `String`, `Int32` и `DateTime`.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-461"><xref::::no-loc(System.Text.Json):::.Utf8JsonWriter?displayProperty=fullName> is a high-performance way to write UTF-8 encoded JSON text from common .NET types like `String`, `Int32`, and `DateTime`.</span></span> <span data-ttu-id="9fcaf-462">Модуль записи — это низкоуровневый тип, с помощью которого можно создавать пользовательские сериализаторы.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-462">The writer is a low-level type that can be used to build custom serializers.</span></span> <span data-ttu-id="9fcaf-463">Метод <xref::::no-loc(System.Text.Json):::.JsonSerializer.Serialize%2A?displayProperty=nameWithType> использует `Utf8JsonWriter`, как описано выше.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-463">The <xref::::no-loc(System.Text.Json):::.JsonSerializer.Serialize%2A?displayProperty=nameWithType> method uses `Utf8JsonWriter` under the covers.</span></span>

<span data-ttu-id="9fcaf-464"><xref::::no-loc(System.Text.Json):::.JsonDocument?displayProperty=fullName> предоставляет возможность создания модели DOM только для чтения с помощью `Utf8JsonReader`.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-464"><xref::::no-loc(System.Text.Json):::.JsonDocument?displayProperty=fullName> provides the ability to build a read-only Document Object Model (DOM) by using `Utf8JsonReader`.</span></span> <span data-ttu-id="9fcaf-465">Модель DOM предоставляет произвольный доступ к данным в полезных данных JSON.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-465">The DOM provides random access to data in a JSON payload.</span></span> <span data-ttu-id="9fcaf-466">Доступ к элементам JSON, составляющим полезные данные, можно получить с помощью типа <xref::::no-loc(System.Text.Json):::.JsonElement>.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-466">The JSON elements that compose the payload can be accessed via the <xref::::no-loc(System.Text.Json):::.JsonElement> type.</span></span> <span data-ttu-id="9fcaf-467">Тип `JsonElement` предоставляет перечислители массивов и объектов вместе с API-интерфейсами для преобразования текста JSON в стандартные типы .NET.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-467">The `JsonElement` type provides array and object enumerators along with APIs to convert JSON text to common .NET types.</span></span> <span data-ttu-id="9fcaf-468">`JsonDocument` предоставляет свойство <xref::::no-loc(System.Text.Json):::.JsonDocument.RootElement>.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-468">`JsonDocument` exposes a <xref::::no-loc(System.Text.Json):::.JsonDocument.RootElement> property.</span></span>

<span data-ttu-id="9fcaf-469">В следующих разделах показано, как использовать эти средства для чтения и записи данных JSON.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-469">The following sections show how to use these tools for reading and writing JSON.</span></span>

## <a name="use-jsondocument-for-access-to-data"></a><span data-ttu-id="9fcaf-470">Использование класса JsonDocument для доступа к данным</span><span class="sxs-lookup"><span data-stu-id="9fcaf-470">Use JsonDocument for access to data</span></span>

<span data-ttu-id="9fcaf-471">В следующем примере показано, как использовать класс <xref::::no-loc(System.Text.Json):::.JsonDocument> для произвольного доступа к данным в строке JSON:</span><span class="sxs-lookup"><span data-stu-id="9fcaf-471">The following example shows how to use the <xref::::no-loc(System.Text.Json):::.JsonDocument> class for random access to data in a JSON string:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/JsonDocumentDataAccess.cs?name=SnippetAverageGrades1)]

<span data-ttu-id="9fcaf-472">Предыдущий код:</span><span class="sxs-lookup"><span data-stu-id="9fcaf-472">The preceding code:</span></span>

* <span data-ttu-id="9fcaf-473">Предполагается, что анализируемый код JSON находится в строке `jsonString`.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-473">Assumes the JSON to analyze is in a string named `jsonString`.</span></span>
* <span data-ttu-id="9fcaf-474">Вычисляет среднее значение для объектов в массиве `Students`, имеющих свойство `Grade`.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-474">Calculates an average grade for objects in a `Students` array that have a `Grade` property.</span></span>
* <span data-ttu-id="9fcaf-475">Назначает значение по умолчанию 70 для учащихся, у которых нет оценки.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-475">Assigns a default grade of 70 for students who don't have a grade.</span></span>
* <span data-ttu-id="9fcaf-476">Подсчитывает число учащихся путем увеличения переменной `count` с каждой итерацией.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-476">Counts students by incrementing a `count` variable with each iteration.</span></span> <span data-ttu-id="9fcaf-477">Альтернативой является вызов <xref::::no-loc(System.Text.Json):::.JsonElement.GetArrayLength%2A>, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="9fcaf-477">An alternative is to call <xref::::no-loc(System.Text.Json):::.JsonElement.GetArrayLength%2A>, as shown in the following example:</span></span>

  [!code-csharp[](snippets/system-text-json-how-to/csharp/JsonDocumentDataAccess.cs?name=SnippetAverageGrades2)]

<span data-ttu-id="9fcaf-478">Ниже приведен пример JSON, обрабатываемый этим кодом:</span><span class="sxs-lookup"><span data-stu-id="9fcaf-478">Here's an example of the JSON that this code processes:</span></span>

[!code-json[](snippets/system-text-json-how-to/csharp/GradesPrettyPrint.json)]

## <a name="use-jsondocument-to-write-json"></a><span data-ttu-id="9fcaf-479">Использование класса JsonDocument для записи кода JSON</span><span class="sxs-lookup"><span data-stu-id="9fcaf-479">Use JsonDocument to write JSON</span></span>

<span data-ttu-id="9fcaf-480">В следующем примере показано, как записать JSON код из <xref::::no-loc(System.Text.Json):::.JsonDocument>.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-480">The following example shows how to write JSON from a <xref::::no-loc(System.Text.Json):::.JsonDocument>:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/JsonDocumentWriteJson.cs?name=SnippetSerialize)]

<span data-ttu-id="9fcaf-481">Предыдущий код:</span><span class="sxs-lookup"><span data-stu-id="9fcaf-481">The preceding code:</span></span>

* <span data-ttu-id="9fcaf-482">Считывает JSON-файл, загружает данные в `JsonDocument` и записывает форматированный (структурированный) код JSON в файл.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-482">Reads a JSON file, loads the data into a `JsonDocument`, and writes formatted (pretty-printed) JSON to a file.</span></span>
* <span data-ttu-id="9fcaf-483">Использует <xref::::no-loc(System.Text.Json):::.JsonDocumentOptions>, чтобы указать, что комментарии во входных данных JSON разрешены, но пропускаются.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-483">Uses <xref::::no-loc(System.Text.Json):::.JsonDocumentOptions> to specify that comments in the input JSON are allowed but ignored.</span></span>
* <span data-ttu-id="9fcaf-484">По завершении для модуля записи вызывается <xref::::no-loc(System.Text.Json):::.Utf8JsonWriter.Flush%2A>.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-484">When finished, calls <xref::::no-loc(System.Text.Json):::.Utf8JsonWriter.Flush%2A> on the writer.</span></span> <span data-ttu-id="9fcaf-485">В качестве альтернативы можно разрешить автоматическую запись в модуле записи при его удалении.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-485">An alternative is to let the writer autoflush when it's disposed.</span></span>

<span data-ttu-id="9fcaf-486">Ниже приведен пример входных данных JSON для обработки в примере кода:</span><span class="sxs-lookup"><span data-stu-id="9fcaf-486">Here's an example of JSON input to be processed by the example code:</span></span>

[!code-json[](snippets/system-text-json-how-to/csharp/Grades.json)]

<span data-ttu-id="9fcaf-487">В результате получаются следующие структурированные выходные данные JSON:</span><span class="sxs-lookup"><span data-stu-id="9fcaf-487">The result is the following pretty-printed JSON output:</span></span>

[!code-json[](snippets/system-text-json-how-to/csharp/GradesPrettyPrint.json)]

## <a name="use-utf8jsonwriter"></a><span data-ttu-id="9fcaf-488">Использование Utf8JsonWriter</span><span class="sxs-lookup"><span data-stu-id="9fcaf-488">Use Utf8JsonWriter</span></span>

<span data-ttu-id="9fcaf-489">В следующем примере показано, как использовать класс <xref::::no-loc(System.Text.Json):::.Utf8JsonWriter>.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-489">The following example shows how to use the <xref::::no-loc(System.Text.Json):::.Utf8JsonWriter> class:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/Utf8WriterToStream.cs?name=SnippetSerialize)]

## <a name="use-utf8jsonreader"></a><span data-ttu-id="9fcaf-490">Использование Utf8JsonReader</span><span class="sxs-lookup"><span data-stu-id="9fcaf-490">Use Utf8JsonReader</span></span>

<span data-ttu-id="9fcaf-491">В следующем примере показано, как использовать класс <xref::::no-loc(System.Text.Json):::.Utf8JsonReader>.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-491">The following example shows how to use the <xref::::no-loc(System.Text.Json):::.Utf8JsonReader> class:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/Utf8ReaderFromBytes.cs?name=SnippetDeserialize)]

<span data-ttu-id="9fcaf-492">В приведенном выше коде предполагается, что переменной `jsonUtf8` является массив байтов, который содержит допустимые данные JSON в кодировке UTF-8.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-492">The preceding code assumes that the `jsonUtf8` variable is a byte array that contains valid JSON, encoded as UTF-8.</span></span>

### <a name="filter-data-using-utf8jsonreader"></a><span data-ttu-id="9fcaf-493">Фильтрация данных с помощью Utf8JsonReader</span><span class="sxs-lookup"><span data-stu-id="9fcaf-493">Filter data using Utf8JsonReader</span></span>

<span data-ttu-id="9fcaf-494">В следующем примере показано, как синхронно выполнить чтение файла и поиск значения:</span><span class="sxs-lookup"><span data-stu-id="9fcaf-494">The following example shows how to read a file synchronously and search for a value:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/Utf8ReaderFromFile.cs)]

<span data-ttu-id="9fcaf-495">Предыдущий код:</span><span class="sxs-lookup"><span data-stu-id="9fcaf-495">The preceding code:</span></span>

* <span data-ttu-id="9fcaf-496">Предполагается, что JSON содержит массив объектов и каждый объект может содержать свойство name строкового типа.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-496">Assumes the JSON contains an array of objects and each object may contain a "name" property of type string.</span></span>
* <span data-ttu-id="9fcaf-497">Подсчитывает объекты и значения свойств name, заканчивающиеся на University.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-497">Counts objects and "name" property values that end with "University".</span></span>
* <span data-ttu-id="9fcaf-498">Предполагается, что файл кодируется как UTF-16 и перекодируется в UTF-8.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-498">Assumes the file is encoded as UTF-16 and transcodes it into UTF-8.</span></span> <span data-ttu-id="9fcaf-499">Файл, закодированный как UTF-8, можно прочитать непосредственно в `ReadOnlySpan<byte>` с помощью следующего кода:</span><span class="sxs-lookup"><span data-stu-id="9fcaf-499">A file encoded as UTF-8 can be read directly into a `ReadOnlySpan<byte>`, by using the following code:</span></span>

  ```csharp
  ReadOnlySpan<byte> jsonReadOnlySpan = File.ReadAllBytes(fileName);
  ```

  <span data-ttu-id="9fcaf-500">Если файл содержит метку порядка байтов (BOM) UTF-8, удалите ее перед передачей байтов в `Utf8JsonReader`, так как средство чтения ждет текст.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-500">If the file contains a UTF-8 byte order mark (BOM), remove it before passing the bytes to the `Utf8JsonReader`, since the reader expects text.</span></span> <span data-ttu-id="9fcaf-501">В противном случае метка порядка байтов считается недопустимым кодом JSON, и средство чтения создает исключение.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-501">Otherwise, the BOM is considered invalid JSON, and the reader throws an exception.</span></span>

<span data-ttu-id="9fcaf-502">Ниже приведен пример JSON, который можно считать с помощью приведенного выше кода.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-502">Here's a JSON sample that the preceding code can read.</span></span> <span data-ttu-id="9fcaf-503">Полученным итоговым сообщением будет 2 out of 4 have names that end with University (2 из 4 имеют имена, заканчивающиеся на University):</span><span class="sxs-lookup"><span data-stu-id="9fcaf-503">The resulting summary message is "2 out of 4 have names that end with 'University'":</span></span>

[!code-json[](snippets/system-text-json-how-to/csharp/Universities.json)]

### <a name="read-from-a-stream-using-utf8jsonreader"></a><span data-ttu-id="9fcaf-504">Чтение из потока данных с помощью Utf8JsonReader</span><span class="sxs-lookup"><span data-stu-id="9fcaf-504">Read from a stream using Utf8JsonReader</span></span>

<span data-ttu-id="9fcaf-505">При чтении большого файла (размером гигабайт и более) вы, скорее всего, предпочтете не загружать весь файл в память сразу.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-505">When reading a large file (a gigabyte or more in size, for example), you might want to avoid having to load the entire file into memory at once.</span></span> <span data-ttu-id="9fcaf-506">В таких ситуациях можно использовать <xref:System.IO.FileStream>.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-506">For this scenario, you can use a <xref:System.IO.FileStream>.</span></span>

<span data-ttu-id="9fcaf-507">При использовании `Utf8JsonReader` для чтения из потока данных действуют следующие правила:</span><span class="sxs-lookup"><span data-stu-id="9fcaf-507">When using the `Utf8JsonReader` to read from a stream, the following rules apply:</span></span>

* <span data-ttu-id="9fcaf-508">Буфер, который накапливает часть данных в формате JSON, должен быть не меньше самого крупного из возможных маркеров JSON, чтобы средство чтения могло продвигаться вперед.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-508">The buffer containing the partial JSON payload must be at least as large as the largest JSON token within it so that the reader can make forward progress.</span></span>
* <span data-ttu-id="9fcaf-509">Размер буфера должен быть не меньше самой большой последовательности пробелов в JSON.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-509">The buffer must be at least as large as the largest sequence of white space within the JSON.</span></span>
* <span data-ttu-id="9fcaf-510">Средство чтения не запоминает прочитанные данные, пока не дойдет до следующего свойства <xref::::no-loc(System.Text.Json):::.Utf8JsonReader.TokenType%2A> в структуре JSON.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-510">The reader doesn't keep track of the data it has read until it completely reads the next <xref::::no-loc(System.Text.Json):::.Utf8JsonReader.TokenType%2A> in the JSON payload.</span></span> <span data-ttu-id="9fcaf-511">Таким образом, если в буфере еще остались байты, их нужно снова передать в средство чтения.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-511">So when there are bytes left over in the buffer, you have to pass them to the reader again.</span></span> <span data-ttu-id="9fcaf-512">Для определения количества оставшихся байтов можно использовать <xref::::no-loc(System.Text.Json):::.Utf8JsonReader.BytesConsumed%2A>.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-512">You can use <xref::::no-loc(System.Text.Json):::.Utf8JsonReader.BytesConsumed%2A> to determine how many bytes are left over.</span></span>

<span data-ttu-id="9fcaf-513">В примере кода ниже показано, как выполнять чтение из потока.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-513">The following code illustrates how to read from a stream.</span></span> <span data-ttu-id="9fcaf-514">Этот пример демонстрирует <xref:System.IO.MemoryStream>.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-514">The example shows a <xref:System.IO.MemoryStream>.</span></span> <span data-ttu-id="9fcaf-515">Аналогичный код будет работать и с <xref:System.IO.FileStream>, за исключением случаев, когда в начале `FileStream` содержится метка порядка байтов UTF-8.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-515">Similar code will work with a <xref:System.IO.FileStream>, except when the `FileStream` contains a UTF-8 BOM at the start.</span></span> <span data-ttu-id="9fcaf-516">В этом случае необходимо удалить эти три байта из буфера, прежде чем передавать оставшиеся байты в `Utf8JsonReader`.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-516">In that case, you need to strip those three bytes from the buffer before passing the remaining bytes to the `Utf8JsonReader`.</span></span> <span data-ttu-id="9fcaf-517">В противном случае средство чтения создаст исключение, поскольку метка порядка байтов не считается допустимой частью JSON.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-517">Otherwise the reader would throw an exception, since the BOM is not considered a valid part of the JSON.</span></span>

<span data-ttu-id="9fcaf-518">Пример кода начинает работу с буфером в 4 КБ и удваивает размер буфера каждый раз, когда тот оказывается недостаточно велик для размещения полного маркера JSON, который потребуется средству чтения для дальнейшего перемещения по структуре данных JSON.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-518">The sample code starts with a 4KB buffer and doubles the buffer size each time it finds that the size is not large enough to fit a complete JSON token, which is required for the reader to make forward progress on the JSON payload.</span></span> <span data-ttu-id="9fcaf-519">Представленный в этом примере фрагмент JSON приводит к увеличению размера буфера только в том случае, если задан очень маленький начальный размер буфера, например 10 байт.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-519">The JSON sample provided in the snippet triggers a buffer size increase only if you set a very small initial buffer size, for example, 10 bytes.</span></span> <span data-ttu-id="9fcaf-520">Если указать для буфера начальное значение 10, то инструкции `Console.WriteLine` продемонстрируют причину и последствия увеличения размера буфера.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-520">If you set the initial buffer size to 10, the `Console.WriteLine` statements illustrate the cause and effect of buffer size increases.</span></span> <span data-ttu-id="9fcaf-521">При начальном размере буфера 4 КБ весь пример JSON целиком отображается в каждой `Console.WriteLine`, и размер буфера увеличивать не нужно.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-521">At the 4KB initial buffer size, the entire sample JSON is shown by each `Console.WriteLine`, and the buffer size never has to be increased.</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/Utf8ReaderPartialRead.cs)]

<span data-ttu-id="9fcaf-522">В примере выше ограничение на увеличение размера буфера не установлено.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-522">The preceding example sets no limit to how large the buffer can grow.</span></span> <span data-ttu-id="9fcaf-523">Если размер маркера будет слишком большой, такой код может возвратить ошибку с исключением <xref:System.OutOfMemoryException>.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-523">If the token size is too large, the code could fail with an <xref:System.OutOfMemoryException> exception.</span></span> <span data-ttu-id="9fcaf-524">Такое может произойти, если в JSON есть маркер размером около 1 ГБ, поскольку удвоение размера 1 ГБ приводит к переполнению буфера `int32`.</span><span class="sxs-lookup"><span data-stu-id="9fcaf-524">This can happen if the JSON contains a token that is around 1 GB or more in size, because doubling the 1 GB size results in a size that is too large to fit into an `int32` buffer.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9fcaf-525">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="9fcaf-525">Additional resources</span></span>

* [<span data-ttu-id="9fcaf-526">Общие сведения о :::no-loc(System.Text.Json):::</span><span class="sxs-lookup"><span data-stu-id="9fcaf-526">:::no-loc(System.Text.Json)::: overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="9fcaf-527">Как написать пользовательские преобразователи для сериализации JSON (маршалинг) в .NET</span><span class="sxs-lookup"><span data-stu-id="9fcaf-527">How to write custom converters</span></span>](system-text-json-converters-how-to.md)
* [<span data-ttu-id="9fcaf-528">Как выполнить миграцию из :::no-loc(Newtonsoft.Json):::</span><span class="sxs-lookup"><span data-stu-id="9fcaf-528">How to migrate from :::no-loc(Newtonsoft.Json):::</span></span>](system-text-json-migrate-from-newtonsoft-how-to.md)
* [<span data-ttu-id="9fcaf-529">Поддержка DateTime и DateTimeOffset в :::no-loc(System.Text.Json):::</span><span class="sxs-lookup"><span data-stu-id="9fcaf-529">DateTime and DateTimeOffset support in :::no-loc(System.Text.Json):::</span></span>](../datetime/system-text-json-support.md)
* <span data-ttu-id="9fcaf-530">[Справочник по API :::no-loc(System.Text.Json):::](xref::::no-loc(System.Text.Json):::)</span><span class="sxs-lookup"><span data-stu-id="9fcaf-530">[:::no-loc(System.Text.Json)::: API reference](xref::::no-loc(System.Text.Json):::)</span></span>
<!-- * [:::no-loc(System.Text.Json)::: roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/:::no-loc(System.Text.Json):::/roadmap/README.md)-->
