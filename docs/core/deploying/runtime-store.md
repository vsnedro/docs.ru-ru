---
title: Хранилище пакетов среды выполнения
description: Сведения о том, как использовать хранилище пакетов среды выполнения в качестве целевого для манифестов, используемых платформой .NET Core.
ms.date: 08/12/2017
ms.openlocfilehash: 4395370c3bb2d97511d549a63813022fb8cac4b7
ms.sourcegitcommit: c2c1269a81ffdcfc8675bcd9a8505b1a11ffb271
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/25/2020
ms.locfileid: "82158297"
---
# <a name="runtime-package-store"></a><span data-ttu-id="e5514-103">Хранилище пакетов среды выполнения</span><span class="sxs-lookup"><span data-stu-id="e5514-103">Runtime package store</span></span>

<span data-ttu-id="e5514-104">Начиная с версии .NET Core 2.0, можно упаковывать и развертывать приложения на основе известного набора пакетов, имеющегося в целевой среде.</span><span class="sxs-lookup"><span data-stu-id="e5514-104">Starting with .NET Core 2.0, it's possible to package and deploy apps against a known set of packages that exist in the target environment.</span></span> <span data-ttu-id="e5514-105">Преимущества заключаются в ускорении развертывания, сокращении используемого дискового пространства и в некоторых случаях повышении производительности запуска.</span><span class="sxs-lookup"><span data-stu-id="e5514-105">The benefits are faster deployments, lower disk space usage, and improved startup performance in some cases.</span></span>

<span data-ttu-id="e5514-106">Эта возможность реализована в виде *хранилища пакетов среды выполнения*, представляющего собой каталог на диске, в котором хранятся пакеты (как правило, */usr/local/share/dotnet/store* в macOS или Linux и *C:/Program Files/dotnet/store* в Windows).</span><span class="sxs-lookup"><span data-stu-id="e5514-106">This feature is implemented as a *runtime package store*, which is a directory on disk where packages are stored (typically at */usr/local/share/dotnet/store* on macOS/Linux and *C:/Program Files/dotnet/store* on Windows).</span></span> <span data-ttu-id="e5514-107">В этом каталоге есть подкаталоги для архитектур и [целевых платформ](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="e5514-107">Under this directory, there are subdirectories for architectures and [target frameworks](../../standard/frameworks.md).</span></span> <span data-ttu-id="e5514-108">Структура файлов аналогична [структуре ресурсов NuGet на диске](/nuget/create-packages/supporting-multiple-target-frameworks#framework-version-folder-structure):</span><span class="sxs-lookup"><span data-stu-id="e5514-108">The file layout is similar to the way that [NuGet assets are laid out on disk](/nuget/create-packages/supporting-multiple-target-frameworks#framework-version-folder-structure):</span></span>

```
\dotnet
    \store
        \x64
            \netcoreapp2.0
                \microsoft.applicationinsights
                \microsoft.aspnetcore
                ...
        \x86
            \netcoreapp2.0
                \microsoft.applicationinsights
                \microsoft.aspnetcore
                ...
```

<span data-ttu-id="e5514-109">В файле *целевого манифеста* содержится список пакетов, имеющихся в хранилище пакетов среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="e5514-109">A *target manifest* file lists the packages in the runtime package store.</span></span> <span data-ttu-id="e5514-110">Разработчики могут указывать этот манифест в качестве целевого при публикации приложений.</span><span class="sxs-lookup"><span data-stu-id="e5514-110">Developers can target this manifest when publishing their app.</span></span> <span data-ttu-id="e5514-111">Целевой манифест, как правило, предоставляется владельцем целевой рабочей среды.</span><span class="sxs-lookup"><span data-stu-id="e5514-111">The target manifest is typically provided by the owner of the targeted production environment.</span></span>

## <a name="preparing-a-runtime-environment"></a><span data-ttu-id="e5514-112">Подготовка среды выполнения</span><span class="sxs-lookup"><span data-stu-id="e5514-112">Preparing a runtime environment</span></span>

<span data-ttu-id="e5514-113">Администратор среды выполнения может оптимизировать приложения для более быстрого развертывания и сокращения используемого дискового пространства, создав хранилище пакетов среды выполнения и соответствующий целевой манифест.</span><span class="sxs-lookup"><span data-stu-id="e5514-113">The administrator of a runtime environment can optimize apps for faster deployments and lower disk space use by building a runtime package store and the corresponding target manifest.</span></span>

<span data-ttu-id="e5514-114">Для этого сначала необходимо создать *манифест хранилища пакетов*, который содержит список пакетов, имеющихся в хранилище пакетов среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="e5514-114">The first step is to create a *package store manifest* that lists the packages that compose the runtime package store.</span></span> <span data-ttu-id="e5514-115">Формат этого файла совместим с форматом файла проекта (*CSPROJ*).</span><span class="sxs-lookup"><span data-stu-id="e5514-115">This file format is compatible with the project file format (*csproj*).</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <ItemGroup>
    <PackageReference Include="NUGET_PACKAGE" Version="VERSION" />
    <!-- Include additional packages here -->
  </ItemGroup>
</Project>
```

<span data-ttu-id="e5514-116">**Пример**</span><span class="sxs-lookup"><span data-stu-id="e5514-116">**Example**</span></span>

<span data-ttu-id="e5514-117">В приведенном ниже примере манифест хранилища пакетов (*packages.csproj*) используется для добавления [`Newtonsoft.Json`](https://www.nuget.org/packages/Newtonsoft.Json/) и [`Moq`](https://www.nuget.org/packages/moq/) в хранилище пакетов среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="e5514-117">The following example package store manifest (*packages.csproj*) is used to add [`Newtonsoft.Json`](https://www.nuget.org/packages/Newtonsoft.Json/) and [`Moq`](https://www.nuget.org/packages/moq/) to a runtime package store:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <ItemGroup>
    <PackageReference Include="Newtonsoft.Json" Version="10.0.3" />
    <PackageReference Include="Moq" Version="4.7.63" />
  </ItemGroup>
</Project>
```

<span data-ttu-id="e5514-118">Чтобы подготовить хранилище пакетов среды выполнения, выполните команду `dotnet store`, указав манифест хранилища пакетов, среду выполнения и платформу.</span><span class="sxs-lookup"><span data-stu-id="e5514-118">Provision the runtime package store by executing `dotnet store` with the package store manifest, runtime, and framework:</span></span>

```dotnetcli
dotnet store --manifest <PATH_TO_MANIFEST_FILE> --runtime <RUNTIME_IDENTIFIER> --framework <FRAMEWORK>
```

<span data-ttu-id="e5514-119">**Пример**</span><span class="sxs-lookup"><span data-stu-id="e5514-119">**Example**</span></span>

```dotnetcli
dotnet store --manifest packages.csproj --runtime win10-x64 --framework netcoreapp2.0 --framework-version 2.0.0
```

<span data-ttu-id="e5514-120">В команду [`dotnet store`](../tools/dotnet-store.md) можно передать несколько путей к целевым манифестам хранилищ пакетов, указав параметр и путь несколько раз.</span><span class="sxs-lookup"><span data-stu-id="e5514-120">You can pass multiple target package store manifest paths to a single [`dotnet store`](../tools/dotnet-store.md) command by repeating the option and path in the command.</span></span>

<span data-ttu-id="e5514-121">По умолчанию выходные данные команды представляют собой хранилище пакетов в подкаталоге *.dotnet/store* профиля пользователя.</span><span class="sxs-lookup"><span data-stu-id="e5514-121">By default, the output of the command is a package store under the *.dotnet/store* subdirectory of the user's profile.</span></span> <span data-ttu-id="e5514-122">С помощью параметра `--output <OUTPUT_DIRECTORY>` можно задать другое расположение.</span><span class="sxs-lookup"><span data-stu-id="e5514-122">You can specify a different location using the `--output <OUTPUT_DIRECTORY>` option.</span></span> <span data-ttu-id="e5514-123">Корневой каталог хранилища содержит файл *artifact.xml* целевого манифеста.</span><span class="sxs-lookup"><span data-stu-id="e5514-123">The root directory of the store contains a target manifest *artifact.xml* file.</span></span> <span data-ttu-id="e5514-124">Этот файл можно сделать доступным для скачивания и использования разработчиками, которые при публикации своих приложений хотят задать это хранилище в качестве целевого.</span><span class="sxs-lookup"><span data-stu-id="e5514-124">This file can be made available for download and be used by app authors who want to target this store when publishing.</span></span>

<span data-ttu-id="e5514-125">**Пример**</span><span class="sxs-lookup"><span data-stu-id="e5514-125">**Example**</span></span>

<span data-ttu-id="e5514-126">После выполнения команды в предыдущем примере создается приведенный ниже файл *artifact.xml*.</span><span class="sxs-lookup"><span data-stu-id="e5514-126">The following *artifact.xml* file is produced after running the previous example.</span></span> <span data-ttu-id="e5514-127">Обратите внимание на то, что пакет [`Castle.Core`](https://www.nuget.org/packages/Castle.Core/) является зависимостью `Moq`, поэтому он включается автоматически и указывается в файле манифеста *artifacts.xml*.</span><span class="sxs-lookup"><span data-stu-id="e5514-127">Note that [`Castle.Core`](https://www.nuget.org/packages/Castle.Core/) is a dependency of `Moq`, so it's included automatically and appears in the *artifacts.xml* manifest file.</span></span>

```xml
<StoreArtifacts>
  <Package Id="Newtonsoft.Json" Version="10.0.3" />
  <Package Id="Castle.Core" Version="4.1.0" />
  <Package Id="Moq" Version="4.7.63" />
</StoreArtifacts>
```

## <a name="publishing-an-app-against-a-target-manifest"></a><span data-ttu-id="e5514-128">Публикация приложения для целевого манифеста</span><span class="sxs-lookup"><span data-stu-id="e5514-128">Publishing an app against a target manifest</span></span>

<span data-ttu-id="e5514-129">Если на диске есть файл целевого манифеста, путь к нему указывается при публикации приложения с помощью команды [`dotnet publish`](../tools/dotnet-publish.md).</span><span class="sxs-lookup"><span data-stu-id="e5514-129">If you have a target manifest file on disk, you specify the path to the file when publishing your app with the [`dotnet publish`](../tools/dotnet-publish.md) command:</span></span>

```dotnetcli
dotnet publish --manifest <PATH_TO_MANIFEST_FILE>
```

<span data-ttu-id="e5514-130">**Пример**</span><span class="sxs-lookup"><span data-stu-id="e5514-130">**Example**</span></span>

```dotnetcli
dotnet publish --manifest manifest.xml
```

<span data-ttu-id="e5514-131">Опубликованное приложение развертывается в среде, в которой имеются пакеты, описываемые в целевом манифесте.</span><span class="sxs-lookup"><span data-stu-id="e5514-131">You deploy the resulting published app to an environment that has the packages described in the target manifest.</span></span> <span data-ttu-id="e5514-132">В противном случае приложение не запустится.</span><span class="sxs-lookup"><span data-stu-id="e5514-132">Failing to do so results in the app failing to start.</span></span>

<span data-ttu-id="e5514-133">Чтобы при публикации приложения указать несколько целевых манифестов, добавьте параметр и путь несколько раз (например, `--manifest manifest1.xml --manifest manifest2.xml`).</span><span class="sxs-lookup"><span data-stu-id="e5514-133">Specify multiple target manifests when publishing an app by repeating the option and path (for example, `--manifest manifest1.xml --manifest manifest2.xml`).</span></span> <span data-ttu-id="e5514-134">При этом приложение ограничивается объединением множеств пакетов, указанных в целевых файлах манифестов, которые заданы в команде.</span><span class="sxs-lookup"><span data-stu-id="e5514-134">When you do so, the app is trimmed for the union of packages specified in the target manifest files provided to the command.</span></span>

<span data-ttu-id="e5514-135">Если вы развертываете приложение с зависимостью манифеста, которая присутствует в развертывании (сборка имеется в папке *bin*), хранилище пакетов среды выполнения *не используется* для этой сборки на узле.</span><span class="sxs-lookup"><span data-stu-id="e5514-135">If you deploy an application with a manifest dependency that's present in the deployment (the assembly is present in the *bin* folder), the runtime package store *isn't used* on the host for that assembly.</span></span> <span data-ttu-id="e5514-136">Сборка в папке *bin* используется вне зависимости от ее наличия в хранилище пакетов среды выполнения на узле.</span><span class="sxs-lookup"><span data-stu-id="e5514-136">The *bin* folder assembly is used regardless of its presence in the runtime package store on the host.</span></span>

<span data-ttu-id="e5514-137">Версия зависимости, указанная в манифесте, должна соответствовать версии зависимости в хранилище пакетов среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="e5514-137">The version of the dependency indicated in the manifest must match the version of the dependency in the runtime package store.</span></span> <span data-ttu-id="e5514-138">Если версия зависимости в целевом манифесте и версия, имеющаяся в хранилище пакетов среды выполнения, не совпадают и приложение не включает в себя требуемую версию пакета, приложение не будет запускаться.</span><span class="sxs-lookup"><span data-stu-id="e5514-138">If you have a version mismatch between the dependency in the target manifest and the version that exists in the runtime package store and the app doesn't include the required version of the package in its deployment, the app fails to start.</span></span> <span data-ttu-id="e5514-139">В исключении будет указано имя целевого манифеста, вызываемого для сборки хранилища пакетов среды выполнения, что может помочь в устранении несоответствия.</span><span class="sxs-lookup"><span data-stu-id="e5514-139">The exception includes the name of the target manifest that called for the runtime package store assembly, which helps you troubleshoot the mismatch.</span></span>

<span data-ttu-id="e5514-140">Если развертывание *усекается* при публикации, в публикуемых выходных данных будут отсутствовать только те версии пакетов манифеста, которые вы указали.</span><span class="sxs-lookup"><span data-stu-id="e5514-140">When the deployment is *trimmed* on publish, only the specific versions of the manifest packages you indicate are withheld from the published output.</span></span> <span data-ttu-id="e5514-141">Чтобы приложение могло запускаться, на узле должны присутствовать пакеты с указанными версиями.</span><span class="sxs-lookup"><span data-stu-id="e5514-141">The packages at the versions indicated must be present on the host for the app to start.</span></span>

## <a name="specifying-target-manifests-in-the-project-file"></a><span data-ttu-id="e5514-142">Указание целевых манифестов в файле проекта</span><span class="sxs-lookup"><span data-stu-id="e5514-142">Specifying target manifests in the project file</span></span>

<span data-ttu-id="e5514-143">Помимо указания целевых манифестов с помощью команды [`dotnet publish`](../tools/dotnet-publish.md), их можно указать в файле проекта в виде разделенного точками с запятой списка путей под тегом **\<TargetManifestFiles>** .</span><span class="sxs-lookup"><span data-stu-id="e5514-143">An alternative to specifying target manifests with the [`dotnet publish`](../tools/dotnet-publish.md) command is to specify them in the project file as a semicolon-separated list of paths under a **\<TargetManifestFiles>** tag.</span></span>

```xml
<PropertyGroup>
  <TargetManifestFiles>manifest1.xml;manifest2.xml</TargetManifestFiles>
</PropertyGroup>
```

<span data-ttu-id="e5514-144">Указывать целевые манифесты в файле проекта следует только в том случае, если целевая среда приложения известна, как в случае с проектами .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e5514-144">Specify the target manifests in the project file only when the target environment for the app is well-known, such as for .NET Core projects.</span></span> <span data-ttu-id="e5514-145">В случае с проектами с открытым кодом ситуация иная.</span><span class="sxs-lookup"><span data-stu-id="e5514-145">This isn't the case for open-source projects.</span></span> <span data-ttu-id="e5514-146">Пользователи проекта с открытым кодом, как правило, развертывают его в разных рабочих средах.</span><span class="sxs-lookup"><span data-stu-id="e5514-146">The users of an open-source project typically deploy it to different production environments.</span></span> <span data-ttu-id="e5514-147">В этих рабочих средах обычно предустановлены разные наборы пакетов.</span><span class="sxs-lookup"><span data-stu-id="e5514-147">These production environments generally have different sets of packages pre-installed.</span></span> <span data-ttu-id="e5514-148">Делать предположения о целевых манифестах в таких средах нельзя, поэтому следует использовать параметр `--manifest` команды [`dotnet publish`](../tools/dotnet-publish.md).</span><span class="sxs-lookup"><span data-stu-id="e5514-148">You can't make assumptions about the target manifest in such environments, so you should use the `--manifest` option of [`dotnet publish`](../tools/dotnet-publish.md).</span></span>

## <a name="aspnet-core-implicit-store-net-core-20-only"></a><span data-ttu-id="e5514-149">Неявное хранилище ASP.NET Core (только для .NET Core 2.0)</span><span class="sxs-lookup"><span data-stu-id="e5514-149">ASP.NET Core implicit store (.NET Core 2.0 only)</span></span>

<span data-ttu-id="e5514-150">Неявное хранилище ASP.NET Core применяется только к ASP.NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="e5514-150">The ASP.NET Core implicit store applies only to ASP.NET Core 2.0.</span></span> <span data-ttu-id="e5514-151">Мы настоятельно рекомендуем, чтобы приложения использовали ASP.NET Core 2.1 и более поздних версий, где **не** используется неявное хранилище.</span><span class="sxs-lookup"><span data-stu-id="e5514-151">We strongly recommend applications use ASP.NET Core 2.1 and later, which does **not** use the implicit store.</span></span> <span data-ttu-id="e5514-152">ASP.NET Core 2.1 и более поздние версии используют общую платформу.</span><span class="sxs-lookup"><span data-stu-id="e5514-152">ASP.NET Core 2.1 and later use the shared framework.</span></span>

<span data-ttu-id="e5514-153">В .NET Core 2.0 хранилище пакетов среды выполнения неявно используется приложением ASP.NET Core при его развертывании в качестве приложения с [зависящим от среды выполнения развертыванием](index.md#publish-runtime-dependent).</span><span class="sxs-lookup"><span data-stu-id="e5514-153">For .NET Core 2.0, the runtime package store feature is used implicitly by an ASP.NET Core app when the app is deployed as a [runtime-dependent deployment](index.md#publish-runtime-dependent) app.</span></span> <span data-ttu-id="e5514-154">Целевые платформы в [`Microsoft.NET.Sdk.Web`](https://github.com/aspnet/websdk) включают в себя манифесты, ссылающиеся на неявное хранилище пакетов в целевой системе.</span><span class="sxs-lookup"><span data-stu-id="e5514-154">The targets in [`Microsoft.NET.Sdk.Web`](https://github.com/aspnet/websdk) include manifests referencing the implicit package store on the target system.</span></span> <span data-ttu-id="e5514-155">Кроме того, если зависящее от среды выполнения приложение зависит от пакета `Microsoft.AspNetCore.All`, опубликованное приложение будет содержать только приложение и его ресурсы, но не пакеты, перечисленные в метапакете `Microsoft.AspNetCore.All`.</span><span class="sxs-lookup"><span data-stu-id="e5514-155">Additionally, any runtime-dependent app that depends on the `Microsoft.AspNetCore.All` package results in a published app that contains only the app and its assets and not the packages listed in the `Microsoft.AspNetCore.All` metapackage.</span></span> <span data-ttu-id="e5514-156">Предполагается, что эти пакеты имеются в целевой системе.</span><span class="sxs-lookup"><span data-stu-id="e5514-156">It's assumed that those packages are present on the target system.</span></span>

<span data-ttu-id="e5514-157">Хранилище пакетов среды выполнения устанавливается на узле при установке пакета SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e5514-157">The runtime package store is installed on the host when the .NET Core SDK is installed.</span></span> <span data-ttu-id="e5514-158">Другие установщики также могут предоставлять хранилище пакетов среды выполнения. Сюда относятся установки пакета SDK для .NET Core из архива Zip или Tarball, `apt-get`, Red Hat Yum, пакет .NET Core Windows Server Hosting и установки хранилища пакетов среды выполнения, осуществленные вручную.</span><span class="sxs-lookup"><span data-stu-id="e5514-158">Other installers may provide the runtime package store, including Zip/tarball installations of the .NET Core SDK, `apt-get`, Red Hat Yum, the .NET Core Windows Server Hosting bundle, and manual runtime package store installations.</span></span>

<span data-ttu-id="e5514-159">При развертывании приложения с [зависящим от среды выполнения развертыванием](index.md#publish-runtime-dependent) в целевой среде должен быть установлен пакет SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e5514-159">When deploying a [runtime-dependent deployment](index.md#publish-runtime-dependent) app, make sure that the target environment has the .NET Core SDK installed.</span></span> <span data-ttu-id="e5514-160">Если приложение развертывается в среде, в которой нет ASP.NET Core, можно отказаться от использования неявного хранилища, указав параметр **\<PublishWithAspNetCoreTargetManifest>** со значением `false` в файле проекта, как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="e5514-160">If the app is deployed to an environment that doesn't include ASP.NET Core, you can opt out of the implicit store by specifying  **\<PublishWithAspNetCoreTargetManifest>** set to `false` in the project file as in the following example:</span></span>

```xml
<PropertyGroup>
  <PublishWithAspNetCoreTargetManifest>false</PublishWithAspNetCoreTargetManifest>
</PropertyGroup>
```

> [!NOTE]
> <span data-ttu-id="e5514-161">В случае с приложениями с [автономным развертыванием](index.md#publish-self-contained) предполагается, что в целевой системе необязательно имеются требуемые пакеты манифеста.</span><span class="sxs-lookup"><span data-stu-id="e5514-161">For [self-contained deployment](index.md#publish-self-contained) apps, it's assumed that the target system doesn't necessarily contain the required manifest packages.</span></span> <span data-ttu-id="e5514-162">Поэтому для автономного приложения параметру **\<PublishWithAspNetCoreTargetManifest>** нельзя присвоить значение `true`.</span><span class="sxs-lookup"><span data-stu-id="e5514-162">Therefore, **\<PublishWithAspNetCoreTargetManifest>** cannot be set to `true` for an self-contained app.</span></span>

## <a name="see-also"></a><span data-ttu-id="e5514-163">См. также</span><span class="sxs-lookup"><span data-stu-id="e5514-163">See also</span></span>

- [<span data-ttu-id="e5514-164">dotnet-publish</span><span class="sxs-lookup"><span data-stu-id="e5514-164">dotnet-publish</span></span>](../tools/dotnet-publish.md)
- [<span data-ttu-id="e5514-165">dotnet-store</span><span class="sxs-lookup"><span data-stu-id="e5514-165">dotnet-store</span></span>](../tools/dotnet-store.md)
