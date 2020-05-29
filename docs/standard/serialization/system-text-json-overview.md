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
ms.openlocfilehash: 909d979d46b30939e304af071de65d230febd92d
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83380127"
---
# <a name="json-serialization-and-deserialization-marshalling-and-unmarshalling-in-net---overview"></a>Сериализация и десериализация JSON (маршалинг и демаршалинг) в .NET — обзор

Пространство имен `System.Text.Json` предоставляет функциональные возможности для сериализации в нотацию объектов JavaScript (JSON) и десериализации объектов из этой нотации.

Архитектура библиотеки позволяет обеспечить высокую производительность и низкое выделение памяти для обширного набора функций. Встроенная поддержка UTF-8 оптимизирует процесс чтения и записи текста JSON в кодировке UTF-8, которая является наиболее распространенной кодировкой для данных в Интернете и файлов на диске.

Библиотека также предоставляет классы для работы с объектной моделью документов (DOM) в памяти. Эта возможность обеспечивает произвольный доступ только для чтения к элементам в файле JSON или строке.

## <a name="how-to-get-the-library"></a>Получение библиотеки

* Библиотека входит в состав общей платформы [.NET Core 3.0](https://aka.ms/netcore3download).
* Для других целевых платформ установите пакет NuGet [System.Text.Json](https://www.nuget.org/packages/System.Text.Json). Пакет поддерживает:
  * .NET Standard 2.0 и более поздних версий
  * .NET Framework 4.7.2 и более поздних версий
  * .NET Core 2.0, 2.1 и 2.2

## <a name="additional-resources"></a>Дополнительные ресурсы

* [Использование библиотеки](system-text-json-how-to.md)
* [Как выполнить миграцию из Newtonsoft.Json](system-text-json-migrate-from-newtonsoft-how-to.md)
* [Написание преобразователей](system-text-json-converters-how-to.md)
* [Исходный код System.Text.Json](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json)
* [Справочник по API System.Text.Json](xref:System.Text.Json)
* [Справочник по API System.Text.Json.Serialization](xref:System.Text.Json.Serialization)
<!-- * [Roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)-->
