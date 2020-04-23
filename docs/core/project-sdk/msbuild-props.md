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
# <a name="msbuild-properties-for-net-core-sdk-projects"></a>Свойства MSBuild для проектов пакета SDK для .NET Core

На этой странице описываются свойства MSBuild для настройки проектов .NET Core.

> [!NOTE]
> Работа над этой страницей еще не завершена, поэтому здесь приведены лишь некоторые полезные свойства MSBuild для пакета SDK для .NET Core. Список стандартных свойств см. в статье [Общие свойства MSBuild](/visualstudio/msbuild/common-msbuild-project-properties).

## <a name="framework-properties"></a>Свойства платформы

- [TargetFramework](#targetframework)
- [TargetFrameworks](#targetframeworks)
- [NetStandardImplicitPackageVersion](#netstandardimplicitpackageversion)

### <a name="targetframework"></a>TargetFramework

Свойство `TargetFramework` указывает версию целевой платформы для приложения, которая неявно ссылается на [метапакет](../packages.md#metapackages). Список допустимых моникеров целевой платформы см. в статье [Целевые платформы в проектах в стиле SDK](../../standard/frameworks.md#supported-target-framework-versions).

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>netcoreapp3.1</TargetFramework>
  </PropertyGroup>
</Project>
```

Дополнительные сведения см.в статье [Целевые платформы в проектах в стиле SDK](../../standard/frameworks.md).

### <a name="targetframeworks"></a>TargetFrameworks

Используйте свойство `TargetFrameworks`, если приложение должно быть предназначено для нескольких платформ. Список допустимых моникеров целевой платформы см. в статье [Целевые платформы в проектах в стиле SDK](../../standard/frameworks.md#supported-target-framework-versions).

> [!NOTE]
> Это свойство игнорируется, если указано свойство `TargetFramework` (в единственном числе).

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFrameworks>netcoreapp3.1;net462</TargetFrameworks>
  </PropertyGroup>
</Project>
```

Дополнительные сведения см.в статье [Целевые платформы в проектах в стиле SDK](../../standard/frameworks.md).

### <a name="netstandardimplicitpackageversion"></a>NetStandardImplicitPackageVersion

> [!NOTE]
> Это свойство применяется только к проектам, использующим `netstandard1.x`. Он не применяется к проектам, использующим `netstandard2.x`.

Используйте свойство `NetStandardImplicitPackageVersion`, если требуется указать версию платформы ниже версии [метапакета](../packages.md#metapackages). Файл проекта, приведенный в следующем примере, предназначен для `netstandard1.3`, но использует `NETStandard.Library` версии 1.6.0.

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>netstandard1.3</TargetFramework>
    <NetStandardImplicitPackageVersion>1.6.0</NetStandardImplicitPackageVersion>
  </PropertyGroup>
</Project>
```

## <a name="publish-properties"></a>Параметры публикации

- [RuntimeIdentifier](#runtimeidentifier)
- [RuntimeIdentifiers](#runtimeidentifiers)
- [UseAppHost](#useapphost)

### <a name="runtimeidentifier"></a>RuntimeIdentifier

Свойство `RuntimeIdentifier` позволяет указать для проекта один [идентификатор среды выполнения (RID)](../rid-catalog.md). Идентификатор среды выполнения позволяет опубликовать автономное развертывание.

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <RuntimeIdentifier>ubuntu.16.04-x64</RuntimeIdentifier>
  </PropertyGroup>
</Project>
```

### <a name="runtimeidentifiers"></a>RuntimeIdentifiers

Свойство `RuntimeIdentifiers` позволяет указать для проекта список [идентификаторов среды выполнения (RID)](../rid-catalog.md) (в качестве разделителя используется точка с запятой). Используйте это свойство, если вам нужна публикация для нескольких сред. `RuntimeIdentifiers` используется во время восстановления для обеспечения наличия в графе нужных ресурсов.

> [!TIP]
> `RuntimeIdentifier` (в единственном числе) может ускорить создание сборок, когда требуется только одна среда выполнения.

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <RuntimeIdentifiers>win10-x64;osx.10.11-x64;ubuntu.16.04-x64</RuntimeIdentifiers>
  </PropertyGroup>
</Project>
```

### <a name="useapphost"></a>UseAppHost

Свойство `UseAppHost` было представлено в пакете SDK для .NET Core.версии 2.1.400. Оно контролирует создание собственного исполняемого файла для развертывания. Этот файл требуется для автономных развертываний.

В .NET Core 3.0 и более поздних версиях зависимый от платформы исполняемый файл создается по умолчанию. Задайте свойству `UseAppHost` значение `false`, чтобы отключить создание исполняемого файла.

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <UseAppHost>false</UseAppHost>
  </PropertyGroup>
</Project>
```

Дополнительные сведения о развертывании см. в статье [Развертывание приложений .NET Core](../deploying/index.md).

## <a name="compile-properties"></a>Свойства компиляции

### <a name="langversion"></a>LangVersion

Свойство `LangVersion` позволяет указать конкретную версию языка программирования. Например, если требуется доступ к предварительным версиям функций C#, задайте параметру `LangVersion` значение `preview`.

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <LangVersion>preview</LangVersion>
  </PropertyGroup>
</Project>
```

Дополнительные сведения см. в статье [Управление версиями языка C#](../../csharp/language-reference/configure-language-version.md#override-a-default).

## <a name="nuget-packages"></a>Пакеты NuGet

- [PackageReference](#packagereference)
- [AssetTargetFallback](#assettargetfallback)

### <a name="packagereference"></a>PackageReference

Элемент `PackageReference` позволяет указать зависимость NuGet. Например, может потребоваться сослаться на один пакет, а не на [метапакет](../packages.md#metapackages). Атрибут `Include` указывает идентификатор пакета. Фрагмент файла проекта в следующем примере ссылается на пакет [System.Runtime](https://www.nuget.org/packages/System.Runtime/).

```xml
<Project Sdk="Microsoft.NET.Sdk">
  ...
  <ItemGroup>
    <PackageReference Include="System.Runtime" Version="4.3.0" />
  </ItemGroup>
</Project>
```

Дополнительные сведения см. в статье [Ссылки на пакеты в файлах проекта](/nuget/consume-packages/package-references-in-project-files).

### <a name="assettargetfallback"></a>AssetTargetFallback

Свойство `AssetTargetFallback` позволяет указать дополнительные совместимые версии платформы для проектов, на которые ссылается ваш проект, и пакеты NuGet, используемые в проекте. Например, если вы указали зависимость пакета с помощью `PackageReference`, но в этом пакете нет ресурсов, совместимых с `TargetFramework` вашего проекта, тогда пригодится свойство `AssetTargetFallback`. Совместимость пакета, на который указывает ссылка, повторно проверяется с помощью каждой целевой платформы, указанной в свойстве `AssetTargetFallback`.

В качестве значения свойства `AssetTargetFallback` можно задать одну [версию целевой платформы](../../standard/frameworks.md#supported-target-framework-versions) или несколько.

```xml
<Project Sdk="Microsoft.NET.Sdk">
  ...
  <PropertyGroup>
    <AssetTargetFallback>net461</AssetTargetFallback>
  </PropertyGroup>
</Project>
```

### <a name="pack-and-restore-targets"></a>Целевые объекты pack и restore

В MSBuild 15.1 появились целевые объекты `pack` и `restore` для создания и восстановления пакетов NuGet в составе сборки. Сведения о свойствах MSBuild для этих целевых объектов, включая `PackageTargetFallback`, см. в статье [Объекты pack и restore NuGet в качестве целевых объектов MSBuild](/nuget/reference/msbuild-targets).

## <a name="see-also"></a>См. также

- [Справочник по схеме MSBuild](/visualstudio/msbuild/msbuild-project-file-schema-reference)
- [Общие свойства MSBuild](/visualstudio/msbuild/common-msbuild-project-properties)
- [Свойства MSBuild для целевого объекта pack NuGet](/nuget/reference/msbuild-targets#pack-target)
- [Свойства MSBuild для целевого объекта restore NuGet](/nuget/reference/msbuild-targets#restore-properties)
- [Настройка сборки](/visualstudio/msbuild/customize-your-build)
