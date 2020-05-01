---
title: Как сериализировать и десериализировать JSON с помощью C# для .NET
ms.date: 01/10/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 6324fe28b23e4df74bcf3fd1dbb7e0c14d5e3d1b
ms.sourcegitcommit: 8b02d42f93adda304246a47f49f6449fc74a3af4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/24/2020
ms.locfileid: "82135806"
---
# <a name="how-to-serialize-and-deserialize-marshal-and-unmarshal-json-in-net"></a><span data-ttu-id="8961f-102">Как сериализировать и десериализировать (маршалирование и демаршалирование) JSON в .NET</span><span class="sxs-lookup"><span data-stu-id="8961f-102">How to serialize and deserialize (marshal and unmarshal) JSON in .NET</span></span>

<span data-ttu-id="8961f-103">Эта статья содержит сведения об использовании пространства имен <xref:System.Text.Json> для сериализации и десериализации в нотации объектов JavaScript (JSON) и из нее.</span><span class="sxs-lookup"><span data-stu-id="8961f-103">This article shows how to use the <xref:System.Text.Json> namespace to serialize and deserialize to and from JavaScript Object Notation (JSON).</span></span> <span data-ttu-id="8961f-104">Если вы переносите существующий код из `Newtonsoft.Json`, ознакомьтесь со статьей [Переход с Newtonsoft.Json на System.Text.Json`System.Text.Json`](system-text-json-migrate-from-newtonsoft-how-to.md).</span><span class="sxs-lookup"><span data-stu-id="8961f-104">If you're porting existing code from `Newtonsoft.Json`, see [How to migrate to `System.Text.Json`](system-text-json-migrate-from-newtonsoft-how-to.md).</span></span>

<span data-ttu-id="8961f-105">В направлениях и образце кода библиотека используется напрямую, а не с помощью платформы, например [ASP.NET Core](/aspnet/core/).</span><span class="sxs-lookup"><span data-stu-id="8961f-105">The directions and sample code use the library directly, not through a framework such as [ASP.NET Core](/aspnet/core/).</span></span>

<span data-ttu-id="8961f-106">Большая часть примера кода сериализации устанавливает для параметра <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> значение `true` для структурирования JSON (с отступами и пробелами для удобства чтения).</span><span class="sxs-lookup"><span data-stu-id="8961f-106">Most of the serialization sample code sets <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> to `true` to "pretty-print" the JSON (with indentation and whitespace for human readability).</span></span> <span data-ttu-id="8961f-107">При использовании в рабочей среде для этого параметра обычно принимается значение по умолчанию `false`.</span><span class="sxs-lookup"><span data-stu-id="8961f-107">For production use, you would typically accept the default value of `false` for this setting.</span></span>

<span data-ttu-id="8961f-108">Примеры кода относятся к следующему классу и его вариантам:</span><span class="sxs-lookup"><span data-stu-id="8961f-108">The code examples refer to the following class and variants of it:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

## <a name="namespaces"></a><span data-ttu-id="8961f-109">Пространства имен</span><span class="sxs-lookup"><span data-stu-id="8961f-109">Namespaces</span></span>

<span data-ttu-id="8961f-110">Пространство имен <xref:System.Text.Json> содержит все точки входа и основные типы.</span><span class="sxs-lookup"><span data-stu-id="8961f-110">The <xref:System.Text.Json> namespace contains all the entry points and the main types.</span></span> <span data-ttu-id="8961f-111">Пространство имен <xref:System.Text.Json.Serialization> содержит атрибуты и интерфейсы API для сложных сценариев и настройки, характерной для сериализации и десериализации.</span><span class="sxs-lookup"><span data-stu-id="8961f-111">The <xref:System.Text.Json.Serialization> namespace contains attributes and APIs for advanced scenarios and customization specific to serialization and deserialization.</span></span> <span data-ttu-id="8961f-112">В примерах кода, приведенных в этой статье, для одного или обоих пространств имен необходимо добавить директивы `using`:</span><span class="sxs-lookup"><span data-stu-id="8961f-112">The code examples shown in this article require `using` directives for one or both of these namespaces:</span></span>

```csharp
using System.Text.Json;
using System.Text.Json.Serialization;
```

<span data-ttu-id="8961f-113">Атрибуты из пространства имен <xref:System.Runtime.Serialization> в настоящее время не поддерживаются в `System.Text.Json`.</span><span class="sxs-lookup"><span data-stu-id="8961f-113">Attributes from the <xref:System.Runtime.Serialization> namespace aren't currently supported in `System.Text.Json`.</span></span>

## <a name="how-to-write-net-objects-to-json-serialize"></a><span data-ttu-id="8961f-114">Как записать объекты .NET в JSON (сериализация)</span><span class="sxs-lookup"><span data-stu-id="8961f-114">How to write .NET objects to JSON (serialize)</span></span>

<span data-ttu-id="8961f-115">Чтобы записать JSON в строку или в файл, вызовите метод <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="8961f-115">To write JSON to a string or to a file, call the <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="8961f-116">В следующем примере показано создание JSON в виде строки:</span><span class="sxs-lookup"><span data-stu-id="8961f-116">The following example creates JSON as a string:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToString.cs?name=SnippetSerialize)]

<span data-ttu-id="8961f-117">В примере ниже для создания JSON-файла используется синхронный код:</span><span class="sxs-lookup"><span data-stu-id="8961f-117">The following example uses synchronous code to create a JSON file:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToFile.cs?name=SnippetSerialize)]

<span data-ttu-id="8961f-118">В следующем примере для создания JSON-файла используется асинхронный код:</span><span class="sxs-lookup"><span data-stu-id="8961f-118">The following example uses asynchronous code to create a JSON file:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToFileAsync.cs?name=SnippetSerialize)]

<span data-ttu-id="8961f-119">В предыдущих примерах для сериализуемого типа используется определение типа.</span><span class="sxs-lookup"><span data-stu-id="8961f-119">The preceding examples use type inference for the type being serialized.</span></span> <span data-ttu-id="8961f-120">Перегрузка `Serialize()` принимает параметр универсального типа:</span><span class="sxs-lookup"><span data-stu-id="8961f-120">An overload of `Serialize()` takes a generic type parameter:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToString.cs?name=SnippetSerializeWithGenericParameter)]

### <a name="serialization-example"></a><span data-ttu-id="8961f-121">Пример сериализации</span><span class="sxs-lookup"><span data-stu-id="8961f-121">Serialization example</span></span>

<span data-ttu-id="8961f-122">Ниже приведен пример класса, который содержит коллекции и вложенный класс:</span><span class="sxs-lookup"><span data-stu-id="8961f-122">Here's an example class that contains collections and a nested class:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPOCOs)]

<span data-ttu-id="8961f-123">Выходные данные JSON из сериализации экземпляра предыдущего типа выглядят следующим образом.</span><span class="sxs-lookup"><span data-stu-id="8961f-123">The JSON output from serializing an instance of the preceding type looks like the following example.</span></span> <span data-ttu-id="8961f-124">Выходные данные JSON по умолчанию сокращены:</span><span class="sxs-lookup"><span data-stu-id="8961f-124">The JSON output is minified by default:</span></span>

```json
{"Date":"2019-08-01T00:00:00-07:00","TemperatureCelsius":25,"Summary":"Hot","DatesAvailable":["2019-08-01T00:00:00-07:00","2019-08-02T00:00:00-07:00"],"TemperatureRanges":{"Cold":{"High":20,"Low":-10},"Hot":{"High":60,"Low":20}},"SummaryWords":["Cool","Windy","Humid"]}
```

<span data-ttu-id="8961f-125">В следующем примере показан тот же формат JSON (т. е. структурированный с пробелами и отступами):</span><span class="sxs-lookup"><span data-stu-id="8961f-125">The following example shows the same JSON, formatted (that is, pretty-printed with whitespace and indentation):</span></span>

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

### <a name="serialize-to-utf-8"></a><span data-ttu-id="8961f-126">Сериализация в UTF-8</span><span class="sxs-lookup"><span data-stu-id="8961f-126">Serialize to UTF-8</span></span>

<span data-ttu-id="8961f-127">Чтобы выполнить сериализацию в UTF-8, вызовите метод <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="8961f-127">To serialize to UTF-8, call the <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> method:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToUtf8.cs?name=SnippetSerialize)]

<span data-ttu-id="8961f-128">Также доступна перегрузка <xref:System.Text.Json.JsonSerializer.Serialize%2A>, которая принимает <xref:System.Text.Json.Utf8JsonWriter>.</span><span class="sxs-lookup"><span data-stu-id="8961f-128">A <xref:System.Text.Json.JsonSerializer.Serialize%2A> overload that takes a <xref:System.Text.Json.Utf8JsonWriter> is also available.</span></span>

<span data-ttu-id="8961f-129">Сериализация в UTF-8 происходит примерно на 5-10 % быстрее, чем при использовании строковых методов.</span><span class="sxs-lookup"><span data-stu-id="8961f-129">Serializing to UTF-8 is about 5-10% faster than using the string-based methods.</span></span> <span data-ttu-id="8961f-130">Разница заключается в том, что байты (например, UTF-8) не нужно преобразовывать в строки (UTF-16).</span><span class="sxs-lookup"><span data-stu-id="8961f-130">The difference is because the bytes (as UTF-8) don't need to be converted to strings (UTF-16).</span></span>

## <a name="serialization-behavior"></a><span data-ttu-id="8961f-131">Поведение сериализации</span><span class="sxs-lookup"><span data-stu-id="8961f-131">Serialization behavior</span></span>

* <span data-ttu-id="8961f-132">По умолчанию все открытые свойства сериализуются.</span><span class="sxs-lookup"><span data-stu-id="8961f-132">By default, all public properties are serialized.</span></span> <span data-ttu-id="8961f-133">Вы можете [указать свойства для исключения](#exclude-properties-from-serialization).</span><span class="sxs-lookup"><span data-stu-id="8961f-133">You can [specify properties to exclude](#exclude-properties-from-serialization).</span></span>
* <span data-ttu-id="8961f-134">[Кодировщик по умолчанию](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) экранирует символы, не относящиеся к ASCII, символы, учитывающие HTML, в пределах диапазона ASCII и символы, которые должны быть экранированы в соответствии со [спецификацией JSON RFC 8259](https://tools.ietf.org/html/rfc8259#section-7).</span><span class="sxs-lookup"><span data-stu-id="8961f-134">The [default encoder](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) escapes non-ASCII characters, HTML-sensitive characters within the ASCII-range, and characters that must be escaped according to [the RFC 8259 JSON spec](https://tools.ietf.org/html/rfc8259#section-7).</span></span>
* <span data-ttu-id="8961f-135">По умолчанию JSON сокращается.</span><span class="sxs-lookup"><span data-stu-id="8961f-135">By default, JSON is minified.</span></span> <span data-ttu-id="8961f-136">Вы можете [структурировать JSON](#serialize-to-formatted-json).</span><span class="sxs-lookup"><span data-stu-id="8961f-136">You can [pretty-print the JSON](#serialize-to-formatted-json).</span></span>
* <span data-ttu-id="8961f-137">По умолчанию регистр имен JSON соответствует именам в .NET.</span><span class="sxs-lookup"><span data-stu-id="8961f-137">By default, casing of JSON names matches the .NET names.</span></span> <span data-ttu-id="8961f-138">Вы можете [настроить регистр имен JSON](#customize-json-names-and-values).</span><span class="sxs-lookup"><span data-stu-id="8961f-138">You can [customize JSON name casing](#customize-json-names-and-values).</span></span>
* <span data-ttu-id="8961f-139">Обнаруживаются циклические ссылки и создаются исключения.</span><span class="sxs-lookup"><span data-stu-id="8961f-139">Circular references are detected and exceptions thrown.</span></span>
* <span data-ttu-id="8961f-140">В настоящее время поля исключаются.</span><span class="sxs-lookup"><span data-stu-id="8961f-140">Currently, fields are excluded.</span></span>

<span data-ttu-id="8961f-141">К поддерживаемым типам относятся:</span><span class="sxs-lookup"><span data-stu-id="8961f-141">Supported types include:</span></span>

* <span data-ttu-id="8961f-142">Примитивы .NET, которые сопоставляются с примитивами JavaScript, например числовыми типами, строками и логическими значениями.</span><span class="sxs-lookup"><span data-stu-id="8961f-142">.NET primitives that map to JavaScript primitives, such as numeric types, strings, and Boolean.</span></span>
* <span data-ttu-id="8961f-143">Определяемые пользователем [объекты POCO (традиционные объекты среды CLR)](https://stackoverflow.com/questions/250001/poco-definition).</span><span class="sxs-lookup"><span data-stu-id="8961f-143">User-defined [Plain Old CLR Objects (POCOs)](https://stackoverflow.com/questions/250001/poco-definition).</span></span>
* <span data-ttu-id="8961f-144">Одномерные массивы и массивы массивов (`ArrayName[][]`).</span><span class="sxs-lookup"><span data-stu-id="8961f-144">One-dimensional and jagged arrays (`ArrayName[][]`).</span></span>
* <span data-ttu-id="8961f-145">`Dictionary<string,TValue>` где `TValue` — это `object`, `JsonElement` или POCO.</span><span class="sxs-lookup"><span data-stu-id="8961f-145">`Dictionary<string,TValue>` where `TValue` is `object`, `JsonElement`, or a POCO.</span></span>
* <span data-ttu-id="8961f-146">Коллекции из следующих пространств имен.</span><span class="sxs-lookup"><span data-stu-id="8961f-146">Collections from the following namespaces.</span></span>
  * <xref:System.Collections>
  * <xref:System.Collections.Generic>
  * <xref:System.Collections.Immutable>

<span data-ttu-id="8961f-147">Для обработки дополнительных типов или для обеспечения функциональности, которая не поддерживается встроенными преобразователями, можно [реализовать пользовательские преобразователи](system-text-json-converters-how-to.md).</span><span class="sxs-lookup"><span data-stu-id="8961f-147">You can [implement custom converters](system-text-json-converters-how-to.md) to handle additional types or to provide functionality that isn't supported by the built-in converters.</span></span>

## <a name="how-to-read-json-into-net-objects-deserialize"></a><span data-ttu-id="8961f-148">Как считать JSON в объекты .NET (десериализация)</span><span class="sxs-lookup"><span data-stu-id="8961f-148">How to read JSON into .NET objects (deserialize)</span></span>

<span data-ttu-id="8961f-149">Чтобы выполнить десериализацию из строки или файла, вызовите метод <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="8961f-149">To deserialize from a string or a file, call the <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="8961f-150">В следующем примере показано считывание JSON из строки и создание экземпляра класса `WeatherForecast`, показанного ранее для [примера сериализации](#serialization-example):</span><span class="sxs-lookup"><span data-stu-id="8961f-150">The following example reads JSON from a string and creates an instance of the `WeatherForecast` class shown earlier for the [serialization example](#serialization-example):</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToString.cs?name=SnippetDeserialize)]

<span data-ttu-id="8961f-151">Чтобы выполнить десериализацию из файла с помощью синхронного кода, выполните считывание файла в строку, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="8961f-151">To deserialize from a file by using synchronous code, read the file into a string, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToFile.cs?name=SnippetDeserialize)]

<span data-ttu-id="8961f-152">Чтобы выполнить десериализацию из файла с помощью асинхронного кода, вызовите метод <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A>:</span><span class="sxs-lookup"><span data-stu-id="8961f-152">To deserialize from a file by using asynchronous code, call the <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A> method:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToFileAsync.cs?name=SnippetDeserialize)]

### <a name="deserialize-from-utf-8"></a><span data-ttu-id="8961f-153">Десериализация из UTF-8</span><span class="sxs-lookup"><span data-stu-id="8961f-153">Deserialize from UTF-8</span></span>

<span data-ttu-id="8961f-154">Для десериализации из UTF-8 вызовите перегрузку <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>, которая принимает значения `Utf8JsonReader` или `ReadOnlySpan<byte>`, как показано в следующих примерах.</span><span class="sxs-lookup"><span data-stu-id="8961f-154">To deserialize from UTF-8, call a <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> overload that takes a `Utf8JsonReader` or a `ReadOnlySpan<byte>`, as shown in the following examples.</span></span> <span data-ttu-id="8961f-155">В примерах предполагается, что JSON находится в массиве байтов jsonUtf8Bytes.</span><span class="sxs-lookup"><span data-stu-id="8961f-155">The examples assume the JSON is in a byte array named jsonUtf8Bytes.</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToUtf8.cs?name=SnippetDeserialize1)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToUtf8.cs?name=SnippetDeserialize2)]

## <a name="deserialization-behavior"></a><span data-ttu-id="8961f-156">Поведение десериализации</span><span class="sxs-lookup"><span data-stu-id="8961f-156">Deserialization behavior</span></span>

* <span data-ttu-id="8961f-157">По умолчанию при сопоставлении имен свойств учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="8961f-157">By default, property name matching is case-sensitive.</span></span> <span data-ttu-id="8961f-158">Вы можете [указать учет регистра](#case-insensitive-property-matching).</span><span class="sxs-lookup"><span data-stu-id="8961f-158">You can [specify case-insensitivity](#case-insensitive-property-matching).</span></span>
* <span data-ttu-id="8961f-159">Если JSON содержит значение для свойства, доступного только для чтения, значение игнорируется, а исключение не создается.</span><span class="sxs-lookup"><span data-stu-id="8961f-159">If the JSON contains a value for a read-only property, the value is ignored and no exception is thrown.</span></span>
* <span data-ttu-id="8961f-160">Десериализация в ссылочные типы без конструктора, не имеющего параметров, не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="8961f-160">Deserialization to reference types without a parameterless constructor isn't supported.</span></span>
* <span data-ttu-id="8961f-161">Десериализация в неизменяемые объекты или свойства только для чтения не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="8961f-161">Deserialization to immutable objects or read-only properties isn't supported.</span></span>
* <span data-ttu-id="8961f-162">По умолчанию перечисления поддерживаются в виде чисел.</span><span class="sxs-lookup"><span data-stu-id="8961f-162">By default, enums are supported as numbers.</span></span> <span data-ttu-id="8961f-163">Вы можете [сериализовать имена перечислений в качестве строк](#enums-as-strings).</span><span class="sxs-lookup"><span data-stu-id="8961f-163">You can [serialize enum names as strings](#enums-as-strings).</span></span>
* <span data-ttu-id="8961f-164">Поля не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="8961f-164">Fields aren't supported.</span></span>
* <span data-ttu-id="8961f-165">По умолчанию комментарии или завершающие запятые в JSON вызывают исключения.</span><span class="sxs-lookup"><span data-stu-id="8961f-165">By default, comments or trailing commas in the JSON throw exceptions.</span></span> <span data-ttu-id="8961f-166">Вы можете разрешить [комментарии и завершающие запятые](#allow-comments-and-trailing-commas).</span><span class="sxs-lookup"><span data-stu-id="8961f-166">You can [allow comments and trailing commas](#allow-comments-and-trailing-commas).</span></span>
* <span data-ttu-id="8961f-167">Максимальная глубина [по умолчанию](xref:System.Text.Json.JsonReaderOptions.MaxDepth) равна 64.</span><span class="sxs-lookup"><span data-stu-id="8961f-167">The [default maximum depth](xref:System.Text.Json.JsonReaderOptions.MaxDepth) is 64.</span></span>

<span data-ttu-id="8961f-168">Для обеспечения функциональности, которая не поддерживается встроенными преобразователями, можно [реализовать пользовательские преобразователи](system-text-json-converters-how-to.md).</span><span class="sxs-lookup"><span data-stu-id="8961f-168">You can [implement custom converters](system-text-json-converters-how-to.md) to provide functionality that isn't supported by the built-in converters.</span></span>

## <a name="serialize-to-formatted-json"></a><span data-ttu-id="8961f-169">Сериализация в форматированный JSON</span><span class="sxs-lookup"><span data-stu-id="8961f-169">Serialize to formatted JSON</span></span>

<span data-ttu-id="8961f-170">Чтобы структурировать выходные данные JSON, задайте для <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> значение `true`.</span><span class="sxs-lookup"><span data-stu-id="8961f-170">To pretty-print the JSON output, set <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> to `true`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToString.cs?name=SnippetSerializePrettyPrint)]

<span data-ttu-id="8961f-171">Ниже приведен пример типа для сериализации и структурирования данных JSON:</span><span class="sxs-lookup"><span data-stu-id="8961f-171">Here's an example type to be serialized and pretty-printed JSON output:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

## <a name="customize-json-names-and-values"></a><span data-ttu-id="8961f-172">Настройка имен и значений JSON</span><span class="sxs-lookup"><span data-stu-id="8961f-172">Customize JSON names and values</span></span>

<span data-ttu-id="8961f-173">По умолчанию имена и ключи словарей не изменяются в выходных данных JSON, включая регистр.</span><span class="sxs-lookup"><span data-stu-id="8961f-173">By default, property names and dictionary keys are unchanged in the JSON output, including case.</span></span> <span data-ttu-id="8961f-174">Значения перечисления представлены в виде чисел.</span><span class="sxs-lookup"><span data-stu-id="8961f-174">Enum values are represented as numbers.</span></span> <span data-ttu-id="8961f-175">В этом разделе объясняется, как выполнить такие задачи:</span><span class="sxs-lookup"><span data-stu-id="8961f-175">This section explains how to:</span></span>

* <span data-ttu-id="8961f-176">[Настраивать отдельные имена свойств](#customize-individual-property-names).</span><span class="sxs-lookup"><span data-stu-id="8961f-176">[Customize individual property names](#customize-individual-property-names)</span></span>
* <span data-ttu-id="8961f-177">[Преобразовывать все имена свойств в неоднородный регистр](#use-camel-case-for-all-json-property-names).</span><span class="sxs-lookup"><span data-stu-id="8961f-177">[Convert all property names to camel case](#use-camel-case-for-all-json-property-names)</span></span>
* <span data-ttu-id="8961f-178">[Реализовывать политики именования пользовательских свойств](#use-a-custom-json-property-naming-policy).</span><span class="sxs-lookup"><span data-stu-id="8961f-178">[Implement a custom property naming policy](#use-a-custom-json-property-naming-policy)</span></span>
* <span data-ttu-id="8961f-179">[Преобразовывать ключи словаря в "верблюжий" стиль](#camel-case-dictionary-keys).</span><span class="sxs-lookup"><span data-stu-id="8961f-179">[Convert dictionary keys to camel case](#camel-case-dictionary-keys)</span></span>
* <span data-ttu-id="8961f-180">[Преобразовывать перечисления в строки и "верблюжий" стиль](#enums-as-strings).</span><span class="sxs-lookup"><span data-stu-id="8961f-180">[Convert enums to strings and camel case](#enums-as-strings)</span></span>

<span data-ttu-id="8961f-181">Для других сценариев, требующих специальной обработки имен и значений свойств JSON, можно [реализовать пользовательские преобразователи](system-text-json-converters-how-to.md).</span><span class="sxs-lookup"><span data-stu-id="8961f-181">For other scenarios that require special handling of JSON property names and values, you can [implement custom converters](system-text-json-converters-how-to.md).</span></span>

### <a name="customize-individual-property-names"></a><span data-ttu-id="8961f-182">Настройка отдельных имен свойств</span><span class="sxs-lookup"><span data-stu-id="8961f-182">Customize individual property names</span></span>

<span data-ttu-id="8961f-183">Чтобы задать имена отдельных свойств, используйте атрибут [[JsonPropertyName]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute).</span><span class="sxs-lookup"><span data-stu-id="8961f-183">To set the name of individual properties, use the [[JsonPropertyName]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute) attribute.</span></span>

<span data-ttu-id="8961f-184">Ниже приведен пример типа для сериализации и полученный код JSON:</span><span class="sxs-lookup"><span data-stu-id="8961f-184">Here's an example type to serialize and resulting JSON:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="8961f-185">Имя свойства, заданное этим атрибутом:</span><span class="sxs-lookup"><span data-stu-id="8961f-185">The property name set by this attribute:</span></span>

* <span data-ttu-id="8961f-186">Применяется в обоих направлениях для сериализации и десериализации.</span><span class="sxs-lookup"><span data-stu-id="8961f-186">Applies in both directions, for serialization and deserialization.</span></span>
* <span data-ttu-id="8961f-187">Имеет приоритет над политиками именования свойств.</span><span class="sxs-lookup"><span data-stu-id="8961f-187">Takes precedence over property naming policies.</span></span>

### <a name="use-camel-case-for-all-json-property-names"></a><span data-ttu-id="8961f-188">Использование "верблюжьего" стиля для всех имен свойств JSON</span><span class="sxs-lookup"><span data-stu-id="8961f-188">Use camel case for all JSON property names</span></span>

<span data-ttu-id="8961f-189">Чтобы использовать "верблюжий" стиль для всех имен свойств JSON, задайте для параметра <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> значение `JsonNamingPolicy.CamelCase`, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="8961f-189">To use camel case for all JSON property names, set <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> to `JsonNamingPolicy.CamelCase`, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundTripCamelCasePropertyNames.cs?name=Serialize)]

<span data-ttu-id="8961f-190">Ниже приведен пример класса для сериализации и вывода JSON.</span><span class="sxs-lookup"><span data-stu-id="8961f-190">Here's an example class to serialize and JSON output:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="8961f-191">Политика именования свойств "верблюжьего" стиля:</span><span class="sxs-lookup"><span data-stu-id="8961f-191">The camel case property naming policy:</span></span>

* <span data-ttu-id="8961f-192">Применяется к сериализации и десериализации.</span><span class="sxs-lookup"><span data-stu-id="8961f-192">Applies to serialization and deserialization.</span></span>
* <span data-ttu-id="8961f-193">Переопределяется атрибутами `[JsonPropertyName]`.</span><span class="sxs-lookup"><span data-stu-id="8961f-193">Is overridden by `[JsonPropertyName]` attributes.</span></span> <span data-ttu-id="8961f-194">Именно поэтому имя свойства JSON, `Wind` в примере, не указано в "верблюжьем" стиле.</span><span class="sxs-lookup"><span data-stu-id="8961f-194">This is why the JSON property name `Wind` in the example is not camel case.</span></span>

### <a name="use-a-custom-json-property-naming-policy"></a><span data-ttu-id="8961f-195">Использование настраиваемой политики именования свойств JSON</span><span class="sxs-lookup"><span data-stu-id="8961f-195">Use a custom JSON property naming policy</span></span>

<span data-ttu-id="8961f-196">Чтобы использовать настраиваемую политику именования свойств JSON, создайте класс, производный от <xref:System.Text.Json.JsonNamingPolicy>, и переопределите метод <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A>, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="8961f-196">To use a custom JSON property naming policy, create a class that derives from <xref:System.Text.Json.JsonNamingPolicy> and override the <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A> method, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/UpperCaseNamingPolicy.cs)]

<span data-ttu-id="8961f-197">Затем задайте для свойства <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> экземпляр класса политики именования:</span><span class="sxs-lookup"><span data-stu-id="8961f-197">Then set the <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> property to an instance of your naming policy class:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripPropertyNamingPolicy.cs?name=SnippetSerialize)]

<span data-ttu-id="8961f-198">Ниже приведен пример класса для сериализации и вывода JSON.</span><span class="sxs-lookup"><span data-stu-id="8961f-198">Here's an example class to serialize and JSON output:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "DATE": "2019-08-01T00:00:00-07:00",
  "TEMPERATURECELSIUS": 25,
  "SUMMARY": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="8961f-199">Политика именования свойств JSON:</span><span class="sxs-lookup"><span data-stu-id="8961f-199">The JSON property naming policy:</span></span>

* <span data-ttu-id="8961f-200">Применяется к сериализации и десериализации.</span><span class="sxs-lookup"><span data-stu-id="8961f-200">Applies to serialization and deserialization.</span></span>
* <span data-ttu-id="8961f-201">Переопределяется атрибутами `[JsonPropertyName]`.</span><span class="sxs-lookup"><span data-stu-id="8961f-201">Is overridden by `[JsonPropertyName]` attributes.</span></span> <span data-ttu-id="8961f-202">Именно поэтому имя свойства JSON, `Wind` в примере, не указано в верхнем регистре.</span><span class="sxs-lookup"><span data-stu-id="8961f-202">This is why the JSON property name `Wind` in the example is not upper case.</span></span>

### <a name="camel-case-dictionary-keys"></a><span data-ttu-id="8961f-203">Ключи словаря в "верблюжьем" стиле.</span><span class="sxs-lookup"><span data-stu-id="8961f-203">Camel case dictionary keys</span></span>

<span data-ttu-id="8961f-204">Если свойство сериализуемого объекта имеет тип `Dictionary<string,TValue>`, ключи `string` можно преобразовать в "верблюжий" стиль.</span><span class="sxs-lookup"><span data-stu-id="8961f-204">If a property of an object to be serialized is of type `Dictionary<string,TValue>`, the `string` keys can be converted to camel case.</span></span> <span data-ttu-id="8961f-205">Для этого задайте для параметра <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy> значение `JsonNamingPolicy.CamelCase`, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="8961f-205">To do that, set <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy> to `JsonNamingPolicy.CamelCase`, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCamelCaseDictionaryKeys.cs?name=SnippetSerialize)]

<span data-ttu-id="8961f-206">Сериализация объекта с помощью словаря с именем `TemperatureRanges`, имеющего пары "ключ-значение" `"ColdMinTemp", 20` и `"HotMinTemp", 40`, приведет к выходным данным JSON, как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="8961f-206">Serializing an object with a dictionary named `TemperatureRanges` that has key-value pairs `"ColdMinTemp", 20` and `"HotMinTemp", 40` would result in JSON output like the following example:</span></span>

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

<span data-ttu-id="8961f-207">Политика именования в "верблюжьем" стиле для ключей словаря применяется только к сериализации.</span><span class="sxs-lookup"><span data-stu-id="8961f-207">The camel case naming policy for dictionary keys applies to serialization only.</span></span> <span data-ttu-id="8961f-208">При десериализации словаря ключи будут соответствовать JSON-файлу, даже если для параметра `DictionaryKeyPolicy` указано значение `JsonNamingPolicy.CamelCase`.</span><span class="sxs-lookup"><span data-stu-id="8961f-208">If you deserialize a dictionary, the keys will match the JSON file even if you specify `JsonNamingPolicy.CamelCase` for the `DictionaryKeyPolicy`.</span></span>

### <a name="enums-as-strings"></a><span data-ttu-id="8961f-209">Перечисление в виде строк</span><span class="sxs-lookup"><span data-stu-id="8961f-209">Enums as strings</span></span>

<span data-ttu-id="8961f-210">По умолчанию перечисления сериализуются как числа.</span><span class="sxs-lookup"><span data-stu-id="8961f-210">By default, enums are serialized as numbers.</span></span> <span data-ttu-id="8961f-211">Чтобы сериализовать имена перечислений как строки, используйте <xref:System.Text.Json.Serialization.JsonStringEnumConverter>.</span><span class="sxs-lookup"><span data-stu-id="8961f-211">To serialize enum names as strings, use the <xref:System.Text.Json.Serialization.JsonStringEnumConverter>.</span></span>

<span data-ttu-id="8961f-212">Например, предположим, что необходимо сериализовать следующий класс, имеющий перечисление:</span><span class="sxs-lookup"><span data-stu-id="8961f-212">For example, suppose you need to serialize the following class that has an enum:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithEnum)]

<span data-ttu-id="8961f-213">Если параметр "Сводка" имеет значение `Hot`, то по умолчанию сериализованный код JSON имеет числовое значение 3:</span><span class="sxs-lookup"><span data-stu-id="8961f-213">If the Summary is `Hot`, by default the serialized JSON has the numeric value 3:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": 3
}
```

<span data-ttu-id="8961f-214">Следующий пример кода сериализует имена перечислений вместо числовых значений и преобразует имена в "верблюжий" стиль:</span><span class="sxs-lookup"><span data-stu-id="8961f-214">The following sample code serializes the enum names instead of the numeric values, and converts the names to camel case:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripEnumAsString.cs?name=SnippetSerialize)]

<span data-ttu-id="8961f-215">Итоговый код JSON выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="8961f-215">The resulting JSON looks like the following example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "hot"
}
```

<span data-ttu-id="8961f-216">Имена строк перечисления можно также десериализовать, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="8961f-216">Enum string names can be deserialized as well, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripEnumAsString.cs?name=SnippetDeserialize)]

## <a name="exclude-properties-from-serialization"></a><span data-ttu-id="8961f-217">Исключение свойства из сериализации</span><span class="sxs-lookup"><span data-stu-id="8961f-217">Exclude properties from serialization</span></span>

<span data-ttu-id="8961f-218">По умолчанию все открытые свойства сериализуются.</span><span class="sxs-lookup"><span data-stu-id="8961f-218">By default, all public properties are serialized.</span></span> <span data-ttu-id="8961f-219">Если вы не хотите, чтобы некоторые из них отображались в выходных данных JSON, у вас есть несколько вариантов.</span><span class="sxs-lookup"><span data-stu-id="8961f-219">If you don't want some of them to appear in the JSON output, you have several options.</span></span> <span data-ttu-id="8961f-220">В этом разделе объясняется, как выполнить исключение:</span><span class="sxs-lookup"><span data-stu-id="8961f-220">This section explains how to exclude:</span></span>

* <span data-ttu-id="8961f-221">[отдельных свойств](#exclude-individual-properties);</span><span class="sxs-lookup"><span data-stu-id="8961f-221">[Individual properties](#exclude-individual-properties)</span></span>
* <span data-ttu-id="8961f-222">[всех свойств только для чтения](#exclude-all-read-only-properties);</span><span class="sxs-lookup"><span data-stu-id="8961f-222">[All read-only properties](#exclude-all-read-only-properties)</span></span>
* <span data-ttu-id="8961f-223">[всех свойств со значением NULL](#exclude-all-null-value-properties).</span><span class="sxs-lookup"><span data-stu-id="8961f-223">[All null-value properties](#exclude-all-null-value-properties)</span></span>

### <a name="exclude-individual-properties"></a><span data-ttu-id="8961f-224">Исключение отдельных свойств</span><span class="sxs-lookup"><span data-stu-id="8961f-224">Exclude individual properties</span></span>

<span data-ttu-id="8961f-225">Чтобы игнорировать отдельные свойства, используйте атрибут [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute).</span><span class="sxs-lookup"><span data-stu-id="8961f-225">To ignore individual properties, use the [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) attribute.</span></span>

<span data-ttu-id="8961f-226">Ниже приведен пример типа для сериализации и вывода JSON.</span><span class="sxs-lookup"><span data-stu-id="8961f-226">Here's an example type to serialize and JSON output:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithIgnoreAttribute)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
}
```

### <a name="exclude-all-read-only-properties"></a><span data-ttu-id="8961f-227">Исключение всех свойств только для чтения</span><span class="sxs-lookup"><span data-stu-id="8961f-227">Exclude all read-only properties</span></span>

<span data-ttu-id="8961f-228">Свойство доступно только для чтения, если оно содержит открытый метод получения, но не является общим методом задания.</span><span class="sxs-lookup"><span data-stu-id="8961f-228">A property is read-only if it contains a public getter but not a public setter.</span></span> <span data-ttu-id="8961f-229">Чтобы исключить все свойства только для чтения, задайте для параметра <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> значение `true`, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="8961f-229">To exclude all read-only properties, set the <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> to `true`, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeExcludeReadOnlyProperties.cs?name=SnippetSerialize)]

<span data-ttu-id="8961f-230">Ниже приведен пример типа для сериализации и вывода JSON.</span><span class="sxs-lookup"><span data-stu-id="8961f-230">Here's an example type to serialize and JSON output:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithROProperty)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
}
```

<span data-ttu-id="8961f-231">Этот параметр применяется только к сериализации.</span><span class="sxs-lookup"><span data-stu-id="8961f-231">This option applies only to serialization.</span></span> <span data-ttu-id="8961f-232">Во время десериализации свойства, доступные только для чтения, по умолчанию игнорируются.</span><span class="sxs-lookup"><span data-stu-id="8961f-232">During deserialization, read-only properties are ignored by default.</span></span>

### <a name="exclude-all-null-value-properties"></a><span data-ttu-id="8961f-233">Исключение всех свойств со значением NULL</span><span class="sxs-lookup"><span data-stu-id="8961f-233">Exclude all null value properties</span></span>

<span data-ttu-id="8961f-234">Чтобы исключить все свойства со значением NULL, задайте для параметра <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> значение `true`, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="8961f-234">To exclude all null value properties, set the <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> property to `true`, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeExcludeNullValueProperties.cs?name=SnippetSerialize)]

<span data-ttu-id="8961f-235">Ниже приведен пример объекта для сериализации и вывода JSON.</span><span class="sxs-lookup"><span data-stu-id="8961f-235">Here's an example object to serialize and JSON output:</span></span>

|<span data-ttu-id="8961f-236">Свойство.</span><span class="sxs-lookup"><span data-stu-id="8961f-236">Property</span></span> |<span data-ttu-id="8961f-237">Значение</span><span class="sxs-lookup"><span data-stu-id="8961f-237">Value</span></span>  |
|---------|---------|
| <span data-ttu-id="8961f-238">Дата</span><span class="sxs-lookup"><span data-stu-id="8961f-238">Date</span></span>    | <span data-ttu-id="8961f-239">01.08.2019 г. 00:00:00 – 7:00</span><span class="sxs-lookup"><span data-stu-id="8961f-239">8/1/2019 12:00:00 AM -07:00</span></span>|
| <span data-ttu-id="8961f-240">TemperatureCelsius</span><span class="sxs-lookup"><span data-stu-id="8961f-240">TemperatureCelsius</span></span>| <span data-ttu-id="8961f-241">25</span><span class="sxs-lookup"><span data-stu-id="8961f-241">25</span></span> |
| <span data-ttu-id="8961f-242">Сводка</span><span class="sxs-lookup"><span data-stu-id="8961f-242">Summary</span></span>| <span data-ttu-id="8961f-243">null</span><span class="sxs-lookup"><span data-stu-id="8961f-243">null</span></span>|

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25
}
```

<span data-ttu-id="8961f-244">Этот параметр применяется к сериализации и десериализации.</span><span class="sxs-lookup"><span data-stu-id="8961f-244">This setting applies to serialization and deserialization.</span></span> <span data-ttu-id="8961f-245">Сведения об его влиянии на десериализацию см. в разделе [Игнорирование значений NULL при десериализации](#ignore-null-when-deserializing).</span><span class="sxs-lookup"><span data-stu-id="8961f-245">For information about its effect on deserialization, see [Ignore null when deserializing](#ignore-null-when-deserializing).</span></span>

## <a name="customize-character-encoding"></a><span data-ttu-id="8961f-246">Настройка кодировки символов</span><span class="sxs-lookup"><span data-stu-id="8961f-246">Customize character encoding</span></span>

<span data-ttu-id="8961f-247">По умолчанию сериализатор экранирует символы, отличные от ASCII.</span><span class="sxs-lookup"><span data-stu-id="8961f-247">By default, the serializer escapes all non-ASCII characters.</span></span>  <span data-ttu-id="8961f-248">То есть он заменяет их на `\uxxxx`, где `xxxx` является кодом в кодировке Юникода символа.</span><span class="sxs-lookup"><span data-stu-id="8961f-248">That is, it replaces them with `\uxxxx` where `xxxx` is the Unicode code of the character.</span></span>  <span data-ttu-id="8961f-249">Например, если свойству `Summary` присвоено кириллическое значение "жарко", то объект `WeatherForecast` сериализуется, как показано в этом примере:</span><span class="sxs-lookup"><span data-stu-id="8961f-249">For example, if the `Summary` property is set to Cyrillic жарко, the `WeatherForecast` object is serialized as shown in this example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "\u0436\u0430\u0440\u043A\u043E"
}
```

### <a name="serialize-language-character-sets"></a><span data-ttu-id="8961f-250">Сериализация кодировки языка</span><span class="sxs-lookup"><span data-stu-id="8961f-250">Serialize language character sets</span></span>

<span data-ttu-id="8961f-251">Чтобы сериализовать кодировки одного или нескольких языков без экранирования, укажите [диапазон символов Юникода](xref:System.Text.Unicode.UnicodeRanges) при создании экземпляра <xref:System.Text.Encodings.Web.JavaScriptEncoder?displayProperty=fullName>, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="8961f-251">To serialize the character set(s) of one or more languages without escaping, specify [Unicode range(s)](xref:System.Text.Unicode.UnicodeRanges) when creating an instance of <xref:System.Text.Encodings.Web.JavaScriptEncoder?displayProperty=fullName>, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetLanguageSets)]

<span data-ttu-id="8961f-252">Этот код не поддерживает символы кириллицы или греческого языка.</span><span class="sxs-lookup"><span data-stu-id="8961f-252">This code doesn't escape Cyrillic or Greek characters.</span></span> <span data-ttu-id="8961f-253">Если свойству `Summary` присвоено кириллическое значение "жарко", то объект `WeatherForecast` сериализуется, как показано в этом примере:</span><span class="sxs-lookup"><span data-stu-id="8961f-253">If the `Summary` property is set to Cyrillic жарко, the `WeatherForecast` object is serialized as shown in this example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жарко"
}
```

<span data-ttu-id="8961f-254">Чтобы сериализовать все кодировки языка без экранирования, используйте <xref:System.Text.Unicode.UnicodeRanges.All?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="8961f-254">To serialize all language sets without escaping, use <xref:System.Text.Unicode.UnicodeRanges.All?displayProperty=nameWithType>.</span></span>

### <a name="serialize-specific-characters"></a><span data-ttu-id="8961f-255">Сериализация определенных символов</span><span class="sxs-lookup"><span data-stu-id="8961f-255">Serialize specific characters</span></span>

<span data-ttu-id="8961f-256">В качестве альтернативного способа вы можете указать отдельные символы, которые нужно разрешить, без экранирования.</span><span class="sxs-lookup"><span data-stu-id="8961f-256">An alternative is to specify individual characters that you want to allow through without being escaped.</span></span> <span data-ttu-id="8961f-257">В следующем примере сериализуются только первые два символа слова "жарко":</span><span class="sxs-lookup"><span data-stu-id="8961f-257">The following example serializes only the first two characters of жарко:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetSelectedCharacters)]

<span data-ttu-id="8961f-258">Ниже приведен пример JSON, созданный с помощью приведенного выше кода.</span><span class="sxs-lookup"><span data-stu-id="8961f-258">Here's an example of JSON produced by the preceding code:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жа\u0440\u043A\u043E"
}
```

### <a name="serialize-all-characters"></a><span data-ttu-id="8961f-259">Сериализация всех символов</span><span class="sxs-lookup"><span data-stu-id="8961f-259">Serialize all characters</span></span>

<span data-ttu-id="8961f-260">Чтобы минимизировать экранирование, можно использовать <xref:System.Text.Encodings.Web.JavaScriptEncoder.UnsafeRelaxedJsonEscaping?displayProperty=nameWithType>, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="8961f-260">To minimize escaping you can use <xref:System.Text.Encodings.Web.JavaScriptEncoder.UnsafeRelaxedJsonEscaping?displayProperty=nameWithType>, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetUnsafeRelaxed)]

> [!CAUTION]
> <span data-ttu-id="8961f-261">По сравнению с кодировщиком по умолчанию, кодировщик `UnsafeRelaxedJsonEscaping` более предпочтителен в отношении передачи символов без экранирования:</span><span class="sxs-lookup"><span data-stu-id="8961f-261">Compared to the default encoder, the `UnsafeRelaxedJsonEscaping` encoder is more permissive about allowing characters to pass through unescaped:</span></span>
>
> * <span data-ttu-id="8961f-262">Он не выполняет экранирование символов, учитывающих HTML, например `<`, `>`, `&` и `'`.</span><span class="sxs-lookup"><span data-stu-id="8961f-262">It doesn't escape HTML-sensitive characters such as `<`, `>`, `&`, and `'`.</span></span>
> * <span data-ttu-id="8961f-263">Он не предоставляет никаких дополнительных средств защиты от атак с помощью XSS или раскрытия информации, которые, например, могут возникать из-за того, что клиент и сервер не согласны с *кодировкой*.</span><span class="sxs-lookup"><span data-stu-id="8961f-263">It doesn't offer any additional defense-in-depth protections against XSS or information disclosure attacks, such as those which might result from the client and server disagreeing on the *charset*.</span></span>
>
> <span data-ttu-id="8961f-264">Используйте ненадежный кодировщик, только если известно, что клиент будет интерпретировать полученные полезные данные как JSON в кодировке UTF-8.</span><span class="sxs-lookup"><span data-stu-id="8961f-264">Use the unsafe encoder only when it's known that the client will be interpreting the resulting payload as UTF-8 encoded JSON.</span></span> <span data-ttu-id="8961f-265">Например, его можно использовать, если сервер отправляет заголовок ответа `Content-Type: application/json; charset=utf-8`.</span><span class="sxs-lookup"><span data-stu-id="8961f-265">For example, you can use it if the server is sending the response header `Content-Type: application/json; charset=utf-8`.</span></span> <span data-ttu-id="8961f-266">Никогда не допускайте, чтобы необработанные выходные данные `UnsafeRelaxedJsonEscaping` выводились на HTML-страницу или в элемент `<script>`.</span><span class="sxs-lookup"><span data-stu-id="8961f-266">Never allow the raw `UnsafeRelaxedJsonEscaping` output to be emitted into an HTML page or a `<script>` element.</span></span>

## <a name="serialize-properties-of-derived-classes"></a><span data-ttu-id="8961f-267">Сериализация свойств производных классов</span><span class="sxs-lookup"><span data-stu-id="8961f-267">Serialize properties of derived classes</span></span>

<span data-ttu-id="8961f-268">Сериализация иерархии полиморфных типов не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="8961f-268">Serialization of a polymorphic type hierarchy is not supported.</span></span> <span data-ttu-id="8961f-269">Например, если свойство определено как интерфейс или абстрактный класс, сериализуются только свойства, определенные в интерфейсе или абстрактном классе, даже если тип среды выполнения имеет дополнительные свойства.</span><span class="sxs-lookup"><span data-stu-id="8961f-269">For example, if a property is defined as an interface or an abstract class, only the properties defined on the interface or abstract class are serialized, even if the runtime type has additional properties.</span></span> <span data-ttu-id="8961f-270">В этом разделе описаны исключения из этого поведения.</span><span class="sxs-lookup"><span data-stu-id="8961f-270">The exceptions to this behavior are explained in this section.</span></span>

<span data-ttu-id="8961f-271">Например, предположим, что у вас есть класс `WeatherForecast` и производный класс `WeatherForecastDerived`:</span><span class="sxs-lookup"><span data-stu-id="8961f-271">For example, suppose you have a `WeatherForecast` class and a derived class `WeatherForecastDerived`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFDerived)]

<span data-ttu-id="8961f-272">Предположим также, что аргумент типа метода `Serialize` во время компиляции `WeatherForecast`:</span><span class="sxs-lookup"><span data-stu-id="8961f-272">And suppose the type argument of the `Serialize` method at compile time is `WeatherForecast`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializePolymorphic.cs?name=SnippetSerializeDefault)]

<span data-ttu-id="8961f-273">В этом сценарии свойство `WindSpeed` не сериализуется, даже если объект `weatherForecast` фактически является объектом `WeatherForecastDerived`.</span><span class="sxs-lookup"><span data-stu-id="8961f-273">In this scenario, the `WindSpeed` property is not serialized even if the `weatherForecast` object is actually a `WeatherForecastDerived` object.</span></span> <span data-ttu-id="8961f-274">Сериализуются только свойства базового класса:</span><span class="sxs-lookup"><span data-stu-id="8961f-274">Only the base class properties are serialized:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

<span data-ttu-id="8961f-275">Это поведение предназначено для предотвращения случайного доступа к данным в производном типе, созданном во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="8961f-275">This behavior is intended to help prevent accidental exposure of data in a derived runtime-created type.</span></span>

<span data-ttu-id="8961f-276">Чтобы сериализовать свойства производного типа в предыдущем примере, используйте один из следующих подходов:</span><span class="sxs-lookup"><span data-stu-id="8961f-276">To serialize the properties of the derived type in the preceding example, use one of the following approaches:</span></span>

* <span data-ttu-id="8961f-277">Вызовите перегрузку <xref:System.Text.Json.JsonSerializer.Serialize%2A>, которая позволяет указать тип во время выполнения:</span><span class="sxs-lookup"><span data-stu-id="8961f-277">Call an overload of <xref:System.Text.Json.JsonSerializer.Serialize%2A> that lets you specify the type at runtime:</span></span>

  [!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializePolymorphic.cs?name=SnippetSerializeGetType)]

* <span data-ttu-id="8961f-278">Объявите объект, который должен быть сериализован как `object`.</span><span class="sxs-lookup"><span data-stu-id="8961f-278">Declare the object to be serialized as `object`.</span></span>

  [!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializePolymorphic.cs?name=SnippetSerializeObject)]

<span data-ttu-id="8961f-279">В предыдущем примере сценария оба подхода приводят к тому, что `WindSpeed` свойство включается в выходные данные JSON:</span><span class="sxs-lookup"><span data-stu-id="8961f-279">In the preceding example scenario, both approaches cause the `WindSpeed` property to be included in the JSON output:</span></span>

```json
{
  "WindSpeed": 35,
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

> [!IMPORTANT]
> <span data-ttu-id="8961f-280">Эти подходы обеспечивают одноэлементную сериализацию только для сериализации корневого объекта, а не для его свойств.</span><span class="sxs-lookup"><span data-stu-id="8961f-280">These approaches provide polymorphic serialization only for the root object to be serialized, not for properties of that root object.</span></span>

<span data-ttu-id="8961f-281">Вы можете выполнить полиморфную сериализацию для объектов более низкого уровня, если вы определите их как тип `object`.</span><span class="sxs-lookup"><span data-stu-id="8961f-281">You can get polymorphic serialization for lower-level objects if you define them as type `object`.</span></span> <span data-ttu-id="8961f-282">Например, предположим, что у класса `WeatherForecast` есть свойство `PreviousForecast`, которое может быть определено как тип `WeatherForecast` или `object`:</span><span class="sxs-lookup"><span data-stu-id="8961f-282">For example, suppose your `WeatherForecast` class has a property named `PreviousForecast` that can be defined as type `WeatherForecast` or `object`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPrevious)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPreviousAsObject)]

<span data-ttu-id="8961f-283">Если свойство `PreviousForecast` содержит экземпляр `WeatherForecastDerived`:</span><span class="sxs-lookup"><span data-stu-id="8961f-283">If the `PreviousForecast` property contains an instance of `WeatherForecastDerived`:</span></span>

* <span data-ttu-id="8961f-284">Выходные данные JSON из сериализации `WeatherForecastWithPrevious` **не содержат** `WindSpeed`.</span><span class="sxs-lookup"><span data-stu-id="8961f-284">The JSON output from serializing `WeatherForecastWithPrevious` **doesn't include** `WindSpeed`.</span></span>
* <span data-ttu-id="8961f-285">Выходные данные JSON из сериализации `WeatherForecastWithPreviousAsObject` **включают в себя** `WindSpeed`.</span><span class="sxs-lookup"><span data-stu-id="8961f-285">The JSON output from serializing `WeatherForecastWithPreviousAsObject` **includes** `WindSpeed`.</span></span>

<span data-ttu-id="8961f-286">Чтобы сериализовать `WeatherForecastWithPreviousAsObject`, не нужно вызывать `Serialize<object>` или `GetType`, потому что корневой объект не является объектом, который может иметь производный тип.</span><span class="sxs-lookup"><span data-stu-id="8961f-286">To serialize `WeatherForecastWithPreviousAsObject`, it isn't necessary to call `Serialize<object>` or `GetType` because the root object isn't the one that may be of a derived type.</span></span> <span data-ttu-id="8961f-287">В следующем примере кода не вызывается `Serialize<object>` или `GetType`:</span><span class="sxs-lookup"><span data-stu-id="8961f-287">The following code example doesn't call `Serialize<object>` or `GetType`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializePolymorphic.cs?name=SnippetSerializeSecondLevel)]

<span data-ttu-id="8961f-288">Приведенный выше код правильно сериализует `WeatherForecastWithPreviousAsObject`:</span><span class="sxs-lookup"><span data-stu-id="8961f-288">The preceding code correctly serializes `WeatherForecastWithPreviousAsObject`:</span></span>

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

<span data-ttu-id="8961f-289">Аналогичный подход к определению свойств `object` работает с интерфейсами.</span><span class="sxs-lookup"><span data-stu-id="8961f-289">The same approach of defining properties as `object` works with interfaces.</span></span> <span data-ttu-id="8961f-290">Предположим, что у вас есть следующий интерфейс и реализация и вы хотите сериализовать класс со свойствами, содержащими экземпляры реализации:</span><span class="sxs-lookup"><span data-stu-id="8961f-290">Suppose you have the following interface and implementation, and you want to serialize a class with properties that contain implementation instances:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/IForecast.cs)]

<span data-ttu-id="8961f-291">Когда вы сериализуете экземпляр `Forecasts`, только `Tuesday` отображает свойство `WindSpeed`, так как `Tuesday` определяется как `object`:</span><span class="sxs-lookup"><span data-stu-id="8961f-291">When you serialize an instance of `Forecasts`, only `Tuesday` shows the `WindSpeed` property, because `Tuesday` is defined as `object`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializePolymorphic.cs?name=SnippetSerializeInterface)]

<span data-ttu-id="8961f-292">В следующем примере показан код JSON, который является результатом предыдущего кода:</span><span class="sxs-lookup"><span data-stu-id="8961f-292">The following example shows the JSON that results from the preceding code:</span></span>

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

<span data-ttu-id="8961f-293">Дополнительные сведения о полиморфной **сериализации** и **десериализации** см. в [этом разделе](system-text-json-migrate-from-newtonsoft-how-to.md#polymorphic-serialization).</span><span class="sxs-lookup"><span data-stu-id="8961f-293">For more information about polymorphic **serialization**, and for information about **deserialization**, see [How to migrate from Newtonsoft.Json to System.Text.Json](system-text-json-migrate-from-newtonsoft-how-to.md#polymorphic-serialization).</span></span>

## <a name="allow-comments-and-trailing-commas"></a><span data-ttu-id="8961f-294">Разрешение комментариев и завершающих запятых</span><span class="sxs-lookup"><span data-stu-id="8961f-294">Allow comments and trailing commas</span></span>

<span data-ttu-id="8961f-295">По умолчанию комментарии и завершающие запятые в JSON не допускаются.</span><span class="sxs-lookup"><span data-stu-id="8961f-295">By default, comments and trailing commas are not allowed in JSON.</span></span> <span data-ttu-id="8961f-296">Чтобы разрешить комментарии в JSON, задайте для свойства <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> значение `JsonCommentHandling.Skip`.</span><span class="sxs-lookup"><span data-stu-id="8961f-296">To allow comments in the JSON, set the <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> property to `JsonCommentHandling.Skip`.</span></span>
<span data-ttu-id="8961f-297">Чтобы разрешить завершающие запятые, задайте для свойства <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> значение `true`.</span><span class="sxs-lookup"><span data-stu-id="8961f-297">And to allow trailing commas, set the <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> property to `true`.</span></span> <span data-ttu-id="8961f-298">В следующем примере показано, как разрешить оба варианта:</span><span class="sxs-lookup"><span data-stu-id="8961f-298">The following example shows how to allow both:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DeserializeCommasComments.cs?name=SnippetDeserialize)]

<span data-ttu-id="8961f-299">Ниже приведен пример JSON с комментариями и завершающей запятой:</span><span class="sxs-lookup"><span data-stu-id="8961f-299">Here's example JSON with comments and a trailing comma:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25, // Fahrenheit 77
  "Summary": "Hot", /* Zharko */
}
```

## <a name="case-insensitive-property-matching"></a><span data-ttu-id="8961f-300">Сопоставление свойств без учета регистра</span><span class="sxs-lookup"><span data-stu-id="8961f-300">Case-insensitive property matching</span></span>

<span data-ttu-id="8961f-301">По умолчанию десериализация выполняет поиск совпадения имен свойств с учетом регистра между кодом JSON и свойствами целевого объекта.</span><span class="sxs-lookup"><span data-stu-id="8961f-301">By default, deserialization looks for case-sensitive property name matches between JSON and the target object properties.</span></span> <span data-ttu-id="8961f-302">Чтобы изменить это поведение, задайте для параметра <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> значение `true`.</span><span class="sxs-lookup"><span data-stu-id="8961f-302">To change that behavior, set <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> to `true`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DeserializeCaseInsensitive.cs?name=SnippetDeserialize)]

<span data-ttu-id="8961f-303">Ниже приведен пример JSON с именами свойств в "верблюжьем" стиле.</span><span class="sxs-lookup"><span data-stu-id="8961f-303">Here's example JSON with camel case property names.</span></span> <span data-ttu-id="8961f-304">Его можно десериализовать в следующий тип, который содержит имена свойств в регистре Pascal.</span><span class="sxs-lookup"><span data-stu-id="8961f-304">It can be deserialized into the following type that has Pascal case property names.</span></span>

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
}
```

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

## <a name="handle-overflow-json"></a><span data-ttu-id="8961f-305">Обработка переполнения JSON</span><span class="sxs-lookup"><span data-stu-id="8961f-305">Handle overflow JSON</span></span>

<span data-ttu-id="8961f-306">При десериализации в JSON могут быть получены данные, которые не представлены свойствами целевого типа.</span><span class="sxs-lookup"><span data-stu-id="8961f-306">While deserializing, you might receive data in the JSON that is not represented by properties of the target type.</span></span> <span data-ttu-id="8961f-307">Предположим у вас есть следующий целевой тип:</span><span class="sxs-lookup"><span data-stu-id="8961f-307">For example, suppose your target type is this:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

<span data-ttu-id="8961f-308">А десериализируемым кодом JSON является:</span><span class="sxs-lookup"><span data-stu-id="8961f-308">And the JSON to be deserialized is this:</span></span>

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

<span data-ttu-id="8961f-309">При десериализации кода JSON, показанного в указанном типе, свойства `DatesAvailable` и `SummaryWords` никуда не переходят и будут потеряны.</span><span class="sxs-lookup"><span data-stu-id="8961f-309">If you deserialize the JSON shown into the type shown, the `DatesAvailable` and `SummaryWords` properties have nowhere to go and are lost.</span></span> <span data-ttu-id="8961f-310">Чтобы записать дополнительные данные, такие как эти свойства, примените атрибут [JsonExtensionData](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute) к свойству типа `Dictionary<string,object>` или `Dictionary<string,JsonElement>`:</span><span class="sxs-lookup"><span data-stu-id="8961f-310">To capture extra data such as these properties, apply the [JsonExtensionData](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute) attribute to a property of type `Dictionary<string,object>` or `Dictionary<string,JsonElement>`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithExtensionData)]

<span data-ttu-id="8961f-311">При десериализации показанного ранее JSON в этот тип данных дополнительные данные становятся парами "ключ-значение" свойства `ExtensionData`:</span><span class="sxs-lookup"><span data-stu-id="8961f-311">When you deserialize the JSON shown earlier into this sample type, the extra data becomes key-value pairs of the `ExtensionData` property:</span></span>

|<span data-ttu-id="8961f-312">Свойство.</span><span class="sxs-lookup"><span data-stu-id="8961f-312">Property</span></span> |<span data-ttu-id="8961f-313">Значение</span><span class="sxs-lookup"><span data-stu-id="8961f-313">Value</span></span>  |<span data-ttu-id="8961f-314">Примечания</span><span class="sxs-lookup"><span data-stu-id="8961f-314">Notes</span></span>  |
|---------|---------|---------|
| <span data-ttu-id="8961f-315">Дата</span><span class="sxs-lookup"><span data-stu-id="8961f-315">Date</span></span>    | <span data-ttu-id="8961f-316">01.08.2019 г. 00:00:00 – 7:00</span><span class="sxs-lookup"><span data-stu-id="8961f-316">8/1/2019 12:00:00 AM -07:00</span></span>||
| <span data-ttu-id="8961f-317">TemperatureCelsius</span><span class="sxs-lookup"><span data-stu-id="8961f-317">TemperatureCelsius</span></span>| <span data-ttu-id="8961f-318">0</span><span class="sxs-lookup"><span data-stu-id="8961f-318">0</span></span> | <span data-ttu-id="8961f-319">Несовпадение с учетом регистра (`temperatureCelsius` в коде JSON), поэтому свойство не задано.</span><span class="sxs-lookup"><span data-stu-id="8961f-319">Case-sensitive mismatch (`temperatureCelsius` in the JSON), so the property isn't set.</span></span> |
| <span data-ttu-id="8961f-320">Сводка</span><span class="sxs-lookup"><span data-stu-id="8961f-320">Summary</span></span> | <span data-ttu-id="8961f-321">Горячий</span><span class="sxs-lookup"><span data-stu-id="8961f-321">Hot</span></span> ||
| <span data-ttu-id="8961f-322">ExtensionData</span><span class="sxs-lookup"><span data-stu-id="8961f-322">ExtensionData</span></span> | <span data-ttu-id="8961f-323">temperatureCelsius: 25</span><span class="sxs-lookup"><span data-stu-id="8961f-323">temperatureCelsius: 25</span></span> |<span data-ttu-id="8961f-324">Так как регистр не совпадает, это свойство JSON является лишним и становится парой "ключ-значение" в словаре.</span><span class="sxs-lookup"><span data-stu-id="8961f-324">Since the case didn't match, this JSON property is an extra and becomes a key-value pair in the dictionary.</span></span>|
|| <span data-ttu-id="8961f-325">DatesAvailable:</span><span class="sxs-lookup"><span data-stu-id="8961f-325">DatesAvailable:</span></span><br>  <span data-ttu-id="8961f-326">01.08.2019 г. 00:00:00 – 7:00</span><span class="sxs-lookup"><span data-stu-id="8961f-326">8/1/2019 12:00:00 AM -07:00</span></span><br><span data-ttu-id="8961f-327">02.08.2019 г. 00:00:00 – 7:00</span><span class="sxs-lookup"><span data-stu-id="8961f-327">8/2/2019 12:00:00 AM -07:00</span></span> |<span data-ttu-id="8961f-328">Дополнительное свойство из кода JSON преобразуется в пару "ключ-значение" с массивом в качестве объекта значения.</span><span class="sxs-lookup"><span data-stu-id="8961f-328">Extra property from the JSON becomes a key-value pair, with an array as the value object.</span></span>|
| |<span data-ttu-id="8961f-329">SummaryWords:</span><span class="sxs-lookup"><span data-stu-id="8961f-329">SummaryWords:</span></span><br><span data-ttu-id="8961f-330">Здорово</span><span class="sxs-lookup"><span data-stu-id="8961f-330">Cool</span></span><br><span data-ttu-id="8961f-331">Ветрено</span><span class="sxs-lookup"><span data-stu-id="8961f-331">Windy</span></span><br><span data-ttu-id="8961f-332">Влажно</span><span class="sxs-lookup"><span data-stu-id="8961f-332">Humid</span></span> |<span data-ttu-id="8961f-333">Дополнительное свойство из кода JSON преобразуется в пару "ключ-значение" с массивом в качестве объекта значения.</span><span class="sxs-lookup"><span data-stu-id="8961f-333">Extra property from the JSON becomes a key-value pair, with an array as the value object.</span></span>|

<span data-ttu-id="8961f-334">Когда целевой объект сериализуется, пары "ключ-значение" данных расширения становятся свойствами JSON точно так же, как они были во входящем коде JSON:</span><span class="sxs-lookup"><span data-stu-id="8961f-334">When the target object is serialized, the extension data key value pairs become JSON properties just as they were in the incoming JSON:</span></span>

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

<span data-ttu-id="8961f-335">Обратите внимание, что имя свойства `ExtensionData` не отображается в коде JSON.</span><span class="sxs-lookup"><span data-stu-id="8961f-335">Notice that the `ExtensionData` property name doesn't appear in the JSON.</span></span> <span data-ttu-id="8961f-336">Такое поведение позволяет JSON выполнить круговой путь без потери дополнительных данных, которые в противном случае не будут десериализованы.</span><span class="sxs-lookup"><span data-stu-id="8961f-336">This behavior lets the JSON make a round trip without losing any extra data that otherwise wouldn't be deserialized.</span></span>

## <a name="ignore-null-when-deserializing"></a><span data-ttu-id="8961f-337">Игнорирование значений NULL при десериализации</span><span class="sxs-lookup"><span data-stu-id="8961f-337">Ignore null when deserializing</span></span>

<span data-ttu-id="8961f-338">По умолчанию, если свойство в JSON имеет значение NULL, соответствующему свойству в целевом объекте присваивается значение NULL.</span><span class="sxs-lookup"><span data-stu-id="8961f-338">By default, if a property in JSON is null, the corresponding property in the target object is set to null.</span></span> <span data-ttu-id="8961f-339">В некоторых сценариях целевое свойство может иметь значение по умолчанию, и вам не будет нужно, чтобы значение NULL переопределяло значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="8961f-339">In some scenarios, the target property might have a default value, and you don't want a null value to override the default.</span></span>

<span data-ttu-id="8961f-340">Например, следующий код представляет целевой объект:</span><span class="sxs-lookup"><span data-stu-id="8961f-340">For example, suppose the following code represents your target object:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithDefault)]

<span data-ttu-id="8961f-341">Предположим, что следующий код JSON десериализуется:</span><span class="sxs-lookup"><span data-stu-id="8961f-341">And suppose the following JSON is deserialized:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": null
}
```

<span data-ttu-id="8961f-342">После десериализации свойство `Summary` объекта `WeatherForecastWithDefault` будет иметь значение NULL.</span><span class="sxs-lookup"><span data-stu-id="8961f-342">After deserialization, the `Summary` property of the `WeatherForecastWithDefault` object is null.</span></span>

<span data-ttu-id="8961f-343">Чтобы изменить это поведение, задайте для параметра <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType> значение `true`, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="8961f-343">To change this behavior, set <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType> to `true`, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DeserializeIgnoreNull.cs?name=SnippetDeserialize)]

<span data-ttu-id="8961f-344">При использовании этого параметра свойство `Summary` объекта `WeatherForecastWithDefault` принимает значение по умолчанию No summary после десериализации.</span><span class="sxs-lookup"><span data-stu-id="8961f-344">With this option, the `Summary` property of the `WeatherForecastWithDefault` object is the default value "No summary" after deserialization.</span></span>

<span data-ttu-id="8961f-345">Значения NULL в JSON пропускаются только в том случае, если они являются допустимыми.</span><span class="sxs-lookup"><span data-stu-id="8961f-345">Null values in the JSON are ignored only if they are valid.</span></span> <span data-ttu-id="8961f-346">Значения NULL для типов значений, не допускающих значения NULL, вызывают исключения.</span><span class="sxs-lookup"><span data-stu-id="8961f-346">Null values for non-nullable value types cause exceptions.</span></span>

## <a name="utf8jsonreader-utf8jsonwriter-and-jsondocument"></a><span data-ttu-id="8961f-347">Utf8JsonReader, Utf8JsonWriter и JsonDocument</span><span class="sxs-lookup"><span data-stu-id="8961f-347">Utf8JsonReader, Utf8JsonWriter, and JsonDocument</span></span>

<span data-ttu-id="8961f-348"><xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName> — это последовательный модуль чтения текста JSON в кодировке UTF-8 из `ReadOnlySpan<byte>` или `ReadOnlySequence<byte>` с высокой производительностью и низким уровнем распределения.</span><span class="sxs-lookup"><span data-stu-id="8961f-348"><xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName> is a high-performance, low allocation, forward-only reader for UTF-8 encoded JSON text, read from a `ReadOnlySpan<byte>` or `ReadOnlySequence<byte>`.</span></span> <span data-ttu-id="8961f-349">`Utf8JsonReader` — это низкоуровневый тип, с помощью которого можно создавать пользовательские средства синтаксического анализа и десериализаторы.</span><span class="sxs-lookup"><span data-stu-id="8961f-349">The `Utf8JsonReader` is a low-level type that can be used to build custom parsers and deserializers.</span></span> <span data-ttu-id="8961f-350">Метод <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> использует `Utf8JsonReader`, как описано выше.</span><span class="sxs-lookup"><span data-stu-id="8961f-350">The <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> method uses `Utf8JsonReader` under the covers.</span></span>

<span data-ttu-id="8961f-351"><xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName> — это высокопроизводительный способ записать текст JSON в кодировке UTF-8 из распространенных типов .NET, например `String`, `Int32` и `DateTime`.</span><span class="sxs-lookup"><span data-stu-id="8961f-351"><xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName> is a high-performance way to write UTF-8 encoded JSON text from common .NET types like `String`, `Int32`, and `DateTime`.</span></span> <span data-ttu-id="8961f-352">Модуль записи — это низкоуровневый тип, с помощью которого можно создавать пользовательские сериализаторы.</span><span class="sxs-lookup"><span data-stu-id="8961f-352">The writer is a low-level type that can be used to build custom serializers.</span></span> <span data-ttu-id="8961f-353">Метод <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> использует `Utf8JsonWriter`, как описано выше.</span><span class="sxs-lookup"><span data-stu-id="8961f-353">The <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> method uses `Utf8JsonWriter` under the covers.</span></span>

<span data-ttu-id="8961f-354"><xref:System.Text.Json.JsonDocument?displayProperty=fullName> предоставляет возможность создания модели DOM только для чтения с помощью `Utf8JsonReader`.</span><span class="sxs-lookup"><span data-stu-id="8961f-354"><xref:System.Text.Json.JsonDocument?displayProperty=fullName> provides the ability to build a read-only Document Object Model (DOM) by using `Utf8JsonReader`.</span></span> <span data-ttu-id="8961f-355">Модель DOM предоставляет произвольный доступ к данным в полезных данных JSON.</span><span class="sxs-lookup"><span data-stu-id="8961f-355">The DOM provides random access to data in a JSON payload.</span></span> <span data-ttu-id="8961f-356">Доступ к элементам JSON, составляющим полезные данные, можно получить с помощью типа <xref:System.Text.Json.JsonElement>.</span><span class="sxs-lookup"><span data-stu-id="8961f-356">The JSON elements that compose the payload can be accessed via the <xref:System.Text.Json.JsonElement> type.</span></span> <span data-ttu-id="8961f-357">Тип `JsonElement` предоставляет перечислители массивов и объектов вместе с API-интерфейсами для преобразования текста JSON в стандартные типы .NET.</span><span class="sxs-lookup"><span data-stu-id="8961f-357">The `JsonElement` type provides array and object enumerators along with APIs to convert JSON text to common .NET types.</span></span> <span data-ttu-id="8961f-358">`JsonDocument` предоставляет свойство <xref:System.Text.Json.JsonDocument.RootElement>.</span><span class="sxs-lookup"><span data-stu-id="8961f-358">`JsonDocument` exposes a <xref:System.Text.Json.JsonDocument.RootElement> property.</span></span>

<span data-ttu-id="8961f-359">В следующих разделах показано, как использовать эти средства для чтения и записи данных JSON.</span><span class="sxs-lookup"><span data-stu-id="8961f-359">The following sections show how to use these tools for reading and writing JSON.</span></span>

## <a name="use-jsondocument-for-access-to-data"></a><span data-ttu-id="8961f-360">Использование класса JsonDocument для доступа к данным</span><span class="sxs-lookup"><span data-stu-id="8961f-360">Use JsonDocument for access to data</span></span>

<span data-ttu-id="8961f-361">В следующем примере показано, как использовать класс <xref:System.Text.Json.JsonDocument> для произвольного доступа к данным в строке JSON:</span><span class="sxs-lookup"><span data-stu-id="8961f-361">The following example shows how to use the <xref:System.Text.Json.JsonDocument> class for random access to data in a JSON string:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/JsonDocumentDataAccess.cs?name=SnippetAverageGrades1)]

<span data-ttu-id="8961f-362">Предыдущий код:</span><span class="sxs-lookup"><span data-stu-id="8961f-362">The preceding code:</span></span>

* <span data-ttu-id="8961f-363">Предполагается, что анализируемый код JSON находится в строке `jsonString`.</span><span class="sxs-lookup"><span data-stu-id="8961f-363">Assumes the JSON to analyze is in a string named `jsonString`.</span></span>
* <span data-ttu-id="8961f-364">Вычисляет среднее значение для объектов в массиве `Students`, имеющих свойство `Grade`.</span><span class="sxs-lookup"><span data-stu-id="8961f-364">Calculates an average grade for objects in a `Students` array that have a `Grade` property.</span></span>
* <span data-ttu-id="8961f-365">Назначает значение по умолчанию 70 для учащихся, у которых нет оценки.</span><span class="sxs-lookup"><span data-stu-id="8961f-365">Assigns a default grade of 70 for students who don't have a grade.</span></span>
* <span data-ttu-id="8961f-366">Подсчитывает число учащихся путем увеличения переменной `count` с каждой итерацией.</span><span class="sxs-lookup"><span data-stu-id="8961f-366">Counts students by incrementing a `count` variable with each iteration.</span></span> <span data-ttu-id="8961f-367">Альтернативой является вызов <xref:System.Text.Json.JsonElement.GetArrayLength%2A>, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="8961f-367">An alternative is to call <xref:System.Text.Json.JsonElement.GetArrayLength%2A>, as shown in the following example:</span></span>

  [!code-csharp[](~/samples/snippets/core/system-text-json/csharp/JsonDocumentDataAccess.cs?name=SnippetAverageGrades2)]

<span data-ttu-id="8961f-368">Ниже приведен пример JSON, обрабатываемый этим кодом:</span><span class="sxs-lookup"><span data-stu-id="8961f-368">Here's an example of the JSON that this code processes:</span></span>

[!code-json[](~/samples/snippets/core/system-text-json/csharp/GradesPrettyPrint.json)]

## <a name="use-jsondocument-to-write-json"></a><span data-ttu-id="8961f-369">Использование класса JsonDocument для записи кода JSON</span><span class="sxs-lookup"><span data-stu-id="8961f-369">Use JsonDocument to write JSON</span></span>

<span data-ttu-id="8961f-370">В следующем примере показано, как записать JSON код из <xref:System.Text.Json.JsonDocument>.</span><span class="sxs-lookup"><span data-stu-id="8961f-370">The following example shows how to write JSON from a <xref:System.Text.Json.JsonDocument>:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/JsonDocumentWriteJson.cs?name=SnippetSerialize)]

<span data-ttu-id="8961f-371">Предыдущий код:</span><span class="sxs-lookup"><span data-stu-id="8961f-371">The preceding code:</span></span>

* <span data-ttu-id="8961f-372">Считывает JSON-файл, загружает данные в `JsonDocument` и записывает форматированный (структурированный) код JSON в файл.</span><span class="sxs-lookup"><span data-stu-id="8961f-372">Reads a JSON file, loads the data into a `JsonDocument`, and writes formatted (pretty-printed) JSON to a file.</span></span>
* <span data-ttu-id="8961f-373">Использует <xref:System.Text.Json.JsonDocumentOptions>, чтобы указать, что комментарии во входных данных JSON разрешены, но пропускаются.</span><span class="sxs-lookup"><span data-stu-id="8961f-373">Uses <xref:System.Text.Json.JsonDocumentOptions> to specify that comments in the input JSON are allowed but ignored.</span></span>
* <span data-ttu-id="8961f-374">По завершении для модуля записи вызывается <xref:System.Text.Json.Utf8JsonWriter.Flush%2A>.</span><span class="sxs-lookup"><span data-stu-id="8961f-374">When finished, calls <xref:System.Text.Json.Utf8JsonWriter.Flush%2A> on the writer.</span></span> <span data-ttu-id="8961f-375">В качестве альтернативы можно разрешить автоматическую запись в модуле записи при его удалении.</span><span class="sxs-lookup"><span data-stu-id="8961f-375">An alternative is to let the writer autoflush when it's disposed.</span></span>

<span data-ttu-id="8961f-376">Ниже приведен пример входных данных JSON для обработки в примере кода:</span><span class="sxs-lookup"><span data-stu-id="8961f-376">Here's an example of JSON input to be processed by the example code:</span></span>

[!code-json[](~/samples/snippets/core/system-text-json/csharp/Grades.json)]

<span data-ttu-id="8961f-377">В результате получаются следующие структурированные выходные данные JSON:</span><span class="sxs-lookup"><span data-stu-id="8961f-377">The result is the following pretty-printed JSON output:</span></span>

[!code-json[](~/samples/snippets/core/system-text-json/csharp/GradesPrettyPrint.json)]

## <a name="use-utf8jsonwriter"></a><span data-ttu-id="8961f-378">Использование Utf8JsonWriter</span><span class="sxs-lookup"><span data-stu-id="8961f-378">Use Utf8JsonWriter</span></span>

<span data-ttu-id="8961f-379">В следующем примере показано, как использовать класс <xref:System.Text.Json.Utf8JsonWriter>.</span><span class="sxs-lookup"><span data-stu-id="8961f-379">The following example shows how to use the <xref:System.Text.Json.Utf8JsonWriter> class:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Utf8WriterToStream.cs?name=SnippetSerialize)]

## <a name="use-utf8jsonreader"></a><span data-ttu-id="8961f-380">Использование Utf8JsonReader</span><span class="sxs-lookup"><span data-stu-id="8961f-380">Use Utf8JsonReader</span></span>

<span data-ttu-id="8961f-381">В следующем примере показано, как использовать класс <xref:System.Text.Json.Utf8JsonReader>.</span><span class="sxs-lookup"><span data-stu-id="8961f-381">The following example shows how to use the <xref:System.Text.Json.Utf8JsonReader> class:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Utf8ReaderFromBytes.cs?name=SnippetDeserialize)]

<span data-ttu-id="8961f-382">В приведенном выше коде предполагается, что переменной `jsonUtf8` является массив байтов, который содержит допустимые данные JSON в кодировке UTF-8.</span><span class="sxs-lookup"><span data-stu-id="8961f-382">The preceding code assumes that the `jsonUtf8` variable is a byte array that contains valid JSON, encoded as UTF-8.</span></span>

### <a name="filter-data-using-utf8jsonreader"></a><span data-ttu-id="8961f-383">Фильтрация данных с помощью Utf8JsonReader</span><span class="sxs-lookup"><span data-stu-id="8961f-383">Filter data using Utf8JsonReader</span></span>

<span data-ttu-id="8961f-384">В следующем примере показано, как синхронно выполнить чтение файла и поиск значения:</span><span class="sxs-lookup"><span data-stu-id="8961f-384">The following example shows how to read a file synchronously and search for a value:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Utf8ReaderFromFile.cs)]

<span data-ttu-id="8961f-385">Предыдущий код:</span><span class="sxs-lookup"><span data-stu-id="8961f-385">The preceding code:</span></span>

* <span data-ttu-id="8961f-386">Предполагается, что JSON содержит массив объектов и каждый объект может содержать свойство name строкового типа.</span><span class="sxs-lookup"><span data-stu-id="8961f-386">Assumes the JSON contains an array of objects and each object may contain a "name" property of type string.</span></span>
* <span data-ttu-id="8961f-387">Подсчитывает объекты и значения свойств name, заканчивающиеся на University.</span><span class="sxs-lookup"><span data-stu-id="8961f-387">Counts objects and "name" property values that end with "University".</span></span>
* <span data-ttu-id="8961f-388">Предполагается, что файл кодируется как UTF-16 и перекодируется в UTF-8.</span><span class="sxs-lookup"><span data-stu-id="8961f-388">Assumes the file is encoded as UTF-16 and transcodes it into UTF-8.</span></span> <span data-ttu-id="8961f-389">Файл, закодированный как UTF-8, можно прочитать непосредственно в `ReadOnlySpan<byte>` с помощью следующего кода:</span><span class="sxs-lookup"><span data-stu-id="8961f-389">A file encoded as UTF-8 can be read directly into a `ReadOnlySpan<byte>`, by using the following code:</span></span>

  ```csharp
  ReadOnlySpan<byte> jsonReadOnlySpan = File.ReadAllBytes(fileName);
  ```

  <span data-ttu-id="8961f-390">Если файл содержит метку порядка байтов (BOM) UTF-8, удалите ее перед передачей байтов в `Utf8JsonReader`, так как средство чтения ждет текст.</span><span class="sxs-lookup"><span data-stu-id="8961f-390">If the file contains a UTF-8 byte order mark (BOM), remove it before passing the bytes to the `Utf8JsonReader`, since the reader expects text.</span></span> <span data-ttu-id="8961f-391">В противном случае метка порядка байтов считается недопустимым кодом JSON, и средство чтения создает исключение.</span><span class="sxs-lookup"><span data-stu-id="8961f-391">Otherwise, the BOM is considered invalid JSON, and the reader throws an exception.</span></span>

<span data-ttu-id="8961f-392">Ниже приведен пример JSON, который можно считать с помощью приведенного выше кода.</span><span class="sxs-lookup"><span data-stu-id="8961f-392">Here's a JSON sample that the preceding code can read.</span></span> <span data-ttu-id="8961f-393">Полученным итоговым сообщением будет 2 out of 4 have names that end with University (2 из 4 имеют имена, заканчивающиеся на University):</span><span class="sxs-lookup"><span data-stu-id="8961f-393">The resulting summary message is "2 out of 4 have names that end with 'University'":</span></span>

[!code-json[](~/samples/snippets/core/system-text-json/csharp/Universities.json)]

## <a name="additional-resources"></a><span data-ttu-id="8961f-394">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="8961f-394">Additional resources</span></span>

* <span data-ttu-id="8961f-395">[Общие сведения о System.Text.Json](system-text-json-overview.md)</span><span class="sxs-lookup"><span data-stu-id="8961f-395">[System.Text.Json overview](system-text-json-overview.md)</span></span>
* [<span data-ttu-id="8961f-396">Как написать пользовательские преобразователи для сериализации JSON (маршалинг) в .NET</span><span class="sxs-lookup"><span data-stu-id="8961f-396">How to write custom converters</span></span>](system-text-json-converters-how-to.md)
* <span data-ttu-id="8961f-397">[Как выполнить миграцию из Newtonsoft.Json](system-text-json-migrate-from-newtonsoft-how-to.md)</span><span class="sxs-lookup"><span data-stu-id="8961f-397">[How to migrate from Newtonsoft.Json](system-text-json-migrate-from-newtonsoft-how-to.md)</span></span>
* <span data-ttu-id="8961f-398">[Поддержка DateTime и DateTimeOffset в System.Text.Json](../datetime/system-text-json-support.md)</span><span class="sxs-lookup"><span data-stu-id="8961f-398">[DateTime and DateTimeOffset support in System.Text.Json](../datetime/system-text-json-support.md)</span></span>
* <span data-ttu-id="8961f-399">[Справочник по API System.Text.Json](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="8961f-399">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
<!-- * [System.Text.Json roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)-->
