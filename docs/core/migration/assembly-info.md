---
title: Свойства AssemblyInfo
description: Сведения о атрибутах сборки и о том, как они соответствуют свойствам MSBuild в .NET Core 2.1 и более поздних версий.
ms.topic: reference
ms.date: 01/08/2021
ms.openlocfilehash: a2c431b3fe3da428f21582624ca5f357887e2815
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/14/2021
ms.locfileid: "98192878"
---
# <a name="map-assemblyinfo-attributes-to-properties"></a>Сопоставление со свойствами для атрибутов AssemblyInfo

[Атрибуты сборки](../../standard/assembly/set-attributes.md), которые обычно присутствовали в файле *AssemblyInfo* в .NET Core 2.0 и более ранних версий, создаются автоматически из свойств MSBuild, начиная с .NET Core 2.1.

## <a name="properties-per-attribute"></a>Свойства каждого атрибута

Как показано в следующей таблице, каждый атрибут имеет два соответствующих свойства: одно управляет содержимым атрибута, а второе отключает его создание.

| Атрибут                                                      | Свойство.               | Свойство, используемое для отключения                             |
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

Примечания.

- `AssemblyVersion` и `FileVersion` по умолчанию имеют значение `$(Version)` без суффикса. Например, если для `$(Version)` нужно указать `1.2.3-beta.4`, то значением будет `1.2.3`.
- По умолчанию для `InformationalVersion` используется значение `$(Version)`.
- Если имеется свойство `$(SourceRevisionId)`, оно добавляется к `InformationalVersion`. Такое поведение можно отключить с помощью `IncludeSourceRevisionInInformationalVersion`.
- Свойства `Copyright` и `Description` также используются для метаданных NuGet.
- Свойство `Configuration`, которое по умолчанию имеет значение `Debug`, является общим для всех целевых объектов MSBuild. Его можно задать с помощью параметра `--configuration` команды `dotnet` (например, [dotnet pack](../tools/dotnet-pack.md)).

## <a name="generateassemblyinfo"></a>GenerateAssemblyInfo

Логическое свойство, которое позволяет включить или отключить создание свойств AssemblyInfo. Значение по умолчанию — `true`.

## <a name="generatedassemblyinfofile"></a>GeneratedAssemblyInfoFile

Относительный или абсолютный путь к файлу сведений о созданной сборке. По умолчанию используется файл с именем *[имя_проекта].AssemblyInfo.[cs|vb]* в каталоге `$(IntermediateOutputPath)` (*obj*).
