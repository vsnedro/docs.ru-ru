---
title: Разрешение некоторых недопустимых объектов JSON с помощью System.Text.Json
description: Узнайте, как в .NET разрешить комментарии, конечные запятые и числа в кавычках при сериализации в JSON и десериализации из JSON.
ms.date: 12/03/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
zone_pivot_groups: dotnet-version
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 2559b081010fb0a2fa208b121cb095efdeb8da2e
ms.sourcegitcommit: 81f1bba2c97a67b5ca76bcc57b37333ffca60c7b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "97009814"
---
# <a name="how-to-allow-some-kinds-of-invalid-json-with-no-locsystemtextjson"></a>Разрешение некоторых недопустимых объектов JSON с помощью System.Text.Json

Из этой статьи вы узнаете, как разрешить комментарии, конечные запятые и числа в кавычках при сериализации в JSON и как записывать числа в виде строк.

## <a name="allow-comments-and-trailing-commas"></a>Разрешение комментариев и завершающих запятых

По умолчанию комментарии и завершающие запятые в JSON не допускаются. Чтобы разрешить комментарии в JSON, задайте для свойства <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> значение `JsonCommentHandling.Skip`.
Чтобы разрешить завершающие запятые, задайте для свойства <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> значение `true`. В следующем примере показано, как разрешить оба варианта:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/DeserializeCommasComments.cs" id="Deserialize":::

Ниже приведен пример JSON с комментариями и завершающей запятой:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25, // Fahrenheit 77
  "Summary": "Hot", /* Zharko */
  // Comments on
  /* separate lines */
}
```

## <a name="allow-or-write-numbers-in-quotes"></a>Разрешение или запись чисел в кавычках

::: zone pivot="dotnet-5-0"

Некоторые сериализаторы кодируют числа в виде строк JSON (заключены в кавычки).

Пример.

```json
{
    "DegreesCelsius": "23"
}
```

Вместо:

```json
{
    "DegreesCelsius": 23
}
```

Для сериализации или принятия чисел в кавычках во всех входных данных графа объектов задайте свойство <xref:System.Text.Json.JsonSerializerOptions.NumberHandling%2A?displayProperty=nameWithType>, как показано ниже:

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/QuotedNumbers.cs" highlight="27-29":::

Если вы используете `System.Text.Json` косвенно через ASP.NET Core, тогда заключенные в кавычки числа будут разрешены при десериализации, поскольку ASP.NET Core определяет [стандартные параметры веб-приложений](xref:System.Text.Json.JsonSerializerDefaults.Web).

Чтобы разрешить или записать заключенные в кавычки числа для конкретных свойств, полей или типов, используйте атрибут [[JsonNumberHandling]](xref:System.Text.Json.Serialization.JsonNumberHandlingAttribute).
::: zone-end

::: zone pivot="dotnet-core-3-1"
`System.Text.Json` в .NET Core 3.1 не поддерживает сериализацию или десериализацию чисел, заключенных в кавычки. Дополнительные сведения см. в разделе [Разрешение или запись чисел в кавычках](system-text-json-migrate-from-newtonsoft-how-to.md#allow-or-write-numbers-in-quotes).
::: zone-end

## <a name="see-also"></a>См. также раздел

* [Общие сведения о System.Text.Json](system-text-json-overview.md)
* [Практическое руководство. Сериализация и десериализация JSON](system-text-json-how-to.md)
* [Создание экземпляров JsonSerializerOptions](system-text-json-configure-options.md)
* [Сопоставление без учета регистра](system-text-json-character-casing.md)
* [Настройка имен и значений свойств](system-text-json-customize-properties.md)
* [Игнорирование свойств](system-text-json-ignore-properties.md)
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
