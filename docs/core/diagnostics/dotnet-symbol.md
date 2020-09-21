---
title: dotnet-symbol — .NET Core
description: Установка и использование программы командной строки dotnet-symbol.
ms.date: 08/26/2020
ms.openlocfilehash: 5a96306fc96525b00e57eda089a45b730a7e3e8c
ms.sourcegitcommit: aa6d8a90a4f5d8fe0f6e967980b8c98433f05a44
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/16/2020
ms.locfileid: "90679192"
---
# <a name="symbol-downloader-dotnet-symbol"></a>Загрузчик символов (dotnet-symbol)

**Эта статья относится к следующему.** ✔️ SDK для .NET Core 2.1 и более поздних версий

## <a name="install-dotnet-symbol"></a>Установка dotnet-symbol

Чтобы установить последнюю версию [пакета NuGet](https://www.nuget.org/packages/dotnet-symbol) `dotnet-symbol`, используйте команду [dotnet tool install](../tools/dotnet-tool-install.md).

```dotnetcli
dotnet tool install -g dotnet-symbol
```

## <a name="synopsis"></a>Краткий обзор

```console
dotnet-symbol [-h|--help] [options] <FILES>
```

## <a name="description"></a>Описание

Глобальный инструмент `dotnet-symbol` скачивает файлы (символы, приложения уровня данных, модули и т. д.), необходимые для отладки основных дампов и минидампов. Это может быть полезно при отладке дампов, записанных на другой компьютер. `dotnet-symbol` может скачивать модули и символы, необходимые для анализа дампа.

## <a name="options"></a>Параметры

- **`--microsoft-symbol-server`**

  Добавление пути к серверу символов "http://msdl.microsoft.com/download/symbols" (по умолчанию).

- **`--server-path <symbol server path>`**

  Добавление сервера символов в путь к серверу.

- **`authenticated-server-path <pat> <server path>`**

  Добавление сервера символов, прошедшего проверку подлинности, в путь к серверу с помощью личного маркера доступа (PAT).

- **`--cache-directory <file cache directory>`**

  Добавление каталога кэша.

- **`--recurse-subdirectories`**

  Обработка входных файлов во всех подкаталогах.

- **`--host-only`**

  Загрузка только основной программы (например, dotnet), которая требуется lldb для загрузки основных дампов.

- **`--symbols`**

  Загрузка файлов символов (PDB, DBG, DWARF).

- **`--modules`**

  Загрузка файлов модулей (DLL, SO, DYLIB).

- **`--debugging`**

  Загрузка специальных модулей отладки (DAC, DBI, SOS).

- **`--windows-pdbs`**

  Принудительная загрузка файлов PDB Windows при наличии переносимых PDB.

- **`-o, --output <output directory>`**

  Указание выходного каталога. В противном случае запись рядом с входным файлом (по умолчанию).

- **`-d, --diagnostics`**

  Включение выходных данных диагностики.

- **`-h|--help`**

  Отображение справки в командной строке.

## <a name="download-symbols"></a>Скачать символы

Выполнение `dotnet-symbol` для файла дампа по умолчанию загружает все модули, символы и файлы DAC/DBI, необходимые для отладки дампа, включая управляемые сборки. Поскольку SOS теперь может скачивать символы при необходимости, большинство основных дампов Linux можно анализировать с помощью lldb, используя только модули host (dotnet) и модули отладки. Чтобы получить эти файлы, необходимые для диагностики основного дампа с помощью lldb, выполните следующую команду:

```console
dotnet-symbol --host-only --debugging <dump file path>
```

## <a name="troubleshoot"></a>Диагностика

- Ошибка 404 (объект не найден) при скачивании символов.

   Загрузка символов поддерживается только для официальных версий среды выполнения .NET Core, полученных по официальным каналам, таким как [официальный веб-сайт](https://dotnet.microsoft.com/download/dotnet-core) и [источники по умолчанию в сценариях установки dotnet](../tools/dotnet-install-script.md). Ошибка 404 при скачивании файлов отладки может указывать на то, что дамп был создан с помощью среды выполнения .NET Core из другого источника, например из исходного кода, созданного локально или для конкретного дистрибутива Linux, либо с сайтов сообщества, таких как archlinux. В таких случаях файл, необходимый для отладки (dotnet, libcoreclr.so и libmscordaccore.so), должен быть скопирован из этих источников или из среды, в которой был создан файл дампа.
