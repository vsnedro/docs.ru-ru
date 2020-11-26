---
title: Средство диагностики dotnet-dump — .NET CLI
description: Узнайте, как установить и использовать средство CLI dotnet-dump для накопления и анализа дампов Windows и Linux без использования отладчика машинного кода.
ms.date: 11/17/2020
ms.openlocfilehash: ea9a70c4dc47b5006339e9a197712092eb66b241
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/18/2020
ms.locfileid: "94822208"
---
# <a name="dump-collection-and-analysis-utility-dotnet-dump"></a><span data-ttu-id="a477a-103">Программа для сбора и анализа дампов (dotnet-dump)</span><span class="sxs-lookup"><span data-stu-id="a477a-103">Dump collection and analysis utility (dotnet-dump)</span></span>

<span data-ttu-id="a477a-104">**Эта статья относится к следующему.** ✔️ SDK для .NET Core 3.0 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="a477a-104">**This article applies to:** ✔️ .NET Core 3.0 SDK and later versions</span></span>

> [!NOTE]
> <span data-ttu-id="a477a-105">`dotnet-dump` для macOS поддерживается только в .NET 5.0 и более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="a477a-105">`dotnet-dump` for macOS is only supported with .NET 5.0 and later versions.</span></span>

## <a name="install"></a><span data-ttu-id="a477a-106">Установка</span><span class="sxs-lookup"><span data-stu-id="a477a-106">Install</span></span>

<span data-ttu-id="a477a-107">Есть два способа загрузки и установки `dotnet-dump`:</span><span class="sxs-lookup"><span data-stu-id="a477a-107">There are two ways to download and install `dotnet-dump`:</span></span>

- <span data-ttu-id="a477a-108">**Средство dotnet global:**</span><span class="sxs-lookup"><span data-stu-id="a477a-108">**dotnet global tool:**</span></span>

  <span data-ttu-id="a477a-109">Чтобы установить последнюю версию [пакета NuGet](https://www.nuget.org/packages/dotnet-dump) `dotnet-dump`, используйте команду [dotnet tool install](../tools/dotnet-tool-install.md).</span><span class="sxs-lookup"><span data-stu-id="a477a-109">To install the latest release version of the `dotnet-dump` [NuGet package](https://www.nuget.org/packages/dotnet-dump), use the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

  ```dotnetcli
  dotnet tool install --global dotnet-dump
  ```

- <span data-ttu-id="a477a-110">**Прямое скачивание:**</span><span class="sxs-lookup"><span data-stu-id="a477a-110">**Direct download:**</span></span>

  <span data-ttu-id="a477a-111">скачайте исполняемый файл средства, соответствующий вашей платформе:</span><span class="sxs-lookup"><span data-stu-id="a477a-111">Download the tool executable that matches your platform:</span></span>

  | <span data-ttu-id="a477a-112">OS</span><span class="sxs-lookup"><span data-stu-id="a477a-112">OS</span></span>  | <span data-ttu-id="a477a-113">Платформа</span><span class="sxs-lookup"><span data-stu-id="a477a-113">Platform</span></span> |
  | --- | -------- |
  | <span data-ttu-id="a477a-114">Windows</span><span class="sxs-lookup"><span data-stu-id="a477a-114">Windows</span></span> | <span data-ttu-id="a477a-115">[x86](https://aka.ms/dotnet-dump/win-x86) \| [x64](https://aka.ms/dotnet-dump/win-x64) \| [arm](https://aka.ms/dotnet-dump/win-arm) \| [arm-x64](https://aka.ms/dotnet-dump/win-arm64)</span><span class="sxs-lookup"><span data-stu-id="a477a-115">[x86](https://aka.ms/dotnet-dump/win-x86) \| [x64](https://aka.ms/dotnet-dump/win-x64) \| [arm](https://aka.ms/dotnet-dump/win-arm) \| [arm-x64](https://aka.ms/dotnet-dump/win-arm64)</span></span> |
  | <span data-ttu-id="a477a-116">macOS</span><span class="sxs-lookup"><span data-stu-id="a477a-116">macOS</span></span>   | [<span data-ttu-id="a477a-117">x64</span><span class="sxs-lookup"><span data-stu-id="a477a-117">x64</span></span>](https://aka.ms/dotnet-dump/osx-x64) |
  | <span data-ttu-id="a477a-118">Linux</span><span class="sxs-lookup"><span data-stu-id="a477a-118">Linux</span></span>   | <span data-ttu-id="a477a-119">[x64](https://aka.ms/dotnet-dump/linux-x64) \| [arm](https://aka.ms/dotnet-dump/linux-arm) \| [arm64](https://aka.ms/dotnet-dump/linux-arm64) \| [musl-x64](https://aka.ms/dotnet-dump/linux-musl-x64) \| [musl-arm64](https://aka.ms/dotnet-dump/linux-musl-arm64)</span><span class="sxs-lookup"><span data-stu-id="a477a-119">[x64](https://aka.ms/dotnet-dump/linux-x64) \| [arm](https://aka.ms/dotnet-dump/linux-arm) \| [arm64](https://aka.ms/dotnet-dump/linux-arm64) \| [musl-x64](https://aka.ms/dotnet-dump/linux-musl-x64) \| [musl-arm64](https://aka.ms/dotnet-dump/linux-musl-arm64)</span></span> |

## <a name="synopsis"></a><span data-ttu-id="a477a-120">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="a477a-120">Synopsis</span></span>

```console
dotnet-dump [-h|--help] [--version] <command>
```

## <a name="description"></a><span data-ttu-id="a477a-121">Описание</span><span class="sxs-lookup"><span data-stu-id="a477a-121">Description</span></span>

<span data-ttu-id="a477a-122">`dotnet-dump` — это средство сбора и анализа дампов в Windows и Linux, которое не задействует собственный отладчик системы (как, например, `lldb` в Linux).</span><span class="sxs-lookup"><span data-stu-id="a477a-122">The `dotnet-dump` global tool is a way to collect and analyze Windows and Linux dumps without any native debugger involved like `lldb` on Linux.</span></span> <span data-ttu-id="a477a-123">Это средство имеет важное значение на таких платформах, как Alpine Linux, где отсутствует полноценно работающее средство `lldb`.</span><span class="sxs-lookup"><span data-stu-id="a477a-123">This tool is important on platforms like Alpine Linux where a fully working `lldb` isn't available.</span></span> <span data-ttu-id="a477a-124">Средство `dotnet-dump` позволяет выполнять команды SOS для анализа сбоев и сборщика мусора (GC), но не поддерживает некоторые функции, как, например, отображение собственных кадров стека, потому что не является встроенным отладчиком.</span><span class="sxs-lookup"><span data-stu-id="a477a-124">The `dotnet-dump` tool allows you to run SOS commands to analyze crashes and the garbage collector (GC), but it isn't a native debugger so things like displaying native stack frames aren't supported.</span></span>

## <a name="options"></a><span data-ttu-id="a477a-125">Параметры</span><span class="sxs-lookup"><span data-stu-id="a477a-125">Options</span></span>

- **`--version`**

  <span data-ttu-id="a477a-126">Отображение версии служебной программы dotnet-dump.</span><span class="sxs-lookup"><span data-stu-id="a477a-126">Displays the version of the dotnet-dump utility.</span></span>

- **`-h|--help`**

  <span data-ttu-id="a477a-127">Отображение справки в командной строке.</span><span class="sxs-lookup"><span data-stu-id="a477a-127">Shows command-line help.</span></span>

## <a name="commands"></a><span data-ttu-id="a477a-128">Команды</span><span class="sxs-lookup"><span data-stu-id="a477a-128">Commands</span></span>

| <span data-ttu-id="a477a-129">Команда</span><span class="sxs-lookup"><span data-stu-id="a477a-129">Command</span></span>                                     |
| ------------------------------------------- |
| [<span data-ttu-id="a477a-130">dotnet-dump collect</span><span class="sxs-lookup"><span data-stu-id="a477a-130">dotnet-dump collect</span></span>](#dotnet-dump-collect) |
| [<span data-ttu-id="a477a-131">dotnet-dump analyze</span><span class="sxs-lookup"><span data-stu-id="a477a-131">dotnet-dump analyze</span></span>](#dotnet-dump-analyze) |

## <a name="dotnet-dump-collect"></a><span data-ttu-id="a477a-132">dotnet-dump collect</span><span class="sxs-lookup"><span data-stu-id="a477a-132">dotnet-dump collect</span></span>

<span data-ttu-id="a477a-133">Записывает дамп из процесса.</span><span class="sxs-lookup"><span data-stu-id="a477a-133">Captures a dump from a process.</span></span>

### <a name="synopsis"></a><span data-ttu-id="a477a-134">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="a477a-134">Synopsis</span></span>

```console
dotnet-dump collect [-h|--help] [-p|--process-id] [-n|--name] [--type] [-o|--output] [--diag]
```

### <a name="options"></a><span data-ttu-id="a477a-135">Параметры</span><span class="sxs-lookup"><span data-stu-id="a477a-135">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="a477a-136">Отображение справки в командной строке.</span><span class="sxs-lookup"><span data-stu-id="a477a-136">Shows command-line help.</span></span>

- **`-p|--process-id <PID>`**

  <span data-ttu-id="a477a-137">Указывает идентификатор процесса, из которого нужно собрать дамп.</span><span class="sxs-lookup"><span data-stu-id="a477a-137">Specifies the process ID number to collect a dump from.</span></span>

- **`-n|--name <name>`**

  <span data-ttu-id="a477a-138">Имя процесса, из которого нужно получить дамп.</span><span class="sxs-lookup"><span data-stu-id="a477a-138">Specifies the name of the process to collect a dump from.</span></span>

- **`--type <Full|Heap|Mini>`**

  <span data-ttu-id="a477a-139">Указывает тип дампа, который определяет типы собираемых из процесса данных.</span><span class="sxs-lookup"><span data-stu-id="a477a-139">Specifies the dump type, which determines the kinds of information that are collected from the process.</span></span> <span data-ttu-id="a477a-140">Здесь возможны три варианта:</span><span class="sxs-lookup"><span data-stu-id="a477a-140">There are three types:</span></span>

  - <span data-ttu-id="a477a-141">`Full` — самый крупный дамп, содержащий всю память, включая образы модулей.</span><span class="sxs-lookup"><span data-stu-id="a477a-141">`Full` - The largest dump containing all memory including the module images.</span></span>
  - <span data-ttu-id="a477a-142">`Heap` — большой и сравнительно подробный дамп, который содержит списки модулей, списки потоков, все стеки, сведения об исключениях, сведения об обработке и всю память, за исключением сопоставленных образов.</span><span class="sxs-lookup"><span data-stu-id="a477a-142">`Heap` - A large and relatively comprehensive dump containing module lists, thread lists, all stacks, exception information, handle information, and all memory except for mapped images.</span></span>
  - <span data-ttu-id="a477a-143">`Mini` — небольшой дамп, который содержит списки модулей, списки потоков, сведения об исключениях и все стеки.</span><span class="sxs-lookup"><span data-stu-id="a477a-143">`Mini` - A small dump containing module lists, thread lists, exception information, and all stacks.</span></span>

  <span data-ttu-id="a477a-144">Если тип не указан, по умолчанию используется вариант `Full`.</span><span class="sxs-lookup"><span data-stu-id="a477a-144">If not specified, `Full` is the default.</span></span>

- **`-o|--output <output_dump_path>`**

  <span data-ttu-id="a477a-145">Полный путь и имя файла, в который будет записан собранный дамп.</span><span class="sxs-lookup"><span data-stu-id="a477a-145">The full path and file name where the collected dump should be written.</span></span>

  <span data-ttu-id="a477a-146">Если значение не указано, используются следующие:</span><span class="sxs-lookup"><span data-stu-id="a477a-146">If not specified:</span></span>

  - <span data-ttu-id="a477a-147">*.\dump_YYYYMMDD_HHMMSS.dmp* в ОС Windows;</span><span class="sxs-lookup"><span data-stu-id="a477a-147">Defaults to *.\dump_YYYYMMDD_HHMMSS.dmp* on Windows.</span></span>
  - <span data-ttu-id="a477a-148">*./core_YYYYMMDD_HHMMSS* в ОС Linux.</span><span class="sxs-lookup"><span data-stu-id="a477a-148">Defaults to *./core_YYYYMMDD_HHMMSS* on Linux.</span></span>

  <span data-ttu-id="a477a-149">YYYYMMDD обозначает формат "год/месяц/день", а HHMMSS — формат "час/минута/секунда".</span><span class="sxs-lookup"><span data-stu-id="a477a-149">YYYYMMDD is Year/Month/Day and HHMMSS is Hour/Minute/Second.</span></span>

- **`--diag`**

  <span data-ttu-id="a477a-150">Включает ведение журнала диагностики для сбора дампов.</span><span class="sxs-lookup"><span data-stu-id="a477a-150">Enables dump collection diagnostic logging.</span></span>

## <a name="dotnet-dump-analyze"></a><span data-ttu-id="a477a-151">dotnet-dump analyze</span><span class="sxs-lookup"><span data-stu-id="a477a-151">dotnet-dump analyze</span></span>

<span data-ttu-id="a477a-152">Запускает интерактивную оболочку для просмотра дампа.</span><span class="sxs-lookup"><span data-stu-id="a477a-152">Starts an interactive shell to explore a dump.</span></span> <span data-ttu-id="a477a-153">Эта оболочка принимает различные [команды SOS](#analyze-sos-commands).</span><span class="sxs-lookup"><span data-stu-id="a477a-153">The shell accepts various [SOS commands](#analyze-sos-commands).</span></span>

### <a name="synopsis"></a><span data-ttu-id="a477a-154">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="a477a-154">Synopsis</span></span>

```console
dotnet-dump analyze <dump_path> [-h|--help] [-c|--command]
```

### <a name="arguments"></a><span data-ttu-id="a477a-155">Аргументы</span><span class="sxs-lookup"><span data-stu-id="a477a-155">Arguments</span></span>

- **`<dump_path>`**

  <span data-ttu-id="a477a-156">Указывает путь к анализируемому файлу дампа.</span><span class="sxs-lookup"><span data-stu-id="a477a-156">Specifies the path to the dump file to analyze.</span></span>

### <a name="options"></a><span data-ttu-id="a477a-157">Параметры</span><span class="sxs-lookup"><span data-stu-id="a477a-157">Options</span></span>

- **`-c|--command <debug_command>`**

  <span data-ttu-id="a477a-158">Указывает [команду](#analyze-sos-commands), которую нужно выполнить при запуске оболочки.</span><span class="sxs-lookup"><span data-stu-id="a477a-158">Specifies the [command](#analyze-sos-commands) to run in the shell on start.</span></span>

### <a name="analyze-sos-commands"></a><span data-ttu-id="a477a-159">Анализ команд SOS</span><span class="sxs-lookup"><span data-stu-id="a477a-159">Analyze SOS commands</span></span>

| <span data-ttu-id="a477a-160">Команда</span><span class="sxs-lookup"><span data-stu-id="a477a-160">Command</span></span>                             | <span data-ttu-id="a477a-161">Функция</span><span class="sxs-lookup"><span data-stu-id="a477a-161">Function</span></span>                                                                                      |
| ----------------------------------- | --------------------------------------------------------------------------------------------- |
| `soshelp`                           | <span data-ttu-id="a477a-162">Отображение всех доступных команд.</span><span class="sxs-lookup"><span data-stu-id="a477a-162">Displays all available commands</span></span>                                                               |
| `soshelp|help <command>`            | <span data-ttu-id="a477a-163">Отображение сведений об указанной команде.</span><span class="sxs-lookup"><span data-stu-id="a477a-163">Displays the specified command.</span></span>                                                               |
| `exit|quit`                         | <span data-ttu-id="a477a-164">Выход из интерактивного режима.</span><span class="sxs-lookup"><span data-stu-id="a477a-164">Exits interactive mode.</span></span>                                                                       |
| `clrstack <arguments>`              | <span data-ttu-id="a477a-165">Обеспечивает трассировку стека только для управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="a477a-165">Provides a stack trace of managed code only.</span></span>                                                  |
| `clrthreads <arguments>`            | <span data-ttu-id="a477a-166">Перечисление всех выполняемых управляемых потоков.</span><span class="sxs-lookup"><span data-stu-id="a477a-166">Lists the managed threads running.</span></span>                                                            |
| `dumpasync <arguments>`             | <span data-ttu-id="a477a-167">Отображение информации о машинах асинхронной обработки для кучи со сборкой мусора.</span><span class="sxs-lookup"><span data-stu-id="a477a-167">Displays information about async state machines on the garbage-collected heap.</span></span>                |
| `dumpassembly <arguments>`          | <span data-ttu-id="a477a-168">Отображение сведений о сборке.</span><span class="sxs-lookup"><span data-stu-id="a477a-168">Displays details about an assembly.</span></span>                                                           |
| `dumpclass <arguments>`             | <span data-ttu-id="a477a-169">Отображение сведений о структуре класса EE, размещенной по указанному адресу.</span><span class="sxs-lookup"><span data-stu-id="a477a-169">Displays information about a EE class structure at the specified address.</span></span>                     |
| `dumpdelegate <arguments>`          | <span data-ttu-id="a477a-170">Отображение сведений о делегате.</span><span class="sxs-lookup"><span data-stu-id="a477a-170">Displays information about a delegate.</span></span>                                                        |
| `dumpdomain <arguments>`            | <span data-ttu-id="a477a-171">Отображение сведений обо всех доменах приложений и всех сборках в этих доменах.</span><span class="sxs-lookup"><span data-stu-id="a477a-171">Displays information all the AppDomains and all assemblies within the domains.</span></span>                |
| `dumpheap <arguments>`              | <span data-ttu-id="a477a-172">Отображение сведений о куче со сборкой мусора и статистики сборки мусора по объектам.</span><span class="sxs-lookup"><span data-stu-id="a477a-172">Displays info about the garbage-collected heap and collection statistics about objects.</span></span>       |
| `dumpil <arguments>`                | <span data-ttu-id="a477a-173">Отображает язык CIL, связанный с управляемым методом.</span><span class="sxs-lookup"><span data-stu-id="a477a-173">Displays the Microsoft intermediate language (MSIL) that is associated with a managed method.</span></span> |
| `dumplog <arguments>`               | <span data-ttu-id="a477a-174">Записывает в указанный файл содержимое журнала нагрузок, хранящегося в памяти.</span><span class="sxs-lookup"><span data-stu-id="a477a-174">Writes the contents of an in-memory stress log to the specified file.</span></span>                         |
| `dumpmd <arguments>`                | <span data-ttu-id="a477a-175">Отображение сведений о структуре MethodDesc, которая расположена по указанному адресу.</span><span class="sxs-lookup"><span data-stu-id="a477a-175">Displays information about a MethodDesc structure at the specified address.</span></span>                   |
| `dumpmodule <arguments>`            | <span data-ttu-id="a477a-176">Отображение сведений о структуре модуля EE, который расположен по указанному адресу.</span><span class="sxs-lookup"><span data-stu-id="a477a-176">Displays information about a EE module structure at the specified address.</span></span>                    |
| `dumpmt <arguments>`                | <span data-ttu-id="a477a-177">Отображает сведения о таблице методов, расположенной по указанному адресу.</span><span class="sxs-lookup"><span data-stu-id="a477a-177">Displays information about a method table at the specified address.</span></span>                           |
| `dumpobj <arguments>`               | <span data-ttu-id="a477a-178">Отображение сведений об объекте, который расположен по указанному адресу.</span><span class="sxs-lookup"><span data-stu-id="a477a-178">Displays info about an object at the specified address.</span></span>                                       |
| `dso|dumpstackobjects <arguments>`  | <span data-ttu-id="a477a-179">Отображает все управляемые объекты, обнаруженные в пределах границ текущего стека.</span><span class="sxs-lookup"><span data-stu-id="a477a-179">Displays all managed objects found within the bounds of the current stack.</span></span>                    |
| `eeheap <arguments>`                | <span data-ttu-id="a477a-180">Отображение сведений о памяти процессов, занятой внутренними структурами данных среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="a477a-180">Displays info about process memory consumed by internal runtime data structures.</span></span>              |
| `finalizequeue <arguments>`         | <span data-ttu-id="a477a-181">Отображает все объекты, зарегистрированные для заключительной обработки.</span><span class="sxs-lookup"><span data-stu-id="a477a-181">Displays all objects registered for finalization.</span></span>                                             |
| `gcroot <arguments>`                | <span data-ttu-id="a477a-182">Отображение информации о ссылках (или корневых элементах) объекта, который расположен по указанному адресу.</span><span class="sxs-lookup"><span data-stu-id="a477a-182">Displays info about references (or roots) to an object at the specified address.</span></span>              |
| `gcwhere <arguments>`               | <span data-ttu-id="a477a-183">Отображение расположения переданного аргумента в куче со сборкой мусора.</span><span class="sxs-lookup"><span data-stu-id="a477a-183">Displays the location in the GC heap of the argument passed in.</span></span>                               |
| `ip2md <arguments>`                 | <span data-ttu-id="a477a-184">Отображение структуры MethodDesc, которая расположена по указанному адресу в JIT-коде.</span><span class="sxs-lookup"><span data-stu-id="a477a-184">Displays the MethodDesc structure at the specified address in JIT code.</span></span>                       |
| `histclear <arguments>`             | <span data-ttu-id="a477a-185">Освобождает все ресурсы, используемые семейством команд `hist*`.</span><span class="sxs-lookup"><span data-stu-id="a477a-185">Releases any resources used by the family of `hist*` commands.</span></span>                                |
| `histinit <arguments>`              | <span data-ttu-id="a477a-186">Инициализирует структуры SOS из журнала нагрузки, сохраненного в отлаживаемом объекте.</span><span class="sxs-lookup"><span data-stu-id="a477a-186">Initializes the SOS structures from the stress log saved in the debuggee.</span></span>                     |
| `histobj <arguments>`               | <span data-ttu-id="a477a-187">Отображение перераспределений журнала нагрузок для сборки мусора, связанных с `<arguments>`.</span><span class="sxs-lookup"><span data-stu-id="a477a-187">Displays the garbage collection stress log relocations related to `<arguments>`.</span></span>              |
| `histobjfind <arguments>`           | <span data-ttu-id="a477a-188">Отображает все записи журнала, ссылающиеся на объект по указанному адресу.</span><span class="sxs-lookup"><span data-stu-id="a477a-188">Displays all the log entries that reference an object at the specified address.</span></span>               |
| `histroot <arguments>`              | <span data-ttu-id="a477a-189">Отображает сведения о повышениях и перемещениях указанного корневого элемента.</span><span class="sxs-lookup"><span data-stu-id="a477a-189">Displays information related to both promotions and relocations of the specified root.</span></span>        |
| `lm|modules`                        | <span data-ttu-id="a477a-190">Отображение выполняемых собственных модулей.</span><span class="sxs-lookup"><span data-stu-id="a477a-190">Displays the native modules in the process.</span></span>                                                   |
| `name2ee <arguments>`               | <span data-ttu-id="a477a-191">Отображение структуры MethodTable и структуры EEClass для `<argument>`.</span><span class="sxs-lookup"><span data-stu-id="a477a-191">Displays the MethodTable structure and EEClass structure for the `<argument>`.</span></span>                |
| `pe|printexception <arguments>`     | <span data-ttu-id="a477a-192">Отображение всех объектов, наследуемых от класса Exception, который расположен по адресу `<argument>`.</span><span class="sxs-lookup"><span data-stu-id="a477a-192">Displays any object derived from the Exception class at the address `<argument>`.</span></span>             |
| `setsymbolserver <arguments>`       | <span data-ttu-id="a477a-193">Включение поддержки сервера символов</span><span class="sxs-lookup"><span data-stu-id="a477a-193">Enables the symbol server support</span></span>                                                             |
| `syncblk <arguments>`               | <span data-ttu-id="a477a-194">Отображение сведений о заполнителе SyncBlock.</span><span class="sxs-lookup"><span data-stu-id="a477a-194">Displays the SyncBlock holder info.</span></span>                                                           |
| `threads|setthread <threadid>`      | <span data-ttu-id="a477a-195">Отображение или изменение идентификатора текущего потока для команд SOS.</span><span class="sxs-lookup"><span data-stu-id="a477a-195">Sets or displays the current thread ID for the SOS commands.</span></span>                                  |

## <a name="using-dotnet-dump"></a><span data-ttu-id="a477a-196">Использование `dotnet-dump`</span><span class="sxs-lookup"><span data-stu-id="a477a-196">Using `dotnet-dump`</span></span>

<span data-ttu-id="a477a-197">Первым шагом является сборка дампа.</span><span class="sxs-lookup"><span data-stu-id="a477a-197">The first step is to collect a dump.</span></span> <span data-ttu-id="a477a-198">Этот шаг можно пропустить, если уже создан основной дамп.</span><span class="sxs-lookup"><span data-stu-id="a477a-198">This step can be skipped if a core dump has already been generated.</span></span> <span data-ttu-id="a477a-199">Основные дампы могут создавать как операционная система, так и встроенная в среду выполнения .NET Core [функция создания дампа](https://github.com/dotnet/runtime/blob/master/docs/design/coreclr/botr/xplat-minidump-generation.md).</span><span class="sxs-lookup"><span data-stu-id="a477a-199">The operating system or the .NET Core runtime's built-in [dump generation feature](https://github.com/dotnet/runtime/blob/master/docs/design/coreclr/botr/xplat-minidump-generation.md) can each create core dumps.</span></span>

```console
$ dotnet-dump collect --process-id 1902
Writing minidump to file ./core_20190226_135837
Written 98983936 bytes (24166 pages) to core file
Complete
```

<span data-ttu-id="a477a-200">Теперь запустите анализ основного дампа с помощью команды `analyze`:</span><span class="sxs-lookup"><span data-stu-id="a477a-200">Now analyze the core dump with the `analyze` command:</span></span>

```console
$ dotnet-dump analyze ./core_20190226_135850
Loading core dump: ./core_20190226_135850
Ready to process analysis commands. Type 'help' to list available commands or 'help [command]' to get detailed help on a command.
Type 'quit' or 'exit' to exit the session.
>
```

<span data-ttu-id="a477a-201">Это действие открывает интерактивный сеанс, который принимает команды следующего вида:</span><span class="sxs-lookup"><span data-stu-id="a477a-201">This action brings up an interactive session that accepts commands like:</span></span>

```console
> clrstack
OS Thread Id: 0x573d (0)
    Child SP               IP Call Site
00007FFD28B42C58 00007fb22c1a8ed9 [HelperMethodFrame_PROTECTOBJ: 00007ffd28b42c58] System.RuntimeMethodHandle.InvokeMethod(System.Object, System.Object[], System.Signature, Boolean, Boolean)
00007FFD28B42DD0 00007FB1B1334F67 System.Reflection.RuntimeMethodInfo.Invoke(System.Object, System.Reflection.BindingFlags, System.Reflection.Binder, System.Object[], System.Globalization.CultureInfo) [/root/coreclr/src/mscorlib/src/System/Reflection/RuntimeMethodInfo.cs @ 472]
00007FFD28B42E20 00007FB1B18D33ED SymbolTestApp.Program.Foo4(System.String) [/home/mikem/builds/SymbolTestApp/SymbolTestApp/SymbolTestApp.cs @ 54]
00007FFD28B42ED0 00007FB1B18D2FC4 SymbolTestApp.Program.Foo2(Int32, System.String) [/home/mikem/builds/SymbolTestApp/SymbolTestApp/SymbolTestApp.cs @ 29]
00007FFD28B42F00 00007FB1B18D2F5A SymbolTestApp.Program.Foo1(Int32, System.String) [/home/mikem/builds/SymbolTestApp/SymbolTestApp/SymbolTestApp.cs @ 24]
00007FFD28B42F30 00007FB1B18D168E SymbolTestApp.Program.Main(System.String[]) [/home/mikem/builds/SymbolTestApp/SymbolTestApp/SymbolTestApp.cs @ 19]
00007FFD28B43210 00007fb22aa9cedf [GCFrame: 00007ffd28b43210]
00007FFD28B43610 00007fb22aa9cedf [GCFrame: 00007ffd28b43610]
```

<span data-ttu-id="a477a-202">Чтобы получить сведения о необработанном исключении, которое привело к сбою приложения, выполните:</span><span class="sxs-lookup"><span data-stu-id="a477a-202">To see an unhandled exception that killed your app:</span></span>

```console
> pe -lines
Exception object: 00007fb18c038590
Exception type:   System.Reflection.TargetInvocationException
Message:          Exception has been thrown by the target of an invocation.
InnerException:   System.Exception, Use !PrintException 00007FB18C038368 to see more.
StackTrace (generated):
SP               IP               Function
00007FFD28B42DD0 0000000000000000 System.Private.CoreLib.dll!System.RuntimeMethodHandle.InvokeMethod(System.Object, System.Object[], System.Signature, Boolean, Boolean)
00007FFD28B42DD0 00007FB1B1334F67 System.Private.CoreLib.dll!System.Reflection.RuntimeMethodInfo.Invoke(System.Object, System.Reflection.BindingFlags, System.Reflection.Binder, System.Object[], System.Globalization.CultureInfo)+0xa7 [/root/coreclr/src/mscorlib/src/System/Reflection/RuntimeMethodInfo.cs @ 472]
00007FFD28B42E20 00007FB1B18D33ED SymbolTestApp.dll!SymbolTestApp.Program.Foo4(System.String)+0x15d [/home/mikem/builds/SymbolTestApp/SymbolTestApp/SymbolTestApp.cs @ 54]
00007FFD28B42ED0 00007FB1B18D2FC4 SymbolTestApp.dll!SymbolTestApp.Program.Foo2(Int32, System.String)+0x34 [/home/mikem/builds/SymbolTestApp/SymbolTestApp/SymbolTestApp.cs @ 29]
00007FFD28B42F00 00007FB1B18D2F5A SymbolTestApp.dll!SymbolTestApp.Program.Foo1(Int32, System.String)+0x3a [/home/mikem/builds/SymbolTestApp/SymbolTestApp/SymbolTestApp.cs @ 24]
00007FFD28B42F30 00007FB1B18D168E SymbolTestApp.dll!SymbolTestApp.Program.Main(System.String[])+0x6e [/home/mikem/builds/SymbolTestApp/SymbolTestApp/SymbolTestApp.cs @ 19]

StackTraceString: <none>
HResult: 80131604
```

## <a name="special-instructions-for-docker"></a><span data-ttu-id="a477a-203">Особые инструкции для Docker</span><span class="sxs-lookup"><span data-stu-id="a477a-203">Special instructions for Docker</span></span>

<span data-ttu-id="a477a-204">Если вы используете Docker, для сбора дампа требуются возможности `SYS_PTRACE` (`--cap-add=SYS_PTRACE` или `--privileged`).</span><span class="sxs-lookup"><span data-stu-id="a477a-204">If you're running under Docker, dump collection requires `SYS_PTRACE` capabilities (`--cap-add=SYS_PTRACE` or `--privileged`).</span></span>

<span data-ttu-id="a477a-205">В образах Docker с Linux и пакетом SDK для Microsoft .NET Core некоторые команды `dotnet-dump` могут вызвать следующее исключение:</span><span class="sxs-lookup"><span data-stu-id="a477a-205">On Microsoft .NET Core SDK Linux Docker images, some `dotnet-dump` commands can throw the following exception:</span></span>

> <span data-ttu-id="a477a-206">Unhandled exception: System.DllNotFoundException: Unable to load shared library 'libdl.so' or one of its dependencies' exception. (Необработанное исключение: System.DllNotFoundException: Не удалось загрузить общую библиотеку libdl.so или одну из ее зависимостей.)</span><span class="sxs-lookup"><span data-stu-id="a477a-206">Unhandled exception: System.DllNotFoundException: Unable to load shared library 'libdl.so' or one of its dependencies' exception.</span></span>

<span data-ttu-id="a477a-207">Чтобы обойти эту проблему, установите пакет libc6-dev.</span><span class="sxs-lookup"><span data-stu-id="a477a-207">To work around this problem, install the "libc6-dev" package.</span></span>

## <a name="see-also"></a><span data-ttu-id="a477a-208">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="a477a-208">See also</span></span>

- [<span data-ttu-id="a477a-209">Сбор и анализ блога дампов памяти</span><span class="sxs-lookup"><span data-stu-id="a477a-209">Collecting and analyzing memory dumps blog</span></span>](https://devblogs.microsoft.com/dotnet/collecting-and-analyzing-memory-dumps/)
- [<span data-ttu-id="a477a-210">Средство анализа кучи (dotnet-gcdump)</span><span class="sxs-lookup"><span data-stu-id="a477a-210">Heap analysis tool (dotnet-gcdump)</span></span>](dotnet-gcdump.md)
