---
title: Свойства MSBuild для Microsoft.NET.Sdk
description: Справочник по свойствам MSBuild, распознаваемым пакетом SDK для .NET Core.
ms.date: 02/14/2020
ms.topic: reference
ms.openlocfilehash: 800ff59310d8437d7f770bf20a5bdf37714f8515
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795577"
---
# <a name="msbuild-properties-for-net-core-sdk-projects"></a><span data-ttu-id="a5ad6-103">Свойства MSBuild для проектов пакета SDK для .NET Core</span><span class="sxs-lookup"><span data-stu-id="a5ad6-103">MSBuild properties for .NET Core SDK projects</span></span>

<span data-ttu-id="a5ad6-104">На этой странице описываются свойства MSBuild для настройки проектов .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a5ad6-104">This page describes MSBuild properties for configuring .NET Core projects.</span></span> <span data-ttu-id="a5ad6-105">Можно указать *метаданные* для каждого свойства в качестве дочерних элементов свойства.</span><span class="sxs-lookup"><span data-stu-id="a5ad6-105">You can specify *metadata* for each property as child elements of the property.</span></span>

> [!NOTE]
> <span data-ttu-id="a5ad6-106">Работа над этой страницей еще не завершена, поэтому здесь приведены лишь некоторые полезные свойства MSBuild для пакета SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a5ad6-106">This page is a work in progress and does not list all of the useful MSBuild properties for the .NET Core SDK.</span></span> <span data-ttu-id="a5ad6-107">Список стандартных свойств см. в статье [Общие свойства MSBuild](/visualstudio/msbuild/common-msbuild-project-properties).</span><span class="sxs-lookup"><span data-stu-id="a5ad6-107">For a list of common MSBuild properties, see [Common MSBuild properties](/visualstudio/msbuild/common-msbuild-project-properties).</span></span>

## <a name="framework-properties"></a><span data-ttu-id="a5ad6-108">Свойства платформы</span><span class="sxs-lookup"><span data-stu-id="a5ad6-108">Framework properties</span></span>

- [<span data-ttu-id="a5ad6-109">TargetFramework</span><span class="sxs-lookup"><span data-stu-id="a5ad6-109">TargetFramework</span></span>](#targetframework)
- [<span data-ttu-id="a5ad6-110">TargetFrameworks</span><span class="sxs-lookup"><span data-stu-id="a5ad6-110">TargetFrameworks</span></span>](#targetframeworks)
- [<span data-ttu-id="a5ad6-111">NetStandardImplicitPackageVersion</span><span class="sxs-lookup"><span data-stu-id="a5ad6-111">NetStandardImplicitPackageVersion</span></span>](#netstandardimplicitpackageversion)

### <a name="targetframework"></a><span data-ttu-id="a5ad6-112">TargetFramework</span><span class="sxs-lookup"><span data-stu-id="a5ad6-112">TargetFramework</span></span>

<span data-ttu-id="a5ad6-113">Свойство `TargetFramework` указывает версию целевой платформы для приложения, которая неявно ссылается на [метапакет](../packages.md#metapackages).</span><span class="sxs-lookup"><span data-stu-id="a5ad6-113">The `TargetFramework` property specifies the target framework version for the app, which implicitly references a [metapackage](../packages.md#metapackages).</span></span> <span data-ttu-id="a5ad6-114">Список допустимых моникеров целевой платформы см. в статье [Целевые платформы в проектах в стиле SDK](../../standard/frameworks.md#supported-target-framework-versions).</span><span class="sxs-lookup"><span data-stu-id="a5ad6-114">For a list of valid target framework monikers, see [Target frameworks in SDK-style projects](../../standard/frameworks.md#supported-target-framework-versions).</span></span>

```xml
<PropertyGroup>
  <TargetFramework>netcoreapp3.1</TargetFramework>
</PropertyGroup>
```

<span data-ttu-id="a5ad6-115">Дополнительные сведения см.в статье [Целевые платформы в проектах в стиле SDK](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="a5ad6-115">For more information, see [Target frameworks in SDK-style projects](../../standard/frameworks.md).</span></span>

### <a name="targetframeworks"></a><span data-ttu-id="a5ad6-116">TargetFrameworks</span><span class="sxs-lookup"><span data-stu-id="a5ad6-116">TargetFrameworks</span></span>

<span data-ttu-id="a5ad6-117">Используйте свойство `TargetFrameworks`, если приложение должно быть предназначено для нескольких платформ.</span><span class="sxs-lookup"><span data-stu-id="a5ad6-117">Use the `TargetFrameworks` property when you want your app to target multiple platforms.</span></span> <span data-ttu-id="a5ad6-118">Список допустимых моникеров целевой платформы см. в статье [Целевые платформы в проектах в стиле SDK](../../standard/frameworks.md#supported-target-framework-versions).</span><span class="sxs-lookup"><span data-stu-id="a5ad6-118">For a list of valid target framework monikers, see [Target frameworks in SDK-style projects](../../standard/frameworks.md#supported-target-framework-versions).</span></span>

> [!NOTE]
> <span data-ttu-id="a5ad6-119">Это свойство игнорируется, если указано свойство `TargetFramework` (в единственном числе).</span><span class="sxs-lookup"><span data-stu-id="a5ad6-119">This property is ignored if `TargetFramework` (singular) is specified.</span></span>

```xml
<PropertyGroup>
  <TargetFrameworks>netcoreapp3.1;net462</TargetFrameworks>
</PropertyGroup>
```

<span data-ttu-id="a5ad6-120">Дополнительные сведения см.в статье [Целевые платформы в проектах в стиле SDK](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="a5ad6-120">For more information, see [Target frameworks in SDK-style projects](../../standard/frameworks.md).</span></span>

### <a name="netstandardimplicitpackageversion"></a><span data-ttu-id="a5ad6-121">NetStandardImplicitPackageVersion</span><span class="sxs-lookup"><span data-stu-id="a5ad6-121">NetStandardImplicitPackageVersion</span></span>

> [!NOTE]
> <span data-ttu-id="a5ad6-122">Это свойство применяется только к проектам, использующим `netstandard1.x`.</span><span class="sxs-lookup"><span data-stu-id="a5ad6-122">This property only applies to projects using `netstandard1.x`.</span></span> <span data-ttu-id="a5ad6-123">Он не применяется к проектам, использующим `netstandard2.x`.</span><span class="sxs-lookup"><span data-stu-id="a5ad6-123">It doesn't apply to projects that use `netstandard2.x`.</span></span>

<span data-ttu-id="a5ad6-124">Используйте свойство `NetStandardImplicitPackageVersion`, если требуется указать версию платформы ниже версии [метапакета](../packages.md#metapackages).</span><span class="sxs-lookup"><span data-stu-id="a5ad6-124">Use the `NetStandardImplicitPackageVersion` property when you want to specify a framework version that's lower than the [metapackage](../packages.md#metapackages) version.</span></span> <span data-ttu-id="a5ad6-125">Файл проекта, приведенный в следующем примере, предназначен для `netstandard1.3`, но использует `NETStandard.Library` версии 1.6.0.</span><span class="sxs-lookup"><span data-stu-id="a5ad6-125">The project file in the following example targets `netstandard1.3` but uses the 1.6.0 version of `NETStandard.Library`.</span></span>

```xml
<PropertyGroup>
  <TargetFramework>netstandard1.3</TargetFramework>
  <NetStandardImplicitPackageVersion>1.6.0</NetStandardImplicitPackageVersion>
</PropertyGroup>
```

## <a name="package-properties"></a><span data-ttu-id="a5ad6-126">Свойства пакета</span><span class="sxs-lookup"><span data-stu-id="a5ad6-126">Package properties</span></span>

<span data-ttu-id="a5ad6-127">Для описания пакета, созданного из проекта, можно указать такие свойства, как `PackageId`, `PackageVersion`, `PackageIcon`, `Title` и `Description`.</span><span class="sxs-lookup"><span data-stu-id="a5ad6-127">You can specify properties such as `PackageId`, `PackageVersion`, `PackageIcon`, `Title`, and `Description` to describe the package that gets created from your project.</span></span> <span data-ttu-id="a5ad6-128">Дополнительные сведения об этих и других свойствах см. в разделе [целевой объект пакета](/nuget/reference/msbuild-targets#pack-target).</span><span class="sxs-lookup"><span data-stu-id="a5ad6-128">For information about these and other properties, see [pack target](/nuget/reference/msbuild-targets#pack-target).</span></span>

```xml
<PropertyGroup>
  ...
  <PackageId>ClassLibDotNetStandard</PackageId>
  <Version>1.0.0</Version>
  <Authors>John Doe</Authors>
  <Company>Contoso</Company>
</PropertyGroup>
```

## <a name="publish-properties"></a><span data-ttu-id="a5ad6-129">Параметры публикации</span><span class="sxs-lookup"><span data-stu-id="a5ad6-129">Publish properties</span></span>

- [<span data-ttu-id="a5ad6-130">RuntimeIdentifier</span><span class="sxs-lookup"><span data-stu-id="a5ad6-130">RuntimeIdentifier</span></span>](#runtimeidentifier)
- [<span data-ttu-id="a5ad6-131">RuntimeIdentifiers</span><span class="sxs-lookup"><span data-stu-id="a5ad6-131">RuntimeIdentifiers</span></span>](#runtimeidentifiers)
- [<span data-ttu-id="a5ad6-132">TrimmerRootAssembly</span><span class="sxs-lookup"><span data-stu-id="a5ad6-132">TrimmerRootAssembly</span></span>](#trimmerrootassembly)
- [<span data-ttu-id="a5ad6-133">UseAppHost</span><span class="sxs-lookup"><span data-stu-id="a5ad6-133">UseAppHost</span></span>](#useapphost)

### <a name="runtimeidentifier"></a><span data-ttu-id="a5ad6-134">RuntimeIdentifier</span><span class="sxs-lookup"><span data-stu-id="a5ad6-134">RuntimeIdentifier</span></span>

<span data-ttu-id="a5ad6-135">Свойство `RuntimeIdentifier` позволяет указать для проекта один [идентификатор среды выполнения (RID)](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="a5ad6-135">The `RuntimeIdentifier` property lets you specify a single [runtime identifier (RID)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="a5ad6-136">Идентификатор среды выполнения позволяет опубликовать автономное развертывание.</span><span class="sxs-lookup"><span data-stu-id="a5ad6-136">The RID enables publishing a self-contained deployment.</span></span>

```xml
<PropertyGroup>
  <RuntimeIdentifier>ubuntu.16.04-x64</RuntimeIdentifier>
</PropertyGroup>
```

### <a name="runtimeidentifiers"></a><span data-ttu-id="a5ad6-137">RuntimeIdentifiers</span><span class="sxs-lookup"><span data-stu-id="a5ad6-137">RuntimeIdentifiers</span></span>

<span data-ttu-id="a5ad6-138">Свойство `RuntimeIdentifiers` позволяет указать для проекта список [идентификаторов среды выполнения (RID)](../rid-catalog.md) (в качестве разделителя используется точка с запятой).</span><span class="sxs-lookup"><span data-stu-id="a5ad6-138">The `RuntimeIdentifiers` property lets you specify a semicolon-delimited list of [runtime identifiers (RIDs)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="a5ad6-139">Используйте это свойство, если вам нужна публикация для нескольких сред.</span><span class="sxs-lookup"><span data-stu-id="a5ad6-139">Use this property if you need to publish for multiple runtimes.</span></span> <span data-ttu-id="a5ad6-140">`RuntimeIdentifiers` используется во время восстановления для обеспечения наличия в графе нужных ресурсов.</span><span class="sxs-lookup"><span data-stu-id="a5ad6-140">`RuntimeIdentifiers` is used at restore time to ensure the right assets are in the graph.</span></span>

> [!TIP]
> <span data-ttu-id="a5ad6-141">`RuntimeIdentifier` (в единственном числе) может ускорить создание сборок, когда требуется только одна среда выполнения.</span><span class="sxs-lookup"><span data-stu-id="a5ad6-141">`RuntimeIdentifier` (singular) can provide faster builds when only a single runtime is required.</span></span>

```xml
<PropertyGroup>
  <RuntimeIdentifiers>win10-x64;osx.10.11-x64;ubuntu.16.04-x64</RuntimeIdentifiers>
</PropertyGroup>
```

### <a name="trimmerrootassembly"></a><span data-ttu-id="a5ad6-142">TrimmerRootAssembly</span><span class="sxs-lookup"><span data-stu-id="a5ad6-142">TrimmerRootAssembly</span></span>

<span data-ttu-id="a5ad6-143">Элемент `TrimmerRootAssembly` позволяет исключить сборку из [*обрезки*](../deploying/trim-self-contained.md).</span><span class="sxs-lookup"><span data-stu-id="a5ad6-143">The `TrimmerRootAssembly` item lets you exclude an assembly from [*trimming*](../deploying/trim-self-contained.md).</span></span> <span data-ttu-id="a5ad6-144">Обрезка — это процесс удаления неиспользуемых частей среды выполнения из упакованного приложения.</span><span class="sxs-lookup"><span data-stu-id="a5ad6-144">Trimming is the process of removing unused parts of the runtime from a packaged application.</span></span> <span data-ttu-id="a5ad6-145">В некоторых случаях при обрезке могут неправильно удаляться необходимые ссылки.</span><span class="sxs-lookup"><span data-stu-id="a5ad6-145">In some cases, trimming might incorrectly remove required references.</span></span>

<span data-ttu-id="a5ad6-146">Следующий код XML исключает сборку `System.Security` из обрезки.</span><span class="sxs-lookup"><span data-stu-id="a5ad6-146">The following XML excludes the `System.Security` assembly from trimming.</span></span>

```xml
<ItemGroup>
  <TrimmerRootAssembly Include="System.Security" />
</ItemGroup>
```

### <a name="useapphost"></a><span data-ttu-id="a5ad6-147">UseAppHost</span><span class="sxs-lookup"><span data-stu-id="a5ad6-147">UseAppHost</span></span>

<span data-ttu-id="a5ad6-148">Свойство `UseAppHost` было представлено в пакете SDK для .NET Core.версии 2.1.400.</span><span class="sxs-lookup"><span data-stu-id="a5ad6-148">The `UseAppHost` property was introduced in the 2.1.400 version of the .NET Core SDK.</span></span> <span data-ttu-id="a5ad6-149">Оно контролирует создание собственного исполняемого файла для развертывания.</span><span class="sxs-lookup"><span data-stu-id="a5ad6-149">It controls whether or not a native executable is created for a deployment.</span></span> <span data-ttu-id="a5ad6-150">Этот файл требуется для автономных развертываний.</span><span class="sxs-lookup"><span data-stu-id="a5ad6-150">A native executable is required for self-contained deployments.</span></span>

<span data-ttu-id="a5ad6-151">В .NET Core 3.0 и более поздних версиях зависимый от платформы исполняемый файл создается по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a5ad6-151">In .NET Core 3.0 and later versions, a framework-dependent executable is created by default.</span></span> <span data-ttu-id="a5ad6-152">Задайте свойству `UseAppHost` значение `false`, чтобы отключить создание исполняемого файла.</span><span class="sxs-lookup"><span data-stu-id="a5ad6-152">Set the `UseAppHost` property to `false` to disable generation of the executable.</span></span>

```xml
<PropertyGroup>
  <UseAppHost>false</UseAppHost>
</PropertyGroup>
```

<span data-ttu-id="a5ad6-153">Дополнительные сведения о развертывании см. в статье [Развертывание приложений .NET Core](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="a5ad6-153">For more information about deployment, see [.NET Core application deployment](../deploying/index.md).</span></span>

## <a name="compile-properties"></a><span data-ttu-id="a5ad6-154">Свойства компиляции</span><span class="sxs-lookup"><span data-stu-id="a5ad6-154">Compile properties</span></span>

- [<span data-ttu-id="a5ad6-155">LangVersion</span><span class="sxs-lookup"><span data-stu-id="a5ad6-155">LangVersion</span></span>](#langversion)

### <a name="langversion"></a><span data-ttu-id="a5ad6-156">LangVersion</span><span class="sxs-lookup"><span data-stu-id="a5ad6-156">LangVersion</span></span>

<span data-ttu-id="a5ad6-157">Свойство `LangVersion` позволяет указать конкретную версию языка программирования.</span><span class="sxs-lookup"><span data-stu-id="a5ad6-157">The `LangVersion` property lets you specify a specific programming language version.</span></span> <span data-ttu-id="a5ad6-158">Например, если требуется доступ к предварительным версиям функций C#, задайте параметру `LangVersion` значение `preview`.</span><span class="sxs-lookup"><span data-stu-id="a5ad6-158">For example, if you want access to C# preview features, set `LangVersion` to `preview`.</span></span>

```xml
<PropertyGroup>
  <LangVersion>preview</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="a5ad6-159">Дополнительные сведения см. в статье [Управление версиями языка C#](../../csharp/language-reference/configure-language-version.md#override-a-default).</span><span class="sxs-lookup"><span data-stu-id="a5ad6-159">For more information, see [C# language versioning](../../csharp/language-reference/configure-language-version.md#override-a-default).</span></span>

## <a name="run-time-configuration-properties"></a><span data-ttu-id="a5ad6-160">Свойства конфигурации среды выполнения</span><span class="sxs-lookup"><span data-stu-id="a5ad6-160">Run-time configuration properties</span></span>

<span data-ttu-id="a5ad6-161">Вы можете настроить некоторые варианты поведения среды выполнения, указав свойства MSBuild в файле проекта приложения.</span><span class="sxs-lookup"><span data-stu-id="a5ad6-161">You can configure some run-time behaviors by specifying MSBuild properties in the project file of the app.</span></span> <span data-ttu-id="a5ad6-162">Сведения о других способах настройки поведения среды выполнения см. в разделе [Параметры конфигурации среды выполнения .NET Core](../run-time-config/index.md).</span><span class="sxs-lookup"><span data-stu-id="a5ad6-162">For information about other ways of configuring run-time behavior, see [.NET Core run-time configuration settings](../run-time-config/index.md).</span></span>

- [<span data-ttu-id="a5ad6-163">ConcurrentGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="a5ad6-163">ConcurrentGarbageCollection</span></span>](#concurrentgarbagecollection)
- [<span data-ttu-id="a5ad6-164">InvariantGlobalization</span><span class="sxs-lookup"><span data-stu-id="a5ad6-164">InvariantGlobalization</span></span>](#invariantglobalization)
- [<span data-ttu-id="a5ad6-165">RetainVMGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="a5ad6-165">RetainVMGarbageCollection</span></span>](#retainvmgarbagecollection)
- [<span data-ttu-id="a5ad6-166">ServerGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="a5ad6-166">ServerGarbageCollection</span></span>](#servergarbagecollection)
- [<span data-ttu-id="a5ad6-167">ThreadPoolMaxThreads</span><span class="sxs-lookup"><span data-stu-id="a5ad6-167">ThreadPoolMaxThreads</span></span>](#threadpoolmaxthreads)
- [<span data-ttu-id="a5ad6-168">ThreadPoolMinThreads</span><span class="sxs-lookup"><span data-stu-id="a5ad6-168">ThreadPoolMinThreads</span></span>](#threadpoolminthreads)
- [<span data-ttu-id="a5ad6-169">TieredCompilation</span><span class="sxs-lookup"><span data-stu-id="a5ad6-169">TieredCompilation</span></span>](#tieredcompilation)
- [<span data-ttu-id="a5ad6-170">TieredCompilationQuickJit</span><span class="sxs-lookup"><span data-stu-id="a5ad6-170">TieredCompilationQuickJit</span></span>](#tieredcompilationquickjit)
- [<span data-ttu-id="a5ad6-171">TieredCompilationQuickJitForLoops</span><span class="sxs-lookup"><span data-stu-id="a5ad6-171">TieredCompilationQuickJitForLoops</span></span>](#tieredcompilationquickjitforloops)

### <a name="concurrentgarbagecollection"></a><span data-ttu-id="a5ad6-172">ConcurrentGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="a5ad6-172">ConcurrentGarbageCollection</span></span>

<span data-ttu-id="a5ad6-173">Свойство `ConcurrentGarbageCollection` указывает, включена ли [фоновая (параллельная) сборка мусора](../../standard/garbage-collection/background-gc.md).</span><span class="sxs-lookup"><span data-stu-id="a5ad6-173">The `ConcurrentGarbageCollection` property configures whether [background (concurrent) garbage collection](../../standard/garbage-collection/background-gc.md) is enabled.</span></span> <span data-ttu-id="a5ad6-174">Задайте значение `false`, чтобы отключить фоновую сборку мусора.</span><span class="sxs-lookup"><span data-stu-id="a5ad6-174">Set the value to `false` to disable background garbage collection.</span></span> <span data-ttu-id="a5ad6-175">Дополнительные сведения см. в разделе [System.GC.Concurrent/COMPlus_gcConcurrent](../run-time-config/garbage-collector.md#systemgcconcurrentcomplus_gcconcurrent).</span><span class="sxs-lookup"><span data-stu-id="a5ad6-175">For more information, see [System.GC.Concurrent/COMPlus_gcConcurrent](../run-time-config/garbage-collector.md#systemgcconcurrentcomplus_gcconcurrent).</span></span>

```xml
<PropertyGroup>
  <ConcurrentGarbageCollection>false</ConcurrentGarbageCollection>
</PropertyGroup>
```

### <a name="invariantglobalization"></a><span data-ttu-id="a5ad6-176">InvariantGlobalization</span><span class="sxs-lookup"><span data-stu-id="a5ad6-176">InvariantGlobalization</span></span>

<span data-ttu-id="a5ad6-177">Свойство `InvariantGlobalization` определяет, выполняется ли приложение в *инвариантном режиме глобализации*, что означает, что у него нет доступа к данным, относящимся к языку и региональным параметрам.</span><span class="sxs-lookup"><span data-stu-id="a5ad6-177">The `InvariantGlobalization` property configures whether the app runs in *globalization-invariant* mode, which means it doesn't have access to culture-specific data.</span></span> <span data-ttu-id="a5ad6-178">Установите значение `true` для запуска в инвариантном режиме глобализации.</span><span class="sxs-lookup"><span data-stu-id="a5ad6-178">Set the value to `true` to run in globalization-invariant mode.</span></span> <span data-ttu-id="a5ad6-179">Дополнительные сведения см. в разделе [Инвариантный режим](../run-time-config/globalization.md#invariant-mode).</span><span class="sxs-lookup"><span data-stu-id="a5ad6-179">For more information, see [Invariant mode](../run-time-config/globalization.md#invariant-mode).</span></span>

```xml
<PropertyGroup>
  <InvariantGlobalization>true</InvariantGlobalization>
</PropertyGroup>
```

### <a name="retainvmgarbagecollection"></a><span data-ttu-id="a5ad6-180">RetainVMGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="a5ad6-180">RetainVMGarbageCollection</span></span>

<span data-ttu-id="a5ad6-181">Свойство `RetainVMGarbageCollection` настраивает сборщик мусора для помещения удаленных сегментов памяти в список ожидания для будущего использования или освобождения.</span><span class="sxs-lookup"><span data-stu-id="a5ad6-181">The `RetainVMGarbageCollection` property configures the garbage collector to put deleted memory segments on a standby list for future use or release them.</span></span> <span data-ttu-id="a5ad6-182">Значение `true` указывает сборщику мусора разместить сегменты в списке ожидания.</span><span class="sxs-lookup"><span data-stu-id="a5ad6-182">Setting the value to `true` tells the garbage collector to put the segments on a standby list.</span></span> <span data-ttu-id="a5ad6-183">Дополнительные сведения см. в разделе [System.GC.RetainVM/COMPlus_GCRetainVM](../run-time-config/garbage-collector.md#systemgcretainvmcomplus_gcretainvm).</span><span class="sxs-lookup"><span data-stu-id="a5ad6-183">For more information, see [System.GC.RetainVM/COMPlus_GCRetainVM](../run-time-config/garbage-collector.md#systemgcretainvmcomplus_gcretainvm).</span></span>

```xml
<PropertyGroup>
  <RetainVMGarbageCollection>true</RetainVMGarbageCollection>
</PropertyGroup>
```

### <a name="servergarbagecollection"></a><span data-ttu-id="a5ad6-184">ServerGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="a5ad6-184">ServerGarbageCollection</span></span>

<span data-ttu-id="a5ad6-185">Свойство `ServerGarbageCollection` указывает, использует ли приложение [сборку мусора рабочей станции или сборку мусора сервера](../../standard/garbage-collection/workstation-server-gc.md).</span><span class="sxs-lookup"><span data-stu-id="a5ad6-185">The `ServerGarbageCollection` property configures whether the application uses [workstation garbage collection or server garbage collection](../../standard/garbage-collection/workstation-server-gc.md).</span></span> <span data-ttu-id="a5ad6-186">Задайте значение `true`, чтобы использовать сборку мусора сервера.</span><span class="sxs-lookup"><span data-stu-id="a5ad6-186">Set the value to `true` to use server garbage collection.</span></span> <span data-ttu-id="a5ad6-187">Дополнительные сведения см. в разделе [System.GC.Server/COMPlus_gcServer](../run-time-config/garbage-collector.md#systemgcservercomplus_gcserver).</span><span class="sxs-lookup"><span data-stu-id="a5ad6-187">For more information, see [System.GC.Server/COMPlus_gcServer](../run-time-config/garbage-collector.md#systemgcservercomplus_gcserver).</span></span>

```xml
<PropertyGroup>
  <ServerGarbageCollection>true</ServerGarbageCollection>
</PropertyGroup>
```

### <a name="threadpoolmaxthreads"></a><span data-ttu-id="a5ad6-188">ThreadPoolMaxThreads</span><span class="sxs-lookup"><span data-stu-id="a5ad6-188">ThreadPoolMaxThreads</span></span>

<span data-ttu-id="a5ad6-189">Свойство `ThreadPoolMaxThreads` указывает максимальное число потоков для пула рабочих потоков.</span><span class="sxs-lookup"><span data-stu-id="a5ad6-189">The `ThreadPoolMaxThreads` property configures the maximum number of threads for the worker thread pool.</span></span> <span data-ttu-id="a5ad6-190">Дополнительные сведения см. в разделе [Максимальное число потоков](../run-time-config/threading.md#maximum-threads).</span><span class="sxs-lookup"><span data-stu-id="a5ad6-190">For more information, see [Maximum threads](../run-time-config/threading.md#maximum-threads).</span></span>

```xml
<PropertyGroup>
  <ThreadPoolMaxThreads>20</ThreadPoolMaxThreads>
</PropertyGroup>
```

### <a name="threadpoolminthreads"></a><span data-ttu-id="a5ad6-191">ThreadPoolMinThreads</span><span class="sxs-lookup"><span data-stu-id="a5ad6-191">ThreadPoolMinThreads</span></span>

<span data-ttu-id="a5ad6-192">Свойство `ThreadPoolMinThreads` указывает минимальное число потоков для пула рабочих потоков.</span><span class="sxs-lookup"><span data-stu-id="a5ad6-192">The `ThreadPoolMinThreads` property configures the minimum number of threads for the worker thread pool.</span></span> <span data-ttu-id="a5ad6-193">Дополнительные сведения см. в разделе [Минимальное число потоков](../run-time-config/threading.md#minimum-threads).</span><span class="sxs-lookup"><span data-stu-id="a5ad6-193">For more information, see [Minimum threads](../run-time-config/threading.md#minimum-threads).</span></span>

```xml
<PropertyGroup>
  <ThreadPoolMinThreads>4</ThreadPoolMinThreads>
</PropertyGroup>
```

### <a name="tieredcompilation"></a><span data-ttu-id="a5ad6-194">TieredCompilation</span><span class="sxs-lookup"><span data-stu-id="a5ad6-194">TieredCompilation</span></span>

<span data-ttu-id="a5ad6-195">Свойство `TieredCompilation` указывает, использует ли JIT-компилятор [многоуровневую компиляцию](../whats-new/dotnet-core-3-0.md#tiered-compilation).</span><span class="sxs-lookup"><span data-stu-id="a5ad6-195">The `TieredCompilation` property configures whether the just-in-time (JIT) compiler uses [tiered compilation](../whats-new/dotnet-core-3-0.md#tiered-compilation).</span></span> <span data-ttu-id="a5ad6-196">Задайте значение `false`, чтобы отключить многоуровневую компиляцию.</span><span class="sxs-lookup"><span data-stu-id="a5ad6-196">Set the value to `false` to disable tiered compilation.</span></span> <span data-ttu-id="a5ad6-197">Дополнительные сведения см. в разделе [Многоуровневая компиляция](../run-time-config/compilation.md#tiered-compilation).</span><span class="sxs-lookup"><span data-stu-id="a5ad6-197">For more information, see [Tiered compilation](../run-time-config/compilation.md#tiered-compilation).</span></span>

```xml
<PropertyGroup>
  <TieredCompilation>false</TieredCompilation>
</PropertyGroup>
```

### <a name="tieredcompilationquickjit"></a><span data-ttu-id="a5ad6-198">TieredCompilationQuickJit</span><span class="sxs-lookup"><span data-stu-id="a5ad6-198">TieredCompilationQuickJit</span></span>

<span data-ttu-id="a5ad6-199">Свойство `TieredCompilationQuickJit` указывает, использует ли JIT-компилятор быструю JIT-компиляцию.</span><span class="sxs-lookup"><span data-stu-id="a5ad6-199">The `TieredCompilationQuickJit` property configures whether the JIT compiler uses quick JIT.</span></span> <span data-ttu-id="a5ad6-200">Задайте значение `false`, чтобы отключить быструю JIT-компиляцию.</span><span class="sxs-lookup"><span data-stu-id="a5ad6-200">Set the value to `false` to disable quick JIT.</span></span> <span data-ttu-id="a5ad6-201">Дополнительные сведения см. в разделе [Быстрая JIT-компиляция](../run-time-config/compilation.md#quick-jit).</span><span class="sxs-lookup"><span data-stu-id="a5ad6-201">For more information, see [Quick JIT](../run-time-config/compilation.md#quick-jit).</span></span>

```xml
<PropertyGroup>
  <TieredCompilationQuickJit>false</TieredCompilationQuickJit>
</PropertyGroup>
```

### <a name="tieredcompilationquickjitforloops"></a><span data-ttu-id="a5ad6-202">TieredCompilationQuickJitForLoops</span><span class="sxs-lookup"><span data-stu-id="a5ad6-202">TieredCompilationQuickJitForLoops</span></span>

<span data-ttu-id="a5ad6-203">Свойство `TieredCompilationQuickJitForLoops` указывает, использует ли JIT-компилятор быструю JIT-компиляцию для методов, содержащих циклы.</span><span class="sxs-lookup"><span data-stu-id="a5ad6-203">The `TieredCompilationQuickJitForLoops` property configures whether the JIT compiler uses quick JIT on methods that contain loops.</span></span> <span data-ttu-id="a5ad6-204">Задайте значение `true`, чтобы включить быструю JIT-компиляцию для методов, содержащих циклы.</span><span class="sxs-lookup"><span data-stu-id="a5ad6-204">Set the value to `true` to enable quick JIT on methods that contain loops.</span></span> <span data-ttu-id="a5ad6-205">Дополнительные сведения см. в разделе [Быстрая JIT-компиляция для циклов](../run-time-config/compilation.md#quick-jit-for-loops).</span><span class="sxs-lookup"><span data-stu-id="a5ad6-205">For more information, see [Quick JIT for loops](../run-time-config/compilation.md#quick-jit-for-loops).</span></span>

```xml
<PropertyGroup>
  <TieredCompilationQuickJitForLoops>true</TieredCompilationQuickJitForLoops>
</PropertyGroup>
```

## <a name="reference-properties"></a><span data-ttu-id="a5ad6-206">Свойства ссылки</span><span class="sxs-lookup"><span data-stu-id="a5ad6-206">Reference properties</span></span>

- [<span data-ttu-id="a5ad6-207">AssetTargetFallback</span><span class="sxs-lookup"><span data-stu-id="a5ad6-207">AssetTargetFallback</span></span>](#assettargetfallback)
- [<span data-ttu-id="a5ad6-208">PackageReference</span><span class="sxs-lookup"><span data-stu-id="a5ad6-208">PackageReference</span></span>](#packagereference)
- [<span data-ttu-id="a5ad6-209">ProjectReference</span><span class="sxs-lookup"><span data-stu-id="a5ad6-209">ProjectReference</span></span>](#projectreference)
- [<span data-ttu-id="a5ad6-210">Ссылки</span><span class="sxs-lookup"><span data-stu-id="a5ad6-210">Reference</span></span>](#reference)
- [<span data-ttu-id="a5ad6-211">Свойства восстановления</span><span class="sxs-lookup"><span data-stu-id="a5ad6-211">Restore properties</span></span>](#restore-properties)

### <a name="assettargetfallback"></a><span data-ttu-id="a5ad6-212">AssetTargetFallback</span><span class="sxs-lookup"><span data-stu-id="a5ad6-212">AssetTargetFallback</span></span>

<span data-ttu-id="a5ad6-213">Свойство `AssetTargetFallback` позволяет указать дополнительные совместимые версии платформы для ссылок на проекты и пакетов NuGet.</span><span class="sxs-lookup"><span data-stu-id="a5ad6-213">The `AssetTargetFallback` property lets you specify additional compatible framework versions for project references and NuGet packages.</span></span> <span data-ttu-id="a5ad6-214">Например, если вы указали зависимость пакета с помощью `PackageReference`, но в этом пакете нет ресурсов, совместимых с `TargetFramework` вашего проекта, тогда пригодится свойство `AssetTargetFallback`.</span><span class="sxs-lookup"><span data-stu-id="a5ad6-214">For example, if you specify a package dependency using `PackageReference` but that package doesn't contain assets that are compatible with your projects's `TargetFramework`, the `AssetTargetFallback` property comes into play.</span></span> <span data-ttu-id="a5ad6-215">Совместимость пакета, на который указывает ссылка, повторно проверяется с помощью каждой целевой платформы, указанной в свойстве `AssetTargetFallback`.</span><span class="sxs-lookup"><span data-stu-id="a5ad6-215">The compatibility of the referenced package is rechecked using each target framework that's specified in `AssetTargetFallback`.</span></span>

<span data-ttu-id="a5ad6-216">В качестве значения свойства `AssetTargetFallback` можно задать одну [версию целевой платформы](../../standard/frameworks.md#supported-target-framework-versions) или несколько.</span><span class="sxs-lookup"><span data-stu-id="a5ad6-216">You can set the `AssetTargetFallback` property to one or more [target framework versions](../../standard/frameworks.md#supported-target-framework-versions).</span></span>

```xml
<PropertyGroup>
  <AssetTargetFallback>net461</AssetTargetFallback>
</PropertyGroup>
```

### <a name="packagereference"></a><span data-ttu-id="a5ad6-217">PackageReference</span><span class="sxs-lookup"><span data-stu-id="a5ad6-217">PackageReference</span></span>

<span data-ttu-id="a5ad6-218">`PackageReference` определяет ссылку на пакет NuGet.</span><span class="sxs-lookup"><span data-stu-id="a5ad6-218">The `PackageReference` defines a reference to a NuGet package.</span></span> <span data-ttu-id="a5ad6-219">Например, может потребоваться сослаться на один пакет, а не на [метапакет](../packages.md#metapackages).</span><span class="sxs-lookup"><span data-stu-id="a5ad6-219">For example, you may want to reference a single package instead of a [metapackage](../packages.md#metapackages).</span></span>

<span data-ttu-id="a5ad6-220">Атрибут `Include` указывает идентификатор пакета.</span><span class="sxs-lookup"><span data-stu-id="a5ad6-220">The `Include` attribute specifies the package ID.</span></span> <span data-ttu-id="a5ad6-221">Атрибут `Version` указывает версию или диапазон версий.</span><span class="sxs-lookup"><span data-stu-id="a5ad6-221">The `Version` attribute specifies the version or version range.</span></span> <span data-ttu-id="a5ad6-222">Сведения о том, как указать минимальную версию, максимальную версию, диапазон или точное соответствие, см. в разделе [Диапазоны версий](/nuget/concepts/package-versioning#version-ranges).</span><span class="sxs-lookup"><span data-stu-id="a5ad6-222">For information about how to specify a minimum version, maximum version, range, or exact match, see [Version ranges](/nuget/concepts/package-versioning#version-ranges).</span></span> <span data-ttu-id="a5ad6-223">Вы также можете добавить в ссылку на проект следующие метаданные: `IncludeAssets`, `ExcludeAssets` и `PrivateAssets`.</span><span class="sxs-lookup"><span data-stu-id="a5ad6-223">You can also add the following metadata to a project reference: `IncludeAssets`, `ExcludeAssets`, and `PrivateAssets`.</span></span>

<span data-ttu-id="a5ad6-224">Фрагмент файла проекта в следующем примере ссылается на пакет [System.Runtime](https://www.nuget.org/packages/System.Runtime/).</span><span class="sxs-lookup"><span data-stu-id="a5ad6-224">The project file snippet in the following example references the [System.Runtime](https://www.nuget.org/packages/System.Runtime/) package.</span></span>

```xml
<ItemGroup>
  <PackageReference Include="System.Runtime" Version="4.3.0" />
</ItemGroup>
```

<span data-ttu-id="a5ad6-225">Дополнительные сведения см. в статье [Ссылки на пакеты в файлах проекта](/nuget/consume-packages/package-references-in-project-files).</span><span class="sxs-lookup"><span data-stu-id="a5ad6-225">For more information, see [Package references in project files](/nuget/consume-packages/package-references-in-project-files).</span></span>

### <a name="projectreference"></a><span data-ttu-id="a5ad6-226">СсылкаНаПроект</span><span class="sxs-lookup"><span data-stu-id="a5ad6-226">ProjectReference</span></span>

<span data-ttu-id="a5ad6-227">Элемент `ProjectReference` определяет ссылку на другой проект.</span><span class="sxs-lookup"><span data-stu-id="a5ad6-227">The `ProjectReference` item defines a reference to another project.</span></span> <span data-ttu-id="a5ad6-228">Проект, на который указывает ссылка, добавляется как зависимость пакета NuGet, то есть обрабатывается так же, как `PackageReference`.</span><span class="sxs-lookup"><span data-stu-id="a5ad6-228">The referenced project is added as a NuGet package dependency, that is, it's treated the same as a `PackageReference`.</span></span>

<span data-ttu-id="a5ad6-229">Атрибут `Include` задает путь к проекту.</span><span class="sxs-lookup"><span data-stu-id="a5ad6-229">The `Include` attribute specifies the path to the project.</span></span> <span data-ttu-id="a5ad6-230">Вы также можете добавить в ссылку на проект следующие метаданные: `IncludeAssets`, `ExcludeAssets` и `PrivateAssets`.</span><span class="sxs-lookup"><span data-stu-id="a5ad6-230">You can also add the following metadata to a project reference: `IncludeAssets`, `ExcludeAssets`, and `PrivateAssets`.</span></span>

<span data-ttu-id="a5ad6-231">Фрагмент файла проекта в следующем примере ссылается на проект `Project2`.</span><span class="sxs-lookup"><span data-stu-id="a5ad6-231">The project file snippet in the following example references a project named `Project2`.</span></span>

```xml
<ItemGroup>
  <ProjectReference Include="..\Project2.csproj" />
</ItemGroup>
```

### <a name="reference"></a><span data-ttu-id="a5ad6-232">Справочник</span><span class="sxs-lookup"><span data-stu-id="a5ad6-232">Reference</span></span>

<span data-ttu-id="a5ad6-233">Элемент `Reference` определяет ссылку на файл сборки.</span><span class="sxs-lookup"><span data-stu-id="a5ad6-233">The `Reference` item defines a reference to an assembly file.</span></span>

<span data-ttu-id="a5ad6-234">Атрибут `Include` задает имя файла, а дочерний элемент `HintPath` указывает путь к сборке.</span><span class="sxs-lookup"><span data-stu-id="a5ad6-234">The `Include` attribute specifies the name of the file, and the `HintPath` child element specifies the path to the assembly.</span></span>

```xml
<ItemGroup>
  <Reference Include="MyAssembly">
    <HintPath>..\..\Assemblies\MyAssembly.dll</HintPath>
  </Reference>
</ItemGroup>
```

### <a name="restore-properties"></a><span data-ttu-id="a5ad6-235">Свойства восстановления</span><span class="sxs-lookup"><span data-stu-id="a5ad6-235">Restore properties</span></span>

<span data-ttu-id="a5ad6-236">При восстановлении пакета, на который указывает ссылка, устанавливаются все его прямые зависимости и все зависимости этих зависимостей.</span><span class="sxs-lookup"><span data-stu-id="a5ad6-236">Restoring a referenced package installs all of its direct dependencies and all the dependencies of those dependencies.</span></span> <span data-ttu-id="a5ad6-237">Можно настроить восстановление пакетов, указав такие свойства, как `RestorePackagesPath` и `RestoreIgnoreFailedSources`.</span><span class="sxs-lookup"><span data-stu-id="a5ad6-237">You can customize package restoration by specifying properties such as `RestorePackagesPath` and `RestoreIgnoreFailedSources`.</span></span> <span data-ttu-id="a5ad6-238">Дополнительные сведения об этих и других свойствах см. в разделе [целевой объект восстановления](/nuget/reference/msbuild-targets#restore-target).</span><span class="sxs-lookup"><span data-stu-id="a5ad6-238">For more information about these and other properties, see [restore target](/nuget/reference/msbuild-targets#restore-target).</span></span>

```xml
<PropertyGroup>
  <RestoreIgnoreFailedSource>true</RestoreIgnoreFailedSource>
</PropertyGroup>
```

## <a name="see-also"></a><span data-ttu-id="a5ad6-239">См. также</span><span class="sxs-lookup"><span data-stu-id="a5ad6-239">See also</span></span>

- [<span data-ttu-id="a5ad6-240">Справочник по схеме MSBuild</span><span class="sxs-lookup"><span data-stu-id="a5ad6-240">MSBuild schema reference</span></span>](/visualstudio/msbuild/msbuild-project-file-schema-reference)
- [<span data-ttu-id="a5ad6-241">Общие свойства MSBuild</span><span class="sxs-lookup"><span data-stu-id="a5ad6-241">Common MSBuild properties</span></span>](/visualstudio/msbuild/common-msbuild-project-properties)
- [<span data-ttu-id="a5ad6-242">Свойства MSBuild для целевого объекта pack NuGet</span><span class="sxs-lookup"><span data-stu-id="a5ad6-242">MSBuild properties for NuGet pack</span></span>](/nuget/reference/msbuild-targets#pack-target)
- [<span data-ttu-id="a5ad6-243">Свойства MSBuild для целевого объекта restore NuGet</span><span class="sxs-lookup"><span data-stu-id="a5ad6-243">MSBuild properties for NuGet restore</span></span>](/nuget/reference/msbuild-targets#restore-properties)
- [<span data-ttu-id="a5ad6-244">Настройка сборки</span><span class="sxs-lookup"><span data-stu-id="a5ad6-244">Customize a build</span></span>](/visualstudio/msbuild/customize-your-build)
