---
title: Как сериализировать и десериализировать JSON с помощью C# для .NET
description: Сведения об использовании пространства имен System.Text.Json для сериализации и десериализации формата JSON в .NET. Содержит пример кода.
ms.date: 11/30/2020
ms.custom: contperfq2
no-loc:
- System.Text.Json
- Newtonsoft.Json
zone_pivot_groups: dotnet-version
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 9ea9e2fef5ef66f2a5ff816168abfbd7b2e75276
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/01/2020
ms.locfileid: "96437672"
---
# <a name="how-to-serialize-and-deserialize-marshal-and-unmarshal-json-in-net"></a>Как сериализировать и десериализировать (маршалирование и демаршалирование) JSON в .NET

Эта статья содержит сведения об использовании пространства имен <xref:System.Text.Json?displayProperty=fullName> для сериализации и десериализации в нотации объектов JavaScript (JSON) и из нее. Если вы переносите существующий код из `Newtonsoft.Json`, ознакомьтесь со статьей [Переход с Newtonsoft.Json на System.Text.Json`System.Text.Json`](system-text-json-migrate-from-newtonsoft-how-to.md).

В направлениях и образце кода библиотека используется напрямую, а не с помощью платформы, например [ASP.NET Core](/aspnet/core/).

Большая часть примера кода сериализации устанавливает для параметра <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> значение `true` для структурирования JSON (с отступами и пробелами для удобства чтения). При использовании в рабочей среде для этого параметра обычно принимается значение по умолчанию `false`.

Примеры кода относятся к следующему классу и его вариантам:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WF":::

## <a name="namespaces"></a>Пространства имен

Пространство имен <xref:System.Text.Json> содержит все точки входа и основные типы. Пространство имен <xref:System.Text.Json.Serialization> содержит атрибуты и интерфейсы API для сложных сценариев и настройки, характерной для сериализации и десериализации. В примерах кода, приведенных в этой статье, для одного или обоих пространств имен необходимо добавить директивы `using`:

```csharp
using System.Text.Json;
using System.Text.Json.Serialization;
```

> [!IMPORTANT]
> Атрибуты из пространства имен <xref:System.Runtime.Serialization> не поддерживаются в `System.Text.Json`.

## <a name="how-to-write-net-objects-as-json-serialize"></a>Как записать объекты .NET в формате JSON (сериализация)

Чтобы записать JSON в строку или в файл, вызовите метод <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>.

В следующем примере показано создание JSON в виде строки:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToString.cs" id="Serialize":::

В примере ниже для создания JSON-файла используется синхронный код:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToFile.cs" id="Serialize":::

В следующем примере для создания JSON-файла используется асинхронный код:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToFileAsync.cs" id="Serialize":::

В предыдущих примерах для сериализуемого типа используется определение типа. Перегрузка `Serialize()` принимает параметр универсального типа:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToString.cs" id="SerializeWithGenericParameter":::

### <a name="serialization-example"></a>Пример сериализации

Ниже приведен пример класса, который содержит свойства типа коллекции и определяемый пользователем тип:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithPOCOs":::

> [!TIP]
> POCO означает [традиционный объект среды CLR](https://en.wikipedia.org/wiki/Plain_old_CLR_object). POCO — это тип .NET, который не зависит от каких-либо типов платформы, например посредством наследования или атрибутов.

Выходные данные JSON из сериализации экземпляра предыдущего типа выглядят следующим образом. По умолчанию выходные данные JSON сокращены (удалены пробелы, отступы и символы новой строки):

```json
{"Date":"2019-08-01T00:00:00-07:00","TemperatureCelsius":25,"Summary":"Hot","DatesAvailable":["2019-08-01T00:00:00-07:00","2019-08-02T00:00:00-07:00"],"TemperatureRanges":{"Cold":{"High":20,"Low":-10},"Hot":{"High":60,"Low":20}},"SummaryWords":["Cool","Windy","Humid"]}
```

В следующем примере показан тот же объект JSON, но с форматированием (т. е. структурированный с пробелами и отступами):

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

## <a name="serialize-to-utf-8"></a>Сериализация в UTF-8

Чтобы выполнить сериализацию в UTF-8, вызовите метод <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType>:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToUtf8.cs" id="Serialize":::

Также доступна перегрузка <xref:System.Text.Json.JsonSerializer.Serialize%2A>, которая принимает <xref:System.Text.Json.Utf8JsonWriter>.

Сериализация в UTF-8 происходит примерно на 5-10 % быстрее, чем при использовании строковых методов. Разница заключается в том, что байты (например, UTF-8) не нужно преобразовывать в строки (UTF-16).

## <a name="serialization-behavior"></a>Поведение сериализации

::: zone pivot="dotnet-5-0"

* По умолчанию все открытые свойства сериализуются. Вы можете [указать свойства, которые нужно игнорировать](system-text-json-ignore-properties.md).
* [Кодировщик по умолчанию](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) экранирует символы, не относящиеся к ASCII, символы, учитывающие HTML, в пределах диапазона ASCII и символы, которые должны быть экранированы в соответствии со [спецификацией JSON RFC 8259](https://tools.ietf.org/html/rfc8259#section-7).
* По умолчанию JSON сокращается. Вы можете [структурировать JSON](#serialize-to-formatted-json).
* По умолчанию регистр имен JSON соответствует именам в .NET. Вы можете [настроить регистр имен JSON](system-text-json-customize-properties.md).
* По умолчанию обнаруживаются циклические ссылки и создаются исключения. Вы можете [сохранять ссылки и обрабатывать циклические ссылки](system-text-json-preserve-references.md).
* По умолчанию [поля](../../csharp/programming-guide/classes-and-structs/fields.md) игнорируются. Вы можете [включить поля](#include-fields).

При косвенном использовании System.Text.Json в приложении ASP.NET Core некоторые поведения по умолчанию отличаются. Дополнительные сведения см. в разделе [Стандартные параметры веб-приложений для JsonSerializerOptions](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions).
::: zone-end

::: zone pivot="dotnet-core-3-1"

* По умолчанию все открытые свойства сериализуются. Вы можете [указать свойства, которые нужно игнорировать](system-text-json-ignore-properties.md).
* [Кодировщик по умолчанию](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) экранирует символы, не относящиеся к ASCII, символы, учитывающие HTML, в пределах диапазона ASCII и символы, которые должны быть экранированы в соответствии со [спецификацией JSON RFC 8259](https://tools.ietf.org/html/rfc8259#section-7).
* По умолчанию JSON сокращается. Вы можете [структурировать JSON](#serialize-to-formatted-json).
* По умолчанию регистр имен JSON соответствует именам в .NET. Вы можете [настроить регистр имен JSON](system-text-json-customize-properties.md).
* Обнаруживаются циклические ссылки и создаются исключения.
* [Поля](../../csharp/programming-guide/classes-and-structs/fields.md) игнорируются.
::: zone-end

К поддерживаемым типам относятся:
::: zone pivot="dotnet-5-0"

* Примитивы .NET, которые сопоставляются с примитивами JavaScript, например числовыми типами, строками и логическими значениями.
* Определяемые пользователем [объекты POCO (традиционные объекты среды CLR)](https://en.wikipedia.org/wiki/Plain_old_CLR_object).
* Одномерные массивы и массивы массивов (`T[][]`).
* Коллекции и словари из следующих пространств имен.
  * <xref:System.Collections>
  * <xref:System.Collections.Generic>
  * <xref:System.Collections.Immutable>
  * <xref:System.Collections.Concurrent>
  * <xref:System.Collections.Specialized>
  * <xref:System.Collections.ObjectModel>
::: zone-end

::: zone pivot="dotnet-core-3-1"

* Примитивы .NET, которые сопоставляются с примитивами JavaScript, например числовыми типами, строками и логическими значениями.
* Определяемые пользователем [объекты POCO (традиционные объекты среды CLR)](https://en.wikipedia.org/wiki/Plain_old_CLR_object).
* Одномерные массивы и массивы массивов (`ArrayName[][]`).
* `Dictionary<string,TValue>` где `TValue` — это `object`, `JsonElement` или POCO.
* Коллекции из следующих пространств имен.
  * <xref:System.Collections>
  * <xref:System.Collections.Generic>
  * <xref:System.Collections.Immutable>
  * <xref:System.Collections.Concurrent>
  * <xref:System.Collections.Specialized>
  * <xref:System.Collections.ObjectModel>
::: zone-end

Для обработки дополнительных типов или для обеспечения функциональности, которая не поддерживается встроенными преобразователями, можно [реализовать пользовательские преобразователи](system-text-json-converters-how-to.md).

## <a name="how-to-read-json-as-net-objects-deserialize"></a>Как считать JSON как объекты .NET (десериализация)

Чтобы выполнить десериализацию из строки или файла, вызовите метод <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>.

В следующем примере показано считывание JSON из строки и создание экземпляра класса `WeatherForecastWithPOCOs`, показанного ранее для [примера сериализации](#serialization-example):

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToString.cs" id="Deserialize":::

Чтобы выполнить десериализацию из файла с помощью синхронного кода, выполните считывание файла в строку, как показано в следующем примере:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToFile.cs" id="Deserialize":::

Чтобы выполнить десериализацию из файла с помощью асинхронного кода, вызовите метод <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A>:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToFileAsync.cs" id="Deserialize":::

## <a name="deserialize-from-utf-8"></a>Десериализация из UTF-8

Для десериализации из UTF-8 вызовите перегрузку <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>, которая принимает значения `ReadOnlySpan<byte>` или `Utf8JsonReader`, как показано в следующих примерах. В примерах предполагается, что JSON находится в массиве байтов jsonUtf8Bytes.

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToUtf8.cs" id="Deserialize1":::

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToUtf8.cs" id="Deserialize2":::

## <a name="deserialization-behavior"></a>Поведение десериализации

При десериализации JSON применяются следующие правила поведения:

::: zone pivot="dotnet-5-0"

* По умолчанию при сопоставлении имен свойств учитывается регистр. Вы можете [указать учет регистра](system-text-json-character-casing.md).
* Если JSON содержит значение для свойства, доступного только для чтения, значение игнорируется, а исключение не создается.
* Сериализатор не учитывает конструкторы, которые не являются открытыми.
* Поддерживается десериализация в неизменяемые объекты или свойства "только для чтения". См. статью [Неизменяемые типы и записи](system-text-json-immutability.md).
* По умолчанию перечисления поддерживаются в виде чисел. Вы можете [сериализовать имена перечислений в качестве строк](system-text-json-customize-properties.md#enums-as-strings).
* По умолчанию поля игнорируются. Вы можете [включить поля](#include-fields).
* По умолчанию комментарии или завершающие запятые в JSON вызывают исключения. Вы можете разрешить [комментарии и завершающие запятые](system-text-json-invalid-json.md).
* Максимальная глубина [по умолчанию](xref:System.Text.Json.JsonReaderOptions.MaxDepth) равна 64.

При косвенном использовании System.Text.Json в приложении ASP.NET Core некоторые поведения по умолчанию отличаются. Дополнительные сведения см. в разделе [Стандартные параметры веб-приложений для JsonSerializerOptions](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions).
::: zone-end

::: zone pivot="dotnet-core-3-1"

* По умолчанию при сопоставлении имен свойств учитывается регистр. Вы можете [указать учет регистра](system-text-json-character-casing.md). Приложения ASP.NET Core [указывают учет регистра по умолчанию](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions).
* Если JSON содержит значение для свойства, доступного только для чтения, значение игнорируется, а исключение не создается.
* Для десериализации используется конструктор без параметров, который может быть общедоступным, внутренним или частным.
* Десериализация в неизменяемые объекты или свойства только для чтения не поддерживается.
* По умолчанию перечисления поддерживаются в виде чисел. Вы можете [сериализовать имена перечислений в качестве строк](system-text-json-customize-properties.md#enums-as-strings).
* Поля не поддерживаются.
* По умолчанию комментарии или завершающие запятые в JSON вызывают исключения. Вы можете разрешить [комментарии и завершающие запятые](system-text-json-invalid-json.md).
* Максимальная глубина [по умолчанию](xref:System.Text.Json.JsonReaderOptions.MaxDepth) равна 64.

При косвенном использовании System.Text.Json в приложении ASP.NET Core некоторые поведения по умолчанию отличаются. Дополнительные сведения см. в разделе [Стандартные параметры веб-приложений для JsonSerializerOptions](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions).
::: zone-end

Для обеспечения функциональности, которая не поддерживается встроенными преобразователями, можно [реализовать пользовательские преобразователи](system-text-json-converters-how-to.md).

## <a name="serialize-to-formatted-json"></a>Сериализация в форматированный JSON

Чтобы структурировать выходные данные JSON, задайте для <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> значение `true`.

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToString.cs" id="SerializePrettyPrint":::

Ниже приведен пример типа для сериализации и структурирования данных JSON:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WF":::

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

## <a name="include-fields"></a>Включение полей

::: zone pivot="dotnet-5-0"
Используйте глобальный параметр <xref:System.Text.Json.JsonSerializerOptions.IncludeFields?displayProperty=nameWithType> или атрибут [[JsonInclude]](xref:System.Text.Json.Serialization.JsonIncludeAttribute) для включения поля при сериализации или десериализации, как показано ниже:

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/Fields.cs" highlight="16,18,20,32-35":::

Чтобы пропустить поля, предназначенные только для чтения, используйте глобальный параметр <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyFields%2A?displayProperty=nameWithType>.
::: zone-end

::: zone pivot="dotnet-core-3-1"
Поля не поддерживаются в System.Text.Json в .NET Core 3.1. Эта функция может быть предоставлена [пользовательскими преобразователями](system-text-json-converters-how-to.md).
::: zone-end

## <a name="httpclient-and-httpcontent-extension-methods"></a>Методы расширения HttpClient и HttpContent

::: zone pivot="dotnet-5-0"

Сериализация и десериализация полезных данных JSON из сети являются обычными операциями. Методы расширения в [HttpClient](xref:System.Net.Http.Json.HttpClientJsonExtensions) и [HttpContent](xref:System.Net.Http.Json.HttpContentJsonExtensions) позволяют выполнять эти операции в одной строке кода. Эти методы расширения используют [стандартные параметры веб-приложений для JsonSerializerOptions](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions).

В следующем примере демонстрируется применение <xref:System.Net.Http.Json.HttpClientJsonExtensions.GetFromJsonAsync%2A?displayProperty=nameWithType> и <xref:System.Net.Http.Json.HttpClientJsonExtensions.PostAsJsonAsync%2A?displayProperty=nameWithType>:

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/HttpClientExtensionMethods.cs" highlight="26,33":::

Для System.Text.Json существуют также методы расширения на [HttpContent](xref:System.Net.Http.Json.HttpContentJsonExtensions).
::: zone-end

::: zone pivot="dotnet-core-3-1"
Методы расширения на `HttpClient` и `HttpContent` недоступны в System.Text.Json для .NET Core 3.1.
::: zone-end

## <a name="see-also"></a>См. также раздел

* [Общие сведения о System.Text.Json](system-text-json-overview.md)
* [Как написать пользовательские преобразователи для сериализации JSON (маршалинг) в .NET](system-text-json-converters-how-to.md)
* [Как выполнить миграцию из Newtonsoft.Json](system-text-json-migrate-from-newtonsoft-how-to.md)
* [Поддержка DateTime и DateTimeOffset в System.Text.Json](../datetime/system-text-json-support.md)
* [Справочник по API System.Text.Json](xref:System.Text.Json)
<!-- * [System.Text.Json roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)-->
