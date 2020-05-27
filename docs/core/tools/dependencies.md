---
title: ''
description: ''
no-loc:
- dotnet add package
- dotnet remove package
- dotnet list package
ms.date: ''
ms.openlocfilehash: 667b2d4d68edd82a4d18c370e45ea18f4d4b379a
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2020
ms.locfileid: "83702837"
---
# <a name="manage-dependencies-in-net-core-applications"></a><span data-ttu-id="59a3c-101">Управление зависимостями в приложениях .NET Core</span><span class="sxs-lookup"><span data-stu-id="59a3c-101">Manage dependencies in .NET Core applications</span></span>

<span data-ttu-id="59a3c-102">Эта статья описывает, как добавлять и удалять зависимости путем изменения файла проекта или с помощью интерфейса командной строки.</span><span class="sxs-lookup"><span data-stu-id="59a3c-102">This article explains how to add and remove dependencies by editing the project file or by using the CLI.</span></span>

## <a name="the-packagereference-element"></a><span data-ttu-id="59a3c-103">Элемент \<PackageReference></span><span class="sxs-lookup"><span data-stu-id="59a3c-103">The \<PackageReference> element</span></span>

<span data-ttu-id="59a3c-104">Элемент файла проекта `<PackageReference>` имеет следующую структуру:</span><span class="sxs-lookup"><span data-stu-id="59a3c-104">The `<PackageReference>` project file element has the following structure:</span></span>

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" />
```

<span data-ttu-id="59a3c-105">Атрибут `Include` указывает идентификатор пакета, добавляемого в проект.</span><span class="sxs-lookup"><span data-stu-id="59a3c-105">The `Include` attribute specifies the ID of the package to add to the project.</span></span> <span data-ttu-id="59a3c-106">Атрибут `Version` указывает версию, которую необходимо получить.</span><span class="sxs-lookup"><span data-stu-id="59a3c-106">The `Version` attribute specifies the version to get.</span></span> <span data-ttu-id="59a3c-107">Версии указываются в соответствии с [правилами версий NuGet](/nuget/create-packages/dependency-versions#version-ranges).</span><span class="sxs-lookup"><span data-stu-id="59a3c-107">Versions are specified as per [NuGet version rules](/nuget/create-packages/dependency-versions#version-ranges).</span></span>

> [!NOTE]
> <span data-ttu-id="59a3c-108">Если вы не знакомы с синтаксисом файла проекта, см. дополнительные сведения в [справочной документации по проектам MSBuild](/visualstudio/msbuild/msbuild-project-file-schema-reference).</span><span class="sxs-lookup"><span data-stu-id="59a3c-108">If you're not familiar with project-file syntax, see the [MSBuild project reference](/visualstudio/msbuild/msbuild-project-file-schema-reference) documentation for more information.</span></span>

<span data-ttu-id="59a3c-109">Зависимость, доступная только в конкретном целевом объекте, добавляется с использованием условий, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="59a3c-109">Use conditions to add a dependency that's available only in a specific target, as shown in the following example:</span></span>

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" Condition="'$(TargetFramework)' == 'netcoreapp2.1'" />
```

<span data-ttu-id="59a3c-110">Зависимость в предыдущем примере будет допустимой только при сборке для указанного целевого объекта.</span><span class="sxs-lookup"><span data-stu-id="59a3c-110">The dependency in the preceding example will only be valid if the build is happening for that given target.</span></span> <span data-ttu-id="59a3c-111">Элемент `$(TargetFramework)` в этом условии представляет собой задаваемое в проекте свойство MSBuild.</span><span class="sxs-lookup"><span data-stu-id="59a3c-111">The `$(TargetFramework)` in the condition is an MSBuild property that's being set in the project.</span></span> <span data-ttu-id="59a3c-112">Для наиболее распространенных приложений .NET Core это не требуется.</span><span class="sxs-lookup"><span data-stu-id="59a3c-112">For most common .NET Core applications, you don't need to do this.</span></span>

## <a name="add-a-dependency-by-editing-the-project-file"></a><span data-ttu-id="59a3c-113">Добавление зависимости путем изменения файла проекта</span><span class="sxs-lookup"><span data-stu-id="59a3c-113">Add a dependency by editing the project file</span></span>

<span data-ttu-id="59a3c-114">Чтобы добавить зависимость, добавьте элемент `<PackageReference>` внутрь элемента `<ItemGroup>`.</span><span class="sxs-lookup"><span data-stu-id="59a3c-114">To add a dependency, add a `<PackageReference>` element inside an `<ItemGroup>` element.</span></span> <span data-ttu-id="59a3c-115">Можно добавить существующий элемент `<ItemGroup>` или создать новый.</span><span class="sxs-lookup"><span data-stu-id="59a3c-115">You can add to an existing `<ItemGroup>` or create a new one.</span></span> <span data-ttu-id="59a3c-116">В следующем примере используется проект консольного приложения по умолчанию, созданный с помощью `dotnet new console`:</span><span class="sxs-lookup"><span data-stu-id="59a3c-116">The following example uses the default console application project that's created by `dotnet new console`:</span></span>

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

## <a name="add-a-dependency-by-using-the-cli"></a><span data-ttu-id="59a3c-117">Добавление зависимости с помощью интерфейса командной строки</span><span class="sxs-lookup"><span data-stu-id="59a3c-117">Add a dependency by using the CLI</span></span>

<span data-ttu-id="59a3c-118">Чтобы добавить зависимость, выполните команду [dotnet add package](dotnet-add-package.md), как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="59a3c-118">To add a dependency, run the [dotnet add package](dotnet-add-package.md) command, as shown in the following example:</span></span>

```dotnetcli
dotnet add package Microsoft.EntityFrameworkCore
```

## <a name="remove-a-dependency-by-editing-the-project-file"></a><span data-ttu-id="59a3c-119">Удаление зависимости путем изменения файла проекта</span><span class="sxs-lookup"><span data-stu-id="59a3c-119">Remove a dependency by editing the project file</span></span>

<span data-ttu-id="59a3c-120">Чтобы удалить зависимость, удалите ее элемент `<PackageReference>` из файла проекта.</span><span class="sxs-lookup"><span data-stu-id="59a3c-120">To remove a dependency, remove its `<PackageReference>` element from the project file.</span></span>

## <a name="remove-a-dependency-by-using-the-cli"></a><span data-ttu-id="59a3c-121">Удаление зависимости с помощью интерфейса командной строки</span><span class="sxs-lookup"><span data-stu-id="59a3c-121">Remove a dependency by using the CLI</span></span>

<span data-ttu-id="59a3c-122">Чтобы удалить зависимость, выполните команду [dotnet remove package](dotnet-remove-package.md), как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="59a3c-122">To remove a dependency, run the [dotnet remove package](dotnet-remove-package.md) command, as shown in the following example:</span></span>

```dotnetcli
dotnet remove package Microsoft.EntityFrameworkCore
```

## <a name="see-also"></a><span data-ttu-id="59a3c-123">См. также</span><span class="sxs-lookup"><span data-stu-id="59a3c-123">See also</span></span>

* [<span data-ttu-id="59a3c-124">Ссылки на пакеты в файлах проекта</span><span class="sxs-lookup"><span data-stu-id="59a3c-124">Package references in project files</span></span>](../project-sdk/msbuild-props.md#reference-properties-and-items)
* <span data-ttu-id="59a3c-125">[Команда dotnet list package](dotnet-list-package.md)</span><span class="sxs-lookup"><span data-stu-id="59a3c-125">[dotnet list package command](dotnet-list-package.md)</span></span>
