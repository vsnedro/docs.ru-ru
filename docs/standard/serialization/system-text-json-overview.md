---
title: Сериализация и десериализация JSON с помощью C# — .NET
description: В статье описаны функциональные возможности пространства имен System.Text.Json для сериализации объектов в JSON из .NET и их десериализации наоборот.
ms.date: 01/10/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: cb5c15c2a5c336e2d5b4a3754fa7a02a370602f3
ms.sourcegitcommit: 81f1bba2c97a67b5ca76bcc57b37333ffca60c7b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "97009889"
---
# <a name="json-serialization-and-deserialization-marshalling-and-unmarshalling-in-net---overview"></a>Сериализация и десериализация JSON (маршалинг и демаршалинг) в .NET — обзор

Пространство имен `System.Text.Json` предоставляет функциональные возможности для сериализации в нотацию объектов JavaScript (JSON) и десериализации объектов из этой нотации.

Архитектура библиотеки позволяет обеспечить высокую производительность и низкое выделение памяти для обширного набора функций. Встроенная поддержка UTF-8 оптимизирует процесс чтения и записи текста JSON в кодировке UTF-8, которая является наиболее распространенной кодировкой для данных в Интернете и файлов на диске.

Библиотека также предоставляет классы для работы с объектной моделью документов (DOM) в памяти. Эта возможность обеспечивает произвольный доступ только для чтения к элементам в файле JSON или строке.

## <a name="how-to-get-the-library"></a>Получение библиотеки

* Библиотека входит в состав общей платформы для .NET Core 3.0 и более поздних версий.
* Для более ранних версий платформы установите пакет NuGet [System.Text.Json](https://www.nuget.org/packages/System.Text.Json). Пакет поддерживает:

  * .NET Standard 2.0 и более поздних версий
  * .NET Framework 4.7.2 и более поздних версий
  * .NET Core 2.0, 2.1 и 2.2

## <a name="additional-resources"></a>Дополнительные ресурсы

* [Использование библиотеки](system-text-json-how-to.md)
* [Создание экземпляров JsonSerializerOptions](system-text-json-configure-options.md)
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
