---
title: Управление зависимостями в .NET Core
description: Сведения об управлении зависимостями проекта для приложения .NET Core.
no-loc:
- dotnet add package
- dotnet remove package
- dotnet list package
ms.date: 02/25/2020
ms.openlocfilehash: 3e1d807ea69e66e31b277a92cd6a1dc0e76531b5
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795551"
---
# <a name="manage-dependencies-in-net-core-applications"></a><span data-ttu-id="3665b-103">Управление зависимостями в приложениях .NET Core</span><span class="sxs-lookup"><span data-stu-id="3665b-103">Manage dependencies in .NET Core applications</span></span>

<span data-ttu-id="3665b-104">Эта статья описывает, как добавлять и удалять зависимости путем изменения файла проекта или с помощью интерфейса командной строки.</span><span class="sxs-lookup"><span data-stu-id="3665b-104">This article explains how to add and remove dependencies by editing the project file or by using the CLI.</span></span>

## <a name="the-packagereference-element"></a><span data-ttu-id="3665b-105">Элемент \<PackageReference></span><span class="sxs-lookup"><span data-stu-id="3665b-105">The \<PackageReference> element</span></span>

<span data-ttu-id="3665b-106">Элемент файла проекта `<PackageReference>` имеет следующую структуру:</span><span class="sxs-lookup"><span data-stu-id="3665b-106">The `<PackageReference>` project file element has the following structure:</span></span>

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" />
```

<span data-ttu-id="3665b-107">Атрибут `Include` указывает идентификатор пакета, добавляемого в проект.</span><span class="sxs-lookup"><span data-stu-id="3665b-107">The `Include` attribute specifies the ID of the package to add to the project.</span></span> <span data-ttu-id="3665b-108">Атрибут `Version` указывает версию, которую необходимо получить.</span><span class="sxs-lookup"><span data-stu-id="3665b-108">The `Version` attribute specifies the version to get.</span></span> <span data-ttu-id="3665b-109">Версии указываются в соответствии с [правилами версий NuGet](/nuget/create-packages/dependency-versions#version-ranges).</span><span class="sxs-lookup"><span data-stu-id="3665b-109">Versions are specified as per [NuGet version rules](/nuget/create-packages/dependency-versions#version-ranges).</span></span>

> [!NOTE]
> <span data-ttu-id="3665b-110">Если вы не знакомы с синтаксисом файла проекта, см. дополнительные сведения в [справочной документации по проектам MSBuild](/visualstudio/msbuild/msbuild-project-file-schema-reference).</span><span class="sxs-lookup"><span data-stu-id="3665b-110">If you're not familiar with project-file syntax, see the [MSBuild project reference](/visualstudio/msbuild/msbuild-project-file-schema-reference) documentation for more information.</span></span>

<span data-ttu-id="3665b-111">Зависимость, доступная только в конкретном целевом объекте, добавляется с использованием условий, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="3665b-111">Use conditions to add a dependency that's available only in a specific target, as shown in the following example:</span></span>

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" Condition="'$(TargetFramework)' == 'netcoreapp2.1'" />
```

<span data-ttu-id="3665b-112">Зависимость в предыдущем примере будет допустимой только при сборке для указанного целевого объекта.</span><span class="sxs-lookup"><span data-stu-id="3665b-112">The dependency in the preceding example will only be valid if the build is happening for that given target.</span></span> <span data-ttu-id="3665b-113">Элемент `$(TargetFramework)` в этом условии представляет собой задаваемое в проекте свойство MSBuild.</span><span class="sxs-lookup"><span data-stu-id="3665b-113">The `$(TargetFramework)` in the condition is an MSBuild property that's being set in the project.</span></span> <span data-ttu-id="3665b-114">Для наиболее распространенных приложений .NET Core это не требуется.</span><span class="sxs-lookup"><span data-stu-id="3665b-114">For most common .NET Core applications, you don't need to do this.</span></span>

## <a name="add-a-dependency-by-editing-the-project-file"></a><span data-ttu-id="3665b-115">Добавление зависимости путем изменения файла проекта</span><span class="sxs-lookup"><span data-stu-id="3665b-115">Add a dependency by editing the project file</span></span>

<span data-ttu-id="3665b-116">Чтобы добавить зависимость, добавьте элемент `<PackageReference>` внутрь элемента `<ItemGroup>`.</span><span class="sxs-lookup"><span data-stu-id="3665b-116">To add a dependency, add a `<PackageReference>` element inside an `<ItemGroup>` element.</span></span> <span data-ttu-id="3665b-117">Можно добавить существующий элемент `<ItemGroup>` или создать новый.</span><span class="sxs-lookup"><span data-stu-id="3665b-117">You can add to an existing `<ItemGroup>` or create a new one.</span></span> <span data-ttu-id="3665b-118">В следующем примере используется проект консольного приложения по умолчанию, созданный с помощью `dotnet new console`:</span><span class="sxs-lookup"><span data-stu-id="3665b-118">The following example uses the default console application project that's created by `dotnet new console`:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">

  <PropertyGroup>
    <TargetFramework>netcoreapp3.1</TargetFramework>
  </PropertyGroup>

  <ItemGroup>
    <PackageReference Include="Microsoft.EntityFrameworkCore" Version="3.1.2" />
  </ItemGroup>

</Project>
```

## <a name="add-a-dependency-by-using-the-cli"></a><span data-ttu-id="3665b-119">Добавление зависимости с помощью интерфейса командной строки</span><span class="sxs-lookup"><span data-stu-id="3665b-119">Add a dependency by using the CLI</span></span>

<span data-ttu-id="3665b-120">Чтобы добавить зависимость, выполните команду [dotnet add package](dotnet-add-package.md), как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="3665b-120">To add a dependency, run the [dotnet add package](dotnet-add-package.md) command, as shown in the following example:</span></span>

```dotnetcli
dotnet add package Microsoft.EntityFrameworkCore
```

## <a name="remove-a-dependency-by-editing-the-project-file"></a><span data-ttu-id="3665b-121">Удаление зависимости путем изменения файла проекта</span><span class="sxs-lookup"><span data-stu-id="3665b-121">Remove a dependency by editing the project file</span></span>

<span data-ttu-id="3665b-122">Чтобы удалить зависимость, удалите ее элемент `<PackageReference>` из файла проекта.</span><span class="sxs-lookup"><span data-stu-id="3665b-122">To remove a dependency, remove its `<PackageReference>` element from the project file.</span></span>

## <a name="remove-a-dependency-by-using-the-cli"></a><span data-ttu-id="3665b-123">Удаление зависимости с помощью интерфейса командной строки</span><span class="sxs-lookup"><span data-stu-id="3665b-123">Remove a dependency by using the CLI</span></span>

<span data-ttu-id="3665b-124">Чтобы удалить зависимость, выполните команду [dotnet remove package](dotnet-remove-package.md), как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="3665b-124">To remove a dependency, run the [dotnet remove package](dotnet-remove-package.md) command, as shown in the following example:</span></span>

```dotnetcli
dotnet remove package Microsoft.EntityFrameworkCore
```

## <a name="see-also"></a><span data-ttu-id="3665b-125">См. также</span><span class="sxs-lookup"><span data-stu-id="3665b-125">See also</span></span>

* [<span data-ttu-id="3665b-126">Ссылки на пакеты в файлах проекта</span><span class="sxs-lookup"><span data-stu-id="3665b-126">Package references in project files</span></span>](../project-sdk/msbuild-props.md#reference-properties)
* <span data-ttu-id="3665b-127">[Команда dotnet list package](dotnet-remove-package.md)</span><span class="sxs-lookup"><span data-stu-id="3665b-127">[dotnet list package command](dotnet-remove-package.md)</span></span>
