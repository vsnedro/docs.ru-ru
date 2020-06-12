---
title: Команда dotnet test
description: Команда dotnet test служит для выполнения модульных тестов в проекте.
ms.date: 04/29/2020
ms.openlocfilehash: 1190ecb75e83c9930c60726e7cd83203b11928cb
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "84283940"
---
# <a name="dotnet-test"></a><span data-ttu-id="8add4-103">dotnet test</span><span class="sxs-lookup"><span data-stu-id="8add4-103">dotnet test</span></span>

<span data-ttu-id="8add4-104">**Эта статья относится к следующему.** ✔️ SDK для .NET Core 2.1 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="8add4-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="8add4-105">name</span><span class="sxs-lookup"><span data-stu-id="8add4-105">Name</span></span>

<span data-ttu-id="8add4-106">`dotnet test` — драйвер тестов .NET, используемый для проведения модульных тестов.</span><span class="sxs-lookup"><span data-stu-id="8add4-106">`dotnet test` - .NET test driver used to execute unit tests.</span></span>

## <a name="synopsis"></a><span data-ttu-id="8add4-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="8add4-107">Synopsis</span></span>

```dotnetcli
dotnet test [<PROJECT> | <SOLUTION> | <DIRECTORY> | <DLL>]
    [-a|--test-adapter-path <PATH_TO_ADAPTER>] [--blame]
    [-c|--configuration <CONFIGURATION>]
    [--collect <DATA_COLLECTOR_FRIENDLY_NAME>]
    [-d|--diag <PATH_TO_DIAGNOSTICS_FILE>] [-f|--framework <FRAMEWORK>]
    [--filter <EXPRESSION>] [--interactive]
    [-l|--logger <LOGGER_URI/FRIENDLY_NAME>] [--no-build]
    [--nologo] [--no-restore] [-o|--output <OUTPUT_DIRECTORY>]
    [-r|--results-directory <PATH>] [--runtime <RUNTIME_IDENTIFIER>]
    [-s|--settings <SETTINGS_FILE>] [-t|--list-tests]
    [-v|--verbosity <LEVEL>] [[--] <RunSettings arguments>]

dotnet test -h|--help
```

## <a name="description"></a><span data-ttu-id="8add4-108">Описание</span><span class="sxs-lookup"><span data-stu-id="8add4-108">Description</span></span>

<span data-ttu-id="8add4-109">Команда `dotnet test` служит для выполнения модульных тестов в решении.</span><span class="sxs-lookup"><span data-stu-id="8add4-109">The `dotnet test` command is used to execute unit tests in a given solution.</span></span> <span data-ttu-id="8add4-110">Команда `dotnet test` создает решение и запускает приложение тестового узла для каждого тестового проекта в решении.</span><span class="sxs-lookup"><span data-stu-id="8add4-110">The `dotnet test` command builds the solution and runs a test host application for each test project in the solution.</span></span> <span data-ttu-id="8add4-111">Тестовый узел выполняет тесты в заданном проекте с помощью платформы тестирования, например MSTest, NUnit или xUnit, и сообщает об успешном или неуспешном завершении каждого теста.</span><span class="sxs-lookup"><span data-stu-id="8add4-111">The test host executes tests in the given project using a test framework, for example: MSTest, NUnit, or xUnit, and reports the success or failure of each test.</span></span> <span data-ttu-id="8add4-112">Если все тесты выполнены успешно, средство выполнения тестов возвращает код 0. Если же любой тест завершается с ошибкой, средство выполнения возвращает 1.</span><span class="sxs-lookup"><span data-stu-id="8add4-112">If all tests are successful, the test runner returns 0 as an exit code; otherwise if any test fails, it returns 1.</span></span>

<span data-ttu-id="8add4-113">Для проектов с несколькими целевыми платформами тесты запускаются для каждой из них.</span><span class="sxs-lookup"><span data-stu-id="8add4-113">For multi-targeted projects, tests are run for each targeted framework.</span></span> <span data-ttu-id="8add4-114">Тестовый узел и платформа модульных тестов упаковываются в пакеты NuGet и восстанавливаются как обычные зависимости проекта.</span><span class="sxs-lookup"><span data-stu-id="8add4-114">The test host and the unit test framework are packaged as NuGet packages and are restored as ordinary dependencies for the project.</span></span>

<span data-ttu-id="8add4-115">Тестовый проект указывает средство выполнения тестов с помощью обычного элемента `<PackageReference>`, как показано в следующем примере файла проекта:</span><span class="sxs-lookup"><span data-stu-id="8add4-115">Test projects specify the test runner using an ordinary `<PackageReference>` element, as seen in the following sample project file:</span></span>

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

<span data-ttu-id="8add4-116">Где `Microsoft.NET.Test.Sdk` — это тестовый узел, `xunit` — платформа тестирования.</span><span class="sxs-lookup"><span data-stu-id="8add4-116">Where `Microsoft.NET.Test.Sdk` is the test host, `xunit` is the test framework.</span></span> <span data-ttu-id="8add4-117">`xunit.runner.visualstudio` — это адаптер теста, позволяющий платформе xUnit работать с тестовым узлом.</span><span class="sxs-lookup"><span data-stu-id="8add4-117">And `xunit.runner.visualstudio` is a test adapter, which allows the xUnit framework to work with the test host.</span></span>

### <a name="implicit-restore"></a><span data-ttu-id="8add4-118">Неявное восстановление</span><span class="sxs-lookup"><span data-stu-id="8add4-118">Implicit restore</span></span>

[!INCLUDE[dotnet restore note](~/includes/dotnet-restore-note.md)]

## <a name="arguments"></a><span data-ttu-id="8add4-119">Аргументы</span><span class="sxs-lookup"><span data-stu-id="8add4-119">Arguments</span></span>

- **`PROJECT | SOLUTION | DIRECTORY | DLL`**

  - <span data-ttu-id="8add4-120">Путь к тестовому проекту.</span><span class="sxs-lookup"><span data-stu-id="8add4-120">Path to the test project.</span></span>
  - <span data-ttu-id="8add4-121">Путь к решению.</span><span class="sxs-lookup"><span data-stu-id="8add4-121">Path to the solution.</span></span>
  - <span data-ttu-id="8add4-122">Путь к каталогу, содержащему проект или решение.</span><span class="sxs-lookup"><span data-stu-id="8add4-122">Path to a directory that contains a project or a solution.</span></span>
  - <span data-ttu-id="8add4-123">Путь к *DLL-файлу* тестового проекта.</span><span class="sxs-lookup"><span data-stu-id="8add4-123">Path to a test project *.dll* file.</span></span>

  <span data-ttu-id="8add4-124">Если он не указан, команда ищет проект или решение в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="8add4-124">If not specified, it searches for a project or a solution in the current directory.</span></span>

## <a name="options"></a><span data-ttu-id="8add4-125">Параметры</span><span class="sxs-lookup"><span data-stu-id="8add4-125">Options</span></span>

- **`-a|--test-adapter-path <PATH_TO_ADAPTER>`**

  <span data-ttu-id="8add4-126">Путь к каталогу для поиска дополнительных адаптеров теста.</span><span class="sxs-lookup"><span data-stu-id="8add4-126">Path to a directory to be searched for additional test adapters.</span></span> <span data-ttu-id="8add4-127">Проверяются только *DLL*-файлы с суффиксом `.TestAdapter.dll`.</span><span class="sxs-lookup"><span data-stu-id="8add4-127">Only *.dll* files with suffix `.TestAdapter.dll` are inspected.</span></span> <span data-ttu-id="8add4-128">Если не указано, выполняется поиск по каталогу тестового *DLL*.</span><span class="sxs-lookup"><span data-stu-id="8add4-128">If not specified, the directory of the test *.dll* is searched.</span></span>

- **`--blame`**

  <span data-ttu-id="8add4-129">Выполнение тестов в режиме обвинения.</span><span class="sxs-lookup"><span data-stu-id="8add4-129">Runs the tests in blame mode.</span></span> <span data-ttu-id="8add4-130">Этот параметр полезен при изоляции проблемных тестов, которые приводят к аварийному завершению хоста для тестов.</span><span class="sxs-lookup"><span data-stu-id="8add4-130">This option is helpful in isolating problematic tests that cause the test host to crash.</span></span> <span data-ttu-id="8add4-131">При обнаружении сбоя он создает файл последовательности в `TestResults/<Guid>/<Guid>_Sequence.xml`, который фиксирует порядок тестов, выполненных до сбоя.</span><span class="sxs-lookup"><span data-stu-id="8add4-131">When a crash is detected, it creates a sequence file in `TestResults/<Guid>/<Guid>_Sequence.xml` that captures the order of tests that were run before the crash.</span></span>

- **`-c|--configuration <CONFIGURATION>`**

  <span data-ttu-id="8add4-132">Определяет конфигурацию сборки.</span><span class="sxs-lookup"><span data-stu-id="8add4-132">Defines the build configuration.</span></span> <span data-ttu-id="8add4-133">Значение по умолчанию — `Debug`, но конфигурация проекта может переопределить этот параметр SDK по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="8add4-133">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

- **`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`**

  <span data-ttu-id="8add4-134">Включает сборщик данных для тестового запуска.</span><span class="sxs-lookup"><span data-stu-id="8add4-134">Enables data collector for the test run.</span></span> <span data-ttu-id="8add4-135">Дополнительные сведения см. в разделе [Мониторинг и анализ тестового запуска](https://aka.ms/vstest-collect).</span><span class="sxs-lookup"><span data-stu-id="8add4-135">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>
  
  <span data-ttu-id="8add4-136">Чтобы получить объем протестированного кода на любой платформе, поддерживаемой .NET Core, установите [Coverlet](https://github.com/coverlet-coverage/coverlet/blob/master/README.md) и используйте параметр `--collect:"XPlat Code Coverage"`.</span><span class="sxs-lookup"><span data-stu-id="8add4-136">To collect code coverage on any platform that is supported by .NET Core, install [Coverlet](https://github.com/coverlet-coverage/coverlet/blob/master/README.md) and use the `--collect:"XPlat Code Coverage"` option.</span></span>

  <span data-ttu-id="8add4-137">В Windows объем протестированного кода можно получить с помощью параметра `--collect "Code Coverage"`.</span><span class="sxs-lookup"><span data-stu-id="8add4-137">On Windows, you can collect code coverage by using the `--collect "Code Coverage"` option.</span></span> <span data-ttu-id="8add4-138">Этот параметр создает файл *COVERAGE*, который можно открыть в Visual Studio 2019 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="8add4-138">This option generates a *.coverage* file, which can be opened in Visual Studio 2019 Enterprise.</span></span> <span data-ttu-id="8add4-139">Дополнительные сведения см. в статьях [Использование объема протестированного кода](/visualstudio/test/using-code-coverage-to-determine-how-much-code-is-being-tested) и [Настройка анализа объема протестированного кода](/visualstudio/test/customizing-code-coverage-analysis).</span><span class="sxs-lookup"><span data-stu-id="8add4-139">For more information, see [Use code coverage](/visualstudio/test/using-code-coverage-to-determine-how-much-code-is-being-tested) and [Customize code coverage analysis](/visualstudio/test/customizing-code-coverage-analysis).</span></span>

- **`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`**

  <span data-ttu-id="8add4-140">Включает режим диагностики для платформы тестирования и записывает диагностические сообщения в указанный файл и в файлы рядом с ним.</span><span class="sxs-lookup"><span data-stu-id="8add4-140">Enables diagnostic mode for the test platform and writes diagnostic messages to the specified file and to files next to it.</span></span> <span data-ttu-id="8add4-141">Процесс, который заносит сообщения в журнал, определяет, какие файлы создаются, например `*.host_<date>.txt` для журнала тестового узла и `*.datacollector_<date>.txt` для журнала сборщика данных.</span><span class="sxs-lookup"><span data-stu-id="8add4-141">The process that is logging the messages determines which files are created, such as `*.host_<date>.txt` for test host log, and `*.datacollector_<date>.txt` for data collector log.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="8add4-142">Определяет принудительное использование `dotnet` или тестового узла .NET Framework для двоичных файлов теста.</span><span class="sxs-lookup"><span data-stu-id="8add4-142">Forces the use of `dotnet` or .NET Framework test host for the test binaries.</span></span> <span data-ttu-id="8add4-143">Этот параметр определяет только используемый тип узла.</span><span class="sxs-lookup"><span data-stu-id="8add4-143">This option only determines which type of host to use.</span></span> <span data-ttu-id="8add4-144">Реальная используемая версия платформы определяется в файле *runtimeconfig.json* тестового проекта.</span><span class="sxs-lookup"><span data-stu-id="8add4-144">The actual framework version to be used is determined by the *runtimeconfig.json* of the test project.</span></span> <span data-ttu-id="8add4-145">Если этот параметр не указан, для определения типа узла используется [атрибут сборки TargetFramework](/dotnet/api/system.runtime.versioning.targetframeworkattribute).</span><span class="sxs-lookup"><span data-stu-id="8add4-145">When not specified, the [TargetFramework assembly attribute](/dotnet/api/system.runtime.versioning.targetframeworkattribute) is used to determine the type of host.</span></span> <span data-ttu-id="8add4-146">Если этот атрибут удален из *DLL*, используется узел .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8add4-146">When that attribute is stripped from the *.dll*, the .NET Framework host is used.</span></span>

- **`--filter <EXPRESSION>`**

  <span data-ttu-id="8add4-147">Фильтрует тесты в текущем проекте с помощью заданного выражения.</span><span class="sxs-lookup"><span data-stu-id="8add4-147">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="8add4-148">Дополнительные сведения см. в разделе [Сведения о параметре "Фильтр"](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="8add4-148">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="8add4-149">Дополнительные сведения и примеры использования фильтрации при выборочном модульном тестировании см. в статье [Выполнение выборочных модульных тестов](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="8add4-149">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

- **`-h|--help`**

  <span data-ttu-id="8add4-150">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="8add4-150">Prints out a short help for the command.</span></span>

- **`--interactive`**

  <span data-ttu-id="8add4-151">Позволяет команде остановиться и дождаться, пока пользователь выполнит действие или введет данные.</span><span class="sxs-lookup"><span data-stu-id="8add4-151">Allows the command to stop and wait for user input or action.</span></span> <span data-ttu-id="8add4-152">Например, чтобы завершить проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="8add4-152">For example, to complete authentication.</span></span> <span data-ttu-id="8add4-153">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="8add4-153">Available since .NET Core 3.0 SDK.</span></span>

- **`-l|--logger <LOGGER_URI/FRIENDLY_NAME>`**

  <span data-ttu-id="8add4-154">Указывает средство ведения журнала для результатов тестирования.</span><span class="sxs-lookup"><span data-stu-id="8add4-154">Specifies a logger for test results.</span></span> <span data-ttu-id="8add4-155">В отличие от MSBuild, dotnet test не принимает аббревиатуры: вместо `-l "console;v=d"` используйте `-l "console;verbosity=detailed"`.</span><span class="sxs-lookup"><span data-stu-id="8add4-155">Unlike MSBuild, dotnet test doesn't accept abbreviations: instead of `-l "console;v=d"` use `-l "console;verbosity=detailed"`.</span></span>

- **`--no-build`**

  <span data-ttu-id="8add4-156">Не выполняет сборку тестового проекта перед запуском.</span><span class="sxs-lookup"><span data-stu-id="8add4-156">Doesn't build the test project before running it.</span></span> <span data-ttu-id="8add4-157">Он также неявно задает флаг `--no-restore`.</span><span class="sxs-lookup"><span data-stu-id="8add4-157">It also implicitly sets the - `--no-restore` flag.</span></span>

- **`--nologo`**

  <span data-ttu-id="8add4-158">Запуск тестов без отображения баннера TestPlatform Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="8add4-158">Run tests without displaying the Microsoft TestPlatform banner.</span></span> <span data-ttu-id="8add4-159">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="8add4-159">Available since .NET Core 3.0 SDK.</span></span>

- **`--no-restore`**

  <span data-ttu-id="8add4-160">Не выполняет неявное восстановление при выполнении команды.</span><span class="sxs-lookup"><span data-stu-id="8add4-160">Doesn't execute an implicit restore when running the command.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="8add4-161">Каталог, в котором выполняется поиск двоичных файлов для выполнения.</span><span class="sxs-lookup"><span data-stu-id="8add4-161">Directory in which to find the binaries to run.</span></span> <span data-ttu-id="8add4-162">Если значение не указано, путь по умолчанию — `./bin/<configuration>/<framework>/`.</span><span class="sxs-lookup"><span data-stu-id="8add4-162">If not specified, the default path is `./bin/<configuration>/<framework>/`.</span></span>  <span data-ttu-id="8add4-163">Для проектов с несколькими целевыми платформами (с помощью свойства `TargetFrameworks`) необходимо также определить `--framework` при указании этого параметра.</span><span class="sxs-lookup"><span data-stu-id="8add4-163">For projects with multiple target frameworks (via the `TargetFrameworks` property), you also need to define `--framework` when you specify this option.</span></span> <span data-ttu-id="8add4-164">`dotnet test` всегда запускает тесты из выходного каталога.</span><span class="sxs-lookup"><span data-stu-id="8add4-164">`dotnet test` always runs tests from the output directory.</span></span> <span data-ttu-id="8add4-165">Для использования ресурсов тестирования в выходном каталоге можно использовать <xref:System.AppDomain.BaseDirectory%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="8add4-165">You can use <xref:System.AppDomain.BaseDirectory%2A?displayProperty=nameWithType> to consume test assets in the output directory.</span></span>

- **`-r|--results-directory <PATH>`**

  <span data-ttu-id="8add4-166">Каталог для сохранения результатов тестов.</span><span class="sxs-lookup"><span data-stu-id="8add4-166">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="8add4-167">Если указанный каталог не существует, он создается.</span><span class="sxs-lookup"><span data-stu-id="8add4-167">If the specified directory doesn't exist, it's created.</span></span> <span data-ttu-id="8add4-168">По умолчанию используется `TestResults` в каталоге, содержащем файл проекта.</span><span class="sxs-lookup"><span data-stu-id="8add4-168">The default is `TestResults` in the directory that contains the project file.</span></span>

- **`--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="8add4-169">Целевая среда выполнения для тестирования.</span><span class="sxs-lookup"><span data-stu-id="8add4-169">The target runtime to test for.</span></span>

- **`-s|--settings <SETTINGS_FILE>`**

  <span data-ttu-id="8add4-170">Файл `.runsettings`, который необходимо использовать для проведения тестов.</span><span class="sxs-lookup"><span data-stu-id="8add4-170">The `.runsettings` file to use for running the tests.</span></span> <span data-ttu-id="8add4-171">Элемент `TargetPlatform` (x86|x64) не влияет на `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="8add4-171">The `TargetPlatform` element (x86|x64) has no effect for `dotnet test`.</span></span> <span data-ttu-id="8add4-172">Чтобы запускать тесты для x86, установите версию .NET Core x86.</span><span class="sxs-lookup"><span data-stu-id="8add4-172">To run tests that target x86, install the x86 version of .NET Core.</span></span> <span data-ttu-id="8add4-173">Разрядность *dotnet.exe* в пути будет использоваться для выполнения тестов.</span><span class="sxs-lookup"><span data-stu-id="8add4-173">The bitness of the *dotnet.exe* that is on the path is what will be used for running tests.</span></span> <span data-ttu-id="8add4-174">Дополнительные сведения см. в следующих ресурсах:</span><span class="sxs-lookup"><span data-stu-id="8add4-174">For more information, see the following resources:</span></span>

  - [<span data-ttu-id="8add4-175">Настройка модульных тестов с помощью файла `.runsettings`.</span><span class="sxs-lookup"><span data-stu-id="8add4-175">Configure unit tests by using a `.runsettings` file.</span></span>](/visualstudio/test/configure-unit-tests-by-using-a-dot-runsettings-file)
  - [<span data-ttu-id="8add4-176">Настройка тестового запуска</span><span class="sxs-lookup"><span data-stu-id="8add4-176">Configure a test run</span></span>](https://github.com/Microsoft/vstest-docs/blob/master/docs/configure.md)

- **`-t|--list-tests`**

  <span data-ttu-id="8add4-177">Отображение списка всех обнаруженных тестов в текущем проекте.</span><span class="sxs-lookup"><span data-stu-id="8add4-177">List all of the discovered tests in the current project.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="8add4-178">Задает уровень детализации команды.</span><span class="sxs-lookup"><span data-stu-id="8add4-178">Sets the verbosity level of the command.</span></span> <span data-ttu-id="8add4-179">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="8add4-179">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="8add4-180">Значение по умолчанию — `minimal`.</span><span class="sxs-lookup"><span data-stu-id="8add4-180">The default is `minimal`.</span></span> <span data-ttu-id="8add4-181">Для получения дополнительной информации см. <xref:Microsoft.Build.Framework.LoggerVerbosity>.</span><span class="sxs-lookup"><span data-stu-id="8add4-181">For more information, see <xref:Microsoft.Build.Framework.LoggerVerbosity>.</span></span>

- <span data-ttu-id="8add4-182">Аргументы **`RunSettings`**</span><span class="sxs-lookup"><span data-stu-id="8add4-182">**`RunSettings`** arguments</span></span>

 <span data-ttu-id="8add4-183">Встроенные `RunSettings` передаются как последние аргументы в командной строке после "-- " (обратите внимание на пробел после "--").</span><span class="sxs-lookup"><span data-stu-id="8add4-183">Inline `RunSettings` are passed as the last arguments on the command line after "-- " (note the space after --).</span></span> <span data-ttu-id="8add4-184">Встроенные `RunSettings` указываются как пары `[name]=[value]`.</span><span class="sxs-lookup"><span data-stu-id="8add4-184">Inline `RunSettings` are specified as `[name]=[value]` pairs.</span></span> <span data-ttu-id="8add4-185">Несколько пар `[name]=[value]` разделяются пробелами.</span><span class="sxs-lookup"><span data-stu-id="8add4-185">A space is used to separate multiple `[name]=[value]` pairs.</span></span>

  <span data-ttu-id="8add4-186">Пример: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span><span class="sxs-lookup"><span data-stu-id="8add4-186">Example: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span></span>

  <span data-ttu-id="8add4-187">Дополнительные сведения см. в статье о [передаче аргументов RunSettings с помощью командной строки](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md).</span><span class="sxs-lookup"><span data-stu-id="8add4-187">For more information, see [Passing RunSettings arguments through command line](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md).</span></span>

## <a name="examples"></a><span data-ttu-id="8add4-188">Примеры</span><span class="sxs-lookup"><span data-stu-id="8add4-188">Examples</span></span>

- <span data-ttu-id="8add4-189">Выполнение тестов в проекте в текущем каталоге:</span><span class="sxs-lookup"><span data-stu-id="8add4-189">Run the tests in the project in the current directory:</span></span>

  ```dotnetcli
  dotnet test
  ```

- <span data-ttu-id="8add4-190">Выполнение тестов в проекте `test1`:</span><span class="sxs-lookup"><span data-stu-id="8add4-190">Run the tests in the `test1` project:</span></span>

  ```dotnetcli
  dotnet test ~/projects/test1/test1.csproj
  ```

- <span data-ttu-id="8add4-191">Выполнение тестов в проекте в текущем каталоге и создание файла результатов теста в формате TRX:</span><span class="sxs-lookup"><span data-stu-id="8add4-191">Run the tests in the project in the current directory, and generate a test results file in the trx format:</span></span>

  ```dotnetcli
  dotnet test --logger trx
  ```

- <span data-ttu-id="8add4-192">Выполнение тестов в проекте в текущем каталоге и создание файла с объемом протестированного кода (после установки [Coverlet](https://github.com/tonerdo/coverlet/blob/master/README.md)):</span><span class="sxs-lookup"><span data-stu-id="8add4-192">Run the tests in the project in the current directory, and generate a code coverage file (after installing [Coverlet](https://github.com/tonerdo/coverlet/blob/master/README.md)):</span></span>

  ```dotnetcli
  dotnet test --collect:"XPlat Code Coverage"
  ```

- <span data-ttu-id="8add4-193">Выполнение тестов в проекте в текущем каталоге и создание файла с объемом протестированного кода (только Windows):</span><span class="sxs-lookup"><span data-stu-id="8add4-193">Run the tests in the project in the current directory, and generate a code coverage file (Windows only):</span></span>

  ```dotnetcli
  dotnet test --collect "Code Coverage"
  ```

- <span data-ttu-id="8add4-194">Выполнение тестов в проекте в текущем каталоге и вывод журнала с подробными сведениями в консоль:</span><span class="sxs-lookup"><span data-stu-id="8add4-194">Run the tests in the project in the current directory, and log with detailed verbosity to the console:</span></span>

  ```dotnetcli
  dotnet test --logger "console;verbosity=detailed"
  ```
  
  - <span data-ttu-id="8add4-195">Выполнение тестов в проекте в текущем каталоге и тестов отчетов, которые выполнялись при сбое узла тестирования:</span><span class="sxs-lookup"><span data-stu-id="8add4-195">Run the tests in the project in the current directory, and report tests that were in progress when the test host crashed:</span></span>

  ```dotnetcli
  dotnet test --blame
  ```

## <a name="filter-option-details"></a><span data-ttu-id="8add4-196">Сведения о параметре "Фильтр"</span><span class="sxs-lookup"><span data-stu-id="8add4-196">Filter option details</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="8add4-197">Параметр `<Expression>` имеет следующий формат: `<property><operator><value>[|&<Expression>]`.</span><span class="sxs-lookup"><span data-stu-id="8add4-197">`<Expression>` has the format `<property><operator><value>[|&<Expression>]`.</span></span>

<span data-ttu-id="8add4-198">`<property>` — это атрибут `Test Case`.</span><span class="sxs-lookup"><span data-stu-id="8add4-198">`<property>` is an attribute of the `Test Case`.</span></span> <span data-ttu-id="8add4-199">Ниже приведены свойства, поддерживаемые популярными платформами модульных тестов.</span><span class="sxs-lookup"><span data-stu-id="8add4-199">The following are the properties supported by popular unit test frameworks:</span></span>

| <span data-ttu-id="8add4-200">Тестовая платформа</span><span class="sxs-lookup"><span data-stu-id="8add4-200">Test Framework</span></span> | <span data-ttu-id="8add4-201">Поддерживаемые свойства</span><span class="sxs-lookup"><span data-stu-id="8add4-201">Supported properties</span></span>                                                                                      |
| -------------- | --------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="8add4-202">MSTest</span><span class="sxs-lookup"><span data-stu-id="8add4-202">MSTest</span></span>         | <ul><li><span data-ttu-id="8add4-203">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="8add4-203">FullyQualifiedName</span></span></li><li><span data-ttu-id="8add4-204">name</span><span class="sxs-lookup"><span data-stu-id="8add4-204">Name</span></span></li><li><span data-ttu-id="8add4-205">ClassName</span><span class="sxs-lookup"><span data-stu-id="8add4-205">ClassName</span></span></li><li><span data-ttu-id="8add4-206">Priority</span><span class="sxs-lookup"><span data-stu-id="8add4-206">Priority</span></span></li><li><span data-ttu-id="8add4-207">TestCategory</span><span class="sxs-lookup"><span data-stu-id="8add4-207">TestCategory</span></span></li></ul> |
| <span data-ttu-id="8add4-208">xUnit</span><span class="sxs-lookup"><span data-stu-id="8add4-208">xUnit</span></span>          | <ul><li><span data-ttu-id="8add4-209">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="8add4-209">FullyQualifiedName</span></span></li><li><span data-ttu-id="8add4-210">DisplayName</span><span class="sxs-lookup"><span data-stu-id="8add4-210">DisplayName</span></span></li><li><span data-ttu-id="8add4-211">Признаки</span><span class="sxs-lookup"><span data-stu-id="8add4-211">Traits</span></span></li></ul>                                   |
| <span data-ttu-id="8add4-212">NUnit</span><span class="sxs-lookup"><span data-stu-id="8add4-212">NUnit</span></span>          | <ul><li><span data-ttu-id="8add4-213">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="8add4-213">FullyQualifiedName</span></span></li><li><span data-ttu-id="8add4-214">name</span><span class="sxs-lookup"><span data-stu-id="8add4-214">Name</span></span></li><li><span data-ttu-id="8add4-215">TestCategory</span><span class="sxs-lookup"><span data-stu-id="8add4-215">TestCategory</span></span></li><li><span data-ttu-id="8add4-216">Priority</span><span class="sxs-lookup"><span data-stu-id="8add4-216">Priority</span></span></li></ul>                                   |

<span data-ttu-id="8add4-217">`<operator>` описывает связь между свойством и значением:</span><span class="sxs-lookup"><span data-stu-id="8add4-217">The `<operator>` describes the relationship between the property and the value:</span></span>

| <span data-ttu-id="8add4-218">Оператор</span><span class="sxs-lookup"><span data-stu-id="8add4-218">Operator</span></span> | <span data-ttu-id="8add4-219">Функция</span><span class="sxs-lookup"><span data-stu-id="8add4-219">Function</span></span>        |
| :------: | --------------- |
| `=`      | <span data-ttu-id="8add4-220">Точное соответствие</span><span class="sxs-lookup"><span data-stu-id="8add4-220">Exact match</span></span>     |
| `!=`     | <span data-ttu-id="8add4-221">Неточное соответствие</span><span class="sxs-lookup"><span data-stu-id="8add4-221">Not exact match</span></span> |
| `~`      | <span data-ttu-id="8add4-222">Содержит</span><span class="sxs-lookup"><span data-stu-id="8add4-222">Contains</span></span>        |
| `!~`     | <span data-ttu-id="8add4-223">Не содержит</span><span class="sxs-lookup"><span data-stu-id="8add4-223">Not contains</span></span>    |

<span data-ttu-id="8add4-224">`<value>` — это строка.</span><span class="sxs-lookup"><span data-stu-id="8add4-224">`<value>` is a string.</span></span> <span data-ttu-id="8add4-225">Поиск выполняется без учета регистра.</span><span class="sxs-lookup"><span data-stu-id="8add4-225">All the lookups are case insensitive.</span></span>

<span data-ttu-id="8add4-226">Выражение без `<operator>` автоматически считается функцией `contains` для свойства `FullyQualifiedName` (например, `dotnet test --filter xyz` совпадает с `dotnet test --filter FullyQualifiedName~xyz`).</span><span class="sxs-lookup"><span data-stu-id="8add4-226">An expression without an `<operator>` is automatically considered as a `contains` on `FullyQualifiedName` property (for example, `dotnet test --filter xyz` is same as `dotnet test --filter FullyQualifiedName~xyz`).</span></span>

<span data-ttu-id="8add4-227">Выражения можно объединять с условными операторами.</span><span class="sxs-lookup"><span data-stu-id="8add4-227">Expressions can be joined with conditional operators:</span></span>

| <span data-ttu-id="8add4-228">Оператор</span><span class="sxs-lookup"><span data-stu-id="8add4-228">Operator</span></span>            | <span data-ttu-id="8add4-229">Функция</span><span class="sxs-lookup"><span data-stu-id="8add4-229">Function</span></span> |
| ------------------- | -------- |
| <code>&#124;</code> | <span data-ttu-id="8add4-230">OR</span><span class="sxs-lookup"><span data-stu-id="8add4-230">OR</span></span>       |
| `&`                 | <span data-ttu-id="8add4-231">AND</span><span class="sxs-lookup"><span data-stu-id="8add4-231">AND</span></span>      |

<span data-ttu-id="8add4-232">При использовании условных операторов выражения можно заключать в скобки (например, `(Name~TestMethod1) | (Name~TestMethod2)`).</span><span class="sxs-lookup"><span data-stu-id="8add4-232">You can enclose expressions in parenthesis when using conditional operators (for example, `(Name~TestMethod1) | (Name~TestMethod2)`).</span></span>

<span data-ttu-id="8add4-233">Дополнительные сведения и примеры использования фильтрации при выборочном модульном тестировании см. в статье [Выполнение выборочных модульных тестов](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="8add4-233">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8add4-234">См. также</span><span class="sxs-lookup"><span data-stu-id="8add4-234">See also</span></span>

- [<span data-ttu-id="8add4-235">Платформы и целевые объекты</span><span class="sxs-lookup"><span data-stu-id="8add4-235">Frameworks and Targets</span></span>](../../standard/frameworks.md)
- [<span data-ttu-id="8add4-236">Каталог идентификаторов сред выполнения (RID) в .NET Core</span><span class="sxs-lookup"><span data-stu-id="8add4-236">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
- [<span data-ttu-id="8add4-237">Передача аргументов runsettings через командную строку</span><span class="sxs-lookup"><span data-stu-id="8add4-237">Passing runsettings arguments through commandline</span></span>](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md)
