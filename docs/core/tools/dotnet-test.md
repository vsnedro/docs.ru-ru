---
title: Команда dotnet test
description: Команда dotnet test служит для выполнения модульных тестов в проекте.
ms.date: 04/29/2020
ms.openlocfilehash: a8218b6596601069b89a60ad018adf89a1f47cf6
ms.sourcegitcommit: e09dbff13f0b21b569a101f3b3c5efa174aec204
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/01/2020
ms.locfileid: "82624895"
---
# <a name="dotnet-test"></a><span data-ttu-id="d7c2d-103">dotnet test</span><span class="sxs-lookup"><span data-stu-id="d7c2d-103">dotnet test</span></span>

<span data-ttu-id="d7c2d-104">**Эта статья относится к следующему.** ✔️ SDK для .NET Core 2.1 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="d7c2d-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="d7c2d-105">name</span><span class="sxs-lookup"><span data-stu-id="d7c2d-105">Name</span></span>

<span data-ttu-id="d7c2d-106">`dotnet test` — драйвер тестов .NET, используемый для проведения модульных тестов.</span><span class="sxs-lookup"><span data-stu-id="d7c2d-106">`dotnet test` - .NET test driver used to execute unit tests.</span></span>

## <a name="synopsis"></a><span data-ttu-id="d7c2d-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="d7c2d-107">Synopsis</span></span>

```dotnetcli
dotnet test [<PROJECT> | <SOLUTION>]
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

## <a name="description"></a><span data-ttu-id="d7c2d-108">Описание</span><span class="sxs-lookup"><span data-stu-id="d7c2d-108">Description</span></span>

<span data-ttu-id="d7c2d-109">Команда `dotnet test` служит для выполнения модульных тестов в проекте.</span><span class="sxs-lookup"><span data-stu-id="d7c2d-109">The `dotnet test` command is used to execute unit tests in a given project.</span></span> <span data-ttu-id="d7c2d-110">Команда `dotnet test` запускает консольное приложение средства выполнения тестов, указанное для проекта.</span><span class="sxs-lookup"><span data-stu-id="d7c2d-110">The `dotnet test` command launches the test runner console application specified for a project.</span></span> <span data-ttu-id="d7c2d-111">Средство выполнения тестов запускает тесты, определенные для платформы модульного тестирования (например, MSTest, NUnit или xUnit) и сообщает об успешном или неудачном выполнении каждого из них.</span><span class="sxs-lookup"><span data-stu-id="d7c2d-111">The test runner executes the tests defined for a unit test framework (for example, MSTest, NUnit, or xUnit) and reports the success or failure of each test.</span></span> <span data-ttu-id="d7c2d-112">Если все тесты выполнены успешно, средство выполнения тестов возвращает код 0. Если же любой тест завершается с ошибкой, средство выполнения возвращает 1.</span><span class="sxs-lookup"><span data-stu-id="d7c2d-112">If all tests are successful, the test runner returns 0 as an exit code; otherwise if any test fails, it returns 1.</span></span> <span data-ttu-id="d7c2d-113">Для проектов с несколькими целевыми платформами тесты запускаются для каждой из них.</span><span class="sxs-lookup"><span data-stu-id="d7c2d-113">For multi-targeted projects, tests are run for each targeted framework.</span></span> <span data-ttu-id="d7c2d-114">Средство выполнения тестов и библиотека модульных тестов упаковываются в пакеты NuGet и восстанавливаются как обычные зависимости проекта.</span><span class="sxs-lookup"><span data-stu-id="d7c2d-114">The test runner and the unit test library are packaged as NuGet packages and are restored as ordinary dependencies for the project.</span></span>

<span data-ttu-id="d7c2d-115">Тестовый проект указывает средство выполнения тестов с помощью обычного элемента `<PackageReference>`, как показано в следующем примере файла проекта:</span><span class="sxs-lookup"><span data-stu-id="d7c2d-115">Test projects specify the test runner using an ordinary `<PackageReference>` element, as seen in the following sample project file:</span></span>

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

### <a name="implicit-restore"></a><span data-ttu-id="d7c2d-116">Неявное восстановление</span><span class="sxs-lookup"><span data-stu-id="d7c2d-116">Implicit restore</span></span>

[!INCLUDE[dotnet restore note](~/includes/dotnet-restore-note.md)]

## <a name="arguments"></a><span data-ttu-id="d7c2d-117">Аргументы</span><span class="sxs-lookup"><span data-stu-id="d7c2d-117">Arguments</span></span>

- **`PROJECT | SOLUTION`**

  <span data-ttu-id="d7c2d-118">Путь к тестовому проекту или решению.</span><span class="sxs-lookup"><span data-stu-id="d7c2d-118">Path to the test project or solution.</span></span> <span data-ttu-id="d7c2d-119">Если значение не задано, по умолчанию используется текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="d7c2d-119">If not specified, it defaults to current directory.</span></span>

## <a name="options"></a><span data-ttu-id="d7c2d-120">Параметры</span><span class="sxs-lookup"><span data-stu-id="d7c2d-120">Options</span></span>

- **`-a|--test-adapter-path <PATH_TO_ADAPTER>`**

  <span data-ttu-id="d7c2d-121">Используйте пользовательские адаптеры теста из указанного пути в тестовом запуске.</span><span class="sxs-lookup"><span data-stu-id="d7c2d-121">Use the custom test adapters from the specified path in the test run.</span></span>

- **`--blame`**

  <span data-ttu-id="d7c2d-122">Выполнение тестов в режиме обвинения.</span><span class="sxs-lookup"><span data-stu-id="d7c2d-122">Runs the tests in blame mode.</span></span> <span data-ttu-id="d7c2d-123">Этот параметр полезен при изоляции проблемных тестов, которые приводят к аварийному завершению хоста для тестов.</span><span class="sxs-lookup"><span data-stu-id="d7c2d-123">This option is helpful in isolating problematic tests that cause the test host to crash.</span></span> <span data-ttu-id="d7c2d-124">Он создает в текущем каталоге выходной файл *Sequence.xml*, который записывает порядок выполнения тестов перед сбоем.</span><span class="sxs-lookup"><span data-stu-id="d7c2d-124">It creates an output file in the current directory as *Sequence.xml* that captures the order of tests execution before the crash.</span></span>

- **`-c|--configuration <CONFIGURATION>`**

  <span data-ttu-id="d7c2d-125">Определяет конфигурацию сборки.</span><span class="sxs-lookup"><span data-stu-id="d7c2d-125">Defines the build configuration.</span></span> <span data-ttu-id="d7c2d-126">Значение по умолчанию — `Debug`, но конфигурация проекта может переопределить этот параметр SDK по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d7c2d-126">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

- **`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`**

  <span data-ttu-id="d7c2d-127">Включает сборщик данных для тестового запуска.</span><span class="sxs-lookup"><span data-stu-id="d7c2d-127">Enables data collector for the test run.</span></span> <span data-ttu-id="d7c2d-128">Дополнительные сведения см. в разделе [Мониторинг и анализ тестового запуска](https://aka.ms/vstest-collect).</span><span class="sxs-lookup"><span data-stu-id="d7c2d-128">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

- **`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`**

  <span data-ttu-id="d7c2d-129">Включает режим диагностики для платформы тестирования и записывает диагностические сообщения в указанный файл.</span><span class="sxs-lookup"><span data-stu-id="d7c2d-129">Enables diagnostic mode for the test platform and writes diagnostic messages to the specified file.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="d7c2d-130">Ищет тестовые двоичные файлы для определенной [платформы](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="d7c2d-130">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

- **`--filter <EXPRESSION>`**

  <span data-ttu-id="d7c2d-131">Фильтрует тесты в текущем проекте с помощью заданного выражения.</span><span class="sxs-lookup"><span data-stu-id="d7c2d-131">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="d7c2d-132">Дополнительные сведения см. в разделе [Сведения о параметре "Фильтр"](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="d7c2d-132">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="d7c2d-133">Дополнительные сведения и примеры использования фильтрации при выборочном модульном тестировании см. в статье [Выполнение выборочных модульных тестов](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="d7c2d-133">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

- **`-h|--help`**

  <span data-ttu-id="d7c2d-134">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="d7c2d-134">Prints out a short help for the command.</span></span>

- **`--interactive`**

  <span data-ttu-id="d7c2d-135">Позволяет команде остановиться и дождаться, пока пользователь выполнит действие или введет данные.</span><span class="sxs-lookup"><span data-stu-id="d7c2d-135">Allows the command to stop and wait for user input or action.</span></span> <span data-ttu-id="d7c2d-136">Например, чтобы завершить проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="d7c2d-136">For example, to complete authentication.</span></span> <span data-ttu-id="d7c2d-137">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="d7c2d-137">Available since .NET Core 3.0 SDK.</span></span>

- **`-l|--logger <LOGGER_URI/FRIENDLY_NAME>`**

  <span data-ttu-id="d7c2d-138">Указывает средство ведения журнала для результатов тестирования.</span><span class="sxs-lookup"><span data-stu-id="d7c2d-138">Specifies a logger for test results.</span></span> <span data-ttu-id="d7c2d-139">В отличие от MSBuild, dotnet test не принимает аббревиатуры: вместо `-l "console;v=d"` используйте `-l "console;verbosity=detailed"`.</span><span class="sxs-lookup"><span data-stu-id="d7c2d-139">Unlike MSBuild, dotnet test doesn't accept abbreviations: instead of `-l "console;v=d"` use `-l "console;verbosity=detailed"`.</span></span>

- **`--no-build`**

  <span data-ttu-id="d7c2d-140">Не выполняет сборку тестового проекта перед запуском.</span><span class="sxs-lookup"><span data-stu-id="d7c2d-140">Doesn't build the test project before running it.</span></span> <span data-ttu-id="d7c2d-141">Он также неявно задает флаг `--no-restore`.</span><span class="sxs-lookup"><span data-stu-id="d7c2d-141">It also implicitly sets the - `--no-restore` flag.</span></span>

- **`--nologo`**

  <span data-ttu-id="d7c2d-142">Запуск тестов без отображения баннера TestPlatform Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="d7c2d-142">Run tests without displaying the Microsoft TestPlatform banner.</span></span> <span data-ttu-id="d7c2d-143">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="d7c2d-143">Available since .NET Core 3.0 SDK.</span></span>

- **`--no-restore`**

  <span data-ttu-id="d7c2d-144">Не выполняет неявное восстановление при выполнении команды.</span><span class="sxs-lookup"><span data-stu-id="d7c2d-144">Doesn't execute an implicit restore when running the command.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="d7c2d-145">Каталог, в котором выполняется поиск двоичных файлов для выполнения.</span><span class="sxs-lookup"><span data-stu-id="d7c2d-145">Directory in which to find the binaries to run.</span></span> <span data-ttu-id="d7c2d-146">Если значение не указано, путь по умолчанию — `./bin/<configuration>/<framework>/`.</span><span class="sxs-lookup"><span data-stu-id="d7c2d-146">If not specified, the default path is `./bin/<configuration>/<framework>/`.</span></span>  <span data-ttu-id="d7c2d-147">Для проектов с несколькими целевыми платформами (с помощью свойства `TargetFrameworks`) необходимо также определить `--framework` при указании этого параметра.</span><span class="sxs-lookup"><span data-stu-id="d7c2d-147">For projects with multiple target frameworks (via the `TargetFrameworks` property), you also need to define `--framework` when you specify this option.</span></span> <span data-ttu-id="d7c2d-148">`dotnet test` всегда запускает тесты из выходного каталога.</span><span class="sxs-lookup"><span data-stu-id="d7c2d-148">`dotnet test` always run tests from the output directory.</span></span> <span data-ttu-id="d7c2d-149">Для использования ресурсов тестирования в выходном каталоге можно использовать <xref:System.AppDomain.BaseDirectory%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d7c2d-149">You can use <xref:System.AppDomain.BaseDirectory%2A?displayProperty=nameWithType> to consume test assets in the output directory.</span></span>

- **`-r|--results-directory <PATH>`**

  <span data-ttu-id="d7c2d-150">Каталог для сохранения результатов тестов.</span><span class="sxs-lookup"><span data-stu-id="d7c2d-150">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="d7c2d-151">Если указанный каталог не существует, он создается.</span><span class="sxs-lookup"><span data-stu-id="d7c2d-151">If the specified directory doesn't exist, it's created.</span></span> <span data-ttu-id="d7c2d-152">По умолчанию используется `TestResults` в каталоге, содержащем файл проекта.</span><span class="sxs-lookup"><span data-stu-id="d7c2d-152">The default is `TestResults` in the directory that contains the project file.</span></span>

- **`--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="d7c2d-153">Целевая среда выполнения для тестирования.</span><span class="sxs-lookup"><span data-stu-id="d7c2d-153">The target runtime to test for.</span></span>

- **`-s|--settings <SETTINGS_FILE>`**

  <span data-ttu-id="d7c2d-154">Файл `.runsettings`, который необходимо использовать для проведения тестов.</span><span class="sxs-lookup"><span data-stu-id="d7c2d-154">The `.runsettings` file to use for running the tests.</span></span> <span data-ttu-id="d7c2d-155">Обратите внимание, что элемент `TargetPlatform` (x86|x64) не влияет на `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="d7c2d-155">Note that the `TargetPlatform` element (x86|x64) has no effect for `dotnet test`.</span></span> <span data-ttu-id="d7c2d-156">Чтобы запускать тесты для x86, установите версию .NET Core x86.</span><span class="sxs-lookup"><span data-stu-id="d7c2d-156">To run tests that target x86, install the x86 version of .NET Core.</span></span> <span data-ttu-id="d7c2d-157">Разрядность *dotnet.exe* в пути будет использоваться для выполнения тестов.</span><span class="sxs-lookup"><span data-stu-id="d7c2d-157">The bitness of the *dotnet.exe* that is on the path is what will be used for running tests.</span></span> <span data-ttu-id="d7c2d-158">Дополнительные сведения см. в следующих ресурсах:</span><span class="sxs-lookup"><span data-stu-id="d7c2d-158">for more information, see the following resources:</span></span>

  - [<span data-ttu-id="d7c2d-159">Настройка модульных тестов с помощью файла `.runsettings`.</span><span class="sxs-lookup"><span data-stu-id="d7c2d-159">Configure unit tests by using a `.runsettings` file.</span></span>](/visualstudio/test/configure-unit-tests-by-using-a-dot-runsettings-file)
  - [<span data-ttu-id="d7c2d-160">Настройка тестового запуска</span><span class="sxs-lookup"><span data-stu-id="d7c2d-160">Configure a test run</span></span>](https://github.com/Microsoft/vstest-docs/blob/master/docs/configure.md)

- **`-t|--list-tests`**

  <span data-ttu-id="d7c2d-161">Отображение списка всех обнаруженных тестов в текущем проекте.</span><span class="sxs-lookup"><span data-stu-id="d7c2d-161">List all of the discovered tests in the current project.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="d7c2d-162">Задает уровень детализации команды.</span><span class="sxs-lookup"><span data-stu-id="d7c2d-162">Sets the verbosity level of the command.</span></span> <span data-ttu-id="d7c2d-163">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="d7c2d-163">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="d7c2d-164">Значение по умолчанию — `minimal`.</span><span class="sxs-lookup"><span data-stu-id="d7c2d-164">The default is `minimal`.</span></span> <span data-ttu-id="d7c2d-165">Для получения дополнительной информации см. <xref:Microsoft.Build.Framework.LoggerVerbosity>.</span><span class="sxs-lookup"><span data-stu-id="d7c2d-165">For more information, see <xref:Microsoft.Build.Framework.LoggerVerbosity>.</span></span>

- <span data-ttu-id="d7c2d-166">Аргументы **`RunSettings`**</span><span class="sxs-lookup"><span data-stu-id="d7c2d-166">**`RunSettings`** arguments</span></span>

  <span data-ttu-id="d7c2d-167">Аргументы передаются в качестве конфигураций `RunSettings` для теста.</span><span class="sxs-lookup"><span data-stu-id="d7c2d-167">Arguments are passed as `RunSettings` configurations for the test.</span></span> <span data-ttu-id="d7c2d-168">Аргументы задаются в виде пар `[name]=[value]` после "-- " (обратите внимание на пробел после --).</span><span class="sxs-lookup"><span data-stu-id="d7c2d-168">Arguments are specified as `[name]=[value]` pairs after "-- " (note the space after --).</span></span> <span data-ttu-id="d7c2d-169">Несколько пар `[name]=[value]` разделяются пробелами.</span><span class="sxs-lookup"><span data-stu-id="d7c2d-169">A space is used to separate multiple `[name]=[value]` pairs.</span></span>

  <span data-ttu-id="d7c2d-170">Пример: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span><span class="sxs-lookup"><span data-stu-id="d7c2d-170">Example: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span></span>

  <span data-ttu-id="d7c2d-171">Дополнительные сведения см. в статье о [передаче аргументов RunSettings с помощью командной строки](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md).</span><span class="sxs-lookup"><span data-stu-id="d7c2d-171">For more information, see [Passing RunSettings arguments through command line](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md).</span></span>

## <a name="examples"></a><span data-ttu-id="d7c2d-172">Примеры</span><span class="sxs-lookup"><span data-stu-id="d7c2d-172">Examples</span></span>

- <span data-ttu-id="d7c2d-173">Выполнение тестов в проекте в текущем каталоге:</span><span class="sxs-lookup"><span data-stu-id="d7c2d-173">Run the tests in the project in the current directory:</span></span>

  ```dotnetcli
  dotnet test
  ```

- <span data-ttu-id="d7c2d-174">Выполнение тестов в проекте `test1`:</span><span class="sxs-lookup"><span data-stu-id="d7c2d-174">Run the tests in the `test1` project:</span></span>

  ```dotnetcli
  dotnet test ~/projects/test1/test1.csproj
  ```

- <span data-ttu-id="d7c2d-175">Выполнение тестов в проекте в текущем каталоге и создание файла результатов теста в формате TRX:</span><span class="sxs-lookup"><span data-stu-id="d7c2d-175">Run the tests in the project in the current directory, and generate a test results file in the trx format:</span></span>

  ```dotnetcli
  dotnet test --logger trx
  ```

- <span data-ttu-id="d7c2d-176">Выполнение тестов в проекте в текущем каталоге и вывод журнала с подробными сведениями в консоль:</span><span class="sxs-lookup"><span data-stu-id="d7c2d-176">Run the tests in the project in the current directory, and log with detailed verbosity to the console:</span></span>

  ```dotnetcli
  dotnet test --logger "console;verbosity=detailed"
  ```

## <a name="filter-option-details"></a><span data-ttu-id="d7c2d-177">Сведения о параметре "Фильтр"</span><span class="sxs-lookup"><span data-stu-id="d7c2d-177">Filter option details</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="d7c2d-178">Параметр `<Expression>` имеет следующий формат: `<property><operator><value>[|&<Expression>]`.</span><span class="sxs-lookup"><span data-stu-id="d7c2d-178">`<Expression>` has the format `<property><operator><value>[|&<Expression>]`.</span></span>

<span data-ttu-id="d7c2d-179">`<property>` — это атрибут `Test Case`.</span><span class="sxs-lookup"><span data-stu-id="d7c2d-179">`<property>` is an attribute of the `Test Case`.</span></span> <span data-ttu-id="d7c2d-180">Ниже приведены свойства, поддерживаемые популярными платформами модульных тестов.</span><span class="sxs-lookup"><span data-stu-id="d7c2d-180">The following are the properties supported by popular unit test frameworks:</span></span>

| <span data-ttu-id="d7c2d-181">Тестовая платформа</span><span class="sxs-lookup"><span data-stu-id="d7c2d-181">Test Framework</span></span> | <span data-ttu-id="d7c2d-182">Поддерживаемые свойства</span><span class="sxs-lookup"><span data-stu-id="d7c2d-182">Supported properties</span></span>                                                                                      |
| -------------- | --------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="d7c2d-183">MSTest</span><span class="sxs-lookup"><span data-stu-id="d7c2d-183">MSTest</span></span>         | <ul><li><span data-ttu-id="d7c2d-184">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="d7c2d-184">FullyQualifiedName</span></span></li><li><span data-ttu-id="d7c2d-185">name</span><span class="sxs-lookup"><span data-stu-id="d7c2d-185">Name</span></span></li><li><span data-ttu-id="d7c2d-186">ClassName</span><span class="sxs-lookup"><span data-stu-id="d7c2d-186">ClassName</span></span></li><li><span data-ttu-id="d7c2d-187">Priority</span><span class="sxs-lookup"><span data-stu-id="d7c2d-187">Priority</span></span></li><li><span data-ttu-id="d7c2d-188">TestCategory</span><span class="sxs-lookup"><span data-stu-id="d7c2d-188">TestCategory</span></span></li></ul> |
| <span data-ttu-id="d7c2d-189">xUnit</span><span class="sxs-lookup"><span data-stu-id="d7c2d-189">xUnit</span></span>          | <ul><li><span data-ttu-id="d7c2d-190">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="d7c2d-190">FullyQualifiedName</span></span></li><li><span data-ttu-id="d7c2d-191">DisplayName</span><span class="sxs-lookup"><span data-stu-id="d7c2d-191">DisplayName</span></span></li><li><span data-ttu-id="d7c2d-192">Признаки</span><span class="sxs-lookup"><span data-stu-id="d7c2d-192">Traits</span></span></li></ul>                                   |

<span data-ttu-id="d7c2d-193">`<operator>` описывает связь между свойством и значением:</span><span class="sxs-lookup"><span data-stu-id="d7c2d-193">The `<operator>` describes the relationship between the property and the value:</span></span>

| <span data-ttu-id="d7c2d-194">Оператор</span><span class="sxs-lookup"><span data-stu-id="d7c2d-194">Operator</span></span> | <span data-ttu-id="d7c2d-195">Функция</span><span class="sxs-lookup"><span data-stu-id="d7c2d-195">Function</span></span>        |
| :------: | --------------- |
| `=`      | <span data-ttu-id="d7c2d-196">Точное соответствие</span><span class="sxs-lookup"><span data-stu-id="d7c2d-196">Exact match</span></span>     |
| `!=`     | <span data-ttu-id="d7c2d-197">Неточное соответствие</span><span class="sxs-lookup"><span data-stu-id="d7c2d-197">Not exact match</span></span> |
| `~`      | <span data-ttu-id="d7c2d-198">Содержит</span><span class="sxs-lookup"><span data-stu-id="d7c2d-198">Contains</span></span>        |
| `!~`     | <span data-ttu-id="d7c2d-199">Не содержит</span><span class="sxs-lookup"><span data-stu-id="d7c2d-199">Not contains</span></span>    |

<span data-ttu-id="d7c2d-200">`<value>` — это строка.</span><span class="sxs-lookup"><span data-stu-id="d7c2d-200">`<value>` is a string.</span></span> <span data-ttu-id="d7c2d-201">Поиск выполняется без учета регистра.</span><span class="sxs-lookup"><span data-stu-id="d7c2d-201">All the lookups are case insensitive.</span></span>

<span data-ttu-id="d7c2d-202">Выражение без `<operator>` автоматически считается функцией `contains` для свойства `FullyQualifiedName` (например, `dotnet test --filter xyz` совпадает с `dotnet test --filter FullyQualifiedName~xyz`).</span><span class="sxs-lookup"><span data-stu-id="d7c2d-202">An expression without an `<operator>` is automatically considered as a `contains` on `FullyQualifiedName` property (for example, `dotnet test --filter xyz` is same as `dotnet test --filter FullyQualifiedName~xyz`).</span></span>

<span data-ttu-id="d7c2d-203">Выражения можно объединять с условными операторами.</span><span class="sxs-lookup"><span data-stu-id="d7c2d-203">Expressions can be joined with conditional operators:</span></span>

| <span data-ttu-id="d7c2d-204">Оператор</span><span class="sxs-lookup"><span data-stu-id="d7c2d-204">Operator</span></span>            | <span data-ttu-id="d7c2d-205">Функция</span><span class="sxs-lookup"><span data-stu-id="d7c2d-205">Function</span></span> |
| ------------------- | -------- |
| <code>&#124;</code> | <span data-ttu-id="d7c2d-206">OR</span><span class="sxs-lookup"><span data-stu-id="d7c2d-206">OR</span></span>       |
| `&`                 | <span data-ttu-id="d7c2d-207">AND</span><span class="sxs-lookup"><span data-stu-id="d7c2d-207">AND</span></span>      |

<span data-ttu-id="d7c2d-208">При использовании условных операторов выражения можно заключать в скобки (например, `(Name~TestMethod1) | (Name~TestMethod2)`).</span><span class="sxs-lookup"><span data-stu-id="d7c2d-208">You can enclose expressions in parenthesis when using conditional operators (for example, `(Name~TestMethod1) | (Name~TestMethod2)`).</span></span>

<span data-ttu-id="d7c2d-209">Дополнительные сведения и примеры использования фильтрации при выборочном модульном тестировании см. в статье [Выполнение выборочных модульных тестов](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="d7c2d-209">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d7c2d-210">См. также</span><span class="sxs-lookup"><span data-stu-id="d7c2d-210">See also</span></span>

- [<span data-ttu-id="d7c2d-211">Платформы и целевые объекты</span><span class="sxs-lookup"><span data-stu-id="d7c2d-211">Frameworks and Targets</span></span>](../../standard/frameworks.md)
- [<span data-ttu-id="d7c2d-212">Каталог идентификаторов сред выполнения (RID) в .NET Core</span><span class="sxs-lookup"><span data-stu-id="d7c2d-212">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
- [<span data-ttu-id="d7c2d-213">Передача аргументов runsettings через командную строку</span><span class="sxs-lookup"><span data-stu-id="d7c2d-213">Passing runsettings arguments through commandline</span></span>](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md)
