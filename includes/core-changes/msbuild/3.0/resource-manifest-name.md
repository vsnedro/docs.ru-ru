---
ms.openlocfilehash: f24a29a00a1bff34a452c43716d76bf72ef277b5
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83206208"
---
### <a name="resource-manifest-file-name-change"></a>Изменение имени файла манифеста для ресурса

Начиная с .NET Core 3.0, в стандартных ситуациях MSBuild создает другие имена файлов манифеста для файлов ресурсов.

#### <a name="version-introduced"></a>Представленная версия

3.0

#### <a name="change-description"></a>Описание изменений

До версии .NET Core 3.0, если для элемента `EmbeddedResource` в файле проекта не были указаны метаданные `LogicalName`, `ManifestResourceName`или `DependentUpon`, платформа MSBuild создавала имя файла манифеста в формате `<RootNamespace>.<ResourceFilePathFromProjectRoot>.resources`. Если в файле проекта не определено значение `RootNamespace`, по умолчанию используется имя проекта. Например, для файла ресурсов с именем *Form1.resx* в корневом каталоге проекта создавался манифест с именем *MyProject.Form1.resources*.

Начиная с версии .NET Core 3.0, при размещении файла ресурса в одной папке с одноименным исходным файлом, (*Form1.resx* и *Form1.cs*), MSBuild использует сведения о типе из исходного файла для создания имени файла манифеста в формате `<Namespace>.<ClassName>.resources`. Пространство имен и имя класса извлекаются из первого типа в исходном файле, найденном в той же папке. Например, для файла ресурсов с именем *Form1.resx*, который расположен в одной папке с исходным файлом *Form1.cs*, создается манифест с именем *MyNamespace.Form1.resources*. Важно отметить, что первая часть имени файла отличается от имени в прежних версиях .NET Core (*MyNamespace* вместо *MyProject*).

> [!NOTE]
> Если для элемента `EmbeddedResource` в файле проекта указаны метаданные `LogicalName`, `ManifestResourceName` или `DependentUpon`, это изменение не применяется к соответствующему файлу ресурсов.

Это критическое изменение было введено одновременно с добавлением свойства `EmbeddedResourceUseDependentUponConvention` для проектов .NET Core. По умолчанию файлы ресурсов не указаны явным образом в файле проекта .NET Core, поэтому в них нет метаданных `DependentUpon`, которые позволяют задать формат именования созданного файла *.resources*. Если `EmbeddedResourceUseDependentUponConvention` имеет значение `true` (используется по умолчанию), MSBuild ищет в той же папке исходный файл и извлекает из этого файла пространство имен и имя класса. Если для `EmbeddedResourceUseDependentUponConvention` задано значение `false`, MSBuild создает имя манифеста по правилам для прежних версий, то есть объединяет `RootNamespace` и относительный путь к файлу.

#### <a name="recommended-action"></a>Рекомендованное действие

В большинстве случаев разработчикам не нужно предпринимать по этому поводу никаких действий, и приложение должно работать нормально. Если же это изменение нарушит работу приложения, вы можете выполнить одно из следующих действий.

- Измените код так, чтобы он ожидал новое имя манифеста.

- Откажитесь от нового соглашения об именовании, указав в файле проекта параметр `EmbeddedResourceUseDependentUponConvention` со значением `false`.

  ```xml
  <PropertyGroup>
    <EmbeddedResourceUseDependentUponConvention>false</EmbeddedResourceUseDependentUponConvention>
  </PropertyGroup>
  ```

#### <a name="category"></a>Категория

MSBuild

#### <a name="affected-apis"></a>Затронутые API

Н/Д
