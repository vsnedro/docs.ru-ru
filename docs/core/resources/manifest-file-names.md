---
title: Как MSBuild генерирует имена файлов манифеста
description: В статье описываются факторы, влияющие на имя файла манифеста ресурса, создаваемого MSBuild во время компиляции.
ms.date: 05/08/2020
ms.topic: conceptual
ms.openlocfilehash: 383bf6a077b0631e70ddaa4721b20e992127a73c
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "97866393"
---
# <a name="how-resource-manifest-files-are-named"></a>Имена файлов манифестов ресурсов

Когда MSBuild компилирует проект .NET Core, файлы ресурсов XML, имеющие расширение файла *RESX*, преобразуются в двоичные файлы *RESOURCES*. Двоичные файлы внедряются в выходные данные компилятора и могут быть считаны <xref:System.Resources.ResourceManager>. В этой статье описывается, как MSBuild выбирает имя для каждого файла *RESOURCES*.

> [!TIP]
> Если в файл проекта явно добавлен элемент ресурса, который также [включен в глобальные элементы по умолчанию для .NET Core](../project-sdk/overview.md#default-compilation-includes), возникнет ошибка сборки. Чтобы вручную включить файлы ресурсов в качестве элементов `EmbeddedResource`, установите для свойства `EnableDefaultEmbeddedResourceItems` значение false.

## <a name="default-name"></a>Имя по умолчанию

В .NET Core 3.0 и более поздних версиях при соблюдении обоих следующих условий манифесту ресурса присваивается имя по умолчанию.

- Файл ресурсов не включен явным образом в файл проекта как элемент `EmbeddedResource` с метаданными `LogicalName`, `ManifestResourceName` или `DependentUpon`.
- В файле проекта для свойства `EmbeddedResourceUseDependentUponConvention` не задано значение `false`. По умолчанию для свойства задано значение `true`. Дополнительные сведения см. в разделе [EmbeddedResourceUseDependentUponConvention](../project-sdk/msbuild-props.md#embeddedresourceusedependentuponconvention).

Если файл ресурсов совместно расположен с исходным файлом (*CS* или *VB*) с тем же именем корневого файла, то для имени файла манифеста используется полное имя первого типа, определенного в исходном файле. Например, если `MyNamespace.Form1` является первым типом, определенным в *Form1.cs*, а *Form1.cs* хранится вместе с *Form1.resx*, то сгенерированным именем манифеста для этого файла ресурсов будет *MyNamespace.Form1.resources*.

## <a name="logicalname-metadata"></a>Метаданные LogicalName

Если файл ресурсов явно включен в файл проекта в качестве элемента `EmbeddedResource` с метаданными `LogicalName`, в качестве имени манифеста используется значение `LogicalName`. `LogicalName` имеет приоритет над любым другим метаданным или параметром.

Например, имя манифеста для файла ресурсов, определенного в следующем фрагменте файла проекта, — *SomeName.resources*.

```xml
<EmbeddedResource Include="X.resx" LogicalName="SomeName.resources" />
```

-или-

```xml
<EmbeddedResource Include="X.fr-FR.resx" LogicalName="SomeName.resources" />
```

## <a name="manifestresourcename-metadata"></a>Метаданные ManifestResourceName

Если файл ресурсов явно включен в файл проекта как элемент `EmbeddedResource` с метаданными `ManifestResourceName` (и `LogicalName` отсутствует), в качестве имени файла манифеста используется значение `ManifestResourceName` в сочетании с расширением файла *RESOURCES*.

Например, имя манифеста для файла ресурсов, определенного в следующем фрагменте файла проекта, — *SomeName.resources*.

```xml
<EmbeddedResource Include="X.resx" ManifestResourceName="SomeName" />
```

Имя манифеста для файла ресурсов, определенного в следующем фрагменте файла проекта, — *SomeName.fr-FR.resources*.

```xml
<EmbeddedResource Include="X.fr-FR.resx" ManifestResourceName="SomeName.fr-FR" />
```

## <a name="dependentupon-metadata"></a>Метаданные DependentUpon

Если файл ресурсов явно включен в файл проекта как элемент `EmbeddedResource` с метаданными `DependentUpon` (а `LogicalName` и `ManifestResourceName` отсутствуют), то сведения из исходного файла, определенного `DependentUpon`, используются для имени файла манифеста ресурса. В частности, имя первого типа, определенное в исходном файле, используется в имени манифеста следующим образом: *Namespace.Classname\[.Culture].resources*.

Например, имя манифеста для файла ресурсов, определенного в следующем фрагменте файла проекта, — *Namespace.Classname.resources* (где `Namespace.Classname` является первым классом, который определен в *MyTypes.cs*).

```xml
<EmbeddedResource Include="X.resx" DependentUpon="MyTypes.cs">
```

Имя манифеста для файла ресурсов, определенного в следующем фрагменте файла проекта, — *Namespace.Classname.fr-FR.resources* (где `Namespace.Classname` является первым классом, который определен в *MyTypes.cs*).

```xml
<EmbeddedResource Include="X.fr-FR.resx" DependentUpon="MyTypes.cs">
```

## <a name="embeddedresourceusedependentuponconvention-property"></a>Свойство EmbeddedResourceUseDependentUponConvention

Если в файле проекта `EmbeddedResourceUseDependentUponConvention` имеет значение `false`, каждое имя файла манифеста ресурса будет основано на имени корневого пространства имен проекта и относительном пути к файлу *RESX* из корневого каталога проекта. В частности, именем сгенерированного файла манифеста ресурса будет *RootNamespace.RelativePathWithDotsForSlashes.\[Culture.]resources*. Такая же логика применяется при генерировании имен манифестов в версиях .NET Core, предшествующих версии 3.0.

> [!NOTE]
>
> - Если параметр `RootNamespace` не определен, по умолчанию используется имя проекта.
> - Если для элемента `EmbeddedResource` в файле проекта заданы метаданные `LogicalName`, `ManifestResourceName` или `DependentUpon`, это правило именования не применяется к этому файлу ресурсов.

## <a name="see-also"></a>См. также раздел

- [Как работает именование ресурсов манифеста](https://gist.github.com/BenVillalobos/041673b9a73bec60fdc3bf0f86fae62a)
- [Свойства MSBuild для проектов пакета SDK для .NET Core](../project-sdk/msbuild-props.md)
- [Критические изменения MSBuild](../compatibility/msbuild.md)
