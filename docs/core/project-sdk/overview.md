---
title: Обзор пакета SDK для проекта .NET Core
description: Сведения о пакетах SDK для проектов .NET Core.
ms.date: 02/02/2020
ms.topic: conceptual
ms.openlocfilehash: d0ac01dca31dffea482745126e00c34b1da20774
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389672"
---
# <a name="net-core-project-sdks"></a><span data-ttu-id="a306f-103">Пакеты SDK для проектов .NET Core</span><span class="sxs-lookup"><span data-stu-id="a306f-103">.NET Core project SDKs</span></span>

<span data-ttu-id="a306f-104">Проекты .NET Core связаны с пакетом средств разработки программного обеспечения (SDK).</span><span class="sxs-lookup"><span data-stu-id="a306f-104">.NET Core projects are associated with a software development kit (SDK).</span></span> <span data-ttu-id="a306f-105">Каждый *пакет SDK для проекта* является набором [целевых объектов](/visualstudio/msbuild/msbuild-targets) MSBuild и связанных [задач](/visualstudio/msbuild/msbuild-tasks), которые отвечают за компиляцию, упаковку и публикацию кода.</span><span class="sxs-lookup"><span data-stu-id="a306f-105">Each *project SDK* is a set of MSBuild [targets](/visualstudio/msbuild/msbuild-targets) and associated [tasks](/visualstudio/msbuild/msbuild-tasks) that are responsible for compiling, packing, and publishing code.</span></span> <span data-ttu-id="a306f-106">Проект, который ссылается на пакет SDK для проекта, иногда называется *проектом в стиле пакета SDK*.</span><span class="sxs-lookup"><span data-stu-id="a306f-106">A project that references a project SDK is sometimes referred to as an *SDK-style project*.</span></span>

## <a name="available-sdks"></a><span data-ttu-id="a306f-107">Доступные пакеты SDK</span><span class="sxs-lookup"><span data-stu-id="a306f-107">Available SDKs</span></span>

<span data-ttu-id="a306f-108">Для .NET Core доступны следующие пакеты SDK:</span><span class="sxs-lookup"><span data-stu-id="a306f-108">The following SDKs are available for .NET Core:</span></span>

| <span data-ttu-id="a306f-109">ID</span><span class="sxs-lookup"><span data-stu-id="a306f-109">ID</span></span> | <span data-ttu-id="a306f-110">Описание</span><span class="sxs-lookup"><span data-stu-id="a306f-110">Description</span></span> | <span data-ttu-id="a306f-111">Репозиторий</span><span class="sxs-lookup"><span data-stu-id="a306f-111">Repo</span></span>|
| - | - | - |
| `Microsoft.NET.Sdk` | <span data-ttu-id="a306f-112">Пакет SDK для .NET Core</span><span class="sxs-lookup"><span data-stu-id="a306f-112">The .NET Core SDK</span></span> | https://github.com/dotnet/sdk |
| `Microsoft.NET.Sdk.Web` | <span data-ttu-id="a306f-113">[Веб-пакет SDK](/aspnet/core/razor-pages/web-sdk) для .NET Core</span><span class="sxs-lookup"><span data-stu-id="a306f-113">The .NET Core [Web SDK](/aspnet/core/razor-pages/web-sdk)</span></span> | https://github.com/aspnet/websdk |
| `Microsoft.NET.Sdk.Razor` | <span data-ttu-id="a306f-114">[Пакет SDK для Razor](/aspnet/core/razor-pages/sdk) в .NET Core</span><span class="sxs-lookup"><span data-stu-id="a306f-114">The .NET Core [Razor SDK](/aspnet/core/razor-pages/sdk)</span></span> |
| `Microsoft.NET.Sdk.Worker` | <span data-ttu-id="a306f-115">Пакет SDK для службы рабочей роли в .NET Core</span><span class="sxs-lookup"><span data-stu-id="a306f-115">The .NET Core Worker Service SDK</span></span> |
| `Microsoft.NET.Sdk.WindowsDesktop` | <span data-ttu-id="a306f-116">Пакет SDK для WinForms и WPF в .NET Core</span><span class="sxs-lookup"><span data-stu-id="a306f-116">The .NET Core WinForms and WPF SDK</span></span> |

<span data-ttu-id="a306f-117">Пакет SDK для .NET Core является базовым пакетом SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a306f-117">The .NET Core SDK is the base SDK for .NET Core.</span></span> <span data-ttu-id="a306f-118">Другие пакеты SDK ссылаются на пакет SDK для .NET Core, а проекты, связанные с другими пакетами SDK, имеют все доступные им свойства пакета SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a306f-118">The other SDKs reference the .NET Core SDK, and projects that are associated with the other SDKs have all the .NET Core SDK properties available to them.</span></span> <span data-ttu-id="a306f-119">Например, веб-пакет SDK зависит от пакета SDK для .NET Core и пакета SDK для Razor.</span><span class="sxs-lookup"><span data-stu-id="a306f-119">The Web SDK, for example, depends on both the .NET Core SDK and the Razor SDK.</span></span>

<span data-ttu-id="a306f-120">Можно также создать собственный пакет SDK и распространять его с помощью NuGet.</span><span class="sxs-lookup"><span data-stu-id="a306f-120">You can also author your own SDK that can be distributed via NuGet.</span></span>

## <a name="project-files"></a><span data-ttu-id="a306f-121">Файлы проекта</span><span class="sxs-lookup"><span data-stu-id="a306f-121">Project files</span></span>

<span data-ttu-id="a306f-122">В основе проектов .NET Core лежит формат [MSBuild](/visualstudio/msbuild/msbuild).</span><span class="sxs-lookup"><span data-stu-id="a306f-122">.NET Core projects are based on the [MSBuild](/visualstudio/msbuild/msbuild) format.</span></span> <span data-ttu-id="a306f-123">Файлы проекта с такими расширениями, как *CPROJ* для проектов C# и *FPROJ* для проектов F#, имеют формат XML.</span><span class="sxs-lookup"><span data-stu-id="a306f-123">Project files, which have extensions like *.csproj* for C# projects and *.fsproj* for F# projects, are in XML format.</span></span> <span data-ttu-id="a306f-124">Корневым элементом файла проекта MSBuild является элемент [Project](/visualstudio/msbuild/project-element-msbuild).</span><span class="sxs-lookup"><span data-stu-id="a306f-124">The root element of an MSBuild project file is the [Project](/visualstudio/msbuild/project-element-msbuild) element.</span></span> <span data-ttu-id="a306f-125">Элемент `Project` имеет необязательный атрибут `Sdk`, указывающий, какой пакет SDK (и версию) следует использовать.</span><span class="sxs-lookup"><span data-stu-id="a306f-125">The `Project` element has an optional `Sdk` attribute that specifies which SDK (and version) to use.</span></span> <span data-ttu-id="a306f-126">Чтобы использовать средства .NET Core и выполнить сборку кода, задайте в качестве значения атрибута `Sdk` один из идентификаторов, указанных в таблице[Доступные пакеты SDK](#available-sdks).</span><span class="sxs-lookup"><span data-stu-id="a306f-126">To use the .NET Core tools and build your code, set the `Sdk` attribute to one of the IDs in the [Available SDKs](#available-sdks) table.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  ...
</Project>
```

<span data-ttu-id="a306f-127">Чтобы указать пакет SDK, который содержится в NuGet, добавьте версию в конец имени или укажите имя и версию в файле *global.json*.</span><span class="sxs-lookup"><span data-stu-id="a306f-127">To specify an SDK that comes from NuGet, include the version at the end of the name, or specify the name and version in the *global.json* file.</span></span>

```xml
<Project Sdk="MSBuild.Sdk.Extras/2.0.54">
  ...
</Project>
```

<span data-ttu-id="a306f-128">Другим способом указания пакета SDK является элемент [Sdk](/visualstudio/msbuild/sdk-element-msbuild) верхнего уровня.</span><span class="sxs-lookup"><span data-stu-id="a306f-128">Another way to specify the SDK is with the top-level [Sdk](/visualstudio/msbuild/sdk-element-msbuild) element:</span></span>

```xml
<Project>
  <Sdk Name="Microsoft.NET.Sdk" />
  ...
</Project>
```

<span data-ttu-id="a306f-129">Указание пакета SDK одним из этих способов значительно упрощает файлы проекта для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a306f-129">Referencing an SDK in one of these ways greatly simplifies project files for .NET Core.</span></span> <span data-ttu-id="a306f-130">На этапе оценки проекта MSBuild добавляет неявные директивы импорта для `Sdk.props` в начале и для `Sdk.targets` в конце файла проекта.</span><span class="sxs-lookup"><span data-stu-id="a306f-130">While evaluating the project, MSBuild adds implicit imports for `Sdk.props` at the top of the project file and `Sdk.targets` at the bottom.</span></span>

```xml
<Project>
  <!-- Implicit top import -->
  <Import Project="Sdk.props" Sdk="Microsoft.NET.Sdk" />
  ...
  <!-- Implicit bottom import -->
  <Import Project="Sdk.targets" Sdk="Microsoft.NET.Sdk" />
</Project>
```

> [!TIP]
> <span data-ttu-id="a306f-131">На компьютере Windows файлы *Sdk.props* и *Sdk.targets* можно найти в папке *%ProgramFiles%\dotnet\sdk\\[версия]\Sdks\Microsoft.NET.Sdk\Sdk*.</span><span class="sxs-lookup"><span data-stu-id="a306f-131">On a Windows machine, the *Sdk.props* and *Sdk.targets* files can be found in the *%ProgramFiles%\dotnet\sdk\\[version]\Sdks\Microsoft.NET.Sdk\Sdk* folder.</span></span>

### <a name="preprocess-the-project-file"></a><span data-ttu-id="a306f-132">Предварительная обработка файла проекта</span><span class="sxs-lookup"><span data-stu-id="a306f-132">Preprocess the project file</span></span>

<span data-ttu-id="a306f-133">Увидеть полностью развернутый проект так, как он отображается в MSBuild, можно после включения пакета SDK и его целевых объектов с помощью команды `dotnet msbuild -preprocess`.</span><span class="sxs-lookup"><span data-stu-id="a306f-133">You can see the fully expanded project as MSBuild sees it after the SDK and its targets are included by using the `dotnet msbuild -preprocess` command.</span></span> <span data-ttu-id="a306f-134">Включите параметр [preprocess](/visualstudio/msbuild/msbuild-command-line-reference#preprocess) в команду [`dotnet msbuild`](../tools/dotnet-msbuild.md), чтобы просмотреть сведения об импортированных файлах, их источниках, вкладе в сборку без фактического создания проекта.</span><span class="sxs-lookup"><span data-stu-id="a306f-134">The [preprocess](/visualstudio/msbuild/msbuild-command-line-reference#preprocess) switch of the [`dotnet msbuild`](../tools/dotnet-msbuild.md) command shows which files are imported, their sources, and their contributions to the build without actually building the project.</span></span>

<span data-ttu-id="a306f-135">Если проект имеет несколько требуемых версий .NET Framework, результаты выполнения команды должны касаться только одной из них. Эту версию следует указать в качестве свойства MSBuild.</span><span class="sxs-lookup"><span data-stu-id="a306f-135">If the project has multiple target frameworks, focus the results of the command on only one framework by specifying it as an MSBuild property.</span></span> <span data-ttu-id="a306f-136">Пример:</span><span class="sxs-lookup"><span data-stu-id="a306f-136">For example:</span></span>

`dotnet msbuild -property:TargetFramework=netcoreapp2.0 -preprocess:output.xml`

### <a name="default-compilation-includes"></a><span data-ttu-id="a306f-137">Включения для элементов компиляции по умолчанию</span><span class="sxs-lookup"><span data-stu-id="a306f-137">Default compilation includes</span></span>

<span data-ttu-id="a306f-138">В пакете SDK определены заданные по умолчанию включения и исключения для элементов компиляции и внедренных ресурсов</span><span class="sxs-lookup"><span data-stu-id="a306f-138">The default includes and excludes for compile items and embedded resources are defined in the SDK.</span></span> <span data-ttu-id="a306f-139">В отличие от проектов .NET Framework без пакетов SDK в файле проекта не нужно указывать эти элементы, так как для наиболее распространенных вариантов использования действуют значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a306f-139">Unlike non-SDK .NET Framework projects, you don't need to specify these items in your project file, because the defaults cover most common use cases.</span></span> <span data-ttu-id="a306f-140">Это позволяет уменьшить файлы проекта и без труда понимать их, а также при необходимости вносить правки вручную.</span><span class="sxs-lookup"><span data-stu-id="a306f-140">This leads to smaller project files that are easier to understand as well as edit by hand, if needed.</span></span>

<span data-ttu-id="a306f-141">Следующая таблица показывает, какой элемент и какие [стандартные маски](https://en.wikipedia.org/wiki/Glob_(programming)) включены и исключены в пакете SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a306f-141">The following table shows which element and which [globs](https://en.wikipedia.org/wiki/Glob_(programming)) are included and excluded in the .NET Core SDK:</span></span>

| <span data-ttu-id="a306f-142">Элемент</span><span class="sxs-lookup"><span data-stu-id="a306f-142">Element</span></span>           | <span data-ttu-id="a306f-143">Стандартная маска включения</span><span class="sxs-lookup"><span data-stu-id="a306f-143">Include glob</span></span>                              | <span data-ttu-id="a306f-144">Стандартная маска исключения</span><span class="sxs-lookup"><span data-stu-id="a306f-144">Exclude glob</span></span>                                                  | <span data-ttu-id="a306f-145">Стандартная маска удаления</span><span class="sxs-lookup"><span data-stu-id="a306f-145">Remove glob</span></span>              |
|-------------------|-------------------------------------------|---------------------------------------------------------------|--------------------------|
| <span data-ttu-id="a306f-146">Компилятор</span><span class="sxs-lookup"><span data-stu-id="a306f-146">Compile</span></span>           | <span data-ttu-id="a306f-147">\*\*/\*.cs (или другие расширения языка)</span><span class="sxs-lookup"><span data-stu-id="a306f-147">\*\*/\*.cs (or other language extensions)</span></span> | <span data-ttu-id="a306f-148">\*\*/\*.user;  \*\*/\*.\*proj;  \*\*/\*.sln;  \*\*/\*.vssscc</span><span class="sxs-lookup"><span data-stu-id="a306f-148">\*\*/\*.user;  \*\*/\*.\*proj;  \*\*/\*.sln;  \*\*/\*.vssscc</span></span>  | <span data-ttu-id="a306f-149">Н/Д</span><span class="sxs-lookup"><span data-stu-id="a306f-149">N/A</span></span>                      |
| <span data-ttu-id="a306f-150">ВнедренныйРесурс</span><span class="sxs-lookup"><span data-stu-id="a306f-150">EmbeddedResource</span></span>  | <span data-ttu-id="a306f-151">\*\*/\*.resx</span><span class="sxs-lookup"><span data-stu-id="a306f-151">\*\*/\*.resx</span></span>                              | <span data-ttu-id="a306f-152">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span><span class="sxs-lookup"><span data-stu-id="a306f-152">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span></span>     | <span data-ttu-id="a306f-153">Н/Д</span><span class="sxs-lookup"><span data-stu-id="a306f-153">N/A</span></span>                      |
| <span data-ttu-id="a306f-154">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="a306f-154">None</span></span>              | \*\*/\*                                   | <span data-ttu-id="a306f-155">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span><span class="sxs-lookup"><span data-stu-id="a306f-155">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span></span>     | <span data-ttu-id="a306f-156">\*\*/\*.cs; \*\*/\*.resx</span><span class="sxs-lookup"><span data-stu-id="a306f-156">\*\*/\*.cs; \*\*/\*.resx</span></span> |

> [!NOTE]
> <span data-ttu-id="a306f-157">Папки `./bin` и `./obj`, которые представлены свойствами MSBuild `$(BaseOutputPath)` и `$(BaseIntermediateOutputPath)`, исключаются из стандартных масок исключения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a306f-157">The `./bin` and `./obj` folders, which are represented by the `$(BaseOutputPath)` and `$(BaseIntermediateOutputPath)` MSBuild properties, are excluded from the globs by default.</span></span> <span data-ttu-id="a306f-158">Исключения представляется свойством `$(DefaultItemExcludes)`.</span><span class="sxs-lookup"><span data-stu-id="a306f-158">Excludes are represented by the property `$(DefaultItemExcludes)`.</span></span>

<span data-ttu-id="a306f-159">При явном определении этих элементов в файле проекта, скорее всего, появится следующая ошибка:</span><span class="sxs-lookup"><span data-stu-id="a306f-159">If you explicitly define these items in your project file, you're likely to get the following error:</span></span>

<span data-ttu-id="a306f-160">**Duplicate Compile items were included. The .NET SDK includes Compile items from your project directory by default. You can either remove these items from your project file, or set the 'EnableDefaultCompileItems' property to 'false' if you want to explicitly include them in your project file. (Включены повторяющиеся элементы Compile. По умолчанию пакет SDK для .NET включает элементы Compile из каталога проекта. Можно удалить эти элементы из файла проекта или задать для свойства EnableDefaultCompileItems значение false, чтобы явно включить их в файл проекта).**</span><span class="sxs-lookup"><span data-stu-id="a306f-160">**Duplicate Compile items were included. The .NET SDK includes Compile items from your project directory by default. You can either remove these items from your project file, or set the 'EnableDefaultCompileItems' property to 'false' if you want to explicitly include them in your project file.**</span></span>

<span data-ttu-id="a306f-161">Чтобы устранить эту ошибку, удалите явные элементы `Compile`, совпадающие с неявными элементами, указанными в предыдущей таблице, или задайте свойству `EnableDefaultCompileItems` значение `false`, которое отключает неявное включение.</span><span class="sxs-lookup"><span data-stu-id="a306f-161">To resolve the error, either remove the explicit `Compile` items that match the implicit ones listed on the previous table, or set the `EnableDefaultCompileItems` property to `false`, which disables implicit inclusion:</span></span>

```xml
<PropertyGroup>
  <EnableDefaultCompileItems>false</EnableDefaultCompileItems>
</PropertyGroup>
```

<span data-ttu-id="a306f-162">Если вы хотите указать, например, отдельные файлы для публикации вместе со своим приложением, для этого можно по-прежнему использовать привычные механизмы MSBuild (например, элемент `Content`).</span><span class="sxs-lookup"><span data-stu-id="a306f-162">If you want to specify, for example, some files to get published with your app, you can still use the known MSBuild mechanisms for that, for example, the `Content` element.</span></span>

<span data-ttu-id="a306f-163">`EnableDefaultCompileItems` отключает только стандартные маски `Compile`, не затрагивая все остальные, например неявную стандартную маску `None`, которая также применяется к элементам \*.cs.</span><span class="sxs-lookup"><span data-stu-id="a306f-163">`EnableDefaultCompileItems` only disables `Compile` globs but doesn't affect other globs, like the implicit `None` glob that also applies to \*.cs items.</span></span> <span data-ttu-id="a306f-164">Из-за этого обозреватель решений в Visual Studio отображает элементы \*.cs как часть проекта, включенную в виде элементов `None`.</span><span class="sxs-lookup"><span data-stu-id="a306f-164">Because of that, Solution Explorer in Visual Studio shows \*.cs items as part of the project, included as `None` items.</span></span> <span data-ttu-id="a306f-165">Чтобы отключить неявную стандартную маску `None`, задайте свойству `EnableDefaultNoneItems` значение `false`.</span><span class="sxs-lookup"><span data-stu-id="a306f-165">To disable the implicit `None` glob, set `EnableDefaultNoneItems` to `false`:</span></span>

```xml
<PropertyGroup>
  <EnableDefaultNoneItems>false</EnableDefaultNoneItems>
</PropertyGroup>
```

<span data-ttu-id="a306f-166">Чтобы отключить *все* неявные стандартные маски, задайте свойству `EnableDefaultItems` значение `false`.</span><span class="sxs-lookup"><span data-stu-id="a306f-166">To disable *all* implicit globs, set the `EnableDefaultItems` property to `false`:</span></span>

```xml
<PropertyGroup>
  <EnableDefaultItems>false</EnableDefaultItems>
</PropertyGroup>
```

## <a name="customize-the-build"></a><span data-ttu-id="a306f-167">Настройка сборки</span><span class="sxs-lookup"><span data-stu-id="a306f-167">Customize the build</span></span>

<span data-ttu-id="a306f-168">Существует несколько способов [настройки сборки](/visualstudio/msbuild/customize-your-build).</span><span class="sxs-lookup"><span data-stu-id="a306f-168">There are various ways to [customize a build](/visualstudio/msbuild/customize-your-build).</span></span> <span data-ttu-id="a306f-169">Может потребоваться переопределить свойство, передав его в качестве аргумента в команду [msbuild](/visualstudio/msbuild/msbuild-command-line-reference) или [dotnet](../tools/index.md).</span><span class="sxs-lookup"><span data-stu-id="a306f-169">You may want to override a property by passing it as an argument to an [msbuild](/visualstudio/msbuild/msbuild-command-line-reference) or [dotnet](../tools/index.md) command.</span></span> <span data-ttu-id="a306f-170">Можно также добавить свойство в файл проекта или в файл *Directory.Build.props*.</span><span class="sxs-lookup"><span data-stu-id="a306f-170">You can also add the property to the project file or to a *Directory.Build.props* file.</span></span> <span data-ttu-id="a306f-171">Список полезных свойств для проектов .NET Core см. в статье [Свойства MSBuild для проектов пакета SDK для .NET Core](msbuild-props.md).</span><span class="sxs-lookup"><span data-stu-id="a306f-171">For a list of useful properties for .NET Core projects, see [MSBuild properties for .NET Core SDK projects](msbuild-props.md).</span></span>

### <a name="custom-targets"></a><span data-ttu-id="a306f-172">Пользовательские целевые объекты</span><span class="sxs-lookup"><span data-stu-id="a306f-172">Custom targets</span></span>

<span data-ttu-id="a306f-173">В проектах .NET Core доступна возможность упаковки пользовательских целевых объектов и свойства MSBuild для использования в проектах, применяющих этот пакет.</span><span class="sxs-lookup"><span data-stu-id="a306f-173">.NET Core projects can package custom MSBuild targets and properties for use by projects that consume the package.</span></span> <span data-ttu-id="a306f-174">Используйте этот тип расширяемости, если нужно выполнить следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="a306f-174">Use this type of extensibility when you want to:</span></span>

- <span data-ttu-id="a306f-175">расширить процесс сборки;</span><span class="sxs-lookup"><span data-stu-id="a306f-175">Extend the build process.</span></span>
- <span data-ttu-id="a306f-176">получить доступ к артефактам процесса сборки, таким как созданные файлы;</span><span class="sxs-lookup"><span data-stu-id="a306f-176">Access artifacts of the build process, such as generated files.</span></span>
- <span data-ttu-id="a306f-177">проверить конфигурацию, с которой была запущена сборка.</span><span class="sxs-lookup"><span data-stu-id="a306f-177">Inspect the configuration under which the build is invoked.</span></span>

<span data-ttu-id="a306f-178">Чтобы добавить пользовательские целевые объекты или свойства сборки, нужно поместить файлы в форме `<package_id>.targets` или `<package_id>.props` (например, `Contoso.Utility.UsefulStuff.targets`) в папку *build* проекта.</span><span class="sxs-lookup"><span data-stu-id="a306f-178">You add custom build targets or properties by placing files in the form `<package_id>.targets` or `<package_id>.props` (for example, `Contoso.Utility.UsefulStuff.targets`) in the *build* folder of the project.</span></span>

<span data-ttu-id="a306f-179">Следующий XML-код является фрагментом из файла *CPROJ*, который указывает команде [`dotnet pack`](../tools/dotnet-pack.md), что именно нужно упаковать.</span><span class="sxs-lookup"><span data-stu-id="a306f-179">The following XML is a snippet from a *.csproj* file that instructs the [`dotnet pack`](../tools/dotnet-pack.md) command what to package.</span></span> <span data-ttu-id="a306f-180">Элемент `<ItemGroup Label="dotnet pack instructions">` помещает файлы целевых объектов в папку *build* в пакете.</span><span class="sxs-lookup"><span data-stu-id="a306f-180">The `<ItemGroup Label="dotnet pack instructions">` element places the targets files into the *build* folder inside the package.</span></span> <span data-ttu-id="a306f-181">Элемент `<Target Name="CollectRuntimeOutputs" BeforeTargets="_GetPackageFiles">` помещает сборки и файлы *JSON* в папку *build*.</span><span class="sxs-lookup"><span data-stu-id="a306f-181">The `<Target Name="CollectRuntimeOutputs" BeforeTargets="_GetPackageFiles">` element places the assemblies and *.json* files into the *build* folder.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  ...
  <ItemGroup Label="dotnet pack instructions">
    <Content Include="build\*.targets">
      <Pack>true</Pack>
      <PackagePath>build\</PackagePath>
    </Content>
  </ItemGroup>
  <Target Name="CollectRuntimeOutputs" BeforeTargets="_GetPackageFiles">
    <!-- Collect these items inside a target that runs after build but before packaging. -->
    <ItemGroup>
      <Content Include="$(OutputPath)\*.dll;$(OutputPath)\*.json">
        <Pack>true</Pack>
        <PackagePath>build\</PackagePath>
      </Content>
    </ItemGroup>
  </Target>
  ...
  
</Project>
```

<span data-ttu-id="a306f-182">Чтобы использовать пользовательский целевой объект в проекте, добавьте элемент `PackageReference`, указывающий на пакет и его версию.</span><span class="sxs-lookup"><span data-stu-id="a306f-182">To consume a custom target in your project, add a `PackageReference` element that points to the package and its version.</span></span> <span data-ttu-id="a306f-183">В отличие от средств пакет пользовательских целевых объектов входит в замыкание зависимостей исходного проекта.</span><span class="sxs-lookup"><span data-stu-id="a306f-183">Unlike the tools, the custom targets package is included in the consuming project's dependency closure.</span></span>

<span data-ttu-id="a306f-184">Вы можете настроить способ использования пользовательского целевого объекта.</span><span class="sxs-lookup"><span data-stu-id="a306f-184">You can configure how to use the custom target.</span></span> <span data-ttu-id="a306f-185">Так как это целевой объект MSBuild, он может зависеть от заданного целевого объекта, запускаться после другого целевого объекта или быть вызван вручную с помощью команды `dotnet msbuild -t:<target-name>`.</span><span class="sxs-lookup"><span data-stu-id="a306f-185">Since it's an MSBuild target, it can depend on a given target, run after another target, or be manually invoked by using the `dotnet msbuild -t:<target-name>` command.</span></span> <span data-ttu-id="a306f-186">Однако для удобства пользователей можно объединить средства для отдельных проектов и пользовательские целевые объекты.</span><span class="sxs-lookup"><span data-stu-id="a306f-186">However, to provide a better user experience, you can combine per-project tools and custom targets.</span></span> <span data-ttu-id="a306f-187">В этом сценарии средство для отдельного проекта принимает необходимые параметры и преобразует их в требуемый вызов [`dotnet msbuild`](../tools/dotnet-msbuild.md), который выполняет целевой объект.</span><span class="sxs-lookup"><span data-stu-id="a306f-187">In this scenario, the per-project tool accepts whatever parameters are needed and translates that into the required [`dotnet msbuild`](../tools/dotnet-msbuild.md) invocation that executes the target.</span></span> <span data-ttu-id="a306f-188">Пример подобного типа синергии можно увидеть в репозитории [примеров хакатона MVP Summit 2016](https://github.com/dotnet/MVPSummitHackathon2016) в проекте [`dotnet-packer`](https://github.com/dotnet/MVPSummitHackathon2016/tree/master/dotnet-packer).</span><span class="sxs-lookup"><span data-stu-id="a306f-188">You can see a sample of this kind of synergy on the [MVP Summit 2016 Hackathon samples](https://github.com/dotnet/MVPSummitHackathon2016) repo in the [`dotnet-packer`](https://github.com/dotnet/MVPSummitHackathon2016/tree/master/dotnet-packer) project.</span></span>

## <a name="see-also"></a><span data-ttu-id="a306f-189">См. также</span><span class="sxs-lookup"><span data-stu-id="a306f-189">See also</span></span>

- <span data-ttu-id="a306f-190">[установите .NET Core](../install/index.md).</span><span class="sxs-lookup"><span data-stu-id="a306f-190">[Install .NET Core](../install/index.md)</span></span>
- [<span data-ttu-id="a306f-191">Использование пакетов SDK проекта MSBuild</span><span class="sxs-lookup"><span data-stu-id="a306f-191">How to use MSBuild project SDKs</span></span>](/visualstudio/msbuild/how-to-use-project-sdk)
- [<span data-ttu-id="a306f-192">Упаковка пользовательских целевых объектов и свойств MSBuild с помощью NuGet</span><span class="sxs-lookup"><span data-stu-id="a306f-192">Package custom MSBuild targets and props with NuGet</span></span>](/nuget/create-packages/creating-a-package#include-msbuild-props-and-targets-in-a-package)
