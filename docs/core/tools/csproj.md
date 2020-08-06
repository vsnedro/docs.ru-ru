---
title: Дополнения к формату CSPROJ для .NET Core
description: Различия между существующими файлами и файлами CSPROJ .NET Core
ms.date: 04/08/2019
ms.openlocfilehash: a0cbead27e52af3114d9c44fd19c966e665a2850
ms.sourcegitcommit: 32f0d6f4c01ddc6ca78767c3a30e3305f8cd032c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2020
ms.locfileid: "87427012"
---
# <a name="additions-to-the-csproj-format-for-net-core"></a><span data-ttu-id="47834-103">Дополнения к формату CSPROJ для .NET Core</span><span class="sxs-lookup"><span data-stu-id="47834-103">Additions to the csproj format for .NET Core</span></span>

<span data-ttu-id="47834-104">В этом документе перечислены изменения, внесенные в файлы проекта при перемещении из *project.json* в *CSPROJ* и [MSBuild](https://github.com/Microsoft/MSBuild).</span><span class="sxs-lookup"><span data-stu-id="47834-104">This document outlines the changes that were added to the project files as part of the move from *project.json* to *csproj* and [MSBuild](https://github.com/Microsoft/MSBuild).</span></span> <span data-ttu-id="47834-105">Дополнительную информацию, которая касается синтаксиса файла проекта в общем, и справку см. в документации по [файлу проекта MSBuild](/visualstudio/msbuild/msbuild-project-file-schema-reference).</span><span class="sxs-lookup"><span data-stu-id="47834-105">For more information about general project file syntax and reference, see [the MSBuild project file](/visualstudio/msbuild/msbuild-project-file-schema-reference) documentation.</span></span>

## <a name="implicit-package-references"></a><span data-ttu-id="47834-106">Неявные ссылки на пакет</span><span class="sxs-lookup"><span data-stu-id="47834-106">Implicit package references</span></span>

<span data-ttu-id="47834-107">Теперь неявные ссылки на метапакеты указываются в зависимости от целевой платформы, указанной в свойстве `<TargetFramework>` или `<TargetFrameworks>` файла проекта.</span><span class="sxs-lookup"><span data-stu-id="47834-107">Metapackages are implicitly referenced based on the target framework(s) specified in the `<TargetFramework>` or `<TargetFrameworks>` property of your project file.</span></span> <span data-ttu-id="47834-108">Если свойство `<TargetFramework>` указано, свойство `<TargetFrameworks>` игнорируется независимо от порядка.</span><span class="sxs-lookup"><span data-stu-id="47834-108">`<TargetFrameworks>` is ignored if `<TargetFramework>` is specified, independent of order.</span></span>

```xml
 <PropertyGroup>
   <TargetFramework>netcoreapp2.1</TargetFramework>
 </PropertyGroup>
 ```

 ```xml
 <PropertyGroup>
   <TargetFrameworks>netcoreapp2.1;net462</TargetFrameworks>
 </PropertyGroup>
 ```

### <a name="recommendations"></a><span data-ttu-id="47834-109">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="47834-109">Recommendations</span></span>

<span data-ttu-id="47834-110">Так как теперь указываются неявные ссылки на метапакеты `Microsoft.NETCore.App` или `NETStandard.Library`, следует учитывать приведенные ниже рекомендации:</span><span class="sxs-lookup"><span data-stu-id="47834-110">Since `Microsoft.NETCore.App` or `NETStandard.Library` metapackages are implicitly referenced, the following are our recommended best practices:</span></span>

- <span data-ttu-id="47834-111">Ориентируясь на .NET Core или .NET Standard, никогда не указывайте явную ссылку на метапакеты `Microsoft.NETCore.App` или `NETStandard.Library` через элемент `<PackageReference>` в файле проекта.</span><span class="sxs-lookup"><span data-stu-id="47834-111">When targeting .NET Core or .NET Standard, never have an explicit reference to the `Microsoft.NETCore.App` or `NETStandard.Library` metapackages via a `<PackageReference>` item in your project file.</span></span>
- <span data-ttu-id="47834-112">Если при ориентации на .NET Core нужна определенная версия среды выполнения, вместо ссылки на метапакет следует использовать свойство `<RuntimeFrameworkVersion>` в проекте (например, `1.0.4`).</span><span class="sxs-lookup"><span data-stu-id="47834-112">If you need a specific version of the runtime when targeting .NET Core, you should use the `<RuntimeFrameworkVersion>` property in your project (for example, `1.0.4`) instead of referencing the metapackage.</span></span>
  - <span data-ttu-id="47834-113">Это может произойти, например, когда вы используете [автономные развертывания](../deploying/index.md#publish-self-contained) и нуждаетесь в определенной версии исправления 1.0.0 LTS для среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="47834-113">This might happen if you are using [self-contained deployments](../deploying/index.md#publish-self-contained) and you need a specific patch version of 1.0.0 LTS runtime, for example.</span></span>
- <span data-ttu-id="47834-114">Если при ориентации на .NET Standard вам нужна конкретная версия метапакета `NETStandard.Library`, можно использовать свойство `<NetStandardImplicitPackageVersion>` и установить требуемую версию.</span><span class="sxs-lookup"><span data-stu-id="47834-114">If you need a specific version of the `NETStandard.Library` metapackage when targeting .NET Standard, you can use the `<NetStandardImplicitPackageVersion>` property and set the version you need.</span></span>
- <span data-ttu-id="47834-115">Не добавляйте и не обновляйте ссылки на метапакет `Microsoft.NETCore.App` или `NETStandard.Library` явным образом в проектах .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="47834-115">Don't explicitly add or update references to either the `Microsoft.NETCore.App` or `NETStandard.Library` metapackage in .NET Framework projects.</span></span> <span data-ttu-id="47834-116">Если при использовании пакета NuGet на основе .NET Standard требуется любая версия `NETStandard.Library`, NuGet автоматически устанавливает ее.</span><span class="sxs-lookup"><span data-stu-id="47834-116">If any version of `NETStandard.Library` is needed when using a .NET Standard-based NuGet package, NuGet automatically installs that version.</span></span>

## <a name="implicit-version-for-some-package-references"></a><span data-ttu-id="47834-117">Неявное указание версий для некоторых ссылок на пакет</span><span class="sxs-lookup"><span data-stu-id="47834-117">Implicit version for some package references</span></span>

<span data-ttu-id="47834-118">В большинстве случаев при использовании [`<PackageReference>`](#packagereference) требуется указать атрибут `Version`, чтобы определить используемую версию пакета NuGet.</span><span class="sxs-lookup"><span data-stu-id="47834-118">Most usages of [`<PackageReference>`](#packagereference) require setting the `Version` attribute to specify the NuGet package version to be used.</span></span> <span data-ttu-id="47834-119">Атрибут необязательно указывать, если используется .NET Core 2.1 или 2.2 со ссылкой на [Microsoft.AspNetCore.App](/aspnet/core/fundamentals/metapackage-app) или [Microsoft.AspNetCore.All](/aspnet/core/fundamentals/metapackage).</span><span class="sxs-lookup"><span data-stu-id="47834-119">When using .NET Core 2.1 or 2.2 and referencing [Microsoft.AspNetCore.App](/aspnet/core/fundamentals/metapackage-app) or [Microsoft.AspNetCore.All](/aspnet/core/fundamentals/metapackage), however, the  attribute is unnecessary.</span></span> <span data-ttu-id="47834-120">Пакет SDK для .NET Core позволяет автоматически выбрать версию этих пакетов, которая должна использоваться.</span><span class="sxs-lookup"><span data-stu-id="47834-120">The .NET Core SDK can automatically select the version of these packages that should be used.</span></span>

### <a name="recommendation"></a><span data-ttu-id="47834-121">Рекомендация</span><span class="sxs-lookup"><span data-stu-id="47834-121">Recommendation</span></span>

<span data-ttu-id="47834-122">Если вы ссылаетесь на пакеты `Microsoft.AspNetCore.App` или `Microsoft.AspNetCore.All`, не указывайте их версии.</span><span class="sxs-lookup"><span data-stu-id="47834-122">When referencing the `Microsoft.AspNetCore.App` or `Microsoft.AspNetCore.All` packages, do not specify their version.</span></span> <span data-ttu-id="47834-123">Если версия указана, пакет SDK может выдать предупреждение NETSDK1071.</span><span class="sxs-lookup"><span data-stu-id="47834-123">If a version is specified, the SDK may produce warning NETSDK1071.</span></span> <span data-ttu-id="47834-124">Чтобы устранить это предупреждение, удалите версию пакета, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="47834-124">To fix this warning, remove the package version like in the following example:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.AspNetCore.App" />
</ItemGroup>
```

> <span data-ttu-id="47834-125">Известная проблема. Пакет SDK для .NET Core 2.1 поддерживал только такой синтаксис, если в проекте также использовался Microsoft.NET.Sdk.Web.</span><span class="sxs-lookup"><span data-stu-id="47834-125">Known issue: the .NET Core 2.1 SDK only supported this syntax when the project also uses Microsoft.NET.Sdk.Web.</span></span> <span data-ttu-id="47834-126">Эта проблема устранена в пакете SDK для .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="47834-126">This is resolved in the .NET Core 2.2 SDK.</span></span>

<span data-ttu-id="47834-127">Эти ссылки на метапакеты ASP.NET Core немного отличаются от ссылок на обычные пакеты NuGet.</span><span class="sxs-lookup"><span data-stu-id="47834-127">These references to ASP.NET Core metapackages have a slightly different behavior from most normal NuGet packages.</span></span> <span data-ttu-id="47834-128">[Зависящие от платформы развертывания](../deploying/index.md#publish-runtime-dependent) приложений, для которых используются эти метапакеты, автоматически получают все преимущества общей платформы ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="47834-128">[Framework-dependent deployments](../deploying/index.md#publish-runtime-dependent) of applications that use these metapackages automatically take advantage of the ASP.NET Core shared framework.</span></span> <span data-ttu-id="47834-129">Если используются метапакеты, с приложением **не** развертываются ресурсы из указанных по ссылке пакетов NuGet ASP.NET Core — общая платформа ASP.NET Core уже содержит эти ресурсы.</span><span class="sxs-lookup"><span data-stu-id="47834-129">When you use the metapackages, **no** assets from the referenced ASP.NET Core NuGet packages are deployed with the application—the ASP.NET Core shared framework contains these assets.</span></span> <span data-ttu-id="47834-130">Для ускорения запуска приложения ресурсы в общей платформе предварительно оптимизируются.</span><span class="sxs-lookup"><span data-stu-id="47834-130">The assets in the shared framework are optimized for the target platform to improve application startup time.</span></span> <span data-ttu-id="47834-131">Дополнительные сведения об общей платформе см. в статье [Упаковка дистрибутивов .NET Core](../distribution-packaging.md).</span><span class="sxs-lookup"><span data-stu-id="47834-131">For more information about shared framework, see [.NET Core distribution packaging](../distribution-packaging.md).</span></span>

<span data-ttu-id="47834-132">Если версия *указана*, она рассматривается как *минимальная* версия общей платформы ASP.NET Core для зависимых от платформы развертываний, а также как *точная* версия для автономных развертываний.</span><span class="sxs-lookup"><span data-stu-id="47834-132">If a version *is* specified, it's treated as the *minimum* version of ASP.NET Core shared framework for framework-dependent deployments and as an *exact* version for self-contained deployments.</span></span> <span data-ttu-id="47834-133">Это может привести к следующим результатам:</span><span class="sxs-lookup"><span data-stu-id="47834-133">This can have the following consequences:</span></span>

- <span data-ttu-id="47834-134">Если на сервере установлена более ранняя версия ASP.NET Core, чем указанная в PackageReference, процесс .NET Core не удастся запустить.</span><span class="sxs-lookup"><span data-stu-id="47834-134">If the version of ASP.NET Core installed on the server is less than the version specified on the PackageReference, the .NET Core process fails to launch.</span></span> <span data-ttu-id="47834-135">Обновления метапакета часто доступны на сайте NuGet.org раньше, чем в средах размещения, таких как Azure.</span><span class="sxs-lookup"><span data-stu-id="47834-135">Updates to the metapackage are often available on NuGet.org before updates have been made available in hosting environments such as Azure.</span></span> <span data-ttu-id="47834-136">Обновление версии PackageReference в ASP.NET Core может привести к сбою развернутого приложения.</span><span class="sxs-lookup"><span data-stu-id="47834-136">Updating the version on the PackageReference to ASP.NET Core could cause a deployed application to fail.</span></span>
- <span data-ttu-id="47834-137">Если приложение развертывается как [автономное развертывание](../deploying/index.md#publish-self-contained), оно не может содержать последние обновления системы безопасности для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="47834-137">If the application is deployed as a [self-contained deployment](../deploying/index.md#publish-self-contained), the application may not contain the latest security updates to .NET Core.</span></span> <span data-ttu-id="47834-138">Если версия не указана, пакет SDK может автоматически включить последнюю версию ASP.NET Core в автономное развертывание.</span><span class="sxs-lookup"><span data-stu-id="47834-138">When a version isn't specified, the SDK can automatically include the newest version of ASP.NET Core in the self-contained deployment.</span></span>

## <a name="default-compilation-includes-in-net-core-projects"></a><span data-ttu-id="47834-139">Компиляция по умолчанию, включенная в проекты .NET Core</span><span class="sxs-lookup"><span data-stu-id="47834-139">Default compilation includes in .NET Core projects</span></span>

<span data-ttu-id="47834-140">В рамках перехода на формат *CSPROJ* в последних версиях пакета SDK мы перенесли включения и исключения по умолчанию для элементов Compile и внедренные ресурсы в файлы свойств пакета SDK.</span><span class="sxs-lookup"><span data-stu-id="47834-140">With the move to the *csproj* format in the latest SDK versions, we've moved the default includes and excludes for compile items and embedded resources to the SDK properties files.</span></span> <span data-ttu-id="47834-141">Это означает, что вам больше не нужно указывать эти элементы в файле проекта.</span><span class="sxs-lookup"><span data-stu-id="47834-141">This means that you no longer need to specify these items in your project file.</span></span>

<span data-ttu-id="47834-142">Основной причиной этого является стремление очистить ваш файл проекта от всего лишнего.</span><span class="sxs-lookup"><span data-stu-id="47834-142">The main reason for doing this is to reduce the clutter in your project file.</span></span> <span data-ttu-id="47834-143">Значения по умолчанию в пакете SDK должны охватывать наиболее распространенные варианты использования, поэтому нет необходимости повторять их в каждом создаваемом проекте.</span><span class="sxs-lookup"><span data-stu-id="47834-143">The defaults that are present in the SDK should cover most common use cases, so there is no need to repeat them in every project that you create.</span></span> <span data-ttu-id="47834-144">Это позволяет уменьшить файлы проекта и гораздо проще читать их, а также вносить правки вручную.</span><span class="sxs-lookup"><span data-stu-id="47834-144">This leads to smaller project files that are much easier to understand as well as edit by hand, if needed.</span></span>

<span data-ttu-id="47834-145">Следующая таблица показывает, какой элемент и какие [стандартные маски](https://en.wikipedia.org/wiki/Glob_(programming)) включены и исключены в пакете SDK:</span><span class="sxs-lookup"><span data-stu-id="47834-145">The following table shows which element and which [globs](https://en.wikipedia.org/wiki/Glob_(programming)) are both included and excluded in the SDK:</span></span>

| <span data-ttu-id="47834-146">Элемент</span><span class="sxs-lookup"><span data-stu-id="47834-146">Element</span></span>           | <span data-ttu-id="47834-147">Стандартная маска включения</span><span class="sxs-lookup"><span data-stu-id="47834-147">Include glob</span></span>                              | <span data-ttu-id="47834-148">Стандартная маска исключения</span><span class="sxs-lookup"><span data-stu-id="47834-148">Exclude glob</span></span>                                                  | <span data-ttu-id="47834-149">Стандартная маска удаления</span><span class="sxs-lookup"><span data-stu-id="47834-149">Remove glob</span></span>              |
|-------------------|-------------------------------------------|---------------------------------------------------------------|----------------------------|
| <span data-ttu-id="47834-150">Компилятор</span><span class="sxs-lookup"><span data-stu-id="47834-150">Compile</span></span>           | <span data-ttu-id="47834-151">\*\*/\*.cs (или другие расширения языка)</span><span class="sxs-lookup"><span data-stu-id="47834-151">\*\*/\*.cs (or other language extensions)</span></span> | <span data-ttu-id="47834-152">\*\*/\*.user;  \*\*/\*.\*proj;  \*\*/\*.sln;  \*\*/\*.vssscc</span><span class="sxs-lookup"><span data-stu-id="47834-152">\*\*/\*.user;  \*\*/\*.\*proj;  \*\*/\*.sln;  \*\*/\*.vssscc</span></span>  | <span data-ttu-id="47834-153">Н/Д</span><span class="sxs-lookup"><span data-stu-id="47834-153">N/A</span></span>                      |
| <span data-ttu-id="47834-154">ВнедренныйРесурс</span><span class="sxs-lookup"><span data-stu-id="47834-154">EmbeddedResource</span></span>  | <span data-ttu-id="47834-155">\*\*/\*.resx</span><span class="sxs-lookup"><span data-stu-id="47834-155">\*\*/\*.resx</span></span>                              | <span data-ttu-id="47834-156">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span><span class="sxs-lookup"><span data-stu-id="47834-156">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span></span>     | <span data-ttu-id="47834-157">Н/Д</span><span class="sxs-lookup"><span data-stu-id="47834-157">N/A</span></span>                      |
| <span data-ttu-id="47834-158">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="47834-158">None</span></span>              | \*\*/\*                                   | <span data-ttu-id="47834-159">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span><span class="sxs-lookup"><span data-stu-id="47834-159">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span></span>     | <span data-ttu-id="47834-160">\*\*/\*.cs; \*\*/\*.resx</span><span class="sxs-lookup"><span data-stu-id="47834-160">\*\*/\*.cs; \*\*/\*.resx</span></span>   |

> [!NOTE]
> <span data-ttu-id="47834-161">**Стандартная маска исключения** всегда исключает папки `./bin` и `./obj`, которые представлены свойствами MSBuild `$(BaseOutputPath)` и `$(BaseIntermediateOutputPath)` соответственно.</span><span class="sxs-lookup"><span data-stu-id="47834-161">**Exclude glob** always excludes the `./bin` and `./obj` folders, which are represented by the `$(BaseOutputPath)` and `$(BaseIntermediateOutputPath)` MSBuild properties, respectively.</span></span> <span data-ttu-id="47834-162">В целом все исключения представляются свойством `$(DefaultItemExcludes)`.</span><span class="sxs-lookup"><span data-stu-id="47834-162">As a whole, all excludes are represented by `$(DefaultItemExcludes)`.</span></span>

<span data-ttu-id="47834-163">Если в вашем проекте имеются стандартные маски и вы пытаетесь выполнить его сборку с помощью новейшего пакета SDK, появится следующая ошибка:</span><span class="sxs-lookup"><span data-stu-id="47834-163">If you have globs in your project and you try to build it using the newest SDK, you'll get the following error:</span></span>

> <span data-ttu-id="47834-164">Duplicate Compile items were included.</span><span class="sxs-lookup"><span data-stu-id="47834-164">Duplicate Compile items were included.</span></span> <span data-ttu-id="47834-165">The .NET SDK includes Compile items from your project directory by default.</span><span class="sxs-lookup"><span data-stu-id="47834-165">The .NET SDK includes Compile items from your project directory by default.</span></span> <span data-ttu-id="47834-166">You can either remove these items from your project file, or set the 'EnableDefaultCompileItems' property to 'false' if you want to explicitly include them in your project file. (Включены повторяющиеся элементы Compile. По умолчанию пакет SDK для .NET включает элементы Compile из каталога проекта. Можно удалить эти элементы из файла проекта или задать для свойства "EnableDefaultCompileItems" значение "false", чтобы явно включить их в файл проекта.)</span><span class="sxs-lookup"><span data-stu-id="47834-166">You can either remove these items from your project file, or set the 'EnableDefaultCompileItems' property to 'false' if you want to explicitly include them in your project file.</span></span>

<span data-ttu-id="47834-167">Чтобы обойти эту ошибку, можно либо удалить явные элементы `Compile`, которые соответствуют указанным в предыдущей таблице, либо установить для свойства `<EnableDefaultCompileItems>` значение `false`, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="47834-167">In order to get around this error, you can either remove the explicit `Compile` items that match the ones listed on the previous table, or you can set the `<EnableDefaultCompileItems>` property to `false`, like this:</span></span>

```xml
<PropertyGroup>
    <EnableDefaultCompileItems>false</EnableDefaultCompileItems>
</PropertyGroup>
```

<span data-ttu-id="47834-168">Указание значения `false` для этого свойства отключает неявное включение, в результате чего возвращается поведение для предыдущих пакетов SDK, где требовалось задавать стандартные маски по умолчанию в проекте.</span><span class="sxs-lookup"><span data-stu-id="47834-168">Setting this property to `false` will disable implicit inclusion, reverting to the behavior of previous SDKs where you had to specify the default globs in your project.</span></span>

<span data-ttu-id="47834-169">Это изменение не затрагивает основные механизмы других включений.</span><span class="sxs-lookup"><span data-stu-id="47834-169">This change does not modify the main mechanics of other includes.</span></span> <span data-ttu-id="47834-170">Но если вы хотите указать, например, отдельные файлы для публикации вместе со своим приложением, для этого можно по-прежнему использовать привычные механизмы в *CSPROJ* (например, элемент `<Content>`).</span><span class="sxs-lookup"><span data-stu-id="47834-170">However, if you wish to specify, for example, some files to get published with your app, you can still use the known mechanisms in *csproj* for that (for example, the `<Content>` element).</span></span>

<span data-ttu-id="47834-171">`<EnableDefaultCompileItems>` отключает только стандартные маски `Compile`, не затрагивая все остальные, например неявную стандартную маску `None`, которая также применяется к элементам \*.cs.</span><span class="sxs-lookup"><span data-stu-id="47834-171">`<EnableDefaultCompileItems>` only disables `Compile` globs but doesn't affect other globs, like the implicit `None` glob, which also applies to \*.cs items.</span></span> <span data-ttu-id="47834-172">Из-за этого **обозреватель решений** продолжит показывать элементы \*.cs как часть проекта, включенную в виде элементов `None`.</span><span class="sxs-lookup"><span data-stu-id="47834-172">Because of that, **Solution Explorer** will continue show \*.cs items as part of the project, included as `None` items.</span></span> <span data-ttu-id="47834-173">Аналогичным образом, можно задать `<EnableDefaultNoneItems>` как false для отключения неявной стандартной маски `None`:</span><span class="sxs-lookup"><span data-stu-id="47834-173">In a similar way, you can set `<EnableDefaultNoneItems>` to false to disable the implicit `None` glob, like this:</span></span>

```xml
<PropertyGroup>
    <EnableDefaultNoneItems>false</EnableDefaultNoneItems>
</PropertyGroup>
```

<span data-ttu-id="47834-174">Чтобы отключить **все неявные стандартные маски**, можно задать для свойства `<EnableDefaultItems>` значение `false`, как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="47834-174">To disable **all implicit globs**, you can set the `<EnableDefaultItems>` property to `false` as in the following example:</span></span>

```xml
<PropertyGroup>
    <EnableDefaultItems>false</EnableDefaultItems>
</PropertyGroup>
```

## <a name="how-to-see-the-whole-project-as-msbuild-sees-it"></a><span data-ttu-id="47834-175">Как просмотреть весь проект в представлении MSBuild</span><span class="sxs-lookup"><span data-stu-id="47834-175">How to see the whole project as MSBuild sees it</span></span>

<span data-ttu-id="47834-176">Хотя эти изменения csproj значительно упростили файлы проекта, возможно, вы захотите просмотреть полностью развернутый пакет в представлении MSBuild после включения пакета SDK и его целевых объектов.</span><span class="sxs-lookup"><span data-stu-id="47834-176">While those csproj changes greatly simplify project files, you might want to see the fully expanded project as MSBuild sees it once the SDK and its targets are included.</span></span> <span data-ttu-id="47834-177">Выполните предварительную обработку проекта, [включив](/visualstudio/msbuild/msbuild-command-line-reference#preprocess) в команду [`dotnet msbuild`](dotnet-msbuild.md) параметр `/pp`. Это позволит просмотреть сведения об импортированных файлах, их источниках, вкладе в сборку без фактического создания проекта:</span><span class="sxs-lookup"><span data-stu-id="47834-177">Preprocess the project with [the `/pp` switch](/visualstudio/msbuild/msbuild-command-line-reference#preprocess) of the [`dotnet msbuild`](dotnet-msbuild.md) command, which shows which files are imported, their sources, and their contributions to the build without actually building the project:</span></span>

`dotnet msbuild -pp:fullproject.xml`

<span data-ttu-id="47834-178">Если проект имеет несколько требуемых версий .NET Framework, результаты выполнения команды должны касаться только одной из них. Эту версию следует указать в качестве свойства MSBuild:</span><span class="sxs-lookup"><span data-stu-id="47834-178">If the project has multiple target frameworks, the results of the command should be focused on only one of them by specifying it as an MSBuild property:</span></span>

`dotnet msbuild -p:TargetFramework=netcoreapp2.0 -pp:fullproject.xml`

## <a name="additions"></a><span data-ttu-id="47834-179">Добавления</span><span class="sxs-lookup"><span data-stu-id="47834-179">Additions</span></span>

### <a name="sdk-attribute"></a><span data-ttu-id="47834-180">Атрибут Sdk</span><span class="sxs-lookup"><span data-stu-id="47834-180">Sdk attribute</span></span>

<span data-ttu-id="47834-181">Корневой элемент `<Project>` файла *CSPROJ* имеет новый атрибут `Sdk`.</span><span class="sxs-lookup"><span data-stu-id="47834-181">The root `<Project>` element of the *.csproj* file has a new attribute called `Sdk`.</span></span> <span data-ttu-id="47834-182">`Sdk` определяет, какой пакет SDK будет использоваться проектом.</span><span class="sxs-lookup"><span data-stu-id="47834-182">`Sdk` specifies which SDK will be used by the project.</span></span> <span data-ttu-id="47834-183">Пакет SDK, согласно описанию в [документе о слоях](cli-msbuild-architecture.md), является набором [задач](/visualstudio/msbuild/msbuild-tasks) и [целевых объектов](/visualstudio/msbuild/msbuild-targets) MSBuild, способным выполнять сборку кода .NET Core.</span><span class="sxs-lookup"><span data-stu-id="47834-183">The SDK, as the [layering document](cli-msbuild-architecture.md) describes, is a set of MSBuild [tasks](/visualstudio/msbuild/msbuild-tasks) and [targets](/visualstudio/msbuild/msbuild-targets) that can build .NET Core code.</span></span> <span data-ttu-id="47834-184">Для .NET Core доступны следующие пакеты SDK:</span><span class="sxs-lookup"><span data-stu-id="47834-184">The following SDKs are available for .NET Core:</span></span>

1. <span data-ttu-id="47834-185">пакет SDK для .NET Core с идентификатором `Microsoft.NET.Sdk`;</span><span class="sxs-lookup"><span data-stu-id="47834-185">The .NET Core SDK with the ID of `Microsoft.NET.Sdk`</span></span>
2. <span data-ttu-id="47834-186">веб-пакет SDK для .NET Core с идентификатором `Microsoft.NET.Sdk.Web`.</span><span class="sxs-lookup"><span data-stu-id="47834-186">The .NET Core web SDK with the ID of `Microsoft.NET.Sdk.Web`</span></span>
3. <span data-ttu-id="47834-187">пакет SDK для библиотеки классов Razor для .NET Core с идентификатором `Microsoft.NET.Sdk.Razor`.</span><span class="sxs-lookup"><span data-stu-id="47834-187">The .NET Core Razor Class Library SDK with the ID of `Microsoft.NET.Sdk.Razor`</span></span>
4. <span data-ttu-id="47834-188">Служба рабочей роли .NET Core с идентификатором `Microsoft.NET.Sdk.Worker` (с версии .NET Core 3.0)</span><span class="sxs-lookup"><span data-stu-id="47834-188">The .NET Core Worker Service with the ID of `Microsoft.NET.Sdk.Worker` (since .NET Core 3.0)</span></span>
5. <span data-ttu-id="47834-189">.NET Core WinForms и WPF с идентификатором `Microsoft.NET.Sdk.WindowsDesktop` (с версии .NET Core 3.0)</span><span class="sxs-lookup"><span data-stu-id="47834-189">The .NET Core WinForms and WPF with the ID of `Microsoft.NET.Sdk.WindowsDesktop` (since .NET Core 3.0)</span></span>

<span data-ttu-id="47834-190">Чтобы использовать инструменты и выполнять сборку кода .NET Core, в качестве значения атрибута `Sdk` в элементе `<Project>` нужно задать один из этих идентификаторов.</span><span class="sxs-lookup"><span data-stu-id="47834-190">You need to have the `Sdk` attribute set to one of those IDs on the `<Project>` element in order to use the .NET Core tools and build your code.</span></span>

### <a name="packagereference"></a><span data-ttu-id="47834-191">PackageReference</span><span class="sxs-lookup"><span data-stu-id="47834-191">PackageReference</span></span>

<span data-ttu-id="47834-192">Элемент `<PackageReference>` указывает [зависимость NuGet в проекте](/nuget/consume-packages/package-references-in-project-files).</span><span class="sxs-lookup"><span data-stu-id="47834-192">A `<PackageReference>` item element specifies a [NuGet dependency in the project](/nuget/consume-packages/package-references-in-project-files).</span></span> <span data-ttu-id="47834-193">Атрибут `Include` указывает идентификатор пакета.</span><span class="sxs-lookup"><span data-stu-id="47834-193">The `Include` attribute specifies the package ID.</span></span>

```xml
<PackageReference Include="package-id" Version="" PrivateAssets="" IncludeAssets="" ExcludeAssets="" />
```

#### <a name="version"></a><span data-ttu-id="47834-194">Version</span><span class="sxs-lookup"><span data-stu-id="47834-194">Version</span></span>

<span data-ttu-id="47834-195">Обязательный атрибут `Version` указывает версию пакета для восстановления.</span><span class="sxs-lookup"><span data-stu-id="47834-195">The required `Version` attribute specifies the version of the package to restore.</span></span> <span data-ttu-id="47834-196">Этот атрибут подчиняется правилам схемы [диапазона версий NuGet](/nuget/concepts/package-versioning#version-ranges).</span><span class="sxs-lookup"><span data-stu-id="47834-196">The attribute respects the rules of the [NuGet version range](/nuget/concepts/package-versioning#version-ranges) scheme.</span></span> <span data-ttu-id="47834-197">По умолчанию выбирается минимальная из заданных версий (включительно).</span><span class="sxs-lookup"><span data-stu-id="47834-197">The default behavior is a minimum version, inclusive match.</span></span> <span data-ttu-id="47834-198">Например, если указать `Version="1.2.3"`, это будет эквивалентно нотации NuGet `[1.2.3, )` и означает, что при разрешении пакет будет иметь версию 1.2.3, если она доступна, или более высокую, если нет.</span><span class="sxs-lookup"><span data-stu-id="47834-198">For example, specifying `Version="1.2.3"` is equivalent to NuGet notation `[1.2.3, )` and means the resolved package will have the version 1.2.3 if available or greater otherwise.</span></span>

#### <a name="includeassets-excludeassets-and-privateassets"></a><span data-ttu-id="47834-199">IncludeAssets, ExcludeAssets и PrivateAssets</span><span class="sxs-lookup"><span data-stu-id="47834-199">IncludeAssets, ExcludeAssets, and PrivateAssets</span></span>

<span data-ttu-id="47834-200">Атрибут `IncludeAssets` указывает, какие ресурсы пакета, указанные `<PackageReference>`, следует использовать.</span><span class="sxs-lookup"><span data-stu-id="47834-200">`IncludeAssets` attribute specifies which assets belonging to the package specified by `<PackageReference>` should be consumed.</span></span> <span data-ttu-id="47834-201">По умолчанию включаются все ресурсы пакета.</span><span class="sxs-lookup"><span data-stu-id="47834-201">By default, all package assets are included.</span></span>

<span data-ttu-id="47834-202">Атрибут `ExcludeAssets` указывает, какие ресурсы пакета, указанные `<PackageReference>`, не следует использовать.</span><span class="sxs-lookup"><span data-stu-id="47834-202">`ExcludeAssets` attribute specifies which assets belonging to the package specified by `<PackageReference>` should not be consumed.</span></span>

<span data-ttu-id="47834-203">Атрибут `PrivateAssets` указывает, какие ресурсы пакета, указанные `<PackageReference>`, следует использовать, но не следует передавать в следующий проект.</span><span class="sxs-lookup"><span data-stu-id="47834-203">`PrivateAssets` attribute specifies which assets belonging to the package specified by `<PackageReference>` should be consumed but not flow to the next project.</span></span> <span data-ttu-id="47834-204">Если этот атрибут отсутствует, ресурсы `Analyzers`, `Build` и `ContentFiles` по умолчанию являются частными.</span><span class="sxs-lookup"><span data-stu-id="47834-204">The `Analyzers`, `Build` and `ContentFiles` assets are private by default when this attribute is not present.</span></span>

> [!NOTE]
> <span data-ttu-id="47834-205">`PrivateAssets` эквивалентен элементу *project.json*/*xproj* `SuppressParent`.</span><span class="sxs-lookup"><span data-stu-id="47834-205">`PrivateAssets` is equivalent to the *project.json*/*xproj* `SuppressParent` element.</span></span>

<span data-ttu-id="47834-206">Эти атрибуты могут содержать один или несколько следующих элементов (если их больше одного, они разделяются точкой с запятой `;`):</span><span class="sxs-lookup"><span data-stu-id="47834-206">These attributes can contain one or more of the following items, separated by the semicolon `;` character if more than one is listed:</span></span>

- <span data-ttu-id="47834-207">`Compile` — содержимое папки *lib* доступно для компиляции.</span><span class="sxs-lookup"><span data-stu-id="47834-207">`Compile` – the contents of the *lib* folder are available to compile against.</span></span>
- <span data-ttu-id="47834-208">`Runtime` — содержимое папки *runtime* распределяется.</span><span class="sxs-lookup"><span data-stu-id="47834-208">`Runtime` – the contents of the *runtime* folder are distributed.</span></span>
- <span data-ttu-id="47834-209">`ContentFiles` — используется содержимое папки *contentfiles*.</span><span class="sxs-lookup"><span data-stu-id="47834-209">`ContentFiles` – the contents of the *contentfiles* folder are used.</span></span>
- <span data-ttu-id="47834-210">`Build` — используются свойства и целевые объекты в папке *build*.</span><span class="sxs-lookup"><span data-stu-id="47834-210">`Build` – the props/targets in the *build* folder are used.</span></span>
- <span data-ttu-id="47834-211">`Native` — содержимое копируется из основных ресурсов в папку *output* среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="47834-211">`Native` – the contents from native assets are copied to the *output* folder for runtime.</span></span>
- <span data-ttu-id="47834-212">`Analyzers` — используются анализаторы.</span><span class="sxs-lookup"><span data-stu-id="47834-212">`Analyzers` – the analyzers are used.</span></span>

<span data-ttu-id="47834-213">Кроме того, атрибут может содержать следующие значения.</span><span class="sxs-lookup"><span data-stu-id="47834-213">Alternatively, the attribute can contain:</span></span>

- <span data-ttu-id="47834-214">`None` — не используется ни один ресурс.</span><span class="sxs-lookup"><span data-stu-id="47834-214">`None` – none of the assets are used.</span></span>
- <span data-ttu-id="47834-215">`All` — используются все ресурсы.</span><span class="sxs-lookup"><span data-stu-id="47834-215">`All` – all assets are used.</span></span>

### <a name="dotnetclitoolreference"></a><span data-ttu-id="47834-216">DotNetCliToolReference</span><span class="sxs-lookup"><span data-stu-id="47834-216">DotNetCliToolReference</span></span>

<span data-ttu-id="47834-217">Элемент `<DotNetCliToolReference>` указывает средство интерфейса командной строки, которое пользователь хочет восстановить в контексте проекта.</span><span class="sxs-lookup"><span data-stu-id="47834-217">A `<DotNetCliToolReference>` item element specifies the CLI tool that the user wants to restore in the context of the project.</span></span> <span data-ttu-id="47834-218">Этот элемент используется вместо узла `tools` в файле *project.json*.</span><span class="sxs-lookup"><span data-stu-id="47834-218">It's a replacement for the `tools` node in *project.json*.</span></span>

```xml
<DotNetCliToolReference Include="<package-id>" Version="" />
```

<span data-ttu-id="47834-219">Обратите внимание, что `DotNetCliToolReference` [теперь считается нерекомендуемый](https://github.com/dotnet/announcements/issues/107). Вместо него используйте [локальные средства .NET Core](./global-tools.md#install-a-local-tool).</span><span class="sxs-lookup"><span data-stu-id="47834-219">Note that `DotNetCliToolReference` is [now deprecated](https://github.com/dotnet/announcements/issues/107) in favor of [.NET Core Local Tools](./global-tools.md#install-a-local-tool).</span></span>

#### <a name="version"></a><span data-ttu-id="47834-220">Version</span><span class="sxs-lookup"><span data-stu-id="47834-220">Version</span></span>

<span data-ttu-id="47834-221">`Version` указывает версию пакета для восстановления.</span><span class="sxs-lookup"><span data-stu-id="47834-221">`Version` specifies the version of the package to restore.</span></span> <span data-ttu-id="47834-222">Этот атрибут подчиняется правилам схемы [управления версиями NuGet](/nuget/create-packages/dependency-versions#version-ranges).</span><span class="sxs-lookup"><span data-stu-id="47834-222">The attribute respects the rules of the [NuGet versioning](/nuget/create-packages/dependency-versions#version-ranges) scheme.</span></span> <span data-ttu-id="47834-223">По умолчанию выбирается минимальная из заданных версий (включительно).</span><span class="sxs-lookup"><span data-stu-id="47834-223">The default behavior is a minimum version, inclusive match.</span></span> <span data-ttu-id="47834-224">Например, если указать `Version="1.2.3"`, это будет эквивалентно нотации NuGet `[1.2.3, )` и означает, что при разрешении пакет будет иметь версию 1.2.3, если она доступна, или более высокую, если нет.</span><span class="sxs-lookup"><span data-stu-id="47834-224">For example, specifying `Version="1.2.3"` is equivalent to NuGet notation `[1.2.3, )` and means the resolved package will have the version 1.2.3 if available or greater otherwise.</span></span>

### <a name="runtimeidentifiers"></a><span data-ttu-id="47834-225">RuntimeIdentifiers</span><span class="sxs-lookup"><span data-stu-id="47834-225">RuntimeIdentifiers</span></span>

<span data-ttu-id="47834-226">Элемент свойства `<RuntimeIdentifiers>` позволяет указать для проекта список [идентификаторов среды выполнения (RID)](../rid-catalog.md) (в качестве разделителя используется точка с запятой).</span><span class="sxs-lookup"><span data-stu-id="47834-226">The `<RuntimeIdentifiers>` property element lets you specify a semicolon-delimited list of [Runtime Identifiers (RIDs)](../rid-catalog.md) for the project.</span></span>
<span data-ttu-id="47834-227">Идентификаторы позволяют публиковать автономные развертывания.</span><span class="sxs-lookup"><span data-stu-id="47834-227">RIDs enable publishing self-contained deployments.</span></span>

```xml
<RuntimeIdentifiers>win10-x64;osx.10.11-x64;ubuntu.16.04-x64</RuntimeIdentifiers>
```

### <a name="runtimeidentifier"></a><span data-ttu-id="47834-228">RuntimeIdentifier</span><span class="sxs-lookup"><span data-stu-id="47834-228">RuntimeIdentifier</span></span>

<span data-ttu-id="47834-229">Элемент свойства `<RuntimeIdentifier>` позволяет указать для проекта только один [идентификатор среды выполнения](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="47834-229">The `<RuntimeIdentifier>` property element allows you to specify only one [Runtime Identifier (RID)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="47834-230">Идентификатор среды выполнения позволяет опубликовать автономное развертывание.</span><span class="sxs-lookup"><span data-stu-id="47834-230">The RID enables publishing a self-contained deployment.</span></span>

```xml
<RuntimeIdentifier>ubuntu.16.04-x64</RuntimeIdentifier>
```

<span data-ttu-id="47834-231">Используйте `<RuntimeIdentifiers>` (во множественном числе) вместо этого, если вам нужна публикация для различных сред.</span><span class="sxs-lookup"><span data-stu-id="47834-231">Use `<RuntimeIdentifiers>` (plural) instead if you need to publish for multiple runtimes.</span></span> <span data-ttu-id="47834-232">`<RuntimeIdentifier>` может ускорить создание сборок, когда требуется только одна среда выполнения.</span><span class="sxs-lookup"><span data-stu-id="47834-232">`<RuntimeIdentifier>` can provide faster builds when only a single runtime is required.</span></span>

### <a name="packagetargetfallback"></a><span data-ttu-id="47834-233">PackageTargetFallback</span><span class="sxs-lookup"><span data-stu-id="47834-233">PackageTargetFallback</span></span>

<span data-ttu-id="47834-234">Элемент свойства `<PackageTargetFallback>` позволяет указать набор совместимых целевых объектов, которые следует использовать при восстановлении пакетов.</span><span class="sxs-lookup"><span data-stu-id="47834-234">The `<PackageTargetFallback>` property element allows you to specify a set of compatible targets to be used when restoring packages.</span></span> <span data-ttu-id="47834-235">Он разрешает пакетам, использующим dotnet [TxM (моникер целевой версии x)](/nuget/schema/target-frameworks), взаимодействовать с пакетами, которые не объявляют dotnet TxM.</span><span class="sxs-lookup"><span data-stu-id="47834-235">It's designed to allow packages that use the dotnet [TxM (Target x Moniker)](/nuget/schema/target-frameworks) to operate with packages that don't declare a dotnet TxM.</span></span> <span data-ttu-id="47834-236">Если в проекте используется dotnet TxM, все пакеты, от которых вы зависите, должны также содержать dotnet TxM. В противном случае нужно добавить `<PackageTargetFallback>` в проект, чтобы обеспечить совместимость с платформами, отличными от dotnet.</span><span class="sxs-lookup"><span data-stu-id="47834-236">If your project uses the dotnet TxM, then all the packages it depends on must also have a dotnet TxM, unless you add the `<PackageTargetFallback>` to your project in order to allow non-dotnet platforms to be compatible with dotnet.</span></span>

<span data-ttu-id="47834-237">В следующем примере приводятся резервные варианты для всех целевых объектов в проекте:</span><span class="sxs-lookup"><span data-stu-id="47834-237">The following example provides the fallbacks for all targets in your project:</span></span>

```xml
<PackageTargetFallback>
    $(PackageTargetFallback);portable-net45+win8+wpa81+wp8
</PackageTargetFallback >
```

<span data-ttu-id="47834-238">В следующем примере приводятся резервные варианты только для целевого объекта `netcoreapp2.1`:</span><span class="sxs-lookup"><span data-stu-id="47834-238">The following example specifies the fallbacks only for the `netcoreapp2.1` target:</span></span>

```xml
<PackageTargetFallback Condition="'$(TargetFramework)'=='netcoreapp2.1'">
    $(PackageTargetFallback);portable-net45+win8+wpa81+wp8
</PackageTargetFallback >
```

## <a name="build-events"></a><span data-ttu-id="47834-239">События сборки</span><span class="sxs-lookup"><span data-stu-id="47834-239">Build events</span></span>

<span data-ttu-id="47834-240">Способ, которым события перед сборкой и после сборки указываются в файле проекта, изменился.</span><span class="sxs-lookup"><span data-stu-id="47834-240">The way that pre-build and post-build events are specified in the project file has changed.</span></span> <span data-ttu-id="47834-241">Свойства PreBuildEvent и PostBuildEvent не рекомендуется использовать в проектах с форматом в стиле пакета SDK из-за того, что такие макросы, как $(ProjectDir), не будут разрешаться.</span><span class="sxs-lookup"><span data-stu-id="47834-241">The properties PreBuildEvent and PostBuildEvent are not recommended in the SDK-style project format, because macros such as $(ProjectDir) are not resolved.</span></span> <span data-ttu-id="47834-242">Например, следующий код больше не поддерживается:</span><span class="sxs-lookup"><span data-stu-id="47834-242">For example, the following code is no longer supported:</span></span>

```xml
<PropertyGroup>
    <PreBuildEvent>"$(ProjectDir)PreBuildEvent.bat" "$(ProjectDir)..\" "$(ProjectDir)" "$(TargetDir)"</PreBuildEvent>
</PropertyGroup>
```

<span data-ttu-id="47834-243">Для проектов в стиле пакета SDK используйте целевой объект MSBuild с именем `PreBuild` или `PostBuild` и задайте свойство `BeforeTargets` для `PreBuild` или свойство `AfterTargets` для `PostBuild`.</span><span class="sxs-lookup"><span data-stu-id="47834-243">In SDK-style projects, use an MSBuild target named `PreBuild` or `PostBuild` and set the `BeforeTargets` property for `PreBuild` or the `AfterTargets` property for `PostBuild`.</span></span> <span data-ttu-id="47834-244">В предыдущем примере используйте такой код:</span><span class="sxs-lookup"><span data-stu-id="47834-244">For the preceding example, use the following code:</span></span>

```xml
<Target Name="PreBuild" BeforeTargets="PreBuildEvent">
    <Exec Command="&quot;$(ProjectDir)PreBuildEvent.bat&quot; &quot;$(ProjectDir)..\&quot; &quot;$(ProjectDir)&quot; &quot;$(TargetDir)&quot;" />
</Target>

<Target Name="PostBuild" AfterTargets="PostBuildEvent">
   <Exec Command="echo Output written to $(TargetDir)" />
</Target>
```

> [!NOTE]
><span data-ttu-id="47834-245">Для целевых объектов MSBuild можно использовать любое имя, но интегрированная среда разработки Visual Studio распознает целевые объекты `PreBuild` и `PostBuild`, поэтому мы рекомендуем использовать эти имена, чтобы можно было изменять команды в интегрированной среде разработки Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="47834-245">You can use any name for the MSBuild targets, but the Visual Studio IDE recognizes `PreBuild` and `PostBuild` targets, so we recommend using those names so that you can edit the commands in the Visual Studio IDE.</span></span>

## <a name="nuget-metadata-properties"></a><span data-ttu-id="47834-246">Свойства метаданных NuGet</span><span class="sxs-lookup"><span data-stu-id="47834-246">NuGet metadata properties</span></span>

<span data-ttu-id="47834-247">При переходе к MSBuild мы переместили входные метаданные, которые использовались при упаковке пакета NuGet из *project.json* в файлы *CSPROJ*.</span><span class="sxs-lookup"><span data-stu-id="47834-247">With the move to MSBuild, we have moved the input metadata that is used when packing a NuGet package from *project.json* to *.csproj* files.</span></span> <span data-ttu-id="47834-248">Входными данными являются свойства MSBuild, поэтому они должны входить в группу `<PropertyGroup>`.</span><span class="sxs-lookup"><span data-stu-id="47834-248">The inputs are MSBuild properties so they have to go within a `<PropertyGroup>` group.</span></span> <span data-ttu-id="47834-249">Ниже представлен список свойств, которые используются как входные данные в процессе упаковки при использовании команды `dotnet pack` или целевого объекта `Pack` MSBuild, входящего в SDK:</span><span class="sxs-lookup"><span data-stu-id="47834-249">The following is the list of properties that are used as inputs to the packing process when using the `dotnet pack` command or the `Pack` MSBuild target that is part of the SDK:</span></span>

### <a name="ispackable"></a><span data-ttu-id="47834-250">IsPackable</span><span class="sxs-lookup"><span data-stu-id="47834-250">IsPackable</span></span>

<span data-ttu-id="47834-251">Логическое значение, которое указывает, можно ли упаковать проект.</span><span class="sxs-lookup"><span data-stu-id="47834-251">A Boolean value that specifies whether the project can be packed.</span></span> <span data-ttu-id="47834-252">Значение по умолчанию — `true`.</span><span class="sxs-lookup"><span data-stu-id="47834-252">The default value is `true`.</span></span>

### <a name="packageversion"></a><span data-ttu-id="47834-253">PackageVersion</span><span class="sxs-lookup"><span data-stu-id="47834-253">PackageVersion</span></span>

<span data-ttu-id="47834-254">Указывает версию, которую будет иметь итоговый пакет.</span><span class="sxs-lookup"><span data-stu-id="47834-254">Specifies the version that the resulting package will have.</span></span> <span data-ttu-id="47834-255">Принимает все формы строки версии NuGet.</span><span class="sxs-lookup"><span data-stu-id="47834-255">Accepts all forms of NuGet version string.</span></span> <span data-ttu-id="47834-256">По умолчанию используется значение `$(Version)`, то есть значение свойства `Version` в проекте.</span><span class="sxs-lookup"><span data-stu-id="47834-256">Default is the value of `$(Version)`, that is, of the property `Version` in the project.</span></span>

### <a name="packageid"></a><span data-ttu-id="47834-257">PackageId</span><span class="sxs-lookup"><span data-stu-id="47834-257">PackageId</span></span>

<span data-ttu-id="47834-258">Указывает имя для итогового пакета.</span><span class="sxs-lookup"><span data-stu-id="47834-258">Specifies the name for the resulting package.</span></span> <span data-ttu-id="47834-259">Если значение не указано, операция `pack` по умолчанию использует в качестве имени пакета `AssemblyName` или имя каталога.</span><span class="sxs-lookup"><span data-stu-id="47834-259">If not specified, the `pack` operation will default to using the `AssemblyName` or directory name as the name of the package.</span></span>

### <a name="title"></a><span data-ttu-id="47834-260">Заголовок</span><span class="sxs-lookup"><span data-stu-id="47834-260">Title</span></span>

<span data-ttu-id="47834-261">Понятный заголовок пакета, обычно используемый при отображении пользовательского интерфейса, как на сайте nuget.org и в диспетчере пакетов Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="47834-261">A human-friendly title of the package, typically used in UI displays as on nuget.org and the Package Manager in Visual Studio.</span></span> <span data-ttu-id="47834-262">Если значение не указано, используется идентификатор пакета.</span><span class="sxs-lookup"><span data-stu-id="47834-262">If not specified, the package ID is used instead.</span></span>

### <a name="authors"></a><span data-ttu-id="47834-263">Authors</span><span class="sxs-lookup"><span data-stu-id="47834-263">Authors</span></span>

<span data-ttu-id="47834-264">Разделенный точками с запятой список авторов пакетов, совпадающих с именами профилей на сайте nuget.org. Они отображаются в коллекции NuGet на сайте nuget.org и используются для перекрестных ссылок на пакеты тех же авторов.</span><span class="sxs-lookup"><span data-stu-id="47834-264">A semicolon-separated list of packages authors, matching the profile names on nuget.org. These are displayed in the NuGet Gallery on nuget.org and are used to cross-reference packages by the same authors.</span></span>

### <a name="packagedescription"></a><span data-ttu-id="47834-265">PackageDescription</span><span class="sxs-lookup"><span data-stu-id="47834-265">PackageDescription</span></span>

<span data-ttu-id="47834-266">Подробное описание пакета для отображения пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="47834-266">A long description of the package for UI display.</span></span>

### <a name="description"></a><span data-ttu-id="47834-267">Описание</span><span class="sxs-lookup"><span data-stu-id="47834-267">Description</span></span>

<span data-ttu-id="47834-268">Подробное описание сборки.</span><span class="sxs-lookup"><span data-stu-id="47834-268">A long description for the assembly.</span></span> <span data-ttu-id="47834-269">Если `PackageDescription` не указывать, это свойство также будет использоваться в качестве описания пакета.</span><span class="sxs-lookup"><span data-stu-id="47834-269">If `PackageDescription` is not specified, then this property is also used as the description of the package.</span></span>

### <a name="copyright"></a><span data-ttu-id="47834-270">Copyright</span><span class="sxs-lookup"><span data-stu-id="47834-270">Copyright</span></span>

<span data-ttu-id="47834-271">Сведения об авторских правах для пакета.</span><span class="sxs-lookup"><span data-stu-id="47834-271">Copyright details for the package.</span></span>

### <a name="packagerequirelicenseacceptance"></a><span data-ttu-id="47834-272">PackageRequireLicenseAcceptance</span><span class="sxs-lookup"><span data-stu-id="47834-272">PackageRequireLicenseAcceptance</span></span>

<span data-ttu-id="47834-273">Логическое значение, указывающее, должен ли клиент просить потребителя принять условия лицензии перед установкой пакета.</span><span class="sxs-lookup"><span data-stu-id="47834-273">A Boolean value that specifies whether the client must prompt the consumer to accept the package license before installing the package.</span></span> <span data-ttu-id="47834-274">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="47834-274">The default is `false`.</span></span>

### <a name="developmentdependency"></a><span data-ttu-id="47834-275">DevelopmentDependency</span><span class="sxs-lookup"><span data-stu-id="47834-275">DevelopmentDependency</span></span>

<span data-ttu-id="47834-276">Логическое значение, указывающее на то, помечен ли пакет как зависимость только для разработки, что позволяет запретить его включение в качестве зависимости в другие пакеты.</span><span class="sxs-lookup"><span data-stu-id="47834-276">A Boolean value that specifies whether the package is marked as a development-only dependency, which prevents the package from being included as a dependency in other packages.</span></span> <span data-ttu-id="47834-277">При использовании PackageReference (NuGet 4.8 и более поздних версий) этот флаг также указывает на то, что ресурсы времени компиляции исключены из компиляции.</span><span class="sxs-lookup"><span data-stu-id="47834-277">With PackageReference (NuGet 4.8+), this flag also means that compile-time assets are excluded from compilation.</span></span> <span data-ttu-id="47834-278">Дополнительные сведения см. в статье [DevelopmentDependency support for PackageReference](https://github.com/NuGet/Home/wiki/DevelopmentDependency-support-for-PackageReference) (Поддержка DevelopmentDependency для PackageReference).</span><span class="sxs-lookup"><span data-stu-id="47834-278">For more information, see [DevelopmentDependency support for PackageReference](https://github.com/NuGet/Home/wiki/DevelopmentDependency-support-for-PackageReference).</span></span>

### <a name="packagelicenseexpression"></a><span data-ttu-id="47834-279">PackageLicenseExpression</span><span class="sxs-lookup"><span data-stu-id="47834-279">PackageLicenseExpression</span></span>

<span data-ttu-id="47834-280">[Идентификатор лицензии SPDX](https://spdx.org/licenses/) или выражение.</span><span class="sxs-lookup"><span data-stu-id="47834-280">An [SPDX license identifier](https://spdx.org/licenses/) or expression.</span></span> <span data-ttu-id="47834-281">Например, `Apache-2.0`.</span><span class="sxs-lookup"><span data-stu-id="47834-281">For example, `Apache-2.0`.</span></span>

<span data-ttu-id="47834-282">Здесь приведен полный список [идентификаторов лицензии SPDX](https://spdx.org/licenses/).</span><span class="sxs-lookup"><span data-stu-id="47834-282">Here is the complete list of [SPDX license identifiers](https://spdx.org/licenses/).</span></span> <span data-ttu-id="47834-283">Если используется выражение типа лицензии, NuGet.org принимает только утвержденные OSI или FSF лицензии.</span><span class="sxs-lookup"><span data-stu-id="47834-283">NuGet.org accepts only OSI or FSF approved licenses when using license type expression.</span></span>

<span data-ttu-id="47834-284">Точный синтаксис выражений лицензии описан ниже в спецификации метаязыка [ABNF](https://tools.ietf.org/html/rfc5234).</span><span class="sxs-lookup"><span data-stu-id="47834-284">The exact syntax of the license expressions is described below in [ABNF](https://tools.ietf.org/html/rfc5234).</span></span>

```abnf
license-id            = <short form license identifier from https://spdx.org/spdx-specification-21-web-version#h.luq9dgcle9mo>

license-exception-id  = <short form license exception identifier from https://spdx.org/spdx-specification-21-web-version#h.ruv3yl8g6czd>

simple-expression = license-id / license-id”+”

compound-expression =  1*1(simple-expression /
                simple-expression "WITH" license-exception-id /
                compound-expression "AND" compound-expression /
                compound-expression "OR" compound-expression ) /
                "(" compound-expression ")" )

license-expression =  1*1(simple-expression / compound-expression / UNLICENSED)
```

> [!NOTE]
> <span data-ttu-id="47834-285">За один раз можно указать только одно из свойств `PackageLicenseExpression`, `PackageLicenseFile` и `PackageLicenseUrl`.</span><span class="sxs-lookup"><span data-stu-id="47834-285">Only one of `PackageLicenseExpression`, `PackageLicenseFile` and `PackageLicenseUrl` can be specified at a time.</span></span>

### <a name="packagelicensefile"></a><span data-ttu-id="47834-286">PackageLicenseFile</span><span class="sxs-lookup"><span data-stu-id="47834-286">PackageLicenseFile</span></span>

<span data-ttu-id="47834-287">Путь к файлу лицензии в пакете, если вы используете лицензию, которой не назначен идентификатор SPDX, или пользовательскую лицензию (в противном случае предпочтительнее использовать свойство `PackageLicenseExpression`).</span><span class="sxs-lookup"><span data-stu-id="47834-287">Path to a license file within the package if you are using a license that hasn’t been assigned an SPDX identifier, or it is a custom license (Otherwise `PackageLicenseExpression` is preferred)</span></span>

<span data-ttu-id="47834-288">Заменяет свойство `PackageLicenseUrl`, не может сочетаться со свойством `PackageLicenseExpression`. Требуется Visual Studio версии 15.9.4 и пакет SDK для .NET 2.1.502, 2.2.101 и выше.</span><span class="sxs-lookup"><span data-stu-id="47834-288">Replaces `PackageLicenseUrl`, can't be combined with `PackageLicenseExpression`, and requires Visual Studio version 15.9.4 and .NET SDK 2.1.502 or 2.2.101 or newer.</span></span>

<span data-ttu-id="47834-289">Вам необходимо убедиться, что файл лицензии упакован. Для этого явно добавьте его в проект. Пример использования:</span><span class="sxs-lookup"><span data-stu-id="47834-289">You will need to ensure the license file is packed by adding it explicitly to the project, example usage:</span></span>

```xml
<PropertyGroup>
  <PackageLicenseFile>LICENSE.txt</PackageLicenseFile>
</PropertyGroup>
<ItemGroup>
  <None Include="licenses\LICENSE.txt" Pack="true" PackagePath="$(PackageLicenseFile)"/>
</ItemGroup>
```

### <a name="packagelicenseurl"></a><span data-ttu-id="47834-290">PackageLicenseUrl</span><span class="sxs-lookup"><span data-stu-id="47834-290">PackageLicenseUrl</span></span>

<span data-ttu-id="47834-291">URL-адрес лицензии, применимой к пакету.</span><span class="sxs-lookup"><span data-stu-id="47834-291">A URL to the license that is applicable to the package.</span></span> <span data-ttu-id="47834-292">(_Отмечено как нерекомендуемое начиная с Visual Studio версии 15.9.4, пакета SDK для .NET 2.1.502 и 2.2.101._ )</span><span class="sxs-lookup"><span data-stu-id="47834-292">(_deprecated since Visual Studio 15.9.4, .NET SDK 2.1.502 and 2.2.101_)</span></span>

### <a name="packageicon"></a><span data-ttu-id="47834-293">PackageIcon</span><span class="sxs-lookup"><span data-stu-id="47834-293">PackageIcon</span></span>

<span data-ttu-id="47834-294">Путь к образу в пакете, используемому в качестве значка пакета.</span><span class="sxs-lookup"><span data-stu-id="47834-294">A path to an image in the package to use as a package icon.</span></span> <span data-ttu-id="47834-295">Подробнее о [метаданных `icon`](/nuget/reference/nuspec#icon).</span><span class="sxs-lookup"><span data-stu-id="47834-295">Read more about [`icon` metadata](/nuget/reference/nuspec#icon).</span></span> <span data-ttu-id="47834-296">[Элемент PackageIconUrl объявлен устаревшим](/nuget/reference/msbuild-targets#packageiconurl). Вместо него следует использовать PackageIcon.</span><span class="sxs-lookup"><span data-stu-id="47834-296">[PackageIconUrl is deprecated](/nuget/reference/msbuild-targets#packageiconurl) in favor of PackageIcon.</span></span>

### <a name="packagereleasenotes"></a><span data-ttu-id="47834-297">PackageReleaseNotes</span><span class="sxs-lookup"><span data-stu-id="47834-297">PackageReleaseNotes</span></span>

<span data-ttu-id="47834-298">Заметки о выпуске для пакета.</span><span class="sxs-lookup"><span data-stu-id="47834-298">Release notes for the package.</span></span>

### <a name="packagetags"></a><span data-ttu-id="47834-299">PackageTags</span><span class="sxs-lookup"><span data-stu-id="47834-299">PackageTags</span></span>

<span data-ttu-id="47834-300">Разделенный точками с запятой список тегов, обозначающий пакет.</span><span class="sxs-lookup"><span data-stu-id="47834-300">A semicolon-delimited list of tags that designates the package.</span></span>

### <a name="packageoutputpath"></a><span data-ttu-id="47834-301">PackageOutputPath</span><span class="sxs-lookup"><span data-stu-id="47834-301">PackageOutputPath</span></span>

<span data-ttu-id="47834-302">Определяет выходной путь для размещения упакованного пакета.</span><span class="sxs-lookup"><span data-stu-id="47834-302">Determines the output path in which the packed package will be dropped.</span></span> <span data-ttu-id="47834-303">Значение по умолчанию — `$(OutputPath)`.</span><span class="sxs-lookup"><span data-stu-id="47834-303">Default is `$(OutputPath)`.</span></span>

### <a name="includesymbols"></a><span data-ttu-id="47834-304">IncludeSymbols</span><span class="sxs-lookup"><span data-stu-id="47834-304">IncludeSymbols</span></span>
<span data-ttu-id="47834-305">Это логическое значение указывает, должен ли пакет создавать дополнительный пакет символов при упаковке проекта.</span><span class="sxs-lookup"><span data-stu-id="47834-305">This Boolean value indicates whether the package should create an additional symbols package when the project is packed.</span></span> <span data-ttu-id="47834-306">Форматом пакета символов управляет свойство `SymbolPackageFormat`.</span><span class="sxs-lookup"><span data-stu-id="47834-306">The symbols package's format is controlled by the `SymbolPackageFormat` property.</span></span>

### <a name="symbolpackageformat"></a><span data-ttu-id="47834-307">SymbolPackageFormat</span><span class="sxs-lookup"><span data-stu-id="47834-307">SymbolPackageFormat</span></span>
<span data-ttu-id="47834-308">Задает формат пакета символов.</span><span class="sxs-lookup"><span data-stu-id="47834-308">Specifies the format of the symbols package.</span></span> <span data-ttu-id="47834-309">Если задано symbols.nupkg, создается пакет символов в старом формате с расширением *. symbols.nupkg*, содержащий PDB-файлы, библиотеки DLL и другие выходные файлы.</span><span class="sxs-lookup"><span data-stu-id="47834-309">If "symbols.nupkg", a legacy symbols package will be created with a *.symbols.nupkg* extension containing PDBs, DLLs, and other output files.</span></span> <span data-ttu-id="47834-310">Если задано snupkg, создается пакет символов snupkg, содержащий переносимые PDB-файлы.</span><span class="sxs-lookup"><span data-stu-id="47834-310">If "snupkg", a snupkg symbol package will be created containing the portable PDBs.</span></span> <span data-ttu-id="47834-311">По умолчанию задано symbols.nupkg.</span><span class="sxs-lookup"><span data-stu-id="47834-311">Default is "symbols.nupkg".</span></span>

### <a name="includesource"></a><span data-ttu-id="47834-312">IncludeSource</span><span class="sxs-lookup"><span data-stu-id="47834-312">IncludeSource</span></span>

<span data-ttu-id="47834-313">Это логическое значение указывает, должен ли процесс упаковки создавать исходный пакет.</span><span class="sxs-lookup"><span data-stu-id="47834-313">This Boolean value indicates whether the pack process should create a source package.</span></span> <span data-ttu-id="47834-314">Исходный пакет содержит библиотеку исходного кода, а также файлы PDB.</span><span class="sxs-lookup"><span data-stu-id="47834-314">The source package contains the library's source code as well as PDB files.</span></span> <span data-ttu-id="47834-315">Исходные файлы помещаются в каталог `src/ProjectName` итогового файла пакета.</span><span class="sxs-lookup"><span data-stu-id="47834-315">Source files are put under the `src/ProjectName` directory in the resulting package file.</span></span>

### <a name="istool"></a><span data-ttu-id="47834-316">IsTool</span><span class="sxs-lookup"><span data-stu-id="47834-316">IsTool</span></span>

<span data-ttu-id="47834-317">Указывает, копируются ли все выходные файлы в папку *tools* вместо папки *lib*.</span><span class="sxs-lookup"><span data-stu-id="47834-317">Specifies whether all output files are copied to the *tools* folder instead of the *lib* folder.</span></span> <span data-ttu-id="47834-318">Это свойство отличается от `DotNetCliTool`, которое указывается путем задания `PackageType` в файле *CSPROJ*.</span><span class="sxs-lookup"><span data-stu-id="47834-318">This is different from a `DotNetCliTool`, which is specified by setting the `PackageType` in the *.csproj* file.</span></span>

### <a name="repositoryurl"></a><span data-ttu-id="47834-319">RepositoryUrl</span><span class="sxs-lookup"><span data-stu-id="47834-319">RepositoryUrl</span></span>

<span data-ttu-id="47834-320">Указывает URL-адрес репозитория, где находится исходный код для пакета или откуда выполняется его сборка.</span><span class="sxs-lookup"><span data-stu-id="47834-320">Specifies the URL for the repository where the source code for the package resides and/or from which it's being built.</span></span>

### <a name="repositorytype"></a><span data-ttu-id="47834-321">RepositoryType</span><span class="sxs-lookup"><span data-stu-id="47834-321">RepositoryType</span></span>

<span data-ttu-id="47834-322">Указывает тип репозитория.</span><span class="sxs-lookup"><span data-stu-id="47834-322">Specifies the type of the repository.</span></span> <span data-ttu-id="47834-323">Значение по умолчанию — "git".</span><span class="sxs-lookup"><span data-stu-id="47834-323">Default is "git".</span></span>

### <a name="repositorybranch"></a><span data-ttu-id="47834-324">RepositoryBranch</span><span class="sxs-lookup"><span data-stu-id="47834-324">RepositoryBranch</span></span>
<span data-ttu-id="47834-325">Указывает имя исходной ветки в репозитории.</span><span class="sxs-lookup"><span data-stu-id="47834-325">Specifies the name of the source branch in the repository.</span></span> <span data-ttu-id="47834-326">Если проект упакован в пакет NuGet, он добавляется в метаданные пакета.</span><span class="sxs-lookup"><span data-stu-id="47834-326">When the project is packaged in a NuGet package, it's added to the package metadata.</span></span>

### <a name="repositorycommit"></a><span data-ttu-id="47834-327">RepositoryCommit</span><span class="sxs-lookup"><span data-stu-id="47834-327">RepositoryCommit</span></span>
<span data-ttu-id="47834-328">Необязательная фиксация или набор изменений репозитория для указания источника, на основе которого был создан пакет.</span><span class="sxs-lookup"><span data-stu-id="47834-328">Optional repository commit or changeset to indicate which source the package was built against.</span></span> <span data-ttu-id="47834-329">Необходимо также указать `RepositoryUrl`, чтобы включить это свойство.</span><span class="sxs-lookup"><span data-stu-id="47834-329">`RepositoryUrl` must also be specified for this property to be included.</span></span> <span data-ttu-id="47834-330">Если проект упакован в пакет NuGet, эта фиксация или набор изменений добавляются в метаданные пакета.</span><span class="sxs-lookup"><span data-stu-id="47834-330">When the project is packaged in a NuGet package, this commit or changeset is added to the package metadata.</span></span>

### <a name="nopackageanalysis"></a><span data-ttu-id="47834-331">NoPackageAnalysis</span><span class="sxs-lookup"><span data-stu-id="47834-331">NoPackageAnalysis</span></span>

<span data-ttu-id="47834-332">Указывает, что пакету не нужно запускать анализ пакета после его сборки.</span><span class="sxs-lookup"><span data-stu-id="47834-332">Specifies that pack should not run package analysis after building the package.</span></span>

### <a name="minclientversion"></a><span data-ttu-id="47834-333">MinClientVersion</span><span class="sxs-lookup"><span data-stu-id="47834-333">MinClientVersion</span></span>

<span data-ttu-id="47834-334">Указывает минимальную версию клиента NuGet, который может установить этот пакет с использованием nuget.exe и диспетчера пакетов Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="47834-334">Specifies the minimum version of the NuGet client that can install this package, enforced by nuget.exe and the Visual Studio Package Manager.</span></span>

### <a name="includebuildoutput"></a><span data-ttu-id="47834-335">IncludeBuildOutput</span><span class="sxs-lookup"><span data-stu-id="47834-335">IncludeBuildOutput</span></span>

<span data-ttu-id="47834-336">Это логическое значение указывает, следует ли упаковывать выходные сборки в файл *NUPKG*.</span><span class="sxs-lookup"><span data-stu-id="47834-336">This Boolean value specifies whether the build output assemblies should be packed into the *.nupkg* file or not.</span></span>

### <a name="includecontentinpack"></a><span data-ttu-id="47834-337">IncludeContentInPack</span><span class="sxs-lookup"><span data-stu-id="47834-337">IncludeContentInPack</span></span>

<span data-ttu-id="47834-338">Это логическое значение указывает, будут ли все элементы, имеющие тип `Content`, автоматически включены в итоговый пакет.</span><span class="sxs-lookup"><span data-stu-id="47834-338">This Boolean value specifies whether any items that have a type of `Content` will be included in the resulting package automatically.</span></span> <span data-ttu-id="47834-339">Значение по умолчанию — `true`.</span><span class="sxs-lookup"><span data-stu-id="47834-339">The default is `true`.</span></span>

### <a name="buildoutputtargetfolder"></a><span data-ttu-id="47834-340">BuildOutputTargetFolder</span><span class="sxs-lookup"><span data-stu-id="47834-340">BuildOutputTargetFolder</span></span>

<span data-ttu-id="47834-341">Указывает папку для размещения выходных сборок.</span><span class="sxs-lookup"><span data-stu-id="47834-341">Specifies the folder where to place the output assemblies.</span></span> <span data-ttu-id="47834-342">Выходные сборки (и другие выходные файлы) копируются в соответствующие папки платформы.</span><span class="sxs-lookup"><span data-stu-id="47834-342">The output assemblies (and other output files) are copied into their respective framework folders.</span></span>

### <a name="contenttargetfolders"></a><span data-ttu-id="47834-343">ContentTargetFolders</span><span class="sxs-lookup"><span data-stu-id="47834-343">ContentTargetFolders</span></span>

<span data-ttu-id="47834-344">Это свойство указывает расположение по умолчанию, куда следует помещать все файлы содержимого, для которых не указан `PackagePath`.</span><span class="sxs-lookup"><span data-stu-id="47834-344">This property specifies the default location of where all the content files should go if `PackagePath` is not specified for them.</span></span> <span data-ttu-id="47834-345">Значение по умолчанию — "content;contentFiles".</span><span class="sxs-lookup"><span data-stu-id="47834-345">The default value is "content;contentFiles".</span></span>

### <a name="nuspecfile"></a><span data-ttu-id="47834-346">NuspecFile</span><span class="sxs-lookup"><span data-stu-id="47834-346">NuspecFile</span></span>

<span data-ttu-id="47834-347">Относительный или абсолютный путь к файлу *NUSPEC*, используемому для упаковки.</span><span class="sxs-lookup"><span data-stu-id="47834-347">Relative or absolute path to the *.nuspec* file being used for packing.</span></span>

> [!NOTE]
> <span data-ttu-id="47834-348">Если файл *NUSPEC* указан, он используется для упаковки в **монопольном порядке**, а любые сведения в проектах не используются.</span><span class="sxs-lookup"><span data-stu-id="47834-348">If the *.nuspec* file is specified, it's used **exclusively** for packaging information and any information in the projects is not used.</span></span>

### <a name="nuspecbasepath"></a><span data-ttu-id="47834-349">NuspecBasePath</span><span class="sxs-lookup"><span data-stu-id="47834-349">NuspecBasePath</span></span>

<span data-ttu-id="47834-350">Базовый путь для файла *NUSPEC*.</span><span class="sxs-lookup"><span data-stu-id="47834-350">Base path for the *.nuspec* file.</span></span>

### <a name="nuspecproperties"></a><span data-ttu-id="47834-351">NuspecProperties</span><span class="sxs-lookup"><span data-stu-id="47834-351">NuspecProperties</span></span>

<span data-ttu-id="47834-352">Список разделенных точками с запятой пар "ключ-значение".</span><span class="sxs-lookup"><span data-stu-id="47834-352">Semicolon separated list of key=value pairs.</span></span>

## <a name="assemblyinfo-properties"></a><span data-ttu-id="47834-353">Свойства AssemblyInfo</span><span class="sxs-lookup"><span data-stu-id="47834-353">AssemblyInfo properties</span></span>

<span data-ttu-id="47834-354">[Атрибуты сборки](../../standard/assembly/set-attributes.md), которые обычно содержатся в файле *AssemblyInfo*, теперь автоматически создаются на основе свойств.</span><span class="sxs-lookup"><span data-stu-id="47834-354">[Assembly attributes](../../standard/assembly/set-attributes.md) that were typically present in an *AssemblyInfo* file are now automatically generated from properties.</span></span>

### <a name="properties-per-attribute"></a><span data-ttu-id="47834-355">Свойства каждого атрибута</span><span class="sxs-lookup"><span data-stu-id="47834-355">Properties per attribute</span></span>

<span data-ttu-id="47834-356">Как показано в следующей таблице, каждый атрибут имеет два свойства: одно управляет содержимым атрибута, а второе отключает его создание.</span><span class="sxs-lookup"><span data-stu-id="47834-356">As shown in the following table, each attribute has a property that controls its content and another that disables its generation:</span></span>

| <span data-ttu-id="47834-357">Атрибут</span><span class="sxs-lookup"><span data-stu-id="47834-357">Attribute</span></span>                                                      | <span data-ttu-id="47834-358">Свойство.</span><span class="sxs-lookup"><span data-stu-id="47834-358">Property</span></span>               | <span data-ttu-id="47834-359">Свойство, используемое для отключения</span><span class="sxs-lookup"><span data-stu-id="47834-359">Property to disable</span></span>                             |
|----------------------------------------------------------------|------------------------|-------------------------------------------------|
| <xref:System.Reflection.AssemblyCompanyAttribute>              | `Company`              | `GenerateAssemblyCompanyAttribute`              |
| <xref:System.Reflection.AssemblyConfigurationAttribute>        | `Configuration`        | `GenerateAssemblyConfigurationAttribute`        |
| <xref:System.Reflection.AssemblyCopyrightAttribute>            | `Copyright`            | `GenerateAssemblyCopyrightAttribute`            |
| <xref:System.Reflection.AssemblyDescriptionAttribute>          | `Description`          | `GenerateAssemblyDescriptionAttribute`          |
| <xref:System.Reflection.AssemblyFileVersionAttribute>          | `FileVersion`          | `GenerateAssemblyFileVersionAttribute`          |
| <xref:System.Reflection.AssemblyInformationalVersionAttribute> | `InformationalVersion` | `GenerateAssemblyInformationalVersionAttribute` |
| <xref:System.Reflection.AssemblyProductAttribute>              | `Product`              | `GenerateAssemblyProductAttribute`              |
| <xref:System.Reflection.AssemblyTitleAttribute>                | `AssemblyTitle`        | `GenerateAssemblyTitleAttribute`                |
| <xref:System.Reflection.AssemblyVersionAttribute>              | `AssemblyVersion`      | `GenerateAssemblyVersionAttribute`              |
| <xref:System.Resources.NeutralResourcesLanguageAttribute>      | `NeutralLanguage`      | `GenerateNeutralResourcesLanguageAttribute`     |

<span data-ttu-id="47834-360">Примечания.</span><span class="sxs-lookup"><span data-stu-id="47834-360">Notes:</span></span>

- <span data-ttu-id="47834-361">`AssemblyVersion` и `FileVersion` по умолчанию имеют значение `$(Version)` без суффикса.</span><span class="sxs-lookup"><span data-stu-id="47834-361">`AssemblyVersion` and `FileVersion` default is to take the value of `$(Version)` without suffix.</span></span> <span data-ttu-id="47834-362">Например, если для `$(Version)` нужно указать `1.2.3-beta.4`, то значением будет `1.2.3`.</span><span class="sxs-lookup"><span data-stu-id="47834-362">For example, if `$(Version)` is `1.2.3-beta.4`, then the value would be `1.2.3`.</span></span>
- <span data-ttu-id="47834-363">По умолчанию для `InformationalVersion` используется значение `$(Version)`.</span><span class="sxs-lookup"><span data-stu-id="47834-363">`InformationalVersion` defaults to the value of `$(Version)`.</span></span>
- <span data-ttu-id="47834-364">`InformationalVersion` имеет значение `$(SourceRevisionId)`, которое добавляется, если указано свойство.</span><span class="sxs-lookup"><span data-stu-id="47834-364">`InformationalVersion` has `$(SourceRevisionId)` appended if the property is present.</span></span> <span data-ttu-id="47834-365">Его можно отключить с помощью `IncludeSourceRevisionInInformationalVersion`.</span><span class="sxs-lookup"><span data-stu-id="47834-365">It can be disabled using `IncludeSourceRevisionInInformationalVersion`.</span></span>
- <span data-ttu-id="47834-366">Свойства `Copyright` и `Description` также используются для метаданных NuGet.</span><span class="sxs-lookup"><span data-stu-id="47834-366">`Copyright` and `Description` properties are also used for NuGet metadata.</span></span>
- <span data-ttu-id="47834-367">Свойство `Configuration` является общим для всего процесса сборки, и задается с помощью параметра `--configuration` команд `dotnet`.</span><span class="sxs-lookup"><span data-stu-id="47834-367">`Configuration` is shared with all the build process and set via the `--configuration` parameter of `dotnet` commands.</span></span>

### <a name="generateassemblyinfo"></a><span data-ttu-id="47834-368">GenerateAssemblyInfo</span><span class="sxs-lookup"><span data-stu-id="47834-368">GenerateAssemblyInfo</span></span>

<span data-ttu-id="47834-369">Логическое свойство, которое позволяет включить или отключить создание всех свойств AssemblyInfo.</span><span class="sxs-lookup"><span data-stu-id="47834-369">A Boolean that enable or disable all the AssemblyInfo generation.</span></span> <span data-ttu-id="47834-370">Значение по умолчанию — `true`.</span><span class="sxs-lookup"><span data-stu-id="47834-370">The default value is `true`.</span></span>

### <a name="generatedassemblyinfofile"></a><span data-ttu-id="47834-371">GeneratedAssemblyInfoFile</span><span class="sxs-lookup"><span data-stu-id="47834-371">GeneratedAssemblyInfoFile</span></span>

<span data-ttu-id="47834-372">Путь к файлу сведений о созданной сборке.</span><span class="sxs-lookup"><span data-stu-id="47834-372">The path of the generated assembly info file.</span></span> <span data-ttu-id="47834-373">По умолчанию это путь к файлу в каталоге объектов `$(IntermediateOutputPath)`.</span><span class="sxs-lookup"><span data-stu-id="47834-373">Default to a file in the `$(IntermediateOutputPath)` (obj) directory.</span></span>
