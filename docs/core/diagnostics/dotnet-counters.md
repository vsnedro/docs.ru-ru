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
# <a name="investigate-performance-counters-dotnet-counters"></a>Исследование счетчиков производительности (dotnet-counter)

**Эта статья относится к следующему.** ✔️ SDK для .NET Core 3.0 и более поздних версий

## <a name="install"></a>Установка

Есть два способа загрузки и установки `dotnet-counters`:

- **Средство dotnet global:**

  Чтобы установить последнюю версию [пакета NuGet](https://www.nuget.org/packages/dotnet-counters) `dotnet-counters`, используйте команду [dotnet tool install](../tools/dotnet-tool-install.md).

  ```dotnetcli
  dotnet tool install --global dotnet-counters
  ```

- **Прямое скачивание:**

  скачайте исполняемый файл средства, соответствующий вашей платформе:

  | OS  | Платформа |
  | --- | -------- |
  | Windows | [x86](https://aka.ms/dotnet-counters/win-x86) \| [x64](https://aka.ms/dotnet-counters/win-x64) \| [arm](https://aka.ms/dotnet-counters/win-arm) \| [arm-x64](https://aka.ms/dotnet-counters/win-arm64) |
  | macOS   | [x64](https://aka.ms/dotnet-counters/osx-x64) |
  | Linux   | [x64](https://aka.ms/dotnet-counters/linux-x64) \| [arm](https://aka.ms/dotnet-counters/linux-arm) \| [arm64](https://aka.ms/dotnet-counters/linux-arm64) \| [musl-x64](https://aka.ms/dotnet-counters/linux-musl-x64) \| [musl-arm64](https://aka.ms/dotnet-counters/linux-musl-arm64) |

## <a name="synopsis"></a>Краткий обзор

```console
dotnet-counters [-h|--help] [--version] <command>
```

## <a name="description"></a>Описание

`dotnet-counters` — это средство мониторинга производительности и первого уровня анализа производительности. Оно умеет отслеживать значения счетчиков производительности, опубликованные через API <xref:System.Diagnostics.Tracing.EventCounter>. Например, вы можете быстро отслеживать такие параметры, как загрузка ЦП или частота возникновения исключений в приложении .NET Core, чтобы обнаружить подозрительное поведение перед началом более серьезных расследований с помощью `PerfView` или `dotnet-trace`.

## <a name="options"></a>Параметры

- **`--version`**

  Отображение версии служебной программы dotnet-counters.

- **`-h|--help`**

  Отображение справки в командной строке.

## <a name="commands"></a>Команды

| Команда                                             |
|-----------------------------------------------------|
| [dotnet-counters collect](#dotnet-counters-collect) |
| [dotnet-counters list](#dotnet-counters-list)       |
| [dotnet-counters monitor](#dotnet-counters-monitor) |
| [dotnet-counters ps](#dotnet-counters-ps)           |

## <a name="dotnet-counters-collect"></a>dotnet-counters collect

Периодический сбор выбранных значений счетчиков и их экспорт в указанном формате файла для последующей обработки.

### <a name="synopsis"></a>Краткий обзор

```console
dotnet-counters collect [-h|--help] [-p|--process-id] [-n|--name] [--refresh-interval] [--counters <COUNTERS>] [--format] [-o|--output] [-- <command>]
```

### <a name="options"></a>Параметры

- **`-p|--process-id <PID>`**

  Идентификатор процесса, из которого нужно получить данные счетчика.

- **`-n|--name <name>`**

  Имя процесса, из которого нужно получить данные счетчика.

- **`--refresh-interval <SECONDS>`**

  Время (в секундах) между обновлением значений отображаемых счетчиков

- **`--counters <COUNTERS>`**

  Список счетчиков, разделенный запятыми. Вы можете объявить счетчики как `provider_name[:counter_name]`. Если `provider_name` используется без соответствующего списка счетчиков, отображаются все счетчики от поставщика. Для обнаружения имен поставщиков и счетчиков используйте команду [dotnet-counters list](#dotnet-counters-list).

- **`--format <csv|json>`**

  Экспортируемый формат. В настоящее время доступно: csv, json.

- **`-o|--output <output>`**

  Имя выходного файла.

- **`-- <command>` (только для целевых приложений, использующих .NET 5.0 или более поздней версии)**

  После параметров конфигурации коллекции пользователь может добавить `--`, а затем команду для запуска приложения .NET с помощью среды выполнения версии не ниже 5.0. `dotnet-counters` запустит процесс с указанной командой и соберет запрошенные метрики. Это часто бывает полезно для сбора метрик для пути запуска приложения и может использоваться для диагностики и отслеживания проблем, происходящих незадолго до основной точки входа или вскоре после нее.

  > [!NOTE]
  > При использовании этого параметра выполняется мониторинг первого процесса .NET 5.0, который передает результаты обратно в средство. Это означает, что если команда запускает несколько приложений .NET, данные будут собираться только о первом приложении. Поэтому рекомендуется использовать этот параметр для автономных приложений или с помощью параметра `dotnet exec <app.dll>`.

### <a name="examples"></a>Примеры

- Сбор всех счетчиков с интервалом обновления в 3 секунды и создание CSV-файла в качестве выходных данных:

  ```console
  > dotnet-counters collect --process-id 1902 --refresh-interval 3 --format csv

  counter_list is unspecified. Monitoring all counters by default.
  Starting a counter session. Press Q to quit.
  ```

- Запустите `dotnet mvc.dll` как дочерний процесс и начните сбор счетчиков времени выполнения и счетчиков размещения ASP.NET Core из запуска и сохраните их в виде выходных данных JSON:

  ```console
  > dotnet-counters collect --format json --counters System.Runtime,Microsoft.AspNetCore.Hosting -- dotnet mvc.dll
  Starting a counter session. Press Q to quit.
  File saved to counter.json
  ```

## <a name="dotnet-counters-list"></a>dotnet-counters list

Отображение списка имен и описаний счетчиков, сгруппированных по поставщикам.

### <a name="synopsis"></a>Краткий обзор

```console
dotnet-counters list [-h|--help]
```

### <a name="example"></a>Пример

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
> Счетчики `Microsoft.AspNetCore.Hosting` отображаются при обнаружении процессов, поддерживающих эти счетчики, например при запуске приложения ASP.NET Core на хост-компьютере.

## <a name="dotnet-counters-monitor"></a>dotnet-counters monitor

Отображение периодически обновляемых значений для выбранных счетчиков.

### <a name="synopsis"></a>Краткий обзор

```console
dotnet-counters monitor [-h|--help] [-p|--process-id] [-n|--name] [--refresh-interval] [--counters] [-- <command>]
```

### <a name="options"></a>Параметры

- **`-p|--process-id <PID>`**

  Идентификатор отслеживаемого процесса.

- **`-n|--name <name>`**

  Имя отслеживаемого процесса.

- **`--refresh-interval <SECONDS>`**

  Время (в секундах) между обновлением значений отображаемых счетчиков

- **`--counters <COUNTERS>`**

  Список счетчиков, разделенный запятыми. Вы можете объявить счетчики как `provider_name[:counter_name]`. Если `provider_name` используется без соответствующего списка счетчиков, отображаются все счетчики от поставщика. Для обнаружения имен поставщиков и счетчиков используйте команду [dotnet-counters list](#dotnet-counters-list).

 **`-- <command>` (только для целевых приложений, использующих .NET 5.0 или более поздней версии)**

  После параметров конфигурации коллекции пользователь может добавить `--`, а затем команду для запуска приложения .NET с помощью среды выполнения версии не ниже 5.0. `dotnet-counters` запустит процесс с указанной командой и будет отслеживать запрошенные метрики. Это часто бывает полезно для сбора метрик для пути запуска приложения и может использоваться для диагностики и отслеживания проблем, происходящих незадолго до основной точки входа или вскоре после нее.

  > [!NOTE]
  > При использовании этого параметра выполняется мониторинг первого процесса .NET 5.0, который передает результаты обратно в средство. Это означает, что если команда запускает несколько приложений .NET, данные будут собираться только о первом приложении. Поэтому рекомендуется использовать этот параметр для автономных приложений или с помощью параметра `dotnet exec <app.dll>`.

### <a name="examples"></a>Примеры

- Мониторинг всех счетчиков из `System.Runtime` с интервалом обновления 3 секунды:

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

- Мониторинг только счетчиков использования ЦП и размера кучи GC из `System.Runtime`:

  ```console
  > dotnet-counters monitor --process-id 1902 --counters System.Runtime[cpu-usage,gc-heap-size]

  Press p to pause, r to resume, q to quit.
    Status: Running

  [System.Runtime]
      CPU Usage (%)                                 24
      GC Heap Size (MB)                            811
  ```

- Мониторинг значений `EventCounter` из определяемых пользователем `EventSource`: Дополнительные сведения см. в статье [Руководство. Измерение производительности с помощью EventCounters в .NET Core](event-counter-perf.md).

  ```console
  > dotnet-counters monitor --process-id 1902 --counters Samples-EventCounterDemos-Minimal

  Press p to pause, r to resume, q to quit.
      request                                      100
  ```

- Запустите `my-aspnet-server.exe` и отслеживайте число сборок, загруженных при запуске (только для .NET 5.0 или более поздних версий):

  > [!IMPORTANT]
  > Это работает только для приложений, использующих .NET 5.0 или более поздней версии.

  ```console
  > dotnet-counters monitor --counters System.Runtime[assembly-count] -- my-aspnet-server.exe

  Press p to pause, r to resume, q to quit.
    Status: Running

  [System.Runtime]
      Number of Assemblies Loaded                   24
  ```
  
- Запустите `my-aspnet-server.exe` с `arg1` и `arg2` в качестве аргументов командной строки и отслеживайте рабочий набор и размер кучи сборки мусора при запуске (только для .NET 5.0 или более поздней версии):

  > [!IMPORTANT]
  > Это работает только для приложений, использующих .NET 5.0 или более поздней версии.

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

## <a name="dotnet-counters-ps"></a>dotnet-counters ps

Отображение списка процессов dotnet, которые можно отслеживать.

### <a name="synopsis"></a>Краткий обзор

```console
dotnet-counters ps [-h|--help]
```

### <a name="example"></a>Пример

```console
> dotnet-counters ps
  
  15683 WebApi     /home/suwhang/repos/WebApi/WebApi
  16324 dotnet     /usr/local/share/dotnet/dotnet
```
