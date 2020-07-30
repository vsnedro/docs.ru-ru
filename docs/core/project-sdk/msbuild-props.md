---
title: Свойства MSBuild для Microsoft.NET.Sdk
description: Справочник по свойствам и элементам MSBuild, распознаваемым пакетом SDK для .NET Core.
ms.date: 02/14/2020
ms.topic: reference
ms.openlocfilehash: 115c4f32e856dee64abe0c607b8ee595a65692e6
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164377"
---
# <a name="msbuild-reference-for-net-core-sdk-projects"></a><span data-ttu-id="68c5b-103">Справочник по MSBuild для проектов пакета SDK для .NET Core</span><span class="sxs-lookup"><span data-stu-id="68c5b-103">MSBuild reference for .NET Core SDK projects</span></span>

<span data-ttu-id="68c5b-104">Эта страница содержит справочные сведения о свойствах и элементах MSBuild, которые вы можете использовать для настройки проектов .NET Core.</span><span class="sxs-lookup"><span data-stu-id="68c5b-104">This page is a reference for the MSBuild properties and items that you can use to configure .NET Core projects.</span></span>

> [!NOTE]
> <span data-ttu-id="68c5b-105">Работа над этой страницей еще не завершена, поэтому здесь приведены лишь некоторые полезные свойства MSBuild для пакета SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="68c5b-105">This page is a work in progress and does not list all of the useful MSBuild properties for the .NET Core SDK.</span></span> <span data-ttu-id="68c5b-106">Список стандартных свойств см. в статье [Общие свойства MSBuild](/visualstudio/msbuild/common-msbuild-project-properties).</span><span class="sxs-lookup"><span data-stu-id="68c5b-106">For a list of common MSBuild properties, see [Common MSBuild properties](/visualstudio/msbuild/common-msbuild-project-properties).</span></span>

## <a name="framework-properties"></a><span data-ttu-id="68c5b-107">Свойства платформы</span><span class="sxs-lookup"><span data-stu-id="68c5b-107">Framework properties</span></span>

- [<span data-ttu-id="68c5b-108">TargetFramework</span><span class="sxs-lookup"><span data-stu-id="68c5b-108">TargetFramework</span></span>](#targetframework)
- [<span data-ttu-id="68c5b-109">TargetFrameworks</span><span class="sxs-lookup"><span data-stu-id="68c5b-109">TargetFrameworks</span></span>](#targetframeworks)
- [<span data-ttu-id="68c5b-110">NetStandardImplicitPackageVersion</span><span class="sxs-lookup"><span data-stu-id="68c5b-110">NetStandardImplicitPackageVersion</span></span>](#netstandardimplicitpackageversion)

### <a name="targetframework"></a><span data-ttu-id="68c5b-111">TargetFramework</span><span class="sxs-lookup"><span data-stu-id="68c5b-111">TargetFramework</span></span>

<span data-ttu-id="68c5b-112">Свойство `TargetFramework` определяет версию целевой платформы для приложения.</span><span class="sxs-lookup"><span data-stu-id="68c5b-112">The `TargetFramework` property specifies the target framework version for the app.</span></span> <span data-ttu-id="68c5b-113">Список допустимых моникеров целевой платформы см. в статье [Целевые платформы в проектах в стиле SDK](../../standard/frameworks.md#supported-target-framework-versions).</span><span class="sxs-lookup"><span data-stu-id="68c5b-113">For a list of valid target framework monikers, see [Target frameworks in SDK-style projects](../../standard/frameworks.md#supported-target-framework-versions).</span></span>

```xml
<PropertyGroup>
  <TargetFramework>netcoreapp3.1</TargetFramework>
</PropertyGroup>
```

<span data-ttu-id="68c5b-114">Дополнительные сведения см.в статье [Целевые платформы в проектах в стиле SDK](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="68c5b-114">For more information, see [Target frameworks in SDK-style projects](../../standard/frameworks.md).</span></span>

### <a name="targetframeworks"></a><span data-ttu-id="68c5b-115">TargetFrameworks</span><span class="sxs-lookup"><span data-stu-id="68c5b-115">TargetFrameworks</span></span>

<span data-ttu-id="68c5b-116">Используйте свойство `TargetFrameworks`, если приложение должно быть предназначено для нескольких платформ.</span><span class="sxs-lookup"><span data-stu-id="68c5b-116">Use the `TargetFrameworks` property when you want your app to target multiple platforms.</span></span> <span data-ttu-id="68c5b-117">Список допустимых моникеров целевой платформы см. в статье [Целевые платформы в проектах в стиле SDK](../../standard/frameworks.md#supported-target-framework-versions).</span><span class="sxs-lookup"><span data-stu-id="68c5b-117">For a list of valid target framework monikers, see [Target frameworks in SDK-style projects](../../standard/frameworks.md#supported-target-framework-versions).</span></span>

> [!NOTE]
> <span data-ttu-id="68c5b-118">Это свойство игнорируется, если указано свойство `TargetFramework` (в единственном числе).</span><span class="sxs-lookup"><span data-stu-id="68c5b-118">This property is ignored if `TargetFramework` (singular) is specified.</span></span>

```xml
<PropertyGroup>
  <TargetFrameworks>netcoreapp3.1;net462</TargetFrameworks>
</PropertyGroup>
```

<span data-ttu-id="68c5b-119">Дополнительные сведения см.в статье [Целевые платформы в проектах в стиле SDK](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="68c5b-119">For more information, see [Target frameworks in SDK-style projects](../../standard/frameworks.md).</span></span>

### <a name="netstandardimplicitpackageversion"></a><span data-ttu-id="68c5b-120">NetStandardImplicitPackageVersion</span><span class="sxs-lookup"><span data-stu-id="68c5b-120">NetStandardImplicitPackageVersion</span></span>

> [!NOTE]
> <span data-ttu-id="68c5b-121">Это свойство применяется только к проектам, использующим `netstandard1.x`.</span><span class="sxs-lookup"><span data-stu-id="68c5b-121">This property only applies to projects using `netstandard1.x`.</span></span> <span data-ttu-id="68c5b-122">Он не применяется к проектам, использующим `netstandard2.x`.</span><span class="sxs-lookup"><span data-stu-id="68c5b-122">It doesn't apply to projects that use `netstandard2.x`.</span></span>

<span data-ttu-id="68c5b-123">Используйте свойство `NetStandardImplicitPackageVersion`, если вам нужно указать версию платформы ниже версии метапакета.</span><span class="sxs-lookup"><span data-stu-id="68c5b-123">Use the `NetStandardImplicitPackageVersion` property when you want to specify a framework version that's lower than the metapackage version.</span></span> <span data-ttu-id="68c5b-124">Файл проекта, приведенный в следующем примере, предназначен для `netstandard1.3`, но использует `NETStandard.Library` версии 1.6.0.</span><span class="sxs-lookup"><span data-stu-id="68c5b-124">The project file in the following example targets `netstandard1.3` but uses the 1.6.0 version of `NETStandard.Library`.</span></span>

```xml
<PropertyGroup>
  <TargetFramework>netstandard1.3</TargetFramework>
  <NetStandardImplicitPackageVersion>1.6.0</NetStandardImplicitPackageVersion>
</PropertyGroup>
```

## <a name="package-properties"></a><span data-ttu-id="68c5b-125">Свойства пакета</span><span class="sxs-lookup"><span data-stu-id="68c5b-125">Package properties</span></span>

<span data-ttu-id="68c5b-126">Для описания пакета, созданного из проекта, можно указать такие свойства, как `PackageId`, `PackageVersion`, `PackageIcon`, `Title` и `Description`.</span><span class="sxs-lookup"><span data-stu-id="68c5b-126">You can specify properties such as `PackageId`, `PackageVersion`, `PackageIcon`, `Title`, and `Description` to describe the package that gets created from your project.</span></span> <span data-ttu-id="68c5b-127">Дополнительные сведения об этих и других свойствах см. в разделе [целевой объект пакета](/nuget/reference/msbuild-targets#pack-target).</span><span class="sxs-lookup"><span data-stu-id="68c5b-127">For information about these and other properties, see [pack target](/nuget/reference/msbuild-targets#pack-target).</span></span>

```xml
<PropertyGroup>
  ...
  <PackageId>ClassLibDotNetStandard</PackageId>
  <Version>1.0.0</Version>
  <Authors>John Doe</Authors>
  <Company>Contoso</Company>
</PropertyGroup>
```

## <a name="publish-properties-and-items"></a><span data-ttu-id="68c5b-128">Публикация свойств и элементов</span><span class="sxs-lookup"><span data-stu-id="68c5b-128">Publish properties and items</span></span>

- [<span data-ttu-id="68c5b-129">RuntimeIdentifier</span><span class="sxs-lookup"><span data-stu-id="68c5b-129">RuntimeIdentifier</span></span>](#runtimeidentifier)
- [<span data-ttu-id="68c5b-130">RuntimeIdentifiers</span><span class="sxs-lookup"><span data-stu-id="68c5b-130">RuntimeIdentifiers</span></span>](#runtimeidentifiers)
- [<span data-ttu-id="68c5b-131">TrimmerRootAssembly</span><span class="sxs-lookup"><span data-stu-id="68c5b-131">TrimmerRootAssembly</span></span>](#trimmerrootassembly)
- [<span data-ttu-id="68c5b-132">UseAppHost</span><span class="sxs-lookup"><span data-stu-id="68c5b-132">UseAppHost</span></span>](#useapphost)

### <a name="runtimeidentifier"></a><span data-ttu-id="68c5b-133">RuntimeIdentifier</span><span class="sxs-lookup"><span data-stu-id="68c5b-133">RuntimeIdentifier</span></span>

<span data-ttu-id="68c5b-134">Свойство `RuntimeIdentifier` позволяет указать для проекта один [идентификатор среды выполнения (RID)](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="68c5b-134">The `RuntimeIdentifier` property lets you specify a single [runtime identifier (RID)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="68c5b-135">Идентификатор среды выполнения позволяет опубликовать автономное развертывание.</span><span class="sxs-lookup"><span data-stu-id="68c5b-135">The RID enables publishing a self-contained deployment.</span></span>

```xml
<PropertyGroup>
  <RuntimeIdentifier>ubuntu.16.04-x64</RuntimeIdentifier>
</PropertyGroup>
```

### <a name="runtimeidentifiers"></a><span data-ttu-id="68c5b-136">RuntimeIdentifiers</span><span class="sxs-lookup"><span data-stu-id="68c5b-136">RuntimeIdentifiers</span></span>

<span data-ttu-id="68c5b-137">Свойство `RuntimeIdentifiers` позволяет указать для проекта список [идентификаторов среды выполнения (RID)](../rid-catalog.md) (в качестве разделителя используется точка с запятой).</span><span class="sxs-lookup"><span data-stu-id="68c5b-137">The `RuntimeIdentifiers` property lets you specify a semicolon-delimited list of [runtime identifiers (RIDs)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="68c5b-138">Используйте это свойство, если вам нужна публикация для нескольких сред.</span><span class="sxs-lookup"><span data-stu-id="68c5b-138">Use this property if you need to publish for multiple runtimes.</span></span> <span data-ttu-id="68c5b-139">`RuntimeIdentifiers` используется во время восстановления для обеспечения наличия в графе нужных ресурсов.</span><span class="sxs-lookup"><span data-stu-id="68c5b-139">`RuntimeIdentifiers` is used at restore time to ensure the right assets are in the graph.</span></span>

> [!TIP]
> <span data-ttu-id="68c5b-140">`RuntimeIdentifier` (в единственном числе) может ускорить создание сборок, когда требуется только одна среда выполнения.</span><span class="sxs-lookup"><span data-stu-id="68c5b-140">`RuntimeIdentifier` (singular) can provide faster builds when only a single runtime is required.</span></span>

```xml
<PropertyGroup>
  <RuntimeIdentifiers>win10-x64;osx.10.11-x64;ubuntu.16.04-x64</RuntimeIdentifiers>
</PropertyGroup>
```

### <a name="trimmerrootassembly"></a><span data-ttu-id="68c5b-141">TrimmerRootAssembly</span><span class="sxs-lookup"><span data-stu-id="68c5b-141">TrimmerRootAssembly</span></span>

<span data-ttu-id="68c5b-142">Элемент `TrimmerRootAssembly` позволяет исключить сборку из [*обрезки*](../deploying/trim-self-contained.md).</span><span class="sxs-lookup"><span data-stu-id="68c5b-142">The `TrimmerRootAssembly` item lets you exclude an assembly from [*trimming*](../deploying/trim-self-contained.md).</span></span> <span data-ttu-id="68c5b-143">Обрезка — это процесс удаления неиспользуемых частей среды выполнения из упакованного приложения.</span><span class="sxs-lookup"><span data-stu-id="68c5b-143">Trimming is the process of removing unused parts of the runtime from a packaged application.</span></span> <span data-ttu-id="68c5b-144">В некоторых случаях при обрезке могут неправильно удаляться необходимые ссылки.</span><span class="sxs-lookup"><span data-stu-id="68c5b-144">In some cases, trimming might incorrectly remove required references.</span></span>

<span data-ttu-id="68c5b-145">Следующий код XML исключает сборку `System.Security` из обрезки.</span><span class="sxs-lookup"><span data-stu-id="68c5b-145">The following XML excludes the `System.Security` assembly from trimming.</span></span>

```xml
<ItemGroup>
  <TrimmerRootAssembly Include="System.Security" />
</ItemGroup>
```

### <a name="useapphost"></a><span data-ttu-id="68c5b-146">UseAppHost</span><span class="sxs-lookup"><span data-stu-id="68c5b-146">UseAppHost</span></span>

<span data-ttu-id="68c5b-147">Свойство `UseAppHost` было представлено в пакете SDK для .NET Core.версии 2.1.400.</span><span class="sxs-lookup"><span data-stu-id="68c5b-147">The `UseAppHost` property was introduced in the 2.1.400 version of the .NET Core SDK.</span></span> <span data-ttu-id="68c5b-148">Оно контролирует создание собственного исполняемого файла для развертывания.</span><span class="sxs-lookup"><span data-stu-id="68c5b-148">It controls whether or not a native executable is created for a deployment.</span></span> <span data-ttu-id="68c5b-149">Этот файл требуется для автономных развертываний.</span><span class="sxs-lookup"><span data-stu-id="68c5b-149">A native executable is required for self-contained deployments.</span></span>

<span data-ttu-id="68c5b-150">В .NET Core 3.0 и более поздних версиях зависимый от платформы исполняемый файл создается по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="68c5b-150">In .NET Core 3.0 and later versions, a framework-dependent executable is created by default.</span></span> <span data-ttu-id="68c5b-151">Задайте свойству `UseAppHost` значение `false`, чтобы отключить создание исполняемого файла.</span><span class="sxs-lookup"><span data-stu-id="68c5b-151">Set the `UseAppHost` property to `false` to disable generation of the executable.</span></span>

```xml
<PropertyGroup>
  <UseAppHost>false</UseAppHost>
</PropertyGroup>
```

<span data-ttu-id="68c5b-152">Дополнительные сведения о развертывании см. в статье [Развертывание приложений .NET Core](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="68c5b-152">For more information about deployment, see [.NET Core application deployment](../deploying/index.md).</span></span>

## <a name="compile-properties"></a><span data-ttu-id="68c5b-153">Свойства компиляции</span><span class="sxs-lookup"><span data-stu-id="68c5b-153">Compile properties</span></span>

- [<span data-ttu-id="68c5b-154">EmbeddedResourceUseDependentUponConvention</span><span class="sxs-lookup"><span data-stu-id="68c5b-154">EmbeddedResourceUseDependentUponConvention</span></span>](#embeddedresourceusedependentuponconvention)
- [<span data-ttu-id="68c5b-155">LangVersion</span><span class="sxs-lookup"><span data-stu-id="68c5b-155">LangVersion</span></span>](#langversion)

### <a name="embeddedresourceusedependentuponconvention"></a><span data-ttu-id="68c5b-156">EmbeddedResourceUseDependentUponConvention</span><span class="sxs-lookup"><span data-stu-id="68c5b-156">EmbeddedResourceUseDependentUponConvention</span></span>

<span data-ttu-id="68c5b-157">Свойство `EmbeddedResourceUseDependentUponConvention` определяет, будет ли использоваться информация о типах в исходных файлах, расположенных в одной папке с файлами ресурсов, для создания имен файлов манифеста этих ресурсов.</span><span class="sxs-lookup"><span data-stu-id="68c5b-157">The `EmbeddedResourceUseDependentUponConvention` property defines whether resource manifest file names are generated from type information in source files that are colocated with resource files.</span></span> <span data-ttu-id="68c5b-158">Например, если *Form1.resx* находится в той же папке, что и *Form1.cs*, а `EmbeddedResourceUseDependentUponConvention` имеет значение `true`, то созданному файл *.resources* присваивается имя на основе имени первого типа, определенного в файле *Form1.cs*.</span><span class="sxs-lookup"><span data-stu-id="68c5b-158">For example, if *Form1.resx* is in the same folder as *Form1.cs*, and `EmbeddedResourceUseDependentUponConvention` is set to `true`, the generated *.resources* file takes its name from the first type that's defined in *Form1.cs*.</span></span> <span data-ttu-id="68c5b-159">Например, если первым типом в файле *Form1.cs* является `MyNamespace.Form1`, созданному файлу присваивается имя *MyNamespace.Form1.resources*.</span><span class="sxs-lookup"><span data-stu-id="68c5b-159">For example, if `MyNamespace.Form1` is the first type defined in *Form1.cs*, the generated file name is *MyNamespace.Form1.resources*.</span></span>

> [!NOTE]
> <span data-ttu-id="68c5b-160">Если для `EmbeddedResource` элемента заданы метаданные `LogicalName`, `ManifestResourceName` или `DependentUpon`, то имя файла манифеста для этого файла ресурсов будет создаваться на основе таких метаданных.</span><span class="sxs-lookup"><span data-stu-id="68c5b-160">If `LogicalName`, `ManifestResourceName`, or `DependentUpon` metadata is specified for an `EmbeddedResource` item, the generated manifest file name for that resource file is based on that metadata instead.</span></span>

<span data-ttu-id="68c5b-161">По умолчанию для нового проекта .NET Core этому свойству задается значение `true`.</span><span class="sxs-lookup"><span data-stu-id="68c5b-161">By default, in a new .NET Core project, this property is set to `true`.</span></span> <span data-ttu-id="68c5b-162">Если задано значение `false` и для элемента `EmbeddedResource` в файле проекта не указаны метаданные `LogicalName`, `ManifestResourceName` или `DependentUpon`, то имя файла манифеста для этого ресурса будет основано на имени корневого пространства имен проекта и относительном пути к файлу *.resx*.</span><span class="sxs-lookup"><span data-stu-id="68c5b-162">If set to `false`, and no `LogicalName`, `ManifestResourceName`, or `DependentUpon` metadata is specified for the `EmbeddedResource` item in the project file, the resource manifest file name is based off the root namespace for the project and the relative file path to the *.resx* file.</span></span> <span data-ttu-id="68c5b-163">Дополнительные сведения об определение имени файла манифеста см. [здесь](../resources/manifest-file-names.md).</span><span class="sxs-lookup"><span data-stu-id="68c5b-163">For more information, see [How resource manifest files are named](../resources/manifest-file-names.md).</span></span>

```xml
<PropertyGroup>
  <EmbeddedResourceUseDependentUponConvention>true</EmbeddedResourceUseDependentUponConvention>
</PropertyGroup>
```

### <a name="langversion"></a><span data-ttu-id="68c5b-164">LangVersion</span><span class="sxs-lookup"><span data-stu-id="68c5b-164">LangVersion</span></span>

<span data-ttu-id="68c5b-165">Свойство `LangVersion` позволяет указать конкретную версию языка программирования.</span><span class="sxs-lookup"><span data-stu-id="68c5b-165">The `LangVersion` property lets you specify a specific programming language version.</span></span> <span data-ttu-id="68c5b-166">Например, если требуется доступ к предварительным версиям функций C#, задайте параметру `LangVersion` значение `preview`.</span><span class="sxs-lookup"><span data-stu-id="68c5b-166">For example, if you want access to C# preview features, set `LangVersion` to `preview`.</span></span>

```xml
<PropertyGroup>
  <LangVersion>preview</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="68c5b-167">Дополнительные сведения см. в статье [Управление версиями языка C#](../../csharp/language-reference/configure-language-version.md#override-a-default).</span><span class="sxs-lookup"><span data-stu-id="68c5b-167">For more information, see [C# language versioning](../../csharp/language-reference/configure-language-version.md#override-a-default).</span></span>

## <a name="run-time-configuration-properties"></a><span data-ttu-id="68c5b-168">Свойства конфигурации среды выполнения</span><span class="sxs-lookup"><span data-stu-id="68c5b-168">Run-time configuration properties</span></span>

<span data-ttu-id="68c5b-169">Вы можете настроить некоторые варианты поведения среды выполнения, указав свойства MSBuild в файле проекта приложения.</span><span class="sxs-lookup"><span data-stu-id="68c5b-169">You can configure some run-time behaviors by specifying MSBuild properties in the project file of the app.</span></span> <span data-ttu-id="68c5b-170">Сведения о других способах настройки поведения среды выполнения см. в разделе [Параметры конфигурации среды выполнения .NET Core](../run-time-config/index.md).</span><span class="sxs-lookup"><span data-stu-id="68c5b-170">For information about other ways of configuring run-time behavior, see [.NET Core run-time configuration settings](../run-time-config/index.md).</span></span>

- [<span data-ttu-id="68c5b-171">ConcurrentGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="68c5b-171">ConcurrentGarbageCollection</span></span>](#concurrentgarbagecollection)
- [<span data-ttu-id="68c5b-172">InvariantGlobalization</span><span class="sxs-lookup"><span data-stu-id="68c5b-172">InvariantGlobalization</span></span>](#invariantglobalization)
- [<span data-ttu-id="68c5b-173">RetainVMGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="68c5b-173">RetainVMGarbageCollection</span></span>](#retainvmgarbagecollection)
- [<span data-ttu-id="68c5b-174">ServerGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="68c5b-174">ServerGarbageCollection</span></span>](#servergarbagecollection)
- [<span data-ttu-id="68c5b-175">ThreadPoolMaxThreads</span><span class="sxs-lookup"><span data-stu-id="68c5b-175">ThreadPoolMaxThreads</span></span>](#threadpoolmaxthreads)
- [<span data-ttu-id="68c5b-176">ThreadPoolMinThreads</span><span class="sxs-lookup"><span data-stu-id="68c5b-176">ThreadPoolMinThreads</span></span>](#threadpoolminthreads)
- [<span data-ttu-id="68c5b-177">TieredCompilation</span><span class="sxs-lookup"><span data-stu-id="68c5b-177">TieredCompilation</span></span>](#tieredcompilation)
- [<span data-ttu-id="68c5b-178">TieredCompilationQuickJit</span><span class="sxs-lookup"><span data-stu-id="68c5b-178">TieredCompilationQuickJit</span></span>](#tieredcompilationquickjit)
- [<span data-ttu-id="68c5b-179">TieredCompilationQuickJitForLoops</span><span class="sxs-lookup"><span data-stu-id="68c5b-179">TieredCompilationQuickJitForLoops</span></span>](#tieredcompilationquickjitforloops)

### <a name="concurrentgarbagecollection"></a><span data-ttu-id="68c5b-180">ConcurrentGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="68c5b-180">ConcurrentGarbageCollection</span></span>

<span data-ttu-id="68c5b-181">Свойство `ConcurrentGarbageCollection` указывает, включена ли [фоновая (параллельная) сборка мусора](../../standard/garbage-collection/background-gc.md).</span><span class="sxs-lookup"><span data-stu-id="68c5b-181">The `ConcurrentGarbageCollection` property configures whether [background (concurrent) garbage collection](../../standard/garbage-collection/background-gc.md) is enabled.</span></span> <span data-ttu-id="68c5b-182">Задайте значение `false`, чтобы отключить фоновую сборку мусора.</span><span class="sxs-lookup"><span data-stu-id="68c5b-182">Set the value to `false` to disable background garbage collection.</span></span> <span data-ttu-id="68c5b-183">Дополнительные сведения см. в разделе [System.GC.Concurrent/COMPlus_gcConcurrent](../run-time-config/garbage-collector.md#systemgcconcurrentcomplus_gcconcurrent).</span><span class="sxs-lookup"><span data-stu-id="68c5b-183">For more information, see [System.GC.Concurrent/COMPlus_gcConcurrent](../run-time-config/garbage-collector.md#systemgcconcurrentcomplus_gcconcurrent).</span></span>

```xml
<PropertyGroup>
  <ConcurrentGarbageCollection>false</ConcurrentGarbageCollection>
</PropertyGroup>
```

### <a name="invariantglobalization"></a><span data-ttu-id="68c5b-184">InvariantGlobalization</span><span class="sxs-lookup"><span data-stu-id="68c5b-184">InvariantGlobalization</span></span>

<span data-ttu-id="68c5b-185">Свойство `InvariantGlobalization` определяет, выполняется ли приложение в *инвариантном режиме глобализации*, что означает, что у него нет доступа к данным, относящимся к языку и региональным параметрам.</span><span class="sxs-lookup"><span data-stu-id="68c5b-185">The `InvariantGlobalization` property configures whether the app runs in *globalization-invariant* mode, which means it doesn't have access to culture-specific data.</span></span> <span data-ttu-id="68c5b-186">Установите значение `true` для запуска в инвариантном режиме глобализации.</span><span class="sxs-lookup"><span data-stu-id="68c5b-186">Set the value to `true` to run in globalization-invariant mode.</span></span> <span data-ttu-id="68c5b-187">Дополнительные сведения см. в разделе [Инвариантный режим](../run-time-config/globalization.md#invariant-mode).</span><span class="sxs-lookup"><span data-stu-id="68c5b-187">For more information, see [Invariant mode](../run-time-config/globalization.md#invariant-mode).</span></span>

```xml
<PropertyGroup>
  <InvariantGlobalization>true</InvariantGlobalization>
</PropertyGroup>
```

### <a name="retainvmgarbagecollection"></a><span data-ttu-id="68c5b-188">RetainVMGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="68c5b-188">RetainVMGarbageCollection</span></span>

<span data-ttu-id="68c5b-189">Свойство `RetainVMGarbageCollection` настраивает сборщик мусора для помещения удаленных сегментов памяти в список ожидания для будущего использования или освобождения.</span><span class="sxs-lookup"><span data-stu-id="68c5b-189">The `RetainVMGarbageCollection` property configures the garbage collector to put deleted memory segments on a standby list for future use or release them.</span></span> <span data-ttu-id="68c5b-190">Значение `true` указывает сборщику мусора разместить сегменты в списке ожидания.</span><span class="sxs-lookup"><span data-stu-id="68c5b-190">Setting the value to `true` tells the garbage collector to put the segments on a standby list.</span></span> <span data-ttu-id="68c5b-191">Дополнительные сведения см. в разделе [System.GC.RetainVM/COMPlus_GCRetainVM](../run-time-config/garbage-collector.md#systemgcretainvmcomplus_gcretainvm).</span><span class="sxs-lookup"><span data-stu-id="68c5b-191">For more information, see [System.GC.RetainVM/COMPlus_GCRetainVM](../run-time-config/garbage-collector.md#systemgcretainvmcomplus_gcretainvm).</span></span>

```xml
<PropertyGroup>
  <RetainVMGarbageCollection>true</RetainVMGarbageCollection>
</PropertyGroup>
```

### <a name="servergarbagecollection"></a><span data-ttu-id="68c5b-192">ServerGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="68c5b-192">ServerGarbageCollection</span></span>

<span data-ttu-id="68c5b-193">Свойство `ServerGarbageCollection` указывает, использует ли приложение [сборку мусора рабочей станции или сборку мусора сервера](../../standard/garbage-collection/workstation-server-gc.md).</span><span class="sxs-lookup"><span data-stu-id="68c5b-193">The `ServerGarbageCollection` property configures whether the application uses [workstation garbage collection or server garbage collection](../../standard/garbage-collection/workstation-server-gc.md).</span></span> <span data-ttu-id="68c5b-194">Задайте значение `true`, чтобы использовать сборку мусора сервера.</span><span class="sxs-lookup"><span data-stu-id="68c5b-194">Set the value to `true` to use server garbage collection.</span></span> <span data-ttu-id="68c5b-195">Дополнительные сведения см. в разделе [System.GC.Server/COMPlus_gcServer](../run-time-config/garbage-collector.md#systemgcservercomplus_gcserver).</span><span class="sxs-lookup"><span data-stu-id="68c5b-195">For more information, see [System.GC.Server/COMPlus_gcServer](../run-time-config/garbage-collector.md#systemgcservercomplus_gcserver).</span></span>

```xml
<PropertyGroup>
  <ServerGarbageCollection>true</ServerGarbageCollection>
</PropertyGroup>
```

### <a name="threadpoolmaxthreads"></a><span data-ttu-id="68c5b-196">ThreadPoolMaxThreads</span><span class="sxs-lookup"><span data-stu-id="68c5b-196">ThreadPoolMaxThreads</span></span>

<span data-ttu-id="68c5b-197">Свойство `ThreadPoolMaxThreads` указывает максимальное число потоков для пула рабочих потоков.</span><span class="sxs-lookup"><span data-stu-id="68c5b-197">The `ThreadPoolMaxThreads` property configures the maximum number of threads for the worker thread pool.</span></span> <span data-ttu-id="68c5b-198">Дополнительные сведения см. в разделе [Максимальное число потоков](../run-time-config/threading.md#maximum-threads).</span><span class="sxs-lookup"><span data-stu-id="68c5b-198">For more information, see [Maximum threads](../run-time-config/threading.md#maximum-threads).</span></span>

```xml
<PropertyGroup>
  <ThreadPoolMaxThreads>20</ThreadPoolMaxThreads>
</PropertyGroup>
```

### <a name="threadpoolminthreads"></a><span data-ttu-id="68c5b-199">ThreadPoolMinThreads</span><span class="sxs-lookup"><span data-stu-id="68c5b-199">ThreadPoolMinThreads</span></span>

<span data-ttu-id="68c5b-200">Свойство `ThreadPoolMinThreads` указывает минимальное число потоков для пула рабочих потоков.</span><span class="sxs-lookup"><span data-stu-id="68c5b-200">The `ThreadPoolMinThreads` property configures the minimum number of threads for the worker thread pool.</span></span> <span data-ttu-id="68c5b-201">Дополнительные сведения см. в разделе [Минимальное число потоков](../run-time-config/threading.md#minimum-threads).</span><span class="sxs-lookup"><span data-stu-id="68c5b-201">For more information, see [Minimum threads](../run-time-config/threading.md#minimum-threads).</span></span>

```xml
<PropertyGroup>
  <ThreadPoolMinThreads>4</ThreadPoolMinThreads>
</PropertyGroup>
```

### <a name="tieredcompilation"></a><span data-ttu-id="68c5b-202">TieredCompilation</span><span class="sxs-lookup"><span data-stu-id="68c5b-202">TieredCompilation</span></span>

<span data-ttu-id="68c5b-203">Свойство `TieredCompilation` указывает, использует ли JIT-компилятор [многоуровневую компиляцию](../whats-new/dotnet-core-3-0.md#tiered-compilation).</span><span class="sxs-lookup"><span data-stu-id="68c5b-203">The `TieredCompilation` property configures whether the just-in-time (JIT) compiler uses [tiered compilation](../whats-new/dotnet-core-3-0.md#tiered-compilation).</span></span> <span data-ttu-id="68c5b-204">Задайте значение `false`, чтобы отключить многоуровневую компиляцию.</span><span class="sxs-lookup"><span data-stu-id="68c5b-204">Set the value to `false` to disable tiered compilation.</span></span> <span data-ttu-id="68c5b-205">Дополнительные сведения см. в разделе [Многоуровневая компиляция](../run-time-config/compilation.md#tiered-compilation).</span><span class="sxs-lookup"><span data-stu-id="68c5b-205">For more information, see [Tiered compilation](../run-time-config/compilation.md#tiered-compilation).</span></span>

```xml
<PropertyGroup>
  <TieredCompilation>false</TieredCompilation>
</PropertyGroup>
```

### <a name="tieredcompilationquickjit"></a><span data-ttu-id="68c5b-206">TieredCompilationQuickJit</span><span class="sxs-lookup"><span data-stu-id="68c5b-206">TieredCompilationQuickJit</span></span>

<span data-ttu-id="68c5b-207">Свойство `TieredCompilationQuickJit` указывает, использует ли JIT-компилятор быструю JIT-компиляцию.</span><span class="sxs-lookup"><span data-stu-id="68c5b-207">The `TieredCompilationQuickJit` property configures whether the JIT compiler uses quick JIT.</span></span> <span data-ttu-id="68c5b-208">Задайте значение `false`, чтобы отключить быструю JIT-компиляцию.</span><span class="sxs-lookup"><span data-stu-id="68c5b-208">Set the value to `false` to disable quick JIT.</span></span> <span data-ttu-id="68c5b-209">Дополнительные сведения см. в разделе [Быстрая JIT-компиляция](../run-time-config/compilation.md#quick-jit).</span><span class="sxs-lookup"><span data-stu-id="68c5b-209">For more information, see [Quick JIT](../run-time-config/compilation.md#quick-jit).</span></span>

```xml
<PropertyGroup>
  <TieredCompilationQuickJit>false</TieredCompilationQuickJit>
</PropertyGroup>
```

### <a name="tieredcompilationquickjitforloops"></a><span data-ttu-id="68c5b-210">TieredCompilationQuickJitForLoops</span><span class="sxs-lookup"><span data-stu-id="68c5b-210">TieredCompilationQuickJitForLoops</span></span>

<span data-ttu-id="68c5b-211">Свойство `TieredCompilationQuickJitForLoops` указывает, использует ли JIT-компилятор быструю JIT-компиляцию для методов, содержащих циклы.</span><span class="sxs-lookup"><span data-stu-id="68c5b-211">The `TieredCompilationQuickJitForLoops` property configures whether the JIT compiler uses quick JIT on methods that contain loops.</span></span> <span data-ttu-id="68c5b-212">Задайте значение `true`, чтобы включить быструю JIT-компиляцию для методов, содержащих циклы.</span><span class="sxs-lookup"><span data-stu-id="68c5b-212">Set the value to `true` to enable quick JIT on methods that contain loops.</span></span> <span data-ttu-id="68c5b-213">Дополнительные сведения см. в разделе [Быстрая JIT-компиляция для циклов](../run-time-config/compilation.md#quick-jit-for-loops).</span><span class="sxs-lookup"><span data-stu-id="68c5b-213">For more information, see [Quick JIT for loops](../run-time-config/compilation.md#quick-jit-for-loops).</span></span>

```xml
<PropertyGroup>
  <TieredCompilationQuickJitForLoops>true</TieredCompilationQuickJitForLoops>
</PropertyGroup>
```

## <a name="reference-properties-and-items"></a><span data-ttu-id="68c5b-214">Справочники по свойствам и элементам</span><span class="sxs-lookup"><span data-stu-id="68c5b-214">Reference properties and items</span></span>

- [<span data-ttu-id="68c5b-215">AssetTargetFallback</span><span class="sxs-lookup"><span data-stu-id="68c5b-215">AssetTargetFallback</span></span>](#assettargetfallback)
- [<span data-ttu-id="68c5b-216">PackageReference</span><span class="sxs-lookup"><span data-stu-id="68c5b-216">PackageReference</span></span>](#packagereference)
- [<span data-ttu-id="68c5b-217">ProjectReference</span><span class="sxs-lookup"><span data-stu-id="68c5b-217">ProjectReference</span></span>](#projectreference)
- [<span data-ttu-id="68c5b-218">Ссылки</span><span class="sxs-lookup"><span data-stu-id="68c5b-218">Reference</span></span>](#reference)
- [<span data-ttu-id="68c5b-219">Свойства восстановления</span><span class="sxs-lookup"><span data-stu-id="68c5b-219">Restore properties</span></span>](#restore-properties)

### <a name="assettargetfallback"></a><span data-ttu-id="68c5b-220">AssetTargetFallback</span><span class="sxs-lookup"><span data-stu-id="68c5b-220">AssetTargetFallback</span></span>

<span data-ttu-id="68c5b-221">Свойство `AssetTargetFallback` позволяет указать дополнительные совместимые версии платформы для ссылок на проекты и пакетов NuGet.</span><span class="sxs-lookup"><span data-stu-id="68c5b-221">The `AssetTargetFallback` property lets you specify additional compatible framework versions for project references and NuGet packages.</span></span> <span data-ttu-id="68c5b-222">Например, если вы указали зависимость пакета с помощью `PackageReference`, но в этом пакете нет ресурсов, совместимых с `TargetFramework` вашего проекта, тогда пригодится свойство `AssetTargetFallback`.</span><span class="sxs-lookup"><span data-stu-id="68c5b-222">For example, if you specify a package dependency using `PackageReference` but that package doesn't contain assets that are compatible with your projects's `TargetFramework`, the `AssetTargetFallback` property comes into play.</span></span> <span data-ttu-id="68c5b-223">Совместимость пакета, на который указывает ссылка, повторно проверяется с помощью каждой целевой платформы, указанной в свойстве `AssetTargetFallback`.</span><span class="sxs-lookup"><span data-stu-id="68c5b-223">The compatibility of the referenced package is rechecked using each target framework that's specified in `AssetTargetFallback`.</span></span>

<span data-ttu-id="68c5b-224">В качестве значения свойства `AssetTargetFallback` можно задать одну [версию целевой платформы](../../standard/frameworks.md#supported-target-framework-versions) или несколько.</span><span class="sxs-lookup"><span data-stu-id="68c5b-224">You can set the `AssetTargetFallback` property to one or more [target framework versions](../../standard/frameworks.md#supported-target-framework-versions).</span></span>

```xml
<PropertyGroup>
  <AssetTargetFallback>net461</AssetTargetFallback>
</PropertyGroup>
```

### <a name="packagereference"></a><span data-ttu-id="68c5b-225">PackageReference</span><span class="sxs-lookup"><span data-stu-id="68c5b-225">PackageReference</span></span>

<span data-ttu-id="68c5b-226">Элемент `PackageReference` определяет ссылку на пакет NuGet.</span><span class="sxs-lookup"><span data-stu-id="68c5b-226">The `PackageReference` item defines a reference to a NuGet package.</span></span>

<span data-ttu-id="68c5b-227">Атрибут `Include` указывает идентификатор пакета.</span><span class="sxs-lookup"><span data-stu-id="68c5b-227">The `Include` attribute specifies the package ID.</span></span> <span data-ttu-id="68c5b-228">Атрибут `Version` указывает версию или диапазон версий.</span><span class="sxs-lookup"><span data-stu-id="68c5b-228">The `Version` attribute specifies the version or version range.</span></span> <span data-ttu-id="68c5b-229">Сведения о том, как указать минимальную версию, максимальную версию, диапазон или точное соответствие, см. в разделе [Диапазоны версий](/nuget/concepts/package-versioning#version-ranges).</span><span class="sxs-lookup"><span data-stu-id="68c5b-229">For information about how to specify a minimum version, maximum version, range, or exact match, see [Version ranges](/nuget/concepts/package-versioning#version-ranges).</span></span> <span data-ttu-id="68c5b-230">Вы также можете добавить в ссылку на проект следующие метаданные: `IncludeAssets`, `ExcludeAssets` и `PrivateAssets`.</span><span class="sxs-lookup"><span data-stu-id="68c5b-230">You can also add the following metadata to a project reference: `IncludeAssets`, `ExcludeAssets`, and `PrivateAssets`.</span></span>

<span data-ttu-id="68c5b-231">Фрагмент файла проекта в следующем примере ссылается на пакет [System.Runtime](https://www.nuget.org/packages/System.Runtime/).</span><span class="sxs-lookup"><span data-stu-id="68c5b-231">The project file snippet in the following example references the [System.Runtime](https://www.nuget.org/packages/System.Runtime/) package.</span></span>

```xml
<ItemGroup>
  <PackageReference Include="System.Runtime" Version="4.3.0" />
</ItemGroup>
```

<span data-ttu-id="68c5b-232">Дополнительные сведения см. в статье [Ссылки на пакеты в файлах проекта](/nuget/consume-packages/package-references-in-project-files).</span><span class="sxs-lookup"><span data-stu-id="68c5b-232">For more information, see [Package references in project files](/nuget/consume-packages/package-references-in-project-files).</span></span>

### <a name="projectreference"></a><span data-ttu-id="68c5b-233">СсылкаНаПроект</span><span class="sxs-lookup"><span data-stu-id="68c5b-233">ProjectReference</span></span>

<span data-ttu-id="68c5b-234">Элемент `ProjectReference` определяет ссылку на другой проект.</span><span class="sxs-lookup"><span data-stu-id="68c5b-234">The `ProjectReference` item defines a reference to another project.</span></span> <span data-ttu-id="68c5b-235">Проект, на который указывает ссылка, добавляется как зависимость пакета NuGet, то есть обрабатывается так же, как `PackageReference`.</span><span class="sxs-lookup"><span data-stu-id="68c5b-235">The referenced project is added as a NuGet package dependency, that is, it's treated the same as a `PackageReference`.</span></span>

<span data-ttu-id="68c5b-236">Атрибут `Include` задает путь к проекту.</span><span class="sxs-lookup"><span data-stu-id="68c5b-236">The `Include` attribute specifies the path to the project.</span></span> <span data-ttu-id="68c5b-237">Вы также можете добавить в ссылку на проект следующие метаданные: `IncludeAssets`, `ExcludeAssets` и `PrivateAssets`.</span><span class="sxs-lookup"><span data-stu-id="68c5b-237">You can also add the following metadata to a project reference: `IncludeAssets`, `ExcludeAssets`, and `PrivateAssets`.</span></span>

<span data-ttu-id="68c5b-238">Фрагмент файла проекта в следующем примере ссылается на проект `Project2`.</span><span class="sxs-lookup"><span data-stu-id="68c5b-238">The project file snippet in the following example references a project named `Project2`.</span></span>

```xml
<ItemGroup>
  <ProjectReference Include="..\Project2.csproj" />
</ItemGroup>
```

### <a name="reference"></a><span data-ttu-id="68c5b-239">Справочник</span><span class="sxs-lookup"><span data-stu-id="68c5b-239">Reference</span></span>

<span data-ttu-id="68c5b-240">Элемент `Reference` определяет ссылку на файл сборки.</span><span class="sxs-lookup"><span data-stu-id="68c5b-240">The `Reference` item defines a reference to an assembly file.</span></span>

<span data-ttu-id="68c5b-241">Атрибут `Include` задает имя файла, а метаданные `HintPath` указывают путь к этой сборке.</span><span class="sxs-lookup"><span data-stu-id="68c5b-241">The `Include` attribute specifies the name of the file, and the `HintPath` metadata specifies the path to the assembly.</span></span>

```xml
<ItemGroup>
  <Reference Include="MyAssembly">
    <HintPath>..\..\Assemblies\MyAssembly.dll</HintPath>
  </Reference>
</ItemGroup>
```

### <a name="restore-properties"></a><span data-ttu-id="68c5b-242">Свойства восстановления</span><span class="sxs-lookup"><span data-stu-id="68c5b-242">Restore properties</span></span>

<span data-ttu-id="68c5b-243">При восстановлении пакета, на который указывает ссылка, устанавливаются все его прямые зависимости и все зависимости этих зависимостей.</span><span class="sxs-lookup"><span data-stu-id="68c5b-243">Restoring a referenced package installs all of its direct dependencies and all the dependencies of those dependencies.</span></span> <span data-ttu-id="68c5b-244">Можно настроить восстановление пакетов, указав такие свойства, как `RestorePackagesPath` и `RestoreIgnoreFailedSources`.</span><span class="sxs-lookup"><span data-stu-id="68c5b-244">You can customize package restoration by specifying properties such as `RestorePackagesPath` and `RestoreIgnoreFailedSources`.</span></span> <span data-ttu-id="68c5b-245">Дополнительные сведения об этих и других свойствах см. в разделе [целевой объект восстановления](/nuget/reference/msbuild-targets#restore-target).</span><span class="sxs-lookup"><span data-stu-id="68c5b-245">For more information about these and other properties, see [restore target](/nuget/reference/msbuild-targets#restore-target).</span></span>

```xml
<PropertyGroup>
  <RestoreIgnoreFailedSource>true</RestoreIgnoreFailedSource>
</PropertyGroup>
```

## <a name="see-also"></a><span data-ttu-id="68c5b-246">См. также</span><span class="sxs-lookup"><span data-stu-id="68c5b-246">See also</span></span>

- [<span data-ttu-id="68c5b-247">Справочник по схеме MSBuild</span><span class="sxs-lookup"><span data-stu-id="68c5b-247">MSBuild schema reference</span></span>](/visualstudio/msbuild/msbuild-project-file-schema-reference)
- [<span data-ttu-id="68c5b-248">Общие свойства MSBuild</span><span class="sxs-lookup"><span data-stu-id="68c5b-248">Common MSBuild properties</span></span>](/visualstudio/msbuild/common-msbuild-project-properties)
- [<span data-ttu-id="68c5b-249">Свойства MSBuild для целевого объекта pack NuGet</span><span class="sxs-lookup"><span data-stu-id="68c5b-249">MSBuild properties for NuGet pack</span></span>](/nuget/reference/msbuild-targets#pack-target)
- [<span data-ttu-id="68c5b-250">Свойства MSBuild для целевого объекта restore NuGet</span><span class="sxs-lookup"><span data-stu-id="68c5b-250">MSBuild properties for NuGet restore</span></span>](/nuget/reference/msbuild-targets#restore-properties)
- [<span data-ttu-id="68c5b-251">Настройка сборки</span><span class="sxs-lookup"><span data-stu-id="68c5b-251">Customize a build</span></span>](/visualstudio/msbuild/customize-your-build)
