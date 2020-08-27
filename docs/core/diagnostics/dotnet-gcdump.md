---
title: dotnet-gcdump — .NET Core
description: Установка и использование программы командной строки dotnet-gcdump.
ms.date: 07/26/2020
ms.openlocfilehash: a7b19f4d7487677b975621e7267a17894dae2e3a
ms.sourcegitcommit: c4a15c6c4ecbb8a46ad4e67d9b3ab9b8b031d849
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/20/2020
ms.locfileid: "88656655"
---
# <a name="heap-analysis-tool-dotnet-gcdump"></a><span data-ttu-id="697a5-103">Средство анализа кучи (dotnet-gcdump)</span><span class="sxs-lookup"><span data-stu-id="697a5-103">Heap analysis tool (dotnet-gcdump)</span></span>

<span data-ttu-id="697a5-104">**Эта статья относится к:** ✔️ пакету SDK для .NET Core 3.1 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="697a5-104">**This article applies to:** ✔️ .NET Core 3.1 SDK and later versions</span></span>

## <a name="install-dotnet-gcdump"></a><span data-ttu-id="697a5-105">Установка dotnet-gcdump</span><span class="sxs-lookup"><span data-stu-id="697a5-105">Install dotnet-gcdump</span></span>

<span data-ttu-id="697a5-106">Чтобы установить последнюю версию [пакета NuGet](https://www.nuget.org/packages/dotnet-gcdump) `dotnet-gcdump`, используйте команду [dotnet tool install](../tools/dotnet-tool-install.md).</span><span class="sxs-lookup"><span data-stu-id="697a5-106">To install the latest release version of the `dotnet-gcdump` [NuGet package](https://www.nuget.org/packages/dotnet-gcdump), use the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

```dotnetcli
dotnet tool install -g dotnet-gcdump
```

## <a name="synopsis"></a><span data-ttu-id="697a5-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="697a5-107">Synopsis</span></span>

```console
dotnet-gcdump [-h|--help] [--version] <command>
```

## <a name="description"></a><span data-ttu-id="697a5-108">Описание</span><span class="sxs-lookup"><span data-stu-id="697a5-108">Description</span></span>

<span data-ttu-id="697a5-109">Глобальное средство `dotnet-gcdump` предоставляет способ сбора дампов сборщика мусора (GC) для активных процессов .NET.</span><span class="sxs-lookup"><span data-stu-id="697a5-109">The `dotnet-gcdump` global tool is a way to collect GC (Garbage Collector) dumps of live .NET processes.</span></span> <span data-ttu-id="697a5-110">Оно использует технологию EventPipe, которая является межплатформенной альтернативой трассировки событий Windows (ETW).</span><span class="sxs-lookup"><span data-stu-id="697a5-110">It uses the EventPipe technology, which is a cross-platform alternative to ETW on Windows.</span></span> <span data-ttu-id="697a5-111">Дампы сборщика мусора создаются путем его запуска в целевом процессе, включения специальных событий и повторного создания графа корней объектов из потока событий.</span><span class="sxs-lookup"><span data-stu-id="697a5-111">GC dumps are created by triggering a GC in the target process, turning on special events, and regenerating the graph of object roots from the event stream.</span></span> <span data-ttu-id="697a5-112">Этот процесс позволяет собирать дампы сборщика мусора во время выполнения процесса и с минимальными издержками.</span><span class="sxs-lookup"><span data-stu-id="697a5-112">This process allows for GC dumps to be collected while the process is running and with minimal overhead.</span></span> <span data-ttu-id="697a5-113">Эти дампы могут быть полезны в нескольких сценариях.</span><span class="sxs-lookup"><span data-stu-id="697a5-113">These dumps are useful for several scenarios:</span></span>

- <span data-ttu-id="697a5-114">Сравнение количества объектов в куче в нескольких моментах времени.</span><span class="sxs-lookup"><span data-stu-id="697a5-114">Comparing the number of objects on the heap at several points in time.</span></span>
- <span data-ttu-id="697a5-115">Анализ корней объектов (ответы на вопросы вида "что все еще содержит ссылку на этот тип?").</span><span class="sxs-lookup"><span data-stu-id="697a5-115">Analyzing roots of objects (answering questions like, "what still has a reference to this type?").</span></span>
- <span data-ttu-id="697a5-116">Сбор общей статистики о количестве объектов в куче.</span><span class="sxs-lookup"><span data-stu-id="697a5-116">Collecting general statistics about the counts of objects on the heap.</span></span>

### <a name="view-the-gc-dump-captured-from-dotnet-gcdump"></a><span data-ttu-id="697a5-117">Просмотр дампа сборщика мусора, захваченного с помощью dotnet-gcdump</span><span class="sxs-lookup"><span data-stu-id="697a5-117">View the GC dump captured from dotnet-gcdump</span></span>

<span data-ttu-id="697a5-118">В Windows файлы `.gcdump` можно просмотреть в [PerfView](https://github.com/microsoft/perfview) для анализа или в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="697a5-118">On Windows, `.gcdump` files can be viewed in [PerfView](https://github.com/microsoft/perfview) for analysis or in Visual Studio.</span></span> <span data-ttu-id="697a5-119">В настоящее время невозможно открыть файлы `.gcdump` на платформах, отличных от Windows.</span><span class="sxs-lookup"><span data-stu-id="697a5-119">Currently, There is no way of opening a `.gcdump` on non-Windows platforms.</span></span>

<span data-ttu-id="697a5-120">Вы можете объединить несколько файлов `.gcdump` и открыть их одновременно в Visual Studio, чтобы получить возможность сравнения.</span><span class="sxs-lookup"><span data-stu-id="697a5-120">You can collect multiple `.gcdump`s and open them simultaneously in Visual Studio to get a comparison experience.</span></span>

## <a name="options"></a><span data-ttu-id="697a5-121">Параметры</span><span class="sxs-lookup"><span data-stu-id="697a5-121">Options</span></span>

- **`--version`**

  <span data-ttu-id="697a5-122">Отображает версию программы `dotnet-gcdump`.</span><span class="sxs-lookup"><span data-stu-id="697a5-122">Displays the version of the `dotnet-gcdump` utility.</span></span>

- **`-h|--help`**

  <span data-ttu-id="697a5-123">Отображение справки в командной строке.</span><span class="sxs-lookup"><span data-stu-id="697a5-123">Shows command-line help.</span></span>

## `dotnet-gcdump collect`

<span data-ttu-id="697a5-124">Собирает дамп сборщика мусора из выполняемого в данный момент процесса.</span><span class="sxs-lookup"><span data-stu-id="697a5-124">Collects a GC dump from a currently running process.</span></span>

### <a name="synopsis"></a><span data-ttu-id="697a5-125">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="697a5-125">Synopsis</span></span>

```console
dotnet-gcdump collect [-h|--help] [-p|--process-id <pid>] [-o|--output <gcdump-file-path>] [-v|--verbose] [-t|--timeout <timeout>] [-n|--name <name>]
```

### <a name="options"></a><span data-ttu-id="697a5-126">Параметры</span><span class="sxs-lookup"><span data-stu-id="697a5-126">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="697a5-127">Отображение справки в командной строке.</span><span class="sxs-lookup"><span data-stu-id="697a5-127">Shows command-line help.</span></span>

- **`-p|--process-id <pid>`**

  <span data-ttu-id="697a5-128">Идентификатор процесса, из которого нужно получить дамп сборщика мусора.</span><span class="sxs-lookup"><span data-stu-id="697a5-128">The process ID to collect the GC dump from.</span></span>

- **`-o|--output <gcdump-file-path>`**

  <span data-ttu-id="697a5-129">Путь, по которому нужно записывать собранные дампы сборщика мусора.</span><span class="sxs-lookup"><span data-stu-id="697a5-129">The path where collected GC dumps should be written.</span></span> <span data-ttu-id="697a5-130">Значение по умолчанию: *.\\ГГГГММДД\_ЧЧММСС\_\<pid>.gcdump*.</span><span class="sxs-lookup"><span data-stu-id="697a5-130">Defaults to *.\\YYYYMMDD\_HHMMSS\_\<pid>.gcdump*.</span></span>

- **`-v|--verbose`**

  <span data-ttu-id="697a5-131">Выводить журнал во время сбора дампа сборщика мусора.</span><span class="sxs-lookup"><span data-stu-id="697a5-131">Output the log while collecting the GC dump.</span></span>

- **`-t|--timeout <timeout>`**

  <span data-ttu-id="697a5-132">Прервать сбор дампа сборщика мусора, если он занимает больше указанного количества секунд.</span><span class="sxs-lookup"><span data-stu-id="697a5-132">Give up on collecting the GC dump if it takes longer than this many seconds.</span></span> <span data-ttu-id="697a5-133">Значение по умолчанию — 30.</span><span class="sxs-lookup"><span data-stu-id="697a5-133">The default value is 30.</span></span>

- **`-n|--name <name>`**

  <span data-ttu-id="697a5-134">Имя процесса, из которого нужно получить дамп сборщика мусора.</span><span class="sxs-lookup"><span data-stu-id="697a5-134">The name of the process to collect the GC dump from.</span></span>

## `dotnet-gcdump ps`

<span data-ttu-id="697a5-135">Список процессов dotnet, из которых можно получить дамп сборщика мусора.</span><span class="sxs-lookup"><span data-stu-id="697a5-135">Lists the dotnet processes that GC dumps can be collected for.</span></span>

### <a name="synopsis"></a><span data-ttu-id="697a5-136">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="697a5-136">Synopsis</span></span>

```console
dotnet-gcdump ps
```

## `dotnet-gcdump report <gcdump_filename>`

<span data-ttu-id="697a5-137">Создание отчета из ранее созданного дампа сборщика мусора или из выполняющегося процесса и запись его в `stdout`.</span><span class="sxs-lookup"><span data-stu-id="697a5-137">Generate a report from a previously generated GC dump or from a running process, and write to `stdout`.</span></span>

### <a name="synopsis"></a><span data-ttu-id="697a5-138">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="697a5-138">Synopsis</span></span>

```console
dotnet-gcdump report [-h|--help] [-p|--process-id <pid>] [-t|--report-type <HeapStat>]
```

### <a name="options"></a><span data-ttu-id="697a5-139">Параметры</span><span class="sxs-lookup"><span data-stu-id="697a5-139">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="697a5-140">Отображение справки в командной строке.</span><span class="sxs-lookup"><span data-stu-id="697a5-140">Shows command-line help.</span></span>

- **`-p|--process-id <pid>`**

  <span data-ttu-id="697a5-141">Идентификатор процесса, из которого нужно получить дамп сборщика мусора.</span><span class="sxs-lookup"><span data-stu-id="697a5-141">The process ID to collect the GC dump from.</span></span>

- **`-t|--report-type <HeapStat>`**

  <span data-ttu-id="697a5-142">Тип создаваемого отчета.</span><span class="sxs-lookup"><span data-stu-id="697a5-142">The type of report to generate.</span></span> <span data-ttu-id="697a5-143">Доступные значения: heapstat (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="697a5-143">Available options: heapstat (default).</span></span>

## <a name="troubleshoot"></a><span data-ttu-id="697a5-144">Диагностика</span><span class="sxs-lookup"><span data-stu-id="697a5-144">Troubleshoot</span></span>

- <span data-ttu-id="697a5-145">В gcdump нет сведений о типе.</span><span class="sxs-lookup"><span data-stu-id="697a5-145">There is no type information in the gcdump.</span></span>

   <span data-ttu-id="697a5-146">До .NET Core 3.1 существовала проблема, при которой кэш типов не очищался между вызовами gcdump, когда они вызывались с помощью EventPipe.</span><span class="sxs-lookup"><span data-stu-id="697a5-146">Prior to .NET Core 3.1, there was an issue where a type cache was not cleared between gcdumps when they were invoked with EventPipe.</span></span> <span data-ttu-id="697a5-147">Это приводило к тому, что события, необходимые для определения сведений о типе, не отправлялись для второго и последующего вызовов gcdump.</span><span class="sxs-lookup"><span data-stu-id="697a5-147">This resulted in the events needed for determining type information not being sent for the second and subsequent gcdumps.</span></span> <span data-ttu-id="697a5-148">Это было исправлено в версии .NET Core 3.1-preview2.</span><span class="sxs-lookup"><span data-stu-id="697a5-148">This was fixed in .NET Core 3.1-preview2.</span></span>

- <span data-ttu-id="697a5-149">COM и статические типы не содержатся в дампе сборщика мусора.</span><span class="sxs-lookup"><span data-stu-id="697a5-149">COM and static types aren't in the GC dump.</span></span>

   <span data-ttu-id="697a5-150">До .NET Core 3.1-preview2 существовала проблема, при которой COM и статические типы не отправлялись при вызове дампа сборщика мусора через EventPipe.</span><span class="sxs-lookup"><span data-stu-id="697a5-150">Prior to .NET Core 3.1-preview2, there was an issue where static and COM types weren't sent when the GC dump was invoked via EventPipe.</span></span> <span data-ttu-id="697a5-151">Это было исправлено в версии .NET Core 3.1-preview2.</span><span class="sxs-lookup"><span data-stu-id="697a5-151">This has been fixed in .NET Core 3.1-preview2.</span></span>
