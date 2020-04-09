---
title: Команда dotnet publish
description: Команда dotnet publish публикует решение или проект .NET Core в каталоге.
ms.date: 02/24/2020
ms.openlocfilehash: 0e18220443f3713c86c257fcf401b98ddd716ebc
ms.sourcegitcommit: 961ec21c22d2f1d55c9cc8a7edf2ade1d1fd92e3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2020
ms.locfileid: "80588271"
---
# <a name="dotnet-publish"></a><span data-ttu-id="c7fa5-103">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="c7fa5-103">dotnet publish</span></span>

<span data-ttu-id="c7fa5-104">**Эта статья относится к следующему.** ✔️ SDK для .NET Core 2.1 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="c7fa5-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="c7fa5-105">name</span><span class="sxs-lookup"><span data-stu-id="c7fa5-105">Name</span></span>

<span data-ttu-id="c7fa5-106">`dotnet publish` — публикует приложение и его зависимости в папке для развертывания на размещающей системе.</span><span class="sxs-lookup"><span data-stu-id="c7fa5-106">`dotnet publish` - Publishes the application and its dependencies to a folder for deployment to a hosting system.</span></span>

## <a name="synopsis"></a><span data-ttu-id="c7fa5-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="c7fa5-107">Synopsis</span></span>

```dotnetcli
dotnet publish [<PROJECT>|<SOLUTION>] [-c|--configuration]
    [-f|--framework] [--force] [--interactive] [--manifest]
    [--no-build] [--no-dependencies] [--no-restore] [--nologo]
    [-o|--output] [-r|--runtime] [--self-contained]
    [--no-self-contained] [-v|--verbosity] [--version-suffix]

dotnet publish [-h|--help]
```

## <a name="description"></a><span data-ttu-id="c7fa5-108">Описание</span><span class="sxs-lookup"><span data-stu-id="c7fa5-108">Description</span></span>

<span data-ttu-id="c7fa5-109">`dotnet publish` компилирует приложение, считывает его зависимости, указанные в файле проекта, и публикует итоговый набор файлов в каталоге.</span><span class="sxs-lookup"><span data-stu-id="c7fa5-109">`dotnet publish` compiles the application, reads through its dependencies specified in the project file, and publishes the resulting set of files to a directory.</span></span> <span data-ttu-id="c7fa5-110">Выходные данные включают следующие ресурсы:</span><span class="sxs-lookup"><span data-stu-id="c7fa5-110">The output includes the following assets:</span></span>

- <span data-ttu-id="c7fa5-111">Код на промежуточном языке (IL) в сборке с расширением *DLL*.</span><span class="sxs-lookup"><span data-stu-id="c7fa5-111">Intermediate Language (IL) code in an assembly with a *dll* extension.</span></span>
- <span data-ttu-id="c7fa5-112">Файл *.deps.json*, содержащий все зависимости проекта.</span><span class="sxs-lookup"><span data-stu-id="c7fa5-112">A *.deps.json* file that includes all of the dependencies of the project.</span></span>
- <span data-ttu-id="c7fa5-113">Файл *.runtimeconfig.json*, определяющий общую среду выполнения, которую ожидает приложение, а также другие параметры конфигурации для среды выполнения (например, тип сборки мусора).</span><span class="sxs-lookup"><span data-stu-id="c7fa5-113">A *.runtimeconfig.json* file that specifies the shared runtime that the application expects, as well as other configuration options for the runtime (for example, garbage collection type).</span></span>
- <span data-ttu-id="c7fa5-114">Зависимости приложения, которые копируются из кэша NuGet в выходную папку.</span><span class="sxs-lookup"><span data-stu-id="c7fa5-114">The application's dependencies, which are copied from the NuGet cache into the output folder.</span></span>

<span data-ttu-id="c7fa5-115">Выходные данные команды `dotnet publish` готовы к развертыванию в размещающей системе (например, на сервере, ПК, Mac, ноутбуке) для выполнения.</span><span class="sxs-lookup"><span data-stu-id="c7fa5-115">The `dotnet publish` command's output is ready for deployment to a hosting system (for example, a server, PC, Mac, laptop) for execution.</span></span> <span data-ttu-id="c7fa5-116">Это единственный официальный способ подготовить приложение к развертыванию.</span><span class="sxs-lookup"><span data-stu-id="c7fa5-116">It's the only officially supported way to prepare the application for deployment.</span></span> <span data-ttu-id="c7fa5-117">В зависимости от указанного в проекте типа развертывания размещающая система может как иметь, так и не иметь общую среду выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c7fa5-117">Depending on the type of deployment that the project specifies, the hosting system may or may not have the .NET Core shared runtime installed on it.</span></span> <span data-ttu-id="c7fa5-118">Дополнительные сведения см. в статье [Публикация приложений .NET Core с помощью .NET Core CLI](../deploying/deploy-with-cli.md).</span><span class="sxs-lookup"><span data-stu-id="c7fa5-118">For more information, see [Publish .NET Core apps with the .NET Core CLI](../deploying/deploy-with-cli.md).</span></span>

### <a name="msbuild"></a><span data-ttu-id="c7fa5-119">MSBuild</span><span class="sxs-lookup"><span data-stu-id="c7fa5-119">MSBuild</span></span>

<span data-ttu-id="c7fa5-120">Команда `dotnet publish` вызывает метод MSBuild, который, в свою очередь, вызывает целевой объект `Publish`.</span><span class="sxs-lookup"><span data-stu-id="c7fa5-120">The `dotnet publish` command calls MSBuild, which invokes the `Publish` target.</span></span> <span data-ttu-id="c7fa5-121">Все параметры, передаваемые в `dotnet publish`, передаются далее в MSBuild.</span><span class="sxs-lookup"><span data-stu-id="c7fa5-121">Any parameters passed to `dotnet publish` are passed to MSBuild.</span></span> <span data-ttu-id="c7fa5-122">Параметры `-c` и `-o` сопоставляются со свойствами MSBuild `Configuration` и `OutputPath` соответственно.</span><span class="sxs-lookup"><span data-stu-id="c7fa5-122">The `-c` and `-o` parameters map to MSBuild's `Configuration` and `OutputPath` properties, respectively.</span></span>

<span data-ttu-id="c7fa5-123">Команда `dotnet publish` принимает параметры MSBuild, например `-p` для задания свойств или `-l` для определения средства ведения журнала.</span><span class="sxs-lookup"><span data-stu-id="c7fa5-123">The `dotnet publish` command accepts MSBuild options, such as `-p` for setting properties and `-l` to define a logger.</span></span> <span data-ttu-id="c7fa5-124">Например, можно задать свойство MSBuild, используя формат: `-p:<NAME>=<VALUE>`.</span><span class="sxs-lookup"><span data-stu-id="c7fa5-124">For example, you can set an MSBuild property by using the format: `-p:<NAME>=<VALUE>`.</span></span> <span data-ttu-id="c7fa5-125">Кроме того, задать связанные с публикацией свойства можно, сославшись на файл *PUBXML*, например:</span><span class="sxs-lookup"><span data-stu-id="c7fa5-125">You can also set publish-related properties by referring to a *.pubxml* file, for example:</span></span>

```dotnetcli
dotnet publish -p:PublishProfile=Properties\PublishProfiles\FolderProfile.pubxml
```

<span data-ttu-id="c7fa5-126">Дополнительные сведения см. в следующих ресурсах:</span><span class="sxs-lookup"><span data-stu-id="c7fa5-126">For more information, see the following resources:</span></span>

- [<span data-ttu-id="c7fa5-127">Справочник по командной строке MSBuild</span><span class="sxs-lookup"><span data-stu-id="c7fa5-127">MSBuild command-line reference</span></span>](/visualstudio/msbuild/msbuild-command-line-reference)
- [<span data-ttu-id="c7fa5-128">Профили публикации Visual Studio (.pubxml) для развертывания приложений ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="c7fa5-128">Visual Studio publish profiles (.pubxml) for ASP.NET Core app deployment</span></span>](/aspnet/core/host-and-deploy/visual-studio-publish-profiles)
- [<span data-ttu-id="c7fa5-129">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="c7fa5-129">dotnet msbuild</span></span>](dotnet-msbuild.md)

## <a name="arguments"></a><span data-ttu-id="c7fa5-130">Аргументы</span><span class="sxs-lookup"><span data-stu-id="c7fa5-130">Arguments</span></span>

- **`PROJECT|SOLUTION`**

  <span data-ttu-id="c7fa5-131">Проект или решение для публикации.</span><span class="sxs-lookup"><span data-stu-id="c7fa5-131">The project or solution to publish.</span></span>
  
  * <span data-ttu-id="c7fa5-132">`PROJECT` — это путь или имя файла проекта [C#](csproj.md), F# или Visual Basic либо путь к папке, которая содержит файл проекта C#, F# или Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="c7fa5-132">`PROJECT` is the path and filename of a [C#](csproj.md), F#, or Visual Basic project file, or the path to a directory that contains a C#, F#, or Visual Basic project file.</span></span> <span data-ttu-id="c7fa5-133">Если каталог не указан, по умолчанию используется текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="c7fa5-133">If the directory is not specified, it defaults to the current directory.</span></span>

  * <span data-ttu-id="c7fa5-134">`SOLUTION` — это путь и имя для файла решения (расширение *SLN*) или путь к каталогу, содержащему файл решения.</span><span class="sxs-lookup"><span data-stu-id="c7fa5-134">`SOLUTION` is the path and filename of a solution file (*.sln* extension), or the path to a directory that contains a solution file.</span></span> <span data-ttu-id="c7fa5-135">Если каталог не указан, по умолчанию используется текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="c7fa5-135">If the directory is not specified, it defaults to the current directory.</span></span> <span data-ttu-id="c7fa5-136">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="c7fa5-136">Available since .NET Core 3.0 SDK.</span></span>

## <a name="options"></a><span data-ttu-id="c7fa5-137">Параметры</span><span class="sxs-lookup"><span data-stu-id="c7fa5-137">Options</span></span>

- **`-c|--configuration <CONFIGURATION>`**

  <span data-ttu-id="c7fa5-138">Определяет конфигурацию сборки.</span><span class="sxs-lookup"><span data-stu-id="c7fa5-138">Defines the build configuration.</span></span> <span data-ttu-id="c7fa5-139">По умолчанию для большинства проектов используется `Debug`, но можно переопределить параметры конфигурации сборки в проекте.</span><span class="sxs-lookup"><span data-stu-id="c7fa5-139">The default for most projects is `Debug`, but you can override the build configuration settings in your project.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="c7fa5-140">Публикует приложение для указанной [целевой платформы](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="c7fa5-140">Publishes the application for the specified [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="c7fa5-141">Вам нужно указать целевую платформу в файле проекта.</span><span class="sxs-lookup"><span data-stu-id="c7fa5-141">You must specify the target framework in the project file.</span></span>

- **`--force`**

  <span data-ttu-id="c7fa5-142">Принудительное разрешение всех зависимостей, даже если последнее восстановление прошло успешно.</span><span class="sxs-lookup"><span data-stu-id="c7fa5-142">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="c7fa5-143">Указание этого флага дает тот же результат, что удаление файла *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="c7fa5-143">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

- **`-h|--help`**

  <span data-ttu-id="c7fa5-144">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="c7fa5-144">Prints out a short help for the command.</span></span>

- **`--interactive`**

  <span data-ttu-id="c7fa5-145">Позволяет команде остановиться и дождаться, пока пользователь выполнит действие или введет данные.</span><span class="sxs-lookup"><span data-stu-id="c7fa5-145">Allows the command to stop and wait for user input or action.</span></span> <span data-ttu-id="c7fa5-146">Например, чтобы завершить проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="c7fa5-146">For example, to complete authentication.</span></span> <span data-ttu-id="c7fa5-147">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="c7fa5-147">Available since .NET Core 3.0 SDK.</span></span>

- **`--manifest <PATH_TO_MANIFEST_FILE>`**

  <span data-ttu-id="c7fa5-148">Определяет один или несколько [целевых манифестов](../deploying/runtime-store.md) для усечения множества пакетов, публикуемых вместе с приложением.</span><span class="sxs-lookup"><span data-stu-id="c7fa5-148">Specifies one or several [target manifests](../deploying/runtime-store.md) to use to trim the set of packages published with the app.</span></span> <span data-ttu-id="c7fa5-149">Файл манифеста является частью выходных данных [команды `dotnet store`](dotnet-store.md).</span><span class="sxs-lookup"><span data-stu-id="c7fa5-149">The manifest file is part of the output of the [`dotnet store` command](dotnet-store.md).</span></span> <span data-ttu-id="c7fa5-150">Чтобы указать несколько манифестов, добавьте параметр `--manifest` для каждого из них.</span><span class="sxs-lookup"><span data-stu-id="c7fa5-150">To specify multiple manifests, add a `--manifest` option for each manifest.</span></span>

- **`--no-build`**

  <span data-ttu-id="c7fa5-151">Не выполняет сборку проекта перед публикацией.</span><span class="sxs-lookup"><span data-stu-id="c7fa5-151">Doesn't build the project before publishing.</span></span> <span data-ttu-id="c7fa5-152">Он также неявно задает флаг `--no-restore`.</span><span class="sxs-lookup"><span data-stu-id="c7fa5-152">It also implicitly sets the `--no-restore` flag.</span></span>

- **`--no-dependencies`**

  <span data-ttu-id="c7fa5-153">Межпроектные ссылки игнорируются, и восстанавливается только корневой проект.</span><span class="sxs-lookup"><span data-stu-id="c7fa5-153">Ignores project-to-project references and only restores the root project.</span></span>

- **`--nologo`**

  <span data-ttu-id="c7fa5-154">Скрывает загрузочный баннер или сообщение об авторских правах.</span><span class="sxs-lookup"><span data-stu-id="c7fa5-154">Doesn't display the startup banner or the copyright message.</span></span> <span data-ttu-id="c7fa5-155">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="c7fa5-155">Available since .NET Core 3.0 SDK.</span></span>

- **`--no-restore`**

  <span data-ttu-id="c7fa5-156">Не выполняет неявное восстановление при выполнении команды.</span><span class="sxs-lookup"><span data-stu-id="c7fa5-156">Doesn't execute an implicit restore when running the command.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="c7fa5-157">Задает путь для выходного каталога.</span><span class="sxs-lookup"><span data-stu-id="c7fa5-157">Specifies the path for the output directory.</span></span>
  
  <span data-ttu-id="c7fa5-158">Если значение не указано, для исполняемого файла, зависящего от среды выполнения, а также для кроссплатформенных двоичных файлов по умолчанию используется путь *[папка_файла_проекта]./bin/[конфигурация]/[платформа]/publish/* .</span><span class="sxs-lookup"><span data-stu-id="c7fa5-158">If not specified, it defaults to *[project_file_folder]./bin/[configuration]/[framework]/publish/* for a runtime-dependent executable and cross-platform binaries.</span></span> <span data-ttu-id="c7fa5-159">Для автономного исполняемого файла по умолчанию используется путь *[папка_файла_проекта]/bin/[конфигурация]/[платформа]/[среда выполения]/publish/* .</span><span class="sxs-lookup"><span data-stu-id="c7fa5-159">It defaults to *[project_file_folder]/bin/[configuration]/[framework]/[runtime]/publish/* for a self-contained executable.</span></span>

  - <span data-ttu-id="c7fa5-160">Пакет SDK для .NET Core 3.x и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="c7fa5-160">.NET Core 3.x SDK and later</span></span>
  
    <span data-ttu-id="c7fa5-161">Если относительный путь указывается при публикации проекта, созданный выходной каталог задается относительно текущего рабочего каталога, а не расположения файла проекта.</span><span class="sxs-lookup"><span data-stu-id="c7fa5-161">If a relative path is specified when publishing a project, the output directory generated is relative to the current working directory, not to the project file location.</span></span>

    <span data-ttu-id="c7fa5-162">Если относительный путь указывается при публикации решения, все выходные данные для всех проектов помещаются в указанную папку относительно текущего рабочего каталога.</span><span class="sxs-lookup"><span data-stu-id="c7fa5-162">If a relative path is specified when publishing a solution, all output for all projects go into the specified folder relative to the current working directory.</span></span> <span data-ttu-id="c7fa5-163">Для размещения выходных данных публикации в отдельные папки для каждого проекта укажите относительный путь, используя свойство `PublishDir` msbuild вместо параметра `--output`.</span><span class="sxs-lookup"><span data-stu-id="c7fa5-163">To make publish output go to separate folders for each project, specify a relative path by using the msbuild `PublishDir` property instead of the `--output` option.</span></span> <span data-ttu-id="c7fa5-164">Например, `dotnet publish -p:PublishDir=.\publish` отправляет выходные данные публикации для каждого проекта в папку `publish`, находящуюся в папке с файлом проекта.</span><span class="sxs-lookup"><span data-stu-id="c7fa5-164">For example, `dotnet publish -p:PublishDir=.\publish` sends publish output for each project to a `publish` folder under the folder that contains the project file.</span></span>

  - <span data-ttu-id="c7fa5-165">Пакет SDK для .NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="c7fa5-165">.NET Core 2.x SDK</span></span>
  
    <span data-ttu-id="c7fa5-166">Если относительный путь указывается при публикации проекта, созданный выходной каталог задается относительно расположения файла проекта, а не текущего рабочего каталога.</span><span class="sxs-lookup"><span data-stu-id="c7fa5-166">If a relative path is specified when publishing a project, the output directory generated is relative to the project file location, not to the current working directory.</span></span>

    <span data-ttu-id="c7fa5-167">Если относительный путь указывается при публикации решения, выходные данные каждого проекта помещаются в отдельную папку относительно расположения файла проекта.</span><span class="sxs-lookup"><span data-stu-id="c7fa5-167">If a relative path is specified when publishing a solution, each project's output goes into a separate folder relative to the project file location.</span></span> <span data-ttu-id="c7fa5-168">Если при публикации решения указан абсолютный путь, все выходные данные публикации для всех проектов размещаются в указанной папке.</span><span class="sxs-lookup"><span data-stu-id="c7fa5-168">If an absolute path is specified when publishing a solution, all publish output for all projects goes into the specified folder.</span></span>

- **`--self-contained [true|false]`**

  <span data-ttu-id="c7fa5-169">Публикует среду выполнения .NET Core вместе с приложением, что позволяет не устанавливать ее на конечном компьютере.</span><span class="sxs-lookup"><span data-stu-id="c7fa5-169">Publishes the .NET Core runtime with your application so the runtime doesn't need to be installed on the target machine.</span></span> <span data-ttu-id="c7fa5-170">Значение по умолчанию — `true`, если указан идентификатор среды выполнения и проект является исполняемым проектом (а не проектом библиотеки).</span><span class="sxs-lookup"><span data-stu-id="c7fa5-170">Default is `true` if a runtime identifier is specified and the project is an executable project (not a library project).</span></span> <span data-ttu-id="c7fa5-171">Дополнительные сведения см. в разделах [Публикация приложения .NET Core](../deploying/index.md) и [Публикация приложений .NET Core с помощью .NET Core CLI](../deploying/deploy-with-cli.md).</span><span class="sxs-lookup"><span data-stu-id="c7fa5-171">For more information, see [.NET Core application publishing](../deploying/index.md) and [Publish .NET Core apps with the .NET Core CLI](../deploying/deploy-with-cli.md).</span></span>

  <span data-ttu-id="c7fa5-172">Если этот параметр используется без указания `true` или `false`, по умолчанию применяется `true`.</span><span class="sxs-lookup"><span data-stu-id="c7fa5-172">If this option is used without specifying `true` or `false`, the default is `true`.</span></span> <span data-ttu-id="c7fa5-173">В этом случае не помещайте аргумент решения или проекта сразу после `--self-contained`, поскольку здесь ожидается `true` или `false`.</span><span class="sxs-lookup"><span data-stu-id="c7fa5-173">In that case, don't put the solution or project argument immediately after `--self-contained`, because `true` or `false` is expected in that position.</span></span>

- **`--no-self-contained`**

  <span data-ttu-id="c7fa5-174">Эквивалент `--self-contained false`.</span><span class="sxs-lookup"><span data-stu-id="c7fa5-174">Equivalent to `--self-contained false`.</span></span> <span data-ttu-id="c7fa5-175">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="c7fa5-175">Available since .NET Core 3.0 SDK.</span></span>

- **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="c7fa5-176">Публикует приложение для данной среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="c7fa5-176">Publishes the application for a given runtime.</span></span> <span data-ttu-id="c7fa5-177">Список идентификаторов сред выполнения (RID) см. в [каталоге RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="c7fa5-177">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="c7fa5-178">Дополнительные сведения см. в разделах [Публикация приложения .NET Core](../deploying/index.md) и [Публикация приложений .NET Core с помощью .NET Core CLI](../deploying/deploy-with-cli.md).</span><span class="sxs-lookup"><span data-stu-id="c7fa5-178">For more information, see [.NET Core application publishing](../deploying/index.md) and [Publish .NET Core apps with the .NET Core CLI](../deploying/deploy-with-cli.md).</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="c7fa5-179">Задает уровень детализации команды.</span><span class="sxs-lookup"><span data-stu-id="c7fa5-179">Sets the verbosity level of the command.</span></span> <span data-ttu-id="c7fa5-180">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="c7fa5-180">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="c7fa5-181">Значение по умолчанию — `minimal`.</span><span class="sxs-lookup"><span data-stu-id="c7fa5-181">Default value is `minimal`.</span></span>

- **`--version-suffix <VERSION_SUFFIX>`**

  <span data-ttu-id="c7fa5-182">Определяет суффикс версии для замены звездочки (`*`) в поле версия файла проекта.</span><span class="sxs-lookup"><span data-stu-id="c7fa5-182">Defines the version suffix to replace the asterisk (`*`) in the version field of the project file.</span></span>

## <a name="examples"></a><span data-ttu-id="c7fa5-183">Примеры</span><span class="sxs-lookup"><span data-stu-id="c7fa5-183">Examples</span></span>

- <span data-ttu-id="c7fa5-184">Создание [кроссплатформенного двоичного файла, зависящего от среды выполнения,](../deploying/index.md#produce-a-cross-platform-binary) для проекта в текущем каталоге:</span><span class="sxs-lookup"><span data-stu-id="c7fa5-184">Create a [runtime-dependent cross-platform binary](../deploying/index.md#produce-a-cross-platform-binary) for the project in the current directory:</span></span>

  ```dotnetcli
  dotnet publish
  ```

  <span data-ttu-id="c7fa5-185">Начиная с пакета SDK для .NET Core 3.0 этот пример также создает [зависящий от среды выполнения исполняемый файл](../deploying/index.md#publish-runtime-dependent) для текущей платформы.</span><span class="sxs-lookup"><span data-stu-id="c7fa5-185">Starting with .NET Core 3.0 SDK, this example also creates a [runtime-dependent executable](../deploying/index.md#publish-runtime-dependent) for the current platform.</span></span>

- <span data-ttu-id="c7fa5-186">Создание [автономного исполняемого файла](../deploying/index.md#publish-self-contained) для проекта в текущем каталоге для конкретной среды выполнения:</span><span class="sxs-lookup"><span data-stu-id="c7fa5-186">Create a [self-contained executable](../deploying/index.md#publish-self-contained) for the project in the current directory, for a specific runtime:</span></span>

  ```dotnetcli
  dotnet publish --runtime osx.10.11-x64
  ```

  <span data-ttu-id="c7fa5-187">Идентификатор RID должен находиться в файле проекта.</span><span class="sxs-lookup"><span data-stu-id="c7fa5-187">The RID must be in the project file.</span></span>

- <span data-ttu-id="c7fa5-188">Создание [зависящего от среды выполнения исполняемого файла](../deploying/index.md#publish-runtime-dependent) для проекта в текущем каталоге для конкретной платформы:</span><span class="sxs-lookup"><span data-stu-id="c7fa5-188">Create a [runtime-dependent executable](../deploying/index.md#publish-runtime-dependent) for the project in the current directory, for a specific platform:</span></span>

  ```dotnetcli
  dotnet publish --runtime osx.10.11-x64 --self-contained false
  ```

  <span data-ttu-id="c7fa5-189">Идентификатор RID должен находиться в файле проекта.</span><span class="sxs-lookup"><span data-stu-id="c7fa5-189">The RID must be in the project file.</span></span> <span data-ttu-id="c7fa5-190">Этот пример относится к пакету SDK для .NET Core 3.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="c7fa5-190">This example applies to .NET Core 3.0 SDK and later versions.</span></span>

- <span data-ttu-id="c7fa5-191">Публикация проекта в текущем каталоге для конкретной среды выполнения и целевой платформы:</span><span class="sxs-lookup"><span data-stu-id="c7fa5-191">Publish the project in the current directory, for a specific runtime and target framework:</span></span>

  ```dotnetcli
  dotnet publish --framework netcoreapp3.1 --runtime osx.10.11-x64
  ```

- <span data-ttu-id="c7fa5-192">Публикация указанного файла проекта:</span><span class="sxs-lookup"><span data-stu-id="c7fa5-192">Publish the specified project file:</span></span>

  ```dotnetcli
  dotnet publish ~/projects/app1/app1.csproj
  ```

- <span data-ttu-id="c7fa5-193">Публикация текущего приложения с обработкой только корневого проекта, без восстановления ссылок между проектами (P2P), во время операции восстановления:</span><span class="sxs-lookup"><span data-stu-id="c7fa5-193">Publish the current application but don't restore project-to-project (P2P) references, just the root project during the restore operation:</span></span>

  ```dotnetcli
  dotnet publish --no-dependencies
  ```

## <a name="see-also"></a><span data-ttu-id="c7fa5-194">См. также</span><span class="sxs-lookup"><span data-stu-id="c7fa5-194">See also</span></span>

- [<span data-ttu-id="c7fa5-195">Общие сведения о публикации приложений .NET Core</span><span class="sxs-lookup"><span data-stu-id="c7fa5-195">.NET Core application publishing overview</span></span>](../deploying/index.md)
- [<span data-ttu-id="c7fa5-196">Публикация приложений .NET Core с помощью .NET Core CLI</span><span class="sxs-lookup"><span data-stu-id="c7fa5-196">Publish .NET Core apps with the .NET Core CLI</span></span>](../deploying/deploy-with-cli.md)
- [<span data-ttu-id="c7fa5-197">Целевые платформы</span><span class="sxs-lookup"><span data-stu-id="c7fa5-197">Target frameworks</span></span>](../../standard/frameworks.md)
- [<span data-ttu-id="c7fa5-198">Каталог идентификаторов сред выполнения (RID)</span><span class="sxs-lookup"><span data-stu-id="c7fa5-198">Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
- [<span data-ttu-id="c7fa5-199">Работа с заверением macOS Catalina</span><span class="sxs-lookup"><span data-stu-id="c7fa5-199">Working with macOS Catalina Notarization</span></span>](../install/macos-notarization-issues.md)
- [<span data-ttu-id="c7fa5-200">Структура каталогов опубликованного приложения</span><span class="sxs-lookup"><span data-stu-id="c7fa5-200">Directory structure of a published application</span></span>](/aspnet/core/hosting/directory-structure)
- [<span data-ttu-id="c7fa5-201">Справочник по командной строке MSBuild</span><span class="sxs-lookup"><span data-stu-id="c7fa5-201">MSBuild command-line reference</span></span>](/visualstudio/msbuild/msbuild-command-line-reference)
- [<span data-ttu-id="c7fa5-202">Профили публикации Visual Studio (.pubxml) для развертывания приложений ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="c7fa5-202">Visual Studio publish profiles (.pubxml) for ASP.NET Core app deployment</span></span>](/aspnet/core/host-and-deploy/visual-studio-publish-profiles)
- [<span data-ttu-id="c7fa5-203">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="c7fa5-203">dotnet msbuild</span></span>](dotnet-msbuild.md)
