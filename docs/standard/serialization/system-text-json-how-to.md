---
title: Как сериализировать и десериализировать JSON с помощью C# для .NET
description: Сведения об использовании пространства имен System.Text.Json для сериализации и десериализации формата JSON в .NET. В ней приведен также пример кода.
ms.date: 10/09/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 0fda248b7d2e5a7cfa748447d0265565cb160b7e
ms.sourcegitcommit: e078b7540a8293ca1b604c9c0da1ff1506f0170b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "91997772"
---
# <a name="how-to-serialize-and-deserialize-marshal-and-unmarshal-json-in-net"></a>Как сериализировать и десериализировать (маршалирование и демаршалирование) JSON в .NET

Эта статья содержит сведения об использовании пространства имен <xref:System.Text.Json?displayProperty=fullName> для сериализации и десериализации в нотации объектов JavaScript (JSON) и из нее. Если вы переносите существующий код из `Newtonsoft.Json`, ознакомьтесь со статьей [Переход с Newtonsoft.Json на System.Text.Json`System.Text.Json`](system-text-json-migrate-from-newtonsoft-how-to.md).

В направлениях и образце кода библиотека используется напрямую, а не с помощью платформы, например [ASP.NET Core](/aspnet/core/).

Большая часть примера кода сериализации устанавливает для параметра <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> значение `true` для структурирования JSON (с отступами и пробелами для удобства чтения). При использовании в рабочей среде для этого параметра обычно принимается значение по умолчанию `false`.

Примеры кода относятся к следующему классу и его вариантам:

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

## <a name="namespaces"></a>Пространства имен

Пространство имен <xref:System.Text.Json> содержит все точки входа и основные типы. Пространство имен <xref:System.Text.Json.Serialization> содержит атрибуты и интерфейсы API для сложных сценариев и настройки, характерной для сериализации и десериализации. В примерах кода, приведенных в этой статье, для одного или обоих пространств имен необходимо добавить директивы `using`:

```csharp
using System.Text.Json;
using System.Text.Json.Serialization;
```

Атрибуты из пространства имен <xref:System.Runtime.Serialization> в настоящее время не поддерживаются в `System.Text.Json`.

## <a name="how-to-write-net-objects-to-json-serialize"></a>Как записать объекты .NET в JSON (сериализация)

Чтобы записать JSON в строку или в файл, вызовите метод <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>.

В следующем примере показано создание JSON в виде строки:

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToString.cs?name=SnippetSerialize)]

В примере ниже для создания JSON-файла используется синхронный код:

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToFile.cs?name=SnippetSerialize)]

В следующем примере для создания JSON-файла используется асинхронный код:

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToFileAsync.cs?name=SnippetSerialize)]

В предыдущих примерах для сериализуемого типа используется определение типа. Перегрузка `Serialize()` принимает параметр универсального типа:

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToString.cs?name=SnippetSerializeWithGenericParameter)]

### <a name="serialization-example"></a>Пример сериализации

Ниже приведен пример класса, который содержит свойства типа коллекции и определяемый пользователем тип:

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPOCOs)]

> [!TIP]
> POCO означает [традиционный объект среды CLR](https://en.wikipedia.org/wiki/Plain_old_CLR_object). POCO — это тип .NET, который не зависит от каких-либо типов платформы, например посредством наследования или атрибутов.

Выходные данные JSON из сериализации экземпляра предыдущего типа выглядят следующим образом. Выходные данные JSON по умолчанию сокращены:

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

### <a name="serialize-to-utf-8"></a>Сериализация в UTF-8

Чтобы выполнить сериализацию в UTF-8, вызовите метод <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType>:

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToUtf8.cs?name=SnippetSerialize)]

Также доступна перегрузка <xref:System.Text.Json.JsonSerializer.Serialize%2A>, которая принимает <xref:System.Text.Json.Utf8JsonWriter>.

Сериализация в UTF-8 происходит примерно на 5-10 % быстрее, чем при использовании строковых методов. Разница заключается в том, что байты (например, UTF-8) не нужно преобразовывать в строки (UTF-16).

## <a name="serialization-behavior"></a>Поведение сериализации

* По умолчанию все открытые свойства сериализуются. Вы можете [указать свойства для исключения](#exclude-properties-from-serialization).
* [Кодировщик по умолчанию](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) экранирует символы, не относящиеся к ASCII, символы, учитывающие HTML, в пределах диапазона ASCII и символы, которые должны быть экранированы в соответствии со [спецификацией JSON RFC 8259](https://tools.ietf.org/html/rfc8259#section-7).
* По умолчанию JSON сокращается. Вы можете [структурировать JSON](#serialize-to-formatted-json).
* По умолчанию регистр имен JSON соответствует именам в .NET. Вы можете [настроить регистр имен JSON](#customize-json-names-and-values).
* Обнаруживаются циклические ссылки и создаются исключения.
* В настоящее время [поля](../../csharp/programming-guide/classes-and-structs/fields.md) исключаются.

К поддерживаемым типам относятся:

* Примитивы .NET, которые сопоставляются с примитивами JavaScript, например числовыми типами, строками и логическими значениями.
* Определяемые пользователем [объекты POCO (традиционные объекты среды CLR)](https://en.wikipedia.org/wiki/Plain_old_CLR_object).
* Одномерные массивы и массивы массивов (`ArrayName[][]`).
* `Dictionary<string,TValue>` где `TValue` — это `object`, `JsonElement` или POCO.
* Коллекции из следующих пространств имен.
  * <xref:System.Collections>
  * <xref:System.Collections.Generic>
  * <xref:System.Collections.Immutable>

Для обработки дополнительных типов или для обеспечения функциональности, которая не поддерживается встроенными преобразователями, можно [реализовать пользовательские преобразователи](system-text-json-converters-how-to.md).

## <a name="how-to-read-json-into-net-objects-deserialize"></a>Как считать JSON в объекты .NET (десериализация)

Чтобы выполнить десериализацию из строки или файла, вызовите метод <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>.

В следующем примере показано считывание JSON из строки и создание экземпляра класса `WeatherForecastWithPOCOs`, показанного ранее для [примера сериализации](#serialization-example):

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToString.cs?name=SnippetDeserialize)]

Чтобы выполнить десериализацию из файла с помощью синхронного кода, выполните считывание файла в строку, как показано в следующем примере:

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToFile.cs?name=SnippetDeserialize)]

Чтобы выполнить десериализацию из файла с помощью асинхронного кода, вызовите метод <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A>:

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToFileAsync.cs?name=SnippetDeserialize)]

### <a name="deserialize-from-utf-8"></a>Десериализация из UTF-8

Для десериализации из UTF-8 вызовите перегрузку <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>, которая принимает значения `Utf8JsonReader` или `ReadOnlySpan<byte>`, как показано в следующих примерах. В примерах предполагается, что JSON находится в массиве байтов jsonUtf8Bytes.

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToUtf8.cs?name=SnippetDeserialize1)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToUtf8.cs?name=SnippetDeserialize2)]

## <a name="deserialization-behavior"></a>Поведение десериализации

При десериализации JSON применяются следующие правила поведения:

* По умолчанию при сопоставлении имен свойств учитывается регистр. Вы можете [указать учет регистра](#case-insensitive-property-matching).
* Если JSON содержит значение для свойства, доступного только для чтения, значение игнорируется, а исключение не создается.
* Конструкторы для десериализации:
  - В .NET Core 3.0 и 3.1 для десериализации используется конструктор без параметров, который может быть открытым, внутренним или закрытым.
  - В .NET 5.0 и более поздних версиях сериализатор не учитывает конструкторы, которые не являются открытыми. Тем не менее, если конструктор без параметров недоступен, можно использовать параметризованные конструкторы.
* Десериализация в неизменяемые объекты или свойства только для чтения не поддерживается.
* По умолчанию перечисления поддерживаются в виде чисел. Вы можете [сериализовать имена перечислений в качестве строк](#enums-as-strings).
* Поля не поддерживаются.
* По умолчанию комментарии или завершающие запятые в JSON вызывают исключения. Вы можете разрешить [комментарии и завершающие запятые](#allow-comments-and-trailing-commas).
* Максимальная глубина [по умолчанию](xref:System.Text.Json.JsonReaderOptions.MaxDepth) равна 64.

Для обеспечения функциональности, которая не поддерживается встроенными преобразователями, можно [реализовать пользовательские преобразователи](system-text-json-converters-how-to.md).

## <a name="serialize-to-formatted-json"></a>Сериализация в форматированный JSON

Чтобы структурировать выходные данные JSON, задайте для <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> значение `true`.

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToString.cs?name=SnippetSerializePrettyPrint)]

Ниже приведен пример типа для сериализации и структурирования данных JSON:

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

## <a name="customize-json-names-and-values"></a>Настройка имен и значений JSON

По умолчанию имена и ключи словарей не изменяются в выходных данных JSON, включая регистр. Значения перечисления представлены в виде чисел. В этом разделе объясняется, как выполнить такие задачи:

* [Настраивать отдельные имена свойств](#customize-individual-property-names).
* [Преобразовывать все имена свойств в неоднородный регистр](#use-camel-case-for-all-json-property-names).
* [Реализовывать политики именования пользовательских свойств](#use-a-custom-json-property-naming-policy).
* [Преобразовывать ключи словаря в "верблюжий" стиль](#camel-case-dictionary-keys).
* [Преобразовывать перечисления в строки и "верблюжий" стиль](#enums-as-strings).

Для других сценариев, требующих специальной обработки имен и значений свойств JSON, можно [реализовать пользовательские преобразователи](system-text-json-converters-how-to.md).

### <a name="customize-individual-property-names"></a>Настройка отдельных имен свойств

Чтобы задать имена отдельных свойств, используйте атрибут [[JsonPropertyName]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute).

Ниже приведен пример типа для сериализации и полученный код JSON:

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "Wind": 35
}
```

Имя свойства, заданное этим атрибутом:

* Применяется в обоих направлениях для сериализации и десериализации.
* Имеет приоритет над политиками именования свойств.

### <a name="use-camel-case-for-all-json-property-names"></a>Использование "верблюжьего" стиля для всех имен свойств JSON

Чтобы использовать "верблюжий" стиль для всех имен свойств JSON, задайте для параметра <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> значение `JsonNamingPolicy.CamelCase`, как показано в следующем примере:

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundTripCamelCasePropertyNames.cs?name=Serialize)]

Ниже приведен пример класса для сериализации и вывода JSON.

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
  "Wind": 35
}
```

Политика именования свойств "верблюжьего" стиля:

* Применяется к сериализации и десериализации.
* Переопределяется атрибутами `[JsonPropertyName]`. Именно поэтому имя свойства JSON, `Wind` в примере, не указано в "верблюжьем" стиле.

### <a name="use-a-custom-json-property-naming-policy"></a>Использование настраиваемой политики именования свойств JSON

Чтобы использовать настраиваемую политику именования свойств JSON, создайте класс, производный от <xref:System.Text.Json.JsonNamingPolicy>, и переопределите метод <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A>, как показано в следующем примере:

[!code-csharp[](snippets/system-text-json-how-to/csharp/UpperCaseNamingPolicy.cs)]

Затем задайте для свойства <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> экземпляр класса политики именования:

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripPropertyNamingPolicy.cs?name=SnippetSerialize)]

Ниже приведен пример класса для сериализации и вывода JSON.

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "DATE": "2019-08-01T00:00:00-07:00",
  "TEMPERATURECELSIUS": 25,
  "SUMMARY": "Hot",
  "Wind": 35
}
```

Политика именования свойств JSON:

* Применяется к сериализации и десериализации.
* Переопределяется атрибутами `[JsonPropertyName]`. Именно поэтому имя свойства JSON, `Wind` в примере, не указано в верхнем регистре.

### <a name="camel-case-dictionary-keys"></a>Ключи словаря в "верблюжьем" стиле.

Если свойство сериализуемого объекта имеет тип `Dictionary<string,TValue>`, ключи `string` можно преобразовать в "верблюжий" стиль. Для этого задайте для параметра <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy> значение `JsonNamingPolicy.CamelCase`, как показано в следующем примере:

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCamelCaseDictionaryKeys.cs?name=SnippetSerialize)]

Сериализация объекта с помощью словаря с именем `TemperatureRanges`, имеющего пары "ключ-значение" `"ColdMinTemp", 20` и `"HotMinTemp", 40`, приведет к выходным данным JSON, как в следующем примере:

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

Политика именования в "верблюжьем" стиле для ключей словаря применяется только к сериализации. При десериализации словаря ключи будут соответствовать JSON-файлу, даже если для параметра `DictionaryKeyPolicy` указано значение `JsonNamingPolicy.CamelCase`.

### <a name="enums-as-strings"></a>Перечисление в виде строк

По умолчанию перечисления сериализуются как числа. Чтобы сериализовать имена перечислений как строки, используйте <xref:System.Text.Json.Serialization.JsonStringEnumConverter>.

Например, предположим, что необходимо сериализовать следующий класс, имеющий перечисление:

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithEnum)]

Если параметр "Сводка" имеет значение `Hot`, то по умолчанию сериализованный код JSON имеет числовое значение 3:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": 3
}
```

Следующий пример кода сериализует имена перечислений вместо числовых значений и преобразует имена в "верблюжий" стиль:

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripEnumAsString.cs?name=SnippetSerialize)]

Итоговый код JSON выглядит следующим образом:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "hot"
}
```

Имена строк перечисления можно также десериализовать, как показано в следующем примере:

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripEnumAsString.cs?name=SnippetDeserialize)]

## <a name="exclude-properties-from-serialization"></a>Исключение свойства из сериализации

По умолчанию все открытые свойства сериализуются. Если вы не хотите, чтобы некоторые из них отображались в выходных данных JSON, у вас есть несколько вариантов. В этом разделе объясняется, как выполнить исключение:

* [отдельных свойств](#exclude-individual-properties);
* [всех свойств только для чтения](#exclude-all-read-only-properties);
* [всех свойств со значением NULL](#exclude-all-null-value-properties).

### <a name="exclude-individual-properties"></a>Исключение отдельных свойств

Чтобы игнорировать отдельные свойства, используйте атрибут [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute).

Ниже приведен пример типа для сериализации и вывода JSON.

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithIgnoreAttribute)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
}
```

### <a name="exclude-all-read-only-properties"></a>Исключение всех свойств только для чтения

Свойство доступно только для чтения, если оно содержит открытый метод получения, но не является общим методом задания. Чтобы исключить все свойства только для чтения, задайте для параметра <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> значение `true`, как показано в следующем примере:

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeExcludeReadOnlyProperties.cs?name=SnippetSerialize)]

Ниже приведен пример типа для сериализации и вывода JSON.

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithROProperty)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
}
```

Этот параметр применяется только к сериализации. Во время десериализации свойства, доступные только для чтения, по умолчанию игнорируются.

### <a name="exclude-all-null-value-properties"></a>Исключение всех свойств со значением NULL

Чтобы исключить все свойства со значением NULL, задайте для параметра <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> значение `true`, как показано в следующем примере:

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeExcludeNullValueProperties.cs?name=SnippetSerialize)]

Ниже приведен пример объекта для сериализации и вывода JSON.

|Свойство. |Значение  |
|---------|---------|
| Дата    | 01.08.2019 г. 00:00:00 – 7:00|
| TemperatureCelsius| 25 |
| Сводка| null|

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25
}
```

Этот параметр применяется к сериализации и десериализации. Сведения об его влиянии на десериализацию см. в разделе [Игнорирование значений NULL при десериализации](#ignore-null-when-deserializing).

## <a name="customize-character-encoding"></a>Настройка кодировки символов

По умолчанию сериализатор экранирует символы, отличные от ASCII.  То есть он заменяет их на `\uxxxx`, где `xxxx` является кодом в кодировке Юникода символа.  Например, если свойству `Summary` присвоено кириллическое значение "жарко", то объект `WeatherForecast` сериализуется, как показано в этом примере:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "\u0436\u0430\u0440\u043A\u043E"
}
```

### <a name="serialize-language-character-sets"></a>Сериализация кодировки языка

Чтобы сериализовать кодировки одного или нескольких языков без экранирования, укажите [диапазон символов Юникода](xref:System.Text.Unicode.UnicodeRanges) при создании экземпляра <xref:System.Text.Encodings.Web.JavaScriptEncoder?displayProperty=fullName>, как показано в следующем примере:

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetLanguageSets)]

Этот код не поддерживает символы кириллицы или греческого языка. Если свойству `Summary` присвоено кириллическое значение "жарко", то объект `WeatherForecast` сериализуется, как показано в этом примере:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жарко"
}
```

Чтобы сериализовать все кодировки языка без экранирования, используйте <xref:System.Text.Unicode.UnicodeRanges.All?displayProperty=nameWithType>.

### <a name="serialize-specific-characters"></a>Сериализация определенных символов

В качестве альтернативного способа вы можете указать отдельные символы, которые нужно разрешить, без экранирования. В следующем примере сериализуются только первые два символа слова "жарко":

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetSelectedCharacters)]

Ниже приведен пример JSON, созданный с помощью приведенного выше кода.

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жа\u0440\u043A\u043E"
}
```

### <a name="serialize-all-characters"></a>Сериализация всех символов

Чтобы минимизировать экранирование, можно использовать <xref:System.Text.Encodings.Web.JavaScriptEncoder.UnsafeRelaxedJsonEscaping?displayProperty=nameWithType>, как показано в следующем примере:

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetUnsafeRelaxed)]

> [!CAUTION]
> По сравнению с кодировщиком по умолчанию, кодировщик `UnsafeRelaxedJsonEscaping` более предпочтителен в отношении передачи символов без экранирования:
>
> * Он не выполняет экранирование символов, учитывающих HTML, например `<`, `>`, `&` и `'`.
> * Он не предоставляет никаких дополнительных средств защиты от атак с помощью XSS или раскрытия информации, которые, например, могут возникать из-за того, что клиент и сервер не согласны с *кодировкой*.
>
> Используйте ненадежный кодировщик, только если известно, что клиент будет интерпретировать полученные полезные данные как JSON в кодировке UTF-8. Например, его можно использовать, если сервер отправляет заголовок ответа `Content-Type: application/json; charset=utf-8`. Никогда не допускайте, чтобы необработанные выходные данные `UnsafeRelaxedJsonEscaping` выводились на HTML-страницу или в элемент `<script>`.

## <a name="serialize-properties-of-derived-classes"></a>Сериализация свойств производных классов

Сериализация иерархии полиморфных типов не поддерживается. Например, если свойство определено как интерфейс или абстрактный класс, сериализуются только свойства, определенные в интерфейсе или абстрактном классе, даже если тип среды выполнения имеет дополнительные свойства. В этом разделе описаны исключения из этого поведения.

Например, предположим, что у вас есть класс `WeatherForecast` и производный класс `WeatherForecastDerived`:

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFDerived)]

Предположим также, что аргумент типа метода `Serialize` во время компиляции `WeatherForecast`:

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs?name=SnippetSerializeDefault)]

В этом сценарии свойство `WindSpeed` не сериализуется, даже если объект `weatherForecast` фактически является объектом `WeatherForecastDerived`. Сериализуются только свойства базового класса:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

Это поведение предназначено для предотвращения случайного доступа к данным в производном типе, созданном во время выполнения.

Чтобы сериализовать свойства производного типа в предыдущем примере, используйте один из следующих подходов:

* Вызовите перегрузку <xref:System.Text.Json.JsonSerializer.Serialize%2A>, которая позволяет указать тип во время выполнения:

  [!code-csharp[](snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs?name=SnippetSerializeGetType)]

* Объявите объект, который должен быть сериализован как `object`.

  [!code-csharp[](snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs?name=SnippetSerializeObject)]

В предыдущем примере сценария оба подхода приводят к тому, что `WindSpeed` свойство включается в выходные данные JSON:

```json
{
  "WindSpeed": 35,
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

> [!IMPORTANT]
> Эти подходы обеспечивают одноэлементную сериализацию только для сериализации корневого объекта, а не для его свойств.

Вы можете выполнить полиморфную сериализацию для объектов более низкого уровня, если вы определите их как тип `object`. Например, предположим, что у класса `WeatherForecast` есть свойство `PreviousForecast`, которое может быть определено как тип `WeatherForecast` или `object`:

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPrevious)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPreviousAsObject)]

Если свойство `PreviousForecast` содержит экземпляр `WeatherForecastDerived`:

* Выходные данные JSON из сериализации `WeatherForecastWithPrevious` **не содержат** `WindSpeed`.
* Выходные данные JSON из сериализации `WeatherForecastWithPreviousAsObject` **включают в себя** `WindSpeed`.

Чтобы сериализовать `WeatherForecastWithPreviousAsObject`, не нужно вызывать `Serialize<object>` или `GetType`, потому что корневой объект не является объектом, который может иметь производный тип. В следующем примере кода не вызывается `Serialize<object>` или `GetType`:

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs?name=SnippetSerializeSecondLevel)]

Приведенный выше код правильно сериализует `WeatherForecastWithPreviousAsObject`:

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

Аналогичный подход к определению свойств `object` работает с интерфейсами. Предположим, что у вас есть следующий интерфейс и реализация и вы хотите сериализовать класс со свойствами, содержащими экземпляры реализации:

[!code-csharp[](snippets/system-text-json-how-to/csharp/IForecast.cs)]

Когда вы сериализуете экземпляр `Forecasts`, только `Tuesday` отображает свойство `WindSpeed`, так как `Tuesday` определяется как `object`:

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs?name=SnippetSerializeInterface)]

В следующем примере показан код JSON, который является результатом предыдущего кода:

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

Дополнительные сведения о полиморфной **сериализации** и **десериализации** см. в статье [Миграция из Newtonsoft.Json в System.Text.Json](system-text-json-migrate-from-newtonsoft-how-to.md#polymorphic-serialization).

## <a name="allow-comments-and-trailing-commas"></a>Разрешение комментариев и завершающих запятых

По умолчанию комментарии и завершающие запятые в JSON не допускаются. Чтобы разрешить комментарии в JSON, задайте для свойства <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> значение `JsonCommentHandling.Skip`.
Чтобы разрешить завершающие запятые, задайте для свойства <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> значение `true`. В следующем примере показано, как разрешить оба варианта:

[!code-csharp[](snippets/system-text-json-how-to/csharp/DeserializeCommasComments.cs?name=SnippetDeserialize)]

Ниже приведен пример JSON с комментариями и завершающей запятой:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25, // Fahrenheit 77
  "Summary": "Hot", /* Zharko */
}
```

## <a name="case-insensitive-property-matching"></a>Сопоставление свойств без учета регистра

По умолчанию десериализация выполняет поиск совпадения имен свойств с учетом регистра между кодом JSON и свойствами целевого объекта. Чтобы изменить это поведение, задайте для параметра <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> значение `true`.

[!code-csharp[](snippets/system-text-json-how-to/csharp/DeserializeCaseInsensitive.cs?name=SnippetDeserialize)]

Ниже приведен пример JSON с именами свойств в "верблюжьем" стиле. Его можно десериализовать в следующий тип, который содержит имена свойств в регистре Pascal.

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
}
```

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

## <a name="handle-overflow-json"></a>Обработка переполнения JSON

При десериализации в JSON могут быть получены данные, которые не представлены свойствами целевого типа. Предположим у вас есть следующий целевой тип:

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

А десериализируемым кодом JSON является:

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

При десериализации кода JSON, показанного в указанном типе, свойства `DatesAvailable` и `SummaryWords` никуда не переходят и будут потеряны. Чтобы записать дополнительные данные, такие как эти свойства, примените атрибут [JsonExtensionData](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute) к свойству типа `Dictionary<string,object>` или `Dictionary<string,JsonElement>`:

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithExtensionData)]

При десериализации показанного ранее JSON в этот тип данных дополнительные данные становятся парами "ключ-значение" свойства `ExtensionData`:

|Свойство. |Значение  |Примечания  |
|---------|---------|---------|
| Дата    | 01.08.2019 г. 00:00:00 – 7:00||
| TemperatureCelsius| 0 | Несовпадение с учетом регистра (`temperatureCelsius` в коде JSON), поэтому свойство не задано. |
| Сводка | Горячий ||
| ExtensionData | temperatureCelsius: 25 |Так как регистр не совпадает, это свойство JSON является лишним и становится парой "ключ-значение" в словаре.|
|| DatesAvailable:<br>  01.08.2019 г. 00:00:00 – 7:00<br>02.08.2019 г. 00:00:00 – 7:00 |Дополнительное свойство из кода JSON преобразуется в пару "ключ-значение" с массивом в качестве объекта значения.|
| |SummaryWords:<br>Здорово<br>Ветрено<br>Влажно |Дополнительное свойство из кода JSON преобразуется в пару "ключ-значение" с массивом в качестве объекта значения.|

Когда целевой объект сериализуется, пары "ключ-значение" данных расширения становятся свойствами JSON точно так же, как они были во входящем коде JSON:

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

Обратите внимание, что имя свойства `ExtensionData` не отображается в коде JSON. Такое поведение позволяет JSON выполнить круговой путь без потери дополнительных данных, которые в противном случае не будут десериализованы.

## <a name="ignore-null-when-deserializing"></a>Игнорирование значений NULL при десериализации

По умолчанию, если свойство в JSON имеет значение NULL, соответствующему свойству в целевом объекте присваивается значение NULL. В некоторых сценариях целевое свойство может иметь значение по умолчанию, и вам не будет нужно, чтобы значение NULL переопределяло значение по умолчанию.

Например, следующий код представляет целевой объект:

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithDefault)]

Предположим, что следующий код JSON десериализуется:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": null
}
```

После десериализации свойство `Summary` объекта `WeatherForecastWithDefault` будет иметь значение NULL.

Чтобы изменить это поведение, задайте для параметра <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType> значение `true`, как показано в следующем примере:

[!code-csharp[](snippets/system-text-json-how-to/csharp/DeserializeIgnoreNull.cs?name=SnippetDeserialize)]

При использовании этого параметра свойство `Summary` объекта `WeatherForecastWithDefault` принимает значение по умолчанию No summary после десериализации.

Значения NULL в JSON пропускаются только в том случае, если они являются допустимыми. Значения NULL для типов значений, не допускающих значения NULL, вызывают исключения.

## <a name="utf8jsonreader-utf8jsonwriter-and-jsondocument"></a>Utf8JsonReader, Utf8JsonWriter и JsonDocument

<xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName> — это последовательный модуль чтения текста JSON в кодировке UTF-8 из `ReadOnlySpan<byte>` или `ReadOnlySequence<byte>` с высокой производительностью и низким уровнем распределения. `Utf8JsonReader` — это низкоуровневый тип, с помощью которого можно создавать пользовательские средства синтаксического анализа и десериализаторы. Метод <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> использует `Utf8JsonReader`, как описано выше.

<xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName> — это высокопроизводительный способ записать текст JSON в кодировке UTF-8 из распространенных типов .NET, например `String`, `Int32` и `DateTime`. Модуль записи — это низкоуровневый тип, с помощью которого можно создавать пользовательские сериализаторы. Метод <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> использует `Utf8JsonWriter`, как описано выше.

<xref:System.Text.Json.JsonDocument?displayProperty=fullName> предоставляет возможность создания модели DOM только для чтения с помощью `Utf8JsonReader`. Модель DOM предоставляет произвольный доступ к данным в полезных данных JSON. Доступ к элементам JSON, составляющим полезные данные, можно получить с помощью типа <xref:System.Text.Json.JsonElement>. Тип `JsonElement` предоставляет перечислители массивов и объектов вместе с API-интерфейсами для преобразования текста JSON в стандартные типы .NET. `JsonDocument` предоставляет свойство <xref:System.Text.Json.JsonDocument.RootElement>.

В следующих разделах показано, как использовать эти средства для чтения и записи данных JSON.

## <a name="use-jsondocument-for-access-to-data"></a>Использование класса JsonDocument для доступа к данным

В следующем примере показано, как использовать класс <xref:System.Text.Json.JsonDocument> для произвольного доступа к данным в строке JSON:

[!code-csharp[](snippets/system-text-json-how-to/csharp/JsonDocumentDataAccess.cs?name=SnippetAverageGrades1)]

Предыдущий код:

* Предполагается, что анализируемый код JSON находится в строке `jsonString`.
* Вычисляет среднее значение для объектов в массиве `Students`, имеющих свойство `Grade`.
* Назначает значение по умолчанию 70 для учащихся, у которых нет оценки.
* Подсчитывает число учащихся путем увеличения переменной `count` с каждой итерацией. Альтернативой является вызов <xref:System.Text.Json.JsonElement.GetArrayLength%2A>, как показано в следующем примере:

  [!code-csharp[](snippets/system-text-json-how-to/csharp/JsonDocumentDataAccess.cs?name=SnippetAverageGrades2)]

Ниже приведен пример JSON, обрабатываемый этим кодом:

[!code-json[](snippets/system-text-json-how-to/csharp/GradesPrettyPrint.json)]

## <a name="use-jsondocument-to-write-json"></a>Использование класса JsonDocument для записи кода JSON

В следующем примере показано, как записать JSON код из <xref:System.Text.Json.JsonDocument>.

[!code-csharp[](snippets/system-text-json-how-to/csharp/JsonDocumentWriteJson.cs?name=SnippetSerialize)]

Предыдущий код:

* Считывает JSON-файл, загружает данные в `JsonDocument` и записывает форматированный (структурированный) код JSON в файл.
* Использует <xref:System.Text.Json.JsonDocumentOptions>, чтобы указать, что комментарии во входных данных JSON разрешены, но пропускаются.
* По завершении для модуля записи вызывается <xref:System.Text.Json.Utf8JsonWriter.Flush%2A>. В качестве альтернативы можно разрешить автоматическую запись в модуле записи при его удалении.

Ниже приведен пример входных данных JSON для обработки в примере кода:

[!code-json[](snippets/system-text-json-how-to/csharp/Grades.json)]

В результате получаются следующие структурированные выходные данные JSON:

[!code-json[](snippets/system-text-json-how-to/csharp/GradesPrettyPrint.json)]

## <a name="use-utf8jsonwriter"></a>Использование Utf8JsonWriter

В следующем примере показано, как использовать класс <xref:System.Text.Json.Utf8JsonWriter>.

[!code-csharp[](snippets/system-text-json-how-to/csharp/Utf8WriterToStream.cs?name=SnippetSerialize)]

## <a name="use-utf8jsonreader"></a>Использование Utf8JsonReader

В следующем примере показано, как использовать класс <xref:System.Text.Json.Utf8JsonReader>.

[!code-csharp[](snippets/system-text-json-how-to/csharp/Utf8ReaderFromBytes.cs?name=SnippetDeserialize)]

В приведенном выше коде предполагается, что переменной `jsonUtf8` является массив байтов, который содержит допустимые данные JSON в кодировке UTF-8.

### <a name="filter-data-using-utf8jsonreader"></a>Фильтрация данных с помощью Utf8JsonReader

В следующем примере показано, как синхронно выполнить чтение файла и поиск значения:

[!code-csharp[](snippets/system-text-json-how-to/csharp/Utf8ReaderFromFile.cs)]

Предыдущий код:

* Предполагается, что JSON содержит массив объектов и каждый объект может содержать свойство name строкового типа.
* Подсчитывает объекты и значения свойств name, заканчивающиеся на University.
* Предполагается, что файл кодируется как UTF-16 и перекодируется в UTF-8. Файл, закодированный как UTF-8, можно прочитать непосредственно в `ReadOnlySpan<byte>` с помощью следующего кода:

  ```csharp
  ReadOnlySpan<byte> jsonReadOnlySpan = File.ReadAllBytes(fileName);
  ```

  Если файл содержит метку порядка байтов (BOM) UTF-8, удалите ее перед передачей байтов в `Utf8JsonReader`, так как средство чтения ждет текст. В противном случае метка порядка байтов считается недопустимым кодом JSON, и средство чтения создает исключение.

Ниже приведен пример JSON, который можно считать с помощью приведенного выше кода. Полученным итоговым сообщением будет 2 out of 4 have names that end with University (2 из 4 имеют имена, заканчивающиеся на University):

[!code-json[](snippets/system-text-json-how-to/csharp/Universities.json)]

### <a name="read-from-a-stream-using-utf8jsonreader"></a>Чтение из потока данных с помощью Utf8JsonReader

При чтении большого файла (размером гигабайт и более) вы, скорее всего, предпочтете не загружать весь файл в память сразу. В таких ситуациях можно использовать <xref:System.IO.FileStream>.

При использовании `Utf8JsonReader` для чтения из потока данных действуют следующие правила:

* Буфер, который накапливает часть данных в формате JSON, должен быть не меньше самого крупного из возможных маркеров JSON, чтобы средство чтения могло продвигаться вперед.
* Размер буфера должен быть не меньше самой большой последовательности пробелов в JSON.
* Средство чтения не запоминает прочитанные данные, пока не дойдет до следующего свойства <xref:System.Text.Json.Utf8JsonReader.TokenType%2A> в структуре JSON. Таким образом, если в буфере еще остались байты, их нужно снова передать в средство чтения. Для определения количества оставшихся байтов можно использовать <xref:System.Text.Json.Utf8JsonReader.BytesConsumed%2A>.

В примере кода ниже показано, как выполнять чтение из потока. Этот пример демонстрирует <xref:System.IO.MemoryStream>. Аналогичный код будет работать и с <xref:System.IO.FileStream>, за исключением случаев, когда в начале `FileStream` содержится метка порядка байтов UTF-8. В этом случае необходимо удалить эти три байта из буфера, прежде чем передавать оставшиеся байты в `Utf8JsonReader`. В противном случае средство чтения создаст исключение, поскольку метка порядка байтов не считается допустимой частью JSON.

Пример кода начинает работу с буфером в 4 КБ и удваивает размер буфера каждый раз, когда тот оказывается недостаточно велик для размещения полного маркера JSON, который потребуется средству чтения для дальнейшего перемещения по структуре данных JSON. Представленный в этом примере фрагмент JSON приводит к увеличению размера буфера только в том случае, если задан очень маленький начальный размер буфера, например 10 байт. Если указать для буфера начальное значение 10, то инструкции `Console.WriteLine` продемонстрируют причину и последствия увеличения размера буфера. При начальном размере буфера 4 КБ весь пример JSON целиком отображается в каждой `Console.WriteLine`, и размер буфера увеличивать не нужно.

[!code-csharp[](snippets/system-text-json-how-to/csharp/Utf8ReaderPartialRead.cs)]

В примере выше ограничение на увеличение размера буфера не установлено. Если размер маркера будет слишком большой, такой код может возвратить ошибку с исключением <xref:System.OutOfMemoryException>. Такое может произойти, если в JSON есть маркер размером около 1 ГБ, поскольку удвоение размера 1 ГБ приводит к переполнению буфера `int32`.

## <a name="additional-resources"></a>Дополнительные ресурсы

* [Общие сведения о System.Text.Json](system-text-json-overview.md)
* [Как написать пользовательские преобразователи для сериализации JSON (маршалинг) в .NET](system-text-json-converters-how-to.md)
* [Как выполнить миграцию из Newtonsoft.Json](system-text-json-migrate-from-newtonsoft-how-to.md)
* [Поддержка DateTime и DateTimeOffset в System.Text.Json](../datetime/system-text-json-support.md)
* [Справочник по API System.Text.Json](xref:System.Text.Json)
<!-- * [System.Text.Json roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)-->
