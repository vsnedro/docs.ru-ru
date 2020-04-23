---
title: Команда dotnet pack
description: Команда dotnet pack создает пакеты NuGet для проекта .NET Core.
ms.date: 02/14/2020
ms.openlocfilehash: 3b9c46ecd5d67519728896b0018e27fb41ebd861
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463501"
---
# <a name="dotnet-pack"></a><span data-ttu-id="0223c-103">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="0223c-103">dotnet pack</span></span>

<span data-ttu-id="0223c-104">**Эта статья относится к следующему:** ✔️ пакет SDK для .NET Core 2.x и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="0223c-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="0223c-105">name</span><span class="sxs-lookup"><span data-stu-id="0223c-105">Name</span></span>

<span data-ttu-id="0223c-106">`dotnet pack` — упаковывает код в пакет NuGet.</span><span class="sxs-lookup"><span data-stu-id="0223c-106">`dotnet pack` - Packs the code into a NuGet package.</span></span>

## <a name="synopsis"></a><span data-ttu-id="0223c-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="0223c-107">Synopsis</span></span>

```dotnetcli
dotnet pack [<PROJECT>|<SOLUTION>] [-c|--configuration <CONFIGURATION>]
    [--force] [--include-source] [--include-symbols] [--interactive]
    [--no-build] [--no-dependencies] [--no-restore] [--nologo]
    [-o|--output <OUTPUT_DIRECTORY>] [--runtime <RUNTIME_IDENTIFIER>]
    [-s|--serviceable] [-v|--verbosity <LEVEL>]
    [--version-suffix <VERSION_SUFFIX>]

dotnet pack -h|--help
```

## <a name="description"></a><span data-ttu-id="0223c-108">Описание</span><span class="sxs-lookup"><span data-stu-id="0223c-108">Description</span></span>

<span data-ttu-id="0223c-109">Команда `dotnet pack` выполняет сборку проекта и создает пакеты NuGet.</span><span class="sxs-lookup"><span data-stu-id="0223c-109">The `dotnet pack` command builds the project and creates NuGet packages.</span></span> <span data-ttu-id="0223c-110">Результат выполнения команды — пакет NuGet (то есть файл *NUPKG*).</span><span class="sxs-lookup"><span data-stu-id="0223c-110">The result of this command is a NuGet package (that is, a *.nupkg* file).</span></span>

<span data-ttu-id="0223c-111">Если вы хотите создать пакет, содержащий отладочные символы, доступны два варианта:</span><span class="sxs-lookup"><span data-stu-id="0223c-111">If you want to generate a package that contains the debug symbols, you have two options available:</span></span>

- <span data-ttu-id="0223c-112">`--include-symbols` — создает пакет символов.</span><span class="sxs-lookup"><span data-stu-id="0223c-112">`--include-symbols` - it creates the symbols package.</span></span>
- <span data-ttu-id="0223c-113">`--include-source` — создает пакет символов с папкой `src`, содержащей исходные файлы.</span><span class="sxs-lookup"><span data-stu-id="0223c-113">`--include-source` - it creates the symbols package with a `src` folder inside containing the source files.</span></span>

<span data-ttu-id="0223c-114">Зависимости NuGet упакованного проекта добавляются в файл *NUSPEC*, чтобы их можно было разрешить при установке пакета.</span><span class="sxs-lookup"><span data-stu-id="0223c-114">NuGet dependencies of the packed project are added to the *.nuspec* file, so they're properly resolved when the package is installed.</span></span> <span data-ttu-id="0223c-115">Межпроектные ссылки не упаковываются в проекте.</span><span class="sxs-lookup"><span data-stu-id="0223c-115">Project-to-project references aren't packaged inside the project.</span></span> <span data-ttu-id="0223c-116">Сейчас при наличии межпроектных зависимостей требуется один пакет на каждый проект.</span><span class="sxs-lookup"><span data-stu-id="0223c-116">Currently, you must have a package per project if you have project-to-project dependencies.</span></span>

<span data-ttu-id="0223c-117">`dotnet pack` по умолчанию сначала выполняет сборку проекта.</span><span class="sxs-lookup"><span data-stu-id="0223c-117">By default, `dotnet pack` builds the project first.</span></span> <span data-ttu-id="0223c-118">Чтобы избежать этого, передайте параметр `--no-build`.</span><span class="sxs-lookup"><span data-stu-id="0223c-118">If you wish to avoid this behavior, pass the `--no-build` option.</span></span> <span data-ttu-id="0223c-119">Этот вариант часто бывает полезен, например в сценариях сборки с непрерывной интеграцией (CI), когда вы знаете, что код был собран недавно.</span><span class="sxs-lookup"><span data-stu-id="0223c-119">This option is often useful in Continuous Integration (CI) build scenarios where you know the code was previously built.</span></span>

> [!NOTE]
> <span data-ttu-id="0223c-120">В некоторых случаях выполнить неявную сборку невозможно.</span><span class="sxs-lookup"><span data-stu-id="0223c-120">In some cases, the implicit build cannot be performed.</span></span> <span data-ttu-id="0223c-121">Это может произойти, если задано свойство `GeneratePackageOnBuild`, позволяющее избежать циклической зависимости между целевыми объектами сборки и упаковки.</span><span class="sxs-lookup"><span data-stu-id="0223c-121">This can occur when `GeneratePackageOnBuild` is set, to avoid a cyclic dependency between build and pack targets.</span></span> <span data-ttu-id="0223c-122">Кроме того, сборка может завершиться ошибкой при наличии заблокированного файла или другой проблемы.</span><span class="sxs-lookup"><span data-stu-id="0223c-122">The build can also fail if there is a locked file or other issue.</span></span>

<span data-ttu-id="0223c-123">Может предоставлять свойства MSBuild команде `dotnet pack` для процесса упаковки.</span><span class="sxs-lookup"><span data-stu-id="0223c-123">You can provide MSBuild properties to the `dotnet pack` command for the packing process.</span></span> <span data-ttu-id="0223c-124">Дополнительные сведения см. в разделах [Свойства метаданных NuGet](csproj.md#nuget-metadata-properties) и [Справочник по командной строке MSBuild](/visualstudio/msbuild/msbuild-command-line-reference).</span><span class="sxs-lookup"><span data-stu-id="0223c-124">For more information, see [NuGet metadata properties](csproj.md#nuget-metadata-properties) and the [MSBuild Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference).</span></span> <span data-ttu-id="0223c-125">В разделе [Примеры](#examples) показано, как использовать параметр -p MSBuild в различных сценариях.</span><span class="sxs-lookup"><span data-stu-id="0223c-125">The [Examples](#examples) section shows how to use the MSBuild -p switch for a couple of different scenarios.</span></span>

<span data-ttu-id="0223c-126">Веб-проекты по умолчанию не упаковываются.</span><span class="sxs-lookup"><span data-stu-id="0223c-126">Web projects aren't packable by default.</span></span> <span data-ttu-id="0223c-127">Чтобы переопределить такое поведение по умолчанию, добавьте следующее свойство в файл с расширением *.csproj*:</span><span class="sxs-lookup"><span data-stu-id="0223c-127">To override the default behavior, add the following property to your *.csproj* file:</span></span>

```xml
<PropertyGroup>
   <IsPackable>true</IsPackable>
</PropertyGroup>
```

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

## <a name="arguments"></a><span data-ttu-id="0223c-128">Аргументы</span><span class="sxs-lookup"><span data-stu-id="0223c-128">Arguments</span></span>

`PROJECT | SOLUTION`

  <span data-ttu-id="0223c-129">Проект или решение для упаковки.</span><span class="sxs-lookup"><span data-stu-id="0223c-129">The project or solution to pack.</span></span> <span data-ttu-id="0223c-130">Это путь к файлу [CSPROJ](csproj.md), файлу решения или каталогу.</span><span class="sxs-lookup"><span data-stu-id="0223c-130">It's either a path to a [csproj file](csproj.md), a solution file, or to a directory.</span></span> <span data-ttu-id="0223c-131">Если он не указан, команда ищет текущий каталог для файла решения или проекта.</span><span class="sxs-lookup"><span data-stu-id="0223c-131">If not specified, the command searches the current directory for a project or solution file.</span></span>

## <a name="options"></a><span data-ttu-id="0223c-132">Параметры</span><span class="sxs-lookup"><span data-stu-id="0223c-132">Options</span></span>

- **`-c|--configuration <CONFIGURATION>`**

  <span data-ttu-id="0223c-133">Определяет конфигурацию сборки.</span><span class="sxs-lookup"><span data-stu-id="0223c-133">Defines the build configuration.</span></span> <span data-ttu-id="0223c-134">По умолчанию для большинства проектов используется `Debug`, но можно переопределить параметры конфигурации сборки в проекте.</span><span class="sxs-lookup"><span data-stu-id="0223c-134">The default for most projects is `Debug`, but you can override the build configuration settings in your project.</span></span>

- **`--force`**

  <span data-ttu-id="0223c-135">Принудительное разрешение всех зависимостей, даже если последнее восстановление прошло успешно.</span><span class="sxs-lookup"><span data-stu-id="0223c-135">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="0223c-136">Указание этого флага дает тот же результат, что удаление файла *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="0223c-136">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

- **`-h|--help`**

  <span data-ttu-id="0223c-137">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="0223c-137">Prints out a short help for the command.</span></span>

- **`--include-source`**

  <span data-ttu-id="0223c-138">Включает пакеты NuGet отладочных символов в дополнение к обычным пакетам NuGet в выходном каталоге.</span><span class="sxs-lookup"><span data-stu-id="0223c-138">Includes the debug symbols NuGet packages in addition to the regular NuGet packages in the output directory.</span></span> <span data-ttu-id="0223c-139">Исходные файлы включены в папку `src` пакета символов.</span><span class="sxs-lookup"><span data-stu-id="0223c-139">The sources files are included in the `src` folder within the symbols package.</span></span>

- **`--include-symbols`**

  <span data-ttu-id="0223c-140">Включает пакеты NuGet отладочных символов в дополнение к обычным пакетам NuGet в выходном каталоге.</span><span class="sxs-lookup"><span data-stu-id="0223c-140">Includes the debug symbols NuGet packages in addition to the regular NuGet packages in the output directory.</span></span>

- **`--interactive`**

  <span data-ttu-id="0223c-141">Позволяет остановить команду и дождаться, пока пользователь введет данные или выполнит действие (например, завершит проверку подлинности).</span><span class="sxs-lookup"><span data-stu-id="0223c-141">Allows the command to stop and wait for user input or action (for example, to complete authentication).</span></span> <span data-ttu-id="0223c-142">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="0223c-142">Available since .NET Core 3.0 SDK.</span></span>

- **`--no-build`**

  <span data-ttu-id="0223c-143">Не выполняет сборку проекта перед упаковкой.</span><span class="sxs-lookup"><span data-stu-id="0223c-143">Doesn't build the project before packing.</span></span> <span data-ttu-id="0223c-144">Он также неявно задает флаг `--no-restore`.</span><span class="sxs-lookup"><span data-stu-id="0223c-144">It also implicitly sets the `--no-restore` flag.</span></span>

- **`--no-dependencies`**

  <span data-ttu-id="0223c-145">Межпроектные ссылки игнорируются, и восстанавливается только корневой проект.</span><span class="sxs-lookup"><span data-stu-id="0223c-145">Ignores project-to-project references and only restores the root project.</span></span>

- **`--no-restore`**

  <span data-ttu-id="0223c-146">Не выполняет неявное восстановление при выполнении команды.</span><span class="sxs-lookup"><span data-stu-id="0223c-146">Doesn't execute an implicit restore when running the command.</span></span>

- **`--nologo`**

  <span data-ttu-id="0223c-147">Скрывает загрузочный баннер или сообщение об авторских правах.</span><span class="sxs-lookup"><span data-stu-id="0223c-147">Doesn't display the startup banner or the copyright message.</span></span> <span data-ttu-id="0223c-148">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="0223c-148">Available since .NET Core 3.0 SDK.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="0223c-149">Собранные пакеты помещаются в указанный каталог.</span><span class="sxs-lookup"><span data-stu-id="0223c-149">Places the built packages in the directory specified.</span></span>

- **`--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="0223c-150">Задает целевую среду выполнения для восстановления пакетов.</span><span class="sxs-lookup"><span data-stu-id="0223c-150">Specifies the target runtime to restore packages for.</span></span> <span data-ttu-id="0223c-151">Список идентификаторов сред выполнения (RID) см. в [каталоге RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="0223c-151">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

- **`-s|--serviceable`**

  <span data-ttu-id="0223c-152">Задает флаг "подлежит обслуживанию" в пакете.</span><span class="sxs-lookup"><span data-stu-id="0223c-152">Sets the serviceable flag in the package.</span></span> <span data-ttu-id="0223c-153">Дополнительные сведения см. в записи блога о том, что [.NET 4.5.1 поддерживает обновления системы безопасности Майкрософт для библиотек .NET NuGet](https://aka.ms/nupkgservicing).</span><span class="sxs-lookup"><span data-stu-id="0223c-153">For more information, see [.NET Blog: .NET 4.5.1 Supports Microsoft Security Updates for .NET NuGet Libraries](https://aka.ms/nupkgservicing).</span></span>

- **`--version-suffix <VERSION_SUFFIX>`**

  <span data-ttu-id="0223c-154">Определяет значение для свойства `$(VersionSuffix)` MSBuild в проекте.</span><span class="sxs-lookup"><span data-stu-id="0223c-154">Defines the value for the `$(VersionSuffix)` MSBuild property in the project.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="0223c-155">Задает уровень детализации команды.</span><span class="sxs-lookup"><span data-stu-id="0223c-155">Sets the verbosity level of the command.</span></span> <span data-ttu-id="0223c-156">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="0223c-156">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

## <a name="examples"></a><span data-ttu-id="0223c-157">Примеры</span><span class="sxs-lookup"><span data-stu-id="0223c-157">Examples</span></span>

- <span data-ttu-id="0223c-158">Упаковка проекта в текущем каталоге:</span><span class="sxs-lookup"><span data-stu-id="0223c-158">Pack the project in the current directory:</span></span>

  ```dotnetcli
  dotnet pack
  ```

- <span data-ttu-id="0223c-159">Упаковка проекта `app1`:</span><span class="sxs-lookup"><span data-stu-id="0223c-159">Pack the `app1` project:</span></span>

  ```dotnetcli
  dotnet pack ~/projects/app1/project.csproj
  ```

- <span data-ttu-id="0223c-160">Упаковка проекта в текущем каталоге; полученные пакеты помещаются в папку `nupkgs`:</span><span class="sxs-lookup"><span data-stu-id="0223c-160">Pack the project in the current directory and place the resulting packages into the `nupkgs` folder:</span></span>

  ```dotnetcli
  dotnet pack --output nupkgs
  ```

- <span data-ttu-id="0223c-161">Упаковка проекта в текущем каталоге в папку `nupkgs` и пропуск этапа сборки:</span><span class="sxs-lookup"><span data-stu-id="0223c-161">Pack the project in the current directory into the `nupkgs` folder and skip the build step:</span></span>

  ```dotnetcli
  dotnet pack --no-build --output nupkgs
  ```

- <span data-ttu-id="0223c-162">Если суффикс версии пакета в файле *CSPROJ* настроен как `<VersionSuffix>$(VersionSuffix)</VersionSuffix>`, упаковка текущего проекта и обновление версии полученных пакетов с использованием указанного суффикса:</span><span class="sxs-lookup"><span data-stu-id="0223c-162">With the project's version suffix configured as `<VersionSuffix>$(VersionSuffix)</VersionSuffix>` in the *.csproj* file, pack the current project and update the resulting package version with the given suffix:</span></span>

  ```dotnetcli
  dotnet pack --version-suffix "ci-1234"
  ```

- <span data-ttu-id="0223c-163">Устанавливает версию пакета в `2.1.0` с использованием свойства MSBuild `PackageVersion`:</span><span class="sxs-lookup"><span data-stu-id="0223c-163">Set the package version to `2.1.0` with the `PackageVersion` MSBuild property:</span></span>

  ```dotnetcli
  dotnet pack -p:PackageVersion=2.1.0
  ```

- <span data-ttu-id="0223c-164">Упакуйте проект для [требуемой версии .NET Framework](../../standard/frameworks.md):</span><span class="sxs-lookup"><span data-stu-id="0223c-164">Pack the project for a specific [target framework](../../standard/frameworks.md):</span></span>

  ```dotnetcli
  dotnet pack -p:TargetFrameworks=net45
  ```

- <span data-ttu-id="0223c-165">Упакуйте проект и используйте определенную среду выполнения (Windows 10) для операции восстановления:</span><span class="sxs-lookup"><span data-stu-id="0223c-165">Pack the project and use a specific runtime (Windows 10) for the restore operation:</span></span>

  ```dotnetcli
  dotnet pack --runtime win10-x64
  ```

- <span data-ttu-id="0223c-166">Упакуйте проект с помощью [NUSPEC-файла](https://docs.microsoft.com/nuget/reference/msbuild-targets#packing-using-a-nuspec):</span><span class="sxs-lookup"><span data-stu-id="0223c-166">Pack the project using a [.nuspec file](https://docs.microsoft.com/nuget/reference/msbuild-targets#packing-using-a-nuspec):</span></span>

  ```dotnetcli
  dotnet pack ~/projects/app1/project.csproj -p:NuspecFile=~/projects/app1/project.nuspec -p:NuspecBasePath=~/projects/app1/nuget
  ```
