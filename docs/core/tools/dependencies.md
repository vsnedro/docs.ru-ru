---
title: Управление зависимостями в .NET Core
description: Сведения об управлении зависимостями проекта для приложения .NET Core.
no-loc:
- dotnet add package
- dotnet remove package
- dotnet list package
ms.topic: how-to
ms.date: 02/25/2020
ms.openlocfilehash: 2aeedb56f774b51076764c2772eb02b2fa095d92
ms.sourcegitcommit: 7476c20d2f911a834a00b8a7f5e8926bae6804d9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/11/2020
ms.locfileid: "88062864"
---
# <a name="manage-dependencies-in-net-core-applications"></a>Управление зависимостями в приложениях .NET Core

Эта статья описывает, как добавлять и удалять зависимости путем изменения файла проекта или с помощью интерфейса командной строки.

## <a name="the-packagereference-element"></a>элемент \<PackageReference>;

Элемент файла проекта `<PackageReference>` имеет следующую структуру:

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" />
```

Атрибут `Include` указывает идентификатор пакета, добавляемого в проект. Атрибут `Version` указывает версию, которую необходимо получить. Версии указываются в соответствии с [правилами версий NuGet](/nuget/create-packages/dependency-versions#version-ranges).

> [!NOTE]
> Если вы не знакомы с синтаксисом файла проекта, см. дополнительные сведения в [справочной документации по проектам MSBuild](/visualstudio/msbuild/msbuild-project-file-schema-reference).

Зависимость, доступная только в конкретном целевом объекте, добавляется с использованием условий, как показано в следующем примере:

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" Condition="'$(TargetFramework)' == 'netcoreapp2.1'" />
```

Зависимость в предыдущем примере будет допустимой только при сборке для указанного целевого объекта. Элемент `$(TargetFramework)` в этом условии представляет собой задаваемое в проекте свойство MSBuild. Для наиболее распространенных приложений .NET Core это не требуется.

## <a name="add-a-dependency-by-editing-the-project-file"></a>Добавление зависимости путем изменения файла проекта

Чтобы добавить зависимость, добавьте элемент `<PackageReference>` внутрь элемента `<ItemGroup>`. Можно добавить существующий элемент `<ItemGroup>` или создать новый. В следующем примере используется проект консольного приложения по умолчанию, созданный с помощью `dotnet new console`:

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

## <a name="add-a-dependency-by-using-the-cli"></a>Добавление зависимости с помощью интерфейса командной строки

Чтобы добавить зависимость, выполните команду [dotnet add package](dotnet-add-package.md), как показано в следующем примере:

```dotnetcli
dotnet add package Microsoft.EntityFrameworkCore
```

## <a name="remove-a-dependency-by-editing-the-project-file"></a>Удаление зависимости путем изменения файла проекта

Чтобы удалить зависимость, удалите ее элемент `<PackageReference>` из файла проекта.

## <a name="remove-a-dependency-by-using-the-cli"></a>Удаление зависимости с помощью интерфейса командной строки

Чтобы удалить зависимость, выполните команду [dotnet remove package](dotnet-remove-package.md), как показано в следующем примере:

```dotnetcli
dotnet remove package Microsoft.EntityFrameworkCore
```

## <a name="see-also"></a>См. также

* [Ссылки на пакеты в файлах проекта](../project-sdk/msbuild-props.md#reference-properties-and-items)
* [Команда dotnet list package](dotnet-list-package.md)
