---
title: Обзор пакета SDK для проекта .NET
titleSuffix: ''
description: Сведения о пакетах SDK для проектов .NET.
ms.date: 09/17/2020
ms.topic: conceptual
no-loc:
- EmbeddedResource
- Compile
- None
ms.openlocfilehash: e5a6d0a1c988818e507936b567fa0188675cedc3
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "100432651"
---
# <a name="net-project-sdks"></a>Пакеты SDK для проектов .NET

Проекты .NET Core и NET 5.0 и более поздних версий связаны с пакетом средств разработки программного обеспечения (SDK). Каждый *пакет SDK для проекта* является набором [целевых объектов](/visualstudio/msbuild/msbuild-targets) MSBuild и связанных [задач](/visualstudio/msbuild/msbuild-tasks), которые отвечают за компиляцию, упаковку и публикацию кода. Проект, который ссылается на пакет SDK для проекта, иногда называется *проектом в стиле пакета SDK*.

## <a name="available-sdks"></a>Доступные пакеты SDK

Доступны следующие пакеты SDK:

| ID | Описание | Репозиторий|
| - | - | - |
| `Microsoft.NET.Sdk` | Пакет SDK для .NET | <https://github.com/dotnet/sdk> |
| `Microsoft.NET.Sdk.Web` | [Веб-пакет SDK](/aspnet/core/razor-pages/web-sdk) для .NET | <https://github.com/dotnet/sdk> |
| `Microsoft.NET.Sdk.Razor` | [Пакет SDK Razor](/aspnet/core/razor-pages/sdk) для .NET |
| `Microsoft.NET.Sdk.Worker` | Пакет SDK для службы рабочей роли в .NET |
| `Microsoft.NET.Sdk.WindowsDesktop` | [Пакет SDK для настольных систем](msbuild-props-desktop.md) в .NET, который включает Windows Forms (WinForms) и Windows Presentation Foundation (WPF).\* | <https://github.com/dotnet/winforms> и <https://github.com/dotnet/wpf> |

Пакет SDK для .NET является базовым пакетом SDK для .NET. Другие пакеты SDK ссылаются на пакет SDK для .NET, а проекты, связанные с другими пакетами SDK, имеют все доступные им свойства пакета SDK для .NET. Например, веб-пакет SDK зависит от пакета SDK для .NET и пакета SDK для Razor.

Можно также создать собственный пакет SDK и распространять его с помощью NuGet.

\* Начиная с .NET 5.0, в проектах Windows Forms и Windows Presentation Foundation (WPF) необходимо указывать пакет SDK для .NET (`Microsoft.NET.Sdk`), а не `Microsoft.NET.Sdk.WindowsDesktop`. Если для параметра `TargetFramework` в таких проектах установить значение `net5.0-windows`, а для параметра `UseWPF` или `UseWindowsForms` — значение `true`, импорт пакета SDK для Windows Desktop будет выполняться автоматически. Если проект предназначен для .NET 5.0 или более поздней версии и в нем указан пакет SDK `Microsoft.NET.Sdk.WindowsDesktop`, при сборке отобразится предупреждение NETSDK1137.

## <a name="project-files"></a>Файлы проекта

В основе проектов .NET лежит формат [MSBuild](/visualstudio/msbuild/msbuild). Файлы проекта с такими расширениями, как *CPROJ* для проектов C# и *FPROJ* для проектов F#, имеют формат XML. Корневым элементом файла проекта MSBuild является элемент [Project](/visualstudio/msbuild/project-element-msbuild). Элемент `Project` имеет необязательный атрибут `Sdk`, указывающий, какой пакет SDK (и версию) следует использовать. Чтобы использовать средства .NET и выполнить сборку кода, задайте в качестве значения атрибута `Sdk` один из идентификаторов, указанных в таблице[Доступные пакеты SDK](#available-sdks).

```xml
<Project Sdk="Microsoft.NET.Sdk">
  ...
</Project>
```

Чтобы указать пакет SDK, который содержится в NuGet, добавьте версию в конец имени или укажите имя и версию в файле *global.json*.

```xml
<Project Sdk="MSBuild.Sdk.Extras/2.0.54">
  ...
</Project>
```

Другим способом указания пакета SDK является элемент [Sdk](/visualstudio/msbuild/sdk-element-msbuild) верхнего уровня.

```xml
<Project>
  <Sdk Name="Microsoft.NET.Sdk" />
  ...
</Project>
```

Указание пакета SDK одним из этих способов значительно упрощает файлы проекта для .NET. На этапе оценки проекта MSBuild добавляет неявные директивы импорта для `Sdk.props` в начале и для `Sdk.targets` в конце файла проекта.

```xml
<Project>
  <!-- Implicit top import -->
  <Import Project="Sdk.props" Sdk="Microsoft.NET.Sdk" />
  ...
  <!-- Implicit bottom import -->
  <Import Project="Sdk.targets" Sdk="Microsoft.NET.Sdk" />
</Project>
```

> [!TIP]
> На компьютере Windows файлы *Sdk.props* и *Sdk.targets* можно найти в папке *%ProgramFiles%\dotnet\sdk\\[версия]\Sdks\Microsoft.NET.Sdk\Sdk*.

### <a name="preprocess-the-project-file"></a>Предварительная обработка файла проекта

Увидеть полностью развернутый проект так, как он отображается в MSBuild, можно после включения пакета SDK и его целевых объектов с помощью команды `dotnet msbuild -preprocess`. Включите параметр [preprocess](/visualstudio/msbuild/msbuild-command-line-reference#preprocess) в команду [`dotnet msbuild`](../tools/dotnet-msbuild.md), чтобы просмотреть сведения об импортированных файлах, их источниках, вкладе в сборку без фактического создания проекта.

Если проект имеет несколько требуемых версий .NET Framework, результаты выполнения команды должны касаться только одной из них. Эту версию следует указать в качестве свойства MSBuild. Пример:

`dotnet msbuild -property:TargetFramework=netcoreapp2.0 -preprocess:output.xml`

## <a name="default-includes-and-excludes"></a>Включения и исключения по умолчанию

В пакете SDK определены стандартные включения и исключения для [элементов `Compile`](/visualstudio/msbuild/common-msbuild-project-items#compile), [внедренных ресурсов](/visualstudio/msbuild/common-msbuild-project-items#embeddedresource) и [элементов `None`](/visualstudio/msbuild/common-msbuild-project-items#none). В отличие от проектов .NET Framework без пакетов SDK в файле проекта не нужно указывать эти элементы, так как для наиболее распространенных вариантов использования действуют значения по умолчанию. Такой подход позволяет уменьшить файлы проекта и без труда понимать их, а при необходимости даже вносить правки вручную.

В следующей таблице показано, какие элементы и [стандартные маски](https://en.wikipedia.org/wiki/Glob_(programming)) включены в пакет SDK для .NET и исключены из него:

| Элемент           | Стандартная маска включения                              | Стандартная маска исключения                                                  | Стандартная маска удаления              |
|-------------------|-------------------------------------------|---------------------------------------------------------------|--------------------------|
| Compile           | \*\*/\*.cs (или другие расширения языка) | \*\*/\*.user;  \*\*/\*.\*proj;  \*\*/\*.sln;  \*\*/\*.vssscc  | Н/Д                      |
| EmbeddedResource  | \*\*/\*.resx                              | \*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc     | Н/Д                      |
| None              | \*\*/\*                                   | \*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc     | \*\*/\*.cs; \*\*/\*.resx |

> [!NOTE]
> Папки `./bin` и `./obj`, которые представлены свойствами MSBuild `$(BaseOutputPath)` и `$(BaseIntermediateOutputPath)`, исключаются из стандартных масок исключения по умолчанию. Исключения представлены свойством [DefaultItemExcludes](msbuild-props.md#defaultitemexcludes).

Пакет SDK для настольных систем в .NET имеет больше включений и исключений для WPF. Дополнительные сведения см. в разделе [Включения и исключения для WPF](msbuild-props-desktop.md#wpf-default-includes-and-excludes).

### <a name="build-errors"></a>Ошибки сборки

Если вы явным образом определите любой из этих элементов в файле проекта, скорее всего, произойдет ошибка сборки NETSDK1022 с примерно таким сообщением:

> Duplicate 'Compile' items were included. The .NET SDK includes 'Compile' items from your project directory by default. You can either remove these items from your project file, or set the 'EnableDefaultCompileItems' property to 'false' if you want to explicitly include them in your project file. (Включены повторяющиеся элементы Compile. По умолчанию пакет SDK для .NET включает элементы Compile из каталога проекта. Можно удалить эти элементы из файла проекта или задать для свойства EnableDefaultCompileItems значение false, чтобы явно включить их в файл проекта).

> Duplicate 'EmbeddedResource' items were included. The .NET SDK includes 'EmbeddedResource' items from your project directory by default. You can either remove these items from your project file, or set the 'EnableDefaultEmbeddedResourceItems' property to 'false' if you want to explicitly include them in your project file. (Включены повторяющиеся элементы Compile. По умолчанию пакет SDK для .NET включает элементы Compile из каталога проекта. Можно удалить эти элементы из файла проекта или задать для свойства EnableDefaultCompileItems значение false, чтобы явно включить их в файл проекта).

Чтобы устранить такую проблему, выполните любое из следующих действий:

- Удалите явно заданные элементы `Compile`, `EmbeddedResource` или `None`, которые совпадают с неявно заданными параметрами из предыдущей таблицы.

- Присвойте [свойству EnableDefaultItems](msbuild-props.md#enabledefaultitems) значение `false`, чтобы отключить все неявные включения файлов:

  ```xml
  <PropertyGroup>
    <EnableDefaultItems>false</EnableDefaultItems>
  </PropertyGroup>
  ```

  Если вы хотите указать файлы, которые нужно публиковать вместе с приложением, для этого можно по-прежнему использовать привычные механизмы MSBuild (например, элемент `Content`).

- Выборочно отключите только стандартные маски `Compile`, `EmbeddedResource` или `None`, присвоив свойствам [EnableDefaultCompileItems](msbuild-props.md#enabledefaultcompileitems), [EnableDefaultEmbeddedResourceItems](msbuild-props.md#enabledefaultembeddedresourceitems) или [EnableDefaultNoneItems](msbuild-props.md#enabledefaultnoneitems) значение `false`:

  ```xml
  <PropertyGroup>
    <EnableDefaultCompileItems>false</EnableDefaultCompileItems>
    <EnableDefaultEmbeddedResourceItems>false</EnableDefaultEmbeddedResourceItems>
    <EnableDefaultNoneItems>false</EnableDefaultNoneItems>
  </PropertyGroup>
  ```

  Если вы отключите только стандартные маски `Compile`, обозреватель решений в Visual Studio будет по-прежнему отображать элементы \*.cs в составе проекта, включая их в виде элементов `None`. Чтобы отключить неявную стандартную маску `None`, задайте свойству `EnableDefaultNoneItems` значение `false`.

## <a name="implicit-package-references"></a>Неявные ссылки на пакет

При использовании .NET Core 1.0–2.2 или .NET Standard 1.0–2.0 пакет SDK для .NET добавляет неявные ссылки на определенные *метапакеты*. Метапакет — это пакет на основе платформы, который состоит только из зависимостей от других пакетов. Теперь неявные ссылки на метапакеты указываются в зависимости от целевой платформы, указанной в свойстве [TargetFramework](msbuild-props.md#targetframework) или [TargetFrameworks](msbuild-props.md#targetframeworks) файла проекта.

```xml
<PropertyGroup>
  <TargetFramework>netcoreapp2.1</TargetFramework>
</PropertyGroup>
```

```xml
<PropertyGroup>
  <TargetFrameworks>netcoreapp2.1;net462</TargetFrameworks>
</PropertyGroup>
```

При необходимости можно отключить неявные ссылки на пакеты с помощью свойства [DisableImplicitFrameworkReferences](msbuild-props.md#disableimplicitframeworkreferences) и добавить явные ссылки только на необходимые платформы или пакеты.

Рекомендации

- При использовании .NET Framework, .NET Core 1.0–2.2 или .NET Standard 1.0–2.0 не добавляйте явную ссылку на метапакеты `Microsoft.NETCore.App` или `NETStandard.Library` через элемент `<PackageReference>` в файле проекта. Для проектов .NET Core 1.0–2.2 и .NET Standard 1.0–2.0 ссылка на эти метапакеты неявно присутствует. Если при использовании проектов .NET Framework и пакета NuGet на основе .NET Standard требуется любая версия `NETStandard.Library`, NuGet автоматически устанавливает ее.
- Если при использовании .NET Core 1.0–2.2 нужна определенная версия среды выполнения, вместо ссылки на метапакет следует использовать свойство `<RuntimeFrameworkVersion>` в проекте (например, `1.0.4`). Например, может потребоваться специальная версия LTS среды выполнения 1.0.0, если вы используете [автономные развертывания](../deploying/index.md#publish-self-contained).
- Если при использовании .NET Standard 1.0–2.0 вам нужна конкретная версия метапакета `NETStandard.Library`, можно использовать свойство `<NetStandardImplicitPackageVersion>` и установить требуемую версию.

## <a name="build-events"></a>События сборки

Для проектов в стиле пакета SDK используйте целевой объект MSBuild с именем `PreBuild` или `PostBuild` и задайте свойство `BeforeTargets` для `PreBuild` или свойство `AfterTargets` для `PostBuild`.

```xml
<Target Name="PreBuild" BeforeTargets="PreBuildEvent">
    <Exec Command="&quot;$(ProjectDir)PreBuildEvent.bat&quot; &quot;$(ProjectDir)..\&quot; &quot;$(ProjectDir)&quot; &quot;$(TargetDir)&quot;" />
</Target>

<Target Name="PostBuild" AfterTargets="PostBuildEvent">
   <Exec Command="echo Output written to $(TargetDir)" />
</Target>
```

> [!NOTE]
>
> - Для целевых объектов MSBuild можно использовать любые имена. Однако интегрированная среда разработки Visual Studio распознает целевые объекты `PreBuild` и `PostBuild`, поэтому с помощью этих имен можно изменять команды в интегрированной среде разработки.
> - Свойства `PreBuildEvent` и `PostBuildEvent` не рекомендуется использовать в проектах в стиле пакета SDK, поскольку такие макросы, как `$(ProjectDir)`, не разрешены. Например, приведенный ниже код не поддерживается.
>
> ```xml
> <PropertyGroup>
>   <PreBuildEvent>"$(ProjectDir)PreBuildEvent.bat" "$(ProjectDir)..\" "$(ProjectDir)" "$(TargetDir)"</PreBuildEvent>
> </PropertyGroup>
> ```

## <a name="customize-the-build"></a>Настройка сборки

Существует несколько способов [настройки сборки](/visualstudio/msbuild/customize-your-build). Может потребоваться переопределить свойство, передав его в качестве аргумента в команду [msbuild](/visualstudio/msbuild/msbuild-command-line-reference) или [dotnet](../tools/index.md). Можно также добавить свойство в файл проекта или в файл *Directory.Build.props*. Список полезных свойств для проектов .NET см. в статье [Справочник по MSBuild для проектов пакета SDK для .NET](msbuild-props.md).

### <a name="custom-targets"></a>Пользовательские целевые объекты

В проектах .NET доступна возможность упаковки пользовательских целевых объектов MSBuild и свойств для использования в проектах, применяющих этот пакет. Используйте этот тип расширяемости, если нужно выполнить следующие задачи:

- расширить процесс сборки;
- получить доступ к артефактам процесса сборки, таким как созданные файлы;
- проверить конфигурацию, с которой была запущена сборка.

Чтобы добавить пользовательские целевые объекты или свойства сборки, нужно поместить файлы в форме `<package_id>.targets` или `<package_id>.props` (например, `Contoso.Utility.UsefulStuff.targets`) в папку *build* проекта.

Следующий XML-код является фрагментом из файла *CPROJ*, который указывает команде [`dotnet pack`](../tools/dotnet-pack.md), что именно нужно упаковать. Элемент `<ItemGroup Label="dotnet pack instructions">` помещает файлы целевых объектов в папку *build* в пакете. Элемент `<Target Name="CollectRuntimeOutputs" BeforeTargets="_GetPackageFiles">` помещает сборки и файлы *JSON* в папку *build*.

```xml
<Project Sdk="Microsoft.NET.Sdk">

  ...
  <ItemGroup Label="dotnet pack instructions">
    <Content Include="build\*.targets">
      <Pack>true</Pack>
      <PackagePath>build\</PackagePath>
    </Content>
  </ItemGroup>
  <Target Name="CollectRuntimeOutputs" BeforeTargets="_GetPackageFiles">
    <!-- Collect these items inside a target that runs after build but before packaging. -->
    <ItemGroup>
      <Content Include="$(OutputPath)\*.dll;$(OutputPath)\*.json">
        <Pack>true</Pack>
        <PackagePath>build\</PackagePath>
      </Content>
    </ItemGroup>
  </Target>
  ...

</Project>
```

Чтобы использовать пользовательский целевой объект в проекте, добавьте элемент `PackageReference`, указывающий на пакет и его версию. В отличие от средств пакет пользовательских целевых объектов входит в замыкание зависимостей исходного проекта.

Вы можете настроить способ использования пользовательского целевого объекта. Так как это целевой объект MSBuild, он может зависеть от заданного целевого объекта, запускаться после другого целевого объекта или быть вызван вручную с помощью команды `dotnet msbuild -t:<target-name>`. Однако для удобства пользователей можно объединить средства для отдельных проектов и пользовательские целевые объекты. В этом сценарии средство для отдельного проекта принимает необходимые параметры и преобразует их в требуемый вызов [`dotnet msbuild`](../tools/dotnet-msbuild.md), который выполняет целевой объект. Пример подобного типа синергии можно увидеть в репозитории [примеров хакатона MVP Summit 2016](https://github.com/dotnet/MVPSummitHackathon2016) в проекте [`dotnet-packer`](https://github.com/dotnet/MVPSummitHackathon2016/tree/master/dotnet-packer).

## <a name="see-also"></a>См. также

- [установите .NET Core](../install/index.yml).
- [Использование пакетов SDK проекта MSBuild](/visualstudio/msbuild/how-to-use-project-sdk)
- [Упаковка пользовательских целевых объектов и свойств MSBuild с помощью NuGet](/nuget/create-packages/creating-a-package#include-msbuild-props-and-targets-in-a-package)
