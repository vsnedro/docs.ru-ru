---
title: Как использовать неизменяемые типы и частные методы доступа с помощью System.Text.Json
description: Узнайте, как в .NET использовать неизменяемые типы и частные методы доступа при сериализации в JSON и десериализации из JSON.
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
ms.openlocfilehash: ff8ecec0d70c877b7cbbd0297b85f0d9578ab828
ms.sourcegitcommit: 81f1bba2c97a67b5ca76bcc57b37333ffca60c7b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "97008829"
---
# <a name="how-to-use-immutable-types-and-non-public-accessors-with-no-locsystemtextjson"></a>Как использовать неизменяемые типы и частные методы доступа с помощью System.Text.Json

Из этой статьи вы узнаете, как использовать неизменяемые типы, например записи, с помощью пространства имен `System.Text.Json`.

## <a name="immutable-types-and-records"></a>Неизменяемые типы и записи

::: zone pivot="dotnet-5-0"
`System.Text.Json` может использовать параметризованный конструктор, позволяющий десериализовать неизменяемый класс или структуру. Если для класса существует только параметризованный конструктор, тогда будет использован этот конструктор. Для структуры или класса с несколькими конструкторами укажите необходимый, применив атрибут [[JsonConstructor]](xref:System.Text.Json.Serialization.JsonConstructorAttribute.%23ctor%2A). Если атрибут не используется, тогда всегда применяется общедоступный конструктор без параметров. Атрибут используется только с общедоступными конструкторами. В следующем примере используется атрибут `[JsonConstructor]`.

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/ImmutableTypes.cs" highlight="13":::

Записи в C# 9 поддерживаются, как показано в примере:

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/Records.cs":::

Подробнее о неизменяемых типах, чьи методы задания не являются общедоступными, см. в разделе о [методах доступа к свойствам, не являющимся общедоступными](#non-public-property-accessors).
::: zone-end

::: zone pivot="dotnet-core-3-1"
`JsonConstructorAttribute` и поддержка записи C# 9 недоступны в .NET Core 3.1.
::: zone-end

## <a name="non-public-property-accessors"></a>Методы доступа к свойствам, не являющимся общедоступными

::: zone pivot="dotnet-5-0"
Для включения метода доступа к свойству, не являющемуся общедоступным, используйте атрибут [[JsonInclude]](xref:System.Text.Json.Serialization.JsonIncludeAttribute), как показано ниже:

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/NonPublicAccessors.cs" highlight="12,15":::
::: zone-end

::: zone pivot="dotnet-core-3-1"
Методы доступа к свойству, не являющемуся общедоступным, не поддерживаются в .NET Core 3.1. Дополнительные сведения см. в статье [о переходе с Newtonsoft.Json](system-text-json-migrate-from-newtonsoft-how-to.md#non-public-property-setters-and-getters).
::: zone-end

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
* [Полиморфная сериализация](system-text-json-polymorphism.md)
* [Миграция из Newtonsoft.Json в System.Text.Json](system-text-json-migrate-from-newtonsoft-how-to.md)
* [Настройка кодировки символов](system-text-json-character-encoding.md)
* [Написание пользовательских сериализаторов и десериализаторов](write-custom-serializer-deserializer.md)
* [Написание пользовательских преобразователей для сериализации JSON](system-text-json-converters-how-to.md)
* [Поддержка DateTime и DateTimeOffset](../datetime/system-text-json-support.md)
* [Справочник по API System.Text.Json](xref:System.Text.Json)
* [Справочник по API System.Text.Json.Serialization](xref:System.Text.Json.Serialization)
