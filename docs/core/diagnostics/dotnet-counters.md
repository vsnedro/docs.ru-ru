---
title: Средство диагностики dotnet-counters — .NET CLI
description: Узнайте, как установить и использовать средство CLI dotnet-counter для нерегламентированного мониторинга работоспособности и анализа производительности первого уровня.
ms.date: 11/17/2020
ms.openlocfilehash: 7dd4c06f3abe423552ba1d3eb82f6d0c35a84d0b
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/18/2020
ms.locfileid: "94822221"
---
# <a name="investigate-performance-counters-dotnet-counters"></a><span data-ttu-id="69c81-103">Исследование счетчиков производительности (dotnet-counter)</span><span class="sxs-lookup"><span data-stu-id="69c81-103">Investigate performance counters (dotnet-counters)</span></span>

<span data-ttu-id="69c81-104">**Эта статья относится к следующему.** ✔️ SDK для .NET Core 3.0 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="69c81-104">**This article applies to:** ✔️ .NET Core 3.0 SDK and later versions</span></span>

## <a name="install"></a><span data-ttu-id="69c81-105">Установка</span><span class="sxs-lookup"><span data-stu-id="69c81-105">Install</span></span>

<span data-ttu-id="69c81-106">Есть два способа загрузки и установки `dotnet-counters`:</span><span class="sxs-lookup"><span data-stu-id="69c81-106">There are two ways to download and install `dotnet-counters`:</span></span>

- <span data-ttu-id="69c81-107">**Средство dotnet global:**</span><span class="sxs-lookup"><span data-stu-id="69c81-107">**dotnet global tool:**</span></span>

  <span data-ttu-id="69c81-108">Чтобы установить последнюю версию [пакета NuGet](https://www.nuget.org/packages/dotnet-counters) `dotnet-counters`, используйте команду [dotnet tool install](../tools/dotnet-tool-install.md).</span><span class="sxs-lookup"><span data-stu-id="69c81-108">To install the latest release version of the `dotnet-counters` [NuGet package](https://www.nuget.org/packages/dotnet-counters), use the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

  ```dotnetcli
  dotnet tool install --global dotnet-counters
  ```

- <span data-ttu-id="69c81-109">**Прямое скачивание:**</span><span class="sxs-lookup"><span data-stu-id="69c81-109">**Direct download:**</span></span>

  <span data-ttu-id="69c81-110">скачайте исполняемый файл средства, соответствующий вашей платформе:</span><span class="sxs-lookup"><span data-stu-id="69c81-110">Download the tool executable that matches your platform:</span></span>

  | <span data-ttu-id="69c81-111">OS</span><span class="sxs-lookup"><span data-stu-id="69c81-111">OS</span></span>  | <span data-ttu-id="69c81-112">Платформа</span><span class="sxs-lookup"><span data-stu-id="69c81-112">Platform</span></span> |
  | --- | -------- |
  | <span data-ttu-id="69c81-113">Windows</span><span class="sxs-lookup"><span data-stu-id="69c81-113">Windows</span></span> | <span data-ttu-id="69c81-114">[x86](https://aka.ms/dotnet-counters/win-x86) \| [x64](https://aka.ms/dotnet-counters/win-x64) \| [arm](https://aka.ms/dotnet-counters/win-arm) \| [arm-x64](https://aka.ms/dotnet-counters/win-arm64)</span><span class="sxs-lookup"><span data-stu-id="69c81-114">[x86](https://aka.ms/dotnet-counters/win-x86) \| [x64](https://aka.ms/dotnet-counters/win-x64) \| [arm](https://aka.ms/dotnet-counters/win-arm) \| [arm-x64](https://aka.ms/dotnet-counters/win-arm64)</span></span> |
  | <span data-ttu-id="69c81-115">macOS</span><span class="sxs-lookup"><span data-stu-id="69c81-115">macOS</span></span>   | [<span data-ttu-id="69c81-116">x64</span><span class="sxs-lookup"><span data-stu-id="69c81-116">x64</span></span>](https://aka.ms/dotnet-counters/osx-x64) |
  | <span data-ttu-id="69c81-117">Linux</span><span class="sxs-lookup"><span data-stu-id="69c81-117">Linux</span></span>   | <span data-ttu-id="69c81-118">[x64](https://aka.ms/dotnet-counters/linux-x64) \| [arm](https://aka.ms/dotnet-counters/linux-arm) \| [arm64](https://aka.ms/dotnet-counters/linux-arm64) \| [musl-x64](https://aka.ms/dotnet-counters/linux-musl-x64) \| [musl-arm64](https://aka.ms/dotnet-counters/linux-musl-arm64)</span><span class="sxs-lookup"><span data-stu-id="69c81-118">[x64](https://aka.ms/dotnet-counters/linux-x64) \| [arm](https://aka.ms/dotnet-counters/linux-arm) \| [arm64](https://aka.ms/dotnet-counters/linux-arm64) \| [musl-x64](https://aka.ms/dotnet-counters/linux-musl-x64) \| [musl-arm64](https://aka.ms/dotnet-counters/linux-musl-arm64)</span></span> |

## <a name="synopsis"></a><span data-ttu-id="69c81-119">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="69c81-119">Synopsis</span></span>

```console
dotnet-counters [-h|--help] [--version] <command>
```

## <a name="description"></a><span data-ttu-id="69c81-120">Описание</span><span class="sxs-lookup"><span data-stu-id="69c81-120">Description</span></span>

<span data-ttu-id="69c81-121">`dotnet-counters` — это средство мониторинга производительности и первого уровня анализа производительности.</span><span class="sxs-lookup"><span data-stu-id="69c81-121">`dotnet-counters` is a performance monitoring tool for ad-hoc health monitoring and first-level performance investigation.</span></span> <span data-ttu-id="69c81-122">Оно умеет отслеживать значения счетчиков производительности, опубликованные через API <xref:System.Diagnostics.Tracing.EventCounter>.</span><span class="sxs-lookup"><span data-stu-id="69c81-122">It can observe performance counter values that are published via the <xref:System.Diagnostics.Tracing.EventCounter> API.</span></span> <span data-ttu-id="69c81-123">Например, вы можете быстро отслеживать такие параметры, как загрузка ЦП или частота возникновения исключений в приложении .NET Core, чтобы обнаружить подозрительное поведение перед началом более серьезных расследований с помощью `PerfView` или `dotnet-trace`.</span><span class="sxs-lookup"><span data-stu-id="69c81-123">For example, you can quickly monitor things like the CPU usage or the rate of exceptions being thrown in your .NET Core application to see if there's anything suspicious before diving into more serious performance investigation using `PerfView` or `dotnet-trace`.</span></span>

## <a name="options"></a><span data-ttu-id="69c81-124">Параметры</span><span class="sxs-lookup"><span data-stu-id="69c81-124">Options</span></span>

- **`--version`**

  <span data-ttu-id="69c81-125">Отображение версии служебной программы dotnet-counters.</span><span class="sxs-lookup"><span data-stu-id="69c81-125">Displays the version of the dotnet-counters utility.</span></span>

- **`-h|--help`**

  <span data-ttu-id="69c81-126">Отображение справки в командной строке.</span><span class="sxs-lookup"><span data-stu-id="69c81-126">Shows command-line help.</span></span>

## <a name="commands"></a><span data-ttu-id="69c81-127">Команды</span><span class="sxs-lookup"><span data-stu-id="69c81-127">Commands</span></span>

| <span data-ttu-id="69c81-128">Команда</span><span class="sxs-lookup"><span data-stu-id="69c81-128">Command</span></span>                                             |
|-----------------------------------------------------|
| [<span data-ttu-id="69c81-129">dotnet-counters collect</span><span class="sxs-lookup"><span data-stu-id="69c81-129">dotnet-counters collect</span></span>](#dotnet-counters-collect) |
| [<span data-ttu-id="69c81-130">dotnet-counters list</span><span class="sxs-lookup"><span data-stu-id="69c81-130">dotnet-counters list</span></span>](#dotnet-counters-list)       |
| [<span data-ttu-id="69c81-131">dotnet-counters monitor</span><span class="sxs-lookup"><span data-stu-id="69c81-131">dotnet-counters monitor</span></span>](#dotnet-counters-monitor) |
| [<span data-ttu-id="69c81-132">dotnet-counters ps</span><span class="sxs-lookup"><span data-stu-id="69c81-132">dotnet-counters ps</span></span>](#dotnet-counters-ps)           |

## <a name="dotnet-counters-collect"></a><span data-ttu-id="69c81-133">dotnet-counters collect</span><span class="sxs-lookup"><span data-stu-id="69c81-133">dotnet-counters collect</span></span>

<span data-ttu-id="69c81-134">Периодический сбор выбранных значений счетчиков и их экспорт в указанном формате файла для последующей обработки.</span><span class="sxs-lookup"><span data-stu-id="69c81-134">Periodically collect selected counter values and export them into a specified file format for post-processing.</span></span>

### <a name="synopsis"></a><span data-ttu-id="69c81-135">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="69c81-135">Synopsis</span></span>

```console
dotnet-counters collect [-h|--help] [-p|--process-id] [-n|--name] [--refresh-interval] [--counters <COUNTERS>] [--format] [-o|--output] [-- <command>]
```

### <a name="options"></a><span data-ttu-id="69c81-136">Параметры</span><span class="sxs-lookup"><span data-stu-id="69c81-136">Options</span></span>

- **`-p|--process-id <PID>`**

  <span data-ttu-id="69c81-137">Идентификатор процесса, из которого нужно получить данные счетчика.</span><span class="sxs-lookup"><span data-stu-id="69c81-137">The ID of the process to be collect counter data from.</span></span>

- **`-n|--name <name>`**

  <span data-ttu-id="69c81-138">Имя процесса, из которого нужно получить данные счетчика.</span><span class="sxs-lookup"><span data-stu-id="69c81-138">The name of the process to be collect counter data from.</span></span>

- **`--refresh-interval <SECONDS>`**

  <span data-ttu-id="69c81-139">Время (в секундах) между обновлением значений отображаемых счетчиков</span><span class="sxs-lookup"><span data-stu-id="69c81-139">The number of seconds to delay between updating the displayed counters</span></span>

- **`--counters <COUNTERS>`**

  <span data-ttu-id="69c81-140">Список счетчиков, разделенный запятыми.</span><span class="sxs-lookup"><span data-stu-id="69c81-140">A comma-separated list of counters.</span></span> <span data-ttu-id="69c81-141">Вы можете объявить счетчики как `provider_name[:counter_name]`.</span><span class="sxs-lookup"><span data-stu-id="69c81-141">Counters can be specified `provider_name[:counter_name]`.</span></span> <span data-ttu-id="69c81-142">Если `provider_name` используется без соответствующего списка счетчиков, отображаются все счетчики от поставщика.</span><span class="sxs-lookup"><span data-stu-id="69c81-142">If the `provider_name` is used without a qualifying list of counters, then all counters from the provider are shown.</span></span> <span data-ttu-id="69c81-143">Для обнаружения имен поставщиков и счетчиков используйте команду [dotnet-counters list](#dotnet-counters-list).</span><span class="sxs-lookup"><span data-stu-id="69c81-143">To discover provider and counter names, use the [dotnet-counters list](#dotnet-counters-list) command.</span></span>

- **`--format <csv|json>`**

  <span data-ttu-id="69c81-144">Экспортируемый формат.</span><span class="sxs-lookup"><span data-stu-id="69c81-144">The format to be exported.</span></span> <span data-ttu-id="69c81-145">В настоящее время доступно: csv, json.</span><span class="sxs-lookup"><span data-stu-id="69c81-145">Currently available: csv, json.</span></span>

- **`-o|--output <output>`**

  <span data-ttu-id="69c81-146">Имя выходного файла.</span><span class="sxs-lookup"><span data-stu-id="69c81-146">The name of the output file.</span></span>

- <span data-ttu-id="69c81-147">**`-- <command>` (только для целевых приложений, использующих .NET 5.0 или более поздней версии)**</span><span class="sxs-lookup"><span data-stu-id="69c81-147">**`-- <command>` (for target applications running .NET 5.0 or later only)**</span></span>

  <span data-ttu-id="69c81-148">После параметров конфигурации коллекции пользователь может добавить `--`, а затем команду для запуска приложения .NET с помощью среды выполнения версии не ниже 5.0.</span><span class="sxs-lookup"><span data-stu-id="69c81-148">After the collection configuration parameters, the user can append `--` followed by a command to start a .NET application with at least a 5.0 runtime.</span></span> <span data-ttu-id="69c81-149">`dotnet-counters` запустит процесс с указанной командой и соберет запрошенные метрики.</span><span class="sxs-lookup"><span data-stu-id="69c81-149">`dotnet-counters` will launch a process with the provided command and collect the requested metrics.</span></span> <span data-ttu-id="69c81-150">Это часто бывает полезно для сбора метрик для пути запуска приложения и может использоваться для диагностики и отслеживания проблем, происходящих незадолго до основной точки входа или вскоре после нее.</span><span class="sxs-lookup"><span data-stu-id="69c81-150">This is often useful to collect metrics for the application's startup path and can be used to diagnose or monitor issues that happen early before or shortly after the main entrypoint.</span></span>

  > [!NOTE]
  > <span data-ttu-id="69c81-151">При использовании этого параметра выполняется мониторинг первого процесса .NET 5.0, который передает результаты обратно в средство. Это означает, что если команда запускает несколько приложений .NET, данные будут собираться только о первом приложении.</span><span class="sxs-lookup"><span data-stu-id="69c81-151">Using this option monitors the first .NET 5.0 process that communicates back to the tool, which means if your command launches multiple .NET applications, it will only collect the first app.</span></span> <span data-ttu-id="69c81-152">Поэтому рекомендуется использовать этот параметр для автономных приложений или с помощью параметра `dotnet exec <app.dll>`.</span><span class="sxs-lookup"><span data-stu-id="69c81-152">Therefore, it is recommended you use this option on self-contained applications, or using the `dotnet exec <app.dll>` option.</span></span>

### <a name="examples"></a><span data-ttu-id="69c81-153">Примеры</span><span class="sxs-lookup"><span data-stu-id="69c81-153">Examples</span></span>

- <span data-ttu-id="69c81-154">Сбор всех счетчиков с интервалом обновления в 3 секунды и создание CSV-файла в качестве выходных данных:</span><span class="sxs-lookup"><span data-stu-id="69c81-154">Collect all counters at a refresh interval of 3 seconds and generate a csv as output:</span></span>

  ```console
  > dotnet-counters collect --process-id 1902 --refresh-interval 3 --format csv

  counter_list is unspecified. Monitoring all counters by default.
  Starting a counter session. Press Q to quit.
  ```

- <span data-ttu-id="69c81-155">Запустите `dotnet mvc.dll` как дочерний процесс и начните сбор счетчиков времени выполнения и счетчиков размещения ASP.NET Core из запуска и сохраните их в виде выходных данных JSON:</span><span class="sxs-lookup"><span data-stu-id="69c81-155">Start `dotnet mvc.dll` as a child process and start collecting runtime counters and ASP.NET Core Hosting counters from startup and save it as a JSON output:</span></span>

  ```console
  > dotnet-counters collect --format json --counters System.Runtime,Microsoft.AspNetCore.Hosting -- dotnet mvc.dll
  Starting a counter session. Press Q to quit.
  File saved to counter.json
  ```

## <a name="dotnet-counters-list"></a><span data-ttu-id="69c81-156">dotnet-counters list</span><span class="sxs-lookup"><span data-stu-id="69c81-156">dotnet-counters list</span></span>

<span data-ttu-id="69c81-157">Отображение списка имен и описаний счетчиков, сгруппированных по поставщикам.</span><span class="sxs-lookup"><span data-stu-id="69c81-157">Displays a list of counter names and descriptions, grouped by provider.</span></span>

### <a name="synopsis"></a><span data-ttu-id="69c81-158">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="69c81-158">Synopsis</span></span>

```console
dotnet-counters list [-h|--help]
```

### <a name="example"></a><span data-ttu-id="69c81-159">Пример</span><span class="sxs-lookup"><span data-stu-id="69c81-159">Example</span></span>

```console
> dotnet-counters list
Showing well-known counters only. Specific processes may support additional counters.

System.Runtime
    cpu-usage                                    Amount of time the process has utilized the CPU (ms)
    working-set                                  Amount of working set used by the process (MB)
    gc-heap-size                                 Total heap size reported by the GC (MB)
    gen-0-gc-count                               Number of Gen 0 GCs / min
    gen-1-gc-count                               Number of Gen 1 GCs / min
    gen-2-gc-count                               Number of Gen 2 GCs / min
    time-in-gc                                   % time in GC since the last GC
    gen-0-size                                   Gen 0 Heap Size
    gen-1-size                                   Gen 1 Heap Size
    gen-2-size                                   Gen 2 Heap Size
    loh-size                                     LOH Heap Size
    alloc-rate                                   Allocation Rate
    assembly-count                               Number of Assemblies Loaded
    exception-count                              Number of Exceptions / sec
    threadpool-thread-count                      Number of ThreadPool Threads
    monitor-lock-contention-count                Monitor Lock Contention Count
    threadpool-queue-length                      ThreadPool Work Items Queue Length
    threadpool-completed-items-count             ThreadPool Completed Work Items Count
    active-timer-count                           Active Timers Count

Microsoft.AspNetCore.Hosting
    requests-per-second                  Request rate
    total-requests                       Total number of requests
    current-requests                     Current number of requests
    failed-requests                      Failed number of requests
```

> [!NOTE]
> <span data-ttu-id="69c81-160">Счетчики `Microsoft.AspNetCore.Hosting` отображаются при обнаружении процессов, поддерживающих эти счетчики, например при запуске приложения ASP.NET Core на хост-компьютере.</span><span class="sxs-lookup"><span data-stu-id="69c81-160">The `Microsoft.AspNetCore.Hosting` counters are displayed when there are processes identified that support these counters, for example; when an ASP.NET Core application is running on the host machine.</span></span>

## <a name="dotnet-counters-monitor"></a><span data-ttu-id="69c81-161">dotnet-counters monitor</span><span class="sxs-lookup"><span data-stu-id="69c81-161">dotnet-counters monitor</span></span>

<span data-ttu-id="69c81-162">Отображение периодически обновляемых значений для выбранных счетчиков.</span><span class="sxs-lookup"><span data-stu-id="69c81-162">Displays periodically refreshing values of selected counters.</span></span>

### <a name="synopsis"></a><span data-ttu-id="69c81-163">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="69c81-163">Synopsis</span></span>

```console
dotnet-counters monitor [-h|--help] [-p|--process-id] [-n|--name] [--refresh-interval] [--counters] [-- <command>]
```

### <a name="options"></a><span data-ttu-id="69c81-164">Параметры</span><span class="sxs-lookup"><span data-stu-id="69c81-164">Options</span></span>

- **`-p|--process-id <PID>`**

  <span data-ttu-id="69c81-165">Идентификатор отслеживаемого процесса.</span><span class="sxs-lookup"><span data-stu-id="69c81-165">The ID of the process to be monitored.</span></span>

- **`-n|--name <name>`**

  <span data-ttu-id="69c81-166">Имя отслеживаемого процесса.</span><span class="sxs-lookup"><span data-stu-id="69c81-166">The name of the process to be monitored.</span></span>

- **`--refresh-interval <SECONDS>`**

  <span data-ttu-id="69c81-167">Время (в секундах) между обновлением значений отображаемых счетчиков</span><span class="sxs-lookup"><span data-stu-id="69c81-167">The number of seconds to delay between updating the displayed counters</span></span>

- **`--counters <COUNTERS>`**

  <span data-ttu-id="69c81-168">Список счетчиков, разделенный запятыми.</span><span class="sxs-lookup"><span data-stu-id="69c81-168">A comma-separated list of counters.</span></span> <span data-ttu-id="69c81-169">Вы можете объявить счетчики как `provider_name[:counter_name]`.</span><span class="sxs-lookup"><span data-stu-id="69c81-169">Counters can be specified `provider_name[:counter_name]`.</span></span> <span data-ttu-id="69c81-170">Если `provider_name` используется без соответствующего списка счетчиков, отображаются все счетчики от поставщика.</span><span class="sxs-lookup"><span data-stu-id="69c81-170">If the `provider_name` is used without a qualifying list of counters, then all counters from the provider are shown.</span></span> <span data-ttu-id="69c81-171">Для обнаружения имен поставщиков и счетчиков используйте команду [dotnet-counters list](#dotnet-counters-list).</span><span class="sxs-lookup"><span data-stu-id="69c81-171">To discover provider and counter names, use the [dotnet-counters list](#dotnet-counters-list) command.</span></span>

 <span data-ttu-id="69c81-172">**`-- <command>` (только для целевых приложений, использующих .NET 5.0 или более поздней версии)**</span><span class="sxs-lookup"><span data-stu-id="69c81-172">**`-- <command>` (for target applications running .NET 5.0 or later only)**</span></span>

  <span data-ttu-id="69c81-173">После параметров конфигурации коллекции пользователь может добавить `--`, а затем команду для запуска приложения .NET с помощью среды выполнения версии не ниже 5.0.</span><span class="sxs-lookup"><span data-stu-id="69c81-173">After the collection configuration parameters, the user can append `--` followed by a command to start a .NET application with at least a 5.0 runtime.</span></span> <span data-ttu-id="69c81-174">`dotnet-counters` запустит процесс с указанной командой и будет отслеживать запрошенные метрики.</span><span class="sxs-lookup"><span data-stu-id="69c81-174">`dotnet-counters` will launch a process with the provided command and monitor the requested metrics.</span></span> <span data-ttu-id="69c81-175">Это часто бывает полезно для сбора метрик для пути запуска приложения и может использоваться для диагностики и отслеживания проблем, происходящих незадолго до основной точки входа или вскоре после нее.</span><span class="sxs-lookup"><span data-stu-id="69c81-175">This is often useful to collect metrics for the application's startup path and can be used to diagnose or monitor issues that happen early before or shortly after the main entrypoint.</span></span>

  > [!NOTE]
  > <span data-ttu-id="69c81-176">При использовании этого параметра выполняется мониторинг первого процесса .NET 5.0, который передает результаты обратно в средство. Это означает, что если команда запускает несколько приложений .NET, данные будут собираться только о первом приложении.</span><span class="sxs-lookup"><span data-stu-id="69c81-176">Using this option monitors the first .NET 5.0 process that communicates back to the tool, which means if your command launches multiple .NET applications, it will only collect the first app.</span></span> <span data-ttu-id="69c81-177">Поэтому рекомендуется использовать этот параметр для автономных приложений или с помощью параметра `dotnet exec <app.dll>`.</span><span class="sxs-lookup"><span data-stu-id="69c81-177">Therefore, it is recommended you use this option on self-contained applications, or using the `dotnet exec <app.dll>` option.</span></span>

### <a name="examples"></a><span data-ttu-id="69c81-178">Примеры</span><span class="sxs-lookup"><span data-stu-id="69c81-178">Examples</span></span>

- <span data-ttu-id="69c81-179">Мониторинг всех счетчиков из `System.Runtime` с интервалом обновления 3 секунды:</span><span class="sxs-lookup"><span data-stu-id="69c81-179">Monitor all counters from `System.Runtime` at a refresh interval of 3 seconds:</span></span>

  ```console
  > dotnet-counters monitor --process-id 1902  --refresh-interval 3 --counters System.Runtime
  Press p to pause, r to resume, q to quit.
      Status: Running

  [System.Runtime]
      % Time in GC since last GC (%)                                 0
      Allocation Rate (B / 1 sec)                                5,376
      CPU Usage (%)                                                  0
      Exception Count (Count / 1 sec)                                0
      GC Fragmentation (%)                                          48.467
      GC Heap Size (MB)                                              0
      Gen 0 GC Count (Count / 1 sec)                                 1
      Gen 0 Size (B)                                                24
      Gen 1 GC Count (Count / 1 sec)                                 1
      Gen 1 Size (B)                                                24
      Gen 2 GC Count (Count / 1 sec)                                 1
      Gen 2 Size (B)                                           272,000
      IL Bytes Jitted (B)                                       19,449
      LOH Size (B)                                              19,640
      Monitor Lock Contention Count (Count / 1 sec)                  0
      Number of Active Timers                                        0
      Number of Assemblies Loaded                                    7
      Number of Methods Jitted                                     166
      POH (Pinned Object Heap) Size (B)                             24
      ThreadPool Completed Work Item Count (Count / 1 sec)           0
      ThreadPool Queue Length                                        0
      ThreadPool Thread Count                                        2
      Working Set (MB)                                              19
  ```

- <span data-ttu-id="69c81-180">Мониторинг только счетчиков использования ЦП и размера кучи GC из `System.Runtime`:</span><span class="sxs-lookup"><span data-stu-id="69c81-180">Monitor just CPU usage and GC heap size from `System.Runtime`:</span></span>

  ```console
  > dotnet-counters monitor --process-id 1902 --counters System.Runtime[cpu-usage,gc-heap-size]

  Press p to pause, r to resume, q to quit.
    Status: Running

  [System.Runtime]
      CPU Usage (%)                                 24
      GC Heap Size (MB)                            811
  ```

- <span data-ttu-id="69c81-181">Мониторинг значений `EventCounter` из определяемых пользователем `EventSource`:</span><span class="sxs-lookup"><span data-stu-id="69c81-181">Monitor `EventCounter` values from user-defined `EventSource`.</span></span> <span data-ttu-id="69c81-182">Дополнительные сведения см. в статье [Руководство. Измерение производительности с помощью EventCounters в .NET Core](event-counter-perf.md).</span><span class="sxs-lookup"><span data-stu-id="69c81-182">For more information, see [Tutorial: Measure performance using EventCounters in .NET Core](event-counter-perf.md).</span></span>

  ```console
  > dotnet-counters monitor --process-id 1902 --counters Samples-EventCounterDemos-Minimal

  Press p to pause, r to resume, q to quit.
      request                                      100
  ```

- <span data-ttu-id="69c81-183">Запустите `my-aspnet-server.exe` и отслеживайте число сборок, загруженных при запуске (только для .NET 5.0 или более поздних версий):</span><span class="sxs-lookup"><span data-stu-id="69c81-183">Launch `my-aspnet-server.exe` and monitor the # of assemblies loaded from its startup (.NET 5.0 or later only):</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="69c81-184">Это работает только для приложений, использующих .NET 5.0 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="69c81-184">This works for apps running .NET 5.0 or later only.</span></span>

  ```console
  > dotnet-counters monitor --counters System.Runtime[assembly-count] -- my-aspnet-server.exe

  Press p to pause, r to resume, q to quit.
    Status: Running

  [System.Runtime]
      Number of Assemblies Loaded                   24
  ```
  
- <span data-ttu-id="69c81-185">Запустите `my-aspnet-server.exe` с `arg1` и `arg2` в качестве аргументов командной строки и отслеживайте рабочий набор и размер кучи сборки мусора при запуске (только для .NET 5.0 или более поздней версии):</span><span class="sxs-lookup"><span data-stu-id="69c81-185">Launch `my-aspnet-server.exe` with `arg1` and `arg2` as command-line arguments and monitor its working set and GC heap size from its startup (.NET 5.0 or later only):</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="69c81-186">Это работает только для приложений, использующих .NET 5.0 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="69c81-186">This works for apps running .NET 5.0 or later only.</span></span>

  ```console
  > dotnet-counters monitor --counters System.Runtime[working-set,gc-heap-size] -- my-aspnet-server.exe arg1 arg2
  ```

  ```console
  Press p to pause, r to resume, q to quit.
    Status: Running

  [System.Runtime]
      GC Heap Size (MB)                                 39
      Working Set (MB)                                  59
  ```

## <a name="dotnet-counters-ps"></a><span data-ttu-id="69c81-187">dotnet-counters ps</span><span class="sxs-lookup"><span data-stu-id="69c81-187">dotnet-counters ps</span></span>

<span data-ttu-id="69c81-188">Отображение списка процессов dotnet, которые можно отслеживать.</span><span class="sxs-lookup"><span data-stu-id="69c81-188">Display a list of dotnet processes that can be monitored.</span></span>

### <a name="synopsis"></a><span data-ttu-id="69c81-189">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="69c81-189">Synopsis</span></span>

```console
dotnet-counters ps [-h|--help]
```

### <a name="example"></a><span data-ttu-id="69c81-190">Пример</span><span class="sxs-lookup"><span data-stu-id="69c81-190">Example</span></span>

```console
> dotnet-counters ps
  
  15683 WebApi     /home/suwhang/repos/WebApi/WebApi
  16324 dotnet     /usr/local/share/dotnet/dotnet
```
