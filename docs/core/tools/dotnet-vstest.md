---
title: Команда dotnet vstest
description: Команда dotnet vstest выполняет сборку проекта и всех его зависимостей.
ms.date: 02/27/2020
ms.openlocfilehash: f7db58f4aab59354b8c69ce0371324c23482dafe
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2020
ms.locfileid: "82975398"
---
# <a name="dotnet-vstest"></a><span data-ttu-id="fc5c7-103">dotnet vstest</span><span class="sxs-lookup"><span data-stu-id="fc5c7-103">dotnet vstest</span></span>

<span data-ttu-id="fc5c7-104">**Эта статья относится к следующему.** ✔️ SDK для .NET Core 2.1 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="fc5c7-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fc5c7-105">Команда `dotnet vstest` заменяется на `dotnet test`, которую теперь можно использовать для запуска сборок.</span><span class="sxs-lookup"><span data-stu-id="fc5c7-105">The `dotnet vstest` command is superseded by `dotnet test`, which can now be used to run assemblies.</span></span> <span data-ttu-id="fc5c7-106">См. раздел [`dotnet test`](dotnet-test.md).</span><span class="sxs-lookup"><span data-stu-id="fc5c7-106">See [`dotnet test`](dotnet-test.md).</span></span>

## <a name="name"></a><span data-ttu-id="fc5c7-107">name</span><span class="sxs-lookup"><span data-stu-id="fc5c7-107">Name</span></span>

<span data-ttu-id="fc5c7-108">`dotnet-vstest` — запускает тесты из указанных сборок.</span><span class="sxs-lookup"><span data-stu-id="fc5c7-108">`dotnet-vstest` - Runs tests from the specified assemblies.</span></span>

## <a name="synopsis"></a><span data-ttu-id="fc5c7-109">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="fc5c7-109">Synopsis</span></span>

```dotnetcli
dotnet vstest [<TEST_FILE_NAMES>] [--Blame] [--Diag <PATH_TO_LOG_FILE>]
    [--Framework <FRAMEWORK>] [--InIsolation] [-lt|--ListTests <FILE_NAME>]
    [--logger <LOGGER_URI/FRIENDLY_NAME>] [--Parallel]
    [--ParentProcessId <PROCESS_ID>] [--Platform] <PLATFORM_TYPE>
    [--Port <PORT>] [--ResultsDirectory<PATH>] [--Settings <SETTINGS_FILE>]
    [--TestAdapterPath <PATH>] [--TestCaseFilter <EXPRESSION>]
    [--Tests <TEST_NAMES>] [[--] <args>...]]

dotnet vstest -?|--Help
```

## <a name="description"></a><span data-ttu-id="fc5c7-110">Описание</span><span class="sxs-lookup"><span data-stu-id="fc5c7-110">Description</span></span>

<span data-ttu-id="fc5c7-111">Команда `dotnet-vstest` запускает приложение командной строки `VSTest.Console` для выполнения автоматического модульного тестирования.</span><span class="sxs-lookup"><span data-stu-id="fc5c7-111">The `dotnet-vstest` command runs the `VSTest.Console` command-line application to run automated unit tests.</span></span>

## <a name="arguments"></a><span data-ttu-id="fc5c7-112">Аргументы</span><span class="sxs-lookup"><span data-stu-id="fc5c7-112">Arguments</span></span>

- **`TEST_FILE_NAMES`**

  <span data-ttu-id="fc5c7-113">Запустите тесты из указанных сборок.</span><span class="sxs-lookup"><span data-stu-id="fc5c7-113">Run tests from the specified assemblies.</span></span> <span data-ttu-id="fc5c7-114">Для разделения имен тестовых сборок используйте пробелы.</span><span class="sxs-lookup"><span data-stu-id="fc5c7-114">Separate multiple test assembly names with spaces.</span></span> <span data-ttu-id="fc5c7-115">Поддерживаются подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="fc5c7-115">Wildcards are supported.</span></span>

## <a name="options"></a><span data-ttu-id="fc5c7-116">Параметры</span><span class="sxs-lookup"><span data-stu-id="fc5c7-116">Options</span></span>

- **`--Blame`**

  <span data-ttu-id="fc5c7-117">Выполнение тестов в режиме обвинения.</span><span class="sxs-lookup"><span data-stu-id="fc5c7-117">Runs the tests in blame mode.</span></span> <span data-ttu-id="fc5c7-118">Этот параметр полезен при изоляции проблемных тестов, которые приводят к аварийному завершению хоста для тестов.</span><span class="sxs-lookup"><span data-stu-id="fc5c7-118">This option is helpful in isolating the problematic tests causing test host to crash.</span></span> <span data-ttu-id="fc5c7-119">Он создает в текущем каталоге выходной файл *Sequence.xml*, который записывает порядок выполнения тестов перед сбоем.</span><span class="sxs-lookup"><span data-stu-id="fc5c7-119">It creates an output file in the current directory as *Sequence.xml* that captures the order of tests execution before the crash.</span></span>

- **`--Diag <PATH_TO_LOG_FILE>`**

  <span data-ttu-id="fc5c7-120">Включает ведение подробных журналов для платформы тестирования.</span><span class="sxs-lookup"><span data-stu-id="fc5c7-120">Enables verbose logs for the test platform.</span></span> <span data-ttu-id="fc5c7-121">Журналы записываются в указанный файл.</span><span class="sxs-lookup"><span data-stu-id="fc5c7-121">Logs are written to the provided file.</span></span>

- **`--Framework <FRAMEWORK>`**

  <span data-ttu-id="fc5c7-122">Целевая версия платформы .NET Framework, используемая для выполнения тестов.</span><span class="sxs-lookup"><span data-stu-id="fc5c7-122">Target .NET Framework version used for test execution.</span></span> <span data-ttu-id="fc5c7-123">Примеры допустимых значений: `.NETFramework,Version=v4.6` или `.NETCoreApp,Version=v1.0`.</span><span class="sxs-lookup"><span data-stu-id="fc5c7-123">Examples of valid values are `.NETFramework,Version=v4.6` or `.NETCoreApp,Version=v1.0`.</span></span> <span data-ttu-id="fc5c7-124">Другие поддерживаемые значения: `Framework40`, `Framework45`, `FrameworkCore10` и `FrameworkUap10`.</span><span class="sxs-lookup"><span data-stu-id="fc5c7-124">Other supported values are `Framework40`, `Framework45`, `FrameworkCore10`, and `FrameworkUap10`.</span></span>

- **`--InIsolation`**

  <span data-ttu-id="fc5c7-125">Запуск тестов в изолированном процессе.</span><span class="sxs-lookup"><span data-stu-id="fc5c7-125">Runs the tests in an isolated process.</span></span> <span data-ttu-id="fc5c7-126">Это снижает вероятность остановки процесса *vstest.console.exe* при возникновении ошибки в тестах, однако тесты могут выполняться медленнее.</span><span class="sxs-lookup"><span data-stu-id="fc5c7-126">This makes *vstest.console.exe* process less likely to be stopped on an error in the tests, but tests may run slower.</span></span>

- **`-lt|--ListTests <FILE_NAME>`**

  <span data-ttu-id="fc5c7-127">Перечисление всех обнаруженных тестов из указанного контейнера тестов.</span><span class="sxs-lookup"><span data-stu-id="fc5c7-127">Lists all discovered tests from the given test container.</span></span>

- **`--logger <LOGGER_URI/FRIENDLY_NAME>`**

  <span data-ttu-id="fc5c7-128">Укажите средство ведения журнала результатов тестирования.</span><span class="sxs-lookup"><span data-stu-id="fc5c7-128">Specify a logger for test results.</span></span>

  - <span data-ttu-id="fc5c7-129">Чтобы опубликовать результаты теста в Team Foundation Server, используйте поставщик средства ведения журнала `TfsPublisher`:</span><span class="sxs-lookup"><span data-stu-id="fc5c7-129">To publish test results to Team Foundation Server, use the `TfsPublisher` logger provider:</span></span>

    ```console
    /logger:TfsPublisher;
        Collection=<team project collection url>;
        BuildName=<build name>;
        TeamProject=<team project name>
        [;Platform=<Defaults to "Any CPU">]
        [;Flavor=<Defaults to "Debug">]
        [;RunTitle=<title>]
    ```

  - <span data-ttu-id="fc5c7-130">Чтобы записать результаты в файл результатов теста Visual Studio (TRX), используйте поставщик средства ведения журнала `trx`.</span><span class="sxs-lookup"><span data-stu-id="fc5c7-130">To log results to a Visual Studio Test Results File (TRX), use the `trx` logger provider.</span></span> <span data-ttu-id="fc5c7-131">Этот параметр создает файл журнала с заданным именем в каталоге результатов теста.</span><span class="sxs-lookup"><span data-stu-id="fc5c7-131">This switch creates a file in the test results directory with given log file name.</span></span> <span data-ttu-id="fc5c7-132">Если `LogFileName` не указан, для хранения результатов теста создается уникальное имя файла.</span><span class="sxs-lookup"><span data-stu-id="fc5c7-132">If `LogFileName` isn't provided, a unique file name is created to hold the test results.</span></span>

    ```console
    /logger:trx [;LogFileName=<Defaults to unique file name>]
    ```

- **`--Parallel`**

  <span data-ttu-id="fc5c7-133">Выполняйте тесты в параллельном режиме.</span><span class="sxs-lookup"><span data-stu-id="fc5c7-133">Run tests in parallel.</span></span> <span data-ttu-id="fc5c7-134">По умолчанию для использования все доступные на компьютере ядра.</span><span class="sxs-lookup"><span data-stu-id="fc5c7-134">By default, all available cores on the machine are available for use.</span></span> <span data-ttu-id="fc5c7-135">Укажите явное число ядер, задав свойство `MaxCpuCount` в узле `RunConfiguration` в файле *runsettings*.</span><span class="sxs-lookup"><span data-stu-id="fc5c7-135">Specify an explicit number of cores by setting the `MaxCpuCount` property under the `RunConfiguration` node in the *runsettings* file.</span></span>

- **`--ParentProcessId <PROCESS_ID>`**

  <span data-ttu-id="fc5c7-136">Идентификатор родительского процесса, отвечающего за запуск текущего процесса.</span><span class="sxs-lookup"><span data-stu-id="fc5c7-136">Process ID of the parent process responsible for launching the current process.</span></span>

- **`--Platform <PLATFORM_TYPE>`**

  <span data-ttu-id="fc5c7-137">Архитектура целевой платформы, используемая для выполнения тестов.</span><span class="sxs-lookup"><span data-stu-id="fc5c7-137">Target platform architecture used for test execution.</span></span> <span data-ttu-id="fc5c7-138">Допустимые значения: `x86`, `x64` и `ARM`.</span><span class="sxs-lookup"><span data-stu-id="fc5c7-138">Valid values are `x86`, `x64`, and `ARM`.</span></span>

- **`--Port <PORT>`**

  <span data-ttu-id="fc5c7-139">Указывает порт для подключения сокета и получения сообщений о событиях.</span><span class="sxs-lookup"><span data-stu-id="fc5c7-139">Specifies the port for the socket connection and receiving the event messages.</span></span>

- **`--ResultsDirectory:<PATH>`**

  <span data-ttu-id="fc5c7-140">По указанному пути будет создан каталог с результатами теста, если этот путь не существует.</span><span class="sxs-lookup"><span data-stu-id="fc5c7-140">Test results directory will be created in specified path if not exists.</span></span>

- **`--Settings <SETTINGS_FILE>`**

  <span data-ttu-id="fc5c7-141">Параметры, используемые при выполнении тестов.</span><span class="sxs-lookup"><span data-stu-id="fc5c7-141">Settings to use when running tests.</span></span>

- **`--TestAdapterPath <PATH>`**

  <span data-ttu-id="fc5c7-142">Используйте пользовательские адаптеры теста из указанного пути (при наличии) в тестовом запуске.</span><span class="sxs-lookup"><span data-stu-id="fc5c7-142">Use custom test adapters from a given path (if any) in the test run.</span></span>

- **`--TestCaseFilter <EXPRESSION>`**

  <span data-ttu-id="fc5c7-143">Запуск тестов, соответствующих заданному выражению.</span><span class="sxs-lookup"><span data-stu-id="fc5c7-143">Run tests that match the given expression.</span></span> <span data-ttu-id="fc5c7-144">`<EXPRESSION>` имеет формат `<property>Operator<value>[|&<EXPRESSION>]`, где Operator принимает одно из следующих значений: `=`, `!=` или `~`.</span><span class="sxs-lookup"><span data-stu-id="fc5c7-144">`<EXPRESSION>` is of the format `<property>Operator<value>[|&<EXPRESSION>]`, where Operator is one of `=`, `!=`, or `~`.</span></span> <span data-ttu-id="fc5c7-145">Оператор `~` имеет семантику "содержит" и применяется для строковых свойств, таких как `DisplayName`.</span><span class="sxs-lookup"><span data-stu-id="fc5c7-145">Operator `~` has 'contains' semantics and is applicable for string properties like `DisplayName`.</span></span> <span data-ttu-id="fc5c7-146">Скобки `()` используются для группировки частей выражений.</span><span class="sxs-lookup"><span data-stu-id="fc5c7-146">Parentheses `()` are used to group subexpressions.</span></span> <span data-ttu-id="fc5c7-147">Дополнительные сведения см. в документе о [фильтре TestCase](https://github.com/Microsoft/vstest-docs/blob/master/docs/filter.md).</span><span class="sxs-lookup"><span data-stu-id="fc5c7-147">For more information, see [TestCase filter](https://github.com/Microsoft/vstest-docs/blob/master/docs/filter.md).</span></span>

- **`--Tests <TEST_NAMES>`**

  <span data-ttu-id="fc5c7-148">Выполните тесты с именами, которые соответствуют предусмотренным значениям.</span><span class="sxs-lookup"><span data-stu-id="fc5c7-148">Run tests with names that match the provided values.</span></span> <span data-ttu-id="fc5c7-149">Для разделения значений используйте запятые.</span><span class="sxs-lookup"><span data-stu-id="fc5c7-149">Separate multiple values with commas.</span></span>

- **`-?|--Help`**

  <span data-ttu-id="fc5c7-150">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="fc5c7-150">Prints out a short help for the command.</span></span>

- **`@<file>`**

  <span data-ttu-id="fc5c7-151">Считывает файл ответов с дополнительными параметрами.</span><span class="sxs-lookup"><span data-stu-id="fc5c7-151">Reads response file for more options.</span></span>

- **`args`**

  <span data-ttu-id="fc5c7-152">Задает дополнительные аргументы, передаваемые адаптеру.</span><span class="sxs-lookup"><span data-stu-id="fc5c7-152">Specifies extra arguments to pass to the adapter.</span></span> <span data-ttu-id="fc5c7-153">Аргументы указываются как пары имя-значение в формате `<n>=<v>`, где `<n>` является именем аргумента, а `<v>` — значением аргумента.</span><span class="sxs-lookup"><span data-stu-id="fc5c7-153">Arguments are specified as name-value pairs of the form `<n>=<v>`, where `<n>` is the argument name and `<v>` is the argument value.</span></span> <span data-ttu-id="fc5c7-154">Для разделения аргументов используйте пробел.</span><span class="sxs-lookup"><span data-stu-id="fc5c7-154">Use a space to separate multiple arguments.</span></span>

## <a name="examples"></a><span data-ttu-id="fc5c7-155">Примеры</span><span class="sxs-lookup"><span data-stu-id="fc5c7-155">Examples</span></span>

<span data-ttu-id="fc5c7-156">Запуск тестов в *mytestproject.dll*:</span><span class="sxs-lookup"><span data-stu-id="fc5c7-156">Run tests in *mytestproject.dll*:</span></span>

```dotnetcli
dotnet vstest mytestproject.dll
```

<span data-ttu-id="fc5c7-157">Запуск тестов в *mytestproject.dll* с экспортом в настраиваемую папку с пользовательским именем:</span><span class="sxs-lookup"><span data-stu-id="fc5c7-157">Run tests in *mytestproject.dll*, exporting to custom folder with custom name:</span></span>

```dotnetcli
dotnet vstest mytestproject.dll --logger:"trx;LogFileName=custom_file_name.trx" --ResultsDirectory:custom/file/path
```

<span data-ttu-id="fc5c7-158">Запуск тестов в *mytestproject.dll* и *myothertestproject.exe*:</span><span class="sxs-lookup"><span data-stu-id="fc5c7-158">Run tests in *mytestproject.dll* and *myothertestproject.exe*:</span></span>

```dotnetcli
dotnet vstest mytestproject.dll myothertestproject.exe
```

<span data-ttu-id="fc5c7-159">Запуск тестов `TestMethod1`:</span><span class="sxs-lookup"><span data-stu-id="fc5c7-159">Run `TestMethod1` tests:</span></span>

```dotnetcli
dotnet vstest /Tests:TestMethod1
```

<span data-ttu-id="fc5c7-160">Запуск тестов `TestMethod1` и `TestMethod2`:</span><span class="sxs-lookup"><span data-stu-id="fc5c7-160">Run `TestMethod1` and `TestMethod2` tests:</span></span>

```dotnetcli
dotnet vstest /Tests:TestMethod1,TestMethod2
```

## <a name="see-also"></a><span data-ttu-id="fc5c7-161">См. также</span><span class="sxs-lookup"><span data-stu-id="fc5c7-161">See also</span></span>

- [<span data-ttu-id="fc5c7-162">Параметры командной строки для VSTest.Console.exe</span><span class="sxs-lookup"><span data-stu-id="fc5c7-162">VSTest.Console.exe command-line options</span></span>](/visualstudio/test/vstest-console-options)
