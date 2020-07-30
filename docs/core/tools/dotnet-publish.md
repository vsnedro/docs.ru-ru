---
title: Команда dotnet publish
description: Команда dotnet publish публикует решение или проект .NET Core в каталоге.
ms.date: 02/24/2020
ms.openlocfilehash: 59fdbfa875dad13963ae198acc6a31b537279dfe
ms.sourcegitcommit: c8c3e1c63a00b7d27f76f5e50ee6469e6bdc8987
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/28/2020
ms.locfileid: "87251183"
---
# <a name="dotnet-publish"></a><span data-ttu-id="83298-103">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="83298-103">dotnet publish</span></span>

<span data-ttu-id="83298-104">**Эта статья относится к следующему.** ✔️ SDK для .NET Core 2.1 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="83298-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="83298-105">name</span><span class="sxs-lookup"><span data-stu-id="83298-105">Name</span></span>

<span data-ttu-id="83298-106">`dotnet publish` — публикует приложение и его зависимости в папке для развертывания на размещающей системе.</span><span class="sxs-lookup"><span data-stu-id="83298-106">`dotnet publish` - Publishes the application and its dependencies to a folder for deployment to a hosting system.</span></span>

## <a name="synopsis"></a><span data-ttu-id="83298-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="83298-107">Synopsis</span></span>

```dotnetcli
dotnet publish [<PROJECT>|<SOLUTION>] [-c|--configuration <CONFIGURATION>]
    [-f|--framework <FRAMEWORK>] [--force] [--interactive]
    [--manifest <PATH_TO_MANIFEST_FILE>] [--no-build] [--no-dependencies]
    [--no-restore] [--nologo] [-o|--output <OUTPUT_DIRECTORY>]
    [-p:PublishReadyToRun=true] [-p:PublishSingleFile=true] [-p:PublishTrimmed=true]
    [-r|--runtime <RUNTIME_IDENTIFIER>] [--self-contained [true|false]]
    [--no-self-contained] [-v|--verbosity <LEVEL>]
    [--version-suffix <VERSION_SUFFIX>]

dotnet publish -h|--help
```

## <a name="description"></a><span data-ttu-id="83298-108">Описание</span><span class="sxs-lookup"><span data-stu-id="83298-108">Description</span></span>

<span data-ttu-id="83298-109">`dotnet publish` компилирует приложение, считывает его зависимости, указанные в файле проекта, и публикует итоговый набор файлов в каталоге.</span><span class="sxs-lookup"><span data-stu-id="83298-109">`dotnet publish` compiles the application, reads through its dependencies specified in the project file, and publishes the resulting set of files to a directory.</span></span> <span data-ttu-id="83298-110">Выходные данные включают следующие ресурсы:</span><span class="sxs-lookup"><span data-stu-id="83298-110">The output includes the following assets:</span></span>

- <span data-ttu-id="83298-111">Код на промежуточном языке (IL) в сборке с расширением *DLL*.</span><span class="sxs-lookup"><span data-stu-id="83298-111">Intermediate Language (IL) code in an assembly with a *dll* extension.</span></span>
- <span data-ttu-id="83298-112">Файл *.deps.json*, содержащий все зависимости проекта.</span><span class="sxs-lookup"><span data-stu-id="83298-112">A *.deps.json* file that includes all of the dependencies of the project.</span></span>
- <span data-ttu-id="83298-113">Файл *.runtimeconfig.json*, определяющий общую среду выполнения, которую ожидает приложение, а также другие параметры конфигурации для среды выполнения (например, тип сборки мусора).</span><span class="sxs-lookup"><span data-stu-id="83298-113">A *.runtimeconfig.json* file that specifies the shared runtime that the application expects, as well as other configuration options for the runtime (for example, garbage collection type).</span></span>
- <span data-ttu-id="83298-114">Зависимости приложения, которые копируются из кэша NuGet в выходную папку.</span><span class="sxs-lookup"><span data-stu-id="83298-114">The application's dependencies, which are copied from the NuGet cache into the output folder.</span></span>

<span data-ttu-id="83298-115">Выходные данные команды `dotnet publish` готовы к развертыванию в размещающей системе (например, на сервере, ПК, Mac, ноутбуке) для выполнения.</span><span class="sxs-lookup"><span data-stu-id="83298-115">The `dotnet publish` command's output is ready for deployment to a hosting system (for example, a server, PC, Mac, laptop) for execution.</span></span> <span data-ttu-id="83298-116">Это единственный официальный способ подготовить приложение к развертыванию.</span><span class="sxs-lookup"><span data-stu-id="83298-116">It's the only officially supported way to prepare the application for deployment.</span></span> <span data-ttu-id="83298-117">В зависимости от указанного в проекте типа развертывания размещающая система может как иметь, так и не иметь общую среду выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="83298-117">Depending on the type of deployment that the project specifies, the hosting system may or may not have the .NET Core shared runtime installed on it.</span></span> <span data-ttu-id="83298-118">Дополнительные сведения см. в статье [Публикация приложений .NET Core с помощью .NET Core CLI](../deploying/deploy-with-cli.md).</span><span class="sxs-lookup"><span data-stu-id="83298-118">For more information, see [Publish .NET Core apps with the .NET Core CLI](../deploying/deploy-with-cli.md).</span></span>

### <a name="implicit-restore"></a><span data-ttu-id="83298-119">Неявное восстановление</span><span class="sxs-lookup"><span data-stu-id="83298-119">Implicit restore</span></span>

[!INCLUDE[dotnet restore note](~/includes/dotnet-restore-note.md)]

### <a name="msbuild"></a><span data-ttu-id="83298-120">MSBuild</span><span class="sxs-lookup"><span data-stu-id="83298-120">MSBuild</span></span>

<span data-ttu-id="83298-121">Команда `dotnet publish` вызывает метод MSBuild, который, в свою очередь, вызывает целевой объект `Publish`.</span><span class="sxs-lookup"><span data-stu-id="83298-121">The `dotnet publish` command calls MSBuild, which invokes the `Publish` target.</span></span> <span data-ttu-id="83298-122">Все параметры, передаваемые в `dotnet publish`, передаются далее в MSBuild.</span><span class="sxs-lookup"><span data-stu-id="83298-122">Any parameters passed to `dotnet publish` are passed to MSBuild.</span></span> <span data-ttu-id="83298-123">Параметры `-c` и `-o` сопоставляются со свойствами MSBuild `Configuration` и `PublishDir` соответственно.</span><span class="sxs-lookup"><span data-stu-id="83298-123">The `-c` and `-o` parameters map to MSBuild's `Configuration` and `PublishDir` properties, respectively.</span></span>

<span data-ttu-id="83298-124">Команда `dotnet publish` принимает параметры MSBuild, например `-p` для задания свойств или `-l` для определения средства ведения журнала.</span><span class="sxs-lookup"><span data-stu-id="83298-124">The `dotnet publish` command accepts MSBuild options, such as `-p` for setting properties and `-l` to define a logger.</span></span> <span data-ttu-id="83298-125">Например, можно задать свойство MSBuild, используя формат: `-p:<NAME>=<VALUE>`.</span><span class="sxs-lookup"><span data-stu-id="83298-125">For example, you can set an MSBuild property by using the format: `-p:<NAME>=<VALUE>`.</span></span> <span data-ttu-id="83298-126">Кроме того, задать связанные с публикацией свойства можно, сославшись на файл *PUBXML*, например:</span><span class="sxs-lookup"><span data-stu-id="83298-126">You can also set publish-related properties by referring to a *.pubxml* file, for example:</span></span>

```dotnetcli
dotnet publish -p:PublishProfile=FolderProfile
```

<span data-ttu-id="83298-127">В предыдущем примере используется файл *FolderProfile.pubxml*, расположенный в папке *\<project_folder>/Properties/PublishProfiles*.</span><span class="sxs-lookup"><span data-stu-id="83298-127">The preceding example uses the *FolderProfile.pubxml* file that is found in the *\<project_folder>/Properties/PublishProfiles* folder.</span></span> <span data-ttu-id="83298-128">Если указать путь и расширение файла при определении свойства `PublishProfile`, эти сведения будут игнорироваться.</span><span class="sxs-lookup"><span data-stu-id="83298-128">If you specify a path and file extension when setting the `PublishProfile` property, they are ignored.</span></span> <span data-ttu-id="83298-129">По умолчанию MSBuild выполняет поиск в папке *Properties/PublishProfiles* по расширению файла *pubxml*.</span><span class="sxs-lookup"><span data-stu-id="83298-129">MSBuild by default looks in the *Properties/PublishProfiles* folder and assumes the *pubxml* file extension.</span></span> <span data-ttu-id="83298-130">Чтобы указать путь и имя файла, включая расширение, определите свойство `PublishProfileFullPath` вместо свойства `PublishProfile`.</span><span class="sxs-lookup"><span data-stu-id="83298-130">To specify the path and filename including extension, set the `PublishProfileFullPath` property instead of the `PublishProfile` property.</span></span>

<span data-ttu-id="83298-131">Дополнительные сведения см. в следующих ресурсах:</span><span class="sxs-lookup"><span data-stu-id="83298-131">For more information, see the following resources:</span></span>

- [<span data-ttu-id="83298-132">Справочник по командной строке MSBuild</span><span class="sxs-lookup"><span data-stu-id="83298-132">MSBuild command-line reference</span></span>](/visualstudio/msbuild/msbuild-command-line-reference)
- [<span data-ttu-id="83298-133">Профили публикации Visual Studio (.pubxml) для развертывания приложений ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="83298-133">Visual Studio publish profiles (.pubxml) for ASP.NET Core app deployment</span></span>](/aspnet/core/host-and-deploy/visual-studio-publish-profiles)
- [<span data-ttu-id="83298-134">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="83298-134">dotnet msbuild</span></span>](dotnet-msbuild.md)

## <a name="arguments"></a><span data-ttu-id="83298-135">Аргументы</span><span class="sxs-lookup"><span data-stu-id="83298-135">Arguments</span></span>

- **`PROJECT|SOLUTION`**

  <span data-ttu-id="83298-136">Проект или решение для публикации.</span><span class="sxs-lookup"><span data-stu-id="83298-136">The project or solution to publish.</span></span>
  
  * <span data-ttu-id="83298-137">`PROJECT` — это путь или имя файла проекта [C#](csproj.md), F# или Visual Basic либо путь к папке, которая содержит файл проекта C#, F# или Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="83298-137">`PROJECT` is the path and filename of a [C#](csproj.md), F#, or Visual Basic project file, or the path to a directory that contains a C#, F#, or Visual Basic project file.</span></span> <span data-ttu-id="83298-138">Если каталог не указан, по умолчанию используется текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="83298-138">If the directory is not specified, it defaults to the current directory.</span></span>

  * <span data-ttu-id="83298-139">`SOLUTION` — это путь и имя для файла решения (расширение *SLN*) или путь к каталогу, содержащему файл решения.</span><span class="sxs-lookup"><span data-stu-id="83298-139">`SOLUTION` is the path and filename of a solution file (*.sln* extension), or the path to a directory that contains a solution file.</span></span> <span data-ttu-id="83298-140">Если каталог не указан, по умолчанию используется текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="83298-140">If the directory is not specified, it defaults to the current directory.</span></span> <span data-ttu-id="83298-141">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="83298-141">Available since .NET Core 3.0 SDK.</span></span>

## <a name="options"></a><span data-ttu-id="83298-142">Параметры</span><span class="sxs-lookup"><span data-stu-id="83298-142">Options</span></span>

- **`-c|--configuration <CONFIGURATION>`**

  <span data-ttu-id="83298-143">Определяет конфигурацию сборки.</span><span class="sxs-lookup"><span data-stu-id="83298-143">Defines the build configuration.</span></span> <span data-ttu-id="83298-144">По умолчанию для большинства проектов используется `Debug`, но можно переопределить параметры конфигурации сборки в проекте.</span><span class="sxs-lookup"><span data-stu-id="83298-144">The default for most projects is `Debug`, but you can override the build configuration settings in your project.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="83298-145">Публикует приложение для указанной [целевой платформы](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="83298-145">Publishes the application for the specified [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="83298-146">Вам нужно указать целевую платформу в файле проекта.</span><span class="sxs-lookup"><span data-stu-id="83298-146">You must specify the target framework in the project file.</span></span>

- **`--force`**

  <span data-ttu-id="83298-147">Принудительное разрешение всех зависимостей, даже если последнее восстановление прошло успешно.</span><span class="sxs-lookup"><span data-stu-id="83298-147">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="83298-148">Указание этого флага дает тот же результат, что удаление файла *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="83298-148">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

- **`-h|--help`**

  <span data-ttu-id="83298-149">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="83298-149">Prints out a short help for the command.</span></span>

- **`--interactive`**

  <span data-ttu-id="83298-150">Позволяет команде остановиться и дождаться, пока пользователь выполнит действие или введет данные.</span><span class="sxs-lookup"><span data-stu-id="83298-150">Allows the command to stop and wait for user input or action.</span></span> <span data-ttu-id="83298-151">Например, чтобы завершить проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="83298-151">For example, to complete authentication.</span></span> <span data-ttu-id="83298-152">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="83298-152">Available since .NET Core 3.0 SDK.</span></span>

- **`--manifest <PATH_TO_MANIFEST_FILE>`**

  <span data-ttu-id="83298-153">Определяет один или несколько [целевых манифестов](../deploying/runtime-store.md) для усечения множества пакетов, публикуемых вместе с приложением.</span><span class="sxs-lookup"><span data-stu-id="83298-153">Specifies one or several [target manifests](../deploying/runtime-store.md) to use to trim the set of packages published with the app.</span></span> <span data-ttu-id="83298-154">Файл манифеста является частью выходных данных [команды `dotnet store`](dotnet-store.md).</span><span class="sxs-lookup"><span data-stu-id="83298-154">The manifest file is part of the output of the [`dotnet store` command](dotnet-store.md).</span></span> <span data-ttu-id="83298-155">Чтобы указать несколько манифестов, добавьте параметр `--manifest` для каждого из них.</span><span class="sxs-lookup"><span data-stu-id="83298-155">To specify multiple manifests, add a `--manifest` option for each manifest.</span></span>

- **`--no-build`**

  <span data-ttu-id="83298-156">Не выполняет сборку проекта перед публикацией.</span><span class="sxs-lookup"><span data-stu-id="83298-156">Doesn't build the project before publishing.</span></span> <span data-ttu-id="83298-157">Он также неявно задает флаг `--no-restore`.</span><span class="sxs-lookup"><span data-stu-id="83298-157">It also implicitly sets the `--no-restore` flag.</span></span>

- **`--no-dependencies`**

  <span data-ttu-id="83298-158">Межпроектные ссылки игнорируются, и восстанавливается только корневой проект.</span><span class="sxs-lookup"><span data-stu-id="83298-158">Ignores project-to-project references and only restores the root project.</span></span>

- **`--nologo`**

  <span data-ttu-id="83298-159">Скрывает загрузочный баннер или сообщение об авторских правах.</span><span class="sxs-lookup"><span data-stu-id="83298-159">Doesn't display the startup banner or the copyright message.</span></span> <span data-ttu-id="83298-160">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="83298-160">Available since .NET Core 3.0 SDK.</span></span>

- **`--no-restore`**

  <span data-ttu-id="83298-161">Не выполняет неявное восстановление при выполнении команды.</span><span class="sxs-lookup"><span data-stu-id="83298-161">Doesn't execute an implicit restore when running the command.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="83298-162">Задает путь для выходного каталога.</span><span class="sxs-lookup"><span data-stu-id="83298-162">Specifies the path for the output directory.</span></span>
  
  <span data-ttu-id="83298-163">Если значение не указано, для исполняемого файла, зависящего от среды выполнения, а также для кроссплатформенных двоичных файлов по умолчанию используется путь *[папка_файла_проекта]./bin/[конфигурация]/[платформа]/publish/* .</span><span class="sxs-lookup"><span data-stu-id="83298-163">If not specified, it defaults to *[project_file_folder]./bin/[configuration]/[framework]/publish/* for a runtime-dependent executable and cross-platform binaries.</span></span> <span data-ttu-id="83298-164">Для автономного исполняемого файла по умолчанию используется путь *[папка_файла_проекта]/bin/[конфигурация]/[платформа]/[среда выполения]/publish/* .</span><span class="sxs-lookup"><span data-stu-id="83298-164">It defaults to *[project_file_folder]/bin/[configuration]/[framework]/[runtime]/publish/* for a self-contained executable.</span></span>

  <span data-ttu-id="83298-165">Если в веб-проекте выходная папка находится в папке проекта, последовательное выполнение команд `dotnet publish` приводит к созданию вложенных выходных папок.</span><span class="sxs-lookup"><span data-stu-id="83298-165">In a web project, if the output folder is in the project folder, successive `dotnet publish` commands result in nested output folders.</span></span> <span data-ttu-id="83298-166">Например, если папкой проекта является *MyProject*, папкой выходных данных публикации — *myproject/publish* и вы дважды запускаете `dotnet publish`, при втором запуске файлы содержимого, такие как *.config* и *.json* помещаются в папку *myproject/publish/publish*.</span><span class="sxs-lookup"><span data-stu-id="83298-166">For example, if the project folder is *myproject*, and the publish output folder is *myproject/publish*, and you run `dotnet publish` twice, the second run puts content files such as *.config* and *.json* files in *myproject/publish/publish*.</span></span> <span data-ttu-id="83298-167">Чтобы избежать вложенности папок публикации, укажите папку публикации, которая не находится **непосредственно** в папке проекта, или исключите папку публикации из проекта.</span><span class="sxs-lookup"><span data-stu-id="83298-167">To avoid nesting publish folders, specify a publish folder that is not **directly** under the project folder, or exclude the publish folder from the project.</span></span> <span data-ttu-id="83298-168">Чтобы исключить папку публикации с именем *publishoutput*, добавьте следующий элемент в элемент `PropertyGroup` в файле *.csproj*.</span><span class="sxs-lookup"><span data-stu-id="83298-168">To exclude a publish folder named *publishoutput*, add the following element to a `PropertyGroup` element in the *.csproj* file:</span></span>

  ```xml
  <DefaultItemExcludes>$(DefaultItemExcludes);publishoutput**</DefaultItemExcludes>
  ```

  - <span data-ttu-id="83298-169">Пакет SDK для .NET Core 3.x и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="83298-169">.NET Core 3.x SDK and later</span></span>
  
    <span data-ttu-id="83298-170">Если относительный путь указывается при публикации проекта, созданный выходной каталог задается относительно текущего рабочего каталога, а не расположения файла проекта.</span><span class="sxs-lookup"><span data-stu-id="83298-170">If a relative path is specified when publishing a project, the output directory generated is relative to the current working directory, not to the project file location.</span></span>

    <span data-ttu-id="83298-171">Если относительный путь указывается при публикации решения, все выходные данные для всех проектов помещаются в указанную папку относительно текущего рабочего каталога.</span><span class="sxs-lookup"><span data-stu-id="83298-171">If a relative path is specified when publishing a solution, all output for all projects goes into the specified folder relative to the current working directory.</span></span> <span data-ttu-id="83298-172">Для размещения выходных данных публикации в отдельные папки для каждого проекта укажите относительный путь, используя свойство `PublishDir` msbuild вместо параметра `--output`.</span><span class="sxs-lookup"><span data-stu-id="83298-172">To make publish output go to separate folders for each project, specify a relative path by using the msbuild `PublishDir` property instead of the `--output` option.</span></span> <span data-ttu-id="83298-173">Например, `dotnet publish -p:PublishDir=.\publish` отправляет выходные данные публикации для каждого проекта в папку `publish`, находящуюся в папке с файлом проекта.</span><span class="sxs-lookup"><span data-stu-id="83298-173">For example, `dotnet publish -p:PublishDir=.\publish` sends publish output for each project to a `publish` folder under the folder that contains the project file.</span></span>

  - <span data-ttu-id="83298-174">Пакет SDK для .NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="83298-174">.NET Core 2.x SDK</span></span>
  
    <span data-ttu-id="83298-175">Если относительный путь указывается при публикации проекта, созданный выходной каталог задается относительно расположения файла проекта, а не текущего рабочего каталога.</span><span class="sxs-lookup"><span data-stu-id="83298-175">If a relative path is specified when publishing a project, the output directory generated is relative to the project file location, not to the current working directory.</span></span>

    <span data-ttu-id="83298-176">Если относительный путь указывается при публикации решения, выходные данные каждого проекта помещаются в отдельную папку относительно расположения файла проекта.</span><span class="sxs-lookup"><span data-stu-id="83298-176">If a relative path is specified when publishing a solution, each project's output goes into a separate folder relative to the project file location.</span></span> <span data-ttu-id="83298-177">Если при публикации решения указан абсолютный путь, все выходные данные публикации для всех проектов размещаются в указанной папке.</span><span class="sxs-lookup"><span data-stu-id="83298-177">If an absolute path is specified when publishing a solution, all publish output for all projects goes into the specified folder.</span></span>

- **`-p:PublishReadyToRun=true`**

  <span data-ttu-id="83298-178">Компилирует сборки приложений в формате ReadyToRun (R2R).</span><span class="sxs-lookup"><span data-stu-id="83298-178">Compiles application assemblies as ReadyToRun (R2R) format.</span></span> <span data-ttu-id="83298-179">R2R является разновидностью компиляции AOT.</span><span class="sxs-lookup"><span data-stu-id="83298-179">R2R is a form of ahead-of-time (AOT) compilation.</span></span> <span data-ttu-id="83298-180">Дополнительные сведения см. в разделе [Образы ReadyToRun](../whats-new/dotnet-core-3-0.md#readytorun-images).</span><span class="sxs-lookup"><span data-stu-id="83298-180">For more information, see [ReadyToRun images](../whats-new/dotnet-core-3-0.md#readytorun-images).</span></span> <span data-ttu-id="83298-181">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="83298-181">Available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="83298-182">Рекомендуется указывать этот параметр в профиле публикации, а не в командной строке.</span><span class="sxs-lookup"><span data-stu-id="83298-182">We recommend that you specify this option in a publish profile rather than on the command line.</span></span> <span data-ttu-id="83298-183">Дополнительные сведения см. в разделе [MSBuild](#msbuild).</span><span class="sxs-lookup"><span data-stu-id="83298-183">For more information, see [MSBuild](#msbuild).</span></span>

- **`-p:PublishSingleFile=true`**

  <span data-ttu-id="83298-184">Упаковывает приложение в однофайловый исполняемый файл для конкретной платформы.</span><span class="sxs-lookup"><span data-stu-id="83298-184">Packages the app into a platform-specific single-file executable.</span></span> <span data-ttu-id="83298-185">Исполняемый файл является самоизвлекаемым и содержит все зависимости (включая машинные), необходимые для запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="83298-185">The executable is self-extracting and contains all dependencies (including native) that are required to run the app.</span></span> <span data-ttu-id="83298-186">При первом запуске приложение извлекается в каталог, который зависит от имени и идентификатора сборки приложения.</span><span class="sxs-lookup"><span data-stu-id="83298-186">When the app is first run, the application is extracted to a directory based on the app name and build identifier.</span></span> <span data-ttu-id="83298-187">Впоследствии запуск происходит быстрее.</span><span class="sxs-lookup"><span data-stu-id="83298-187">Startup is faster when the application is run again.</span></span> <span data-ttu-id="83298-188">Если версия не изменилась, приложению не нужно извлекать себя заново.</span><span class="sxs-lookup"><span data-stu-id="83298-188">The application doesn't need to extract itself a second time unless a new version is used.</span></span> <span data-ttu-id="83298-189">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="83298-189">Available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="83298-190">Дополнительные сведения о публикации однофайловых исполняемых файлов см. в [документе о разработке однофайловых пакетных установщиков](https://github.com/dotnet/designs/blob/master/accepted/2020/single-file/design.md).</span><span class="sxs-lookup"><span data-stu-id="83298-190">For more information about single-file publishing, see the [single-file bundler design document](https://github.com/dotnet/designs/blob/master/accepted/2020/single-file/design.md).</span></span>

  <span data-ttu-id="83298-191">Рекомендуется указывать этот параметр в профиле публикации, а не в командной строке.</span><span class="sxs-lookup"><span data-stu-id="83298-191">We recommend that you specify this option in a publish profile rather than on the command line.</span></span> <span data-ttu-id="83298-192">Дополнительные сведения см. в разделе [MSBuild](#msbuild).</span><span class="sxs-lookup"><span data-stu-id="83298-192">For more information, see [MSBuild](#msbuild).</span></span>

- **`-p:PublishTrimmed=true`**

  <span data-ttu-id="83298-193">Обрезает неиспользуемые библиотеки, чтобы уменьшить размер развертывания приложения при публикации автономного исполняемого файла.</span><span class="sxs-lookup"><span data-stu-id="83298-193">Trims unused libraries to reduce the deployment size of an app when publishing a self-contained executable.</span></span> <span data-ttu-id="83298-194">Дополнительные сведения см. в статье [Обрезка автономных развертываний и исполняемых файлов](../deploying/trim-self-contained.md).</span><span class="sxs-lookup"><span data-stu-id="83298-194">For more information, see [Trim self-contained deployments and executables](../deploying/trim-self-contained.md).</span></span> <span data-ttu-id="83298-195">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="83298-195">Available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="83298-196">Рекомендуется указывать этот параметр в профиле публикации, а не в командной строке.</span><span class="sxs-lookup"><span data-stu-id="83298-196">We recommend that you specify this option in a publish profile rather than on the command line.</span></span> <span data-ttu-id="83298-197">Дополнительные сведения см. в разделе [MSBuild](#msbuild).</span><span class="sxs-lookup"><span data-stu-id="83298-197">For more information, see [MSBuild](#msbuild).</span></span>

- **`--self-contained [true|false]`**

  <span data-ttu-id="83298-198">Публикует среду выполнения .NET Core вместе с приложением, что позволяет не устанавливать ее на конечном компьютере.</span><span class="sxs-lookup"><span data-stu-id="83298-198">Publishes the .NET Core runtime with your application so the runtime doesn't need to be installed on the target machine.</span></span> <span data-ttu-id="83298-199">Значение по умолчанию — `true`, если указан идентификатор среды выполнения и проект является исполняемым проектом (а не проектом библиотеки).</span><span class="sxs-lookup"><span data-stu-id="83298-199">Default is `true` if a runtime identifier is specified and the project is an executable project (not a library project).</span></span> <span data-ttu-id="83298-200">Дополнительные сведения см. в разделах [Публикация приложения .NET Core](../deploying/index.md) и [Публикация приложений .NET Core с помощью .NET Core CLI](../deploying/deploy-with-cli.md).</span><span class="sxs-lookup"><span data-stu-id="83298-200">For more information, see [.NET Core application publishing](../deploying/index.md) and [Publish .NET Core apps with the .NET Core CLI](../deploying/deploy-with-cli.md).</span></span>

  <span data-ttu-id="83298-201">Если этот параметр используется без указания `true` или `false`, по умолчанию применяется `true`.</span><span class="sxs-lookup"><span data-stu-id="83298-201">If this option is used without specifying `true` or `false`, the default is `true`.</span></span> <span data-ttu-id="83298-202">В этом случае не помещайте аргумент решения или проекта сразу после `--self-contained`, поскольку здесь ожидается `true` или `false`.</span><span class="sxs-lookup"><span data-stu-id="83298-202">In that case, don't put the solution or project argument immediately after `--self-contained`, because `true` or `false` is expected in that position.</span></span>

- **`--no-self-contained`**

  <span data-ttu-id="83298-203">Эквивалент `--self-contained false`.</span><span class="sxs-lookup"><span data-stu-id="83298-203">Equivalent to `--self-contained false`.</span></span> <span data-ttu-id="83298-204">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="83298-204">Available since .NET Core 3.0 SDK.</span></span>

- **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="83298-205">Публикует приложение для данной среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="83298-205">Publishes the application for a given runtime.</span></span> <span data-ttu-id="83298-206">Список идентификаторов сред выполнения (RID) см. в [каталоге RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="83298-206">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="83298-207">Дополнительные сведения см. в разделах [Публикация приложения .NET Core](../deploying/index.md) и [Публикация приложений .NET Core с помощью .NET Core CLI](../deploying/deploy-with-cli.md).</span><span class="sxs-lookup"><span data-stu-id="83298-207">For more information, see [.NET Core application publishing](../deploying/index.md) and [Publish .NET Core apps with the .NET Core CLI](../deploying/deploy-with-cli.md).</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="83298-208">Задает уровень детализации команды.</span><span class="sxs-lookup"><span data-stu-id="83298-208">Sets the verbosity level of the command.</span></span> <span data-ttu-id="83298-209">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="83298-209">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="83298-210">Значение по умолчанию — `minimal`.</span><span class="sxs-lookup"><span data-stu-id="83298-210">Default value is `minimal`.</span></span>

- **`--version-suffix <VERSION_SUFFIX>`**

  <span data-ttu-id="83298-211">Определяет суффикс версии для замены звездочки (`*`) в поле версия файла проекта.</span><span class="sxs-lookup"><span data-stu-id="83298-211">Defines the version suffix to replace the asterisk (`*`) in the version field of the project file.</span></span>

## <a name="examples"></a><span data-ttu-id="83298-212">Примеры</span><span class="sxs-lookup"><span data-stu-id="83298-212">Examples</span></span>

- <span data-ttu-id="83298-213">Создание [кроссплатформенного двоичного файла, зависящего от среды выполнения,](../deploying/index.md#produce-a-cross-platform-binary) для проекта в текущем каталоге:</span><span class="sxs-lookup"><span data-stu-id="83298-213">Create a [runtime-dependent cross-platform binary](../deploying/index.md#produce-a-cross-platform-binary) for the project in the current directory:</span></span>

  ```dotnetcli
  dotnet publish
  ```

  <span data-ttu-id="83298-214">Начиная с пакета SDK для .NET Core 3.0 этот пример также создает [зависящий от среды выполнения исполняемый файл](../deploying/index.md#publish-runtime-dependent) для текущей платформы.</span><span class="sxs-lookup"><span data-stu-id="83298-214">Starting with .NET Core 3.0 SDK, this example also creates a [runtime-dependent executable](../deploying/index.md#publish-runtime-dependent) for the current platform.</span></span>

- <span data-ttu-id="83298-215">Создание [автономного исполняемого файла](../deploying/index.md#publish-self-contained) для проекта в текущем каталоге для конкретной среды выполнения:</span><span class="sxs-lookup"><span data-stu-id="83298-215">Create a [self-contained executable](../deploying/index.md#publish-self-contained) for the project in the current directory, for a specific runtime:</span></span>

  ```dotnetcli
  dotnet publish --runtime osx.10.11-x64
  ```

  <span data-ttu-id="83298-216">Идентификатор RID должен находиться в файле проекта.</span><span class="sxs-lookup"><span data-stu-id="83298-216">The RID must be in the project file.</span></span>

- <span data-ttu-id="83298-217">Создание [зависящего от среды выполнения исполняемого файла](../deploying/index.md#publish-runtime-dependent) для проекта в текущем каталоге для конкретной платформы:</span><span class="sxs-lookup"><span data-stu-id="83298-217">Create a [runtime-dependent executable](../deploying/index.md#publish-runtime-dependent) for the project in the current directory, for a specific platform:</span></span>

  ```dotnetcli
  dotnet publish --runtime osx.10.11-x64 --self-contained false
  ```

  <span data-ttu-id="83298-218">Идентификатор RID должен находиться в файле проекта.</span><span class="sxs-lookup"><span data-stu-id="83298-218">The RID must be in the project file.</span></span> <span data-ttu-id="83298-219">Этот пример относится к пакету SDK для .NET Core 3.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="83298-219">This example applies to .NET Core 3.0 SDK and later versions.</span></span>

- <span data-ttu-id="83298-220">Публикация проекта в текущем каталоге для конкретной среды выполнения и целевой платформы:</span><span class="sxs-lookup"><span data-stu-id="83298-220">Publish the project in the current directory, for a specific runtime and target framework:</span></span>

  ```dotnetcli
  dotnet publish --framework netcoreapp3.1 --runtime osx.10.11-x64
  ```

- <span data-ttu-id="83298-221">Публикация указанного файла проекта:</span><span class="sxs-lookup"><span data-stu-id="83298-221">Publish the specified project file:</span></span>

  ```dotnetcli
  dotnet publish ~/projects/app1/app1.csproj
  ```

- <span data-ttu-id="83298-222">Публикация текущего приложения с обработкой только корневого проекта, без восстановления ссылок между проектами (P2P), во время операции восстановления:</span><span class="sxs-lookup"><span data-stu-id="83298-222">Publish the current application but don't restore project-to-project (P2P) references, just the root project during the restore operation:</span></span>

  ```dotnetcli
  dotnet publish --no-dependencies
  ```

## <a name="see-also"></a><span data-ttu-id="83298-223">См. также</span><span class="sxs-lookup"><span data-stu-id="83298-223">See also</span></span>

- [<span data-ttu-id="83298-224">Общие сведения о публикации приложений .NET Core</span><span class="sxs-lookup"><span data-stu-id="83298-224">.NET Core application publishing overview</span></span>](../deploying/index.md)
- [<span data-ttu-id="83298-225">Публикация приложений .NET Core с помощью .NET Core CLI</span><span class="sxs-lookup"><span data-stu-id="83298-225">Publish .NET Core apps with the .NET Core CLI</span></span>](../deploying/deploy-with-cli.md)
- [<span data-ttu-id="83298-226">Целевые платформы</span><span class="sxs-lookup"><span data-stu-id="83298-226">Target frameworks</span></span>](../../standard/frameworks.md)
- [<span data-ttu-id="83298-227">Каталог идентификаторов сред выполнения (RID)</span><span class="sxs-lookup"><span data-stu-id="83298-227">Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
- [<span data-ttu-id="83298-228">Работа с заверением macOS Catalina</span><span class="sxs-lookup"><span data-stu-id="83298-228">Working with macOS Catalina Notarization</span></span>](../install/macos-notarization-issues.md)
- [<span data-ttu-id="83298-229">Структура каталогов опубликованного приложения</span><span class="sxs-lookup"><span data-stu-id="83298-229">Directory structure of a published application</span></span>](/aspnet/core/hosting/directory-structure)
- [<span data-ttu-id="83298-230">Справочник по командной строке MSBuild</span><span class="sxs-lookup"><span data-stu-id="83298-230">MSBuild command-line reference</span></span>](/visualstudio/msbuild/msbuild-command-line-reference)
- [<span data-ttu-id="83298-231">Профили публикации Visual Studio (.pubxml) для развертывания приложений ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="83298-231">Visual Studio publish profiles (.pubxml) for ASP.NET Core app deployment</span></span>](/aspnet/core/host-and-deploy/visual-studio-publish-profiles)
- [<span data-ttu-id="83298-232">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="83298-232">dotnet msbuild</span></span>](dotnet-msbuild.md)
- [<span data-ttu-id="83298-233">ILLInk.Tasks</span><span class="sxs-lookup"><span data-stu-id="83298-233">ILLInk.Tasks</span></span>](https://aka.ms/dotnet-illink)
