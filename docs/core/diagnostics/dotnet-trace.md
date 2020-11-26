---
title: Средство диагностики dotnet-trace — .NET CLI
description: Узнайте, как установить и использовать средство CLI dotnet-trace для получения трассировки .NET для запущенного процесса без собственного профилировщика с помощью .NET EventPipe.
ms.date: 11/17/2020
ms.openlocfilehash: d0798e4f703c18c48db47193ac24ec0d13b66ae5
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/18/2020
ms.locfileid: "94829314"
---
# <a name="dotnet-trace-performance-analysis-utility"></a>Программа анализа производительности dotnet-trace

**Эта статья относится к следующему.** ✔️ SDK для .NET Core 3.0 и более поздних версий

## <a name="install"></a>Установка

Есть два способа загрузки и установки `dotnet-trace`:

- **Средство dotnet global:**

  Чтобы установить последнюю версию [пакета NuGet](https://www.nuget.org/packages/dotnet-trace) `dotnet-trace`, используйте команду [dotnet tool install](../tools/dotnet-tool-install.md).

  ```dotnetcli
  dotnet tool install --global dotnet-trace
  ```

- **Прямое скачивание:**

  скачайте исполняемый файл средства, соответствующий вашей платформе:

  | OS  | Платформа |
  | --- | -------- |
  | Windows | [x86](https://aka.ms/dotnet-trace/win-x86) \| [x64](https://aka.ms/dotnet-trace/win-x64) \| [arm](https://aka.ms/dotnet-trace/win-arm) \| [arm-x64](https://aka.ms/dotnet-trace/win-arm64) |
  | macOS   | [x64](https://aka.ms/dotnet-trace/osx-x64) |
  | Linux   | [x64](https://aka.ms/dotnet-trace/linux-x64) \| [arm](https://aka.ms/dotnet-trace/linux-arm) \| [arm64](https://aka.ms/dotnet-trace/linux-arm64) \| [musl-x64](https://aka.ms/dotnet-trace/linux-musl-x64) \| [musl-arm64](https://aka.ms/dotnet-trace/linux-musl-arm64) |

## <a name="synopsis"></a>Краткий обзор

```console
dotnet-trace [-h, --help] [--version] <command>
```

## <a name="description"></a>Описание

Программа `dotnet-trace` —

* это кроссплатформенное средство .NET Core.
* Выполняет сбор трассировок .NET Core для запущенного процесса без встроенного профилировщика.
* Построен на [`EventPipe`](./eventpipe.md) среды выполнения .NET Core.
* Предоставляет одинаковые возможности в Windows, Linux и macOS.

## <a name="options"></a>Параметры

- **`-h|--help`**

  Отображение справки в командной строке.

- **`--version`**

  Отображение версии служебной программы dotnet-trace.

## <a name="commands"></a>Команды

| Команда                                                   |
|-----------------------------------------------------------|
| [dotnet-trace collect](#dotnet-trace-collect)             |
| [dotnet-trace convert](#dotnet-trace-convert)             |
| [dotnet-trace ps](#dotnet-trace-ps)                       |
| [dotnet-trace list-profiles](#dotnet-trace-list-profiles) |

## <a name="dotnet-trace-collect"></a>dotnet-trace collect

Собирает диагностическую трассировку для выполняющегося процесса.

### <a name="synopsis"></a>Краткий обзор

```console
dotnet-trace collect [--buffersize <size>] [--clreventlevel <clreventlevel>] [--clrevents <clrevents>]
    [--format <Chromium|NetTrace|Speedscope>] [-h|--help]
    [-n, --name <name>]  [-o|--output <trace-file-path>] [-p|--process-id <pid>]
    [--profile <profile-name>] [--providers <list-of-comma-separated-providers>]
    [-- <command>] (for target applications running .NET 5.0 or later)
```

### <a name="options"></a>Параметры

- **`--buffersize <size>`**

  Задает размер кольцевого буфера в памяти (в мегабайтах). По умолчанию используется значение 256 МБ.

- **`--clreventlevel <clreventlevel>`**

  Уровень детализации создаваемых событий среды выполнения.

- **`--clrevents <clrevents>`**

  Список вызываемых событий среды выполнения.

- **`--format {Chromium|NetTrace|Speedscope}`**

  Задает формат выходных данных для преобразования файла трассировки. Значение по умолчанию — `NetTrace`.

- **`-n, --name <name>`**

  Имя процесса, из которого нужно получить трассировку.

- **`-o|--output <trace-file-path>`**

  Выходной путь для собранных данных трассировки. Если это значение не указано, по умолчанию используется `trace.nettrace`.

- **`-p|--process-id <PID>`**

  Идентификатор процесса, из которого нужно получить трассировку.

- **`--profile <profile-name>`**

  Заранее определенный именованный набор конфигураций поставщиков, который позволяет кратко указывать типичные сценарии трассировки.

- **`--providers <list-of-comma-separated-providers>`**

  Список применяемых поставщиков `EventPipe`, разделенный запятыми. Поставщики из этого списка применяются в дополнение к тем, которые подразумеваются в `--profile <profile-name>`. При наличии несогласованности по конкретному поставщику указанная здесь конфигурация имеет приоритет над неявной конфигурацией из профиля.

  Список поставщиков предоставляется в следующем формате:

  - `Provider[,Provider]`
  - `Provider` имеет формат `KnownProviderName[:Flags[:Level][:KeyValueArgs]]`;
  - `KeyValueArgs` имеет формат `[key1=value1][;key2=value2]`.

- **`-- <command>` (только для целевых приложений, использующих .NET 5.0)**

  После параметров конфигурации коллекции пользователь может добавить `--`, а затем команду для запуска приложения .NET с помощью среды выполнения версии не ниже 5.0. Это может быть полезно при диагностике проблем, происходящих на ранних этапах процесса, таких как проблема с производительностью при запуске или ошибки загрузчика и модуля привязки.

  > [!NOTE]
  > При использовании этого параметра выполняется мониторинг первого процесса .NET 5.0, который передает результаты обратно в средство. Это означает, что если команда запускает несколько приложений .NET, данные будут собираться только о первом приложении. Поэтому рекомендуется использовать этот параметр для автономных приложений или с помощью параметра `dotnet exec <app.dll>`.

## <a name="dotnet-trace-convert"></a>dotnet-trace convert

Преобразует трассировки `nettrace` в альтернативные форматы для использования с другими средствами анализа трассировок.

### <a name="synopsis"></a>Краткий обзор

```console
dotnet-trace convert [<input-filename>] [--format <Chromium|NetTrace|Speedscope>] [-h|--help] [-o|--output <output-filename>]
```

### <a name="arguments"></a>Аргументы

- **`<input-filename>`**

  Исходный файл трассировки для преобразования. По умолчанию используется значение *trace.nettrace*.

### <a name="options"></a>Параметры

- **`--format <Chromium|NetTrace|Speedscope>`**

  Задает формат выходных данных для преобразования файла трассировки.

- **`-o|--output <output-filename>`**

  Имя файла выходных данных. К нему добавляется расширение целевого формата.

## <a name="dotnet-trace-ps"></a>dotnet-trace ps

 Список процессов dotnet, из которых можно получить трассировку.

### <a name="synopsis"></a>Краткий обзор

```console
dotnet-trace ps [-h|--help]
```

## <a name="dotnet-trace-list-profiles"></a>dotnet-trace list-profiles

Список предварительно созданных профилей трассировки с перечислением поставщиков и фильтров в каждом профиле.

### <a name="synopsis"></a>Краткий обзор

```console
dotnet-trace list-profiles [-h|--help]
```

## <a name="collect-a-trace-with-dotnet-trace"></a>Сбор трассировки с помощью dotnet-trace

Для сбора трассировок с помощью `dotnet-trace` выполните указанные ниже действия.

- Получите идентификатор процесса (PID) для трассируемого приложения .NET Core.

  - В Windows его можно получить, например, через диспетчер задач или с помощью команды `tasklist`.
  - В Linux можно использовать, например, команду `ps`.
  - [dotnet-trace ps](#dotnet-trace-ps)

- Выполните следующую команду:

  ```console
  dotnet-trace collect --process-id <PID>
  ```

  Приведенная выше команда создает выходные данные наподобие следующих:

  ```console
  Press <Enter> to exit...
  Connecting to process: <Full-Path-To-Process-Being-Profiled>/dotnet.exe
  Collecting to file: <Full-Path-To-Trace>/trace.nettrace
  Session Id: <SessionId>
  Recording trace 721.025 (KB)
  ```

- Чтобы остановить сбор, нажмите клавишу `<Enter>`. `dotnet-trace` завершит запись событий в файл *trace.nettrace*.

## <a name="launch-a-child-application-and-collect-a-trace-from-its-startup-using-dotnet-trace"></a>Запуск дочернего приложения и получение трассировки от запуска с помощью dotnet-trace

> [!IMPORTANT]
> Это работает только для приложений, использующих .NET 5.0 или более поздней версии.

Иногда бывает полезно получить трассировку процесса от запуска. Для приложений, использующих .NET 5.0 или более поздней версии, это можно сделать с помощью dotnet-trace.

Это приведет к запуску `hello.exe` с `arg1` и `arg2` в качестве аргументов командной строки и сбору трассировки при запуске среды выполнения:

```console
dotnet-trace collect -- hello.exe arg1 arg2
```

Приведенная выше команда создает выходные данные наподобие следующих:

```console
No profile or providers specified, defaulting to trace profile 'cpu-sampling'

Provider Name                           Keywords            Level               Enabled By
Microsoft-DotNETCore-SampleProfiler     0x0000F00000000000  Informational(4)    --profile
Microsoft-Windows-DotNETRuntime         0x00000014C14FCCBD  Informational(4)    --profile

Process        : E:\temp\gcperfsim\bin\Debug\net5.0\gcperfsim.exe
Output File    : E:\temp\gcperfsim\trace.nettrace


[00:00:00:05]   Recording trace 122.244  (KB)
Press <Enter> or <Ctrl+C> to exit...
```

Вы можете отключить сбор данных трассировки, нажав клавишу `<Enter>` или `<Ctrl + C>`. Это также приведет к выходу из `hello.exe`.

> [!NOTE]
> При запуске `hello.exe` с помощью dotnet-trace выполняется перенаправление входных и выходных данных, и вы не сможете взаимодействовать со стандартным stdin/stdout.
> Выход из средства с помощью клавиш CTRL+C или SIGTERM приведет к безопасному завершению работы средства и дочернего процесса.
> Если дочерний процесс завершает работу до средства, средство также завершит работу, а трассировка будет доступна для безопасного просмотра.

## <a name="view-the-trace-captured-from-dotnet-trace"></a>Просмотр трассировки, собранной с помощью dotnet-trace

В Windows файлы *NETTRACE* можно просматривать и анализировать в [PerfView](https://github.com/microsoft/perfview). Если трассировка была собрана на другой платформе, ее файл можно переместить на компьютер с Windows для просмотра в PerfView.

В Linux трассировку можно просмотреть, изменив формат выходных данных с `dotnet-trace` на `speedscope`. Чтобы изменить формат выходного файла, укажите параметр `-f|--format`. При значении `-f speedscope` программа `dotnet-trace` создаст файл `speedscope`. Вы можете выбрать варианты `nettrace` (по умолчанию) или `speedscope`. Файлы `Speedscope` можно открывать с помощью <https://www.speedscope.app>.

> [!NOTE]
> Среда выполнения .NET Core создает трассировки в формате `nettrace`. В формат speedscope (если требуется) они преобразуются уже после завершения трассировки. Так как некоторые преобразования приводят к потере данных, исходный файл `nettrace` сохраняется рядом с преобразованным файлом.

## <a name="use-dotnet-trace-to-collect-counter-values-over-time"></a>Использование dotnet-trace для получения значений счетчиков за период времени

Программа `dotnet-trace` позволяет выполнять следующие задачи:

* использовать `EventCounter` для простого мониторинга работоспособности в средах с высокой чувствительностью к производительности, например рабочих;
* собирать трассировки, чтобы их не нужно было просматривать в режиме реального времени.

Например, если вам нужны значения счетчика производительности из среды выполнения, используйте следующую команду:

```console
dotnet-trace collect --process-id <PID> --providers System.Runtime:0:1:EventCounterIntervalSec=1
```

Эта команда означает, что счетчики среды выполнения будут отслеживаться каждую секунду, то есть реализует не требовательную к ресурсам схему мониторинга работоспособности. Заменив `EventCounterIntervalSec=1` большим значением (например, 60), вы получите трассировку данных счетчиков меньшего объема и с меньшим уровнем детализации.

Следующая команда сокращает накладные расходы и размер трассировки сильнее, чем предыдущая:

```console
dotnet-trace collect --process-id <PID> --providers System.Runtime:0:1:EventCounterIntervalSec=1,Microsoft-Windows-DotNETRuntime:0:1,Microsoft-DotNETCore-SampleProfiler:0:1
```

Эта команда отключает события среды выполнения и профилировщик управляемого стека.

## <a name="net-providers"></a>Поставщики .NET

Среда выполнения .NET Core поддерживает следующие поставщики .NET. .NET Core использует одинаковые ключевые слова для включения трассировок `Event Tracing for Windows (ETW)` и `EventPipe`.

| Имя поставщика                            | Сведения |
|------------------------------------------|-------------|
| `Microsoft-Windows-DotNETRuntime`        | [Поставщик среды выполнения](../../framework/performance/clr-etw-providers.md#the-runtime-provider)<br>[Ключевые слова среды выполнения CLR](../../framework/performance/clr-etw-keywords-and-levels.md#runtime) |
| `Microsoft-Windows-DotNETRuntimeRundown` | [Поставщик очистки](../../framework/performance/clr-etw-providers.md#the-rundown-provider)<br>[Ключевые слова очистки CLR](../../framework/performance/clr-etw-keywords-and-levels.md#rundown) |
| `Microsoft-DotNETCore-SampleProfiler`    | Включает пример профилировщика. |
