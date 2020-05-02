---
title: Команда dotnet
description: Узнайте о команде dotnet (универсальном драйвере для CLI .NET Core) и о том, как ее использовать.
ms.date: 02/13/2020
ms.openlocfilehash: 6a08297499d955db44e342dc82fed25b7b9b8171
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2020
ms.locfileid: "81739070"
---
# <a name="dotnet-command"></a><span data-ttu-id="f1acb-103">Команда dotnet</span><span class="sxs-lookup"><span data-stu-id="f1acb-103">dotnet command</span></span>

<span data-ttu-id="f1acb-104">**Эта статья относится к следующему.** ✔️ SDK для .NET Core 2.1 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="f1acb-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="f1acb-105">name</span><span class="sxs-lookup"><span data-stu-id="f1acb-105">Name</span></span>

<span data-ttu-id="f1acb-106">`dotnet` — универсальный драйвер для интерфейса командной строки .NET Core (CLI).</span><span class="sxs-lookup"><span data-stu-id="f1acb-106">`dotnet` - The generic driver for the .NET Core CLI.</span></span>

## <a name="synopsis"></a><span data-ttu-id="f1acb-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="f1acb-107">Synopsis</span></span>

<span data-ttu-id="f1acb-108">Чтобы получить сведения о среде и доступных командах, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="f1acb-108">To get information about the available commands and the environment:</span></span>

```dotnetcli
dotnet [--version] [--info] [--list-runtimes] [--list-sdks]

dotnet -h|--help
```

<span data-ttu-id="f1acb-109">Выполнение команды (требуется установка пакета SDK):</span><span class="sxs-lookup"><span data-stu-id="f1acb-109">To run a command (requires SDK installation):</span></span>

```dotnetcli
dotnet <COMMAND> [-d|--diagnostics] [-h|--help] [--verbosity <LEVEL>]
    [command-options] [arguments]
```

<span data-ttu-id="f1acb-110">Запуск приложения:</span><span class="sxs-lookup"><span data-stu-id="f1acb-110">To run an application:</span></span>

```dotnetcli
dotnet [--additionalprobingpath <PATH>] [--additional-deps <PATH>]
    [--fx-version <VERSION>]  [--roll-forward <SETTING>]
    <PATH_TO_APPLICATION> [arguments]

dotnet exec [--additionalprobingpath] [--additional-deps <PATH>]
    [--fx-version <VERSION>]  [--roll-forward <SETTING>]
    <PATH_TO_APPLICATION> [arguments]
```

<span data-ttu-id="f1acb-111">Команда `--roll-forward` доступна, начиная с версии .NET Core 3.x.</span><span class="sxs-lookup"><span data-stu-id="f1acb-111">`--roll-forward` is available since .NET Core 3.x.</span></span> <span data-ttu-id="f1acb-112">Для .NET Core 2.x следует использовать `--roll-forward-on-no-candidate-fx`.</span><span class="sxs-lookup"><span data-stu-id="f1acb-112">Use `--roll-forward-on-no-candidate-fx` for .NET Core 2.x.</span></span>

## <a name="description"></a><span data-ttu-id="f1acb-113">Описание</span><span class="sxs-lookup"><span data-stu-id="f1acb-113">Description</span></span>

<span data-ttu-id="f1acb-114">Команда `dotnet` выполняет две функции:</span><span class="sxs-lookup"><span data-stu-id="f1acb-114">The `dotnet` command has two functions:</span></span>

- <span data-ttu-id="f1acb-115">Она предоставляет команды для работы с проектами .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f1acb-115">It provides commands for working with .NET Core projects.</span></span>

  <span data-ttu-id="f1acb-116">Например, команда [`dotnet build`](dotnet-build.md) выполняет построение проекта.</span><span class="sxs-lookup"><span data-stu-id="f1acb-116">For example, [`dotnet build`](dotnet-build.md) builds a project.</span></span> <span data-ttu-id="f1acb-117">Каждая команда определяет свои параметры и аргументы.</span><span class="sxs-lookup"><span data-stu-id="f1acb-117">Each command defines its own options and arguments.</span></span> <span data-ttu-id="f1acb-118">Все команды поддерживают параметр `--help`, позволяющий вывести краткую справку по их использованию.</span><span class="sxs-lookup"><span data-stu-id="f1acb-118">All commands support the `--help` option for printing out brief documentation about how to use the command.</span></span>

- <span data-ttu-id="f1acb-119">Запускает приложения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f1acb-119">It runs .NET Core applications.</span></span>

  <span data-ttu-id="f1acb-120">Для запуска приложения необходимо указать путь к его файлу `.dll`.</span><span class="sxs-lookup"><span data-stu-id="f1acb-120">You specify the path to an application `.dll` file to run the application.</span></span>  <span data-ttu-id="f1acb-121">Чтобы запустить приложение, необходимо найти и выполнить точку входа, которая в случае использования консольных приложений является методом `Main`.</span><span class="sxs-lookup"><span data-stu-id="f1acb-121">To run the application means to find and execute the entry point, which in the case of console apps is the `Main` method.</span></span> <span data-ttu-id="f1acb-122">Например, команда `dotnet myapp.dll` запускает приложение `myapp`.</span><span class="sxs-lookup"><span data-stu-id="f1acb-122">For example, `dotnet myapp.dll` runs the `myapp` application.</span></span> <span data-ttu-id="f1acb-123">Дополнительные сведения о параметрах развертывания см. в статье [Развертывание приложений .NET Core](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="f1acb-123">See [.NET Core application deployment](../deploying/index.md) to learn about deployment options.</span></span>

## <a name="options"></a><span data-ttu-id="f1acb-124">Параметры</span><span class="sxs-lookup"><span data-stu-id="f1acb-124">Options</span></span>

<span data-ttu-id="f1acb-125">Доступны параметры для `dotnet`, для выполнения команды, а также для запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="f1acb-125">Different options are available for `dotnet` by itself, for running a command, and for running an application.</span></span>

### <a name="options-for-dotnet-by-itself"></a><span data-ttu-id="f1acb-126">Параметры для dotnet</span><span class="sxs-lookup"><span data-stu-id="f1acb-126">Options for dotnet by itself</span></span>

<span data-ttu-id="f1acb-127">Для `dotnet` доступны следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="f1acb-127">The following options are for `dotnet` by itself.</span></span> <span data-ttu-id="f1acb-128">Например, `dotnet --info`.</span><span class="sxs-lookup"><span data-stu-id="f1acb-128">For example, `dotnet --info`.</span></span> <span data-ttu-id="f1acb-129">Выводит сведения о среде.</span><span class="sxs-lookup"><span data-stu-id="f1acb-129">They print out information about the environment.</span></span>

- **`--info`**

  <span data-ttu-id="f1acb-130">Выводит подробные сведения об установке .NET Core и среде компьютера, например текущую операционную систему и фиксацию SHA версии .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f1acb-130">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

- **`--version`**

  <span data-ttu-id="f1acb-131">Выводит версию используемого пакета SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f1acb-131">Prints out the version of the .NET Core SDK in use.</span></span>

- **`--list-runtimes`**

  <span data-ttu-id="f1acb-132">Выводит список установленных сред выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f1acb-132">Prints out a list of the installed .NET Core runtimes.</span></span> <span data-ttu-id="f1acb-133">Версия x86 пакета SDK содержит только среды выполнения x86, а в версии x64 пакета SDK содержатся только среды выполнения x64.</span><span class="sxs-lookup"><span data-stu-id="f1acb-133">An x86 version of the SDK lists only x86 runtimes, and an x64 version of the SDK lists only x64 runtimes.</span></span>

- **`--list-sdks`**

  <span data-ttu-id="f1acb-134">Выводит список установленных пакетов SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f1acb-134">Prints out a list of the installed .NET Core SDKs.</span></span>

- **`-h|--help`**

  <span data-ttu-id="f1acb-135">Выводит список доступных команд.</span><span class="sxs-lookup"><span data-stu-id="f1acb-135">Prints out a list of available commands.</span></span>

### <a name="sdk-options-for-running-a-command"></a><span data-ttu-id="f1acb-136">Параметры пакета SDK для выполнения команды</span><span class="sxs-lookup"><span data-stu-id="f1acb-136">SDK options for running a command</span></span>

<span data-ttu-id="f1acb-137">Для `dotnet` с командой доступны следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="f1acb-137">The following options are for `dotnet` with a command.</span></span> <span data-ttu-id="f1acb-138">Например, `dotnet build --help`.</span><span class="sxs-lookup"><span data-stu-id="f1acb-138">For example, `dotnet build --help`.</span></span>

- **`-d|--diagnostics`**

  <span data-ttu-id="f1acb-139">Включает вывод диагностических данных.</span><span class="sxs-lookup"><span data-stu-id="f1acb-139">Enables diagnostic output.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="f1acb-140">Задает уровень детализации команды.</span><span class="sxs-lookup"><span data-stu-id="f1acb-140">Sets the verbosity level of the command.</span></span> <span data-ttu-id="f1acb-141">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="f1acb-141">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="f1acb-142">Поддерживается не во всех командах.</span><span class="sxs-lookup"><span data-stu-id="f1acb-142">Not supported in every command.</span></span> <span data-ttu-id="f1acb-143">Дополнительные сведения см. на странице соответствующей команды.</span><span class="sxs-lookup"><span data-stu-id="f1acb-143">See specific command page to determine if this option is available.</span></span>

- **`-h|--help`**

  <span data-ttu-id="f1acb-144">Выводит на экран документацию для определенной команды, например `dotnet build --help`.</span><span class="sxs-lookup"><span data-stu-id="f1acb-144">Prints out documentation for a given command, such as `dotnet build --help`.</span></span>

- **`command options`**

  <span data-ttu-id="f1acb-145">Для каждой команды определяются относящиеся к ней параметры.</span><span class="sxs-lookup"><span data-stu-id="f1acb-145">Each command defines options specific to that command.</span></span> <span data-ttu-id="f1acb-146">Список доступных для команды параметров можно просмотреть на соответствующей ей странице.</span><span class="sxs-lookup"><span data-stu-id="f1acb-146">See specific command page for a list of available options.</span></span>

### <a name="runtime-options"></a><span data-ttu-id="f1acb-147">Параметры среды выполнения</span><span class="sxs-lookup"><span data-stu-id="f1acb-147">Runtime options</span></span>

<span data-ttu-id="f1acb-148">При запуске приложения в `dotnet` доступны следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="f1acb-148">The following options are available when `dotnet` runs an application.</span></span> <span data-ttu-id="f1acb-149">Например, `dotnet myapp.dll --fx-version 3.1.1`.</span><span class="sxs-lookup"><span data-stu-id="f1acb-149">For example, `dotnet myapp.dll --fx-version 3.1.1`.</span></span>

- **`--additionalprobingpath <PATH>`**

  <span data-ttu-id="f1acb-150">Путь, содержащий политику проверки и проверяемые сборки.</span><span class="sxs-lookup"><span data-stu-id="f1acb-150">Path containing probing policy and assemblies to probe.</span></span>

- **`--additional-deps <PATH>`**

  <span data-ttu-id="f1acb-151">Путь к дополнительному файлу *.deps.json*.</span><span class="sxs-lookup"><span data-stu-id="f1acb-151">Path to an additional *.deps.json* file.</span></span> <span data-ttu-id="f1acb-152">Файл *deps.json* содержит список зависимостей, зависимости компиляции и сведения о версии, используемые для устранения конфликтов сборок.</span><span class="sxs-lookup"><span data-stu-id="f1acb-152">A *deps.json* file contains a list of dependencies, compilation dependencies, and version information used to address assembly conflicts.</span></span> <span data-ttu-id="f1acb-153">Дополнительные сведения см. в разделе [Файлы конфигурации среды выполнения](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) на GitHub.</span><span class="sxs-lookup"><span data-stu-id="f1acb-153">For more information, see [Runtime Configuration Files](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) on GitHub.</span></span>

- **`--fx-version <VERSION>`**

  <span data-ttu-id="f1acb-154">Версия среды выполнения .NET Core, используемой для запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="f1acb-154">Version of the .NET Core runtime to use to run the application.</span></span>

- **`--runtimeconfig`**

  <span data-ttu-id="f1acb-155">Путь к файлу *runtimeconfig.json*.</span><span class="sxs-lookup"><span data-stu-id="f1acb-155">Path to a *runtimeconfig.json* file.</span></span> <span data-ttu-id="f1acb-156">Файл *runtimeconfig.json* представляет собой файл конфигурации, содержащий параметры среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="f1acb-156">A *runtimeconfig.json* file is a configuration file that contains run-time settings.</span></span> <span data-ttu-id="f1acb-157">Дополнительные сведения см. в статье [Параметры конфигурации среды выполнения .NET Core](../run-time-config/index.md#runtimeconfigjson).</span><span class="sxs-lookup"><span data-stu-id="f1acb-157">For more information, see [.NET Core run-time configuration settings](../run-time-config/index.md#runtimeconfigjson).</span></span>

- <span data-ttu-id="f1acb-158">**`--roll-forward-on-no-candidate-fx <N>`** **Доступно в пакете SDK для .NET Core 2.x.**</span><span class="sxs-lookup"><span data-stu-id="f1acb-158">**`--roll-forward-on-no-candidate-fx <N>`** **Available in .NET Core 2.x SDK.**</span></span>

  <span data-ttu-id="f1acb-159">Определяет поведение, когда требуемая общая платформа недоступна.</span><span class="sxs-lookup"><span data-stu-id="f1acb-159">Defines behavior when the required shared framework is not available.</span></span> <span data-ttu-id="f1acb-160">Параметр `N` может принимать следующие значения:</span><span class="sxs-lookup"><span data-stu-id="f1acb-160">`N` can be:</span></span>

  - <span data-ttu-id="f1acb-161">`0` — отключает увеличение дополнительных версий.</span><span class="sxs-lookup"><span data-stu-id="f1acb-161">`0` - Disable even minor version roll forward.</span></span>
  - <span data-ttu-id="f1acb-162">`1` — позволяет увеличивать дополнительный номер версии, но не основной.</span><span class="sxs-lookup"><span data-stu-id="f1acb-162">`1` - Roll forward on minor version, but not on major version.</span></span> <span data-ttu-id="f1acb-163">Это поведение установлено по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f1acb-163">This is the default behavior.</span></span>
  - <span data-ttu-id="f1acb-164">`2` — включает увеличение основных и дополнительных версий.</span><span class="sxs-lookup"><span data-stu-id="f1acb-164">`2` - Roll forward on minor and major versions.</span></span>

   <span data-ttu-id="f1acb-165">Дополнительные сведения о накате можно найти в [этой статье](../whats-new/dotnet-core-2-1.md#roll-forward).</span><span class="sxs-lookup"><span data-stu-id="f1acb-165">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

- <span data-ttu-id="f1acb-166">**`--roll-forward <SETTING>`** **Доступно, начиная с пакета SDK для .NET Core 3.0.**</span><span class="sxs-lookup"><span data-stu-id="f1acb-166">**`--roll-forward <SETTING>`** **Available starting with .NET Core SDK 3.0.**</span></span>

  <span data-ttu-id="f1acb-167">Управляет применением наката к приложению.</span><span class="sxs-lookup"><span data-stu-id="f1acb-167">Controls how roll forward is applied to the app.</span></span> <span data-ttu-id="f1acb-168">`SETTING` может иметь одно из следующих значений.</span><span class="sxs-lookup"><span data-stu-id="f1acb-168">The `SETTING` can be one of the following values.</span></span> <span data-ttu-id="f1acb-169">Если тип не указан, по умолчанию используется вариант `Minor`.</span><span class="sxs-lookup"><span data-stu-id="f1acb-169">If not specified, `Minor` is the default.</span></span>

  - <span data-ttu-id="f1acb-170">`LatestPatch` — накат до версии с наибольшим номером исправления.</span><span class="sxs-lookup"><span data-stu-id="f1acb-170">`LatestPatch` - Roll forward to the highest patch version.</span></span> <span data-ttu-id="f1acb-171">Отключает накат дополнительных версий.</span><span class="sxs-lookup"><span data-stu-id="f1acb-171">This disables minor version roll forward.</span></span>
  - <span data-ttu-id="f1acb-172">`Minor` — накат до дополнительной версии со следующим по порядку возрастания номером, если запрошенная дополнительная версия отсутствует.</span><span class="sxs-lookup"><span data-stu-id="f1acb-172">`Minor` - Roll forward to the lowest higher minor version, if requested minor version is missing.</span></span> <span data-ttu-id="f1acb-173">Если запрошенная дополнительная версия присутствует, используется политика LatestPatch.</span><span class="sxs-lookup"><span data-stu-id="f1acb-173">If the requested minor version is present, then the LatestPatch policy is used.</span></span>
  - <span data-ttu-id="f1acb-174">`Major` — накат до основной версии со следующим по порядку возрастания или дополнительной версии с наименьшим номером, если запрошенная дополнительная версия отсутствует.</span><span class="sxs-lookup"><span data-stu-id="f1acb-174">`Major` - Roll forward to lowest higher major version, and lowest minor version, if requested major version is missing.</span></span> <span data-ttu-id="f1acb-175">Если запрошенная основная версия присутствует, используется политика Minor.</span><span class="sxs-lookup"><span data-stu-id="f1acb-175">If the requested major version is present, then the Minor policy is used.</span></span>
  - <span data-ttu-id="f1acb-176">`LatestMinor` — накат до дополнительной версии с наибольшим номером, даже если запрошенная дополнительная версия присутствует.</span><span class="sxs-lookup"><span data-stu-id="f1acb-176">`LatestMinor` - Roll forward to highest minor version, even if requested minor version is present.</span></span> <span data-ttu-id="f1acb-177">Предназначен для сценариев размещения компонентов.</span><span class="sxs-lookup"><span data-stu-id="f1acb-177">Intended for component hosting scenarios.</span></span>
  - <span data-ttu-id="f1acb-178">`LatestMajor` — накат до основной версии с наибольшим номером и дополнительной версии с наибольшим номером, даже если запрошенная основная версия присутствует.</span><span class="sxs-lookup"><span data-stu-id="f1acb-178">`LatestMajor` - Roll forward to highest major and highest minor version, even if requested major is present.</span></span> <span data-ttu-id="f1acb-179">Предназначен для сценариев размещения компонентов.</span><span class="sxs-lookup"><span data-stu-id="f1acb-179">Intended for component hosting scenarios.</span></span>
  - <span data-ttu-id="f1acb-180">`Disable` — накат не выполняется.</span><span class="sxs-lookup"><span data-stu-id="f1acb-180">`Disable` - Don't roll forward.</span></span> <span data-ttu-id="f1acb-181">Привязка только к указанной версии.</span><span class="sxs-lookup"><span data-stu-id="f1acb-181">Only bind to specified version.</span></span> <span data-ttu-id="f1acb-182">Эта политика не рекомендуется для общего использования, поскольку отключает возможность наката до последних исправлений.</span><span class="sxs-lookup"><span data-stu-id="f1acb-182">This policy isn't recommended for general use because it disables the ability to roll forward to the latest patches.</span></span> <span data-ttu-id="f1acb-183">Это значение рекомендуется использовать только для тестирования.</span><span class="sxs-lookup"><span data-stu-id="f1acb-183">This value is only recommended for testing.</span></span>

<span data-ttu-id="f1acb-184">Все параметры, кроме параметра `Disable`, будут использовать версию с последним доступным исправлением.</span><span class="sxs-lookup"><span data-stu-id="f1acb-184">With the exception of `Disable`, all settings will use the highest available patch version.</span></span>

<span data-ttu-id="f1acb-185">Поведение наката также можно настроить в свойствах файла проекта, файла конфигурации среды выполнения и переменной среды.</span><span class="sxs-lookup"><span data-stu-id="f1acb-185">Roll forward behavior can also be configured in a project file property, a run-time configuration file property, and an environment variable.</span></span> <span data-ttu-id="f1acb-186">Дополнительные сведения см. в разделе [Накат основной версии среды выполнения](../whats-new/dotnet-core-3-0.md#major-version-runtime-roll-forward).</span><span class="sxs-lookup"><span data-stu-id="f1acb-186">For more information, see [Major-version runtime roll forward](../whats-new/dotnet-core-3-0.md#major-version-runtime-roll-forward).</span></span>

## <a name="dotnet-commands"></a><span data-ttu-id="f1acb-187">Команды dotnet</span><span class="sxs-lookup"><span data-stu-id="f1acb-187">dotnet commands</span></span>

### <a name="general"></a><span data-ttu-id="f1acb-188">Общее</span><span class="sxs-lookup"><span data-stu-id="f1acb-188">General</span></span>

| <span data-ttu-id="f1acb-189">Команда</span><span class="sxs-lookup"><span data-stu-id="f1acb-189">Command</span></span>                                       | <span data-ttu-id="f1acb-190">Функция</span><span class="sxs-lookup"><span data-stu-id="f1acb-190">Function</span></span>                                                            |
| --------------------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="f1acb-191">dotnet build</span><span class="sxs-lookup"><span data-stu-id="f1acb-191">dotnet build</span></span>](dotnet-build.md)               | <span data-ttu-id="f1acb-192">Выполняет сборку приложения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f1acb-192">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="f1acb-193">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="f1acb-193">dotnet build-server</span></span>](dotnet-build-server.md) | <span data-ttu-id="f1acb-194">Взаимодействует с серверами, запущенными сборкой.</span><span class="sxs-lookup"><span data-stu-id="f1acb-194">Interacts with servers started by a build.</span></span>                          |
| [<span data-ttu-id="f1acb-195">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="f1acb-195">dotnet clean</span></span>](dotnet-clean.md)               | <span data-ttu-id="f1acb-196">Очищает выходные данные сборки.</span><span class="sxs-lookup"><span data-stu-id="f1acb-196">Clean build outputs.</span></span>                                                |
| [<span data-ttu-id="f1acb-197">dotnet help</span><span class="sxs-lookup"><span data-stu-id="f1acb-197">dotnet help</span></span>](dotnet-help.md)                 | <span data-ttu-id="f1acb-198">Выводит более подробную документацию из Интернета для команды.</span><span class="sxs-lookup"><span data-stu-id="f1acb-198">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="f1acb-199">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="f1acb-199">dotnet migrate</span></span>](dotnet-migrate.md)           | <span data-ttu-id="f1acb-200">Переносит допустимый проект предварительной версии 2 в проект пакета SDK .NET Core 1.0.</span><span class="sxs-lookup"><span data-stu-id="f1acb-200">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="f1acb-201">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="f1acb-201">dotnet msbuild</span></span>](dotnet-msbuild.md)           | <span data-ttu-id="f1acb-202">Обеспечивает доступ к командной строке MSBuild.</span><span class="sxs-lookup"><span data-stu-id="f1acb-202">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="f1acb-203">dotnet new</span><span class="sxs-lookup"><span data-stu-id="f1acb-203">dotnet new</span></span>](dotnet-new.md)                   | <span data-ttu-id="f1acb-204">Инициализирует проект C# или F# для заданного шаблона.</span><span class="sxs-lookup"><span data-stu-id="f1acb-204">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="f1acb-205">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="f1acb-205">dotnet pack</span></span>](dotnet-pack.md)                 | <span data-ttu-id="f1acb-206">Создает пакет NuGet с кодом.</span><span class="sxs-lookup"><span data-stu-id="f1acb-206">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="f1acb-207">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="f1acb-207">dotnet publish</span></span>](dotnet-publish.md)           | <span data-ttu-id="f1acb-208">Публикует платформозависимое или автономное приложение .NET.</span><span class="sxs-lookup"><span data-stu-id="f1acb-208">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="f1acb-209">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="f1acb-209">dotnet restore</span></span>](dotnet-restore.md)           | <span data-ttu-id="f1acb-210">Восстанавливает зависимости для данного приложения.</span><span class="sxs-lookup"><span data-stu-id="f1acb-210">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="f1acb-211">dotnet run</span><span class="sxs-lookup"><span data-stu-id="f1acb-211">dotnet run</span></span>](dotnet-run.md)                   | <span data-ttu-id="f1acb-212">Запускает приложение из источника.</span><span class="sxs-lookup"><span data-stu-id="f1acb-212">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="f1acb-213">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="f1acb-213">dotnet sln</span></span>](dotnet-sln.md)                   | <span data-ttu-id="f1acb-214">Параметры для добавления, удаления и перечисления проектов в файле решения.</span><span class="sxs-lookup"><span data-stu-id="f1acb-214">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="f1acb-215">dotnet store</span><span class="sxs-lookup"><span data-stu-id="f1acb-215">dotnet store</span></span>](dotnet-store.md)               | <span data-ttu-id="f1acb-216">Сохраняет сборки в хранилище пакетов среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="f1acb-216">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="f1acb-217">dotnet test</span><span class="sxs-lookup"><span data-stu-id="f1acb-217">dotnet test</span></span>](dotnet-test.md)                 | <span data-ttu-id="f1acb-218">Выполняет тесты с помощью средства запуска тестов.</span><span class="sxs-lookup"><span data-stu-id="f1acb-218">Runs tests using a test runner.</span></span>                                     |

### <a name="project-references"></a><span data-ttu-id="f1acb-219">Ссылки на проекты</span><span class="sxs-lookup"><span data-stu-id="f1acb-219">Project references</span></span>

<span data-ttu-id="f1acb-220">Команда</span><span class="sxs-lookup"><span data-stu-id="f1acb-220">Command</span></span> | <span data-ttu-id="f1acb-221">Функция</span><span class="sxs-lookup"><span data-stu-id="f1acb-221">Function</span></span>
--- | ---
[<span data-ttu-id="f1acb-222">dotnet add reference</span><span class="sxs-lookup"><span data-stu-id="f1acb-222">dotnet add reference</span></span>](dotnet-add-reference.md) | <span data-ttu-id="f1acb-223">Добавляет ссылку на проект.</span><span class="sxs-lookup"><span data-stu-id="f1acb-223">Adds a project reference.</span></span>
[<span data-ttu-id="f1acb-224">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="f1acb-224">dotnet list reference</span></span>](dotnet-list-reference.md) | <span data-ttu-id="f1acb-225">Перечисляет ссылки на проекты.</span><span class="sxs-lookup"><span data-stu-id="f1acb-225">Lists project references.</span></span>
[<span data-ttu-id="f1acb-226">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="f1acb-226">dotnet remove reference</span></span>](dotnet-remove-reference.md) | <span data-ttu-id="f1acb-227">Удаляет ссылку на проект.</span><span class="sxs-lookup"><span data-stu-id="f1acb-227">Removes a project reference.</span></span>

### <a name="nuget-packages"></a><span data-ttu-id="f1acb-228">Пакеты NuGet</span><span class="sxs-lookup"><span data-stu-id="f1acb-228">NuGet packages</span></span>

<span data-ttu-id="f1acb-229">Команда</span><span class="sxs-lookup"><span data-stu-id="f1acb-229">Command</span></span> | <span data-ttu-id="f1acb-230">Функция</span><span class="sxs-lookup"><span data-stu-id="f1acb-230">Function</span></span>
--- | ---
[<span data-ttu-id="f1acb-231">dotnet add package</span><span class="sxs-lookup"><span data-stu-id="f1acb-231">dotnet add package</span></span>](dotnet-add-package.md) | <span data-ttu-id="f1acb-232">Добавляет пакет NuGet.</span><span class="sxs-lookup"><span data-stu-id="f1acb-232">Adds a NuGet package.</span></span>
[<span data-ttu-id="f1acb-233">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="f1acb-233">dotnet remove package</span></span>](dotnet-remove-package.md) | <span data-ttu-id="f1acb-234">Удаляет пакет NuGet.</span><span class="sxs-lookup"><span data-stu-id="f1acb-234">Removes a NuGet package.</span></span>

### <a name="nuget-commands"></a><span data-ttu-id="f1acb-235">Команды NuGet</span><span class="sxs-lookup"><span data-stu-id="f1acb-235">NuGet commands</span></span>

<span data-ttu-id="f1acb-236">Команда</span><span class="sxs-lookup"><span data-stu-id="f1acb-236">Command</span></span> | <span data-ttu-id="f1acb-237">Функция</span><span class="sxs-lookup"><span data-stu-id="f1acb-237">Function</span></span>
--- | ---
[<span data-ttu-id="f1acb-238">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="f1acb-238">dotnet nuget delete</span></span>](dotnet-nuget-delete.md) | <span data-ttu-id="f1acb-239">Удаляет пакет с сервера или из списка.</span><span class="sxs-lookup"><span data-stu-id="f1acb-239">Deletes or unlists a package from the server.</span></span>
[<span data-ttu-id="f1acb-240">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="f1acb-240">dotnet nuget push</span></span>](dotnet-nuget-push.md) | <span data-ttu-id="f1acb-241">Отправляет пакет на сервер и публикует его.</span><span class="sxs-lookup"><span data-stu-id="f1acb-241">Pushes a package to the server and publishes it.</span></span>
[<span data-ttu-id="f1acb-242">dotnet nuget locals</span><span class="sxs-lookup"><span data-stu-id="f1acb-242">dotnet nuget locals</span></span>](dotnet-nuget-locals.md) | <span data-ttu-id="f1acb-243">Очищает или перечисляет локальные ресурсы NuGet в кэше HTTP-запросов, временном кэше или папке пакетов, используемой на уровне компьютера.</span><span class="sxs-lookup"><span data-stu-id="f1acb-243">Clears or lists local NuGet resources such as http-request cache, temporary cache, or machine-wide global packages folder.</span></span>
[<span data-ttu-id="f1acb-244">dotnet nuget add source</span><span class="sxs-lookup"><span data-stu-id="f1acb-244">dotnet nuget add source</span></span>](dotnet-nuget-add-source.md) | <span data-ttu-id="f1acb-245">Добавляет источник NuGet.</span><span class="sxs-lookup"><span data-stu-id="f1acb-245">Adds a NuGet source.</span></span>
[<span data-ttu-id="f1acb-246">dotnet nuget disable source</span><span class="sxs-lookup"><span data-stu-id="f1acb-246">dotnet nuget disable source</span></span>](dotnet-nuget-disable-source.md) | <span data-ttu-id="f1acb-247">Отключает источник NuGet.</span><span class="sxs-lookup"><span data-stu-id="f1acb-247">Disables a NuGet source.</span></span>
[<span data-ttu-id="f1acb-248">dotnet nuget enable source</span><span class="sxs-lookup"><span data-stu-id="f1acb-248">dotnet nuget enable source</span></span>](dotnet-nuget-enable-source.md) | <span data-ttu-id="f1acb-249">Включает источник NuGet.</span><span class="sxs-lookup"><span data-stu-id="f1acb-249">Enables a NuGet source.</span></span>
[<span data-ttu-id="f1acb-250">dotnet nuget list source</span><span class="sxs-lookup"><span data-stu-id="f1acb-250">dotnet nuget list source</span></span>](dotnet-nuget-list-source.md) | <span data-ttu-id="f1acb-251">Перечисляет все настроенные источники NuGet.</span><span class="sxs-lookup"><span data-stu-id="f1acb-251">Lists all configured NuGet sources.</span></span>
[<span data-ttu-id="f1acb-252">dotnet nuget remove source</span><span class="sxs-lookup"><span data-stu-id="f1acb-252">dotnet nuget remove source</span></span>](dotnet-nuget-remove-source.md) | <span data-ttu-id="f1acb-253">Удаляет источник NuGet.</span><span class="sxs-lookup"><span data-stu-id="f1acb-253">Removes a NuGet source.</span></span>
[<span data-ttu-id="f1acb-254">dotnet nuget update source</span><span class="sxs-lookup"><span data-stu-id="f1acb-254">dotnet nuget update source</span></span>](dotnet-nuget-update-source.md) | <span data-ttu-id="f1acb-255">Обновляет источник NuGet.</span><span class="sxs-lookup"><span data-stu-id="f1acb-255">Updates a NuGet source.</span></span>

### <a name="global-tool-path-and-local-tools-commands"></a><span data-ttu-id="f1acb-256">Команды глобального, установочного и локального средства</span><span class="sxs-lookup"><span data-stu-id="f1acb-256">Global, tool-path, and local tools commands</span></span>

<span data-ttu-id="f1acb-257">Средства — это консольные приложения, которые устанавливаются из пакетов NuGet и вызываются из командной строки.</span><span class="sxs-lookup"><span data-stu-id="f1acb-257">Tools are console applications that are installed from NuGet packages and are invoked from the command prompt.</span></span> <span data-ttu-id="f1acb-258">Вы можете писать средства самостоятельно или устанавливать средства, написанные другими.</span><span class="sxs-lookup"><span data-stu-id="f1acb-258">You can write tools yourself or install tools written by third parties.</span></span> <span data-ttu-id="f1acb-259">Средства также называются глобальными средствами, средствами пути к средству и локальными средствами.</span><span class="sxs-lookup"><span data-stu-id="f1acb-259">Tools are also known as global tools, tool-path tools, and local tools.</span></span> <span data-ttu-id="f1acb-260">Дополнительные сведения см. в [обзоре средств .NET Core](global-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f1acb-260">For more information, see [.NET Core tools overview](global-tools.md).</span></span> <span data-ttu-id="f1acb-261">Глобальные и установочные средства доступны, начиная с версии пакета SDK .NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="f1acb-261">Global and tool-path tools are available starting with .NET Core SDK 2.1.</span></span> <span data-ttu-id="f1acb-262">Локальные средства доступны в пакете SDK для .NET Core, начиная с версии 3.0.</span><span class="sxs-lookup"><span data-stu-id="f1acb-262">Local tools are available starting with .NET Core SDK 3.0.</span></span>

<span data-ttu-id="f1acb-263">Команда</span><span class="sxs-lookup"><span data-stu-id="f1acb-263">Command</span></span> | <span data-ttu-id="f1acb-264">Функция</span><span class="sxs-lookup"><span data-stu-id="f1acb-264">Function</span></span>
--- | ---
[<span data-ttu-id="f1acb-265">dotnet tool install</span><span class="sxs-lookup"><span data-stu-id="f1acb-265">dotnet tool install</span></span>](dotnet-tool-install.md) | <span data-ttu-id="f1acb-266">Устанавливает средство на компьютере.</span><span class="sxs-lookup"><span data-stu-id="f1acb-266">Installs a tool on your machine.</span></span>
[<span data-ttu-id="f1acb-267">dotnet tool list</span><span class="sxs-lookup"><span data-stu-id="f1acb-267">dotnet tool list</span></span>](dotnet-tool-list.md) | <span data-ttu-id="f1acb-268">Выводит все глобальные, установочные и локальные средства, установленные на компьютере.</span><span class="sxs-lookup"><span data-stu-id="f1acb-268">Lists all global, tool-path, or local tools currently installed on your machine.</span></span>
[<span data-ttu-id="f1acb-269">dotnet tool uninstall</span><span class="sxs-lookup"><span data-stu-id="f1acb-269">dotnet tool uninstall</span></span>](dotnet-tool-uninstall.md) | <span data-ttu-id="f1acb-270">Удаляет средство с компьютера.</span><span class="sxs-lookup"><span data-stu-id="f1acb-270">Uninstalls a tool from your machine.</span></span>
[<span data-ttu-id="f1acb-271">dotnet tool update</span><span class="sxs-lookup"><span data-stu-id="f1acb-271">dotnet tool update</span></span>](dotnet-tool-update.md) | <span data-ttu-id="f1acb-272">Обновляет средство, установленное на компьютере.</span><span class="sxs-lookup"><span data-stu-id="f1acb-272">Updates a tool that is installed on your machine.</span></span>

### <a name="additional-tools"></a><span data-ttu-id="f1acb-273">Дополнительные средства</span><span class="sxs-lookup"><span data-stu-id="f1acb-273">Additional tools</span></span>

<span data-ttu-id="f1acb-274">Ряд средств, которые ранее были доступны только для отдельных проектов через `DotnetCliToolReference`, стали частью пакета SDK для .NET начиная с версии 2.1.300.</span><span class="sxs-lookup"><span data-stu-id="f1acb-274">Starting with .NET Core SDK 2.1.300, a number of tools that were available only on a per project basis using `DotnetCliToolReference` are now available as part of the .NET Core SDK.</span></span> <span data-ttu-id="f1acb-275">Эти средства перечислены в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="f1acb-275">These tools are listed in the following table:</span></span>

| <span data-ttu-id="f1acb-276">Средство</span><span class="sxs-lookup"><span data-stu-id="f1acb-276">Tool</span></span>                                              | <span data-ttu-id="f1acb-277">Функция</span><span class="sxs-lookup"><span data-stu-id="f1acb-277">Function</span></span>                                                     |
| ------------------------------------------------- | ------------------------------------------------------------ |
| <span data-ttu-id="f1acb-278">dev-certs</span><span class="sxs-lookup"><span data-stu-id="f1acb-278">dev-certs</span></span>                                         | <span data-ttu-id="f1acb-279">Создает сертификаты разработки и управляет ими.</span><span class="sxs-lookup"><span data-stu-id="f1acb-279">Creates and manages development certificates.</span></span>                |
| [<span data-ttu-id="f1acb-280">ef</span><span class="sxs-lookup"><span data-stu-id="f1acb-280">ef</span></span>](/ef/core/miscellaneous/cli/dotnet)           | <span data-ttu-id="f1acb-281">Средства командной строки для Entity Framework Core.</span><span class="sxs-lookup"><span data-stu-id="f1acb-281">Entity Framework Core command-line tools.</span></span>                    |
| <span data-ttu-id="f1acb-282">sql-cache</span><span class="sxs-lookup"><span data-stu-id="f1acb-282">sql-cache</span></span>                                         | <span data-ttu-id="f1acb-283">Средства командной строки для кэша SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f1acb-283">SQL Server cache command-line tools.</span></span>                         |
| [<span data-ttu-id="f1acb-284">user-secrets</span><span class="sxs-lookup"><span data-stu-id="f1acb-284">user-secrets</span></span>](/aspnet/core/security/app-secrets) | <span data-ttu-id="f1acb-285">Управляет секретами пользователей для разработки.</span><span class="sxs-lookup"><span data-stu-id="f1acb-285">Manages development user secrets.</span></span>                            |
| [<span data-ttu-id="f1acb-286">watch</span><span class="sxs-lookup"><span data-stu-id="f1acb-286">watch</span></span>](/aspnet/core/tutorials/dotnet-watch)      | <span data-ttu-id="f1acb-287">Запускает наблюдатель за файлами, который выполняет команду при изменении файлов.</span><span class="sxs-lookup"><span data-stu-id="f1acb-287">Starts a file watcher that runs a command when files change.</span></span> |

<span data-ttu-id="f1acb-288">Дополнительные сведения о каждом средстве можно получить с помощью команды `dotnet <tool-name> --help`.</span><span class="sxs-lookup"><span data-stu-id="f1acb-288">For more information about each tool, type `dotnet <tool-name> --help`.</span></span>

## <a name="examples"></a><span data-ttu-id="f1acb-289">Примеры</span><span class="sxs-lookup"><span data-stu-id="f1acb-289">Examples</span></span>

<span data-ttu-id="f1acb-290">Создание консольного приложения .NET Core:</span><span class="sxs-lookup"><span data-stu-id="f1acb-290">Create a new .NET Core console application:</span></span>

```dotnetcli
dotnet new console
```

<span data-ttu-id="f1acb-291">Сборка проекта и его зависимостей в указанном каталоге:</span><span class="sxs-lookup"><span data-stu-id="f1acb-291">Build a project and its dependencies in a given directory:</span></span>

```dotnetcli
dotnet build
```

<span data-ttu-id="f1acb-292">Запуск приложения:</span><span class="sxs-lookup"><span data-stu-id="f1acb-292">Run an application:</span></span>

```dotnetcli
dotnet myapp.dll
```

## <a name="environment-variables"></a><span data-ttu-id="f1acb-293">Переменные среды</span><span class="sxs-lookup"><span data-stu-id="f1acb-293">Environment variables</span></span>

- <span data-ttu-id="f1acb-294">`DOTNET_ROOT`, `DOTNET_ROOT(x86)`</span><span class="sxs-lookup"><span data-stu-id="f1acb-294">`DOTNET_ROOT`, `DOTNET_ROOT(x86)`</span></span>

  <span data-ttu-id="f1acb-295">Указывает расположение сред выполнения .NET Core, если оно отличается от задаваемого по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f1acb-295">Specifies the location of the .NET Core runtimes, if they are not installed in the default location.</span></span> <span data-ttu-id="f1acb-296">В ОС Windows по умолчанию используется расположение `C:\Program Files\dotnet`.</span><span class="sxs-lookup"><span data-stu-id="f1acb-296">The default location on Windows is `C:\Program Files\dotnet`.</span></span> <span data-ttu-id="f1acb-297">В ОС Linux и macOS по умолчанию используется расположение `/usr/share/dotnet`.</span><span class="sxs-lookup"><span data-stu-id="f1acb-297">The default location on Linux and macOS is `/usr/share/dotnet`.</span></span> <span data-ttu-id="f1acb-298">Эта переменная среды используется только при запуске приложений с помощью созданных исполняемых файлов (apphost).</span><span class="sxs-lookup"><span data-stu-id="f1acb-298">This environment variable is used only when running apps via generated executables (apphosts).</span></span> <span data-ttu-id="f1acb-299">При запуске 32-разрядного исполняемого файла в 64-разрядной ОС вместо нее используется `DOTNET_ROOT(x86)`.</span><span class="sxs-lookup"><span data-stu-id="f1acb-299">`DOTNET_ROOT(x86)` is used instead when running a 32-bit executable on a 64-bit OS.</span></span>

- `DOTNET_PACKAGES`

  <span data-ttu-id="f1acb-300">Папка глобальных пакетов.</span><span class="sxs-lookup"><span data-stu-id="f1acb-300">The global packages folder.</span></span> <span data-ttu-id="f1acb-301">Если значение не задано, то по умолчанию в Unix используется `~/.nuget/packages`, а в Windows — `%userprofile%\.nuget\packages`.</span><span class="sxs-lookup"><span data-stu-id="f1acb-301">If not set, it defaults to `~/.nuget/packages` on Unix or `%userprofile%\.nuget\packages` on Windows.</span></span>

- `DOTNET_SERVICING`

  <span data-ttu-id="f1acb-302">Задает расположение служебного индекса, который будет использоваться общим узлом при загрузке среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="f1acb-302">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

- `DOTNET_NOLOGO`

  <span data-ttu-id="f1acb-303">Указывает, отображаются ли сообщения приветствия и данные телеметрии .NET Core при первом запуске.</span><span class="sxs-lookup"><span data-stu-id="f1acb-303">Specifies whether .NET Core welcome and telemetry messages are displayed on first run.</span></span> <span data-ttu-id="f1acb-304">Установите значение `true` для отключения звука этих сообщений (принимаются значения `true`, `1` или `yes`) или установите значение `false` для разрешения звука (принимаются значения `false`, `0` или `no`).</span><span class="sxs-lookup"><span data-stu-id="f1acb-304">Set to `true` to mute these messages (values `true`, `1`, or `yes` accepted) or set to `false` to allow (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="f1acb-305">Если не задано, по умолчанию используется `false` и при первом запуске будут отображаться сообщения.</span><span class="sxs-lookup"><span data-stu-id="f1acb-305">If not set, the default is `false` and the messages will be displayed on first run.</span></span> <span data-ttu-id="f1acb-306">Этот флаг не влияет на данные телеметрии (см. `DOTNET_CLI_TELEMETRY_OPTOUT`, чтобы отменить отправку телеметрии).</span><span class="sxs-lookup"><span data-stu-id="f1acb-306">This flag has no effect on telemetry (see `DOTNET_CLI_TELEMETRY_OPTOUT` for opting out of sending telemetry).</span></span>

- `DOTNET_CLI_TELEMETRY_OPTOUT`

  <span data-ttu-id="f1acb-307">Указывает, собираются ли данные по использованию средств .NET Core для отправки в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="f1acb-307">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="f1acb-308">Установите значение `true`, чтобы отказаться от функций телеметрии (поддерживаются значения `true`, `1` или `yes`).</span><span class="sxs-lookup"><span data-stu-id="f1acb-308">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="f1acb-309">Также можно установить значение `false`, чтобы согласиться на функции телеметрии (поддерживаются значения `false`, `0` или `no`).</span><span class="sxs-lookup"><span data-stu-id="f1acb-309">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="f1acb-310">Если значение не задано, то по умолчанию используется `false`, то есть функция телеметрии включена.</span><span class="sxs-lookup"><span data-stu-id="f1acb-310">If not set, the default is `false` and the telemetry feature is active.</span></span>

- `DOTNET_MULTILEVEL_LOOKUP`

  <span data-ttu-id="f1acb-311">Указывает, разрешается ли из глобального расположения среда выполнения .NET Core, общая платформа или пакет SDK.</span><span class="sxs-lookup"><span data-stu-id="f1acb-311">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="f1acb-312">Если не задано, используется значение по умолчанию 1 (логическое значение `true`).</span><span class="sxs-lookup"><span data-stu-id="f1acb-312">If not set, it defaults to 1 (logical `true`).</span></span> <span data-ttu-id="f1acb-313">Задайте значение 0 (логическое значение `false`), чтобы не разрешать эти сущности из глобального расположения и использовать изолированные установки .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f1acb-313">Set to 0 (logical `false`) to not resolve from the global location and have isolated .NET Core installations.</span></span> <span data-ttu-id="f1acb-314">Дополнительные сведения о многоуровневом поиске см. в разделе [Многоуровневый поиск SharedFX](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span><span class="sxs-lookup"><span data-stu-id="f1acb-314">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

- <span data-ttu-id="f1acb-315">`DOTNET_ROLL_FORWARD` **Доступно, начиная с пакета SDK для .NET Core 3.x.**</span><span class="sxs-lookup"><span data-stu-id="f1acb-315">`DOTNET_ROLL_FORWARD` **Available starting with .NET Core 3.x SDK.**</span></span>

  <span data-ttu-id="f1acb-316">Определяет поведение наката.</span><span class="sxs-lookup"><span data-stu-id="f1acb-316">Determines roll forward behavior.</span></span> <span data-ttu-id="f1acb-317">Дополнительные сведения см. в описании параметра `--roll-forward`, приведенном выше в этой статье.</span><span class="sxs-lookup"><span data-stu-id="f1acb-317">For more information, see the `--roll-forward` option earlier in this article.</span></span>

- <span data-ttu-id="f1acb-318">`DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX` **Доступно в пакете SDK для .NET Core 2.x.**</span><span class="sxs-lookup"><span data-stu-id="f1acb-318">`DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX` **Available in .NET Core 2.x SDK.**</span></span>

  <span data-ttu-id="f1acb-319">Отключает накат дополнительных версий, если установлено `0`.</span><span class="sxs-lookup"><span data-stu-id="f1acb-319">Disables minor version roll forward, if set to `0`.</span></span> <span data-ttu-id="f1acb-320">Дополнительные сведения о накате можно найти в [этой статье](../whats-new/dotnet-core-2-1.md#roll-forward).</span><span class="sxs-lookup"><span data-stu-id="f1acb-320">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

- `DOTNET_CLI_UI_LANGUAGE`

  <span data-ttu-id="f1acb-321">Задает язык пользовательского интерфейса CLI с помощью значения языкового стандарта, например `en-us`.</span><span class="sxs-lookup"><span data-stu-id="f1acb-321">Sets the language of the CLI UI using a locale value such as `en-us`.</span></span> <span data-ttu-id="f1acb-322">Поддерживаются те же значения, что и для Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f1acb-322">The supported values are the same as for Visual Studio.</span></span> <span data-ttu-id="f1acb-323">Дополнительные сведения см. в разделе, посвященном изменению языка установщика, в [документации по установке Visual Studio](https://docs.microsoft.com/visualstudio/install/install-visual-studio?view=vs-2019).</span><span class="sxs-lookup"><span data-stu-id="f1acb-323">For more information, see the section on changing the installer language in the [Visual Studio installation documentation](https://docs.microsoft.com/visualstudio/install/install-visual-studio?view=vs-2019).</span></span> <span data-ttu-id="f1acb-324">Применяются правила диспетчера ресурсов .NET, в связи с чем вам не нужно выбирать точное соответствие &mdash; можно также выбрать потомков в дереве `CultureInfo`.</span><span class="sxs-lookup"><span data-stu-id="f1acb-324">The .NET resource manager rules apply, so you don't have to pick an exact match&mdash;you can also pick descendants in the `CultureInfo` tree.</span></span> <span data-ttu-id="f1acb-325">Например, если задать значение `fr-CA`, интерфейс командной строки будет находить и использовать переводы `fr`.</span><span class="sxs-lookup"><span data-stu-id="f1acb-325">For example, if you set it to `fr-CA`, the CLI will find and use the `fr` translations.</span></span> <span data-ttu-id="f1acb-326">Если задать язык, который не поддерживается, для интерфейса командной строки будет использоваться английский язык.</span><span class="sxs-lookup"><span data-stu-id="f1acb-326">If you set it to a language that is not supported, the CLI falls back to English.</span></span>

- `DOTNET_DISABLE_GUI_ERRORS`

  <span data-ttu-id="f1acb-327">Для создаваемых исполняемых файлов с поддержкой графического пользовательского интерфейса отключает всплывающее диалоговое окно, которое обычно выводится для определенных классов ошибок.</span><span class="sxs-lookup"><span data-stu-id="f1acb-327">For GUI-enabled generated executables - disables dialog popup, which normally shows for certain classes of errors.</span></span> <span data-ttu-id="f1acb-328">В таких случаях выполняются только запись в `stderr` и выход.</span><span class="sxs-lookup"><span data-stu-id="f1acb-328">It only writes to `stderr` and exits in those cases.</span></span>
  
- `DOTNET_ADDITIONAL_DEPS`

  <span data-ttu-id="f1acb-329">Эквивалентно параметру `--additional-deps` интерфейса командной строки.</span><span class="sxs-lookup"><span data-stu-id="f1acb-329">Equivalent to CLI option `--additional-deps`.</span></span>

- `DOTNET_RUNTIME_ID`

  <span data-ttu-id="f1acb-330">Переопределяет обнаруженный RID.</span><span class="sxs-lookup"><span data-stu-id="f1acb-330">Overrides the detected RID.</span></span>

- `DOTNET_SHARED_STORE`

  <span data-ttu-id="f1acb-331">Расположение общего хранилища, которое в некоторых случаях используется для разрешения сборки.</span><span class="sxs-lookup"><span data-stu-id="f1acb-331">Location of the "shared store" which assembly resolution falls back to in some cases.</span></span>

- `DOTNET_STARTUP_HOOKS`

  <span data-ttu-id="f1acb-332">Список сборок, из которого осуществляется загрузка и выполнение перехватчиков запуска.</span><span class="sxs-lookup"><span data-stu-id="f1acb-332">List of assemblies to load and execute startup hooks from.</span></span>

- <span data-ttu-id="f1acb-333">`COREHOST_TRACE`, `COREHOST_TRACEFILE`, `COREHOST_TRACE_VERBOSITY`</span><span class="sxs-lookup"><span data-stu-id="f1acb-333">`COREHOST_TRACE`, `COREHOST_TRACEFILE`, `COREHOST_TRACE_VERBOSITY`</span></span>

  <span data-ttu-id="f1acb-334">Управляет диагностической трассировкой из компонентов размещения, таких как `dotnet.exe`, `hostfxr` и `hostpolicy`.</span><span class="sxs-lookup"><span data-stu-id="f1acb-334">Controls diagnostics tracing from the hosting components, such as `dotnet.exe`, `hostfxr`, and `hostpolicy`.</span></span>

## <a name="see-also"></a><span data-ttu-id="f1acb-335">См. также</span><span class="sxs-lookup"><span data-stu-id="f1acb-335">See also</span></span>

- [<span data-ttu-id="f1acb-336">Файлы конфигурации среды выполнения</span><span class="sxs-lookup"><span data-stu-id="f1acb-336">Runtime Configuration Files</span></span>](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md)
- [<span data-ttu-id="f1acb-337">Параметры конфигурации среды выполнения .NET Core</span><span class="sxs-lookup"><span data-stu-id="f1acb-337">.NET Core run-time configuration settings</span></span>](../run-time-config/index.md)
