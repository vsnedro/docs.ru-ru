---
title: Свойства MSBuild для Microsoft.NET.Sdk
description: Справочник по свойствам и элементам MSBuild, распознаваемым пакетом SDK для .NET.
ms.date: 02/14/2020
ms.topic: reference
ms.custom: updateeachrelease
ms.openlocfilehash: 3b58fd080439c73ee30d5c8dc59c50c0410db164
ms.sourcegitcommit: 45c7148f2483db2501c1aa696ab6ed2ed8cb71b2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/08/2020
ms.locfileid: "96851579"
---
# <a name="msbuild-reference-for-net-sdk-projects"></a>Справочник по MSBuild для проектов пакета SDK для .NET

Эта страница содержит справочные сведения о свойствах и элементах MSBuild, которые вы можете использовать для настройки проектов .NET.

> [!NOTE]
> Работа над этой страницей еще не завершена, поэтому здесь приведены лишь некоторые полезные свойства MSBuild для пакета SDK для .NET. Список стандартных свойств см. в статье [Общие свойства MSBuild](/visualstudio/msbuild/common-msbuild-project-properties).

## <a name="framework-properties"></a>Свойства платформы

- [TargetFramework](#targetframework)
- [TargetFrameworks](#targetframeworks)
- [NetStandardImplicitPackageVersion](#netstandardimplicitpackageversion)

### <a name="targetframework"></a>TargetFramework

Свойство `TargetFramework` определяет версию целевой платформы для приложения. Список допустимых моникеров целевой платформы см. в статье [Целевые платформы в проектах в стиле SDK](../../standard/frameworks.md#supported-target-frameworks).

```xml
<PropertyGroup>
  <TargetFramework>netcoreapp3.1</TargetFramework>
</PropertyGroup>
```

Дополнительные сведения см.в статье [Целевые платформы в проектах в стиле SDK](../../standard/frameworks.md).

### <a name="targetframeworks"></a>TargetFrameworks

Используйте свойство `TargetFrameworks`, если приложение должно быть предназначено для нескольких платформ. Список допустимых моникеров целевой платформы см. в статье [Целевые платформы в проектах в стиле SDK](../../standard/frameworks.md#supported-target-frameworks).

> [!NOTE]
> Это свойство игнорируется, если указано свойство `TargetFramework` (в единственном числе).

```xml
<PropertyGroup>
  <TargetFrameworks>netcoreapp3.1;net462</TargetFrameworks>
</PropertyGroup>
```

Дополнительные сведения см.в статье [Целевые платформы в проектах в стиле SDK](../../standard/frameworks.md).

### <a name="netstandardimplicitpackageversion"></a>NetStandardImplicitPackageVersion

> [!NOTE]
> Это свойство применяется только к проектам, использующим `netstandard1.x`. Он не применяется к проектам, использующим `netstandard2.x`.

Используйте свойство `NetStandardImplicitPackageVersion`, если вам нужно указать версию платформы ниже версии метапакета. Файл проекта, приведенный в следующем примере, предназначен для `netstandard1.3`, но использует `NETStandard.Library` версии 1.6.0.

```xml
<PropertyGroup>
  <TargetFramework>netstandard1.3</TargetFramework>
  <NetStandardImplicitPackageVersion>1.6.0</NetStandardImplicitPackageVersion>
</PropertyGroup>
```

## <a name="package-properties"></a>Свойства пакета

Для описания пакета, созданного из проекта, можно указать такие свойства, как `PackageId`, `PackageVersion`, `PackageIcon`, `Title` и `Description`. Дополнительные сведения об этих и других свойствах см. в разделе [целевой объект пакета](/nuget/reference/msbuild-targets#pack-target).

```xml
<PropertyGroup>
  ...
  <PackageId>ClassLibDotNetStandard</PackageId>
  <Version>1.0.0</Version>
  <Authors>John Doe</Authors>
  <Company>Contoso</Company>
</PropertyGroup>
```

## <a name="publish-properties-and-items"></a>Публикация свойств и элементов

- [CopyLocalLockFileAssemblies](#copylocallockfileassemblies)
- [RuntimeIdentifier](#runtimeidentifier)
- [RuntimeIdentifiers](#runtimeidentifiers)
- [TrimmerRootAssembly](#trimmerrootassembly)
- [UseAppHost](#useapphost)

### <a name="copylocallockfileassemblies"></a>CopyLocalLockFileAssemblies

Свойство `CopyLocalLockFileAssemblies` полезно для проектов подключаемых модулей, которые имеют зависимости от других библиотек. Если для этого свойства задано значение `true`, все зависимости пакета NuGet копируются в выходной каталог. Это означает, что вы можете использовать выходные данные `dotnet build` для запуска подключаемого модуля на любом компьютере.

```xml
<PropertyGroup>
  <CopyLocalLockFileAssemblies>true</CopyLocalLockFileAssemblies>
</PropertyGroup>
```

> [!TIP]
> Кроме того, можно использовать `dotnet publish` для публикации библиотеки классов. Дополнительные сведения см. в разделе [dotnet publish](../tools/dotnet-publish.md).

### <a name="runtimeidentifier"></a>RuntimeIdentifier

Свойство `RuntimeIdentifier` позволяет указать для проекта один [идентификатор среды выполнения (RID)](../rid-catalog.md). Идентификатор среды выполнения позволяет опубликовать автономное развертывание.

```xml
<PropertyGroup>
  <RuntimeIdentifier>ubuntu.16.04-x64</RuntimeIdentifier>
</PropertyGroup>
```

### <a name="runtimeidentifiers"></a>RuntimeIdentifiers

Свойство `RuntimeIdentifiers` позволяет указать для проекта список [идентификаторов среды выполнения (RID)](../rid-catalog.md) (в качестве разделителя используется точка с запятой). Используйте это свойство, если вам нужна публикация для нескольких сред. `RuntimeIdentifiers` используется во время восстановления для обеспечения наличия в графе нужных ресурсов.

> [!TIP]
> `RuntimeIdentifier` (в единственном числе) может ускорить создание сборок, когда требуется только одна среда выполнения.

```xml
<PropertyGroup>
  <RuntimeIdentifiers>win10-x64;osx.10.11-x64;ubuntu.16.04-x64</RuntimeIdentifiers>
</PropertyGroup>
```

### <a name="trimmerrootassembly"></a>TrimmerRootAssembly

Элемент `TrimmerRootAssembly` позволяет исключить сборку из [*обрезки*](../deploying/trim-self-contained.md). Обрезка — это процесс удаления неиспользуемых частей среды выполнения из упакованного приложения. В некоторых случаях при обрезке могут неправильно удаляться необходимые ссылки.

Следующий код XML исключает сборку `System.Security` из обрезки.

```xml
<ItemGroup>
  <TrimmerRootAssembly Include="System.Security" />
</ItemGroup>
```

### <a name="useapphost"></a>UseAppHost

Свойство `UseAppHost` контролирует создание собственного исполняемого файла для развертывания. Этот файл требуется для автономных развертываний.

В .NET Core 3.0 и более поздних версиях зависимый от платформы исполняемый файл создается по умолчанию. Задайте свойству `UseAppHost` значение `false`, чтобы отключить создание исполняемого файла.

```xml
<PropertyGroup>
  <UseAppHost>false</UseAppHost>
</PropertyGroup>
```

Дополнительные сведения см. в статье о [развертывании приложений .NET](../deploying/index.md).

## <a name="compile-properties"></a>Свойства компиляции

- [EmbeddedResourceUseDependentUponConvention](#embeddedresourceusedependentuponconvention)
- [LangVersion](#langversion)

### <a name="embeddedresourceusedependentuponconvention"></a>EmbeddedResourceUseDependentUponConvention

Свойство `EmbeddedResourceUseDependentUponConvention` определяет, будет ли использоваться информация о типах в исходных файлах, расположенных в одной папке с файлами ресурсов, для создания имен файлов манифеста этих ресурсов. Например, если *Form1.resx* находится в той же папке, что и *Form1.cs*, а `EmbeddedResourceUseDependentUponConvention` имеет значение `true`, то созданному файл *.resources* присваивается имя на основе имени первого типа, определенного в файле *Form1.cs*. Например, если первым типом в файле *Form1.cs* является `MyNamespace.Form1`, созданному файлу присваивается имя *MyNamespace.Form1.resources*.

> [!NOTE]
> Если для `EmbeddedResource` элемента заданы метаданные `LogicalName`, `ManifestResourceName` или `DependentUpon`, то имя файла манифеста для этого файла ресурсов будет создаваться на основе таких метаданных.

По умолчанию для нового проекта .NET этому свойству задается значение `true`. Если задано значение `false` и для элемента `EmbeddedResource` в файле проекта не указаны метаданные `LogicalName`, `ManifestResourceName` или `DependentUpon`, то имя файла манифеста для этого ресурса будет основано на имени корневого пространства имен проекта и относительном пути к файлу *.resx*. Дополнительные сведения об определение имени файла манифеста см. [здесь](../resources/manifest-file-names.md).

```xml
<PropertyGroup>
  <EmbeddedResourceUseDependentUponConvention>true</EmbeddedResourceUseDependentUponConvention>
</PropertyGroup>
```

### <a name="langversion"></a>LangVersion

Свойство `LangVersion` позволяет указать конкретную версию языка программирования. Например, если требуется доступ к предварительным версиям функций C#, задайте параметру `LangVersion` значение `preview`.

```xml
<PropertyGroup>
  <LangVersion>preview</LangVersion>
</PropertyGroup>
```

Дополнительные сведения см. в статье [Управление версиями языка C#](../../csharp/language-reference/configure-language-version.md#override-a-default).

## <a name="code-analysis-properties"></a>Свойства анализа кода

### <a name="analysislevel"></a>AnalysisLevel

Свойство `AnalysisLevel` позволяет указать уровень анализа кода. Например, если требуется доступ к анализаторам кода предварительной версии, задайте для параметра `AnalysisLevel` значение `preview`. Значение по умолчанию — `latest`.

```xml
<PropertyGroup>
  <AnalysisLevel>preview</AnalysisLevel>
</PropertyGroup>
```

В следующей таблице приведены доступные параметры.

| Значение | Значение |
|-|-|
| `latest` | Используются новейшие анализаторы кода, которые были выпущены. Это значение по умолчанию. |
| `preview` | Используются новейшие анализаторы кода, даже если они находятся на этапе предварительной версии. |
| `5.0` | Используется набор правил, включенных для выпуска .NET 5.0, даже если доступны новые правила. |
| `5` | Используется набор правил, включенных для выпуска .NET 5.0, даже если доступны новые правила. |

### <a name="analysismode"></a>AnalysisMode

Начиная с .NET 5.0 пакет SDK для .NET поставляется со всеми [правилами качества кода "CA"](../../fundamentals/code-analysis/quality-rules/index.md). По умолчанию в качестве предупреждений сборки включены только [некоторые правила](../../fundamentals/code-analysis/overview.md#enabled-rules). Свойство `AnalysisMode` позволяет настроить набор правил, включенных по умолчанию. Можно либо переключиться на более агрессивный (неявный) режим анализа, либо более консервативный (явный) режим анализа. Например, если вы хотите включить все правила по умолчанию как предупреждения сборки, установите значение `AllEnabledByDefault`.

```xml
<PropertyGroup>
  <AnalysisMode>AllEnabledByDefault</AnalysisMode>
</PropertyGroup>
```

В следующей таблице приведены доступные параметры.

| Значение | Значение |
|-|-|
| `Default` | Режим по умолчанию, при котором определенные правила включаются в виде предупреждений сборки, некоторые правила включаются в качестве предложений интегрированной среды разработки Visual Studio, а остальные отключаются. |
| `AllEnabledByDefault` | Агрессивный или неявный режим означает, что все правила по умолчанию включены как предупреждения сборки. Вы можете выборочно [отказаться](../../fundamentals/code-analysis/configuration-options.md) от отдельных правил, чтобы отключить их. |
| `AllDisabledByDefault` | Консервативный или явный режим означает, что все правила по умолчанию отключены. Можно выборочно [принять](../../fundamentals/code-analysis/configuration-options.md) отдельные правила, чтобы включить их. |

### <a name="codeanalysistreatwarningsaserrors"></a>CodeAnalysisTreatWarningsAsErrors

Свойство `CodeAnalysisTreatWarningsAsErrors` позволяет настроить, следует ли обрабатывать предупреждения анализа качества кода (CAxxxx) как предупреждения и прекращать сборку. Если при построении проектов используется флаг `-warnaserror`, предупреждения [анализа качества кода .NET](../../fundamentals/code-analysis/overview.md#code-quality-analysis) также обрабатываются как ошибки. Если вы не хотите, чтобы предупреждения качества кода обрабатывались как ошибки, можно задать для свойства MSBuild `CodeAnalysisTreatWarningsAsErrors` значение `false` в файле проекта.

```xml
<PropertyGroup>
  <CodeAnalysisTreatWarningsAsErrors>false</CodeAnalysisTreatWarningsAsErrors>
</PropertyGroup>
```

### <a name="enablenetanalyzers"></a>EnableNETAnalyzers

Для проектов, предназначенных для .NET 5.0 или более поздней версии, по умолчанию включен [анализ качества кода .NET](../../fundamentals/code-analysis/overview.md#code-quality-analysis). Вы можете включить анализ кода .NET для проектов, предназначенных для более ранних версий .NET, установив для свойства `EnableNETAnalyzers` значение `true`. Чтобы отключить анализ кода в любом проекте, присвойте этому свойству значение `false`.

```xml
<PropertyGroup>
  <EnableNETAnalyzers>true</EnableNETAnalyzers>
</PropertyGroup>
```

> [!TIP]
> Другой способ включить анализ кода .NET для проектов, предназначенных для версий .NET до .NET 5.0, — задать для свойства [AnalysisLevel](#analysislevel) значение `latest`.

### <a name="enforcecodestyleinbuild"></a>EnforceCodeStyleInBuild

> [!NOTE]
> Эта функция в настоящее время является экспериментальной и может измениться в .NET 6 по сравнению с реализацией в .NET 5.

[Анализ стиля кода .NET](../../fundamentals/code-analysis/overview.md#code-style-analysis) по умолчанию отключен при сборке для всех проектов .NET. Можно включить анализ стиля кода для проектов .NET, задав для свойства `EnforceCodeStyleInBuild` значение `true`.

```xml
<PropertyGroup>
  <EnforceCodeStyleInBuild>true</EnforceCodeStyleInBuild>
</PropertyGroup>
```

Все правила стиля кода, которые [настроены](../../fundamentals/code-analysis/overview.md#code-style-analysis) как предупреждения или ошибки, будут выполняться при нарушениях сборки и отчета.

## <a name="run-time-configuration-properties"></a>Свойства конфигурации среды выполнения

Вы можете настроить некоторые варианты поведения среды выполнения, указав свойства MSBuild в файле проекта приложения. Сведения о других способах настройки поведения среды выполнения см. в статье о [параметрах конфигурации среды выполнения](../run-time-config/index.md).

- [ConcurrentGarbageCollection](#concurrentgarbagecollection)
- [InvariantGlobalization](#invariantglobalization)
- [RetainVMGarbageCollection](#retainvmgarbagecollection)
- [ServerGarbageCollection](#servergarbagecollection)
- [ThreadPoolMaxThreads](#threadpoolmaxthreads)
- [ThreadPoolMinThreads](#threadpoolminthreads)
- [TieredCompilation](#tieredcompilation)
- [TieredCompilationQuickJit](#tieredcompilationquickjit)
- [TieredCompilationQuickJitForLoops](#tieredcompilationquickjitforloops)

### <a name="concurrentgarbagecollection"></a>ConcurrentGarbageCollection

Свойство `ConcurrentGarbageCollection` указывает, включена ли [фоновая (параллельная) сборка мусора](../../standard/garbage-collection/background-gc.md). Задайте значение `false`, чтобы отключить фоновую сборку мусора. Дополнительные сведения см. в разделе [Сборка мусора в фоновом режиме](../run-time-config/garbage-collector.md#background-gc).

```xml
<PropertyGroup>
  <ConcurrentGarbageCollection>false</ConcurrentGarbageCollection>
</PropertyGroup>
```

### <a name="invariantglobalization"></a>InvariantGlobalization

Свойство `InvariantGlobalization` определяет, выполняется ли приложение в *инвариантном режиме глобализации*, что означает, что у него нет доступа к данным, относящимся к языку и региональным параметрам. Установите значение `true` для запуска в инвариантном режиме глобализации. Дополнительные сведения см. в разделе [Инвариантный режим](../run-time-config/globalization.md#invariant-mode).

```xml
<PropertyGroup>
  <InvariantGlobalization>true</InvariantGlobalization>
</PropertyGroup>
```

### <a name="retainvmgarbagecollection"></a>RetainVMGarbageCollection

Свойство `RetainVMGarbageCollection` настраивает сборщик мусора для помещения удаленных сегментов памяти в список ожидания для будущего использования или освобождения. Значение `true` указывает сборщику мусора разместить сегменты в списке ожидания. Дополнительные сведения см. в разделе [Сохранение виртуальной машины](../run-time-config/garbage-collector.md#retain-vm).

```xml
<PropertyGroup>
  <RetainVMGarbageCollection>true</RetainVMGarbageCollection>
</PropertyGroup>
```

### <a name="servergarbagecollection"></a>ServerGarbageCollection

Свойство `ServerGarbageCollection` указывает, использует ли приложение [сборку мусора рабочей станции или сборку мусора сервера](../../standard/garbage-collection/workstation-server-gc.md). Задайте значение `true`, чтобы использовать сборку мусора сервера. Дополнительные сведения см. в разделе [Рабочая станция и сервер](../run-time-config/garbage-collector.md#workstation-vs-server).

```xml
<PropertyGroup>
  <ServerGarbageCollection>true</ServerGarbageCollection>
</PropertyGroup>
```

### <a name="threadpoolmaxthreads"></a>ThreadPoolMaxThreads

Свойство `ThreadPoolMaxThreads` указывает максимальное число потоков для пула рабочих потоков. Дополнительные сведения см. в разделе [Максимальное число потоков](../run-time-config/threading.md#maximum-threads).

```xml
<PropertyGroup>
  <ThreadPoolMaxThreads>20</ThreadPoolMaxThreads>
</PropertyGroup>
```

### <a name="threadpoolminthreads"></a>ThreadPoolMinThreads

Свойство `ThreadPoolMinThreads` указывает минимальное число потоков для пула рабочих потоков. Дополнительные сведения см. в разделе [Минимальное число потоков](../run-time-config/threading.md#minimum-threads).

```xml
<PropertyGroup>
  <ThreadPoolMinThreads>4</ThreadPoolMinThreads>
</PropertyGroup>
```

### <a name="tieredcompilation"></a>TieredCompilation

Свойство `TieredCompilation` указывает, использует ли JIT-компилятор [многоуровневую компиляцию](../whats-new/dotnet-core-3-0.md#tiered-compilation). Задайте значение `false`, чтобы отключить многоуровневую компиляцию. Дополнительные сведения см. в разделе [Многоуровневая компиляция](../run-time-config/compilation.md#tiered-compilation).

```xml
<PropertyGroup>
  <TieredCompilation>false</TieredCompilation>
</PropertyGroup>
```

### <a name="tieredcompilationquickjit"></a>TieredCompilationQuickJit

Свойство `TieredCompilationQuickJit` указывает, использует ли JIT-компилятор быструю JIT-компиляцию. Задайте значение `false`, чтобы отключить быструю JIT-компиляцию. Дополнительные сведения см. в разделе [Быстрая JIT-компиляция](../run-time-config/compilation.md#quick-jit).

```xml
<PropertyGroup>
  <TieredCompilationQuickJit>false</TieredCompilationQuickJit>
</PropertyGroup>
```

### <a name="tieredcompilationquickjitforloops"></a>TieredCompilationQuickJitForLoops

Свойство `TieredCompilationQuickJitForLoops` указывает, использует ли JIT-компилятор быструю JIT-компиляцию для методов, содержащих циклы. Задайте значение `true`, чтобы включить быструю JIT-компиляцию для методов, содержащих циклы. Дополнительные сведения см. в разделе [Быстрая JIT-компиляция для циклов](../run-time-config/compilation.md#quick-jit-for-loops).

```xml
<PropertyGroup>
  <TieredCompilationQuickJitForLoops>true</TieredCompilationQuickJitForLoops>
</PropertyGroup>
```

## <a name="reference-properties-and-items"></a>Справочники по свойствам и элементам

- [AssetTargetFallback](#assettargetfallback)
- [PackageReference](#packagereference)
- [ProjectReference](#projectreference)
- [Ссылки](#reference)
- [Свойства, связанные с восстановлением](#restore-related-properties)

### <a name="assettargetfallback"></a>AssetTargetFallback

Свойство `AssetTargetFallback` позволяет указать дополнительные совместимые версии платформы для ссылок на проекты и пакетов NuGet. Например, если вы указали зависимость пакета с помощью `PackageReference`, но в этом пакете нет ресурсов, совместимых с `TargetFramework` вашего проекта, тогда пригодится свойство `AssetTargetFallback`. Совместимость пакета, на который указывает ссылка, повторно проверяется с помощью каждой целевой платформы, указанной в свойстве `AssetTargetFallback`.

В качестве значения свойства `AssetTargetFallback` можно задать одну [версию целевой платформы](../../standard/frameworks.md#supported-target-frameworks) или несколько.

```xml
<PropertyGroup>
  <AssetTargetFallback>net461</AssetTargetFallback>
</PropertyGroup>
```

### <a name="packagereference"></a>PackageReference

Элемент `PackageReference` определяет ссылку на пакет NuGet.

Атрибут `Include` указывает идентификатор пакета. Атрибут `Version` указывает версию или диапазон версий. Сведения о том, как указать минимальную версию, максимальную версию, диапазон или точное соответствие, см. в разделе [Диапазоны версий](/nuget/concepts/package-versioning#version-ranges). Вы также можете добавить в ссылку на проект следующие метаданные: `IncludeAssets`, `ExcludeAssets` и `PrivateAssets`.

Фрагмент файла проекта в следующем примере ссылается на пакет [System.Runtime](https://www.nuget.org/packages/System.Runtime/).

```xml
<ItemGroup>
  <PackageReference Include="System.Runtime" Version="4.3.0" />
</ItemGroup>
```

Дополнительные сведения см. в статье [Ссылки на пакеты в файлах проекта](/nuget/consume-packages/package-references-in-project-files).

### <a name="projectreference"></a>СсылкаНаПроект

Элемент `ProjectReference` определяет ссылку на другой проект. Проект, на который указывает ссылка, добавляется как зависимость пакета NuGet, то есть обрабатывается так же, как `PackageReference`.

Атрибут `Include` задает путь к проекту. Вы также можете добавить в ссылку на проект следующие метаданные: `IncludeAssets`, `ExcludeAssets` и `PrivateAssets`.

Фрагмент файла проекта в следующем примере ссылается на проект `Project2`.

```xml
<ItemGroup>
  <ProjectReference Include="..\Project2.csproj" />
</ItemGroup>
```

### <a name="reference"></a>Справочник

Элемент `Reference` определяет ссылку на файл сборки.

Атрибут `Include` задает имя файла, а метаданные `HintPath` указывают путь к этой сборке.

```xml
<ItemGroup>
  <Reference Include="MyAssembly">
    <HintPath>..\..\Assemblies\MyAssembly.dll</HintPath>
  </Reference>
</ItemGroup>
```

### <a name="restore-related-properties"></a>Свойства, связанные с восстановлением

При восстановлении пакета, на который указывает ссылка, устанавливаются все его прямые зависимости и все зависимости этих зависимостей. Можно настроить восстановление пакетов, указав такие свойства, как `RestorePackagesPath` и `RestoreIgnoreFailedSources`. Дополнительные сведения об этих и других свойствах см. в разделе [целевой объект восстановления](/nuget/reference/msbuild-targets#restore-target).

```xml
<PropertyGroup>
  <RestoreIgnoreFailedSource>true</RestoreIgnoreFailedSource>
</PropertyGroup>
```

## <a name="hosting-properties-and-items"></a>Размещение свойств и элементов

- [EnableComHosting](#enablecomhosting)
- [EnableDynamicLoading](#enabledynamicloading)

### <a name="enablecomhosting"></a>EnableComHosting

Свойство `EnableComHosting` указывает, что сборка предоставляет сервер COM. Установка `EnableComHosting` в `true` также подразумевает, что [EnableDynamicLoading](#enabledynamicloading) — `true`.

```xml
<PropertyGroup>
  <EnableComHosting>True</EnableComHosting>
</PropertyGroup>
```

Дополнительные сведения см. в разделе [Предоставление компонентов .NET для COM](../native-interop/expose-components-to-com.md).

### <a name="enabledynamicloading"></a>EnableDynamicLoading

Свойство `EnableDynamicLoading` указывает, что сборка является динамически загружаемым компонентом. Компонентом может быть [библиотека COM](/windows/win32/com/the-component-object-model) или библиотека, не относящаяся к COM, которую можно [использовать из собственного узла](../tutorials/netcore-hosting.md). Если присвоить этому свойству значения `true`:

- Создается файл *runtimeconfig.json*.
- [Накат](../whats-new/dotnet-core-3-0.md#major-version-runtime-roll-forward) получает значение `LatestMinor`.
- Ссылки NuGet копируются локально.

```xml
<PropertyGroup>
  <EnableDynamicLoading>true</EnableDynamicLoading>
</PropertyGroup>
```

## <a name="see-also"></a>См. также

- [Справочник по схеме MSBuild](/visualstudio/msbuild/msbuild-project-file-schema-reference)
- [Общие свойства MSBuild](/visualstudio/msbuild/common-msbuild-project-properties)
- [Свойства MSBuild для целевого объекта pack NuGet](/nuget/reference/msbuild-targets#pack-target)
- [Свойства MSBuild для целевого объекта restore NuGet](/nuget/reference/msbuild-targets#restore-properties)
- [Настройка сборки](/visualstudio/msbuild/customize-your-build)
