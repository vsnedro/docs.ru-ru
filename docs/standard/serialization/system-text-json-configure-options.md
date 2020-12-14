---
title: Создание экземпляров JsonSerializerOptions с помощью System.Text.Json
description: Сведения о том, как избежать проблем с производительностью и использовать доступные конструкторы для экземпляров JsonSerializerOptions.
ms.date: 12/02/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
zone_pivot_groups: dotnet-version
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 5f32e1369e58dd9550f28abc822f187dee46c022
ms.sourcegitcommit: 81f1bba2c97a67b5ca76bcc57b37333ffca60c7b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "97009837"
---
# <a name="how-to-instantiate-jsonserializeroptions-instances-with-no-locsystemtextjson"></a>Создание экземпляров JsonSerializerOptions с помощью System.Text.Json

В этой статье объясняется, как избежать проблем с производительностью при использовании <xref:System.Text.Json.JsonSerializerOptions>. В ней также показано, как использовать доступные параметризованные конструкторы.

## <a name="reuse-jsonserializeroptions-instances"></a>Повторное использование экземпляров JsonSerializerOptions

При многократном использовании `JsonSerializerOptions` с одинаковыми параметрами не создавайте новый экземпляр `JsonSerializerOptions` при каждом использовании. Повторно используйте один и тот же экземпляр для каждого вызова. Это руководство относится к коду для настраиваемых преобразователей, а также при вызове <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> или <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>.

В следующем примере кода демонстрируется снижение производительности при использовании новых экземпляров параметров.

:::code language="csharp" source="snippets/system-text-json-configure-options/csharp/ReuseOptionsInstances.cs":::

Предыдущий код сериализует небольшой объект 100 000 раз с помощью одного и того же экземпляра параметров. Затем он сериализует тот же объект такое же количество раз и каждый раз создает новый экземпляр параметров. Типичная разница во времени выполнения — 190 и 40 140 миллисекунд. Разница станет еще больше, если увеличить число итераций.

Сериализатор выполняет этап прогрева во время первой сериализации каждого типа в графе объектов при передаче ему нового экземпляра параметров. Этот прогрев включает создание кэша метаданных, необходимых для сериализации. Метаданные содержат делегаты для методов получения свойств, методов задания свойств, аргументов конструктора, заданных атрибутов и т. д. Этот кэш метаданных хранится в экземпляре параметров. Тот же процесс прогрева и создания кэша относится к десериализации.

Размер кэша метаданных в экземпляре `JsonSerializerOptions` зависит от числа сериализуемых типов. Если в сериализатор передается большое число типов, например, динамически создаваемые типы, то размер кэша будет продолжать расти и может привести к появлению `OutOfMemoryException`.

## <a name="copy-jsonserializeroptions"></a>Копирование JsonSerializerOptions

::: zone pivot="dotnet-5-0"
Существует [конструктор JsonSerializerOptions](xref:System.Text.Json.JsonSerializerOptions.%23ctor(System.Text.Json.JsonSerializerOptions)), который позволяет создавать новый экземпляр с параметрами, использованными для существующего экземпляра:

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/CopyOptions.cs" highlight="29":::
::: zone-end

::: zone pivot="dotnet-core-3-1"
Конструктор `JsonSerializerOptions`, который принимает существующий экземпляр, недоступен в .NET Core 3.1.
::: zone-end

## <a name="web-defaults-for-jsonserializeroptions"></a>Стандартные параметры веб-приложений для JsonSerializerOptions

::: zone pivot="dotnet-5-0"
Ниже приведены параметры с различными значениями по умолчанию для веб-приложений:

* <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive%2A> = `true`
* <xref:System.Text.Json.JsonNamingPolicy> = <xref:System.Text.Json.JsonNamingPolicy.CamelCase>
* <xref:System.Text.Json.JsonSerializerOptions.NumberHandling%2A> = <xref:System.Text.Json.Serialization.JsonNumberHandling.AllowReadingFromString>

Существует [конструктор JsonSerializerOptions](xref:System.Text.Json.JsonSerializerOptions.%23ctor(System.Text.Json.JsonSerializerDefaults)?view=net-5.0&preserve-view=true), который позволяет создавать новый экземпляр со стандартными параметрами, которые ASP.NET Core использует для веб-приложений, как показано ниже:

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/OptionsDefaults.cs" highlight="24":::
::: zone-end

::: zone pivot="dotnet-core-3-1"
Ниже приведены параметры с различными значениями по умолчанию для веб-приложений:

* <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive%2A> = `true`
* <xref:System.Text.Json.JsonNamingPolicy> = <xref:System.Text.Json.JsonNamingPolicy.CamelCase>

Конструктор `JsonSerializerOptions`, указывающий набор значений по умолчанию, недоступен в .NET Core 3.1.
::: zone-end

## <a name="see-also"></a>См. также раздел

* [Общие сведения о System.Text.Json](system-text-json-overview.md)
* [Практическое руководство. Сериализация и десериализация JSON](system-text-json-how-to.md)
* [Сопоставление без учета регистра](system-text-json-character-casing.md)
* [Настройка имен и значений свойств](system-text-json-customize-properties.md)
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
