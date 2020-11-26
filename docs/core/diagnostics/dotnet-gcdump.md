---
title: Средство диагностики dotnet-gcdump — .NET CLI
description: Узнайте, как установить и использовать средство CLI dotnet-gcdump для сбора дампов сборщика мусора активных процессов .NET с помощью .NET EventPipe.
ms.date: 11/17/2020
ms.openlocfilehash: 59de1845ada9e5bdd0b24bf4312517283324ce94
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/18/2020
ms.locfileid: "94826044"
---
# <a name="heap-analysis-tool-dotnet-gcdump"></a><span data-ttu-id="b343c-103">Средство анализа кучи (dotnet-gcdump)</span><span class="sxs-lookup"><span data-stu-id="b343c-103">Heap analysis tool (dotnet-gcdump)</span></span>

<span data-ttu-id="b343c-104">**Эта статья относится к:** ✔️ пакету SDK для .NET Core 3.1 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="b343c-104">**This article applies to:** ✔️ .NET Core 3.1 SDK and later versions</span></span>

## <a name="install"></a><span data-ttu-id="b343c-105">Установка</span><span class="sxs-lookup"><span data-stu-id="b343c-105">Install</span></span>

<span data-ttu-id="b343c-106">Есть два способа загрузки и установки `dotnet-gcdump`:</span><span class="sxs-lookup"><span data-stu-id="b343c-106">There are two ways to download and install `dotnet-gcdump`:</span></span>

- <span data-ttu-id="b343c-107">**Средство dotnet global:**</span><span class="sxs-lookup"><span data-stu-id="b343c-107">**dotnet global tool:**</span></span>

  <span data-ttu-id="b343c-108">Чтобы установить последнюю версию [пакета NuGet](https://www.nuget.org/packages/dotnet-gcdump) `dotnet-gcdump`, используйте команду [dotnet tool install](../tools/dotnet-tool-install.md).</span><span class="sxs-lookup"><span data-stu-id="b343c-108">To install the latest release version of the `dotnet-gcdump` [NuGet package](https://www.nuget.org/packages/dotnet-gcdump), use the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

  ```dotnetcli
  dotnet tool install --global dotnet-gcdump
  ```

- <span data-ttu-id="b343c-109">**Прямое скачивание:**</span><span class="sxs-lookup"><span data-stu-id="b343c-109">**Direct download:**</span></span>

  <span data-ttu-id="b343c-110">скачайте исполняемый файл средства, соответствующий вашей платформе:</span><span class="sxs-lookup"><span data-stu-id="b343c-110">Download the tool executable that matches your platform:</span></span>

  | <span data-ttu-id="b343c-111">OS</span><span class="sxs-lookup"><span data-stu-id="b343c-111">OS</span></span>  | <span data-ttu-id="b343c-112">Платформа</span><span class="sxs-lookup"><span data-stu-id="b343c-112">Platform</span></span> |
  | --- | -------- |
  | <span data-ttu-id="b343c-113">Windows</span><span class="sxs-lookup"><span data-stu-id="b343c-113">Windows</span></span> | <span data-ttu-id="b343c-114">[x86](https://aka.ms/dotnet-gcdump/win-x86) \| [x64](https://aka.ms/dotnet-gcdump/win-x64) \| [arm](https://aka.ms/dotnet-gcdump/win-arm) \| [arm-x64](https://aka.ms/dotnet-gcdump/win-arm64)</span><span class="sxs-lookup"><span data-stu-id="b343c-114">[x86](https://aka.ms/dotnet-gcdump/win-x86) \| [x64](https://aka.ms/dotnet-gcdump/win-x64) \| [arm](https://aka.ms/dotnet-gcdump/win-arm) \| [arm-x64](https://aka.ms/dotnet-gcdump/win-arm64)</span></span> |
  | <span data-ttu-id="b343c-115">macOS</span><span class="sxs-lookup"><span data-stu-id="b343c-115">macOS</span></span>   | [<span data-ttu-id="b343c-116">x64</span><span class="sxs-lookup"><span data-stu-id="b343c-116">x64</span></span>](https://aka.ms/dotnet-gcdump/osx-x64) |
  | <span data-ttu-id="b343c-117">Linux</span><span class="sxs-lookup"><span data-stu-id="b343c-117">Linux</span></span>   | <span data-ttu-id="b343c-118">[x64](https://aka.ms/dotnet-gcdump/linux-x64) \| [arm](https://aka.ms/dotnet-gcdump/linux-arm) \| [arm64](https://aka.ms/dotnet-gcdump/linux-arm64) \| [musl-x64](https://aka.ms/dotnet-gcdump/linux-musl-x64) \| [musl-arm64](https://aka.ms/dotnet-gcdump/linux-musl-arm64)</span><span class="sxs-lookup"><span data-stu-id="b343c-118">[x64](https://aka.ms/dotnet-gcdump/linux-x64) \| [arm](https://aka.ms/dotnet-gcdump/linux-arm) \| [arm64](https://aka.ms/dotnet-gcdump/linux-arm64) \| [musl-x64](https://aka.ms/dotnet-gcdump/linux-musl-x64) \| [musl-arm64](https://aka.ms/dotnet-gcdump/linux-musl-arm64)</span></span> |

## <a name="synopsis"></a><span data-ttu-id="b343c-119">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="b343c-119">Synopsis</span></span>

```console
dotnet-gcdump [-h|--help] [--version] <command>
```

## <a name="description"></a><span data-ttu-id="b343c-120">Описание</span><span class="sxs-lookup"><span data-stu-id="b343c-120">Description</span></span>

<span data-ttu-id="b343c-121">Глобальное средство `dotnet-gcdump` собирает дампы сборщика мусора для активных процессов .NET с помощью [EventPipe](./eventpipe.md).</span><span class="sxs-lookup"><span data-stu-id="b343c-121">The `dotnet-gcdump` global tool collects GC (Garbage Collector) dumps of live .NET processes using [EventPipe](./eventpipe.md).</span></span> <span data-ttu-id="b343c-122">Дампы сборщика мусора создаются путем его запуска в целевом процессе, включения специальных событий и повторного создания графа корней объектов из потока событий.</span><span class="sxs-lookup"><span data-stu-id="b343c-122">GC dumps are created by triggering a GC in the target process, turning on special events, and regenerating the graph of object roots from the event stream.</span></span> <span data-ttu-id="b343c-123">Этот процесс позволяет собирать дампы сборщика мусора во время выполнения процесса и с минимальными издержками.</span><span class="sxs-lookup"><span data-stu-id="b343c-123">This process allows for GC dumps to be collected while the process is running and with minimal overhead.</span></span> <span data-ttu-id="b343c-124">Эти дампы могут быть полезны в нескольких сценариях.</span><span class="sxs-lookup"><span data-stu-id="b343c-124">These dumps are useful for several scenarios:</span></span>

- <span data-ttu-id="b343c-125">Сравнение количества объектов в куче в нескольких моментах времени.</span><span class="sxs-lookup"><span data-stu-id="b343c-125">Comparing the number of objects on the heap at several points in time.</span></span>
- <span data-ttu-id="b343c-126">Анализ корней объектов (ответы на вопросы вида "что все еще содержит ссылку на этот тип?").</span><span class="sxs-lookup"><span data-stu-id="b343c-126">Analyzing roots of objects (answering questions like, "what still has a reference to this type?").</span></span>
- <span data-ttu-id="b343c-127">Сбор общей статистики о количестве объектов в куче.</span><span class="sxs-lookup"><span data-stu-id="b343c-127">Collecting general statistics about the counts of objects on the heap.</span></span>

### <a name="view-the-gc-dump-captured-from-dotnet-gcdump"></a><span data-ttu-id="b343c-128">Просмотр дампа сборщика мусора, захваченного с помощью dotnet-gcdump</span><span class="sxs-lookup"><span data-stu-id="b343c-128">View the GC dump captured from dotnet-gcdump</span></span>

<span data-ttu-id="b343c-129">В Windows файлы `.gcdump` можно просмотреть в [PerfView](https://github.com/microsoft/perfview) для анализа или в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b343c-129">On Windows, `.gcdump` files can be viewed in [PerfView](https://github.com/microsoft/perfview) for analysis or in Visual Studio.</span></span> <span data-ttu-id="b343c-130">В настоящее время невозможно открыть файлы `.gcdump` на платформах, отличных от Windows.</span><span class="sxs-lookup"><span data-stu-id="b343c-130">Currently, There is no way of opening a `.gcdump` on non-Windows platforms.</span></span>

<span data-ttu-id="b343c-131">Вы можете объединить несколько файлов `.gcdump` и открыть их одновременно в Visual Studio, чтобы получить возможность сравнения.</span><span class="sxs-lookup"><span data-stu-id="b343c-131">You can collect multiple `.gcdump`s and open them simultaneously in Visual Studio to get a comparison experience.</span></span>

## <a name="options"></a><span data-ttu-id="b343c-132">Параметры</span><span class="sxs-lookup"><span data-stu-id="b343c-132">Options</span></span>

- **`--version`**

  <span data-ttu-id="b343c-133">Отображает версию программы `dotnet-gcdump`.</span><span class="sxs-lookup"><span data-stu-id="b343c-133">Displays the version of the `dotnet-gcdump` utility.</span></span>

- **`-h|--help`**

  <span data-ttu-id="b343c-134">Отображение справки в командной строке.</span><span class="sxs-lookup"><span data-stu-id="b343c-134">Shows command-line help.</span></span>

## `dotnet-gcdump collect`

<span data-ttu-id="b343c-135">Собирает дамп сборщика мусора из выполняемого в данный момент процесса.</span><span class="sxs-lookup"><span data-stu-id="b343c-135">Collects a GC dump from a currently running process.</span></span>

### <a name="synopsis"></a><span data-ttu-id="b343c-136">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="b343c-136">Synopsis</span></span>

```console
dotnet-gcdump collect [-h|--help] [-p|--process-id <pid>] [-o|--output <gcdump-file-path>] [-v|--verbose] [-t|--timeout <timeout>] [-n|--name <name>]
```

### <a name="options"></a><span data-ttu-id="b343c-137">Параметры</span><span class="sxs-lookup"><span data-stu-id="b343c-137">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="b343c-138">Отображение справки в командной строке.</span><span class="sxs-lookup"><span data-stu-id="b343c-138">Shows command-line help.</span></span>

- **`-p|--process-id <pid>`**

  <span data-ttu-id="b343c-139">Идентификатор процесса, из которого нужно получить дамп сборщика мусора.</span><span class="sxs-lookup"><span data-stu-id="b343c-139">The process ID to collect the GC dump from.</span></span>

- **`-o|--output <gcdump-file-path>`**

  <span data-ttu-id="b343c-140">Путь, по которому нужно записывать собранные дампы сборщика мусора.</span><span class="sxs-lookup"><span data-stu-id="b343c-140">The path where collected GC dumps should be written.</span></span> <span data-ttu-id="b343c-141">Значение по умолчанию: *.\\ГГГГММДД\_ЧЧММСС\_\<pid>.gcdump*.</span><span class="sxs-lookup"><span data-stu-id="b343c-141">Defaults to *.\\YYYYMMDD\_HHMMSS\_\<pid>.gcdump*.</span></span>

- **`-v|--verbose`**

  <span data-ttu-id="b343c-142">Выводить журнал во время сбора дампа сборщика мусора.</span><span class="sxs-lookup"><span data-stu-id="b343c-142">Output the log while collecting the GC dump.</span></span>

- **`-t|--timeout <timeout>`**

  <span data-ttu-id="b343c-143">Прервать сбор дампа сборщика мусора, если он занимает больше указанного количества секунд.</span><span class="sxs-lookup"><span data-stu-id="b343c-143">Give up on collecting the GC dump if it takes longer than this many seconds.</span></span> <span data-ttu-id="b343c-144">Значение по умолчанию — 30.</span><span class="sxs-lookup"><span data-stu-id="b343c-144">The default value is 30.</span></span>

- **`-n|--name <name>`**

  <span data-ttu-id="b343c-145">Имя процесса, из которого нужно получить дамп сборщика мусора.</span><span class="sxs-lookup"><span data-stu-id="b343c-145">The name of the process to collect the GC dump from.</span></span>

## `dotnet-gcdump ps`

<span data-ttu-id="b343c-146">Список процессов dotnet, из которых можно получить дамп сборщика мусора.</span><span class="sxs-lookup"><span data-stu-id="b343c-146">Lists the dotnet processes that GC dumps can be collected for.</span></span>

### <a name="synopsis"></a><span data-ttu-id="b343c-147">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="b343c-147">Synopsis</span></span>

```console
dotnet-gcdump ps
```

## `dotnet-gcdump report <gcdump_filename>`

<span data-ttu-id="b343c-148">Создание отчета из ранее созданного дампа сборщика мусора или из выполняющегося процесса и запись его в `stdout`.</span><span class="sxs-lookup"><span data-stu-id="b343c-148">Generate a report from a previously generated GC dump or from a running process, and write to `stdout`.</span></span>

### <a name="synopsis"></a><span data-ttu-id="b343c-149">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="b343c-149">Synopsis</span></span>

```console
dotnet-gcdump report [-h|--help] [-p|--process-id <pid>] [-t|--report-type <HeapStat>]
```

### <a name="options"></a><span data-ttu-id="b343c-150">Параметры</span><span class="sxs-lookup"><span data-stu-id="b343c-150">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="b343c-151">Отображение справки в командной строке.</span><span class="sxs-lookup"><span data-stu-id="b343c-151">Shows command-line help.</span></span>

- **`-p|--process-id <pid>`**

  <span data-ttu-id="b343c-152">Идентификатор процесса, из которого нужно получить дамп сборщика мусора.</span><span class="sxs-lookup"><span data-stu-id="b343c-152">The process ID to collect the GC dump from.</span></span>

- **`-t|--report-type <HeapStat>`**

  <span data-ttu-id="b343c-153">Тип создаваемого отчета.</span><span class="sxs-lookup"><span data-stu-id="b343c-153">The type of report to generate.</span></span> <span data-ttu-id="b343c-154">Доступные значения: heapstat (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="b343c-154">Available options: heapstat (default).</span></span>

## <a name="troubleshoot"></a><span data-ttu-id="b343c-155">Диагностика</span><span class="sxs-lookup"><span data-stu-id="b343c-155">Troubleshoot</span></span>

- <span data-ttu-id="b343c-156">В gcdump нет сведений о типе.</span><span class="sxs-lookup"><span data-stu-id="b343c-156">There is no type information in the gcdump.</span></span>

   <span data-ttu-id="b343c-157">До .NET Core 3.1 существовала проблема, при которой кэш типов не очищался между вызовами gcdump, когда они вызывались с помощью EventPipe.</span><span class="sxs-lookup"><span data-stu-id="b343c-157">Prior to .NET Core 3.1, there was an issue where a type cache was not cleared between gcdumps when they were invoked with EventPipe.</span></span> <span data-ttu-id="b343c-158">Это приводило к тому, что события, необходимые для определения сведений о типе, не отправлялись для второго и последующего вызовов gcdump.</span><span class="sxs-lookup"><span data-stu-id="b343c-158">This resulted in the events needed for determining type information not being sent for the second and subsequent gcdumps.</span></span> <span data-ttu-id="b343c-159">Это было исправлено в версии .NET Core 3.1-preview2.</span><span class="sxs-lookup"><span data-stu-id="b343c-159">This was fixed in .NET Core 3.1-preview2.</span></span>

- <span data-ttu-id="b343c-160">COM и статические типы не содержатся в дампе сборщика мусора.</span><span class="sxs-lookup"><span data-stu-id="b343c-160">COM and static types aren't in the GC dump.</span></span>

   <span data-ttu-id="b343c-161">До .NET Core 3.1-preview2 существовала проблема, при которой COM и статические типы не отправлялись при вызове дампа сборщика мусора через EventPipe.</span><span class="sxs-lookup"><span data-stu-id="b343c-161">Prior to .NET Core 3.1-preview2, there was an issue where static and COM types weren't sent when the GC dump was invoked via EventPipe.</span></span> <span data-ttu-id="b343c-162">Это было исправлено в версии .NET Core 3.1-preview2.</span><span class="sxs-lookup"><span data-stu-id="b343c-162">This has been fixed in .NET Core 3.1-preview2.</span></span>
