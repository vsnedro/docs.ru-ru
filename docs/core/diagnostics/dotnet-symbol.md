---
title: dotnet-symbol — .NET Core
description: Установка и использование программы командной строки dotnet-symbol.
ms.date: 08/26/2020
ms.openlocfilehash: feaa64ad756878f85b829ab0cecf6ea2736014ba
ms.sourcegitcommit: 43d5aca3fda42bad8843f6c4e72f6bd52daa55f1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/09/2020
ms.locfileid: "89598302"
---
# <a name="symbol-downloader-dotnet-symbol"></a><span data-ttu-id="38bba-103">Загрузчик символов (dotnet-symbol)</span><span class="sxs-lookup"><span data-stu-id="38bba-103">Symbol downloader (dotnet-symbol)</span></span>

<span data-ttu-id="38bba-104">**Эта статья относится к следующему.** ✔️ SDK для .NET Core 2.1 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="38bba-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="install-dotnet-symbol"></a><span data-ttu-id="38bba-105">Установка dotnet-symbol</span><span class="sxs-lookup"><span data-stu-id="38bba-105">Install dotnet-symbol</span></span>

<span data-ttu-id="38bba-106">Чтобы установить последнюю версию [пакета NuGet](https://www.nuget.org/packages/dotnet-symbol) `dotnet-symbol`, используйте команду [dotnet tool install](../tools/dotnet-tool-install.md).</span><span class="sxs-lookup"><span data-stu-id="38bba-106">To install the latest release version of the `dotnet-symbol` [NuGet package](https://www.nuget.org/packages/dotnet-symbol), use the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

```dotnetcli
dotnet tool install -g dotnet-symbol
```

## <a name="synopsis"></a><span data-ttu-id="38bba-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="38bba-107">Synopsis</span></span>

```console
dotnet-symbol [-h|--help] [options] <FILES>
```

## <a name="description"></a><span data-ttu-id="38bba-108">Описание</span><span class="sxs-lookup"><span data-stu-id="38bba-108">Description</span></span>

<span data-ttu-id="38bba-109">Глобальный инструмент `dotnet-symbol` скачивает файлы (символы, приложения уровня данных, модули и т. д.), необходимые для отладки основных дампов и минидампов.</span><span class="sxs-lookup"><span data-stu-id="38bba-109">The `dotnet-symbol` global tool downloads files (symbols, DAC, modules, etc.) needed for debugging core dumps and minidumps.</span></span> <span data-ttu-id="38bba-110">Это может быть полезно при отладке дампов, записанных на другой компьютер.</span><span class="sxs-lookup"><span data-stu-id="38bba-110">This can be useful when debugging dumps captured on another machine.</span></span> <span data-ttu-id="38bba-111">`dotnet-symbol` может скачивать модули и символы, необходимые для анализа дампа.</span><span class="sxs-lookup"><span data-stu-id="38bba-111">`dotnet-symbol` can download modules and symbols needed to analyze the dump.</span></span>

## <a name="options"></a><span data-ttu-id="38bba-112">Параметры</span><span class="sxs-lookup"><span data-stu-id="38bba-112">Options</span></span>

- **`--microsoft-symbol-server`**

  <span data-ttu-id="38bba-113">Добавление пути к серверу символов "http://msdl.microsoft.com/download/symbols" (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="38bba-113">Add 'http://msdl.microsoft.com/download/symbols' symbol server path (default).</span></span>

- **`--server-path <symbol server path>`**

  <span data-ttu-id="38bba-114">Добавление сервера символов в путь к серверу.</span><span class="sxs-lookup"><span data-stu-id="38bba-114">Add a symbol server to the server path.</span></span>

- **`authenticated-server-path <pat> <server path>`**

  <span data-ttu-id="38bba-115">Добавление сервера символов, прошедшего проверку подлинности, в путь к серверу с помощью личного маркера доступа (PAT).</span><span class="sxs-lookup"><span data-stu-id="38bba-115">Add an authenticated symbol server to the server path using a personal access token (PAT).</span></span>

- **`--cache-directory <file cache directory>`**

  <span data-ttu-id="38bba-116">Добавление каталога кэша.</span><span class="sxs-lookup"><span data-stu-id="38bba-116">Adds a cache directory.</span></span>

- **`--recurse-subdirectories`**

  <span data-ttu-id="38bba-117">Обработка входных файлов во всех подкаталогах.</span><span class="sxs-lookup"><span data-stu-id="38bba-117">Process input files in all subdirectories.</span></span>

- **`--host-only`**

  <span data-ttu-id="38bba-118">Загрузка только основной программы (например, dotnet), которая требуется lldb для загрузки основных дампов.</span><span class="sxs-lookup"><span data-stu-id="38bba-118">Download only the host program (i.e. dotnet) that lldb needs for loading core dumps.</span></span>

- **`--symbols`**

  <span data-ttu-id="38bba-119">Загрузка файлов символов (PDB, DBG, DWARF).</span><span class="sxs-lookup"><span data-stu-id="38bba-119">Download symbol files (.pdb, .dbg, .dwarf).</span></span>

- **`--modules`**

  <span data-ttu-id="38bba-120">Загрузка файлов модулей (DLL, SO, DYLIB).</span><span class="sxs-lookup"><span data-stu-id="38bba-120">Download the module files (.dll, .so, .dylib).</span></span>

- **`--debugging`**

  <span data-ttu-id="38bba-121">Загрузка специальных модулей отладки (DAC, DBI, SOS).</span><span class="sxs-lookup"><span data-stu-id="38bba-121">Download the special debugging modules (DAC, DBI, SOS).</span></span>

- **`--windows-pdbs`**

  <span data-ttu-id="38bba-122">Принудительная загрузка файлов PDB Windows при наличии переносимых PDB.</span><span class="sxs-lookup"><span data-stu-id="38bba-122">Force the downloading of the Windows PDBs when Portable PDBs are also available.</span></span>

- **`-o, --output <output directory>`**

  <span data-ttu-id="38bba-123">Указание выходного каталога.</span><span class="sxs-lookup"><span data-stu-id="38bba-123">Set the output directory.</span></span> <span data-ttu-id="38bba-124">В противном случае запись рядом с входным файлом (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="38bba-124">Otherwise, write next to the input file (default).</span></span>

- **`-d, --diagnostics`**

  <span data-ttu-id="38bba-125">Включение выходных данных диагностики.</span><span class="sxs-lookup"><span data-stu-id="38bba-125">Enable diagnostic output.</span></span>

- **`-h|--help`**

  <span data-ttu-id="38bba-126">Отображение справки в командной строке.</span><span class="sxs-lookup"><span data-stu-id="38bba-126">Shows command-line help.</span></span>

## <a name="download-symbols"></a><span data-ttu-id="38bba-127">Скачать символы</span><span class="sxs-lookup"><span data-stu-id="38bba-127">Download symbols</span></span>

<span data-ttu-id="38bba-128">Выполнение `dotnet-symbol` для файла дампа по умолчанию загружает все модули, символы и файлы DAC/DBI, необходимые для отладки дампа, включая управляемые сборки.</span><span class="sxs-lookup"><span data-stu-id="38bba-128">Running `dotnet-symbol` against a dump file will, by default, download all the modules, symbols, and DAC/DBI files needed to debug the dump including the managed assemblies.</span></span> <span data-ttu-id="38bba-129">Поскольку SOS теперь может скачивать символы при необходимости, большинство основных дампов Linux можно анализировать с помощью lldb, используя только модули host (dotnet) и модули отладки.</span><span class="sxs-lookup"><span data-stu-id="38bba-129">Because SOS can now download symbols when needed, most Linux core dumps can be analyzed using lldb with only the host (dotnet) and debugging modules.</span></span> <span data-ttu-id="38bba-130">Чтобы получить эти файлы, необходимые для диагностики основного дампа с помощью lldb, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="38bba-130">To get these files necessary for diagnosing a core dump with lldb run:</span></span>

```console
dotnet-symbol --host-only --debugging <dump file path>
```

## <a name="troubleshoot"></a><span data-ttu-id="38bba-131">Диагностика</span><span class="sxs-lookup"><span data-stu-id="38bba-131">Troubleshoot</span></span>

- <span data-ttu-id="38bba-132">Ошибка 404 (объект не найден) при скачивании символов.</span><span class="sxs-lookup"><span data-stu-id="38bba-132">404 Not Found while downloading symbols.</span></span>

   <span data-ttu-id="38bba-133">Загрузка символов поддерживается только для официальных версий среды выполнения .NET Core, полученных по официальным каналам, таким как [официальный веб-сайт](https://dotnet.microsoft.com/download/dotnet-core) и [источники по умолчанию в сценариях установки dotnet](https://docs.microsoft.com/dotnet/core/tools/dotnet-install-scripts).</span><span class="sxs-lookup"><span data-stu-id="38bba-133">Symbol download is only supported for official .NET Core runtime versions acquired through official channels such as [the official web site](https://dotnet.microsoft.com/download/dotnet-core) and the [default sources in the dotnet installation scripts](https://docs.microsoft.com/dotnet/core/tools/dotnet-install-scripts).</span></span> <span data-ttu-id="38bba-134">Ошибка 404 при скачивании файлов отладки может указывать на то, что дамп был создан с помощью среды выполнения .NET Core из другого источника, например из исходного кода, созданного локально или для конкретного дистрибутива Linux, либо с сайтов сообщества, таких как archlinux.</span><span class="sxs-lookup"><span data-stu-id="38bba-134">A 404 error while downloading debugging files may indicate that the dump was created with a .NET Core runtime from another source, such as one built from source locally or for a particular Linux distro, or from community sites like archlinux.</span></span> <span data-ttu-id="38bba-135">В таких случаях файл, необходимый для отладки (dotnet, libcoreclr.so и libmscordaccore.so), должен быть скопирован из этих источников или из среды, в которой был создан файл дампа.</span><span class="sxs-lookup"><span data-stu-id="38bba-135">In such cases, file necessary for debugging (dotnet, libcoreclr.so, and libmscordaccore.so) should be copied from those sources or from the environment the dump file was created in.</span></span>
