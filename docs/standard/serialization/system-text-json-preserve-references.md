---
title: Как сохранять ссылки с помощью System.Text.Json
description: Узнайте, как в .NET сохранять ссылки и обрабатывать циклические ссылки при сериализации в JSON и десериализации из JSON.
ms.date: 12/09/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
zone_pivot_groups: dotnet-version
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: d358c953c0979ca097c080fcd750d5ef95b07de0
ms.sourcegitcommit: 81f1bba2c97a67b5ca76bcc57b37333ffca60c7b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "97008738"
---
# <a name="how-to-preserve-references-and-handle-circular-references-with-no-locsystemtextjson"></a>Сохранение ссылок и обработка циклических ссылок с помощью System.Text.Json

::: zone pivot="dotnet-5-0"

Для сохранения ссылок и обработки циклических ссылок задайте для свойства <xref:System.Text.Json.JsonSerializerOptions.ReferenceHandler%2A> значение <xref:System.Text.Json.Serialization.ReferenceHandler.Preserve%2A>. Этот параметр приводит к следующему поведению:

* При сериализации:

  При написании сложных типов сериализатор также записывает свойства метаданных (`$id`, `$values`, а также `$ref`).

* При десериализации:

  Ожидаются метаданные (не обязательно), и десериализатор пытается их распознать.

В следующем коде показано использование параметра `Preserve`.

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/PreserveReferences.cs" highlight="34":::

Эту функцию нельзя использовать для сохранения типов значений или неизменяемых типов. При десериализации экземпляр неизменяемого типа создается после считывания всех полезных данных. Поэтому для того же экземпляра невозможно будет выполнить десериализацию, если в полезных данных JSON появляется ссылка на него.

Для типов значений, неизменяемых типов и массивов ссылочные метаданные не сериализуются. Если при десериализации было найдено `$ref` или `$id`, создается исключение. Однако типы значений игнорируют `$id` (и `$values` для коллекций), чтобы позволить десериализацию полезных данных, сериализованных с помощью Newtonsoft.Json.  Newtonsoft.Json выполняет сериализацию метаданных для таких типов.

Для определения равенства объектов System.Text.Json использует свойство <xref:System.Collections.Generic.ReferenceEqualityComparer.Instance%2A?displayProperty=nameWithType>, которое при сравнении двух экземпляров объекта использует эквивалентность ссылок (<xref:System.Object.ReferenceEquals(System.Object,System.Object)?displayProperty=nameWithType>), а не эквивалентность значений (<xref:System.Object.Equals(System.Object)?displayProperty=nameWithType>).

Больше о сериализации и десериализации ссылок см. в статье <xref:System.Text.Json.Serialization.ReferenceHandler.Preserve%2A?displayProperty=nameWithType>.

Класс <xref:System.Text.Json.Serialization.ReferenceResolver> определяет поведение сохранения ссылок при сериализации и десериализации. Создайте производный класс, чтобы указать настраиваемое поведение. Пример см. в статье [GuidReferenceResolver](https://github.com/dotnet/docs/blob/9d5e88edbd7f12be463775ffebbf07ac8415fe18/docs/standard/serialization/snippets/system-text-json-how-to-5-0/csharp/GuidReferenceResolverExample.cs).

::: zone-end

::: zone pivot="dotnet-core-3-1"
System.Text.Json в .NET Core 3.1 поддерживает сериализацию только по значению и вызывает исключение для циклических ссылок.
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
* [Неизменяемые типы и непубличные методы доступа](system-text-json-immutability.md)
* [Полиморфная сериализация](system-text-json-polymorphism.md)
* [Миграция из Newtonsoft.Json в System.Text.Json](system-text-json-migrate-from-newtonsoft-how-to.md)
* [Настройка кодировки символов](system-text-json-character-encoding.md)
* [Написание пользовательских сериализаторов и десериализаторов](write-custom-serializer-deserializer.md)
* [Написание пользовательских преобразователей для сериализации JSON](system-text-json-converters-how-to.md)
* [Поддержка DateTime и DateTimeOffset](../datetime/system-text-json-support.md)
* [Справочник по API System.Text.Json](xref:System.Text.Json)
* [Справочник по API System.Text.Json.Serialization](xref:System.Text.Json.Serialization)
