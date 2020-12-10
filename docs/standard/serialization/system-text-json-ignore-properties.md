---
title: Игнорирование свойств с помощью System.Text.Json
description: Узнайте, как игнорировать свойства при сериализации с помощью System.Text.Json в .NET.
ms.date: 11/30/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
zone_pivot_groups: dotnet-version
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: ed7ef8509d6660bbbbaf194a87aa9d4815143507
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/01/2020
ms.locfileid: "96439822"
---
# <a name="how-to-ignore-properties-with-no-locsystemtextjson"></a>Игнорирование свойств с помощью System.Text.Json

По умолчанию при сериализации объектов C# в JSON сериализуются все открытые свойства. Если вы не хотите, чтобы некоторые из них отображались в итоговом коде JSON, у вас есть несколько вариантов. Из этой статьи вы узнаете, как игнорировать свойства в зависимости от различных критериев.

::: zone pivot="dotnet-5-0"

* [отдельных свойств](#ignore-individual-properties);
* [всех свойств только для чтения](#ignore-all-read-only-properties);
* [всех свойств со значением NULL](#ignore-all-null-value-properties).
* [всех свойств значений по умолчанию](#ignore-all-default-value-properties);
::: zone-end

::: zone pivot="dotnet-core-3-1"

* [отдельных свойств](#ignore-individual-properties);
* [всех свойств только для чтения](#ignore-all-read-only-properties);
* [всех свойств со значением NULL](#ignore-all-null-value-properties).
::: zone-end

## <a name="ignore-individual-properties"></a>Игнорирование индивидуальных свойств

Чтобы игнорировать отдельные свойства, используйте атрибут [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute).

Ниже приведен пример типа для сериализации и вывода JSON.

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithIgnoreAttribute":::

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
}
```

::: zone pivot="dotnet-5-0"
Можно указать условное исключение, задав свойство `Condition` атрибута [ [JsonIgnore] ](xref:System.Text.Json.Serialization.JsonIgnoreAttribute). Перечисление <xref:System.Text.Json.Serialization.JsonIgnoreCondition> предоставляет следующие возможности:

* `Always` — свойство всегда игнорируется. Если свойство `Condition` не указано, предполагается этот параметр.
* `Never` — свойство всегда сериализуется и десериализуется, независимо от глобальных параметров `DefaultIgnoreCondition`, `IgnoreReadOnlyProperties` и `IgnoreReadOnlyFields`.
* `WhenWritingDefault` — свойство не учитывается при сериализации, если оно является ссылочным типом `null`, типом значения `default`, допускающим NULL, или типом значения `null`.
* `WhenWritingNull` — свойство не учитывается при сериализации, если оно является ссылочным типом `null` или типом значения `null`, допускающим значение NULL.

В следующем примере показано использование свойства `Condition` атрибута [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute):

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/JsonIgnoreAttributeExample.cs" highlight="10,13,16":::
::: zone-end

## <a name="ignore-all-read-only-properties"></a>Игнорирование всех свойств "только для чтения"

Свойство доступно только для чтения, если оно содержит открытый метод получения, но не является общим методом задания. Чтобы игнорировать при сериализации все свойства "только для чтения", задайте для параметра <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> значение `true`, как показано ниже:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializeExcludeReadOnlyProperties.cs" id="Serialize":::

Ниже приведен пример типа для сериализации и вывода JSON.

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithROProperty":::

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
}
```

Этот параметр применяется только к сериализации. Во время десериализации свойства, доступные только для чтения, по умолчанию игнорируются.

::: zone pivot="dotnet-5-0"
Этот параметр применяется только к свойствам. Чтобы пропустить при [сериализации полей](system-text-json-how-to.md#include-fields) поля, предназначенные только для чтения, используйте глобальный параметр <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyFields%2A?displayProperty=nameWithType>.
::: zone-end

## <a name="ignore-all-null-value-properties"></a>Игнорировать все свойства со значением NULL

::: zone pivot="dotnet-5-0"
Чтобы игнорировать все свойства со значением NULL, задайте для параметра <xref:System.Text.Json.JsonSerializerOptions.DefaultIgnoreCondition> значение <xref:System.Text.Json.Serialization.JsonIgnoreCondition.WhenWritingNull>, как показано в следующем примере:

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/IgnoreNullOnSerialize.cs" highlight="28":::

::: zone-end

::: zone pivot="dotnet-core-3-1"
Чтобы игнорировать при сериализации все свойства со значением NULL, задайте для параметра <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> значение `true`, как показано в следующем примере:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializeExcludeNullValueProperties.cs" id="Serialize":::

Ниже приведен пример объекта для сериализации и вывода JSON.

| Свойство.             | Значение                         |
|----------------------|-------------------------------|
| `Date`               | `8/1/2019 12:00:00 AM -07:00` |
| `TemperatureCelsius` | `25`                          |
| `Summary`            | `null`                        |

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25
}
```

::: zone-end

## <a name="ignore-all-default-value-properties"></a>Игнорирование всех свойств со значениями по умолчанию

::: zone pivot="dotnet-5-0"
Чтобы предотвратить сериализацию значений по умолчанию в свойствах типа значения, присвойте свойству <xref:System.Text.Json.JsonSerializerOptions.DefaultIgnoreCondition> значение <xref:System.Text.Json.Serialization.JsonIgnoreCondition.WhenWritingDefault>, как показано ниже:

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/IgnoreValueDefaultOnSerialize.cs" highlight="28":::
::: zone-end

Параметр <xref:System.Text.Json.Serialization.JsonIgnoreCondition.WhenWritingDefault> также предотвращает сериализацию свойств ссылочного типа со значением NULL и типа значения, допускающим значение NULL.

::: zone pivot="dotnet-core-3-1"
Для .NET Core 3.1. не существует встроенного способа предотвращения сериализации свойств с типом значения "по умолчанию" в `System.Text.Json`.
::: zone-end

## <a name="see-also"></a>См. также раздел

* [Общие сведения о System.Text.Json](system-text-json-overview.md)
* [Создание экземпляров JsonSerializerOptions](system-text-json-configure-options.md)
* [Сопоставление без учета регистра](system-text-json-character-casing.md)
* [Настройка имен и значений свойств](system-text-json-customize-properties.md)
* [Применение недействительного кода JSON](system-text-json-invalid-json.md)
* [Обработка переполнения JSON](system-text-json-handle-overflow.md)
* [Сохранение циклических ссылок](system-text-json-preserve-references.md)
* [Неизменяемые типы и непубличные методы доступа](system-text-json-immutability.md)
* [Полиморфная сериализация](system-text-json-polymorphism.md)
* [Справочник по API System.Text.Json](xref:System.Text.Json)
