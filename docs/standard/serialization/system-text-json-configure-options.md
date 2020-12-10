---
title: Создание экземпляров JsonSerializerOptions с помощью System.Text.Json
description: Узнайте, как создавать экземпляры JsonSerializerOptions путем копирования существующих экземпляров или с помощью стандартных параметров веб-приложения.
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
ms.openlocfilehash: 0febfe15f36856f10699fd327fb17c146277eb9b
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/01/2020
ms.locfileid: "96439871"
---
# <a name="how-to-instantiate-jsonserializeroptions-instances-with-no-locsystemtextjson"></a>Создание экземпляров JsonSerializerOptions с помощью System.Text.Json

Из этой статьи вы узнаете, как создавать экземпляры <xref:System.Text.Json.JsonSerializerOptions> путем копирования существующих экземпляров или с помощью стандартных параметров веб-приложения.

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
* [Сопоставление без учета регистра](system-text-json-character-casing.md)
* [Настройка имен и значений свойств](system-text-json-customize-properties.md)
* [Игнорирование свойств](system-text-json-ignore-properties.md)
* [Применение недействительного кода JSON](system-text-json-invalid-json.md)
* [Обработка переполнения JSON](system-text-json-handle-overflow.md)
* [Сохранение циклических ссылок](system-text-json-preserve-references.md)
* [Неизменяемые типы и непубличные методы доступа](system-text-json-immutability.md)
* [Полиморфная сериализация](system-text-json-polymorphism.md)
* [Справочник по API System.Text.Json](xref:System.Text.Json)
