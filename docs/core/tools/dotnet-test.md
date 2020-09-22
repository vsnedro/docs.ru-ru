---
title: Команда dotnet test
description: Команда dotnet test служит для выполнения модульных тестов в проекте.
ms.date: 04/29/2020
ms.openlocfilehash: 5ecfa24905537a663cd967142b765c258495fb22
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90537745"
---
# <a name="dotnet-test"></a><span data-ttu-id="51fe0-103">dotnet test</span><span class="sxs-lookup"><span data-stu-id="51fe0-103">dotnet test</span></span>

<span data-ttu-id="51fe0-104">**Эта статья относится к следующему.** ✔️ SDK для .NET Core 2.1 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="51fe0-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="51fe0-105">name</span><span class="sxs-lookup"><span data-stu-id="51fe0-105">Name</span></span>

<span data-ttu-id="51fe0-106">`dotnet test` — драйвер тестов .NET, используемый для проведения модульных тестов.</span><span class="sxs-lookup"><span data-stu-id="51fe0-106">`dotnet test` - .NET test driver used to execute unit tests.</span></span>

## <a name="synopsis"></a><span data-ttu-id="51fe0-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="51fe0-107">Synopsis</span></span>

```dotnetcli
dotnet test [<PROJECT> | <SOLUTION> | <DIRECTORY> | <DLL>]
    [-a|--test-adapter-path <ADAPTER_PATH>] [--blame] [--blame-crash]
    [--blame-crash-dump-type <DUMP_TYPE>] [--blame-crash-collect-always]
    [--blame-hang] [--blame-hang-dump-type <DUMP_TYPE>]
    [--blame-hang-timeout <TIMESPAN>]
    [-c|--configuration <CONFIGURATION>]
    [--collect <DATA_COLLECTOR_NAME>]
    [-d|--diag <LOG_FILE>] [-f|--framework <FRAMEWORK>]
    [--filter <EXPRESSION>] [--interactive]
    [-l|--logger <LOGGER>] [--no-build]
    [--nologo] [--no-restore] [-o|--output <OUTPUT_DIRECTORY>]
    [-r|--results-directory <RESULTS_DIR>] [--runtime <RUNTIME_IDENTIFIER>]
    [-s|--settings <SETTINGS_FILE>] [-t|--list-tests]
    [-v|--verbosity <LEVEL>] [[--] <RunSettings arguments>]

dotnet test -h|--help
```

## <a name="description"></a><span data-ttu-id="51fe0-108">Описание</span><span class="sxs-lookup"><span data-stu-id="51fe0-108">Description</span></span>

<span data-ttu-id="51fe0-109">Команда `dotnet test` служит для выполнения модульных тестов в решении.</span><span class="sxs-lookup"><span data-stu-id="51fe0-109">The `dotnet test` command is used to execute unit tests in a given solution.</span></span> <span data-ttu-id="51fe0-110">Команда `dotnet test` создает решение и запускает приложение тестового узла для каждого тестового проекта в решении.</span><span class="sxs-lookup"><span data-stu-id="51fe0-110">The `dotnet test` command builds the solution and runs a test host application for each test project in the solution.</span></span> <span data-ttu-id="51fe0-111">Тестовый узел выполняет тесты в заданном проекте с помощью платформы тестирования, например MSTest, NUnit или xUnit, и сообщает об успешном или неуспешном завершении каждого теста.</span><span class="sxs-lookup"><span data-stu-id="51fe0-111">The test host executes tests in the given project using a test framework, for example: MSTest, NUnit, or xUnit, and reports the success or failure of each test.</span></span> <span data-ttu-id="51fe0-112">Если все тесты выполнены успешно, средство выполнения тестов возвращает код 0. Если же любой тест завершается с ошибкой, средство выполнения возвращает 1.</span><span class="sxs-lookup"><span data-stu-id="51fe0-112">If all tests are successful, the test runner returns 0 as an exit code; otherwise if any test fails, it returns 1.</span></span>

<span data-ttu-id="51fe0-113">Для проектов с несколькими целевыми платформами тесты запускаются для каждой из них.</span><span class="sxs-lookup"><span data-stu-id="51fe0-113">For multi-targeted projects, tests are run for each targeted framework.</span></span> <span data-ttu-id="51fe0-114">Тестовый узел и платформа модульных тестов упаковываются в пакеты NuGet и восстанавливаются как обычные зависимости проекта.</span><span class="sxs-lookup"><span data-stu-id="51fe0-114">The test host and the unit test framework are packaged as NuGet packages and are restored as ordinary dependencies for the project.</span></span>

<span data-ttu-id="51fe0-115">Тестовый проект указывает средство выполнения тестов с помощью обычного элемента `<PackageReference>`, как показано в следующем примере файла проекта:</span><span class="sxs-lookup"><span data-stu-id="51fe0-115">Test projects specify the test runner using an ordinary `<PackageReference>` element, as seen in the following sample project file:</span></span>

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

<span data-ttu-id="51fe0-116">Где `Microsoft.NET.Test.Sdk` — это тестовый узел, `xunit` — платформа тестирования.</span><span class="sxs-lookup"><span data-stu-id="51fe0-116">Where `Microsoft.NET.Test.Sdk` is the test host, `xunit` is the test framework.</span></span> <span data-ttu-id="51fe0-117">`xunit.runner.visualstudio` — это адаптер теста, позволяющий платформе xUnit работать с тестовым узлом.</span><span class="sxs-lookup"><span data-stu-id="51fe0-117">And `xunit.runner.visualstudio` is a test adapter, which allows the xUnit framework to work with the test host.</span></span>

### <a name="implicit-restore"></a><span data-ttu-id="51fe0-118">Неявное восстановление</span><span class="sxs-lookup"><span data-stu-id="51fe0-118">Implicit restore</span></span>

[!INCLUDE[dotnet restore note](~/includes/dotnet-restore-note.md)]

## <a name="arguments"></a><span data-ttu-id="51fe0-119">Аргументы</span><span class="sxs-lookup"><span data-stu-id="51fe0-119">Arguments</span></span>

- **`PROJECT | SOLUTION | DIRECTORY | DLL`**

  - <span data-ttu-id="51fe0-120">Путь к тестовому проекту.</span><span class="sxs-lookup"><span data-stu-id="51fe0-120">Path to the test project.</span></span>
  - <span data-ttu-id="51fe0-121">Путь к решению.</span><span class="sxs-lookup"><span data-stu-id="51fe0-121">Path to the solution.</span></span>
  - <span data-ttu-id="51fe0-122">Путь к каталогу, содержащему проект или решение.</span><span class="sxs-lookup"><span data-stu-id="51fe0-122">Path to a directory that contains a project or a solution.</span></span>
  - <span data-ttu-id="51fe0-123">Путь к *DLL-файлу* тестового проекта.</span><span class="sxs-lookup"><span data-stu-id="51fe0-123">Path to a test project *.dll* file.</span></span>

  <span data-ttu-id="51fe0-124">Если он не указан, команда ищет проект или решение в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="51fe0-124">If not specified, it searches for a project or a solution in the current directory.</span></span>

## <a name="options"></a><span data-ttu-id="51fe0-125">Параметры</span><span class="sxs-lookup"><span data-stu-id="51fe0-125">Options</span></span>

- **`-a|--test-adapter-path <ADAPTER_PATH>`**

  <span data-ttu-id="51fe0-126">Путь к каталогу для поиска дополнительных адаптеров теста.</span><span class="sxs-lookup"><span data-stu-id="51fe0-126">Path to a directory to be searched for additional test adapters.</span></span> <span data-ttu-id="51fe0-127">Проверяются только *DLL*-файлы с суффиксом `.TestAdapter.dll`.</span><span class="sxs-lookup"><span data-stu-id="51fe0-127">Only *.dll* files with suffix `.TestAdapter.dll` are inspected.</span></span> <span data-ttu-id="51fe0-128">Если не указано, выполняется поиск по каталогу тестового *DLL*.</span><span class="sxs-lookup"><span data-stu-id="51fe0-128">If not specified, the directory of the test *.dll* is searched.</span></span>

- **`--blame`**

  <span data-ttu-id="51fe0-129">Выполнение тестов в режиме обвинения.</span><span class="sxs-lookup"><span data-stu-id="51fe0-129">Runs the tests in blame mode.</span></span> <span data-ttu-id="51fe0-130">Этот параметр полезен при изоляции проблемных тестов, которые приводят к аварийному завершению хоста для тестов.</span><span class="sxs-lookup"><span data-stu-id="51fe0-130">This option is helpful in isolating problematic tests that cause the test host to crash.</span></span> <span data-ttu-id="51fe0-131">При обнаружении сбоя он создает файл последовательности в `TestResults/<Guid>/<Guid>_Sequence.xml`, который фиксирует порядок тестов, выполненных до сбоя.</span><span class="sxs-lookup"><span data-stu-id="51fe0-131">When a crash is detected, it creates a sequence file in `TestResults/<Guid>/<Guid>_Sequence.xml` that captures the order of tests that were run before the crash.</span></span>

- <span data-ttu-id="51fe0-132">**`--blame-crash`** (Доступно, начиная с выпуска пакета SDK для NET 5.0 предварительной версии)</span><span class="sxs-lookup"><span data-stu-id="51fe0-132">**`--blame-crash`** (Available since .NET 5.0 preview SDK)</span></span>

  <span data-ttu-id="51fe0-133">Выполняет тесты в режиме обвинения и собирает аварийный дамп при непредвиденном завершении процесса хоста для тестов.</span><span class="sxs-lookup"><span data-stu-id="51fe0-133">Runs the tests in blame mode and collects a crash dump when the test host exits unexpectedly.</span></span> <span data-ttu-id="51fe0-134">Эта возможность поддерживается только в Windows.</span><span class="sxs-lookup"><span data-stu-id="51fe0-134">This option is only supported on Windows.</span></span> <span data-ttu-id="51fe0-135">Каталог, содержащий файлы *procdump.exe* и *procdump64.exe*, должен быть включен в переменную среды PATH или PROCDUMP_PATH.</span><span class="sxs-lookup"><span data-stu-id="51fe0-135">A directory that contains *procdump.exe* and *procdump64.exe* must be in the PATH or PROCDUMP_PATH environment variable.</span></span> <span data-ttu-id="51fe0-136">[Скачать средства.](/sysinternals/downloads/procdump)</span><span class="sxs-lookup"><span data-stu-id="51fe0-136">[Download the tools](/sysinternals/downloads/procdump).</span></span> <span data-ttu-id="51fe0-137">Подразумевает `--blame`.</span><span class="sxs-lookup"><span data-stu-id="51fe0-137">Implies `--blame`.</span></span>

- <span data-ttu-id="51fe0-138">**`--blame-crash-dump-type <DUMP_TYPE>`** (Доступно, начиная с выпуска пакета SDK для NET 5.0 предварительной версии)</span><span class="sxs-lookup"><span data-stu-id="51fe0-138">**`--blame-crash-dump-type <DUMP_TYPE>`** (Available since .NET 5.0 preview SDK)</span></span>

  <span data-ttu-id="51fe0-139">Тип собираемого аварийного дампа.</span><span class="sxs-lookup"><span data-stu-id="51fe0-139">The type of crash dump to be collected.</span></span> <span data-ttu-id="51fe0-140">Подразумевает `--blame-crash`.</span><span class="sxs-lookup"><span data-stu-id="51fe0-140">Implies `--blame-crash`.</span></span>

- <span data-ttu-id="51fe0-141">**`--blame-crash-collect-always`** (Доступно, начиная с выпуска пакета SDK для NET 5.0 предварительной версии)</span><span class="sxs-lookup"><span data-stu-id="51fe0-141">**`--blame-crash-collect-always`** (Available since .NET 5.0 preview SDK)</span></span>

  <span data-ttu-id="51fe0-142">Собирает аварийный дамп при ожидаемом и непредвиденном завершении процесса хоста для тестов.</span><span class="sxs-lookup"><span data-stu-id="51fe0-142">Collects a crash dump on expected as well as unexpected test host exit.</span></span>

- <span data-ttu-id="51fe0-143">**`--blame-hang`** (Доступно, начиная с выпуска пакета SDK для NET 5.0 предварительной версии)</span><span class="sxs-lookup"><span data-stu-id="51fe0-143">**`--blame-hang`** (Available since .NET 5.0 preview SDK)</span></span>

  <span data-ttu-id="51fe0-144">Выполняет тесты в режиме обвинения и собирает дамп зависания при превышении тестом заданного времени ожидания.</span><span class="sxs-lookup"><span data-stu-id="51fe0-144">Run the tests in blame mode and collects a hang dump when a test exceeds the given timeout.</span></span>

- <span data-ttu-id="51fe0-145">**`--blame-hang-dump-type <DUMP_TYPE>`** (Доступно, начиная с выпуска пакета SDK для NET 5.0 предварительной версии)</span><span class="sxs-lookup"><span data-stu-id="51fe0-145">**`--blame-hang-dump-type <DUMP_TYPE>`** (Available since .NET 5.0 preview SDK)</span></span>

  <span data-ttu-id="51fe0-146">Тип собираемого аварийного дампа:</span><span class="sxs-lookup"><span data-stu-id="51fe0-146">The type of crash dump to be collected.</span></span> <span data-ttu-id="51fe0-147">`full`, `mini` или `none`.</span><span class="sxs-lookup"><span data-stu-id="51fe0-147">It should be `full`, `mini`, or `none`.</span></span> <span data-ttu-id="51fe0-148">Если указан тип `none`, процесс хоста для тестов завершается по истечении времени ожидания, но дамп не собирается.</span><span class="sxs-lookup"><span data-stu-id="51fe0-148">When `none` is specified, test host is terminated on timeout, but no dump is collected.</span></span> <span data-ttu-id="51fe0-149">Подразумевает `--blame-hang`.</span><span class="sxs-lookup"><span data-stu-id="51fe0-149">Implies `--blame-hang`.</span></span>

- <span data-ttu-id="51fe0-150">**`--blame-hang-timeout <TIMESPAN>`** (Доступно, начиная с выпуска пакета SDK для NET 5.0 предварительной версии)</span><span class="sxs-lookup"><span data-stu-id="51fe0-150">**`--blame-hang-timeout <TIMESPAN>`** (Available since .NET 5.0 preview SDK)</span></span>

  <span data-ttu-id="51fe0-151">Время ожидания каждого теста, после которого дамп зависания активируется и процесс хоста для тестов завершается.</span><span class="sxs-lookup"><span data-stu-id="51fe0-151">Per-test timeout, after which a hang dump is triggered and the test host process is terminated.</span></span> <span data-ttu-id="51fe0-152">Значение времени ожидания указывается в одном из следующих форматов:</span><span class="sxs-lookup"><span data-stu-id="51fe0-152">The timeout value is specified in one of the following formats:</span></span>
  
  - <span data-ttu-id="51fe0-153">1,5 ч</span><span class="sxs-lookup"><span data-stu-id="51fe0-153">1.5h</span></span>
  - <span data-ttu-id="51fe0-154">90 мин</span><span class="sxs-lookup"><span data-stu-id="51fe0-154">90m</span></span>
  - <span data-ttu-id="51fe0-155">5400 с</span><span class="sxs-lookup"><span data-stu-id="51fe0-155">5400s</span></span>
  - <span data-ttu-id="51fe0-156">5 400 000 мс</span><span class="sxs-lookup"><span data-stu-id="51fe0-156">5400000ms</span></span>

  <span data-ttu-id="51fe0-157">Если единица измерения не указана (например, 5 400 000), предполагается, что значение указано в миллисекундах.</span><span class="sxs-lookup"><span data-stu-id="51fe0-157">When no unit is used (for example, 5400000), the value is assumed to be in milliseconds.</span></span> <span data-ttu-id="51fe0-158">При использовании вместе с тестами, управляемыми данными, поведение времени ожидания зависит от используемого адаптера теста.</span><span class="sxs-lookup"><span data-stu-id="51fe0-158">When used together with data driven tests, the timeout behavior depends on the test adapter used.</span></span> <span data-ttu-id="51fe0-159">Для xUnit и NUnit время ожидания обновляется после каждого тестового случая.</span><span class="sxs-lookup"><span data-stu-id="51fe0-159">For xUnit and NUnit the timeout is renewed after every test case.</span></span> <span data-ttu-id="51fe0-160">Для MSTest время ожидания используется для всех тестовых случаев.</span><span class="sxs-lookup"><span data-stu-id="51fe0-160">For MSTest, the timeout is used for all test cases.</span></span> <span data-ttu-id="51fe0-161">Эта возможность поддерживается в Windows с netcoreapp 2.1 и более поздних версий, а также в Linux с netcoreapp 3.1 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="51fe0-161">This option is supported on Windows with netcoreapp2.1 and later, and on Linux with netcoreapp3.1 and later.</span></span> <span data-ttu-id="51fe0-162">macOS не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="51fe0-162">macOS is not supported.</span></span>

- **`-c|--configuration <CONFIGURATION>`**

  <span data-ttu-id="51fe0-163">Определяет конфигурацию сборки.</span><span class="sxs-lookup"><span data-stu-id="51fe0-163">Defines the build configuration.</span></span> <span data-ttu-id="51fe0-164">Значение по умолчанию — `Debug`, но конфигурация проекта может переопределить этот параметр SDK по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="51fe0-164">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

- **`--collect <DATA_COLLECTOR_NAME>`**

  <span data-ttu-id="51fe0-165">Включает сборщик данных для тестового запуска.</span><span class="sxs-lookup"><span data-stu-id="51fe0-165">Enables data collector for the test run.</span></span> <span data-ttu-id="51fe0-166">Дополнительные сведения см. в разделе [Мониторинг и анализ тестового запуска](https://aka.ms/vstest-collect).</span><span class="sxs-lookup"><span data-stu-id="51fe0-166">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>
  
  <span data-ttu-id="51fe0-167">Чтобы получить объем протестированного кода на любой платформе, поддерживаемой .NET Core, установите [Coverlet](https://github.com/coverlet-coverage/coverlet/blob/master/README.md) и используйте параметр `--collect:"XPlat Code Coverage"`.</span><span class="sxs-lookup"><span data-stu-id="51fe0-167">To collect code coverage on any platform that is supported by .NET Core, install [Coverlet](https://github.com/coverlet-coverage/coverlet/blob/master/README.md) and use the `--collect:"XPlat Code Coverage"` option.</span></span>

  <span data-ttu-id="51fe0-168">В Windows объем протестированного кода можно получить с помощью параметра `--collect "Code Coverage"`.</span><span class="sxs-lookup"><span data-stu-id="51fe0-168">On Windows, you can collect code coverage by using the `--collect "Code Coverage"` option.</span></span> <span data-ttu-id="51fe0-169">Этот параметр создает файл *COVERAGE*, который можно открыть в Visual Studio 2019 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="51fe0-169">This option generates a *.coverage* file, which can be opened in Visual Studio 2019 Enterprise.</span></span> <span data-ttu-id="51fe0-170">Дополнительные сведения см. в статьях [Использование объема протестированного кода](/visualstudio/test/using-code-coverage-to-determine-how-much-code-is-being-tested) и [Настройка анализа объема протестированного кода](/visualstudio/test/customizing-code-coverage-analysis).</span><span class="sxs-lookup"><span data-stu-id="51fe0-170">For more information, see [Use code coverage](/visualstudio/test/using-code-coverage-to-determine-how-much-code-is-being-tested) and [Customize code coverage analysis](/visualstudio/test/customizing-code-coverage-analysis).</span></span>

- **`-d|--diag <LOG_FILE>`**

  <span data-ttu-id="51fe0-171">Включает режим диагностики для платформы тестирования и записывает диагностические сообщения в указанный файл и в файлы рядом с ним.</span><span class="sxs-lookup"><span data-stu-id="51fe0-171">Enables diagnostic mode for the test platform and writes diagnostic messages to the specified file and to files next to it.</span></span> <span data-ttu-id="51fe0-172">Процесс, который заносит сообщения в журнал, определяет, какие файлы создаются, например `*.host_<date>.txt` для журнала тестового узла и `*.datacollector_<date>.txt` для журнала сборщика данных.</span><span class="sxs-lookup"><span data-stu-id="51fe0-172">The process that is logging the messages determines which files are created, such as `*.host_<date>.txt` for test host log, and `*.datacollector_<date>.txt` for data collector log.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="51fe0-173">Определяет принудительное использование `dotnet` или тестового узла .NET Framework для двоичных файлов теста.</span><span class="sxs-lookup"><span data-stu-id="51fe0-173">Forces the use of `dotnet` or .NET Framework test host for the test binaries.</span></span> <span data-ttu-id="51fe0-174">Этот параметр определяет только используемый тип узла.</span><span class="sxs-lookup"><span data-stu-id="51fe0-174">This option only determines which type of host to use.</span></span> <span data-ttu-id="51fe0-175">Реальная используемая версия платформы определяется в файле *runtimeconfig.json* тестового проекта.</span><span class="sxs-lookup"><span data-stu-id="51fe0-175">The actual framework version to be used is determined by the *runtimeconfig.json* of the test project.</span></span> <span data-ttu-id="51fe0-176">Если этот параметр не указан, для определения типа узла используется [атрибут сборки TargetFramework](/dotnet/api/system.runtime.versioning.targetframeworkattribute).</span><span class="sxs-lookup"><span data-stu-id="51fe0-176">When not specified, the [TargetFramework assembly attribute](/dotnet/api/system.runtime.versioning.targetframeworkattribute) is used to determine the type of host.</span></span> <span data-ttu-id="51fe0-177">Если этот атрибут удален из *DLL*, используется узел .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="51fe0-177">When that attribute is stripped from the *.dll*, the .NET Framework host is used.</span></span>

- **`--filter <EXPRESSION>`**

  <span data-ttu-id="51fe0-178">Фильтрует тесты в текущем проекте с помощью заданного выражения.</span><span class="sxs-lookup"><span data-stu-id="51fe0-178">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="51fe0-179">Дополнительные сведения см. в разделе [Сведения о параметре "Фильтр"](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="51fe0-179">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="51fe0-180">Дополнительные сведения и примеры использования фильтрации при выборочном модульном тестировании см. в статье [Выполнение выборочных модульных тестов](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="51fe0-180">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

- **`-h|--help`**

  <span data-ttu-id="51fe0-181">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="51fe0-181">Prints out a short help for the command.</span></span>

- **`--interactive`**

  <span data-ttu-id="51fe0-182">Позволяет команде остановиться и дождаться, пока пользователь выполнит действие или введет данные.</span><span class="sxs-lookup"><span data-stu-id="51fe0-182">Allows the command to stop and wait for user input or action.</span></span> <span data-ttu-id="51fe0-183">Например, чтобы завершить проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="51fe0-183">For example, to complete authentication.</span></span> <span data-ttu-id="51fe0-184">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="51fe0-184">Available since .NET Core 3.0 SDK.</span></span>

- **`-l|--logger <LOGGER>`**

  <span data-ttu-id="51fe0-185">Указывает средство ведения журнала для результатов тестирования.</span><span class="sxs-lookup"><span data-stu-id="51fe0-185">Specifies a logger for test results.</span></span> <span data-ttu-id="51fe0-186">В отличие от MSBuild, dotnet test не принимает аббревиатуры: вместо `-l "console;v=d"` используйте `-l "console;verbosity=detailed"`.</span><span class="sxs-lookup"><span data-stu-id="51fe0-186">Unlike MSBuild, dotnet test doesn't accept abbreviations: instead of `-l "console;v=d"` use `-l "console;verbosity=detailed"`.</span></span>

- **`--no-build`**

  <span data-ttu-id="51fe0-187">Не выполняет сборку тестового проекта перед запуском.</span><span class="sxs-lookup"><span data-stu-id="51fe0-187">Doesn't build the test project before running it.</span></span> <span data-ttu-id="51fe0-188">Он также неявно задает флаг `--no-restore`.</span><span class="sxs-lookup"><span data-stu-id="51fe0-188">It also implicitly sets the - `--no-restore` flag.</span></span>

- **`--nologo`**

  <span data-ttu-id="51fe0-189">Запуск тестов без отображения баннера TestPlatform Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="51fe0-189">Run tests without displaying the Microsoft TestPlatform banner.</span></span> <span data-ttu-id="51fe0-190">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="51fe0-190">Available since .NET Core 3.0 SDK.</span></span>

- **`--no-restore`**

  <span data-ttu-id="51fe0-191">Не выполняет неявное восстановление при выполнении команды.</span><span class="sxs-lookup"><span data-stu-id="51fe0-191">Doesn't execute an implicit restore when running the command.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="51fe0-192">Каталог, в котором выполняется поиск двоичных файлов для выполнения.</span><span class="sxs-lookup"><span data-stu-id="51fe0-192">Directory in which to find the binaries to run.</span></span> <span data-ttu-id="51fe0-193">Если значение не указано, путь по умолчанию — `./bin/<configuration>/<framework>/`.</span><span class="sxs-lookup"><span data-stu-id="51fe0-193">If not specified, the default path is `./bin/<configuration>/<framework>/`.</span></span>  <span data-ttu-id="51fe0-194">Для проектов с несколькими целевыми платформами (с помощью свойства `TargetFrameworks`) необходимо также определить `--framework` при указании этого параметра.</span><span class="sxs-lookup"><span data-stu-id="51fe0-194">For projects with multiple target frameworks (via the `TargetFrameworks` property), you also need to define `--framework` when you specify this option.</span></span> <span data-ttu-id="51fe0-195">`dotnet test` всегда запускает тесты из выходного каталога.</span><span class="sxs-lookup"><span data-stu-id="51fe0-195">`dotnet test` always runs tests from the output directory.</span></span> <span data-ttu-id="51fe0-196">Для использования ресурсов тестирования в выходном каталоге можно использовать <xref:System.AppDomain.BaseDirectory%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="51fe0-196">You can use <xref:System.AppDomain.BaseDirectory%2A?displayProperty=nameWithType> to consume test assets in the output directory.</span></span>

- **`-r|--results-directory <RESULTS_DIR>`**

  <span data-ttu-id="51fe0-197">Каталог для сохранения результатов тестов.</span><span class="sxs-lookup"><span data-stu-id="51fe0-197">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="51fe0-198">Если указанный каталог не существует, он создается.</span><span class="sxs-lookup"><span data-stu-id="51fe0-198">If the specified directory doesn't exist, it's created.</span></span> <span data-ttu-id="51fe0-199">По умолчанию используется `TestResults` в каталоге, содержащем файл проекта.</span><span class="sxs-lookup"><span data-stu-id="51fe0-199">The default is `TestResults` in the directory that contains the project file.</span></span>

- **`--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="51fe0-200">Целевая среда выполнения для тестирования.</span><span class="sxs-lookup"><span data-stu-id="51fe0-200">The target runtime to test for.</span></span>

- **`-s|--settings <SETTINGS_FILE>`**

  <span data-ttu-id="51fe0-201">Файл `.runsettings`, который необходимо использовать для проведения тестов.</span><span class="sxs-lookup"><span data-stu-id="51fe0-201">The `.runsettings` file to use for running the tests.</span></span> <span data-ttu-id="51fe0-202">Элемент `TargetPlatform` (x86|x64) не влияет на `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="51fe0-202">The `TargetPlatform` element (x86|x64) has no effect for `dotnet test`.</span></span> <span data-ttu-id="51fe0-203">Чтобы запускать тесты для x86, установите версию .NET Core x86.</span><span class="sxs-lookup"><span data-stu-id="51fe0-203">To run tests that target x86, install the x86 version of .NET Core.</span></span> <span data-ttu-id="51fe0-204">Разрядность *dotnet.exe* в пути будет использоваться для выполнения тестов.</span><span class="sxs-lookup"><span data-stu-id="51fe0-204">The bitness of the *dotnet.exe* that is on the path is what will be used for running tests.</span></span> <span data-ttu-id="51fe0-205">Дополнительные сведения см. в следующих ресурсах:</span><span class="sxs-lookup"><span data-stu-id="51fe0-205">For more information, see the following resources:</span></span>

  - [<span data-ttu-id="51fe0-206">Настройка модульных тестов с помощью файла `.runsettings`.</span><span class="sxs-lookup"><span data-stu-id="51fe0-206">Configure unit tests by using a `.runsettings` file.</span></span>](/visualstudio/test/configure-unit-tests-by-using-a-dot-runsettings-file)
  - [<span data-ttu-id="51fe0-207">Настройка тестового запуска</span><span class="sxs-lookup"><span data-stu-id="51fe0-207">Configure a test run</span></span>](https://github.com/Microsoft/vstest-docs/blob/master/docs/configure.md)

- **`-t|--list-tests`**

  <span data-ttu-id="51fe0-208">Вывод списка обнаруженных тестов вместо выполнения тестов.</span><span class="sxs-lookup"><span data-stu-id="51fe0-208">List the discovered tests instead of running the tests.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="51fe0-209">Задает уровень детализации команды.</span><span class="sxs-lookup"><span data-stu-id="51fe0-209">Sets the verbosity level of the command.</span></span> <span data-ttu-id="51fe0-210">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="51fe0-210">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="51fe0-211">Значение по умолчанию — `minimal`.</span><span class="sxs-lookup"><span data-stu-id="51fe0-211">The default is `minimal`.</span></span> <span data-ttu-id="51fe0-212">Для получения дополнительной информации см. <xref:Microsoft.Build.Framework.LoggerVerbosity>.</span><span class="sxs-lookup"><span data-stu-id="51fe0-212">For more information, see <xref:Microsoft.Build.Framework.LoggerVerbosity>.</span></span>

- <span data-ttu-id="51fe0-213">Аргументы **`RunSettings`**</span><span class="sxs-lookup"><span data-stu-id="51fe0-213">**`RunSettings`** arguments</span></span>

 <span data-ttu-id="51fe0-214">Встроенные `RunSettings` передаются как последние аргументы в командной строке после "-- " (обратите внимание на пробел после "--").</span><span class="sxs-lookup"><span data-stu-id="51fe0-214">Inline `RunSettings` are passed as the last arguments on the command line after "-- " (note the space after --).</span></span> <span data-ttu-id="51fe0-215">Встроенные `RunSettings` указываются как пары `[name]=[value]`.</span><span class="sxs-lookup"><span data-stu-id="51fe0-215">Inline `RunSettings` are specified as `[name]=[value]` pairs.</span></span> <span data-ttu-id="51fe0-216">Несколько пар `[name]=[value]` разделяются пробелами.</span><span class="sxs-lookup"><span data-stu-id="51fe0-216">A space is used to separate multiple `[name]=[value]` pairs.</span></span>

  <span data-ttu-id="51fe0-217">Пример: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span><span class="sxs-lookup"><span data-stu-id="51fe0-217">Example: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span></span>

  <span data-ttu-id="51fe0-218">Дополнительные сведения см. в статье о [передаче аргументов RunSettings с помощью командной строки](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md).</span><span class="sxs-lookup"><span data-stu-id="51fe0-218">For more information, see [Passing RunSettings arguments through command line](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md).</span></span>

## <a name="examples"></a><span data-ttu-id="51fe0-219">Примеры</span><span class="sxs-lookup"><span data-stu-id="51fe0-219">Examples</span></span>

- <span data-ttu-id="51fe0-220">Выполнение тестов в проекте в текущем каталоге:</span><span class="sxs-lookup"><span data-stu-id="51fe0-220">Run the tests in the project in the current directory:</span></span>

  ```dotnetcli
  dotnet test
  ```

- <span data-ttu-id="51fe0-221">Выполнение тестов в проекте `test1`:</span><span class="sxs-lookup"><span data-stu-id="51fe0-221">Run the tests in the `test1` project:</span></span>

  ```dotnetcli
  dotnet test ~/projects/test1/test1.csproj
  ```

- <span data-ttu-id="51fe0-222">Выполнение тестов в проекте в текущем каталоге и создание файла результатов теста в формате TRX:</span><span class="sxs-lookup"><span data-stu-id="51fe0-222">Run the tests in the project in the current directory, and generate a test results file in the trx format:</span></span>

  ```dotnetcli
  dotnet test --logger trx
  ```

- <span data-ttu-id="51fe0-223">Выполнение тестов в проекте в текущем каталоге и создание файла с объемом протестированного кода (после установки интеграции сборщиков [Coverlet](https://github.com/coverlet-coverage/coverlet/blob/master/Documentation/VSTestIntegration.md)):</span><span class="sxs-lookup"><span data-stu-id="51fe0-223">Run the tests in the project in the current directory, and generate a code coverage file (after installing [Coverlet](https://github.com/coverlet-coverage/coverlet/blob/master/Documentation/VSTestIntegration.md) collectors integration):</span></span>

  ```dotnetcli
  dotnet test --collect:"XPlat Code Coverage"
  ```

- <span data-ttu-id="51fe0-224">Выполнение тестов в проекте в текущем каталоге и создание файла с объемом протестированного кода (только Windows):</span><span class="sxs-lookup"><span data-stu-id="51fe0-224">Run the tests in the project in the current directory, and generate a code coverage file (Windows only):</span></span>

  ```dotnetcli
  dotnet test --collect "Code Coverage"
  ```

- <span data-ttu-id="51fe0-225">Выполнение тестов в проекте в текущем каталоге и вывод журнала с подробными сведениями в консоль:</span><span class="sxs-lookup"><span data-stu-id="51fe0-225">Run the tests in the project in the current directory, and log with detailed verbosity to the console:</span></span>

  ```dotnetcli
  dotnet test --logger "console;verbosity=detailed"
  ```

- <span data-ttu-id="51fe0-226">Выполнение тестов в проекте в текущем каталоге и тестов отчетов, которые выполнялись при сбое узла тестирования:</span><span class="sxs-lookup"><span data-stu-id="51fe0-226">Run the tests in the project in the current directory, and report tests that were in progress when the test host crashed:</span></span>

  ```dotnetcli
  dotnet test --blame
  ```

## <a name="filter-option-details"></a><span data-ttu-id="51fe0-227">Сведения о параметре "Фильтр"</span><span class="sxs-lookup"><span data-stu-id="51fe0-227">Filter option details</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="51fe0-228">Параметр `<Expression>` имеет следующий формат: `<property><operator><value>[|&<Expression>]`.</span><span class="sxs-lookup"><span data-stu-id="51fe0-228">`<Expression>` has the format `<property><operator><value>[|&<Expression>]`.</span></span>

<span data-ttu-id="51fe0-229">`<property>` — это атрибут `Test Case`.</span><span class="sxs-lookup"><span data-stu-id="51fe0-229">`<property>` is an attribute of the `Test Case`.</span></span> <span data-ttu-id="51fe0-230">Ниже приведены свойства, поддерживаемые популярными платформами модульных тестов.</span><span class="sxs-lookup"><span data-stu-id="51fe0-230">The following are the properties supported by popular unit test frameworks:</span></span>

| <span data-ttu-id="51fe0-231">Тестовая платформа</span><span class="sxs-lookup"><span data-stu-id="51fe0-231">Test Framework</span></span> | <span data-ttu-id="51fe0-232">Поддерживаемые свойства</span><span class="sxs-lookup"><span data-stu-id="51fe0-232">Supported properties</span></span>                                                                                      |
| -------------- | --------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="51fe0-233">MSTest</span><span class="sxs-lookup"><span data-stu-id="51fe0-233">MSTest</span></span>         | <ul><li><span data-ttu-id="51fe0-234">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="51fe0-234">FullyQualifiedName</span></span></li><li><span data-ttu-id="51fe0-235">name</span><span class="sxs-lookup"><span data-stu-id="51fe0-235">Name</span></span></li><li><span data-ttu-id="51fe0-236">ClassName</span><span class="sxs-lookup"><span data-stu-id="51fe0-236">ClassName</span></span></li><li><span data-ttu-id="51fe0-237">Priority</span><span class="sxs-lookup"><span data-stu-id="51fe0-237">Priority</span></span></li><li><span data-ttu-id="51fe0-238">TestCategory</span><span class="sxs-lookup"><span data-stu-id="51fe0-238">TestCategory</span></span></li></ul> |
| <span data-ttu-id="51fe0-239">xUnit</span><span class="sxs-lookup"><span data-stu-id="51fe0-239">xUnit</span></span>          | <ul><li><span data-ttu-id="51fe0-240">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="51fe0-240">FullyQualifiedName</span></span></li><li><span data-ttu-id="51fe0-241">DisplayName</span><span class="sxs-lookup"><span data-stu-id="51fe0-241">DisplayName</span></span></li><li><span data-ttu-id="51fe0-242">Признаки</span><span class="sxs-lookup"><span data-stu-id="51fe0-242">Traits</span></span></li></ul>                                   |
| <span data-ttu-id="51fe0-243">NUnit</span><span class="sxs-lookup"><span data-stu-id="51fe0-243">NUnit</span></span>          | <ul><li><span data-ttu-id="51fe0-244">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="51fe0-244">FullyQualifiedName</span></span></li><li><span data-ttu-id="51fe0-245">name</span><span class="sxs-lookup"><span data-stu-id="51fe0-245">Name</span></span></li><li><span data-ttu-id="51fe0-246">TestCategory</span><span class="sxs-lookup"><span data-stu-id="51fe0-246">TestCategory</span></span></li><li><span data-ttu-id="51fe0-247">Priority</span><span class="sxs-lookup"><span data-stu-id="51fe0-247">Priority</span></span></li></ul>                                   |

<span data-ttu-id="51fe0-248">`<operator>` описывает связь между свойством и значением:</span><span class="sxs-lookup"><span data-stu-id="51fe0-248">The `<operator>` describes the relationship between the property and the value:</span></span>

| <span data-ttu-id="51fe0-249">Оператор</span><span class="sxs-lookup"><span data-stu-id="51fe0-249">Operator</span></span> | <span data-ttu-id="51fe0-250">Функция</span><span class="sxs-lookup"><span data-stu-id="51fe0-250">Function</span></span>        |
| :------: | --------------- |
| `=`      | <span data-ttu-id="51fe0-251">Точное соответствие</span><span class="sxs-lookup"><span data-stu-id="51fe0-251">Exact match</span></span>     |
| `!=`     | <span data-ttu-id="51fe0-252">Неточное соответствие</span><span class="sxs-lookup"><span data-stu-id="51fe0-252">Not exact match</span></span> |
| `~`      | <span data-ttu-id="51fe0-253">Содержит</span><span class="sxs-lookup"><span data-stu-id="51fe0-253">Contains</span></span>        |
| `!~`     | <span data-ttu-id="51fe0-254">Не содержит</span><span class="sxs-lookup"><span data-stu-id="51fe0-254">Not contains</span></span>    |

<span data-ttu-id="51fe0-255">`<value>` — это строка.</span><span class="sxs-lookup"><span data-stu-id="51fe0-255">`<value>` is a string.</span></span> <span data-ttu-id="51fe0-256">Поиск выполняется без учета регистра.</span><span class="sxs-lookup"><span data-stu-id="51fe0-256">All the lookups are case insensitive.</span></span>

<span data-ttu-id="51fe0-257">Выражение без `<operator>` автоматически считается функцией `contains` для свойства `FullyQualifiedName` (например, `dotnet test --filter xyz` совпадает с `dotnet test --filter FullyQualifiedName~xyz`).</span><span class="sxs-lookup"><span data-stu-id="51fe0-257">An expression without an `<operator>` is automatically considered as a `contains` on `FullyQualifiedName` property (for example, `dotnet test --filter xyz` is same as `dotnet test --filter FullyQualifiedName~xyz`).</span></span>

<span data-ttu-id="51fe0-258">Выражения можно объединять с условными операторами.</span><span class="sxs-lookup"><span data-stu-id="51fe0-258">Expressions can be joined with conditional operators:</span></span>

| <span data-ttu-id="51fe0-259">Оператор</span><span class="sxs-lookup"><span data-stu-id="51fe0-259">Operator</span></span>            | <span data-ttu-id="51fe0-260">Функция</span><span class="sxs-lookup"><span data-stu-id="51fe0-260">Function</span></span> |
| ------------------- | -------- |
| <code>&#124;</code> | <span data-ttu-id="51fe0-261">OR</span><span class="sxs-lookup"><span data-stu-id="51fe0-261">OR</span></span>       |
| `&`                 | <span data-ttu-id="51fe0-262">AND</span><span class="sxs-lookup"><span data-stu-id="51fe0-262">AND</span></span>      |

<span data-ttu-id="51fe0-263">При использовании условных операторов выражения можно заключать в скобки (например, `(Name~TestMethod1) | (Name~TestMethod2)`).</span><span class="sxs-lookup"><span data-stu-id="51fe0-263">You can enclose expressions in parenthesis when using conditional operators (for example, `(Name~TestMethod1) | (Name~TestMethod2)`).</span></span>

<span data-ttu-id="51fe0-264">Дополнительные сведения и примеры использования фильтрации при выборочном модульном тестировании см. в статье [Выполнение выборочных модульных тестов](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="51fe0-264">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="51fe0-265">См. также</span><span class="sxs-lookup"><span data-stu-id="51fe0-265">See also</span></span>

- [<span data-ttu-id="51fe0-266">Платформы и целевые объекты</span><span class="sxs-lookup"><span data-stu-id="51fe0-266">Frameworks and Targets</span></span>](../../standard/frameworks.md)
- [<span data-ttu-id="51fe0-267">Каталог идентификаторов сред выполнения (RID) в .NET Core</span><span class="sxs-lookup"><span data-stu-id="51fe0-267">.NET Core Runtime Identifier (RID) catalog</span></span>](../rid-catalog.md)
- [<span data-ttu-id="51fe0-268">Передача аргументов runsettings через командную строку</span><span class="sxs-lookup"><span data-stu-id="51fe0-268">Passing runsettings arguments through commandline</span></span>](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md)
