---
title: Установка шаблонов SDK и управление ими — .NET Core
description: Сведения об установке шаблонов .NET Core в Windows, Linux и macOS.
author: adegeo
ms.author: adegeo
ms.date: 04/24/2020
zone_pivot_groups: operating-systems-set-one
no-loc:
- dotnet new
- dotnet nuget add source
ms.openlocfilehash: 09acae1409eb0492be10bd3a61b14da5be57c6c7
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/24/2020
ms.locfileid: "85324498"
---
# <a name="manage-net-project-and-item-templates"></a><span data-ttu-id="b6cfd-103">Создание шаблонов проектов и элементов .NET</span><span class="sxs-lookup"><span data-stu-id="b6cfd-103">Manage .NET project and item templates</span></span>

<span data-ttu-id="b6cfd-104">.NET Core предоставляет систему шаблонов, которая позволяет пользователям устанавливать или удалять шаблоны из NuGet, файла пакета NuGet или каталога файловой системы.</span><span class="sxs-lookup"><span data-stu-id="b6cfd-104">.NET Core provides a template system that enables users to install or uninstall templates from NuGet, a NuGet package file, or a file system directory.</span></span> <span data-ttu-id="b6cfd-105">В этой статье описывается, как управлять шаблонами .NET Core с помощью интерфейса командной строки пакета SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="b6cfd-105">This article describes how to manage .NET Core templates through the .NET Core SDK CLI.</span></span>

<span data-ttu-id="b6cfd-106">Дополнительные сведения о создании шаблонов см. в [руководстве по созданию шаблонов](../tutorials/cli-templates-create-item-template.md).</span><span class="sxs-lookup"><span data-stu-id="b6cfd-106">For more information about creating templates, see [Tutorial: Create templates](../tutorials/cli-templates-create-item-template.md).</span></span>

## <a name="install-template"></a><span data-ttu-id="b6cfd-107">Установка шаблонов</span><span class="sxs-lookup"><span data-stu-id="b6cfd-107">Install template</span></span>

<span data-ttu-id="b6cfd-108">Шаблоны устанавливаются с помощью команды SDK [dotnet new](../tools/dotnet-new.md) с параметром `-i`.</span><span class="sxs-lookup"><span data-stu-id="b6cfd-108">Templates are installed through the [dotnet new](../tools/dotnet-new.md) SDK command with the `-i` parameter.</span></span> <span data-ttu-id="b6cfd-109">Можно указать идентификатор пакета NuGet шаблона или папку, содержащую файлы шаблонов.</span><span class="sxs-lookup"><span data-stu-id="b6cfd-109">You can either provide the NuGet package identifier of a template, or a folder that contains the template files.</span></span>

### <a name="nuget-hosted-package"></a><span data-ttu-id="b6cfd-110">Размещенный пакет NuGet</span><span class="sxs-lookup"><span data-stu-id="b6cfd-110">NuGet hosted package</span></span>

<span data-ttu-id="b6cfd-111">Шаблоны .NET CLI передаются в [NuGet](https://www.nuget.org/) для широкого распространения.</span><span class="sxs-lookup"><span data-stu-id="b6cfd-111">.NET CLI templates are uploaded to [NuGet](https://www.nuget.org/) for wide distribution.</span></span> <span data-ttu-id="b6cfd-112">Шаблоны также можно установить из частного веб-канала.</span><span class="sxs-lookup"><span data-stu-id="b6cfd-112">Templates can also be installed from a private feed.</span></span> <span data-ttu-id="b6cfd-113">Вместо отправки шаблона в веб-канал NuGet файлы шаблонов *nupkg* можно распространять и устанавливать вручную, как описано в разделе [Локальный пакет NuGet](#local-nuget-package).</span><span class="sxs-lookup"><span data-stu-id="b6cfd-113">Instead of uploading a template to a NuGet feed, *nupkg* template files can be distributed and manually installed, as described in the [Local NuGet package](#local-nuget-package) section.</span></span>

<span data-ttu-id="b6cfd-114">Для получения дополнительных сведений о настройке веб-каналов NuGet см. [dotnet nuget add source](../tools/dotnet-nuget-add-source.md).</span><span class="sxs-lookup"><span data-stu-id="b6cfd-114">For more information about configuring NuGet feeds, see [dotnet nuget add source](../tools/dotnet-nuget-add-source.md).</span></span>

<span data-ttu-id="b6cfd-115">Чтобы установить пакет шаблона из веб-канала NuGet по умолчанию, используйте команду `dotnet new -i {package-id}`:</span><span class="sxs-lookup"><span data-stu-id="b6cfd-115">To install a template pack from the default NuGet feed, use the `dotnet new -i {package-id}` command:</span></span>

```dotnetcli
dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates
```

<span data-ttu-id="b6cfd-116">Чтобы установить пакет шаблона из веб-канала NuGet по умолчанию с конкретной версией, используйте команду `dotnet new -i {package-id}::{version}`:</span><span class="sxs-lookup"><span data-stu-id="b6cfd-116">To install a template pack from the default NuGet feed with a specific version, use the `dotnet new -i {package-id}::{version}` command:</span></span>

```dotnetcli
dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.2.6
```

### <a name="local-nuget-package"></a><span data-ttu-id="b6cfd-117">Локальный пакет NuGet</span><span class="sxs-lookup"><span data-stu-id="b6cfd-117">Local NuGet package</span></span>

<span data-ttu-id="b6cfd-118">При создании пакета шаблона создается файл *nupkg*.</span><span class="sxs-lookup"><span data-stu-id="b6cfd-118">When a template pack is created, a *nupkg* file is generated.</span></span> <span data-ttu-id="b6cfd-119">Если у вас есть файл *nupkg*, содержащий шаблоны, его можно установить с помощью команды `dotnet new -i {path-to-package}`:</span><span class="sxs-lookup"><span data-stu-id="b6cfd-119">If you have a *nupkg* file containing templates, you can install it with the `dotnet new -i {path-to-package}` command:</span></span>

::: zone pivot="os-windows"

```dotnetcli
dotnet new -i c:\code\nuget-packages\Some.Templates.1.0.0.nupkg
```

::: zone-end

::: zone pivot="os-linux,os-macos"

```dotnetcli
dotnet new -i ~/code/nuget-packages/Some.Templates.1.0.0.nupkg
```

::: zone-end

### <a name="folder"></a><span data-ttu-id="b6cfd-120">Папка</span><span class="sxs-lookup"><span data-stu-id="b6cfd-120">Folder</span></span>

<span data-ttu-id="b6cfd-121">В качестве альтернативы установке шаблона из файла *nupkg* можно также установить шаблоны из папки напрямую с помощью команды `dotnet new -i {folder-path}`.</span><span class="sxs-lookup"><span data-stu-id="b6cfd-121">As an alternative to installing template from a *nupkg* file, you can also install templates from a folder directly with the `dotnet new -i {folder-path}` command.</span></span> <span data-ttu-id="b6cfd-122">Указанная папка считается идентификатором пакета шаблона для любого найденного шаблона.</span><span class="sxs-lookup"><span data-stu-id="b6cfd-122">The folder specified is treated as the template pack identifier for any template found.</span></span> <span data-ttu-id="b6cfd-123">Любой шаблон, найденный в иерархии указанной папки, устанавливается.</span><span class="sxs-lookup"><span data-stu-id="b6cfd-123">Any template found in the specified folder's hierarchy is installed.</span></span>

::: zone pivot="os-windows"

```dotnetcli
dotnet new -i c:\code\nuget-packages\some-folder\
```

::: zone-end

::: zone pivot="os-linux,os-macos"

```dotnetcli
dotnet new -i ~/code/nuget-packages/some-folder/
```

::: zone-end

<span data-ttu-id="b6cfd-124">`{folder-path}`, указанный в команде, становится идентификатором пакета шаблона для всех найденных шаблонов.</span><span class="sxs-lookup"><span data-stu-id="b6cfd-124">The `{folder-path}` specified on the command becomes the template pack identifier for all templates found.</span></span> <span data-ttu-id="b6cfd-125">Как указано в разделе [Список шаблонов](#list-templates), можно получить список установленных шаблонов с помощью команды `dotnet new -u`.</span><span class="sxs-lookup"><span data-stu-id="b6cfd-125">As specified in the [List templates](#list-templates) section, you can get a list of templates installed with the `dotnet new -u` command.</span></span> <span data-ttu-id="b6cfd-126">В этом примере идентификатор пакета шаблона отображается как папка, используемая для установки:</span><span class="sxs-lookup"><span data-stu-id="b6cfd-126">In this example, the template pack identifier is shown as the folder used for install:</span></span>

::: zone pivot="os-windows"

```console
dotnet new -u
Template Instantiation Commands for .NET Core CLI

Currently installed items:

... cut to save space ...

  c:\code\nuget-packages\some-folder
    Templates:
      A Template Console Class (templateconsole) C#
      Project for some technology (contosoproject) C#
    Uninstall Command:
      dotnet new -u c:\code\nuget-packages\some-folder
```

::: zone-end

::: zone pivot="os-linux,os-macos"

```console
dotnet new -u
Template Instantiation Commands for .NET Core CLI

Currently installed items:

... cut to save space ...

  /home/username/code/templates
    Templates:
      A Template Console Class (templateconsole) C#
      Project for some technology (contosoproject) C#
    Uninstall Command:
      dotnet new -u /home/username/code/templates
```

::: zone-end

## <a name="uninstall-template"></a><span data-ttu-id="b6cfd-127">Удаление шаблона</span><span class="sxs-lookup"><span data-stu-id="b6cfd-127">Uninstall template</span></span>

<span data-ttu-id="b6cfd-128">Шаблоны удаляются с помощью команды SDK [dotnet new](../tools/dotnet-new.md) с параметром `-u`.</span><span class="sxs-lookup"><span data-stu-id="b6cfd-128">Templates are uninstalled through the [dotnet new](../tools/dotnet-new.md) SDK command with the `-u` parameter.</span></span> <span data-ttu-id="b6cfd-129">Можно указать идентификатор пакета NuGet шаблона или папку, содержащую файлы шаблонов.</span><span class="sxs-lookup"><span data-stu-id="b6cfd-129">You can either provide the NuGet package identifier of a template, or a folder that contains the template files.</span></span>

### <a name="nuget-package"></a><span data-ttu-id="b6cfd-130">Пакет NuGet</span><span class="sxs-lookup"><span data-stu-id="b6cfd-130">NuGet package</span></span>

<span data-ttu-id="b6cfd-131">После установки пакета шаблона NuGet из веб-канала NuGet или файла *nupkg* можно удалить его, сославшись на идентификатор пакета NuGet.</span><span class="sxs-lookup"><span data-stu-id="b6cfd-131">After a NuGet template pack is installed, either from a NuGet feed or a *nupkg* file, you can uninstall it by referencing the NuGet package identifier.</span></span>

<span data-ttu-id="b6cfd-132">Чтобы удалить пакет шаблона, используйте команду `dotnet new -u {package-id}`:</span><span class="sxs-lookup"><span data-stu-id="b6cfd-132">To uninstall a template pack, use the `dotnet new -u {package-id}` command:</span></span>

```dotnetcli
dotnet new -u Microsoft.DotNet.Web.Spa.ProjectTemplates
```

### <a name="folder"></a><span data-ttu-id="b6cfd-133">Папка</span><span class="sxs-lookup"><span data-stu-id="b6cfd-133">Folder</span></span>

<span data-ttu-id="b6cfd-134">При установке шаблонов с помощью [пути к папке](#folder) путь к папке становится идентификатором пакета шаблона.</span><span class="sxs-lookup"><span data-stu-id="b6cfd-134">When templates are installed through a [folder path](#folder), the folder path becomes the template pack identifier.</span></span>

<span data-ttu-id="b6cfd-135">Чтобы удалить пакет шаблона, используйте команду `dotnet new -u {package-folder-path}`:</span><span class="sxs-lookup"><span data-stu-id="b6cfd-135">To uninstall a template pack, use the `dotnet new -u {package-folder-path}` command:</span></span>

::: zone pivot="os-windows"

```dotnetcli
dotnet new -u c:\code\nuget-packages\some-folder
```

::: zone-end

::: zone pivot="os-linux,os-macos"

```dotnetcli
dotnet new -u /home/username/code/templates
```

::: zone-end

## <a name="list-templates"></a><span data-ttu-id="b6cfd-136">Список шаблонов</span><span class="sxs-lookup"><span data-stu-id="b6cfd-136">List templates</span></span>

<span data-ttu-id="b6cfd-137">Используя стандартную команду удаления без идентификатора пакета, можно просмотреть список установленных шаблонов вместе с командой, которая удаляет каждый шаблон.</span><span class="sxs-lookup"><span data-stu-id="b6cfd-137">By using the standard uninstall command without a package identifier, you can see a list of installed templates along with the command that uninstalls each template.</span></span>

```console
dotnet new -u
Template Instantiation Commands for .NET Core CLI

Currently installed items:

... cut to save space ...

  c:\code\nuget-packages\some-folder
    Templates:
      A Template Console Class (templateconsole) C#
      Project for some technology (contosoproject) C#
    Uninstall Command:
      dotnet new -u c:\code\nuget-packages\some-folder
```

## <a name="install-templates-from-other-sdks"></a><span data-ttu-id="b6cfd-138">Установка шаблонов из других пакетов SDK</span><span class="sxs-lookup"><span data-stu-id="b6cfd-138">Install templates from other SDKs</span></span>

<span data-ttu-id="b6cfd-139">Если вы установили каждую версию пакета SDK последовательно, например пакет SDK 2.0, пакет SDK 2.1 и т. д., у вас будут установлены все шаблоны пакета SDK.</span><span class="sxs-lookup"><span data-stu-id="b6cfd-139">If you've installed each version of the SDK sequentially, for example you installed SDK 2.0, then SDK 2.1, and so on, you'll have every SDK's templates installed.</span></span> <span data-ttu-id="b6cfd-140">Однако если начать с более поздней версии пакета SDK, например 3.1, будут включены только шаблоны для [выпусков LTS (долгосрочная поддержка)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core), и на момент выпуска пакета SDK 3.1 это пакет SDK 2.1 и пакет SDK 3.1.</span><span class="sxs-lookup"><span data-stu-id="b6cfd-140">However, if you start with a later SDK version, like 3.1, only the templates for [LTS (long term support) releases](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) are included, which at the time of the SDK 3.1 release is SDK 2.1 and SDK 3.1.</span></span> <span data-ttu-id="b6cfd-141">Шаблоны для любого другого выпуска не включаются.</span><span class="sxs-lookup"><span data-stu-id="b6cfd-141">Templates for any other release aren't included.</span></span>

<span data-ttu-id="b6cfd-142">Шаблоны .NET Core доступны в NuGet, и их можно установить как любые другие шаблоны.</span><span class="sxs-lookup"><span data-stu-id="b6cfd-142">The .NET Core templates are available on NuGet, and you can install them like any other template.</span></span> <span data-ttu-id="b6cfd-143">Дополнительные сведения см. в разделе [Установка размещенного пакета NuGet](#nuget-hosted-package).</span><span class="sxs-lookup"><span data-stu-id="b6cfd-143">For more information, see [Install NuGet hosted package](#nuget-hosted-package).</span></span>

| <span data-ttu-id="b6cfd-144">SDK</span><span class="sxs-lookup"><span data-stu-id="b6cfd-144">SDK</span></span>              | <span data-ttu-id="b6cfd-145">Идентификатор пакета NuGet</span><span class="sxs-lookup"><span data-stu-id="b6cfd-145">NuGet Package Identifier</span></span>                                                                                                      |
|------------------|-------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="b6cfd-146">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="b6cfd-146">.NET Core 2.1</span></span>    | [`Microsoft.DotNet.Common.ProjectTemplates.2.1`](https://www.nuget.org/packages/Microsoft.DotNet.Common.ProjectTemplates.2.1) |
| <span data-ttu-id="b6cfd-147">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="b6cfd-147">.NET Core 2.2</span></span>    | [`Microsoft.DotNet.Common.ProjectTemplates.2.2`](https://www.nuget.org/packages/Microsoft.DotNet.Common.ProjectTemplates.2.2) |
| <span data-ttu-id="b6cfd-148">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="b6cfd-148">.NET Core 3.0</span></span>    | [`Microsoft.DotNet.Common.ProjectTemplates.3.0`](https://www.nuget.org/packages/Microsoft.DotNet.Common.ProjectTemplates.3.0) |
| <span data-ttu-id="b6cfd-149">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="b6cfd-149">.NET Core 3.1</span></span>    | [`Microsoft.DotNet.Common.ProjectTemplates.3.1`](https://www.nuget.org/packages/Microsoft.DotNet.Common.ProjectTemplates.3.1) |
| <span data-ttu-id="b6cfd-150">ASP.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="b6cfd-150">ASP.NET Core 2.1</span></span> | [`Microsoft.DotNet.Web.ProjectTemplates.2.1`](https://www.nuget.org/packages/Microsoft.DotNet.Web.ProjectTemplates.2.1)       |
| <span data-ttu-id="b6cfd-151">ASP.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="b6cfd-151">ASP.NET Core 2.2</span></span> | [`Microsoft.DotNet.Web.ProjectTemplates.2.2`](https://www.nuget.org/packages/Microsoft.DotNet.Web.ProjectTemplates.2.2)       |
| <span data-ttu-id="b6cfd-152">ASP.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="b6cfd-152">ASP.NET Core 3.0</span></span> | [`Microsoft.DotNet.Web.ProjectTemplates.3.0`](https://www.nuget.org/packages/Microsoft.DotNet.Web.ProjectTemplates.3.0)       |
| <span data-ttu-id="b6cfd-153">ASP.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="b6cfd-153">ASP.NET Core 3.1</span></span> | [`Microsoft.DotNet.Web.ProjectTemplates.3.1`](https://www.nuget.org/packages/Microsoft.DotNet.Web.ProjectTemplates.3.1)       |

<span data-ttu-id="b6cfd-154">Например, пакет SDK для .NET Core включает шаблоны для консольного приложения, предназначенного для .NET Core 2.1 и .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="b6cfd-154">For example, the .NET Core SDK includes templates for a console app targeting .NET Core 2.1 and .NET Core 3.1.</span></span> <span data-ttu-id="b6cfd-155">Если ваша целевая версия — .NET Core 3.0, необходимо установить шаблоны 3.0.</span><span class="sxs-lookup"><span data-stu-id="b6cfd-155">If you wanted to target .NET Core 3.0, you would need to install the 3.0 templates.</span></span>

01. <span data-ttu-id="b6cfd-156">Попробуйте создать приложение, предназначенное для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="b6cfd-156">Try creating an app that targets .NET Core 3.0.</span></span>

    ```dotnetcli
    dotnet new console --framework netcoreapp3.0
    ```

    <span data-ttu-id="b6cfd-157">Если отображается сообщение об ошибке, необходимо установить шаблоны.</span><span class="sxs-lookup"><span data-stu-id="b6cfd-157">If you see an error message, you need to install the templates.</span></span>

    > <span data-ttu-id="b6cfd-158">Не удалось найти установленный шаблон, соответствующий входным данным, поиск нужного шаблона в Интернете...</span><span class="sxs-lookup"><span data-stu-id="b6cfd-158">Couldn't find an installed template that matches the input, searching online for one that does...</span></span>

01. <span data-ttu-id="b6cfd-159">Установите шаблоны проекта .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="b6cfd-159">Install the .NET Core 3.0 project templates.</span></span>

    ```dotnetcli
    dotnet new -i Microsoft.DotNet.Common.ProjectTemplates.3.0
    ```

01. <span data-ttu-id="b6cfd-160">Попробуйте создать приложение еще раз.</span><span class="sxs-lookup"><span data-stu-id="b6cfd-160">Try creating the app a second time.</span></span>

    ```dotnetcli
    dotnet new console --framework netcoreapp3.0
    ```

    <span data-ttu-id="b6cfd-161">Вы увидите сообщение о том, что проект был создан.</span><span class="sxs-lookup"><span data-stu-id="b6cfd-161">And you should see a message indicating the project was created.</span></span>

    > <span data-ttu-id="b6cfd-162">Шаблон "Консольное приложение" успешно создан.</span><span class="sxs-lookup"><span data-stu-id="b6cfd-162">The template "Console Application" was created successfully.</span></span>
    >
    > <span data-ttu-id="b6cfd-163">Обработка действий после создания... Выполнение dotnet restore для path-to-project-file.csproj... Определение проектов для восстановления... Восстановление завершено за 1,05 с для path-to-project-file.csproj.</span><span class="sxs-lookup"><span data-stu-id="b6cfd-163">Processing post-creation actions... Running 'dotnet restore' on path-to-project-file.csproj... Determining projects to restore... Restore completed in 1.05 sec for path-to-project-file.csproj.</span></span>
    >
    > <span data-ttu-id="b6cfd-164">Восстановление выполнено.</span><span class="sxs-lookup"><span data-stu-id="b6cfd-164">Restore succeeded.</span></span>

## <a name="see-also"></a><span data-ttu-id="b6cfd-165">См. также</span><span class="sxs-lookup"><span data-stu-id="b6cfd-165">See also</span></span>

- [<span data-ttu-id="b6cfd-166">Учебник. Создание шаблона элемента</span><span class="sxs-lookup"><span data-stu-id="b6cfd-166">Tutorial: Create an item template</span></span>](../tutorials/cli-templates-create-item-template.md)
- [dotnet new](../tools/dotnet-new.md)
- [dotnet nuget add source](../tools/dotnet-nuget-add-source.md)
