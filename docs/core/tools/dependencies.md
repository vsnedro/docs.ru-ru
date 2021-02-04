---
title: Управление зависимостями в .NET
description: Сведения об управлении зависимостями проекта для приложения .NET.
no-loc:
- dotnet add package
- dotnet remove package
- dotnet list package
ms.topic: how-to
ms.date: 01/28/2021
ms.openlocfilehash: 9f5f814d0b4dc7aa3ff1a938c172475169a55bf2
ms.sourcegitcommit: 68c9d9d9a97aab3b59d388914004b5474cf1dbd7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99216132"
---
# <a name="manage-dependencies-in-net-applications"></a>Управление зависимостями в приложениях .NET

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

Зависимость в предыдущем примере будет допустимой только при сборке для указанного целевого объекта. Элемент `$(TargetFramework)` в этом условии представляет собой задаваемое в проекте свойство MSBuild. Для наиболее распространенных приложений .NET это не требуется.

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
