---
title: Как настроить имена и значения свойств с помощью System.Text.Json
description: Узнайте, как настроить имена и значения свойств при сериализации с использованием System.Text.Json в .NET.
ms.date: 11/30/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 4b88509313e719ea993e00d889bc6145f4976a2d
ms.sourcegitcommit: 81f1bba2c97a67b5ca76bcc57b37333ffca60c7b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "97008907"
---
# <a name="how-to-customize-property-names-and-values-with-no-locsystemtextjson"></a>Как настроить имена и значения свойств с помощью System.Text.Json

По умолчанию имена и ключи словарей не изменяются в выходных данных JSON, включая регистр. Значения перечисления представлены в виде чисел. В этой статье вы узнаете, как выполнять следующие задачи.

> [!NOTE]
> [Стандартный параметр веб-приложения](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions) представлен в "верблюжем" стиле.

* [Настраивать отдельные имена свойств](#customize-individual-property-names).
* [Преобразовывать все имена свойств в неоднородный регистр](#use-camel-case-for-all-json-property-names).
* [Реализовывать политики именования пользовательских свойств](#use-a-custom-json-property-naming-policy).
* [Преобразовывать ключи словаря в "верблюжий" стиль](#camel-case-dictionary-keys).
* [Преобразовывать перечисления в строки и "верблюжий" стиль](#enums-as-strings).

Для других сценариев, требующих специальной обработки имен и значений свойств JSON, можно [реализовать пользовательские преобразователи](system-text-json-converters-how-to.md).

## <a name="customize-individual-property-names"></a>Настройка отдельных имен свойств

Чтобы задать имена отдельных свойств, используйте атрибут [[JsonPropertyName]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute).

Ниже приведен пример типа для сериализации и полученный код JSON:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithPropertyNameAttribute":::

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

## <a name="use-camel-case-for-all-json-property-names"></a>Использование "верблюжьего" стиля для всех имен свойств JSON

Чтобы использовать "верблюжий" стиль для всех имен свойств JSON, задайте для параметра <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> значение `JsonNamingPolicy.CamelCase`, как показано в следующем примере:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundTripCamelCasePropertyNames.cs" id="Serialize":::

Ниже приведен пример класса для сериализации и вывода JSON.

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithPropertyNameAttribute":::

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

## <a name="use-a-custom-json-property-naming-policy"></a>Использование настраиваемой политики именования свойств JSON

Чтобы использовать настраиваемую политику именования свойств JSON, создайте класс, производный от <xref:System.Text.Json.JsonNamingPolicy>, и переопределите метод <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A>, как показано в следующем примере:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/UpperCaseNamingPolicy.cs":::

Затем задайте для свойства <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> экземпляр класса политики именования:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripPropertyNamingPolicy.cs" id="Serialize":::

Ниже приведен пример класса для сериализации и вывода JSON.

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithPropertyNameAttribute":::

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

## <a name="camel-case-dictionary-keys"></a>Ключи словаря в "верблюжьем" стиле.

Если свойство сериализуемого объекта имеет тип `Dictionary<string,TValue>`, ключи `string` можно преобразовать в "верблюжий" стиль. Для этого задайте для параметра <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy> значение `JsonNamingPolicy.CamelCase`, как показано в следующем примере:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializeCamelCaseDictionaryKeys.cs" id="Serialize":::

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

## <a name="enums-as-strings"></a>Перечисление в виде строк

По умолчанию перечисления сериализуются как числа. Чтобы сериализовать имена перечислений как строки, используйте <xref:System.Text.Json.Serialization.JsonStringEnumConverter>.

Например, предположим, что необходимо сериализовать следующий класс, имеющий перечисление:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithEnum":::

Если параметр "Сводка" имеет значение `Hot`, то по умолчанию сериализованный код JSON имеет числовое значение 3:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": 3
}
```

Следующий пример кода сериализует имена перечислений вместо числовых значений и преобразует имена в "верблюжий" стиль:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripEnumAsString.cs" id="Serialize":::

Итоговый код JSON выглядит следующим образом:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "hot"
}
```

Имена строк перечисления можно также десериализовать, как показано в следующем примере:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripEnumAsString.cs" id="Deserialize":::

## <a name="see-also"></a>См. также раздел

* [Общие сведения о System.Text.Json](system-text-json-overview.md)
* [Практическое руководство. Сериализация и десериализация JSON](system-text-json-how-to.md)
* [Создание экземпляров JsonSerializerOptions](system-text-json-configure-options.md)
* [Сопоставление без учета регистра](system-text-json-character-casing.md)
* [Игнорирование свойств](system-text-json-ignore-properties.md)
* [Применение недействительного кода JSON](system-text-json-invalid-json.md)
* [Обработка переполнения JSON](system-text-json-handle-overflow.md)
* [Сохранение ссылок](system-text-json-preserve-references.md)
* [Неизменяемые типы и непубличные методы доступа](system-text-json-immutability.md)
* [Полиморфная сериализация](system-text-json-polymorphism.md)
* [Миграция из Newtonsoft.Json в System.Text.Json](system-text-json-migrate-from-newtonsoft-how-to.md)
* [Настройка кодировки символов](system-text-json-character-encoding.md)
* [Написание пользовательских сериализаторов и десериализаторов](write-custom-serializer-deserializer.md)
* [Написание пользовательских преобразователей для сериализации JSON](system-text-json-converters-how-to.md)
* [Поддержка DateTime и DateTimeOffset](../datetime/system-text-json-support.md)
* [Справочник по API System.Text.Json](xref:System.Text.Json)
* [Справочник по API System.Text.Json.Serialization](xref:System.Text.Json.Serialization)
