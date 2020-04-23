---
title: Свойства MSBuild для Microsoft.NET.Sdk
description: Справочник по свойствам MSBuild, распознаваемым пакетом SDK для .NET Core.
ms.date: 02/14/2020
ms.topic: reference
ms.openlocfilehash: d4a204a1e0216313418d278ec3bd333f72db8751
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "81386660"
---
# <a name="msbuild-properties-for-net-core-sdk-projects"></a><span data-ttu-id="a6e32-103">Свойства MSBuild для проектов пакета SDK для .NET Core</span><span class="sxs-lookup"><span data-stu-id="a6e32-103">MSBuild properties for .NET Core SDK projects</span></span>

<span data-ttu-id="a6e32-104">На этой странице описываются свойства MSBuild для настройки проектов .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a6e32-104">This page describes MSBuild properties for configuring .NET Core projects.</span></span>

> [!NOTE]
> <span data-ttu-id="a6e32-105">Работа над этой страницей еще не завершена, поэтому здесь приведены лишь некоторые полезные свойства MSBuild для пакета SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a6e32-105">This page is a work in progress and does not list all of the useful MSBuild properties for the .NET Core SDK.</span></span> <span data-ttu-id="a6e32-106">Список стандартных свойств см. в статье [Общие свойства MSBuild](/visualstudio/msbuild/common-msbuild-project-properties).</span><span class="sxs-lookup"><span data-stu-id="a6e32-106">For a list of common MSBuild properties, see [Common MSBuild properties](/visualstudio/msbuild/common-msbuild-project-properties).</span></span>

## <a name="framework-properties"></a><span data-ttu-id="a6e32-107">Свойства платформы</span><span class="sxs-lookup"><span data-stu-id="a6e32-107">Framework properties</span></span>

- [<span data-ttu-id="a6e32-108">TargetFramework</span><span class="sxs-lookup"><span data-stu-id="a6e32-108">TargetFramework</span></span>](#targetframework)
- [<span data-ttu-id="a6e32-109">TargetFrameworks</span><span class="sxs-lookup"><span data-stu-id="a6e32-109">TargetFrameworks</span></span>](#targetframeworks)
- [<span data-ttu-id="a6e32-110">NetStandardImplicitPackageVersion</span><span class="sxs-lookup"><span data-stu-id="a6e32-110">NetStandardImplicitPackageVersion</span></span>](#netstandardimplicitpackageversion)

### <a name="targetframework"></a><span data-ttu-id="a6e32-111">TargetFramework</span><span class="sxs-lookup"><span data-stu-id="a6e32-111">TargetFramework</span></span>

<span data-ttu-id="a6e32-112">Свойство `TargetFramework` указывает версию целевой платформы для приложения, которая неявно ссылается на [метапакет](../packages.md#metapackages).</span><span class="sxs-lookup"><span data-stu-id="a6e32-112">The `TargetFramework` property specifies the target framework version for the app, which implicitly references a [metapackage](../packages.md#metapackages).</span></span> <span data-ttu-id="a6e32-113">Список допустимых моникеров целевой платформы см. в статье [Целевые платформы в проектах в стиле SDK](../../standard/frameworks.md#supported-target-framework-versions).</span><span class="sxs-lookup"><span data-stu-id="a6e32-113">For a list of valid target framework monikers, see [Target frameworks in SDK-style projects](../../standard/frameworks.md#supported-target-framework-versions).</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>netcoreapp3.1</TargetFramework>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="a6e32-114">Дополнительные сведения см.в статье [Целевые платформы в проектах в стиле SDK](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="a6e32-114">For more information, see [Target frameworks in SDK-style projects](../../standard/frameworks.md).</span></span>

### <a name="targetframeworks"></a><span data-ttu-id="a6e32-115">TargetFrameworks</span><span class="sxs-lookup"><span data-stu-id="a6e32-115">TargetFrameworks</span></span>

<span data-ttu-id="a6e32-116">Используйте свойство `TargetFrameworks`, если приложение должно быть предназначено для нескольких платформ.</span><span class="sxs-lookup"><span data-stu-id="a6e32-116">Use the `TargetFrameworks` property when you want your app to target multiple platforms.</span></span> <span data-ttu-id="a6e32-117">Список допустимых моникеров целевой платформы см. в статье [Целевые платформы в проектах в стиле SDK](../../standard/frameworks.md#supported-target-framework-versions).</span><span class="sxs-lookup"><span data-stu-id="a6e32-117">For a list of valid target framework monikers, see [Target frameworks in SDK-style projects](../../standard/frameworks.md#supported-target-framework-versions).</span></span>

> [!NOTE]
> <span data-ttu-id="a6e32-118">Это свойство игнорируется, если указано свойство `TargetFramework` (в единственном числе).</span><span class="sxs-lookup"><span data-stu-id="a6e32-118">This property is ignored if `TargetFramework` (singular) is specified.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFrameworks>netcoreapp3.1;net462</TargetFrameworks>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="a6e32-119">Дополнительные сведения см.в статье [Целевые платформы в проектах в стиле SDK](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="a6e32-119">For more information, see [Target frameworks in SDK-style projects](../../standard/frameworks.md).</span></span>

### <a name="netstandardimplicitpackageversion"></a><span data-ttu-id="a6e32-120">NetStandardImplicitPackageVersion</span><span class="sxs-lookup"><span data-stu-id="a6e32-120">NetStandardImplicitPackageVersion</span></span>

> [!NOTE]
> <span data-ttu-id="a6e32-121">Это свойство применяется только к проектам, использующим `netstandard1.x`.</span><span class="sxs-lookup"><span data-stu-id="a6e32-121">This property only applies to projects using `netstandard1.x`.</span></span> <span data-ttu-id="a6e32-122">Он не применяется к проектам, использующим `netstandard2.x`.</span><span class="sxs-lookup"><span data-stu-id="a6e32-122">It doesn't apply to projects that use `netstandard2.x`.</span></span>

<span data-ttu-id="a6e32-123">Используйте свойство `NetStandardImplicitPackageVersion`, если требуется указать версию платформы ниже версии [метапакета](../packages.md#metapackages).</span><span class="sxs-lookup"><span data-stu-id="a6e32-123">Use the `NetStandardImplicitPackageVersion` property when you want to specify a framework version that's lower than the [metapackage](../packages.md#metapackages) version.</span></span> <span data-ttu-id="a6e32-124">Файл проекта, приведенный в следующем примере, предназначен для `netstandard1.3`, но использует `NETStandard.Library` версии 1.6.0.</span><span class="sxs-lookup"><span data-stu-id="a6e32-124">The project file in the following example targets `netstandard1.3` but uses the 1.6.0 version of `NETStandard.Library`.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>netstandard1.3</TargetFramework>
    <NetStandardImplicitPackageVersion>1.6.0</NetStandardImplicitPackageVersion>
  </PropertyGroup>
</Project>
```

## <a name="publish-properties"></a><span data-ttu-id="a6e32-125">Параметры публикации</span><span class="sxs-lookup"><span data-stu-id="a6e32-125">Publish properties</span></span>

- [<span data-ttu-id="a6e32-126">RuntimeIdentifier</span><span class="sxs-lookup"><span data-stu-id="a6e32-126">RuntimeIdentifier</span></span>](#runtimeidentifier)
- [<span data-ttu-id="a6e32-127">RuntimeIdentifiers</span><span class="sxs-lookup"><span data-stu-id="a6e32-127">RuntimeIdentifiers</span></span>](#runtimeidentifiers)
- [<span data-ttu-id="a6e32-128">UseAppHost</span><span class="sxs-lookup"><span data-stu-id="a6e32-128">UseAppHost</span></span>](#useapphost)

### <a name="runtimeidentifier"></a><span data-ttu-id="a6e32-129">RuntimeIdentifier</span><span class="sxs-lookup"><span data-stu-id="a6e32-129">RuntimeIdentifier</span></span>

<span data-ttu-id="a6e32-130">Свойство `RuntimeIdentifier` позволяет указать для проекта один [идентификатор среды выполнения (RID)](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="a6e32-130">The `RuntimeIdentifier` property lets you specify a single [runtime identifier (RID)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="a6e32-131">Идентификатор среды выполнения позволяет опубликовать автономное развертывание.</span><span class="sxs-lookup"><span data-stu-id="a6e32-131">The RID enables publishing a self-contained deployment.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <RuntimeIdentifier>ubuntu.16.04-x64</RuntimeIdentifier>
  </PropertyGroup>
</Project>
```

### <a name="runtimeidentifiers"></a><span data-ttu-id="a6e32-132">RuntimeIdentifiers</span><span class="sxs-lookup"><span data-stu-id="a6e32-132">RuntimeIdentifiers</span></span>

<span data-ttu-id="a6e32-133">Свойство `RuntimeIdentifiers` позволяет указать для проекта список [идентификаторов среды выполнения (RID)](../rid-catalog.md) (в качестве разделителя используется точка с запятой).</span><span class="sxs-lookup"><span data-stu-id="a6e32-133">The `RuntimeIdentifiers` property lets you specify a semicolon-delimited list of [runtime identifiers (RIDs)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="a6e32-134">Используйте это свойство, если вам нужна публикация для нескольких сред.</span><span class="sxs-lookup"><span data-stu-id="a6e32-134">Use this property if you need to publish for multiple runtimes.</span></span> <span data-ttu-id="a6e32-135">`RuntimeIdentifiers` используется во время восстановления для обеспечения наличия в графе нужных ресурсов.</span><span class="sxs-lookup"><span data-stu-id="a6e32-135">`RuntimeIdentifiers` is used at restore time to ensure the right assets are in the graph.</span></span>

> [!TIP]
> <span data-ttu-id="a6e32-136">`RuntimeIdentifier` (в единственном числе) может ускорить создание сборок, когда требуется только одна среда выполнения.</span><span class="sxs-lookup"><span data-stu-id="a6e32-136">`RuntimeIdentifier` (singular) can provide faster builds when only a single runtime is required.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <RuntimeIdentifiers>win10-x64;osx.10.11-x64;ubuntu.16.04-x64</RuntimeIdentifiers>
  </PropertyGroup>
</Project>
```

### <a name="useapphost"></a><span data-ttu-id="a6e32-137">UseAppHost</span><span class="sxs-lookup"><span data-stu-id="a6e32-137">UseAppHost</span></span>

<span data-ttu-id="a6e32-138">Свойство `UseAppHost` было представлено в пакете SDK для .NET Core.версии 2.1.400.</span><span class="sxs-lookup"><span data-stu-id="a6e32-138">The `UseAppHost` property was introduced in the 2.1.400 version of the .NET Core SDK.</span></span> <span data-ttu-id="a6e32-139">Оно контролирует создание собственного исполняемого файла для развертывания.</span><span class="sxs-lookup"><span data-stu-id="a6e32-139">It controls whether or not a native executable is created for a deployment.</span></span> <span data-ttu-id="a6e32-140">Этот файл требуется для автономных развертываний.</span><span class="sxs-lookup"><span data-stu-id="a6e32-140">A native executable is required for self-contained deployments.</span></span>

<span data-ttu-id="a6e32-141">В .NET Core 3.0 и более поздних версиях зависимый от платформы исполняемый файл создается по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a6e32-141">In .NET Core 3.0 and later versions, a framework-dependent executable is created by default.</span></span> <span data-ttu-id="a6e32-142">Задайте свойству `UseAppHost` значение `false`, чтобы отключить создание исполняемого файла.</span><span class="sxs-lookup"><span data-stu-id="a6e32-142">Set the `UseAppHost` property to `false` to disable generation of the executable.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <UseAppHost>false</UseAppHost>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="a6e32-143">Дополнительные сведения о развертывании см. в статье [Развертывание приложений .NET Core](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="a6e32-143">For more information about deployment, see [.NET Core application deployment](../deploying/index.md).</span></span>

## <a name="compile-properties"></a><span data-ttu-id="a6e32-144">Свойства компиляции</span><span class="sxs-lookup"><span data-stu-id="a6e32-144">Compile properties</span></span>

### <a name="langversion"></a><span data-ttu-id="a6e32-145">LangVersion</span><span class="sxs-lookup"><span data-stu-id="a6e32-145">LangVersion</span></span>

<span data-ttu-id="a6e32-146">Свойство `LangVersion` позволяет указать конкретную версию языка программирования.</span><span class="sxs-lookup"><span data-stu-id="a6e32-146">The `LangVersion` property lets you specify a specific programming language version.</span></span> <span data-ttu-id="a6e32-147">Например, если требуется доступ к предварительным версиям функций C#, задайте параметру `LangVersion` значение `preview`.</span><span class="sxs-lookup"><span data-stu-id="a6e32-147">For example, if you want access to C# preview features, set `LangVersion` to `preview`.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <LangVersion>preview</LangVersion>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="a6e32-148">Дополнительные сведения см. в статье [Управление версиями языка C#](../../csharp/language-reference/configure-language-version.md#override-a-default).</span><span class="sxs-lookup"><span data-stu-id="a6e32-148">For more information, see [C# language versioning](../../csharp/language-reference/configure-language-version.md#override-a-default).</span></span>

## <a name="nuget-packages"></a><span data-ttu-id="a6e32-149">Пакеты NuGet</span><span class="sxs-lookup"><span data-stu-id="a6e32-149">NuGet packages</span></span>

- [<span data-ttu-id="a6e32-150">PackageReference</span><span class="sxs-lookup"><span data-stu-id="a6e32-150">PackageReference</span></span>](#packagereference)
- [<span data-ttu-id="a6e32-151">AssetTargetFallback</span><span class="sxs-lookup"><span data-stu-id="a6e32-151">AssetTargetFallback</span></span>](#assettargetfallback)

### <a name="packagereference"></a><span data-ttu-id="a6e32-152">PackageReference</span><span class="sxs-lookup"><span data-stu-id="a6e32-152">PackageReference</span></span>

<span data-ttu-id="a6e32-153">Элемент `PackageReference` позволяет указать зависимость NuGet.</span><span class="sxs-lookup"><span data-stu-id="a6e32-153">The `PackageReference` item lets you specify a NuGet dependency.</span></span> <span data-ttu-id="a6e32-154">Например, может потребоваться сослаться на один пакет, а не на [метапакет](../packages.md#metapackages).</span><span class="sxs-lookup"><span data-stu-id="a6e32-154">For example, you may want to reference a single package instead of a [metapackage](../packages.md#metapackages).</span></span> <span data-ttu-id="a6e32-155">Атрибут `Include` указывает идентификатор пакета.</span><span class="sxs-lookup"><span data-stu-id="a6e32-155">The `Include` attribute specifies the package ID.</span></span> <span data-ttu-id="a6e32-156">Фрагмент файла проекта в следующем примере ссылается на пакет [System.Runtime](https://www.nuget.org/packages/System.Runtime/).</span><span class="sxs-lookup"><span data-stu-id="a6e32-156">The project file snippet in the following example references the [System.Runtime](https://www.nuget.org/packages/System.Runtime/) package.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  ...
  <ItemGroup>
    <PackageReference Include="System.Runtime" Version="4.3.0" />
  </ItemGroup>
</Project>
```

<span data-ttu-id="a6e32-157">Дополнительные сведения см. в статье [Ссылки на пакеты в файлах проекта](/nuget/consume-packages/package-references-in-project-files).</span><span class="sxs-lookup"><span data-stu-id="a6e32-157">For more information, see [Package references in project files](/nuget/consume-packages/package-references-in-project-files).</span></span>

### <a name="assettargetfallback"></a><span data-ttu-id="a6e32-158">AssetTargetFallback</span><span class="sxs-lookup"><span data-stu-id="a6e32-158">AssetTargetFallback</span></span>

<span data-ttu-id="a6e32-159">Свойство `AssetTargetFallback` позволяет указать дополнительные совместимые версии платформы для проектов, на которые ссылается ваш проект, и пакеты NuGet, используемые в проекте.</span><span class="sxs-lookup"><span data-stu-id="a6e32-159">The `AssetTargetFallback` property lets you specify additional compatible framework versions for projects that your project references and NuGet packages that your project consumes.</span></span> <span data-ttu-id="a6e32-160">Например, если вы указали зависимость пакета с помощью `PackageReference`, но в этом пакете нет ресурсов, совместимых с `TargetFramework` вашего проекта, тогда пригодится свойство `AssetTargetFallback`.</span><span class="sxs-lookup"><span data-stu-id="a6e32-160">For example, if you specify a package dependency using `PackageReference` but that package doesn't contain assets that are compatible with your projects's `TargetFramework`, the `AssetTargetFallback` property comes into play.</span></span> <span data-ttu-id="a6e32-161">Совместимость пакета, на который указывает ссылка, повторно проверяется с помощью каждой целевой платформы, указанной в свойстве `AssetTargetFallback`.</span><span class="sxs-lookup"><span data-stu-id="a6e32-161">The compatibility of the referenced package is rechecked using each target framework that's specified in `AssetTargetFallback`.</span></span>

<span data-ttu-id="a6e32-162">В качестве значения свойства `AssetTargetFallback` можно задать одну [версию целевой платформы](../../standard/frameworks.md#supported-target-framework-versions) или несколько.</span><span class="sxs-lookup"><span data-stu-id="a6e32-162">You can set the `AssetTargetFallback` property to one or more [target framework versions](../../standard/frameworks.md#supported-target-framework-versions).</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  ...
  <PropertyGroup>
    <AssetTargetFallback>net461</AssetTargetFallback>
  </PropertyGroup>
</Project>
```

### <a name="pack-and-restore-targets"></a><span data-ttu-id="a6e32-163">Целевые объекты pack и restore</span><span class="sxs-lookup"><span data-stu-id="a6e32-163">Pack and restore targets</span></span>

<span data-ttu-id="a6e32-164">В MSBuild 15.1 появились целевые объекты `pack` и `restore` для создания и восстановления пакетов NuGet в составе сборки.</span><span class="sxs-lookup"><span data-stu-id="a6e32-164">MSBuild 15.1 introduced `pack` and `restore` targets for creating and restoring NuGet packages as part of a build.</span></span> <span data-ttu-id="a6e32-165">Сведения о свойствах MSBuild для этих целевых объектов, включая `PackageTargetFallback`, см. в статье [Объекты pack и restore NuGet в качестве целевых объектов MSBuild](/nuget/reference/msbuild-targets).</span><span class="sxs-lookup"><span data-stu-id="a6e32-165">For information about the MSBuild properties for these targets, including `PackageTargetFallback`, see [NuGet pack and restore as MSBuild targets](/nuget/reference/msbuild-targets).</span></span>

## <a name="see-also"></a><span data-ttu-id="a6e32-166">См. также</span><span class="sxs-lookup"><span data-stu-id="a6e32-166">See also</span></span>

- [<span data-ttu-id="a6e32-167">Справочник по схеме MSBuild</span><span class="sxs-lookup"><span data-stu-id="a6e32-167">MSBuild schema reference</span></span>](/visualstudio/msbuild/msbuild-project-file-schema-reference)
- [<span data-ttu-id="a6e32-168">Общие свойства MSBuild</span><span class="sxs-lookup"><span data-stu-id="a6e32-168">Common MSBuild properties</span></span>](/visualstudio/msbuild/common-msbuild-project-properties)
- [<span data-ttu-id="a6e32-169">Свойства MSBuild для целевого объекта pack NuGet</span><span class="sxs-lookup"><span data-stu-id="a6e32-169">MSBuild properties for NuGet pack</span></span>](/nuget/reference/msbuild-targets#pack-target)
- [<span data-ttu-id="a6e32-170">Свойства MSBuild для целевого объекта restore NuGet</span><span class="sxs-lookup"><span data-stu-id="a6e32-170">MSBuild properties for NuGet restore</span></span>](/nuget/reference/msbuild-targets#restore-properties)
- [<span data-ttu-id="a6e32-171">Настройка сборки</span><span class="sxs-lookup"><span data-stu-id="a6e32-171">Customize a build</span></span>](/visualstudio/msbuild/customize-your-build)
