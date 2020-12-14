---
title: Как сериализовать свойства производных классов с помощью System.Text.Json
description: Узнайте, как в .NET выполнить сериализацию полиморфных объектов при сериализации в JSON и десериализации из JSON.
ms.date: 11/30/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: c0bc16c60d3bf96a380bc29bbf7f4765f752b320
ms.sourcegitcommit: 81f1bba2c97a67b5ca76bcc57b37333ffca60c7b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "97008751"
---
# <a name="how-to-serialize-properties-of-derived-classes-with-no-locsystemtextjson"></a>Как сериализовать свойства производных классов с помощью System.Text.Json

Из этой статьи вы узнаете, как сериализовать свойства производных классов с помощью пространства имен `System.Text.Json`.

## <a name="serialize-properties-of-derived-classes"></a>Сериализация свойств производных классов

Сериализация иерархии полиморфных типов _не_ поддерживается. Например, если свойство определено как интерфейс или абстрактный класс, сериализуются только свойства, определенные в интерфейсе или абстрактном классе, даже если тип среды выполнения имеет дополнительные свойства. В этом разделе описаны исключения из этого поведения.

Например, предположим, что у вас есть класс `WeatherForecast` и производный класс `WeatherForecastDerived`:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WF":::

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFDerived":::

Предположим также, что аргумент типа метода `Serialize` во время компиляции `WeatherForecast`:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs" id="SerializeDefault":::

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

  :::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs" id="SerializeGetType":::

* Объявите объект, который должен быть сериализован как `object`.

  :::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs" id="SerializeObject":::

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

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithPrevious":::

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithPreviousAsObject":::

Если свойство `PreviousForecast` содержит экземпляр `WeatherForecastDerived`:

* Выходные данные JSON из сериализации `WeatherForecastWithPrevious` **не содержат** `WindSpeed`.
* Выходные данные JSON из сериализации `WeatherForecastWithPreviousAsObject` **включают в себя** `WindSpeed`.

Чтобы сериализовать `WeatherForecastWithPreviousAsObject`, не нужно вызывать `Serialize<object>` или `GetType`, потому что корневой объект не является объектом, который может иметь производный тип. В следующем примере кода не вызывается `Serialize<object>` или `GetType`:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs" id="SerializeSecondLevel":::

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

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/IForecast.cs":::

Когда вы сериализуете экземпляр `Forecasts`, только `Tuesday` отображает свойство `WindSpeed`, так как `Tuesday` определяется как `object`:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs" id="SerializeInterface":::

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

## <a name="see-also"></a>См. также раздел

* [Общие сведения о System.Text.Json](system-text-json-overview.md)
* [Практическое руководство. Сериализация и десериализация JSON](system-text-json-how-to.md)
* [Создание экземпляров JsonSerializerOptions](system-text-json-configure-options.md)
* [Сопоставление без учета регистра](system-text-json-character-casing.md)
* [Настройка имен и значений свойств](system-text-json-customize-properties.md)
* [Игнорирование свойств](system-text-json-ignore-properties.md)
* [Применение недействительного кода JSON](system-text-json-invalid-json.md)
* [Обработка переполнения JSON](system-text-json-handle-overflow.md)
* [Сохранение ссылок](system-text-json-preserve-references.md)
* [Неизменяемые типы и непубличные методы доступа](system-text-json-immutability.md)
* [Миграция из Newtonsoft.Json в System.Text.Json](system-text-json-migrate-from-newtonsoft-how-to.md)
* [Настройка кодировки символов](system-text-json-character-encoding.md)
* [Написание пользовательских сериализаторов и десериализаторов](write-custom-serializer-deserializer.md)
* [Написание пользовательских преобразователей для сериализации JSON](system-text-json-converters-how-to.md)
* [Поддержка DateTime и DateTimeOffset](../datetime/system-text-json-support.md)
* [Справочник по API System.Text.Json](xref:System.Text.Json)
* [Справочник по API System.Text.Json.Serialization](xref:System.Text.Json.Serialization)
