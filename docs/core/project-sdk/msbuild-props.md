---
title: Свойства MSBuild для Microsoft.NET.Sdk
description: Справочник по свойствам и элементам MSBuild, распознаваемым пакетом SDK для .NET Core.
ms.date: 02/14/2020
ms.topic: reference
ms.custom: updateeachrelease
ms.openlocfilehash: 39cbd18121d2b8659b2f5270f39624798f4ebbdc
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88810528"
---
# <a name="msbuild-reference-for-net-core-sdk-projects"></a><span data-ttu-id="691e6-103">Справочник по MSBuild для проектов пакета SDK для .NET Core</span><span class="sxs-lookup"><span data-stu-id="691e6-103">MSBuild reference for .NET Core SDK projects</span></span>

<span data-ttu-id="691e6-104">Эта страница содержит справочные сведения о свойствах и элементах MSBuild, которые вы можете использовать для настройки проектов .NET Core.</span><span class="sxs-lookup"><span data-stu-id="691e6-104">This page is a reference for the MSBuild properties and items that you can use to configure .NET Core projects.</span></span>

> [!NOTE]
> <span data-ttu-id="691e6-105">Работа над этой страницей еще не завершена, поэтому здесь приведены лишь некоторые полезные свойства MSBuild для пакета SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="691e6-105">This page is a work in progress and does not list all of the useful MSBuild properties for the .NET Core SDK.</span></span> <span data-ttu-id="691e6-106">Список стандартных свойств см. в статье [Общие свойства MSBuild](/visualstudio/msbuild/common-msbuild-project-properties).</span><span class="sxs-lookup"><span data-stu-id="691e6-106">For a list of common MSBuild properties, see [Common MSBuild properties](/visualstudio/msbuild/common-msbuild-project-properties).</span></span>

## <a name="framework-properties"></a><span data-ttu-id="691e6-107">Свойства платформы</span><span class="sxs-lookup"><span data-stu-id="691e6-107">Framework properties</span></span>

- [<span data-ttu-id="691e6-108">TargetFramework</span><span class="sxs-lookup"><span data-stu-id="691e6-108">TargetFramework</span></span>](#targetframework)
- [<span data-ttu-id="691e6-109">TargetFrameworks</span><span class="sxs-lookup"><span data-stu-id="691e6-109">TargetFrameworks</span></span>](#targetframeworks)
- [<span data-ttu-id="691e6-110">NetStandardImplicitPackageVersion</span><span class="sxs-lookup"><span data-stu-id="691e6-110">NetStandardImplicitPackageVersion</span></span>](#netstandardimplicitpackageversion)

### <a name="targetframework"></a><span data-ttu-id="691e6-111">TargetFramework</span><span class="sxs-lookup"><span data-stu-id="691e6-111">TargetFramework</span></span>

<span data-ttu-id="691e6-112">Свойство `TargetFramework` определяет версию целевой платформы для приложения.</span><span class="sxs-lookup"><span data-stu-id="691e6-112">The `TargetFramework` property specifies the target framework version for the app.</span></span> <span data-ttu-id="691e6-113">Список допустимых моникеров целевой платформы см. в статье [Целевые платформы в проектах в стиле SDK](../../standard/frameworks.md#supported-target-framework-versions).</span><span class="sxs-lookup"><span data-stu-id="691e6-113">For a list of valid target framework monikers, see [Target frameworks in SDK-style projects](../../standard/frameworks.md#supported-target-framework-versions).</span></span>

```xml
<PropertyGroup>
  <TargetFramework>netcoreapp3.1</TargetFramework>
</PropertyGroup>
```

<span data-ttu-id="691e6-114">Дополнительные сведения см.в статье [Целевые платформы в проектах в стиле SDK](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="691e6-114">For more information, see [Target frameworks in SDK-style projects](../../standard/frameworks.md).</span></span>

### <a name="targetframeworks"></a><span data-ttu-id="691e6-115">TargetFrameworks</span><span class="sxs-lookup"><span data-stu-id="691e6-115">TargetFrameworks</span></span>

<span data-ttu-id="691e6-116">Используйте свойство `TargetFrameworks`, если приложение должно быть предназначено для нескольких платформ.</span><span class="sxs-lookup"><span data-stu-id="691e6-116">Use the `TargetFrameworks` property when you want your app to target multiple platforms.</span></span> <span data-ttu-id="691e6-117">Список допустимых моникеров целевой платформы см. в статье [Целевые платформы в проектах в стиле SDK](../../standard/frameworks.md#supported-target-framework-versions).</span><span class="sxs-lookup"><span data-stu-id="691e6-117">For a list of valid target framework monikers, see [Target frameworks in SDK-style projects](../../standard/frameworks.md#supported-target-framework-versions).</span></span>

> [!NOTE]
> <span data-ttu-id="691e6-118">Это свойство игнорируется, если указано свойство `TargetFramework` (в единственном числе).</span><span class="sxs-lookup"><span data-stu-id="691e6-118">This property is ignored if `TargetFramework` (singular) is specified.</span></span>

```xml
<PropertyGroup>
  <TargetFrameworks>netcoreapp3.1;net462</TargetFrameworks>
</PropertyGroup>
```

<span data-ttu-id="691e6-119">Дополнительные сведения см.в статье [Целевые платформы в проектах в стиле SDK](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="691e6-119">For more information, see [Target frameworks in SDK-style projects](../../standard/frameworks.md).</span></span>

### <a name="netstandardimplicitpackageversion"></a><span data-ttu-id="691e6-120">NetStandardImplicitPackageVersion</span><span class="sxs-lookup"><span data-stu-id="691e6-120">NetStandardImplicitPackageVersion</span></span>

> [!NOTE]
> <span data-ttu-id="691e6-121">Это свойство применяется только к проектам, использующим `netstandard1.x`.</span><span class="sxs-lookup"><span data-stu-id="691e6-121">This property only applies to projects using `netstandard1.x`.</span></span> <span data-ttu-id="691e6-122">Он не применяется к проектам, использующим `netstandard2.x`.</span><span class="sxs-lookup"><span data-stu-id="691e6-122">It doesn't apply to projects that use `netstandard2.x`.</span></span>

<span data-ttu-id="691e6-123">Используйте свойство `NetStandardImplicitPackageVersion`, если вам нужно указать версию платформы ниже версии метапакета.</span><span class="sxs-lookup"><span data-stu-id="691e6-123">Use the `NetStandardImplicitPackageVersion` property when you want to specify a framework version that's lower than the metapackage version.</span></span> <span data-ttu-id="691e6-124">Файл проекта, приведенный в следующем примере, предназначен для `netstandard1.3`, но использует `NETStandard.Library` версии 1.6.0.</span><span class="sxs-lookup"><span data-stu-id="691e6-124">The project file in the following example targets `netstandard1.3` but uses the 1.6.0 version of `NETStandard.Library`.</span></span>

```xml
<PropertyGroup>
  <TargetFramework>netstandard1.3</TargetFramework>
  <NetStandardImplicitPackageVersion>1.6.0</NetStandardImplicitPackageVersion>
</PropertyGroup>
```

## <a name="package-properties"></a><span data-ttu-id="691e6-125">Свойства пакета</span><span class="sxs-lookup"><span data-stu-id="691e6-125">Package properties</span></span>

<span data-ttu-id="691e6-126">Для описания пакета, созданного из проекта, можно указать такие свойства, как `PackageId`, `PackageVersion`, `PackageIcon`, `Title` и `Description`.</span><span class="sxs-lookup"><span data-stu-id="691e6-126">You can specify properties such as `PackageId`, `PackageVersion`, `PackageIcon`, `Title`, and `Description` to describe the package that gets created from your project.</span></span> <span data-ttu-id="691e6-127">Дополнительные сведения об этих и других свойствах см. в разделе [целевой объект пакета](/nuget/reference/msbuild-targets#pack-target).</span><span class="sxs-lookup"><span data-stu-id="691e6-127">For information about these and other properties, see [pack target](/nuget/reference/msbuild-targets#pack-target).</span></span>

```xml
<PropertyGroup>
  ...
  <PackageId>ClassLibDotNetStandard</PackageId>
  <Version>1.0.0</Version>
  <Authors>John Doe</Authors>
  <Company>Contoso</Company>
</PropertyGroup>
```

## <a name="publish-properties-and-items"></a><span data-ttu-id="691e6-128">Публикация свойств и элементов</span><span class="sxs-lookup"><span data-stu-id="691e6-128">Publish properties and items</span></span>

- [<span data-ttu-id="691e6-129">RuntimeIdentifier</span><span class="sxs-lookup"><span data-stu-id="691e6-129">RuntimeIdentifier</span></span>](#runtimeidentifier)
- [<span data-ttu-id="691e6-130">RuntimeIdentifiers</span><span class="sxs-lookup"><span data-stu-id="691e6-130">RuntimeIdentifiers</span></span>](#runtimeidentifiers)
- [<span data-ttu-id="691e6-131">TrimmerRootAssembly</span><span class="sxs-lookup"><span data-stu-id="691e6-131">TrimmerRootAssembly</span></span>](#trimmerrootassembly)
- [<span data-ttu-id="691e6-132">UseAppHost</span><span class="sxs-lookup"><span data-stu-id="691e6-132">UseAppHost</span></span>](#useapphost)

### <a name="runtimeidentifier"></a><span data-ttu-id="691e6-133">RuntimeIdentifier</span><span class="sxs-lookup"><span data-stu-id="691e6-133">RuntimeIdentifier</span></span>

<span data-ttu-id="691e6-134">Свойство `RuntimeIdentifier` позволяет указать для проекта один [идентификатор среды выполнения (RID)](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="691e6-134">The `RuntimeIdentifier` property lets you specify a single [runtime identifier (RID)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="691e6-135">Идентификатор среды выполнения позволяет опубликовать автономное развертывание.</span><span class="sxs-lookup"><span data-stu-id="691e6-135">The RID enables publishing a self-contained deployment.</span></span>

```xml
<PropertyGroup>
  <RuntimeIdentifier>ubuntu.16.04-x64</RuntimeIdentifier>
</PropertyGroup>
```

### <a name="runtimeidentifiers"></a><span data-ttu-id="691e6-136">RuntimeIdentifiers</span><span class="sxs-lookup"><span data-stu-id="691e6-136">RuntimeIdentifiers</span></span>

<span data-ttu-id="691e6-137">Свойство `RuntimeIdentifiers` позволяет указать для проекта список [идентификаторов среды выполнения (RID)](../rid-catalog.md) (в качестве разделителя используется точка с запятой).</span><span class="sxs-lookup"><span data-stu-id="691e6-137">The `RuntimeIdentifiers` property lets you specify a semicolon-delimited list of [runtime identifiers (RIDs)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="691e6-138">Используйте это свойство, если вам нужна публикация для нескольких сред.</span><span class="sxs-lookup"><span data-stu-id="691e6-138">Use this property if you need to publish for multiple runtimes.</span></span> <span data-ttu-id="691e6-139">`RuntimeIdentifiers` используется во время восстановления для обеспечения наличия в графе нужных ресурсов.</span><span class="sxs-lookup"><span data-stu-id="691e6-139">`RuntimeIdentifiers` is used at restore time to ensure the right assets are in the graph.</span></span>

> [!TIP]
> <span data-ttu-id="691e6-140">`RuntimeIdentifier` (в единственном числе) может ускорить создание сборок, когда требуется только одна среда выполнения.</span><span class="sxs-lookup"><span data-stu-id="691e6-140">`RuntimeIdentifier` (singular) can provide faster builds when only a single runtime is required.</span></span>

```xml
<PropertyGroup>
  <RuntimeIdentifiers>win10-x64;osx.10.11-x64;ubuntu.16.04-x64</RuntimeIdentifiers>
</PropertyGroup>
```

### <a name="trimmerrootassembly"></a><span data-ttu-id="691e6-141">TrimmerRootAssembly</span><span class="sxs-lookup"><span data-stu-id="691e6-141">TrimmerRootAssembly</span></span>

<span data-ttu-id="691e6-142">Элемент `TrimmerRootAssembly` позволяет исключить сборку из [*обрезки*](../deploying/trim-self-contained.md).</span><span class="sxs-lookup"><span data-stu-id="691e6-142">The `TrimmerRootAssembly` item lets you exclude an assembly from [*trimming*](../deploying/trim-self-contained.md).</span></span> <span data-ttu-id="691e6-143">Обрезка — это процесс удаления неиспользуемых частей среды выполнения из упакованного приложения.</span><span class="sxs-lookup"><span data-stu-id="691e6-143">Trimming is the process of removing unused parts of the runtime from a packaged application.</span></span> <span data-ttu-id="691e6-144">В некоторых случаях при обрезке могут неправильно удаляться необходимые ссылки.</span><span class="sxs-lookup"><span data-stu-id="691e6-144">In some cases, trimming might incorrectly remove required references.</span></span>

<span data-ttu-id="691e6-145">Следующий код XML исключает сборку `System.Security` из обрезки.</span><span class="sxs-lookup"><span data-stu-id="691e6-145">The following XML excludes the `System.Security` assembly from trimming.</span></span>

```xml
<ItemGroup>
  <TrimmerRootAssembly Include="System.Security" />
</ItemGroup>
```

### <a name="useapphost"></a><span data-ttu-id="691e6-146">UseAppHost</span><span class="sxs-lookup"><span data-stu-id="691e6-146">UseAppHost</span></span>

<span data-ttu-id="691e6-147">Свойство `UseAppHost` было представлено в пакете SDK для .NET Core.версии 2.1.400.</span><span class="sxs-lookup"><span data-stu-id="691e6-147">The `UseAppHost` property was introduced in the 2.1.400 version of the .NET Core SDK.</span></span> <span data-ttu-id="691e6-148">Оно контролирует создание собственного исполняемого файла для развертывания.</span><span class="sxs-lookup"><span data-stu-id="691e6-148">It controls whether or not a native executable is created for a deployment.</span></span> <span data-ttu-id="691e6-149">Этот файл требуется для автономных развертываний.</span><span class="sxs-lookup"><span data-stu-id="691e6-149">A native executable is required for self-contained deployments.</span></span>

<span data-ttu-id="691e6-150">В .NET Core 3.0 и более поздних версиях зависимый от платформы исполняемый файл создается по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="691e6-150">In .NET Core 3.0 and later versions, a framework-dependent executable is created by default.</span></span> <span data-ttu-id="691e6-151">Задайте свойству `UseAppHost` значение `false`, чтобы отключить создание исполняемого файла.</span><span class="sxs-lookup"><span data-stu-id="691e6-151">Set the `UseAppHost` property to `false` to disable generation of the executable.</span></span>

```xml
<PropertyGroup>
  <UseAppHost>false</UseAppHost>
</PropertyGroup>
```

<span data-ttu-id="691e6-152">Дополнительные сведения о развертывании см. в статье [Развертывание приложений .NET Core](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="691e6-152">For more information about deployment, see [.NET Core application deployment](../deploying/index.md).</span></span>

## <a name="compile-properties"></a><span data-ttu-id="691e6-153">Свойства компиляции</span><span class="sxs-lookup"><span data-stu-id="691e6-153">Compile properties</span></span>

- [<span data-ttu-id="691e6-154">EmbeddedResourceUseDependentUponConvention</span><span class="sxs-lookup"><span data-stu-id="691e6-154">EmbeddedResourceUseDependentUponConvention</span></span>](#embeddedresourceusedependentuponconvention)
- [<span data-ttu-id="691e6-155">LangVersion</span><span class="sxs-lookup"><span data-stu-id="691e6-155">LangVersion</span></span>](#langversion)

### <a name="embeddedresourceusedependentuponconvention"></a><span data-ttu-id="691e6-156">EmbeddedResourceUseDependentUponConvention</span><span class="sxs-lookup"><span data-stu-id="691e6-156">EmbeddedResourceUseDependentUponConvention</span></span>

<span data-ttu-id="691e6-157">Свойство `EmbeddedResourceUseDependentUponConvention` определяет, будет ли использоваться информация о типах в исходных файлах, расположенных в одной папке с файлами ресурсов, для создания имен файлов манифеста этих ресурсов.</span><span class="sxs-lookup"><span data-stu-id="691e6-157">The `EmbeddedResourceUseDependentUponConvention` property defines whether resource manifest file names are generated from type information in source files that are colocated with resource files.</span></span> <span data-ttu-id="691e6-158">Например, если *Form1.resx* находится в той же папке, что и *Form1.cs*, а `EmbeddedResourceUseDependentUponConvention` имеет значение `true`, то созданному файл *.resources* присваивается имя на основе имени первого типа, определенного в файле *Form1.cs*.</span><span class="sxs-lookup"><span data-stu-id="691e6-158">For example, if *Form1.resx* is in the same folder as *Form1.cs*, and `EmbeddedResourceUseDependentUponConvention` is set to `true`, the generated *.resources* file takes its name from the first type that's defined in *Form1.cs*.</span></span> <span data-ttu-id="691e6-159">Например, если первым типом в файле *Form1.cs* является `MyNamespace.Form1`, созданному файлу присваивается имя *MyNamespace.Form1.resources*.</span><span class="sxs-lookup"><span data-stu-id="691e6-159">For example, if `MyNamespace.Form1` is the first type defined in *Form1.cs*, the generated file name is *MyNamespace.Form1.resources*.</span></span>

> [!NOTE]
> <span data-ttu-id="691e6-160">Если для `EmbeddedResource` элемента заданы метаданные `LogicalName`, `ManifestResourceName` или `DependentUpon`, то имя файла манифеста для этого файла ресурсов будет создаваться на основе таких метаданных.</span><span class="sxs-lookup"><span data-stu-id="691e6-160">If `LogicalName`, `ManifestResourceName`, or `DependentUpon` metadata is specified for an `EmbeddedResource` item, the generated manifest file name for that resource file is based on that metadata instead.</span></span>

<span data-ttu-id="691e6-161">По умолчанию для нового проекта .NET Core этому свойству задается значение `true`.</span><span class="sxs-lookup"><span data-stu-id="691e6-161">By default, in a new .NET Core project, this property is set to `true`.</span></span> <span data-ttu-id="691e6-162">Если задано значение `false` и для элемента `EmbeddedResource` в файле проекта не указаны метаданные `LogicalName`, `ManifestResourceName` или `DependentUpon`, то имя файла манифеста для этого ресурса будет основано на имени корневого пространства имен проекта и относительном пути к файлу *.resx*.</span><span class="sxs-lookup"><span data-stu-id="691e6-162">If set to `false`, and no `LogicalName`, `ManifestResourceName`, or `DependentUpon` metadata is specified for the `EmbeddedResource` item in the project file, the resource manifest file name is based off the root namespace for the project and the relative file path to the *.resx* file.</span></span> <span data-ttu-id="691e6-163">Дополнительные сведения об определение имени файла манифеста см. [здесь](../resources/manifest-file-names.md).</span><span class="sxs-lookup"><span data-stu-id="691e6-163">For more information, see [How resource manifest files are named](../resources/manifest-file-names.md).</span></span>

```xml
<PropertyGroup>
  <EmbeddedResourceUseDependentUponConvention>true</EmbeddedResourceUseDependentUponConvention>
</PropertyGroup>
```

### <a name="langversion"></a><span data-ttu-id="691e6-164">LangVersion</span><span class="sxs-lookup"><span data-stu-id="691e6-164">LangVersion</span></span>

<span data-ttu-id="691e6-165">Свойство `LangVersion` позволяет указать конкретную версию языка программирования.</span><span class="sxs-lookup"><span data-stu-id="691e6-165">The `LangVersion` property lets you specify a specific programming language version.</span></span> <span data-ttu-id="691e6-166">Например, если требуется доступ к предварительным версиям функций C#, задайте параметру `LangVersion` значение `preview`.</span><span class="sxs-lookup"><span data-stu-id="691e6-166">For example, if you want access to C# preview features, set `LangVersion` to `preview`.</span></span>

```xml
<PropertyGroup>
  <LangVersion>preview</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="691e6-167">Дополнительные сведения см. в статье [Управление версиями языка C#](../../csharp/language-reference/configure-language-version.md#override-a-default).</span><span class="sxs-lookup"><span data-stu-id="691e6-167">For more information, see [C# language versioning](../../csharp/language-reference/configure-language-version.md#override-a-default).</span></span>

## <a name="code-analysis-properties"></a><span data-ttu-id="691e6-168">Свойства анализа кода</span><span class="sxs-lookup"><span data-stu-id="691e6-168">Code analysis properties</span></span>

### <a name="analysislevel"></a><span data-ttu-id="691e6-169">AnalysisLevel</span><span class="sxs-lookup"><span data-stu-id="691e6-169">AnalysisLevel</span></span>

<span data-ttu-id="691e6-170">Свойство `AnalysisLevel` позволяет указать уровень анализа кода.</span><span class="sxs-lookup"><span data-stu-id="691e6-170">The `AnalysisLevel` property lets you specify a code analysis level.</span></span> <span data-ttu-id="691e6-171">Например, если требуется доступ к анализаторам кода предварительной версии, задайте для параметра `AnalysisLevel` значение `preview`.</span><span class="sxs-lookup"><span data-stu-id="691e6-171">For example, if you want access to preview code analyzers, set `AnalysisLevel` to `preview`.</span></span> <span data-ttu-id="691e6-172">Значение по умолчанию — `latest`.</span><span class="sxs-lookup"><span data-stu-id="691e6-172">The default value is `latest`.</span></span>

```xml
<PropertyGroup>
  <AnalysisLevel>preview</AnalysisLevel>
</PropertyGroup>
```

<span data-ttu-id="691e6-173">В следующей таблице приведены доступные параметры.</span><span class="sxs-lookup"><span data-stu-id="691e6-173">The following table shows the available options.</span></span>

| <span data-ttu-id="691e6-174">Значение</span><span class="sxs-lookup"><span data-stu-id="691e6-174">Value</span></span> | <span data-ttu-id="691e6-175">Значение</span><span class="sxs-lookup"><span data-stu-id="691e6-175">Meaning</span></span> |
|-|-|
| `latest` | <span data-ttu-id="691e6-176">Используются новейшие анализаторы кода, которые были выпущены.</span><span class="sxs-lookup"><span data-stu-id="691e6-176">The latest code analyzers that have been released are used.</span></span> <span data-ttu-id="691e6-177">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="691e6-177">This is the default.</span></span> |
| `preview` | <span data-ttu-id="691e6-178">Используются новейшие анализаторы кода, даже если они находятся на этапе предварительной версии.</span><span class="sxs-lookup"><span data-stu-id="691e6-178">The latest code analyzers are used, even if they are in preview.</span></span> |
| `5.0` | <span data-ttu-id="691e6-179">Используется набор правил, включенных для выпуска .NET 5.0, даже если доступны новые правила.</span><span class="sxs-lookup"><span data-stu-id="691e6-179">The set of rules that was enabled for the .NET 5.0 release is used, even if newer rules are available.</span></span> |
| `5` | <span data-ttu-id="691e6-180">Используется набор правил, включенных для выпуска .NET 5.0, даже если доступны новые правила.</span><span class="sxs-lookup"><span data-stu-id="691e6-180">The set of rules that was enabled for the .NET 5.0 release is used, even if newer rules are available.</span></span> |

### <a name="codeanalysistreatwarningsaserrors"></a><span data-ttu-id="691e6-181">CodeAnalysisTreatWarningsAsErrors</span><span class="sxs-lookup"><span data-stu-id="691e6-181">CodeAnalysisTreatWarningsAsErrors</span></span>

<span data-ttu-id="691e6-182">Свойство `CodeAnalysisTreatWarningsAsErrors` позволяет настроить, следует ли обрабатывать предупреждения анализа кода как предупреждения и прекращать сборку.</span><span class="sxs-lookup"><span data-stu-id="691e6-182">The `CodeAnalysisTreatWarningsAsErrors` property lets you configure whether code analysis warnings should be treated as warnings and break the build.</span></span> <span data-ttu-id="691e6-183">Если при построении проектов используется флаг `-warnaserror`, предупреждения [анализа кода .NET](../../fundamentals/productivity/code-analysis.md) также обрабатываются как ошибки.</span><span class="sxs-lookup"><span data-stu-id="691e6-183">If you use the `-warnaserror` flag when you build your projects, [.NET code analysis](../../fundamentals/productivity/code-analysis.md) warnings are also treated as errors.</span></span> <span data-ttu-id="691e6-184">Если вы хотите, чтобы предупреждения компилятора обрабатывались как ошибки, можно задать для свойства MSBuild `CodeAnalysisTreatWarningsAsErrors` значение `false` в файле проекта.</span><span class="sxs-lookup"><span data-stu-id="691e6-184">If you only want compiler warnings to be treated as errors, you can set the `CodeAnalysisTreatWarningsAsErrors` MSBuild property to `false` in your project file.</span></span>

```xml
<PropertyGroup>
  <CodeAnalysisTreatWarningsAsErrors>false</CodeAnalysisTreatWarningsAsErrors>
</PropertyGroup>
```

### <a name="enablenetanalyzers"></a><span data-ttu-id="691e6-185">EnableNETAnalyzers</span><span class="sxs-lookup"><span data-stu-id="691e6-185">EnableNETAnalyzers</span></span>

<span data-ttu-id="691e6-186">Для проектов, предназначенных для .NET 5.0 или более поздней версии, по умолчанию включен [анализ кода .NET](../../fundamentals/productivity/code-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="691e6-186">[.NET Code analysis](../../fundamentals/productivity/code-analysis.md) is enabled, by default, for projects that target .NET 5.0 or later.</span></span> <span data-ttu-id="691e6-187">Вы можете включить анализ кода .NET для проектов, предназначенных для более ранних версий .NET, установив для свойства `EnableNETAnalyzers` значение true.</span><span class="sxs-lookup"><span data-stu-id="691e6-187">You can enable .NET code analysis for projects that target earlier versions of .NET by setting the `EnableNETAnalyzers` property to true.</span></span> <span data-ttu-id="691e6-188">Чтобы отключить анализ кода в любом проекте, присвойте этому свойству значение `false`.</span><span class="sxs-lookup"><span data-stu-id="691e6-188">To disable code analysis in any project, set this property to `false`.</span></span>

```xml
<PropertyGroup>
  <EnableNETAnalyzers>true</EnableNETAnalyzers>
</PropertyGroup>
```

> [!TIP]
> <span data-ttu-id="691e6-189">Другой способ включить анализ кода .NET для проектов, предназначенных для версий .NET до .NET 5.0, — задать для свойства [AnalysisLevel](#analysislevel) значение `latest`.</span><span class="sxs-lookup"><span data-stu-id="691e6-189">Another way to enable .NET code analysis on projects that target .NET versions prior to .NET 5.0 is to set the [AnalysisLevel](#analysislevel) property to `latest`.</span></span>

## <a name="run-time-configuration-properties"></a><span data-ttu-id="691e6-190">Свойства конфигурации среды выполнения</span><span class="sxs-lookup"><span data-stu-id="691e6-190">Run-time configuration properties</span></span>

<span data-ttu-id="691e6-191">Вы можете настроить некоторые варианты поведения среды выполнения, указав свойства MSBuild в файле проекта приложения.</span><span class="sxs-lookup"><span data-stu-id="691e6-191">You can configure some run-time behaviors by specifying MSBuild properties in the project file of the app.</span></span> <span data-ttu-id="691e6-192">Сведения о других способах настройки поведения среды выполнения см. в разделе [Параметры конфигурации среды выполнения .NET Core](../run-time-config/index.md).</span><span class="sxs-lookup"><span data-stu-id="691e6-192">For information about other ways of configuring run-time behavior, see [.NET Core run-time configuration settings](../run-time-config/index.md).</span></span>

- [<span data-ttu-id="691e6-193">ConcurrentGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="691e6-193">ConcurrentGarbageCollection</span></span>](#concurrentgarbagecollection)
- [<span data-ttu-id="691e6-194">InvariantGlobalization</span><span class="sxs-lookup"><span data-stu-id="691e6-194">InvariantGlobalization</span></span>](#invariantglobalization)
- [<span data-ttu-id="691e6-195">RetainVMGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="691e6-195">RetainVMGarbageCollection</span></span>](#retainvmgarbagecollection)
- [<span data-ttu-id="691e6-196">ServerGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="691e6-196">ServerGarbageCollection</span></span>](#servergarbagecollection)
- [<span data-ttu-id="691e6-197">ThreadPoolMaxThreads</span><span class="sxs-lookup"><span data-stu-id="691e6-197">ThreadPoolMaxThreads</span></span>](#threadpoolmaxthreads)
- [<span data-ttu-id="691e6-198">ThreadPoolMinThreads</span><span class="sxs-lookup"><span data-stu-id="691e6-198">ThreadPoolMinThreads</span></span>](#threadpoolminthreads)
- [<span data-ttu-id="691e6-199">TieredCompilation</span><span class="sxs-lookup"><span data-stu-id="691e6-199">TieredCompilation</span></span>](#tieredcompilation)
- [<span data-ttu-id="691e6-200">TieredCompilationQuickJit</span><span class="sxs-lookup"><span data-stu-id="691e6-200">TieredCompilationQuickJit</span></span>](#tieredcompilationquickjit)
- [<span data-ttu-id="691e6-201">TieredCompilationQuickJitForLoops</span><span class="sxs-lookup"><span data-stu-id="691e6-201">TieredCompilationQuickJitForLoops</span></span>](#tieredcompilationquickjitforloops)

### <a name="concurrentgarbagecollection"></a><span data-ttu-id="691e6-202">ConcurrentGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="691e6-202">ConcurrentGarbageCollection</span></span>

<span data-ttu-id="691e6-203">Свойство `ConcurrentGarbageCollection` указывает, включена ли [фоновая (параллельная) сборка мусора](../../standard/garbage-collection/background-gc.md).</span><span class="sxs-lookup"><span data-stu-id="691e6-203">The `ConcurrentGarbageCollection` property configures whether [background (concurrent) garbage collection](../../standard/garbage-collection/background-gc.md) is enabled.</span></span> <span data-ttu-id="691e6-204">Задайте значение `false`, чтобы отключить фоновую сборку мусора.</span><span class="sxs-lookup"><span data-stu-id="691e6-204">Set the value to `false` to disable background garbage collection.</span></span> <span data-ttu-id="691e6-205">Дополнительные сведения см. в разделе [Сборка мусора в фоновом режиме](../run-time-config/garbage-collector.md#background-gc).</span><span class="sxs-lookup"><span data-stu-id="691e6-205">For more information, see [Background GC](../run-time-config/garbage-collector.md#background-gc).</span></span>

```xml
<PropertyGroup>
  <ConcurrentGarbageCollection>false</ConcurrentGarbageCollection>
</PropertyGroup>
```

### <a name="invariantglobalization"></a><span data-ttu-id="691e6-206">InvariantGlobalization</span><span class="sxs-lookup"><span data-stu-id="691e6-206">InvariantGlobalization</span></span>

<span data-ttu-id="691e6-207">Свойство `InvariantGlobalization` определяет, выполняется ли приложение в *инвариантном режиме глобализации*, что означает, что у него нет доступа к данным, относящимся к языку и региональным параметрам.</span><span class="sxs-lookup"><span data-stu-id="691e6-207">The `InvariantGlobalization` property configures whether the app runs in *globalization-invariant* mode, which means it doesn't have access to culture-specific data.</span></span> <span data-ttu-id="691e6-208">Установите значение `true` для запуска в инвариантном режиме глобализации.</span><span class="sxs-lookup"><span data-stu-id="691e6-208">Set the value to `true` to run in globalization-invariant mode.</span></span> <span data-ttu-id="691e6-209">Дополнительные сведения см. в разделе [Инвариантный режим](../run-time-config/globalization.md#invariant-mode).</span><span class="sxs-lookup"><span data-stu-id="691e6-209">For more information, see [Invariant mode](../run-time-config/globalization.md#invariant-mode).</span></span>

```xml
<PropertyGroup>
  <InvariantGlobalization>true</InvariantGlobalization>
</PropertyGroup>
```

### <a name="retainvmgarbagecollection"></a><span data-ttu-id="691e6-210">RetainVMGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="691e6-210">RetainVMGarbageCollection</span></span>

<span data-ttu-id="691e6-211">Свойство `RetainVMGarbageCollection` настраивает сборщик мусора для помещения удаленных сегментов памяти в список ожидания для будущего использования или освобождения.</span><span class="sxs-lookup"><span data-stu-id="691e6-211">The `RetainVMGarbageCollection` property configures the garbage collector to put deleted memory segments on a standby list for future use or release them.</span></span> <span data-ttu-id="691e6-212">Значение `true` указывает сборщику мусора разместить сегменты в списке ожидания.</span><span class="sxs-lookup"><span data-stu-id="691e6-212">Setting the value to `true` tells the garbage collector to put the segments on a standby list.</span></span> <span data-ttu-id="691e6-213">Дополнительные сведения см. в разделе [Сохранение виртуальной машины](../run-time-config/garbage-collector.md#retain-vm).</span><span class="sxs-lookup"><span data-stu-id="691e6-213">For more information, see [Retain VM](../run-time-config/garbage-collector.md#retain-vm).</span></span>

```xml
<PropertyGroup>
  <RetainVMGarbageCollection>true</RetainVMGarbageCollection>
</PropertyGroup>
```

### <a name="servergarbagecollection"></a><span data-ttu-id="691e6-214">ServerGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="691e6-214">ServerGarbageCollection</span></span>

<span data-ttu-id="691e6-215">Свойство `ServerGarbageCollection` указывает, использует ли приложение [сборку мусора рабочей станции или сборку мусора сервера](../../standard/garbage-collection/workstation-server-gc.md).</span><span class="sxs-lookup"><span data-stu-id="691e6-215">The `ServerGarbageCollection` property configures whether the application uses [workstation garbage collection or server garbage collection](../../standard/garbage-collection/workstation-server-gc.md).</span></span> <span data-ttu-id="691e6-216">Задайте значение `true`, чтобы использовать сборку мусора сервера.</span><span class="sxs-lookup"><span data-stu-id="691e6-216">Set the value to `true` to use server garbage collection.</span></span> <span data-ttu-id="691e6-217">Дополнительные сведения см. в разделе [Рабочая станция и сервер](../run-time-config/garbage-collector.md#workstation-vs-server).</span><span class="sxs-lookup"><span data-stu-id="691e6-217">For more information, see [Workstation vs. server](../run-time-config/garbage-collector.md#workstation-vs-server).</span></span>

```xml
<PropertyGroup>
  <ServerGarbageCollection>true</ServerGarbageCollection>
</PropertyGroup>
```

### <a name="threadpoolmaxthreads"></a><span data-ttu-id="691e6-218">ThreadPoolMaxThreads</span><span class="sxs-lookup"><span data-stu-id="691e6-218">ThreadPoolMaxThreads</span></span>

<span data-ttu-id="691e6-219">Свойство `ThreadPoolMaxThreads` указывает максимальное число потоков для пула рабочих потоков.</span><span class="sxs-lookup"><span data-stu-id="691e6-219">The `ThreadPoolMaxThreads` property configures the maximum number of threads for the worker thread pool.</span></span> <span data-ttu-id="691e6-220">Дополнительные сведения см. в разделе [Максимальное число потоков](../run-time-config/threading.md#maximum-threads).</span><span class="sxs-lookup"><span data-stu-id="691e6-220">For more information, see [Maximum threads](../run-time-config/threading.md#maximum-threads).</span></span>

```xml
<PropertyGroup>
  <ThreadPoolMaxThreads>20</ThreadPoolMaxThreads>
</PropertyGroup>
```

### <a name="threadpoolminthreads"></a><span data-ttu-id="691e6-221">ThreadPoolMinThreads</span><span class="sxs-lookup"><span data-stu-id="691e6-221">ThreadPoolMinThreads</span></span>

<span data-ttu-id="691e6-222">Свойство `ThreadPoolMinThreads` указывает минимальное число потоков для пула рабочих потоков.</span><span class="sxs-lookup"><span data-stu-id="691e6-222">The `ThreadPoolMinThreads` property configures the minimum number of threads for the worker thread pool.</span></span> <span data-ttu-id="691e6-223">Дополнительные сведения см. в разделе [Минимальное число потоков](../run-time-config/threading.md#minimum-threads).</span><span class="sxs-lookup"><span data-stu-id="691e6-223">For more information, see [Minimum threads](../run-time-config/threading.md#minimum-threads).</span></span>

```xml
<PropertyGroup>
  <ThreadPoolMinThreads>4</ThreadPoolMinThreads>
</PropertyGroup>
```

### <a name="tieredcompilation"></a><span data-ttu-id="691e6-224">TieredCompilation</span><span class="sxs-lookup"><span data-stu-id="691e6-224">TieredCompilation</span></span>

<span data-ttu-id="691e6-225">Свойство `TieredCompilation` указывает, использует ли JIT-компилятор [многоуровневую компиляцию](../whats-new/dotnet-core-3-0.md#tiered-compilation).</span><span class="sxs-lookup"><span data-stu-id="691e6-225">The `TieredCompilation` property configures whether the just-in-time (JIT) compiler uses [tiered compilation](../whats-new/dotnet-core-3-0.md#tiered-compilation).</span></span> <span data-ttu-id="691e6-226">Задайте значение `false`, чтобы отключить многоуровневую компиляцию.</span><span class="sxs-lookup"><span data-stu-id="691e6-226">Set the value to `false` to disable tiered compilation.</span></span> <span data-ttu-id="691e6-227">Дополнительные сведения см. в разделе [Многоуровневая компиляция](../run-time-config/compilation.md#tiered-compilation).</span><span class="sxs-lookup"><span data-stu-id="691e6-227">For more information, see [Tiered compilation](../run-time-config/compilation.md#tiered-compilation).</span></span>

```xml
<PropertyGroup>
  <TieredCompilation>false</TieredCompilation>
</PropertyGroup>
```

### <a name="tieredcompilationquickjit"></a><span data-ttu-id="691e6-228">TieredCompilationQuickJit</span><span class="sxs-lookup"><span data-stu-id="691e6-228">TieredCompilationQuickJit</span></span>

<span data-ttu-id="691e6-229">Свойство `TieredCompilationQuickJit` указывает, использует ли JIT-компилятор быструю JIT-компиляцию.</span><span class="sxs-lookup"><span data-stu-id="691e6-229">The `TieredCompilationQuickJit` property configures whether the JIT compiler uses quick JIT.</span></span> <span data-ttu-id="691e6-230">Задайте значение `false`, чтобы отключить быструю JIT-компиляцию.</span><span class="sxs-lookup"><span data-stu-id="691e6-230">Set the value to `false` to disable quick JIT.</span></span> <span data-ttu-id="691e6-231">Дополнительные сведения см. в разделе [Быстрая JIT-компиляция](../run-time-config/compilation.md#quick-jit).</span><span class="sxs-lookup"><span data-stu-id="691e6-231">For more information, see [Quick JIT](../run-time-config/compilation.md#quick-jit).</span></span>

```xml
<PropertyGroup>
  <TieredCompilationQuickJit>false</TieredCompilationQuickJit>
</PropertyGroup>
```

### <a name="tieredcompilationquickjitforloops"></a><span data-ttu-id="691e6-232">TieredCompilationQuickJitForLoops</span><span class="sxs-lookup"><span data-stu-id="691e6-232">TieredCompilationQuickJitForLoops</span></span>

<span data-ttu-id="691e6-233">Свойство `TieredCompilationQuickJitForLoops` указывает, использует ли JIT-компилятор быструю JIT-компиляцию для методов, содержащих циклы.</span><span class="sxs-lookup"><span data-stu-id="691e6-233">The `TieredCompilationQuickJitForLoops` property configures whether the JIT compiler uses quick JIT on methods that contain loops.</span></span> <span data-ttu-id="691e6-234">Задайте значение `true`, чтобы включить быструю JIT-компиляцию для методов, содержащих циклы.</span><span class="sxs-lookup"><span data-stu-id="691e6-234">Set the value to `true` to enable quick JIT on methods that contain loops.</span></span> <span data-ttu-id="691e6-235">Дополнительные сведения см. в разделе [Быстрая JIT-компиляция для циклов](../run-time-config/compilation.md#quick-jit-for-loops).</span><span class="sxs-lookup"><span data-stu-id="691e6-235">For more information, see [Quick JIT for loops](../run-time-config/compilation.md#quick-jit-for-loops).</span></span>

```xml
<PropertyGroup>
  <TieredCompilationQuickJitForLoops>true</TieredCompilationQuickJitForLoops>
</PropertyGroup>
```

## <a name="reference-properties-and-items"></a><span data-ttu-id="691e6-236">Справочники по свойствам и элементам</span><span class="sxs-lookup"><span data-stu-id="691e6-236">Reference properties and items</span></span>

- [<span data-ttu-id="691e6-237">AssetTargetFallback</span><span class="sxs-lookup"><span data-stu-id="691e6-237">AssetTargetFallback</span></span>](#assettargetfallback)
- [<span data-ttu-id="691e6-238">PackageReference</span><span class="sxs-lookup"><span data-stu-id="691e6-238">PackageReference</span></span>](#packagereference)
- [<span data-ttu-id="691e6-239">ProjectReference</span><span class="sxs-lookup"><span data-stu-id="691e6-239">ProjectReference</span></span>](#projectreference)
- [<span data-ttu-id="691e6-240">Ссылки</span><span class="sxs-lookup"><span data-stu-id="691e6-240">Reference</span></span>](#reference)
- [<span data-ttu-id="691e6-241">Свойства восстановления</span><span class="sxs-lookup"><span data-stu-id="691e6-241">Restore properties</span></span>](#restore-properties)

### <a name="assettargetfallback"></a><span data-ttu-id="691e6-242">AssetTargetFallback</span><span class="sxs-lookup"><span data-stu-id="691e6-242">AssetTargetFallback</span></span>

<span data-ttu-id="691e6-243">Свойство `AssetTargetFallback` позволяет указать дополнительные совместимые версии платформы для ссылок на проекты и пакетов NuGet.</span><span class="sxs-lookup"><span data-stu-id="691e6-243">The `AssetTargetFallback` property lets you specify additional compatible framework versions for project references and NuGet packages.</span></span> <span data-ttu-id="691e6-244">Например, если вы указали зависимость пакета с помощью `PackageReference`, но в этом пакете нет ресурсов, совместимых с `TargetFramework` вашего проекта, тогда пригодится свойство `AssetTargetFallback`.</span><span class="sxs-lookup"><span data-stu-id="691e6-244">For example, if you specify a package dependency using `PackageReference` but that package doesn't contain assets that are compatible with your projects's `TargetFramework`, the `AssetTargetFallback` property comes into play.</span></span> <span data-ttu-id="691e6-245">Совместимость пакета, на который указывает ссылка, повторно проверяется с помощью каждой целевой платформы, указанной в свойстве `AssetTargetFallback`.</span><span class="sxs-lookup"><span data-stu-id="691e6-245">The compatibility of the referenced package is rechecked using each target framework that's specified in `AssetTargetFallback`.</span></span>

<span data-ttu-id="691e6-246">В качестве значения свойства `AssetTargetFallback` можно задать одну [версию целевой платформы](../../standard/frameworks.md#supported-target-framework-versions) или несколько.</span><span class="sxs-lookup"><span data-stu-id="691e6-246">You can set the `AssetTargetFallback` property to one or more [target framework versions](../../standard/frameworks.md#supported-target-framework-versions).</span></span>

```xml
<PropertyGroup>
  <AssetTargetFallback>net461</AssetTargetFallback>
</PropertyGroup>
```

### <a name="packagereference"></a><span data-ttu-id="691e6-247">PackageReference</span><span class="sxs-lookup"><span data-stu-id="691e6-247">PackageReference</span></span>

<span data-ttu-id="691e6-248">Элемент `PackageReference` определяет ссылку на пакет NuGet.</span><span class="sxs-lookup"><span data-stu-id="691e6-248">The `PackageReference` item defines a reference to a NuGet package.</span></span>

<span data-ttu-id="691e6-249">Атрибут `Include` указывает идентификатор пакета.</span><span class="sxs-lookup"><span data-stu-id="691e6-249">The `Include` attribute specifies the package ID.</span></span> <span data-ttu-id="691e6-250">Атрибут `Version` указывает версию или диапазон версий.</span><span class="sxs-lookup"><span data-stu-id="691e6-250">The `Version` attribute specifies the version or version range.</span></span> <span data-ttu-id="691e6-251">Сведения о том, как указать минимальную версию, максимальную версию, диапазон или точное соответствие, см. в разделе [Диапазоны версий](/nuget/concepts/package-versioning#version-ranges).</span><span class="sxs-lookup"><span data-stu-id="691e6-251">For information about how to specify a minimum version, maximum version, range, or exact match, see [Version ranges](/nuget/concepts/package-versioning#version-ranges).</span></span> <span data-ttu-id="691e6-252">Вы также можете добавить в ссылку на проект следующие метаданные: `IncludeAssets`, `ExcludeAssets` и `PrivateAssets`.</span><span class="sxs-lookup"><span data-stu-id="691e6-252">You can also add the following metadata to a project reference: `IncludeAssets`, `ExcludeAssets`, and `PrivateAssets`.</span></span>

<span data-ttu-id="691e6-253">Фрагмент файла проекта в следующем примере ссылается на пакет [System.Runtime](https://www.nuget.org/packages/System.Runtime/).</span><span class="sxs-lookup"><span data-stu-id="691e6-253">The project file snippet in the following example references the [System.Runtime](https://www.nuget.org/packages/System.Runtime/) package.</span></span>

```xml
<ItemGroup>
  <PackageReference Include="System.Runtime" Version="4.3.0" />
</ItemGroup>
```

<span data-ttu-id="691e6-254">Дополнительные сведения см. в статье [Ссылки на пакеты в файлах проекта](/nuget/consume-packages/package-references-in-project-files).</span><span class="sxs-lookup"><span data-stu-id="691e6-254">For more information, see [Package references in project files](/nuget/consume-packages/package-references-in-project-files).</span></span>

### <a name="projectreference"></a><span data-ttu-id="691e6-255">СсылкаНаПроект</span><span class="sxs-lookup"><span data-stu-id="691e6-255">ProjectReference</span></span>

<span data-ttu-id="691e6-256">Элемент `ProjectReference` определяет ссылку на другой проект.</span><span class="sxs-lookup"><span data-stu-id="691e6-256">The `ProjectReference` item defines a reference to another project.</span></span> <span data-ttu-id="691e6-257">Проект, на который указывает ссылка, добавляется как зависимость пакета NuGet, то есть обрабатывается так же, как `PackageReference`.</span><span class="sxs-lookup"><span data-stu-id="691e6-257">The referenced project is added as a NuGet package dependency, that is, it's treated the same as a `PackageReference`.</span></span>

<span data-ttu-id="691e6-258">Атрибут `Include` задает путь к проекту.</span><span class="sxs-lookup"><span data-stu-id="691e6-258">The `Include` attribute specifies the path to the project.</span></span> <span data-ttu-id="691e6-259">Вы также можете добавить в ссылку на проект следующие метаданные: `IncludeAssets`, `ExcludeAssets` и `PrivateAssets`.</span><span class="sxs-lookup"><span data-stu-id="691e6-259">You can also add the following metadata to a project reference: `IncludeAssets`, `ExcludeAssets`, and `PrivateAssets`.</span></span>

<span data-ttu-id="691e6-260">Фрагмент файла проекта в следующем примере ссылается на проект `Project2`.</span><span class="sxs-lookup"><span data-stu-id="691e6-260">The project file snippet in the following example references a project named `Project2`.</span></span>

```xml
<ItemGroup>
  <ProjectReference Include="..\Project2.csproj" />
</ItemGroup>
```

### <a name="reference"></a><span data-ttu-id="691e6-261">Справочник</span><span class="sxs-lookup"><span data-stu-id="691e6-261">Reference</span></span>

<span data-ttu-id="691e6-262">Элемент `Reference` определяет ссылку на файл сборки.</span><span class="sxs-lookup"><span data-stu-id="691e6-262">The `Reference` item defines a reference to an assembly file.</span></span>

<span data-ttu-id="691e6-263">Атрибут `Include` задает имя файла, а метаданные `HintPath` указывают путь к этой сборке.</span><span class="sxs-lookup"><span data-stu-id="691e6-263">The `Include` attribute specifies the name of the file, and the `HintPath` metadata specifies the path to the assembly.</span></span>

```xml
<ItemGroup>
  <Reference Include="MyAssembly">
    <HintPath>..\..\Assemblies\MyAssembly.dll</HintPath>
  </Reference>
</ItemGroup>
```

### <a name="restore-properties"></a><span data-ttu-id="691e6-264">Свойства восстановления</span><span class="sxs-lookup"><span data-stu-id="691e6-264">Restore properties</span></span>

<span data-ttu-id="691e6-265">При восстановлении пакета, на который указывает ссылка, устанавливаются все его прямые зависимости и все зависимости этих зависимостей.</span><span class="sxs-lookup"><span data-stu-id="691e6-265">Restoring a referenced package installs all of its direct dependencies and all the dependencies of those dependencies.</span></span> <span data-ttu-id="691e6-266">Можно настроить восстановление пакетов, указав такие свойства, как `RestorePackagesPath` и `RestoreIgnoreFailedSources`.</span><span class="sxs-lookup"><span data-stu-id="691e6-266">You can customize package restoration by specifying properties such as `RestorePackagesPath` and `RestoreIgnoreFailedSources`.</span></span> <span data-ttu-id="691e6-267">Дополнительные сведения об этих и других свойствах см. в разделе [целевой объект восстановления](/nuget/reference/msbuild-targets#restore-target).</span><span class="sxs-lookup"><span data-stu-id="691e6-267">For more information about these and other properties, see [restore target](/nuget/reference/msbuild-targets#restore-target).</span></span>

```xml
<PropertyGroup>
  <RestoreIgnoreFailedSource>true</RestoreIgnoreFailedSource>
</PropertyGroup>
```

## <a name="see-also"></a><span data-ttu-id="691e6-268">См. также</span><span class="sxs-lookup"><span data-stu-id="691e6-268">See also</span></span>

- [<span data-ttu-id="691e6-269">Справочник по схеме MSBuild</span><span class="sxs-lookup"><span data-stu-id="691e6-269">MSBuild schema reference</span></span>](/visualstudio/msbuild/msbuild-project-file-schema-reference)
- [<span data-ttu-id="691e6-270">Общие свойства MSBuild</span><span class="sxs-lookup"><span data-stu-id="691e6-270">Common MSBuild properties</span></span>](/visualstudio/msbuild/common-msbuild-project-properties)
- [<span data-ttu-id="691e6-271">Свойства MSBuild для целевого объекта pack NuGet</span><span class="sxs-lookup"><span data-stu-id="691e6-271">MSBuild properties for NuGet pack</span></span>](/nuget/reference/msbuild-targets#pack-target)
- [<span data-ttu-id="691e6-272">Свойства MSBuild для целевого объекта restore NuGet</span><span class="sxs-lookup"><span data-stu-id="691e6-272">MSBuild properties for NuGet restore</span></span>](/nuget/reference/msbuild-targets#restore-properties)
- [<span data-ttu-id="691e6-273">Настройка сборки</span><span class="sxs-lookup"><span data-stu-id="691e6-273">Customize a build</span></span>](/visualstudio/msbuild/customize-your-build)
