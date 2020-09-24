---
title: Как сериализировать и десериализировать JSON с помощью C# для .NET
description: Эта статья содержит сведения об использовании пространства имен System.Text.Json для сериализации и десериализации формата JSON в .NET. В ней приведен также пример кода.
ms.date: 05/13/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 72ba79784d3eb1beb43eab8db0a448a7e3b18eb6
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557844"
---
# <a name="how-to-serialize-and-deserialize-marshal-and-unmarshal-json-in-net"></a><span data-ttu-id="41770-104">Как сериализировать и десериализировать (маршалирование и демаршалирование) JSON в .NET</span><span class="sxs-lookup"><span data-stu-id="41770-104">How to serialize and deserialize (marshal and unmarshal) JSON in .NET</span></span>

<span data-ttu-id="41770-105">Эта статья содержит сведения об использовании пространства имен <xref:System.Text.Json> для сериализации и десериализации в нотации объектов JavaScript (JSON) и из нее.</span><span class="sxs-lookup"><span data-stu-id="41770-105">This article shows how to use the <xref:System.Text.Json> namespace to serialize and deserialize to and from JavaScript Object Notation (JSON).</span></span> <span data-ttu-id="41770-106">Если вы переносите существующий код из `Newtonsoft.Json`, ознакомьтесь со статьей [Переход с Newtonsoft.Json на System.Text.Json`System.Text.Json`](system-text-json-migrate-from-newtonsoft-how-to.md).</span><span class="sxs-lookup"><span data-stu-id="41770-106">If you're porting existing code from `Newtonsoft.Json`, see [How to migrate to `System.Text.Json`](system-text-json-migrate-from-newtonsoft-how-to.md).</span></span>

<span data-ttu-id="41770-107">В направлениях и образце кода библиотека используется напрямую, а не с помощью платформы, например [ASP.NET Core](/aspnet/core/).</span><span class="sxs-lookup"><span data-stu-id="41770-107">The directions and sample code use the library directly, not through a framework such as [ASP.NET Core](/aspnet/core/).</span></span>

<span data-ttu-id="41770-108">Большая часть примера кода сериализации устанавливает для параметра <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> значение `true` для структурирования JSON (с отступами и пробелами для удобства чтения).</span><span class="sxs-lookup"><span data-stu-id="41770-108">Most of the serialization sample code sets <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> to `true` to "pretty-print" the JSON (with indentation and whitespace for human readability).</span></span> <span data-ttu-id="41770-109">При использовании в рабочей среде для этого параметра обычно принимается значение по умолчанию `false`.</span><span class="sxs-lookup"><span data-stu-id="41770-109">For production use, you would typically accept the default value of `false` for this setting.</span></span>

<span data-ttu-id="41770-110">Примеры кода относятся к следующему классу и его вариантам:</span><span class="sxs-lookup"><span data-stu-id="41770-110">The code examples refer to the following class and variants of it:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

## <a name="namespaces"></a><span data-ttu-id="41770-111">Пространства имен</span><span class="sxs-lookup"><span data-stu-id="41770-111">Namespaces</span></span>

<span data-ttu-id="41770-112">Пространство имен <xref:System.Text.Json> содержит все точки входа и основные типы.</span><span class="sxs-lookup"><span data-stu-id="41770-112">The <xref:System.Text.Json> namespace contains all the entry points and the main types.</span></span> <span data-ttu-id="41770-113">Пространство имен <xref:System.Text.Json.Serialization> содержит атрибуты и интерфейсы API для сложных сценариев и настройки, характерной для сериализации и десериализации.</span><span class="sxs-lookup"><span data-stu-id="41770-113">The <xref:System.Text.Json.Serialization> namespace contains attributes and APIs for advanced scenarios and customization specific to serialization and deserialization.</span></span> <span data-ttu-id="41770-114">В примерах кода, приведенных в этой статье, для одного или обоих пространств имен необходимо добавить директивы `using`:</span><span class="sxs-lookup"><span data-stu-id="41770-114">The code examples shown in this article require `using` directives for one or both of these namespaces:</span></span>

```csharp
using System.Text.Json;
using System.Text.Json.Serialization;
```

<span data-ttu-id="41770-115">Атрибуты из пространства имен <xref:System.Runtime.Serialization> в настоящее время не поддерживаются в `System.Text.Json`.</span><span class="sxs-lookup"><span data-stu-id="41770-115">Attributes from the <xref:System.Runtime.Serialization> namespace aren't currently supported in `System.Text.Json`.</span></span>

## <a name="how-to-write-net-objects-to-json-serialize"></a><span data-ttu-id="41770-116">Как записать объекты .NET в JSON (сериализация)</span><span class="sxs-lookup"><span data-stu-id="41770-116">How to write .NET objects to JSON (serialize)</span></span>

<span data-ttu-id="41770-117">Чтобы записать JSON в строку или в файл, вызовите метод <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="41770-117">To write JSON to a string or to a file, call the <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="41770-118">В следующем примере показано создание JSON в виде строки:</span><span class="sxs-lookup"><span data-stu-id="41770-118">The following example creates JSON as a string:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToString.cs?name=SnippetSerialize)]

<span data-ttu-id="41770-119">В примере ниже для создания JSON-файла используется синхронный код:</span><span class="sxs-lookup"><span data-stu-id="41770-119">The following example uses synchronous code to create a JSON file:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToFile.cs?name=SnippetSerialize)]

<span data-ttu-id="41770-120">В следующем примере для создания JSON-файла используется асинхронный код:</span><span class="sxs-lookup"><span data-stu-id="41770-120">The following example uses asynchronous code to create a JSON file:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToFileAsync.cs?name=SnippetSerialize)]

<span data-ttu-id="41770-121">В предыдущих примерах для сериализуемого типа используется определение типа.</span><span class="sxs-lookup"><span data-stu-id="41770-121">The preceding examples use type inference for the type being serialized.</span></span> <span data-ttu-id="41770-122">Перегрузка `Serialize()` принимает параметр универсального типа:</span><span class="sxs-lookup"><span data-stu-id="41770-122">An overload of `Serialize()` takes a generic type parameter:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToString.cs?name=SnippetSerializeWithGenericParameter)]

### <a name="serialization-example"></a><span data-ttu-id="41770-123">Пример сериализации</span><span class="sxs-lookup"><span data-stu-id="41770-123">Serialization example</span></span>

<span data-ttu-id="41770-124">Ниже приведен пример класса, который содержит коллекции и вложенный класс:</span><span class="sxs-lookup"><span data-stu-id="41770-124">Here's an example class that contains collections and a nested class:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPOCOs)]

<span data-ttu-id="41770-125">Выходные данные JSON из сериализации экземпляра предыдущего типа выглядят следующим образом.</span><span class="sxs-lookup"><span data-stu-id="41770-125">The JSON output from serializing an instance of the preceding type looks like the following example.</span></span> <span data-ttu-id="41770-126">Выходные данные JSON по умолчанию сокращены:</span><span class="sxs-lookup"><span data-stu-id="41770-126">The JSON output is minified by default:</span></span>

```json
{"Date":"2019-08-01T00:00:00-07:00","TemperatureCelsius":25,"Summary":"Hot","DatesAvailable":["2019-08-01T00:00:00-07:00","2019-08-02T00:00:00-07:00"],"TemperatureRanges":{"Cold":{"High":20,"Low":-10},"Hot":{"High":60,"Low":20}},"SummaryWords":["Cool","Windy","Humid"]}
```

<span data-ttu-id="41770-127">В следующем примере показан тот же формат JSON (т. е. структурированный с пробелами и отступами):</span><span class="sxs-lookup"><span data-stu-id="41770-127">The following example shows the same JSON, formatted (that is, pretty-printed with whitespace and indentation):</span></span>

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

### <a name="serialize-to-utf-8"></a><span data-ttu-id="41770-128">Сериализация в UTF-8</span><span class="sxs-lookup"><span data-stu-id="41770-128">Serialize to UTF-8</span></span>

<span data-ttu-id="41770-129">Чтобы выполнить сериализацию в UTF-8, вызовите метод <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="41770-129">To serialize to UTF-8, call the <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> method:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToUtf8.cs?name=SnippetSerialize)]

<span data-ttu-id="41770-130">Также доступна перегрузка <xref:System.Text.Json.JsonSerializer.Serialize%2A>, которая принимает <xref:System.Text.Json.Utf8JsonWriter>.</span><span class="sxs-lookup"><span data-stu-id="41770-130">A <xref:System.Text.Json.JsonSerializer.Serialize%2A> overload that takes a <xref:System.Text.Json.Utf8JsonWriter> is also available.</span></span>

<span data-ttu-id="41770-131">Сериализация в UTF-8 происходит примерно на 5-10 % быстрее, чем при использовании строковых методов.</span><span class="sxs-lookup"><span data-stu-id="41770-131">Serializing to UTF-8 is about 5-10% faster than using the string-based methods.</span></span> <span data-ttu-id="41770-132">Разница заключается в том, что байты (например, UTF-8) не нужно преобразовывать в строки (UTF-16).</span><span class="sxs-lookup"><span data-stu-id="41770-132">The difference is because the bytes (as UTF-8) don't need to be converted to strings (UTF-16).</span></span>

## <a name="serialization-behavior"></a><span data-ttu-id="41770-133">Поведение сериализации</span><span class="sxs-lookup"><span data-stu-id="41770-133">Serialization behavior</span></span>

* <span data-ttu-id="41770-134">По умолчанию все открытые свойства сериализуются.</span><span class="sxs-lookup"><span data-stu-id="41770-134">By default, all public properties are serialized.</span></span> <span data-ttu-id="41770-135">Вы можете [указать свойства для исключения](#exclude-properties-from-serialization).</span><span class="sxs-lookup"><span data-stu-id="41770-135">You can [specify properties to exclude](#exclude-properties-from-serialization).</span></span>
* <span data-ttu-id="41770-136">[Кодировщик по умолчанию](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) экранирует символы, не относящиеся к ASCII, символы, учитывающие HTML, в пределах диапазона ASCII и символы, которые должны быть экранированы в соответствии со [спецификацией JSON RFC 8259](https://tools.ietf.org/html/rfc8259#section-7).</span><span class="sxs-lookup"><span data-stu-id="41770-136">The [default encoder](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) escapes non-ASCII characters, HTML-sensitive characters within the ASCII-range, and characters that must be escaped according to [the RFC 8259 JSON spec](https://tools.ietf.org/html/rfc8259#section-7).</span></span>
* <span data-ttu-id="41770-137">По умолчанию JSON сокращается.</span><span class="sxs-lookup"><span data-stu-id="41770-137">By default, JSON is minified.</span></span> <span data-ttu-id="41770-138">Вы можете [структурировать JSON](#serialize-to-formatted-json).</span><span class="sxs-lookup"><span data-stu-id="41770-138">You can [pretty-print the JSON](#serialize-to-formatted-json).</span></span>
* <span data-ttu-id="41770-139">По умолчанию регистр имен JSON соответствует именам в .NET.</span><span class="sxs-lookup"><span data-stu-id="41770-139">By default, casing of JSON names matches the .NET names.</span></span> <span data-ttu-id="41770-140">Вы можете [настроить регистр имен JSON](#customize-json-names-and-values).</span><span class="sxs-lookup"><span data-stu-id="41770-140">You can [customize JSON name casing](#customize-json-names-and-values).</span></span>
* <span data-ttu-id="41770-141">Обнаруживаются циклические ссылки и создаются исключения.</span><span class="sxs-lookup"><span data-stu-id="41770-141">Circular references are detected and exceptions thrown.</span></span>
* <span data-ttu-id="41770-142">В настоящее время [поля](../../csharp/programming-guide/classes-and-structs/fields.md) исключаются.</span><span class="sxs-lookup"><span data-stu-id="41770-142">Currently, [fields](../../csharp/programming-guide/classes-and-structs/fields.md) are excluded.</span></span>

<span data-ttu-id="41770-143">К поддерживаемым типам относятся:</span><span class="sxs-lookup"><span data-stu-id="41770-143">Supported types include:</span></span>

* <span data-ttu-id="41770-144">Примитивы .NET, которые сопоставляются с примитивами JavaScript, например числовыми типами, строками и логическими значениями.</span><span class="sxs-lookup"><span data-stu-id="41770-144">.NET primitives that map to JavaScript primitives, such as numeric types, strings, and Boolean.</span></span>
* <span data-ttu-id="41770-145">Определяемые пользователем [объекты POCO (традиционные объекты среды CLR)](https://stackoverflow.com/questions/250001/poco-definition).</span><span class="sxs-lookup"><span data-stu-id="41770-145">User-defined [Plain Old CLR Objects (POCOs)](https://stackoverflow.com/questions/250001/poco-definition).</span></span>
* <span data-ttu-id="41770-146">Одномерные массивы и массивы массивов (`ArrayName[][]`).</span><span class="sxs-lookup"><span data-stu-id="41770-146">One-dimensional and jagged arrays (`ArrayName[][]`).</span></span>
* <span data-ttu-id="41770-147">`Dictionary<string,TValue>` где `TValue` — это `object`, `JsonElement` или POCO.</span><span class="sxs-lookup"><span data-stu-id="41770-147">`Dictionary<string,TValue>` where `TValue` is `object`, `JsonElement`, or a POCO.</span></span>
* <span data-ttu-id="41770-148">Коллекции из следующих пространств имен.</span><span class="sxs-lookup"><span data-stu-id="41770-148">Collections from the following namespaces.</span></span>
  * <xref:System.Collections>
  * <xref:System.Collections.Generic>
  * <xref:System.Collections.Immutable>

<span data-ttu-id="41770-149">Для обработки дополнительных типов или для обеспечения функциональности, которая не поддерживается встроенными преобразователями, можно [реализовать пользовательские преобразователи](system-text-json-converters-how-to.md).</span><span class="sxs-lookup"><span data-stu-id="41770-149">You can [implement custom converters](system-text-json-converters-how-to.md) to handle additional types or to provide functionality that isn't supported by the built-in converters.</span></span>

## <a name="how-to-read-json-into-net-objects-deserialize"></a><span data-ttu-id="41770-150">Как считать JSON в объекты .NET (десериализация)</span><span class="sxs-lookup"><span data-stu-id="41770-150">How to read JSON into .NET objects (deserialize)</span></span>

<span data-ttu-id="41770-151">Чтобы выполнить десериализацию из строки или файла, вызовите метод <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="41770-151">To deserialize from a string or a file, call the <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="41770-152">В следующем примере показано считывание JSON из строки и создание экземпляра класса `WeatherForecast`, показанного ранее для [примера сериализации](#serialization-example):</span><span class="sxs-lookup"><span data-stu-id="41770-152">The following example reads JSON from a string and creates an instance of the `WeatherForecast` class shown earlier for the [serialization example](#serialization-example):</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToString.cs?name=SnippetDeserialize)]

<span data-ttu-id="41770-153">Чтобы выполнить десериализацию из файла с помощью синхронного кода, выполните считывание файла в строку, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="41770-153">To deserialize from a file by using synchronous code, read the file into a string, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToFile.cs?name=SnippetDeserialize)]

<span data-ttu-id="41770-154">Чтобы выполнить десериализацию из файла с помощью асинхронного кода, вызовите метод <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A>:</span><span class="sxs-lookup"><span data-stu-id="41770-154">To deserialize from a file by using asynchronous code, call the <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A> method:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToFileAsync.cs?name=SnippetDeserialize)]

### <a name="deserialize-from-utf-8"></a><span data-ttu-id="41770-155">Десериализация из UTF-8</span><span class="sxs-lookup"><span data-stu-id="41770-155">Deserialize from UTF-8</span></span>

<span data-ttu-id="41770-156">Для десериализации из UTF-8 вызовите перегрузку <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>, которая принимает значения `Utf8JsonReader` или `ReadOnlySpan<byte>`, как показано в следующих примерах.</span><span class="sxs-lookup"><span data-stu-id="41770-156">To deserialize from UTF-8, call a <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> overload that takes a `Utf8JsonReader` or a `ReadOnlySpan<byte>`, as shown in the following examples.</span></span> <span data-ttu-id="41770-157">В примерах предполагается, что JSON находится в массиве байтов jsonUtf8Bytes.</span><span class="sxs-lookup"><span data-stu-id="41770-157">The examples assume the JSON is in a byte array named jsonUtf8Bytes.</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToUtf8.cs?name=SnippetDeserialize1)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToUtf8.cs?name=SnippetDeserialize2)]

## <a name="deserialization-behavior"></a><span data-ttu-id="41770-158">Поведение десериализации</span><span class="sxs-lookup"><span data-stu-id="41770-158">Deserialization behavior</span></span>

* <span data-ttu-id="41770-159">По умолчанию при сопоставлении имен свойств учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="41770-159">By default, property name matching is case-sensitive.</span></span> <span data-ttu-id="41770-160">Вы можете [указать учет регистра](#case-insensitive-property-matching).</span><span class="sxs-lookup"><span data-stu-id="41770-160">You can [specify case-insensitivity](#case-insensitive-property-matching).</span></span>
* <span data-ttu-id="41770-161">Если JSON содержит значение для свойства, доступного только для чтения, значение игнорируется, а исключение не создается.</span><span class="sxs-lookup"><span data-stu-id="41770-161">If the JSON contains a value for a read-only property, the value is ignored and no exception is thrown.</span></span>
* <span data-ttu-id="41770-162">Десериализация в ссылочные типы без конструктора, не имеющего параметров, не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="41770-162">Deserialization to reference types without a parameterless constructor isn't supported.</span></span>
* <span data-ttu-id="41770-163">Десериализация в неизменяемые объекты или свойства только для чтения не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="41770-163">Deserialization to immutable objects or read-only properties isn't supported.</span></span>
* <span data-ttu-id="41770-164">По умолчанию перечисления поддерживаются в виде чисел.</span><span class="sxs-lookup"><span data-stu-id="41770-164">By default, enums are supported as numbers.</span></span> <span data-ttu-id="41770-165">Вы можете [сериализовать имена перечислений в качестве строк](#enums-as-strings).</span><span class="sxs-lookup"><span data-stu-id="41770-165">You can [serialize enum names as strings](#enums-as-strings).</span></span>
* <span data-ttu-id="41770-166">Поля не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="41770-166">Fields aren't supported.</span></span>
* <span data-ttu-id="41770-167">По умолчанию комментарии или завершающие запятые в JSON вызывают исключения.</span><span class="sxs-lookup"><span data-stu-id="41770-167">By default, comments or trailing commas in the JSON throw exceptions.</span></span> <span data-ttu-id="41770-168">Вы можете разрешить [комментарии и завершающие запятые](#allow-comments-and-trailing-commas).</span><span class="sxs-lookup"><span data-stu-id="41770-168">You can [allow comments and trailing commas](#allow-comments-and-trailing-commas).</span></span>
* <span data-ttu-id="41770-169">Максимальная глубина [по умолчанию](xref:System.Text.Json.JsonReaderOptions.MaxDepth) равна 64.</span><span class="sxs-lookup"><span data-stu-id="41770-169">The [default maximum depth](xref:System.Text.Json.JsonReaderOptions.MaxDepth) is 64.</span></span>

<span data-ttu-id="41770-170">Для обеспечения функциональности, которая не поддерживается встроенными преобразователями, можно [реализовать пользовательские преобразователи](system-text-json-converters-how-to.md).</span><span class="sxs-lookup"><span data-stu-id="41770-170">You can [implement custom converters](system-text-json-converters-how-to.md) to provide functionality that isn't supported by the built-in converters.</span></span>

## <a name="serialize-to-formatted-json"></a><span data-ttu-id="41770-171">Сериализация в форматированный JSON</span><span class="sxs-lookup"><span data-stu-id="41770-171">Serialize to formatted JSON</span></span>

<span data-ttu-id="41770-172">Чтобы структурировать выходные данные JSON, задайте для <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> значение `true`.</span><span class="sxs-lookup"><span data-stu-id="41770-172">To pretty-print the JSON output, set <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> to `true`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToString.cs?name=SnippetSerializePrettyPrint)]

<span data-ttu-id="41770-173">Ниже приведен пример типа для сериализации и структурирования данных JSON:</span><span class="sxs-lookup"><span data-stu-id="41770-173">Here's an example type to be serialized and pretty-printed JSON output:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

## <a name="customize-json-names-and-values"></a><span data-ttu-id="41770-174">Настройка имен и значений JSON</span><span class="sxs-lookup"><span data-stu-id="41770-174">Customize JSON names and values</span></span>

<span data-ttu-id="41770-175">По умолчанию имена и ключи словарей не изменяются в выходных данных JSON, включая регистр.</span><span class="sxs-lookup"><span data-stu-id="41770-175">By default, property names and dictionary keys are unchanged in the JSON output, including case.</span></span> <span data-ttu-id="41770-176">Значения перечисления представлены в виде чисел.</span><span class="sxs-lookup"><span data-stu-id="41770-176">Enum values are represented as numbers.</span></span> <span data-ttu-id="41770-177">В этом разделе объясняется, как выполнить такие задачи:</span><span class="sxs-lookup"><span data-stu-id="41770-177">This section explains how to:</span></span>

* <span data-ttu-id="41770-178">[Настраивать отдельные имена свойств](#customize-individual-property-names).</span><span class="sxs-lookup"><span data-stu-id="41770-178">[Customize individual property names](#customize-individual-property-names)</span></span>
* <span data-ttu-id="41770-179">[Преобразовывать все имена свойств в неоднородный регистр](#use-camel-case-for-all-json-property-names).</span><span class="sxs-lookup"><span data-stu-id="41770-179">[Convert all property names to camel case](#use-camel-case-for-all-json-property-names)</span></span>
* <span data-ttu-id="41770-180">[Реализовывать политики именования пользовательских свойств](#use-a-custom-json-property-naming-policy).</span><span class="sxs-lookup"><span data-stu-id="41770-180">[Implement a custom property naming policy](#use-a-custom-json-property-naming-policy)</span></span>
* <span data-ttu-id="41770-181">[Преобразовывать ключи словаря в "верблюжий" стиль](#camel-case-dictionary-keys).</span><span class="sxs-lookup"><span data-stu-id="41770-181">[Convert dictionary keys to camel case](#camel-case-dictionary-keys)</span></span>
* <span data-ttu-id="41770-182">[Преобразовывать перечисления в строки и "верблюжий" стиль](#enums-as-strings).</span><span class="sxs-lookup"><span data-stu-id="41770-182">[Convert enums to strings and camel case](#enums-as-strings)</span></span>

<span data-ttu-id="41770-183">Для других сценариев, требующих специальной обработки имен и значений свойств JSON, можно [реализовать пользовательские преобразователи](system-text-json-converters-how-to.md).</span><span class="sxs-lookup"><span data-stu-id="41770-183">For other scenarios that require special handling of JSON property names and values, you can [implement custom converters](system-text-json-converters-how-to.md).</span></span>

### <a name="customize-individual-property-names"></a><span data-ttu-id="41770-184">Настройка отдельных имен свойств</span><span class="sxs-lookup"><span data-stu-id="41770-184">Customize individual property names</span></span>

<span data-ttu-id="41770-185">Чтобы задать имена отдельных свойств, используйте атрибут [[JsonPropertyName]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute).</span><span class="sxs-lookup"><span data-stu-id="41770-185">To set the name of individual properties, use the [[JsonPropertyName]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute) attribute.</span></span>

<span data-ttu-id="41770-186">Ниже приведен пример типа для сериализации и полученный код JSON:</span><span class="sxs-lookup"><span data-stu-id="41770-186">Here's an example type to serialize and resulting JSON:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="41770-187">Имя свойства, заданное этим атрибутом:</span><span class="sxs-lookup"><span data-stu-id="41770-187">The property name set by this attribute:</span></span>

* <span data-ttu-id="41770-188">Применяется в обоих направлениях для сериализации и десериализации.</span><span class="sxs-lookup"><span data-stu-id="41770-188">Applies in both directions, for serialization and deserialization.</span></span>
* <span data-ttu-id="41770-189">Имеет приоритет над политиками именования свойств.</span><span class="sxs-lookup"><span data-stu-id="41770-189">Takes precedence over property naming policies.</span></span>

### <a name="use-camel-case-for-all-json-property-names"></a><span data-ttu-id="41770-190">Использование "верблюжьего" стиля для всех имен свойств JSON</span><span class="sxs-lookup"><span data-stu-id="41770-190">Use camel case for all JSON property names</span></span>

<span data-ttu-id="41770-191">Чтобы использовать "верблюжий" стиль для всех имен свойств JSON, задайте для параметра <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> значение `JsonNamingPolicy.CamelCase`, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="41770-191">To use camel case for all JSON property names, set <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> to `JsonNamingPolicy.CamelCase`, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundTripCamelCasePropertyNames.cs?name=Serialize)]

<span data-ttu-id="41770-192">Ниже приведен пример класса для сериализации и вывода JSON.</span><span class="sxs-lookup"><span data-stu-id="41770-192">Here's an example class to serialize and JSON output:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="41770-193">Политика именования свойств "верблюжьего" стиля:</span><span class="sxs-lookup"><span data-stu-id="41770-193">The camel case property naming policy:</span></span>

* <span data-ttu-id="41770-194">Применяется к сериализации и десериализации.</span><span class="sxs-lookup"><span data-stu-id="41770-194">Applies to serialization and deserialization.</span></span>
* <span data-ttu-id="41770-195">Переопределяется атрибутами `[JsonPropertyName]`.</span><span class="sxs-lookup"><span data-stu-id="41770-195">Is overridden by `[JsonPropertyName]` attributes.</span></span> <span data-ttu-id="41770-196">Именно поэтому имя свойства JSON, `Wind` в примере, не указано в "верблюжьем" стиле.</span><span class="sxs-lookup"><span data-stu-id="41770-196">This is why the JSON property name `Wind` in the example is not camel case.</span></span>

### <a name="use-a-custom-json-property-naming-policy"></a><span data-ttu-id="41770-197">Использование настраиваемой политики именования свойств JSON</span><span class="sxs-lookup"><span data-stu-id="41770-197">Use a custom JSON property naming policy</span></span>

<span data-ttu-id="41770-198">Чтобы использовать настраиваемую политику именования свойств JSON, создайте класс, производный от <xref:System.Text.Json.JsonNamingPolicy>, и переопределите метод <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A>, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="41770-198">To use a custom JSON property naming policy, create a class that derives from <xref:System.Text.Json.JsonNamingPolicy> and override the <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A> method, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/UpperCaseNamingPolicy.cs)]

<span data-ttu-id="41770-199">Затем задайте для свойства <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> экземпляр класса политики именования:</span><span class="sxs-lookup"><span data-stu-id="41770-199">Then set the <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> property to an instance of your naming policy class:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripPropertyNamingPolicy.cs?name=SnippetSerialize)]

<span data-ttu-id="41770-200">Ниже приведен пример класса для сериализации и вывода JSON.</span><span class="sxs-lookup"><span data-stu-id="41770-200">Here's an example class to serialize and JSON output:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "DATE": "2019-08-01T00:00:00-07:00",
  "TEMPERATURECELSIUS": 25,
  "SUMMARY": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="41770-201">Политика именования свойств JSON:</span><span class="sxs-lookup"><span data-stu-id="41770-201">The JSON property naming policy:</span></span>

* <span data-ttu-id="41770-202">Применяется к сериализации и десериализации.</span><span class="sxs-lookup"><span data-stu-id="41770-202">Applies to serialization and deserialization.</span></span>
* <span data-ttu-id="41770-203">Переопределяется атрибутами `[JsonPropertyName]`.</span><span class="sxs-lookup"><span data-stu-id="41770-203">Is overridden by `[JsonPropertyName]` attributes.</span></span> <span data-ttu-id="41770-204">Именно поэтому имя свойства JSON, `Wind` в примере, не указано в верхнем регистре.</span><span class="sxs-lookup"><span data-stu-id="41770-204">This is why the JSON property name `Wind` in the example is not upper case.</span></span>

### <a name="camel-case-dictionary-keys"></a><span data-ttu-id="41770-205">Ключи словаря в "верблюжьем" стиле.</span><span class="sxs-lookup"><span data-stu-id="41770-205">Camel case dictionary keys</span></span>

<span data-ttu-id="41770-206">Если свойство сериализуемого объекта имеет тип `Dictionary<string,TValue>`, ключи `string` можно преобразовать в "верблюжий" стиль.</span><span class="sxs-lookup"><span data-stu-id="41770-206">If a property of an object to be serialized is of type `Dictionary<string,TValue>`, the `string` keys can be converted to camel case.</span></span> <span data-ttu-id="41770-207">Для этого задайте для параметра <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy> значение `JsonNamingPolicy.CamelCase`, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="41770-207">To do that, set <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy> to `JsonNamingPolicy.CamelCase`, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCamelCaseDictionaryKeys.cs?name=SnippetSerialize)]

<span data-ttu-id="41770-208">Сериализация объекта с помощью словаря с именем `TemperatureRanges`, имеющего пары "ключ-значение" `"ColdMinTemp", 20` и `"HotMinTemp", 40`, приведет к выходным данным JSON, как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="41770-208">Serializing an object with a dictionary named `TemperatureRanges` that has key-value pairs `"ColdMinTemp", 20` and `"HotMinTemp", 40` would result in JSON output like the following example:</span></span>

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

<span data-ttu-id="41770-209">Политика именования в "верблюжьем" стиле для ключей словаря применяется только к сериализации.</span><span class="sxs-lookup"><span data-stu-id="41770-209">The camel case naming policy for dictionary keys applies to serialization only.</span></span> <span data-ttu-id="41770-210">При десериализации словаря ключи будут соответствовать JSON-файлу, даже если для параметра `DictionaryKeyPolicy` указано значение `JsonNamingPolicy.CamelCase`.</span><span class="sxs-lookup"><span data-stu-id="41770-210">If you deserialize a dictionary, the keys will match the JSON file even if you specify `JsonNamingPolicy.CamelCase` for the `DictionaryKeyPolicy`.</span></span>

### <a name="enums-as-strings"></a><span data-ttu-id="41770-211">Перечисление в виде строк</span><span class="sxs-lookup"><span data-stu-id="41770-211">Enums as strings</span></span>

<span data-ttu-id="41770-212">По умолчанию перечисления сериализуются как числа.</span><span class="sxs-lookup"><span data-stu-id="41770-212">By default, enums are serialized as numbers.</span></span> <span data-ttu-id="41770-213">Чтобы сериализовать имена перечислений как строки, используйте <xref:System.Text.Json.Serialization.JsonStringEnumConverter>.</span><span class="sxs-lookup"><span data-stu-id="41770-213">To serialize enum names as strings, use the <xref:System.Text.Json.Serialization.JsonStringEnumConverter>.</span></span>

<span data-ttu-id="41770-214">Например, предположим, что необходимо сериализовать следующий класс, имеющий перечисление:</span><span class="sxs-lookup"><span data-stu-id="41770-214">For example, suppose you need to serialize the following class that has an enum:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithEnum)]

<span data-ttu-id="41770-215">Если параметр "Сводка" имеет значение `Hot`, то по умолчанию сериализованный код JSON имеет числовое значение 3:</span><span class="sxs-lookup"><span data-stu-id="41770-215">If the Summary is `Hot`, by default the serialized JSON has the numeric value 3:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": 3
}
```

<span data-ttu-id="41770-216">Следующий пример кода сериализует имена перечислений вместо числовых значений и преобразует имена в "верблюжий" стиль:</span><span class="sxs-lookup"><span data-stu-id="41770-216">The following sample code serializes the enum names instead of the numeric values, and converts the names to camel case:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripEnumAsString.cs?name=SnippetSerialize)]

<span data-ttu-id="41770-217">Итоговый код JSON выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="41770-217">The resulting JSON looks like the following example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "hot"
}
```

<span data-ttu-id="41770-218">Имена строк перечисления можно также десериализовать, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="41770-218">Enum string names can be deserialized as well, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripEnumAsString.cs?name=SnippetDeserialize)]

## <a name="exclude-properties-from-serialization"></a><span data-ttu-id="41770-219">Исключение свойства из сериализации</span><span class="sxs-lookup"><span data-stu-id="41770-219">Exclude properties from serialization</span></span>

<span data-ttu-id="41770-220">По умолчанию все открытые свойства сериализуются.</span><span class="sxs-lookup"><span data-stu-id="41770-220">By default, all public properties are serialized.</span></span> <span data-ttu-id="41770-221">Если вы не хотите, чтобы некоторые из них отображались в выходных данных JSON, у вас есть несколько вариантов.</span><span class="sxs-lookup"><span data-stu-id="41770-221">If you don't want some of them to appear in the JSON output, you have several options.</span></span> <span data-ttu-id="41770-222">В этом разделе объясняется, как выполнить исключение:</span><span class="sxs-lookup"><span data-stu-id="41770-222">This section explains how to exclude:</span></span>

* <span data-ttu-id="41770-223">[отдельных свойств](#exclude-individual-properties);</span><span class="sxs-lookup"><span data-stu-id="41770-223">[Individual properties](#exclude-individual-properties)</span></span>
* <span data-ttu-id="41770-224">[всех свойств только для чтения](#exclude-all-read-only-properties);</span><span class="sxs-lookup"><span data-stu-id="41770-224">[All read-only properties](#exclude-all-read-only-properties)</span></span>
* <span data-ttu-id="41770-225">[всех свойств со значением NULL](#exclude-all-null-value-properties).</span><span class="sxs-lookup"><span data-stu-id="41770-225">[All null-value properties](#exclude-all-null-value-properties)</span></span>

### <a name="exclude-individual-properties"></a><span data-ttu-id="41770-226">Исключение отдельных свойств</span><span class="sxs-lookup"><span data-stu-id="41770-226">Exclude individual properties</span></span>

<span data-ttu-id="41770-227">Чтобы игнорировать отдельные свойства, используйте атрибут [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute).</span><span class="sxs-lookup"><span data-stu-id="41770-227">To ignore individual properties, use the [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) attribute.</span></span>

<span data-ttu-id="41770-228">Ниже приведен пример типа для сериализации и вывода JSON.</span><span class="sxs-lookup"><span data-stu-id="41770-228">Here's an example type to serialize and JSON output:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithIgnoreAttribute)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
}
```

### <a name="exclude-all-read-only-properties"></a><span data-ttu-id="41770-229">Исключение всех свойств только для чтения</span><span class="sxs-lookup"><span data-stu-id="41770-229">Exclude all read-only properties</span></span>

<span data-ttu-id="41770-230">Свойство доступно только для чтения, если оно содержит открытый метод получения, но не является общим методом задания.</span><span class="sxs-lookup"><span data-stu-id="41770-230">A property is read-only if it contains a public getter but not a public setter.</span></span> <span data-ttu-id="41770-231">Чтобы исключить все свойства только для чтения, задайте для параметра <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> значение `true`, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="41770-231">To exclude all read-only properties, set the <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> to `true`, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeExcludeReadOnlyProperties.cs?name=SnippetSerialize)]

<span data-ttu-id="41770-232">Ниже приведен пример типа для сериализации и вывода JSON.</span><span class="sxs-lookup"><span data-stu-id="41770-232">Here's an example type to serialize and JSON output:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithROProperty)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
}
```

<span data-ttu-id="41770-233">Этот параметр применяется только к сериализации.</span><span class="sxs-lookup"><span data-stu-id="41770-233">This option applies only to serialization.</span></span> <span data-ttu-id="41770-234">Во время десериализации свойства, доступные только для чтения, по умолчанию игнорируются.</span><span class="sxs-lookup"><span data-stu-id="41770-234">During deserialization, read-only properties are ignored by default.</span></span>

### <a name="exclude-all-null-value-properties"></a><span data-ttu-id="41770-235">Исключение всех свойств со значением NULL</span><span class="sxs-lookup"><span data-stu-id="41770-235">Exclude all null value properties</span></span>

<span data-ttu-id="41770-236">Чтобы исключить все свойства со значением NULL, задайте для параметра <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> значение `true`, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="41770-236">To exclude all null value properties, set the <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> property to `true`, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeExcludeNullValueProperties.cs?name=SnippetSerialize)]

<span data-ttu-id="41770-237">Ниже приведен пример объекта для сериализации и вывода JSON.</span><span class="sxs-lookup"><span data-stu-id="41770-237">Here's an example object to serialize and JSON output:</span></span>

|<span data-ttu-id="41770-238">Свойство.</span><span class="sxs-lookup"><span data-stu-id="41770-238">Property</span></span> |<span data-ttu-id="41770-239">Значение</span><span class="sxs-lookup"><span data-stu-id="41770-239">Value</span></span>  |
|---------|---------|
| <span data-ttu-id="41770-240">Дата</span><span class="sxs-lookup"><span data-stu-id="41770-240">Date</span></span>    | <span data-ttu-id="41770-241">01.08.2019 г. 00:00:00 – 7:00</span><span class="sxs-lookup"><span data-stu-id="41770-241">8/1/2019 12:00:00 AM -07:00</span></span>|
| <span data-ttu-id="41770-242">TemperatureCelsius</span><span class="sxs-lookup"><span data-stu-id="41770-242">TemperatureCelsius</span></span>| <span data-ttu-id="41770-243">25</span><span class="sxs-lookup"><span data-stu-id="41770-243">25</span></span> |
| <span data-ttu-id="41770-244">Сводка</span><span class="sxs-lookup"><span data-stu-id="41770-244">Summary</span></span>| <span data-ttu-id="41770-245">null</span><span class="sxs-lookup"><span data-stu-id="41770-245">null</span></span>|

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25
}
```

<span data-ttu-id="41770-246">Этот параметр применяется к сериализации и десериализации.</span><span class="sxs-lookup"><span data-stu-id="41770-246">This setting applies to serialization and deserialization.</span></span> <span data-ttu-id="41770-247">Сведения об его влиянии на десериализацию см. в разделе [Игнорирование значений NULL при десериализации](#ignore-null-when-deserializing).</span><span class="sxs-lookup"><span data-stu-id="41770-247">For information about its effect on deserialization, see [Ignore null when deserializing](#ignore-null-when-deserializing).</span></span>

## <a name="customize-character-encoding"></a><span data-ttu-id="41770-248">Настройка кодировки символов</span><span class="sxs-lookup"><span data-stu-id="41770-248">Customize character encoding</span></span>

<span data-ttu-id="41770-249">По умолчанию сериализатор экранирует символы, отличные от ASCII.</span><span class="sxs-lookup"><span data-stu-id="41770-249">By default, the serializer escapes all non-ASCII characters.</span></span>  <span data-ttu-id="41770-250">То есть он заменяет их на `\uxxxx`, где `xxxx` является кодом в кодировке Юникода символа.</span><span class="sxs-lookup"><span data-stu-id="41770-250">That is, it replaces them with `\uxxxx` where `xxxx` is the Unicode code of the character.</span></span>  <span data-ttu-id="41770-251">Например, если свойству `Summary` присвоено кириллическое значение "жарко", то объект `WeatherForecast` сериализуется, как показано в этом примере:</span><span class="sxs-lookup"><span data-stu-id="41770-251">For example, if the `Summary` property is set to Cyrillic жарко, the `WeatherForecast` object is serialized as shown in this example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "\u0436\u0430\u0440\u043A\u043E"
}
```

### <a name="serialize-language-character-sets"></a><span data-ttu-id="41770-252">Сериализация кодировки языка</span><span class="sxs-lookup"><span data-stu-id="41770-252">Serialize language character sets</span></span>

<span data-ttu-id="41770-253">Чтобы сериализовать кодировки одного или нескольких языков без экранирования, укажите [диапазон символов Юникода](xref:System.Text.Unicode.UnicodeRanges) при создании экземпляра <xref:System.Text.Encodings.Web.JavaScriptEncoder?displayProperty=fullName>, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="41770-253">To serialize the character set(s) of one or more languages without escaping, specify [Unicode range(s)](xref:System.Text.Unicode.UnicodeRanges) when creating an instance of <xref:System.Text.Encodings.Web.JavaScriptEncoder?displayProperty=fullName>, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetLanguageSets)]

<span data-ttu-id="41770-254">Этот код не поддерживает символы кириллицы или греческого языка.</span><span class="sxs-lookup"><span data-stu-id="41770-254">This code doesn't escape Cyrillic or Greek characters.</span></span> <span data-ttu-id="41770-255">Если свойству `Summary` присвоено кириллическое значение "жарко", то объект `WeatherForecast` сериализуется, как показано в этом примере:</span><span class="sxs-lookup"><span data-stu-id="41770-255">If the `Summary` property is set to Cyrillic жарко, the `WeatherForecast` object is serialized as shown in this example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жарко"
}
```

<span data-ttu-id="41770-256">Чтобы сериализовать все кодировки языка без экранирования, используйте <xref:System.Text.Unicode.UnicodeRanges.All?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="41770-256">To serialize all language sets without escaping, use <xref:System.Text.Unicode.UnicodeRanges.All?displayProperty=nameWithType>.</span></span>

### <a name="serialize-specific-characters"></a><span data-ttu-id="41770-257">Сериализация определенных символов</span><span class="sxs-lookup"><span data-stu-id="41770-257">Serialize specific characters</span></span>

<span data-ttu-id="41770-258">В качестве альтернативного способа вы можете указать отдельные символы, которые нужно разрешить, без экранирования.</span><span class="sxs-lookup"><span data-stu-id="41770-258">An alternative is to specify individual characters that you want to allow through without being escaped.</span></span> <span data-ttu-id="41770-259">В следующем примере сериализуются только первые два символа слова "жарко":</span><span class="sxs-lookup"><span data-stu-id="41770-259">The following example serializes only the first two characters of жарко:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetSelectedCharacters)]

<span data-ttu-id="41770-260">Ниже приведен пример JSON, созданный с помощью приведенного выше кода.</span><span class="sxs-lookup"><span data-stu-id="41770-260">Here's an example of JSON produced by the preceding code:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жа\u0440\u043A\u043E"
}
```

### <a name="serialize-all-characters"></a><span data-ttu-id="41770-261">Сериализация всех символов</span><span class="sxs-lookup"><span data-stu-id="41770-261">Serialize all characters</span></span>

<span data-ttu-id="41770-262">Чтобы минимизировать экранирование, можно использовать <xref:System.Text.Encodings.Web.JavaScriptEncoder.UnsafeRelaxedJsonEscaping?displayProperty=nameWithType>, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="41770-262">To minimize escaping you can use <xref:System.Text.Encodings.Web.JavaScriptEncoder.UnsafeRelaxedJsonEscaping?displayProperty=nameWithType>, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetUnsafeRelaxed)]

> [!CAUTION]
> <span data-ttu-id="41770-263">По сравнению с кодировщиком по умолчанию, кодировщик `UnsafeRelaxedJsonEscaping` более предпочтителен в отношении передачи символов без экранирования:</span><span class="sxs-lookup"><span data-stu-id="41770-263">Compared to the default encoder, the `UnsafeRelaxedJsonEscaping` encoder is more permissive about allowing characters to pass through unescaped:</span></span>
>
> * <span data-ttu-id="41770-264">Он не выполняет экранирование символов, учитывающих HTML, например `<`, `>`, `&` и `'`.</span><span class="sxs-lookup"><span data-stu-id="41770-264">It doesn't escape HTML-sensitive characters such as `<`, `>`, `&`, and `'`.</span></span>
> * <span data-ttu-id="41770-265">Он не предоставляет никаких дополнительных средств защиты от атак с помощью XSS или раскрытия информации, которые, например, могут возникать из-за того, что клиент и сервер не согласны с *кодировкой*.</span><span class="sxs-lookup"><span data-stu-id="41770-265">It doesn't offer any additional defense-in-depth protections against XSS or information disclosure attacks, such as those which might result from the client and server disagreeing on the *charset*.</span></span>
>
> <span data-ttu-id="41770-266">Используйте ненадежный кодировщик, только если известно, что клиент будет интерпретировать полученные полезные данные как JSON в кодировке UTF-8.</span><span class="sxs-lookup"><span data-stu-id="41770-266">Use the unsafe encoder only when it's known that the client will be interpreting the resulting payload as UTF-8 encoded JSON.</span></span> <span data-ttu-id="41770-267">Например, его можно использовать, если сервер отправляет заголовок ответа `Content-Type: application/json; charset=utf-8`.</span><span class="sxs-lookup"><span data-stu-id="41770-267">For example, you can use it if the server is sending the response header `Content-Type: application/json; charset=utf-8`.</span></span> <span data-ttu-id="41770-268">Никогда не допускайте, чтобы необработанные выходные данные `UnsafeRelaxedJsonEscaping` выводились на HTML-страницу или в элемент `<script>`.</span><span class="sxs-lookup"><span data-stu-id="41770-268">Never allow the raw `UnsafeRelaxedJsonEscaping` output to be emitted into an HTML page or a `<script>` element.</span></span>

## <a name="serialize-properties-of-derived-classes"></a><span data-ttu-id="41770-269">Сериализация свойств производных классов</span><span class="sxs-lookup"><span data-stu-id="41770-269">Serialize properties of derived classes</span></span>

<span data-ttu-id="41770-270">Сериализация иерархии полиморфных типов не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="41770-270">Serialization of a polymorphic type hierarchy is not supported.</span></span> <span data-ttu-id="41770-271">Например, если свойство определено как интерфейс или абстрактный класс, сериализуются только свойства, определенные в интерфейсе или абстрактном классе, даже если тип среды выполнения имеет дополнительные свойства.</span><span class="sxs-lookup"><span data-stu-id="41770-271">For example, if a property is defined as an interface or an abstract class, only the properties defined on the interface or abstract class are serialized, even if the runtime type has additional properties.</span></span> <span data-ttu-id="41770-272">В этом разделе описаны исключения из этого поведения.</span><span class="sxs-lookup"><span data-stu-id="41770-272">The exceptions to this behavior are explained in this section.</span></span>

<span data-ttu-id="41770-273">Например, предположим, что у вас есть класс `WeatherForecast` и производный класс `WeatherForecastDerived`:</span><span class="sxs-lookup"><span data-stu-id="41770-273">For example, suppose you have a `WeatherForecast` class and a derived class `WeatherForecastDerived`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFDerived)]

<span data-ttu-id="41770-274">Предположим также, что аргумент типа метода `Serialize` во время компиляции `WeatherForecast`:</span><span class="sxs-lookup"><span data-stu-id="41770-274">And suppose the type argument of the `Serialize` method at compile time is `WeatherForecast`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs?name=SnippetSerializeDefault)]

<span data-ttu-id="41770-275">В этом сценарии свойство `WindSpeed` не сериализуется, даже если объект `weatherForecast` фактически является объектом `WeatherForecastDerived`.</span><span class="sxs-lookup"><span data-stu-id="41770-275">In this scenario, the `WindSpeed` property is not serialized even if the `weatherForecast` object is actually a `WeatherForecastDerived` object.</span></span> <span data-ttu-id="41770-276">Сериализуются только свойства базового класса:</span><span class="sxs-lookup"><span data-stu-id="41770-276">Only the base class properties are serialized:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

<span data-ttu-id="41770-277">Это поведение предназначено для предотвращения случайного доступа к данным в производном типе, созданном во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="41770-277">This behavior is intended to help prevent accidental exposure of data in a derived runtime-created type.</span></span>

<span data-ttu-id="41770-278">Чтобы сериализовать свойства производного типа в предыдущем примере, используйте один из следующих подходов:</span><span class="sxs-lookup"><span data-stu-id="41770-278">To serialize the properties of the derived type in the preceding example, use one of the following approaches:</span></span>

* <span data-ttu-id="41770-279">Вызовите перегрузку <xref:System.Text.Json.JsonSerializer.Serialize%2A>, которая позволяет указать тип во время выполнения:</span><span class="sxs-lookup"><span data-stu-id="41770-279">Call an overload of <xref:System.Text.Json.JsonSerializer.Serialize%2A> that lets you specify the type at run time:</span></span>

  [!code-csharp[](snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs?name=SnippetSerializeGetType)]

* <span data-ttu-id="41770-280">Объявите объект, который должен быть сериализован как `object`.</span><span class="sxs-lookup"><span data-stu-id="41770-280">Declare the object to be serialized as `object`.</span></span>

  [!code-csharp[](snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs?name=SnippetSerializeObject)]

<span data-ttu-id="41770-281">В предыдущем примере сценария оба подхода приводят к тому, что `WindSpeed` свойство включается в выходные данные JSON:</span><span class="sxs-lookup"><span data-stu-id="41770-281">In the preceding example scenario, both approaches cause the `WindSpeed` property to be included in the JSON output:</span></span>

```json
{
  "WindSpeed": 35,
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

> [!IMPORTANT]
> <span data-ttu-id="41770-282">Эти подходы обеспечивают одноэлементную сериализацию только для сериализации корневого объекта, а не для его свойств.</span><span class="sxs-lookup"><span data-stu-id="41770-282">These approaches provide polymorphic serialization only for the root object to be serialized, not for properties of that root object.</span></span>

<span data-ttu-id="41770-283">Вы можете выполнить полиморфную сериализацию для объектов более низкого уровня, если вы определите их как тип `object`.</span><span class="sxs-lookup"><span data-stu-id="41770-283">You can get polymorphic serialization for lower-level objects if you define them as type `object`.</span></span> <span data-ttu-id="41770-284">Например, предположим, что у класса `WeatherForecast` есть свойство `PreviousForecast`, которое может быть определено как тип `WeatherForecast` или `object`:</span><span class="sxs-lookup"><span data-stu-id="41770-284">For example, suppose your `WeatherForecast` class has a property named `PreviousForecast` that can be defined as type `WeatherForecast` or `object`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPrevious)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPreviousAsObject)]

<span data-ttu-id="41770-285">Если свойство `PreviousForecast` содержит экземпляр `WeatherForecastDerived`:</span><span class="sxs-lookup"><span data-stu-id="41770-285">If the `PreviousForecast` property contains an instance of `WeatherForecastDerived`:</span></span>

* <span data-ttu-id="41770-286">Выходные данные JSON из сериализации `WeatherForecastWithPrevious` **не содержат** `WindSpeed`.</span><span class="sxs-lookup"><span data-stu-id="41770-286">The JSON output from serializing `WeatherForecastWithPrevious` **doesn't include** `WindSpeed`.</span></span>
* <span data-ttu-id="41770-287">Выходные данные JSON из сериализации `WeatherForecastWithPreviousAsObject` **включают в себя** `WindSpeed`.</span><span class="sxs-lookup"><span data-stu-id="41770-287">The JSON output from serializing `WeatherForecastWithPreviousAsObject` **includes** `WindSpeed`.</span></span>

<span data-ttu-id="41770-288">Чтобы сериализовать `WeatherForecastWithPreviousAsObject`, не нужно вызывать `Serialize<object>` или `GetType`, потому что корневой объект не является объектом, который может иметь производный тип.</span><span class="sxs-lookup"><span data-stu-id="41770-288">To serialize `WeatherForecastWithPreviousAsObject`, it isn't necessary to call `Serialize<object>` or `GetType` because the root object isn't the one that may be of a derived type.</span></span> <span data-ttu-id="41770-289">В следующем примере кода не вызывается `Serialize<object>` или `GetType`:</span><span class="sxs-lookup"><span data-stu-id="41770-289">The following code example doesn't call `Serialize<object>` or `GetType`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs?name=SnippetSerializeSecondLevel)]

<span data-ttu-id="41770-290">Приведенный выше код правильно сериализует `WeatherForecastWithPreviousAsObject`:</span><span class="sxs-lookup"><span data-stu-id="41770-290">The preceding code correctly serializes `WeatherForecastWithPreviousAsObject`:</span></span>

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

<span data-ttu-id="41770-291">Аналогичный подход к определению свойств `object` работает с интерфейсами.</span><span class="sxs-lookup"><span data-stu-id="41770-291">The same approach of defining properties as `object` works with interfaces.</span></span> <span data-ttu-id="41770-292">Предположим, что у вас есть следующий интерфейс и реализация и вы хотите сериализовать класс со свойствами, содержащими экземпляры реализации:</span><span class="sxs-lookup"><span data-stu-id="41770-292">Suppose you have the following interface and implementation, and you want to serialize a class with properties that contain implementation instances:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/IForecast.cs)]

<span data-ttu-id="41770-293">Когда вы сериализуете экземпляр `Forecasts`, только `Tuesday` отображает свойство `WindSpeed`, так как `Tuesday` определяется как `object`:</span><span class="sxs-lookup"><span data-stu-id="41770-293">When you serialize an instance of `Forecasts`, only `Tuesday` shows the `WindSpeed` property, because `Tuesday` is defined as `object`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs?name=SnippetSerializeInterface)]

<span data-ttu-id="41770-294">В следующем примере показан код JSON, который является результатом предыдущего кода:</span><span class="sxs-lookup"><span data-stu-id="41770-294">The following example shows the JSON that results from the preceding code:</span></span>

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

<span data-ttu-id="41770-295">Дополнительные сведения о полиморфной **сериализации** и **десериализации** см. в статье [Миграция из Newtonsoft.Json в System.Text.Json](system-text-json-migrate-from-newtonsoft-how-to.md#polymorphic-serialization).</span><span class="sxs-lookup"><span data-stu-id="41770-295">For more information about polymorphic **serialization**, and for information about **deserialization**, see [How to migrate from Newtonsoft.Json to System.Text.Json](system-text-json-migrate-from-newtonsoft-how-to.md#polymorphic-serialization).</span></span>

## <a name="allow-comments-and-trailing-commas"></a><span data-ttu-id="41770-296">Разрешение комментариев и завершающих запятых</span><span class="sxs-lookup"><span data-stu-id="41770-296">Allow comments and trailing commas</span></span>

<span data-ttu-id="41770-297">По умолчанию комментарии и завершающие запятые в JSON не допускаются.</span><span class="sxs-lookup"><span data-stu-id="41770-297">By default, comments and trailing commas are not allowed in JSON.</span></span> <span data-ttu-id="41770-298">Чтобы разрешить комментарии в JSON, задайте для свойства <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> значение `JsonCommentHandling.Skip`.</span><span class="sxs-lookup"><span data-stu-id="41770-298">To allow comments in the JSON, set the <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> property to `JsonCommentHandling.Skip`.</span></span>
<span data-ttu-id="41770-299">Чтобы разрешить завершающие запятые, задайте для свойства <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> значение `true`.</span><span class="sxs-lookup"><span data-stu-id="41770-299">And to allow trailing commas, set the <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> property to `true`.</span></span> <span data-ttu-id="41770-300">В следующем примере показано, как разрешить оба варианта:</span><span class="sxs-lookup"><span data-stu-id="41770-300">The following example shows how to allow both:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/DeserializeCommasComments.cs?name=SnippetDeserialize)]

<span data-ttu-id="41770-301">Ниже приведен пример JSON с комментариями и завершающей запятой:</span><span class="sxs-lookup"><span data-stu-id="41770-301">Here's example JSON with comments and a trailing comma:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25, // Fahrenheit 77
  "Summary": "Hot", /* Zharko */
}
```

## <a name="case-insensitive-property-matching"></a><span data-ttu-id="41770-302">Сопоставление свойств без учета регистра</span><span class="sxs-lookup"><span data-stu-id="41770-302">Case-insensitive property matching</span></span>

<span data-ttu-id="41770-303">По умолчанию десериализация выполняет поиск совпадения имен свойств с учетом регистра между кодом JSON и свойствами целевого объекта.</span><span class="sxs-lookup"><span data-stu-id="41770-303">By default, deserialization looks for case-sensitive property name matches between JSON and the target object properties.</span></span> <span data-ttu-id="41770-304">Чтобы изменить это поведение, задайте для параметра <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> значение `true`.</span><span class="sxs-lookup"><span data-stu-id="41770-304">To change that behavior, set <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> to `true`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/DeserializeCaseInsensitive.cs?name=SnippetDeserialize)]

<span data-ttu-id="41770-305">Ниже приведен пример JSON с именами свойств в "верблюжьем" стиле.</span><span class="sxs-lookup"><span data-stu-id="41770-305">Here's example JSON with camel case property names.</span></span> <span data-ttu-id="41770-306">Его можно десериализовать в следующий тип, который содержит имена свойств в регистре Pascal.</span><span class="sxs-lookup"><span data-stu-id="41770-306">It can be deserialized into the following type that has Pascal case property names.</span></span>

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
}
```

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

## <a name="handle-overflow-json"></a><span data-ttu-id="41770-307">Обработка переполнения JSON</span><span class="sxs-lookup"><span data-stu-id="41770-307">Handle overflow JSON</span></span>

<span data-ttu-id="41770-308">При десериализации в JSON могут быть получены данные, которые не представлены свойствами целевого типа.</span><span class="sxs-lookup"><span data-stu-id="41770-308">While deserializing, you might receive data in the JSON that is not represented by properties of the target type.</span></span> <span data-ttu-id="41770-309">Предположим у вас есть следующий целевой тип:</span><span class="sxs-lookup"><span data-stu-id="41770-309">For example, suppose your target type is this:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

<span data-ttu-id="41770-310">А десериализируемым кодом JSON является:</span><span class="sxs-lookup"><span data-stu-id="41770-310">And the JSON to be deserialized is this:</span></span>

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

<span data-ttu-id="41770-311">При десериализации кода JSON, показанного в указанном типе, свойства `DatesAvailable` и `SummaryWords` никуда не переходят и будут потеряны.</span><span class="sxs-lookup"><span data-stu-id="41770-311">If you deserialize the JSON shown into the type shown, the `DatesAvailable` and `SummaryWords` properties have nowhere to go and are lost.</span></span> <span data-ttu-id="41770-312">Чтобы записать дополнительные данные, такие как эти свойства, примените атрибут [JsonExtensionData](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute) к свойству типа `Dictionary<string,object>` или `Dictionary<string,JsonElement>`:</span><span class="sxs-lookup"><span data-stu-id="41770-312">To capture extra data such as these properties, apply the [JsonExtensionData](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute) attribute to a property of type `Dictionary<string,object>` or `Dictionary<string,JsonElement>`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithExtensionData)]

<span data-ttu-id="41770-313">При десериализации показанного ранее JSON в этот тип данных дополнительные данные становятся парами "ключ-значение" свойства `ExtensionData`:</span><span class="sxs-lookup"><span data-stu-id="41770-313">When you deserialize the JSON shown earlier into this sample type, the extra data becomes key-value pairs of the `ExtensionData` property:</span></span>

|<span data-ttu-id="41770-314">Свойство.</span><span class="sxs-lookup"><span data-stu-id="41770-314">Property</span></span> |<span data-ttu-id="41770-315">Значение</span><span class="sxs-lookup"><span data-stu-id="41770-315">Value</span></span>  |<span data-ttu-id="41770-316">Примечания</span><span class="sxs-lookup"><span data-stu-id="41770-316">Notes</span></span>  |
|---------|---------|---------|
| <span data-ttu-id="41770-317">Дата</span><span class="sxs-lookup"><span data-stu-id="41770-317">Date</span></span>    | <span data-ttu-id="41770-318">01.08.2019 г. 00:00:00 – 7:00</span><span class="sxs-lookup"><span data-stu-id="41770-318">8/1/2019 12:00:00 AM -07:00</span></span>||
| <span data-ttu-id="41770-319">TemperatureCelsius</span><span class="sxs-lookup"><span data-stu-id="41770-319">TemperatureCelsius</span></span>| <span data-ttu-id="41770-320">0</span><span class="sxs-lookup"><span data-stu-id="41770-320">0</span></span> | <span data-ttu-id="41770-321">Несовпадение с учетом регистра (`temperatureCelsius` в коде JSON), поэтому свойство не задано.</span><span class="sxs-lookup"><span data-stu-id="41770-321">Case-sensitive mismatch (`temperatureCelsius` in the JSON), so the property isn't set.</span></span> |
| <span data-ttu-id="41770-322">Сводка</span><span class="sxs-lookup"><span data-stu-id="41770-322">Summary</span></span> | <span data-ttu-id="41770-323">Горячий</span><span class="sxs-lookup"><span data-stu-id="41770-323">Hot</span></span> ||
| <span data-ttu-id="41770-324">ExtensionData</span><span class="sxs-lookup"><span data-stu-id="41770-324">ExtensionData</span></span> | <span data-ttu-id="41770-325">temperatureCelsius: 25</span><span class="sxs-lookup"><span data-stu-id="41770-325">temperatureCelsius: 25</span></span> |<span data-ttu-id="41770-326">Так как регистр не совпадает, это свойство JSON является лишним и становится парой "ключ-значение" в словаре.</span><span class="sxs-lookup"><span data-stu-id="41770-326">Since the case didn't match, this JSON property is an extra and becomes a key-value pair in the dictionary.</span></span>|
|| <span data-ttu-id="41770-327">DatesAvailable:</span><span class="sxs-lookup"><span data-stu-id="41770-327">DatesAvailable:</span></span><br>  <span data-ttu-id="41770-328">01.08.2019 г. 00:00:00 – 7:00</span><span class="sxs-lookup"><span data-stu-id="41770-328">8/1/2019 12:00:00 AM -07:00</span></span><br><span data-ttu-id="41770-329">02.08.2019 г. 00:00:00 – 7:00</span><span class="sxs-lookup"><span data-stu-id="41770-329">8/2/2019 12:00:00 AM -07:00</span></span> |<span data-ttu-id="41770-330">Дополнительное свойство из кода JSON преобразуется в пару "ключ-значение" с массивом в качестве объекта значения.</span><span class="sxs-lookup"><span data-stu-id="41770-330">Extra property from the JSON becomes a key-value pair, with an array as the value object.</span></span>|
| |<span data-ttu-id="41770-331">SummaryWords:</span><span class="sxs-lookup"><span data-stu-id="41770-331">SummaryWords:</span></span><br><span data-ttu-id="41770-332">Здорово</span><span class="sxs-lookup"><span data-stu-id="41770-332">Cool</span></span><br><span data-ttu-id="41770-333">Ветрено</span><span class="sxs-lookup"><span data-stu-id="41770-333">Windy</span></span><br><span data-ttu-id="41770-334">Влажно</span><span class="sxs-lookup"><span data-stu-id="41770-334">Humid</span></span> |<span data-ttu-id="41770-335">Дополнительное свойство из кода JSON преобразуется в пару "ключ-значение" с массивом в качестве объекта значения.</span><span class="sxs-lookup"><span data-stu-id="41770-335">Extra property from the JSON becomes a key-value pair, with an array as the value object.</span></span>|

<span data-ttu-id="41770-336">Когда целевой объект сериализуется, пары "ключ-значение" данных расширения становятся свойствами JSON точно так же, как они были во входящем коде JSON:</span><span class="sxs-lookup"><span data-stu-id="41770-336">When the target object is serialized, the extension data key value pairs become JSON properties just as they were in the incoming JSON:</span></span>

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

<span data-ttu-id="41770-337">Обратите внимание, что имя свойства `ExtensionData` не отображается в коде JSON.</span><span class="sxs-lookup"><span data-stu-id="41770-337">Notice that the `ExtensionData` property name doesn't appear in the JSON.</span></span> <span data-ttu-id="41770-338">Такое поведение позволяет JSON выполнить круговой путь без потери дополнительных данных, которые в противном случае не будут десериализованы.</span><span class="sxs-lookup"><span data-stu-id="41770-338">This behavior lets the JSON make a round trip without losing any extra data that otherwise wouldn't be deserialized.</span></span>

## <a name="ignore-null-when-deserializing"></a><span data-ttu-id="41770-339">Игнорирование значений NULL при десериализации</span><span class="sxs-lookup"><span data-stu-id="41770-339">Ignore null when deserializing</span></span>

<span data-ttu-id="41770-340">По умолчанию, если свойство в JSON имеет значение NULL, соответствующему свойству в целевом объекте присваивается значение NULL.</span><span class="sxs-lookup"><span data-stu-id="41770-340">By default, if a property in JSON is null, the corresponding property in the target object is set to null.</span></span> <span data-ttu-id="41770-341">В некоторых сценариях целевое свойство может иметь значение по умолчанию, и вам не будет нужно, чтобы значение NULL переопределяло значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="41770-341">In some scenarios, the target property might have a default value, and you don't want a null value to override the default.</span></span>

<span data-ttu-id="41770-342">Например, следующий код представляет целевой объект:</span><span class="sxs-lookup"><span data-stu-id="41770-342">For example, suppose the following code represents your target object:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithDefault)]

<span data-ttu-id="41770-343">Предположим, что следующий код JSON десериализуется:</span><span class="sxs-lookup"><span data-stu-id="41770-343">And suppose the following JSON is deserialized:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": null
}
```

<span data-ttu-id="41770-344">После десериализации свойство `Summary` объекта `WeatherForecastWithDefault` будет иметь значение NULL.</span><span class="sxs-lookup"><span data-stu-id="41770-344">After deserialization, the `Summary` property of the `WeatherForecastWithDefault` object is null.</span></span>

<span data-ttu-id="41770-345">Чтобы изменить это поведение, задайте для параметра <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType> значение `true`, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="41770-345">To change this behavior, set <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType> to `true`, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/DeserializeIgnoreNull.cs?name=SnippetDeserialize)]

<span data-ttu-id="41770-346">При использовании этого параметра свойство `Summary` объекта `WeatherForecastWithDefault` принимает значение по умолчанию No summary после десериализации.</span><span class="sxs-lookup"><span data-stu-id="41770-346">With this option, the `Summary` property of the `WeatherForecastWithDefault` object is the default value "No summary" after deserialization.</span></span>

<span data-ttu-id="41770-347">Значения NULL в JSON пропускаются только в том случае, если они являются допустимыми.</span><span class="sxs-lookup"><span data-stu-id="41770-347">Null values in the JSON are ignored only if they are valid.</span></span> <span data-ttu-id="41770-348">Значения NULL для типов значений, не допускающих значения NULL, вызывают исключения.</span><span class="sxs-lookup"><span data-stu-id="41770-348">Null values for non-nullable value types cause exceptions.</span></span>

## <a name="utf8jsonreader-utf8jsonwriter-and-jsondocument"></a><span data-ttu-id="41770-349">Utf8JsonReader, Utf8JsonWriter и JsonDocument</span><span class="sxs-lookup"><span data-stu-id="41770-349">Utf8JsonReader, Utf8JsonWriter, and JsonDocument</span></span>

<span data-ttu-id="41770-350"><xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName> — это последовательный модуль чтения текста JSON в кодировке UTF-8 из `ReadOnlySpan<byte>` или `ReadOnlySequence<byte>` с высокой производительностью и низким уровнем распределения.</span><span class="sxs-lookup"><span data-stu-id="41770-350"><xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName> is a high-performance, low allocation, forward-only reader for UTF-8 encoded JSON text, read from a `ReadOnlySpan<byte>` or `ReadOnlySequence<byte>`.</span></span> <span data-ttu-id="41770-351">`Utf8JsonReader` — это низкоуровневый тип, с помощью которого можно создавать пользовательские средства синтаксического анализа и десериализаторы.</span><span class="sxs-lookup"><span data-stu-id="41770-351">The `Utf8JsonReader` is a low-level type that can be used to build custom parsers and deserializers.</span></span> <span data-ttu-id="41770-352">Метод <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> использует `Utf8JsonReader`, как описано выше.</span><span class="sxs-lookup"><span data-stu-id="41770-352">The <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> method uses `Utf8JsonReader` under the covers.</span></span>

<span data-ttu-id="41770-353"><xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName> — это высокопроизводительный способ записать текст JSON в кодировке UTF-8 из распространенных типов .NET, например `String`, `Int32` и `DateTime`.</span><span class="sxs-lookup"><span data-stu-id="41770-353"><xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName> is a high-performance way to write UTF-8 encoded JSON text from common .NET types like `String`, `Int32`, and `DateTime`.</span></span> <span data-ttu-id="41770-354">Модуль записи — это низкоуровневый тип, с помощью которого можно создавать пользовательские сериализаторы.</span><span class="sxs-lookup"><span data-stu-id="41770-354">The writer is a low-level type that can be used to build custom serializers.</span></span> <span data-ttu-id="41770-355">Метод <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> использует `Utf8JsonWriter`, как описано выше.</span><span class="sxs-lookup"><span data-stu-id="41770-355">The <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> method uses `Utf8JsonWriter` under the covers.</span></span>

<span data-ttu-id="41770-356"><xref:System.Text.Json.JsonDocument?displayProperty=fullName> предоставляет возможность создания модели DOM только для чтения с помощью `Utf8JsonReader`.</span><span class="sxs-lookup"><span data-stu-id="41770-356"><xref:System.Text.Json.JsonDocument?displayProperty=fullName> provides the ability to build a read-only Document Object Model (DOM) by using `Utf8JsonReader`.</span></span> <span data-ttu-id="41770-357">Модель DOM предоставляет произвольный доступ к данным в полезных данных JSON.</span><span class="sxs-lookup"><span data-stu-id="41770-357">The DOM provides random access to data in a JSON payload.</span></span> <span data-ttu-id="41770-358">Доступ к элементам JSON, составляющим полезные данные, можно получить с помощью типа <xref:System.Text.Json.JsonElement>.</span><span class="sxs-lookup"><span data-stu-id="41770-358">The JSON elements that compose the payload can be accessed via the <xref:System.Text.Json.JsonElement> type.</span></span> <span data-ttu-id="41770-359">Тип `JsonElement` предоставляет перечислители массивов и объектов вместе с API-интерфейсами для преобразования текста JSON в стандартные типы .NET.</span><span class="sxs-lookup"><span data-stu-id="41770-359">The `JsonElement` type provides array and object enumerators along with APIs to convert JSON text to common .NET types.</span></span> <span data-ttu-id="41770-360">`JsonDocument` предоставляет свойство <xref:System.Text.Json.JsonDocument.RootElement>.</span><span class="sxs-lookup"><span data-stu-id="41770-360">`JsonDocument` exposes a <xref:System.Text.Json.JsonDocument.RootElement> property.</span></span>

<span data-ttu-id="41770-361">В следующих разделах показано, как использовать эти средства для чтения и записи данных JSON.</span><span class="sxs-lookup"><span data-stu-id="41770-361">The following sections show how to use these tools for reading and writing JSON.</span></span>

## <a name="use-jsondocument-for-access-to-data"></a><span data-ttu-id="41770-362">Использование класса JsonDocument для доступа к данным</span><span class="sxs-lookup"><span data-stu-id="41770-362">Use JsonDocument for access to data</span></span>

<span data-ttu-id="41770-363">В следующем примере показано, как использовать класс <xref:System.Text.Json.JsonDocument> для произвольного доступа к данным в строке JSON:</span><span class="sxs-lookup"><span data-stu-id="41770-363">The following example shows how to use the <xref:System.Text.Json.JsonDocument> class for random access to data in a JSON string:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/JsonDocumentDataAccess.cs?name=SnippetAverageGrades1)]

<span data-ttu-id="41770-364">Предыдущий код:</span><span class="sxs-lookup"><span data-stu-id="41770-364">The preceding code:</span></span>

* <span data-ttu-id="41770-365">Предполагается, что анализируемый код JSON находится в строке `jsonString`.</span><span class="sxs-lookup"><span data-stu-id="41770-365">Assumes the JSON to analyze is in a string named `jsonString`.</span></span>
* <span data-ttu-id="41770-366">Вычисляет среднее значение для объектов в массиве `Students`, имеющих свойство `Grade`.</span><span class="sxs-lookup"><span data-stu-id="41770-366">Calculates an average grade for objects in a `Students` array that have a `Grade` property.</span></span>
* <span data-ttu-id="41770-367">Назначает значение по умолчанию 70 для учащихся, у которых нет оценки.</span><span class="sxs-lookup"><span data-stu-id="41770-367">Assigns a default grade of 70 for students who don't have a grade.</span></span>
* <span data-ttu-id="41770-368">Подсчитывает число учащихся путем увеличения переменной `count` с каждой итерацией.</span><span class="sxs-lookup"><span data-stu-id="41770-368">Counts students by incrementing a `count` variable with each iteration.</span></span> <span data-ttu-id="41770-369">Альтернативой является вызов <xref:System.Text.Json.JsonElement.GetArrayLength%2A>, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="41770-369">An alternative is to call <xref:System.Text.Json.JsonElement.GetArrayLength%2A>, as shown in the following example:</span></span>

  [!code-csharp[](snippets/system-text-json-how-to/csharp/JsonDocumentDataAccess.cs?name=SnippetAverageGrades2)]

<span data-ttu-id="41770-370">Ниже приведен пример JSON, обрабатываемый этим кодом:</span><span class="sxs-lookup"><span data-stu-id="41770-370">Here's an example of the JSON that this code processes:</span></span>

[!code-json[](snippets/system-text-json-how-to/csharp/GradesPrettyPrint.json)]

## <a name="use-jsondocument-to-write-json"></a><span data-ttu-id="41770-371">Использование класса JsonDocument для записи кода JSON</span><span class="sxs-lookup"><span data-stu-id="41770-371">Use JsonDocument to write JSON</span></span>

<span data-ttu-id="41770-372">В следующем примере показано, как записать JSON код из <xref:System.Text.Json.JsonDocument>.</span><span class="sxs-lookup"><span data-stu-id="41770-372">The following example shows how to write JSON from a <xref:System.Text.Json.JsonDocument>:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/JsonDocumentWriteJson.cs?name=SnippetSerialize)]

<span data-ttu-id="41770-373">Предыдущий код:</span><span class="sxs-lookup"><span data-stu-id="41770-373">The preceding code:</span></span>

* <span data-ttu-id="41770-374">Считывает JSON-файл, загружает данные в `JsonDocument` и записывает форматированный (структурированный) код JSON в файл.</span><span class="sxs-lookup"><span data-stu-id="41770-374">Reads a JSON file, loads the data into a `JsonDocument`, and writes formatted (pretty-printed) JSON to a file.</span></span>
* <span data-ttu-id="41770-375">Использует <xref:System.Text.Json.JsonDocumentOptions>, чтобы указать, что комментарии во входных данных JSON разрешены, но пропускаются.</span><span class="sxs-lookup"><span data-stu-id="41770-375">Uses <xref:System.Text.Json.JsonDocumentOptions> to specify that comments in the input JSON are allowed but ignored.</span></span>
* <span data-ttu-id="41770-376">По завершении для модуля записи вызывается <xref:System.Text.Json.Utf8JsonWriter.Flush%2A>.</span><span class="sxs-lookup"><span data-stu-id="41770-376">When finished, calls <xref:System.Text.Json.Utf8JsonWriter.Flush%2A> on the writer.</span></span> <span data-ttu-id="41770-377">В качестве альтернативы можно разрешить автоматическую запись в модуле записи при его удалении.</span><span class="sxs-lookup"><span data-stu-id="41770-377">An alternative is to let the writer autoflush when it's disposed.</span></span>

<span data-ttu-id="41770-378">Ниже приведен пример входных данных JSON для обработки в примере кода:</span><span class="sxs-lookup"><span data-stu-id="41770-378">Here's an example of JSON input to be processed by the example code:</span></span>

[!code-json[](snippets/system-text-json-how-to/csharp/Grades.json)]

<span data-ttu-id="41770-379">В результате получаются следующие структурированные выходные данные JSON:</span><span class="sxs-lookup"><span data-stu-id="41770-379">The result is the following pretty-printed JSON output:</span></span>

[!code-json[](snippets/system-text-json-how-to/csharp/GradesPrettyPrint.json)]

## <a name="use-utf8jsonwriter"></a><span data-ttu-id="41770-380">Использование Utf8JsonWriter</span><span class="sxs-lookup"><span data-stu-id="41770-380">Use Utf8JsonWriter</span></span>

<span data-ttu-id="41770-381">В следующем примере показано, как использовать класс <xref:System.Text.Json.Utf8JsonWriter>.</span><span class="sxs-lookup"><span data-stu-id="41770-381">The following example shows how to use the <xref:System.Text.Json.Utf8JsonWriter> class:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/Utf8WriterToStream.cs?name=SnippetSerialize)]

## <a name="use-utf8jsonreader"></a><span data-ttu-id="41770-382">Использование Utf8JsonReader</span><span class="sxs-lookup"><span data-stu-id="41770-382">Use Utf8JsonReader</span></span>

<span data-ttu-id="41770-383">В следующем примере показано, как использовать класс <xref:System.Text.Json.Utf8JsonReader>.</span><span class="sxs-lookup"><span data-stu-id="41770-383">The following example shows how to use the <xref:System.Text.Json.Utf8JsonReader> class:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/Utf8ReaderFromBytes.cs?name=SnippetDeserialize)]

<span data-ttu-id="41770-384">В приведенном выше коде предполагается, что переменной `jsonUtf8` является массив байтов, который содержит допустимые данные JSON в кодировке UTF-8.</span><span class="sxs-lookup"><span data-stu-id="41770-384">The preceding code assumes that the `jsonUtf8` variable is a byte array that contains valid JSON, encoded as UTF-8.</span></span>

### <a name="filter-data-using-utf8jsonreader"></a><span data-ttu-id="41770-385">Фильтрация данных с помощью Utf8JsonReader</span><span class="sxs-lookup"><span data-stu-id="41770-385">Filter data using Utf8JsonReader</span></span>

<span data-ttu-id="41770-386">В следующем примере показано, как синхронно выполнить чтение файла и поиск значения:</span><span class="sxs-lookup"><span data-stu-id="41770-386">The following example shows how to read a file synchronously and search for a value:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/Utf8ReaderFromFile.cs)]

<span data-ttu-id="41770-387">Предыдущий код:</span><span class="sxs-lookup"><span data-stu-id="41770-387">The preceding code:</span></span>

* <span data-ttu-id="41770-388">Предполагается, что JSON содержит массив объектов и каждый объект может содержать свойство name строкового типа.</span><span class="sxs-lookup"><span data-stu-id="41770-388">Assumes the JSON contains an array of objects and each object may contain a "name" property of type string.</span></span>
* <span data-ttu-id="41770-389">Подсчитывает объекты и значения свойств name, заканчивающиеся на University.</span><span class="sxs-lookup"><span data-stu-id="41770-389">Counts objects and "name" property values that end with "University".</span></span>
* <span data-ttu-id="41770-390">Предполагается, что файл кодируется как UTF-16 и перекодируется в UTF-8.</span><span class="sxs-lookup"><span data-stu-id="41770-390">Assumes the file is encoded as UTF-16 and transcodes it into UTF-8.</span></span> <span data-ttu-id="41770-391">Файл, закодированный как UTF-8, можно прочитать непосредственно в `ReadOnlySpan<byte>` с помощью следующего кода:</span><span class="sxs-lookup"><span data-stu-id="41770-391">A file encoded as UTF-8 can be read directly into a `ReadOnlySpan<byte>`, by using the following code:</span></span>

  ```csharp
  ReadOnlySpan<byte> jsonReadOnlySpan = File.ReadAllBytes(fileName);
  ```

  <span data-ttu-id="41770-392">Если файл содержит метку порядка байтов (BOM) UTF-8, удалите ее перед передачей байтов в `Utf8JsonReader`, так как средство чтения ждет текст.</span><span class="sxs-lookup"><span data-stu-id="41770-392">If the file contains a UTF-8 byte order mark (BOM), remove it before passing the bytes to the `Utf8JsonReader`, since the reader expects text.</span></span> <span data-ttu-id="41770-393">В противном случае метка порядка байтов считается недопустимым кодом JSON, и средство чтения создает исключение.</span><span class="sxs-lookup"><span data-stu-id="41770-393">Otherwise, the BOM is considered invalid JSON, and the reader throws an exception.</span></span>

<span data-ttu-id="41770-394">Ниже приведен пример JSON, который можно считать с помощью приведенного выше кода.</span><span class="sxs-lookup"><span data-stu-id="41770-394">Here's a JSON sample that the preceding code can read.</span></span> <span data-ttu-id="41770-395">Полученным итоговым сообщением будет 2 out of 4 have names that end with University (2 из 4 имеют имена, заканчивающиеся на University):</span><span class="sxs-lookup"><span data-stu-id="41770-395">The resulting summary message is "2 out of 4 have names that end with 'University'":</span></span>

[!code-json[](snippets/system-text-json-how-to/csharp/Universities.json)]

### <a name="read-from-a-stream-using-utf8jsonreader"></a><span data-ttu-id="41770-396">Чтение из потока данных с помощью Utf8JsonReader</span><span class="sxs-lookup"><span data-stu-id="41770-396">Read from a stream using Utf8JsonReader</span></span>

<span data-ttu-id="41770-397">При чтении большого файла (размером гигабайт и более) вы, скорее всего, предпочтете не загружать весь файл в память сразу.</span><span class="sxs-lookup"><span data-stu-id="41770-397">When reading a large file (a gigabyte or more in size, for example), you might want to avoid having to load the entire file into memory at once.</span></span> <span data-ttu-id="41770-398">В таких ситуациях можно использовать <xref:System.IO.FileStream>.</span><span class="sxs-lookup"><span data-stu-id="41770-398">For this scenario, you can use a <xref:System.IO.FileStream>.</span></span>

<span data-ttu-id="41770-399">При использовании `Utf8JsonReader` для чтения из потока данных действуют следующие правила:</span><span class="sxs-lookup"><span data-stu-id="41770-399">When using the `Utf8JsonReader` to read from a stream, the following rules apply:</span></span>

* <span data-ttu-id="41770-400">Буфер, который накапливает часть данных в формате JSON, должен быть не меньше самого крупного из возможных маркеров JSON, чтобы средство чтения могло продвигаться вперед.</span><span class="sxs-lookup"><span data-stu-id="41770-400">The buffer containing the partial JSON payload must be at least as big as the largest JSON token within it so that the reader can make forward progress.</span></span>
* <span data-ttu-id="41770-401">Размер буфера должен быть не меньше самой большой последовательности пробелов в JSON.</span><span class="sxs-lookup"><span data-stu-id="41770-401">The buffer must be at least as big as the largest sequence of white space within the JSON.</span></span>
* <span data-ttu-id="41770-402">Средство чтения не запоминает прочитанные данные, пока не дойдет до следующего свойства <xref:System.Text.Json.Utf8JsonReader.TokenType%2A> в структуре JSON.</span><span class="sxs-lookup"><span data-stu-id="41770-402">The reader doesn't keep track of the data it has read until it completely reads the next <xref:System.Text.Json.Utf8JsonReader.TokenType%2A> in the JSON payload.</span></span> <span data-ttu-id="41770-403">Таким образом, если в буфере еще остались байты, их нужно снова передать в средство чтения.</span><span class="sxs-lookup"><span data-stu-id="41770-403">So when there are bytes left over in the buffer, you have to pass them to the reader again.</span></span> <span data-ttu-id="41770-404">Для определения количества оставшихся байтов можно использовать <xref:System.Text.Json.Utf8JsonReader.BytesConsumed%2A>.</span><span class="sxs-lookup"><span data-stu-id="41770-404">You can use <xref:System.Text.Json.Utf8JsonReader.BytesConsumed%2A> to determine how many bytes are left over.</span></span>

<span data-ttu-id="41770-405">В примере кода ниже показано, как выполнять чтение из потока.</span><span class="sxs-lookup"><span data-stu-id="41770-405">The following code illustrates how to read from a stream.</span></span> <span data-ttu-id="41770-406">Этот пример демонстрирует <xref:System.IO.MemoryStream>.</span><span class="sxs-lookup"><span data-stu-id="41770-406">The example shows a <xref:System.IO.MemoryStream>.</span></span> <span data-ttu-id="41770-407">Аналогичный код будет работать и с <xref:System.IO.FileStream>, за исключением случаев, когда в начале `FileStream` содержится метка порядка байтов UTF-8.</span><span class="sxs-lookup"><span data-stu-id="41770-407">Similar code will work with a <xref:System.IO.FileStream>, except when the `FileStream` contains a UTF-8 BOM at the start.</span></span> <span data-ttu-id="41770-408">В этом случае необходимо удалить эти три байта из буфера, прежде чем передавать оставшиеся байты в `Utf8JsonReader`.</span><span class="sxs-lookup"><span data-stu-id="41770-408">In that case, you need to strip those three bytes from the buffer before passing the remaining bytes to the `Utf8JsonReader`.</span></span> <span data-ttu-id="41770-409">В противном случае средство чтения создаст исключение, поскольку метка порядка байтов не считается допустимой частью JSON.</span><span class="sxs-lookup"><span data-stu-id="41770-409">Otherwise the reader would throw an exception, since the BOM is not considered a valid part of the JSON.</span></span>

<span data-ttu-id="41770-410">Пример кода начинает работу с буфером в 4 КБ и удваивает размер буфера каждый раз, когда тот оказывается недостаточно велик для размещения полного маркера JSON, который потребуется средству чтения для дальнейшего перемещения по структуре данных JSON.</span><span class="sxs-lookup"><span data-stu-id="41770-410">The sample code starts with a 4KB buffer and doubles the buffer size each time it finds that the size is not big enough to fit a complete JSON token, which is required for the reader to make forward progress on the JSON payload.</span></span> <span data-ttu-id="41770-411">Представленный в этом примере фрагмент JSON приводит к увеличению размера буфера только в том случае, если задан очень маленький начальный размер буфера, например 10 байт.</span><span class="sxs-lookup"><span data-stu-id="41770-411">The JSON sample provided in the snippet triggers a buffer size increase only if you set a very small initial buffer size, for example, 10 bytes.</span></span> <span data-ttu-id="41770-412">Если указать для буфера начальное значение 10, то инструкции `Console.WriteLine` продемонстрируют причину и последствия увеличения размера буфера.</span><span class="sxs-lookup"><span data-stu-id="41770-412">If you set the initial buffer size to 10, the `Console.WriteLine` statements illustrate the cause and effect of buffer size increases.</span></span> <span data-ttu-id="41770-413">При начальном размере буфера 4 КБ весь пример JSON целиком отображается в каждой `Console.WriteLine`, и размер буфера увеличивать не нужно.</span><span class="sxs-lookup"><span data-stu-id="41770-413">At the 4KB initial buffer size, the entire sample JSON is shown by each `Console.WriteLine`, and the buffer size never has to be increased.</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/Utf8ReaderPartialRead.cs)]

<span data-ttu-id="41770-414">В примере выше ограничение на увеличение размера буфера не установлено.</span><span class="sxs-lookup"><span data-stu-id="41770-414">The preceding example sets no limit to how big the buffer can grow.</span></span> <span data-ttu-id="41770-415">Если размер маркера будет слишком большой, такой код может возвратить ошибку с исключением <xref:System.OutOfMemoryException>.</span><span class="sxs-lookup"><span data-stu-id="41770-415">If the token size is too large, the code could fail with an <xref:System.OutOfMemoryException> exception.</span></span> <span data-ttu-id="41770-416">Такое может произойти, если в JSON есть маркер размером около 1 ГБ, поскольку удвоение размера 1 ГБ приводит к переполнению буфера `int32`.</span><span class="sxs-lookup"><span data-stu-id="41770-416">This can happen if the JSON contains a token that is around 1 GB or more in size, because doubling the 1 GB size results in a size that is too large to fit into an `int32` buffer.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="41770-417">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="41770-417">Additional resources</span></span>

* [<span data-ttu-id="41770-418">Общие сведения о System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="41770-418">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="41770-419">Как написать пользовательские преобразователи для сериализации JSON (маршалинг) в .NET</span><span class="sxs-lookup"><span data-stu-id="41770-419">How to write custom converters</span></span>](system-text-json-converters-how-to.md)
* [<span data-ttu-id="41770-420">Как выполнить миграцию из Newtonsoft.Json</span><span class="sxs-lookup"><span data-stu-id="41770-420">How to migrate from Newtonsoft.Json</span></span>](system-text-json-migrate-from-newtonsoft-how-to.md)
* [<span data-ttu-id="41770-421">Поддержка DateTime и DateTimeOffset в System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="41770-421">DateTime and DateTimeOffset support in System.Text.Json</span></span>](../datetime/system-text-json-support.md)
* <span data-ttu-id="41770-422">[Справочник по API System.Text.Json](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="41770-422">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
<!-- * [System.Text.Json roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)-->
