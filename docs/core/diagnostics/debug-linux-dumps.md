---
title: Отладка дампов Linux
description: В этой статье вы узнаете, как выполнять сбор и анализ дампов из сред Linux.
ms.date: 08/27/2020
ms.openlocfilehash: d62295e165f56e32ef73ab628ca9ebd77a4435d1
ms.sourcegitcommit: 43d5aca3fda42bad8843f6c4e72f6bd52daa55f1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/09/2020
ms.locfileid: "89598306"
---
# <a name="debug-linux-dumps"></a><span data-ttu-id="fef12-103">Отладка дампов Linux</span><span class="sxs-lookup"><span data-stu-id="fef12-103">Debug Linux dumps</span></span>

<span data-ttu-id="fef12-104">**Эта статья относится к:** ✔️ пакету SDK для .NET Core 3.0 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="fef12-104">**This article applies to: ✔️** .NET Core 3.0 SDK and later versions</span></span>

## <a name="collect-dumps-on-linux"></a><span data-ttu-id="fef12-105">Сбор дампов в Linux</span><span class="sxs-lookup"><span data-stu-id="fef12-105">Collect dumps on Linux</span></span>

<span data-ttu-id="fef12-106">Два рекомендуемых способа сбора дампов в Linux — это средства [`dotnet-dump`](dotnet-dump.md) или [`createdump`](https://github.com/dotnet/runtime/blob/master/docs/design/coreclr/botr/xplat-minidump-generation.md).</span><span class="sxs-lookup"><span data-stu-id="fef12-106">The two recommended ways of collecting dumps on Linux are the [`dotnet-dump`](dotnet-dump.md) or [`createdump`](https://github.com/dotnet/runtime/blob/master/docs/design/coreclr/botr/xplat-minidump-generation.md) tools.</span></span>

### <a name="managed-dumps-with-dotnet-dump"></a><span data-ttu-id="fef12-107">Управляемые дампы с помощью `dotnet-dump`</span><span class="sxs-lookup"><span data-stu-id="fef12-107">Managed dumps with `dotnet-dump`</span></span>

<span data-ttu-id="fef12-108">Средство [`dotnet-dump`](dotnet-dump.md) просто в использовании и не зависит от каких-либо отладчиков машинного кода.</span><span class="sxs-lookup"><span data-stu-id="fef12-108">The [`dotnet-dump`](dotnet-dump.md) tool is simple to use, and does not have a dependency on any native debuggers.</span></span> <span data-ttu-id="fef12-109">`dotnet-dump` работает на различных платформах Linux (например, Alpine или ARM32/ARM64), где традиционные средства отладки могут быть недоступны.</span><span class="sxs-lookup"><span data-stu-id="fef12-109">`dotnet-dump` works on a wide variety of Linux platforms (like Alpine or ARM32/ARM64) where traditional debugging tools may not be available.</span></span> <span data-ttu-id="fef12-110">Однако `dotnet-dump` фиксирует только управляемое состояние, поэтому его нельзя использовать для отладки в машинном коде.</span><span class="sxs-lookup"><span data-stu-id="fef12-110">However, `dotnet-dump` only captures managed state so it can't be used for debugging issues in native code.</span></span> <span data-ttu-id="fef12-111">Дампы, собранные `dotnet-dump`, анализируются в среде с той же ОС и архитектурой, в которой был создан дамп.</span><span class="sxs-lookup"><span data-stu-id="fef12-111">Dumps collected by `dotnet-dump` are analyzed in an environment with the the same OS and architecture the dump was created on.</span></span> <span data-ttu-id="fef12-112">Средство [`dotnet-gcdump`](dotnet-gcdump.md) можно использовать в качестве альтернативного варианта, которое фиксирует только сведения о куче GC, но создает дампы, которые можно проанализировать в Windows.</span><span class="sxs-lookup"><span data-stu-id="fef12-112">The [`dotnet-gcdump`](dotnet-gcdump.md) tool can be used as an alternative that only captures GC heap information but produces dumps that can be analyzed on Windows.</span></span>

### <a name="core-dumps-with-createdump"></a><span data-ttu-id="fef12-113">Дампы ядра с помощью `createdump`</span><span class="sxs-lookup"><span data-stu-id="fef12-113">Core dumps with `createdump`</span></span>

<span data-ttu-id="fef12-114">Вместо `dotnet-dump`, создающего только управляемые дампы, [`createdump`](https://github.com/dotnet/runtime/blob/master/docs/design/coreclr/botr/xplat-minidump-generation.md) рекомендуется для создания основных дампов в Linux, содержащих как собственные, так и управляемые данные.</span><span class="sxs-lookup"><span data-stu-id="fef12-114">Alternative to `dotnet-dump` which creates managed-only dumps, [`createdump`](https://github.com/dotnet/runtime/blob/master/docs/design/coreclr/botr/xplat-minidump-generation.md) is the recommended tool for creating core dumps on Linux containing both native and managed information.</span></span> <span data-ttu-id="fef12-115">Другие средства, такие как gdb или gcore, можно также использовать для создания основных дампов, однако они могут не учитывать состояние, необходимое для управляемой отладки, что приводит к неизвестному типу или именам функций во время анализа.</span><span class="sxs-lookup"><span data-stu-id="fef12-115">Other tools like gdb or gcore can also be used to create core dumps but may miss state needed for managed debugging, resulting in "UNKNOWN" type or function names during analysis.</span></span>

<span data-ttu-id="fef12-116">Средства `createdump` устанавливаются вместе со средой выполнения .NET Core. Их можно найти вместе с libcoreclr.so (обычно в папке "/usr/share/dotnet/shared/Microsoft.NETCore.App/[версия]").</span><span class="sxs-lookup"><span data-stu-id="fef12-116">The `createdump` tools is installed with the .NET Core runtime and can be found next to libcoreclr.so (typically in "/usr/share/dotnet/shared/Microsoft.NETCore.App/[version]").</span></span> <span data-ttu-id="fef12-117">Средство использует идентификатор процесса для получения дампа в качестве основного аргумента, а также может принимать необязательные параметры, указывающие, какой тип дампа следует сохранять (по умолчанию используется малый дамп с кучей).</span><span class="sxs-lookup"><span data-stu-id="fef12-117">The tool takes a process ID to collect a dump from as its primary argument and can also take optional parameters specifying what kind of dump to collect (a minidump with heap is the default).</span></span> <span data-ttu-id="fef12-118">Возможны следующие значения.</span><span class="sxs-lookup"><span data-stu-id="fef12-118">Options include:</span></span>

- **`<input-filename>`**

  <span data-ttu-id="fef12-119">Исходный файл трассировки для преобразования.</span><span class="sxs-lookup"><span data-stu-id="fef12-119">Input trace file to be converted.</span></span> <span data-ttu-id="fef12-120">По умолчанию используется значение *trace.nettrace*.</span><span class="sxs-lookup"><span data-stu-id="fef12-120">Defaults to *trace.nettrace*.</span></span>

### <a name="options"></a><span data-ttu-id="fef12-121">Параметры</span><span class="sxs-lookup"><span data-stu-id="fef12-121">Options</span></span>

- **`-f|--name <output-filename>`**

  <span data-ttu-id="fef12-122">Файл, в который записывается дамп.</span><span class="sxs-lookup"><span data-stu-id="fef12-122">The file to write the dump to.</span></span> <span data-ttu-id="fef12-123">Значение по умолчанию — "/tmp/coredump.%p", где % p — это идентификатор целевого процесса.</span><span class="sxs-lookup"><span data-stu-id="fef12-123">Default is '/tmp/coredump.%p' where %p is the process ID of the target process.</span></span>

- **`-n|--normal`**

  <span data-ttu-id="fef12-124">Создание минидампа.</span><span class="sxs-lookup"><span data-stu-id="fef12-124">Create a minidump.</span></span>

- **`-h|--withheap`**

  <span data-ttu-id="fef12-125">Создание минидампа с кучей (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="fef12-125">Create a minidump with heap (default).</span></span>

- **`-t|--triage`**

  <span data-ttu-id="fef12-126">Создание минидампа для рассмотрения.</span><span class="sxs-lookup"><span data-stu-id="fef12-126">Create a triage minidump.</span></span>

- **`-u|--full`**

  <span data-ttu-id="fef12-127">Создайте полного дампа ядра.</span><span class="sxs-lookup"><span data-stu-id="fef12-127">Create a full core dump.</span></span>

- **`-d|--diag`**

  <span data-ttu-id="fef12-128">Включение диагностических сообщений.</span><span class="sxs-lookup"><span data-stu-id="fef12-128">Enable diagnostic messages.</span></span>

<span data-ttu-id="fef12-129">Обратите внимание, что для сбора дампов ядра требуется либо возможность `SYS_PTRACE`, либо `createdump` необходимо запустить с помощью sudo или su.</span><span class="sxs-lookup"><span data-stu-id="fef12-129">Note that collecting core dumps requires either the `SYS_PTRACE` capability or that `createdump` be run with sudo or su.</span></span>

## <a name="analyze-dumps-on-linux"></a><span data-ttu-id="fef12-130">Анализ дампов в Linux</span><span class="sxs-lookup"><span data-stu-id="fef12-130">Analyze dumps on Linux</span></span>

<span data-ttu-id="fef12-131">Как управляемые дампы, собранные с помощью `dotnet-dump`, так и дампы ядра, собранные с помощью `createdump`, можно проанализировать с помощью средства `dotnet-dump`, используя команду `dotnet-dump analyze`.</span><span class="sxs-lookup"><span data-stu-id="fef12-131">Both managed dumps collected with `dotnet-dump` and core dumps collected with `createdump` can be analyzed with the `dotnet-dump` tool using the `dotnet-dump analyze` command.</span></span> <span data-ttu-id="fef12-132">`dotnet dump` требует, чтобы среда, в которой анализируется дамп, использовала ту же ОС и архитектуру, что и среда, в которой был записан дамп.</span><span class="sxs-lookup"><span data-stu-id="fef12-132">The `dotnet dump` requires that the environment analyzing the dump has the same OS and architecture as the environment the dump was captured in.</span></span>

<span data-ttu-id="fef12-133">Кроме того, [LLDB](https://lldb.llvm.org/) можно использовать для анализа основных дампов в Linux, что позволяет выполнять анализ как управляемых, так и собственных кадров.</span><span class="sxs-lookup"><span data-stu-id="fef12-133">Alternatively, [LLDB](https://lldb.llvm.org/) can be used to analyze core dumps on Linux, which allows analysis of both managed and native frames.</span></span> <span data-ttu-id="fef12-134">LLDB использует расширение SOS для отладки управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="fef12-134">LLDB uses the SOS extension to debug managed code.</span></span> <span data-ttu-id="fef12-135">Средство [`dotnet-sos`](dotnet-sos.md) CLI можно использовать для установки SOS, в котором содержится [много полезных команд](https://github.com/dotnet/diagnostics/blob/master/documentation/sos-debugging-extension.md) для отладки управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="fef12-135">The [`dotnet-sos`](dotnet-sos.md) CLI tool can be used to install SOS which has [many useful commands](https://github.com/dotnet/diagnostics/blob/master/documentation/sos-debugging-extension.md) for debugging managed code.</span></span> <span data-ttu-id="fef12-136">Чтобы проанализировать дампы .NET Core, для LLDB и SOS требуются следующие двоичные файлы .NET Core из среды, в которой был создан дамп.</span><span class="sxs-lookup"><span data-stu-id="fef12-136">In order to analyze .NET Core dumps, LLDB and SOS require the following .NET Core binaries from the environment the dump was created in:</span></span>

1. <span data-ttu-id="fef12-137">libmscordaccore.so</span><span class="sxs-lookup"><span data-stu-id="fef12-137">libmscordaccore.so</span></span>
2. <span data-ttu-id="fef12-138">libcoreclr.so</span><span class="sxs-lookup"><span data-stu-id="fef12-138">libcoreclr.so</span></span>
3. <span data-ttu-id="fef12-139">dotnet (узел, используемый для запуска приложения)</span><span class="sxs-lookup"><span data-stu-id="fef12-139">dotnet (the host used to launch the app)</span></span>

<span data-ttu-id="fef12-140">В большинстве случаев эти двоичные файлы можно скачать с помощью средства [`dotnet-symbol`](dotnet-symbol.md).</span><span class="sxs-lookup"><span data-stu-id="fef12-140">In most cases, these binaries can be downloaded using the [`dotnet-symbol`](dotnet-symbol.md) tool.</span></span> <span data-ttu-id="fef12-141">Если необходимые двоичные файлы невозможно загрузить с помощью `dotnet-symbol` (например, если используется частная версия .NET Core, построенная на основе источника), может потребоваться скопировать перечисленные выше файлы из среды, в которой был создан дамп.</span><span class="sxs-lookup"><span data-stu-id="fef12-141">If the necessary binaries can't be downloaded with `dotnet-symbol` (for example, if a private version of .NET Core built from source was in use), it may be necessary to copy the files listed above from the environment the dump was created in.</span></span> <span data-ttu-id="fef12-142">Если файлы не расположены вместе с файлом дампа, можно использовать команду LLDB/SOS `setclrpath <path>`, чтобы задать путь, из которого они должны быть загружены, и `setsymbolserver -directory <path>`, чтобы задать путь для поиска файлов символов.</span><span class="sxs-lookup"><span data-stu-id="fef12-142">If the files aren't located next to the dump file, you can use the LLDB/SOS command `setclrpath <path>` to set the path they should be loaded from and `setsymbolserver -directory <path>` to set the path to look in for symbol files.</span></span>

<span data-ttu-id="fef12-143">После того как необходимые файлы будут доступны, можно загрузить дамп в LLDB, указав узел dotnet в качестве исполняемого файла для отладки:</span><span class="sxs-lookup"><span data-stu-id="fef12-143">Once the necessary files are available, the dump can be loaded in LLDB by specifying the dotnet host as the executable to debug:</span></span>

```console
lldb --core <dump-file> <host-program>
```

<span data-ttu-id="fef12-144">В приведенной выше командной строке `<dump-file>` — это путь к дампу для анализа, а `<host-program>` — это собственная программа, запускающая приложение .NET Core.</span><span class="sxs-lookup"><span data-stu-id="fef12-144">In the above command line, `<dump-file>` is the path of the dump to analyze and `<host-program>` is the native program that started the .NET Core application.</span></span> <span data-ttu-id="fef12-145">Обычно это двоичный файл `dotnet`, если приложение не является автономным. В этом случае это имя приложения без расширения DLL.</span><span class="sxs-lookup"><span data-stu-id="fef12-145">This is typically the `dotnet` binary unless the app is self-contained, in which case it is the name of the application without the dll extension.</span></span>

<span data-ttu-id="fef12-146">После запуска LLDB может потребоваться использовать команду `setsymbolserver`, чтобы указать правильное расположение символов (`setsymbolserver -ms`, чтобы использовать сервер символов корпорации Майкрософт, или `setsymbolserver -directory <path>` для указания локального пути).</span><span class="sxs-lookup"><span data-stu-id="fef12-146">Once LLDB starts, it may be necessary to use the `setsymbolserver` command to point at the correct symbol location (`setsymbolserver -ms` to use Microsoft's symbol server or `setsymbolserver -directory <path>` to specify a local path).</span></span> <span data-ttu-id="fef12-147">Собственные символы можно загрузить, запустив `loadsymbols`.</span><span class="sxs-lookup"><span data-stu-id="fef12-147">Native symbols can be loaded by running `loadsymbols`.</span></span> <span data-ttu-id="fef12-148">На этом этапе для анализа дампа можно использовать [команды SOS](https://github.com/dotnet/diagnostics/blob/master/documentation/sos-debugging-extension.md).</span><span class="sxs-lookup"><span data-stu-id="fef12-148">At this point, [SOS commands](https://github.com/dotnet/diagnostics/blob/master/documentation/sos-debugging-extension.md) can be used to analyze the dump.</span></span>

## <a name="see-also"></a><span data-ttu-id="fef12-149">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="fef12-149">See also</span></span>

- <span data-ttu-id="fef12-150">[dotnet-sos](dotnet-sos.md) для получения дополнительных сведений об установке расширения SOS.</span><span class="sxs-lookup"><span data-stu-id="fef12-150">[dotnet-sos](dotnet-sos.md) for more details on installing the SOS extension.</span></span>
- <span data-ttu-id="fef12-151">[dotnet-symbol](dotnet-symbol.md) для получения дополнительных сведений об установке и использовании средства скачивания символов.</span><span class="sxs-lookup"><span data-stu-id="fef12-151">[dotnet-symbol](dotnet-symbol.md) for more details on installing and using the symbol download tool.</span></span>
- <span data-ttu-id="fef12-152">[Репозиторий диагностики .NET Core](https://github.com/dotnet/diagnostics/blob/master/documentation/) для получения дополнительных сведений об отладке, включая полезные часто задаваемые вопросы.</span><span class="sxs-lookup"><span data-stu-id="fef12-152">[.NET Core diagnostics repo](https://github.com/dotnet/diagnostics/blob/master/documentation/) for more details on debugging, including a useful FAQ.</span></span>
- <span data-ttu-id="fef12-153">[Установка LLDB](https://github.com/dotnet/diagnostics/blob/master/documentation/sos.md#getting-lldb) для получения инструкций по установке LLDB в Linux или Mac.</span><span class="sxs-lookup"><span data-stu-id="fef12-153">[Installing LLDB](https://github.com/dotnet/diagnostics/blob/master/documentation/sos.md#getting-lldb) for instructions on installing LLDB on Linux or Mac.</span></span>
