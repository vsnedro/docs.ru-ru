---
title: Параметры конфигурация во время выполнения
description: Узнайте, как настроить приложения .NET Core с помощью параметров конфигурации среды выполнения.
ms.date: 01/21/2020
ms.openlocfilehash: 21673a221d0f21202febf4730b955da66132d5f7
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90538202"
---
# <a name="net-core-run-time-configuration-settings"></a><span data-ttu-id="2e8ae-103">Параметры конфигурации среды выполнения .NET Core</span><span class="sxs-lookup"><span data-stu-id="2e8ae-103">.NET Core run-time configuration settings</span></span>

<span data-ttu-id="2e8ae-104">.NET Core поддерживает использование файлов конфигурации и переменных среды для настройки поведения приложений .NET Core во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="2e8ae-104">.NET Core supports the use of configuration files and environment variables to configure the behavior of .NET Core applications at run time.</span></span> <span data-ttu-id="2e8ae-105">Конфигурация среды выполнения является удобным вариантом в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="2e8ae-105">Run-time configuration is an attractive option if:</span></span>

- <span data-ttu-id="2e8ae-106">Вы не владеете исходным кодом приложения или не можете управлять им, поэтому вы не можете задать соответствующие настройки программным способом.</span><span class="sxs-lookup"><span data-stu-id="2e8ae-106">You don't own or control the source code for an application and therefore are unable to configure it programmatically.</span></span>

- <span data-ttu-id="2e8ae-107">Вы одновременно запускаете несколько экземпляров приложения в одной системе и хотите настроить оптимальную производительность для каждого экземпляра.</span><span class="sxs-lookup"><span data-stu-id="2e8ae-107">Multiple instances of your application run at the same time on a single system, and you want to configure each for optimum performance.</span></span>

> [!NOTE]
> <span data-ttu-id="2e8ae-108">Работа над этой документацией продолжается.</span><span class="sxs-lookup"><span data-stu-id="2e8ae-108">This documentation is a work in progress.</span></span> <span data-ttu-id="2e8ae-109">Если вы заметили, что приведенные здесь сведения являются неполными или неточными, [создайте сообщение о проблеме](https://github.com/dotnet/docs/issues), чтобы оповестить нас об этом, или [отправьте запрос на вытягивание](https://github.com/dotnet/docs/pulls) для этой проблемы.</span><span class="sxs-lookup"><span data-stu-id="2e8ae-109">If you notice that the information presented here is either incomplete or inaccurate, either [open an issue](https://github.com/dotnet/docs/issues) to let us know about it, or [submit a pull request](https://github.com/dotnet/docs/pulls) to address the issue.</span></span> <span data-ttu-id="2e8ae-110">Сведения о том, как отправлять запросы на вытягивание для репозитория dotnet/docs, см. в [руководстве участника](/contribute/dotnet/dotnet-contribute).</span><span class="sxs-lookup"><span data-stu-id="2e8ae-110">For information about submitting pull requests for the dotnet/docs repository, see the [contributor's guide](/contribute/dotnet/dotnet-contribute).</span></span>

<span data-ttu-id="2e8ae-111">.NET Core предоставляет следующие механизмы для настройки поведения приложений во время выполнения:</span><span class="sxs-lookup"><span data-stu-id="2e8ae-111">.NET Core provides the following mechanisms for configuring application behavior at run time:</span></span>

- <span data-ttu-id="2e8ae-112">[Файл runtimeconfig.json](#runtimeconfigjson)</span><span class="sxs-lookup"><span data-stu-id="2e8ae-112">The [runtimeconfig.json file](#runtimeconfigjson)</span></span>

- [<span data-ttu-id="2e8ae-113">Свойства MSBuild</span><span class="sxs-lookup"><span data-stu-id="2e8ae-113">MSBuild properties</span></span>](#msbuild-properties)

- [<span data-ttu-id="2e8ae-114">Переменные среды</span><span class="sxs-lookup"><span data-stu-id="2e8ae-114">Environment variables</span></span>](#environment-variables)

> [!TIP]
> <span data-ttu-id="2e8ae-115">При настройке параметра времени выполнения с помощью переменной среды этот параметр будет применяться ко всем приложениям .NET Core.</span><span class="sxs-lookup"><span data-stu-id="2e8ae-115">Configuring a run-time option by using an environment variable applies the setting to all .NET Core apps.</span></span> <span data-ttu-id="2e8ae-116">При настройке параметра времени выполнения в *runtimeconfig.json* или в файле проекта параметр будет действовать только для конкретного приложения.</span><span class="sxs-lookup"><span data-stu-id="2e8ae-116">Configuring a run-time option in the *runtimeconfig.json* or project file applies the setting to that application only.</span></span>

<span data-ttu-id="2e8ae-117">Значения некоторых параметров конфигурации также можно задать программным способом, вызвав метод <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2e8ae-117">Some configuration values can also be set programmatically by calling the <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="2e8ae-118">Статьи в этом разделе документации упорядочены по категориям, например, [отладка](debugging-profiling.md) и [сборка мусора](garbage-collector.md).</span><span class="sxs-lookup"><span data-stu-id="2e8ae-118">The articles in this section of the documentation are organized by category, for example, [debugging](debugging-profiling.md) and [garbage collection](garbage-collector.md).</span></span> <span data-ttu-id="2e8ae-119">В соответствующих случаях параметры конфигурации отображаются для файлов *runtimeconfig.json*, свойств MSBuild, переменных среды и, для перекрестных ссылок, файлов *app.config* для проектов .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2e8ae-119">Where applicable, configuration options are shown for *runtimeconfig.json* files, MSBuild properties, environment variables, and, for cross-reference, *app.config* files for .NET Framework projects.</span></span>

## <a name="runtimeconfigjson"></a><span data-ttu-id="2e8ae-120">runtimeconfig.json</span><span class="sxs-lookup"><span data-stu-id="2e8ae-120">runtimeconfig.json</span></span>

<span data-ttu-id="2e8ae-121">Если проект [собран](../tools/dotnet-build.md), в выходном каталоге создается файл *[имя_приложения].runtimeconfig.json*.</span><span class="sxs-lookup"><span data-stu-id="2e8ae-121">When a project is [built](../tools/dotnet-build.md), an *[appname].runtimeconfig.json* file is generated in the output directory.</span></span> <span data-ttu-id="2e8ae-122">Если файл *runtimeconfig.template.json* находится в той же папке, что и файл проекта, все параметры конфигурации, которые он содержит, объединяются в файл *[имя_приложения].runtimeconfig.json*.</span><span class="sxs-lookup"><span data-stu-id="2e8ae-122">If a *runtimeconfig.template.json* file exists in the same folder as the project file, any configuration options it contains are merged into the *[appname].runtimeconfig.json* file.</span></span> <span data-ttu-id="2e8ae-123">Если вы самостоятельно создаете приложение, разместите все параметры конфигурации в файле *runtimeconfig.template.json*.</span><span class="sxs-lookup"><span data-stu-id="2e8ae-123">If you're building the app yourself, put any configuration options in the *runtimeconfig.template.json* file.</span></span> <span data-ttu-id="2e8ae-124">Если вы только запускаете приложение, вставьте их непосредственно в файл *[имя_приложения].runtimeconfig.json*.</span><span class="sxs-lookup"><span data-stu-id="2e8ae-124">If you're just running the app, insert them directly into the *[appname].runtimeconfig.json* file.</span></span>

> [!NOTE]
> <span data-ttu-id="2e8ae-125">Файл *[имя_приложения].runtimeconfig.json* будет перезаписан при последующих сборках.</span><span class="sxs-lookup"><span data-stu-id="2e8ae-125">The *[appname].runtimeconfig.json* file will get overwritten on subsequent builds.</span></span>

<span data-ttu-id="2e8ae-126">Укажите параметры конфигурации среды выполнения в разделе **configProperties** файлов *runtimeconfig.json*.</span><span class="sxs-lookup"><span data-stu-id="2e8ae-126">Specify run-time configuration options in the **configProperties** section of the *runtimeconfig.json* files.</span></span> <span data-ttu-id="2e8ae-127">Этот раздел имеет следующий вид:</span><span class="sxs-lookup"><span data-stu-id="2e8ae-127">This section has the form:</span></span>

```json
"configProperties": {
  "config-property-name1": "config-value1",
  "config-property-name2": "config-value2"
}
```

### <a name="example-appnameruntimeconfigjson-file"></a><span data-ttu-id="2e8ae-128">Пример файла [имя_приложения].runtimeconfig.json</span><span class="sxs-lookup"><span data-stu-id="2e8ae-128">Example [appname].runtimeconfig.json file</span></span>

<span data-ttu-id="2e8ae-129">Если вы помещаете параметры в выходной JSON-файл, вложите их в свойство `runtimeOptions`.</span><span class="sxs-lookup"><span data-stu-id="2e8ae-129">If you're placing the options in the output JSON file, nest them under the `runtimeOptions` property.</span></span>

```json
{
  "runtimeOptions": {
    "tfm": "netcoreapp3.1",
    "framework": {
      "name": "Microsoft.NETCore.App",
      "version": "3.1.0"
    },
    "configProperties": {
      "System.GC.Concurrent": false,
      "System.Threading.ThreadPool.MinThreads": 4,
      "System.Threading.ThreadPool.MaxThreads": 25
    }
  }
}
```

### <a name="example-runtimeconfigtemplatejson-file"></a><span data-ttu-id="2e8ae-130">Пример файла runtimeconfig.template.json</span><span class="sxs-lookup"><span data-stu-id="2e8ae-130">Example runtimeconfig.template.json file</span></span>

<span data-ttu-id="2e8ae-131">Если вы помещаете параметры в шаблон JSON-файла, опустите свойство `runtimeOptions`.</span><span class="sxs-lookup"><span data-stu-id="2e8ae-131">If you're placing the options in the template JSON file, omit the `runtimeOptions` property.</span></span>

```json
{
  "configProperties": {
    "System.GC.Concurrent": false,
    "System.Threading.ThreadPool.MinThreads": "4",
    "System.Threading.ThreadPool.MaxThreads": "25"
  }
}
```

## <a name="msbuild-properties"></a><span data-ttu-id="2e8ae-132">свойства MSBuild</span><span class="sxs-lookup"><span data-stu-id="2e8ae-132">MSBuild properties</span></span>

<span data-ttu-id="2e8ae-133">Некоторые параметры конфигурации времени выполнения можно задать с помощью свойств MSBuild в файле *CSPROJ* или *VBPROJ* в проектах .NET Core типа SDK.</span><span class="sxs-lookup"><span data-stu-id="2e8ae-133">Some run-time configuration options can be set using MSBuild properties in the *.csproj* or *.vbproj* file of SDK-style .NET Core projects.</span></span> <span data-ttu-id="2e8ae-134">Свойства MSBuild имеют приоритет над параметрами, заданными в файле *runtimeconfig.template.json*.</span><span class="sxs-lookup"><span data-stu-id="2e8ae-134">MSBuild properties take precedence over options set in the *runtimeconfig.template.json* file.</span></span> <span data-ttu-id="2e8ae-135">Они также перезапишут все параметры, заданные в файле *[имя_приложения].runtimeconfig.json* во время сборки.</span><span class="sxs-lookup"><span data-stu-id="2e8ae-135">They also overwrite any options you set in the *[appname].runtimeconfig.json* file at build time.</span></span>

<span data-ttu-id="2e8ae-136">Ниже приведен пример файла проекта в стиле пакета SDK со свойствами MSBuild для настройки поведения во время выполнения:</span><span class="sxs-lookup"><span data-stu-id="2e8ae-136">Here is an example SDK-style project file with MSBuild properties for configuring run-time behavior:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp3.1</TargetFramework>
  </PropertyGroup>

  <PropertyGroup>
    <ConcurrentGarbageCollection>false</ConcurrentGarbageCollection>
    <ThreadPoolMinThreads>4</ThreadPoolMinThreads>
    <ThreadPoolMaxThreads>25</ThreadPoolMaxThreads>
  </PropertyGroup>

</Project>
```

<span data-ttu-id="2e8ae-137">Свойства MSBuild для настройки поведения во время выполнения указаны в отдельных статьях для каждой области, например [сборка мусора](garbage-collector.md).</span><span class="sxs-lookup"><span data-stu-id="2e8ae-137">MSBuild properties for configuring run-time behavior are noted in the individual articles for each area, for example, [garbage collection](garbage-collector.md).</span></span> <span data-ttu-id="2e8ae-138">Они также перечислены в разделе [Свойства конфигурации среды выполнения](../project-sdk/msbuild-props.md#run-time-configuration-properties) в справочнике по свойствам MSBuild для проектов с SDK.</span><span class="sxs-lookup"><span data-stu-id="2e8ae-138">They are also listed in the [Run-time configuration](../project-sdk/msbuild-props.md#run-time-configuration-properties) section of the MSBuild properties reference for SDK-style projects.</span></span>

## <a name="environment-variables"></a><span data-ttu-id="2e8ae-139">Переменные среды</span><span class="sxs-lookup"><span data-stu-id="2e8ae-139">Environment variables</span></span>

<span data-ttu-id="2e8ae-140">Переменные среды можно использовать для предоставления некоторых сведений о конфигурации среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="2e8ae-140">Environment variables can be used to supply some run-time configuration information.</span></span> <span data-ttu-id="2e8ae-141">При настройке параметра времени выполнения с помощью переменной среды этот параметр будет применяться ко всем приложениям .NET Core.</span><span class="sxs-lookup"><span data-stu-id="2e8ae-141">Configuring a run-time option by using an environment variable applies the setting to all .NET Core apps.</span></span> <span data-ttu-id="2e8ae-142">Элементы конфигурации, указанные в качестве переменных среды, обычно имеют префикс **COMPlus_** .</span><span class="sxs-lookup"><span data-stu-id="2e8ae-142">Configuration knobs specified as environment variables generally have the prefix **COMPlus_**.</span></span>

<span data-ttu-id="2e8ae-143">Переменные среды можно определить с помощью панели управления Windows, в командной строке или программным способом, вызвав метод <xref:System.Environment.SetEnvironmentVariable(System.String,System.String)?displayProperty=nameWithType> в Windows и системах на основе Unix.</span><span class="sxs-lookup"><span data-stu-id="2e8ae-143">You can define environment variables from the Windows Control Panel, at the command line, or programmatically by calling the <xref:System.Environment.SetEnvironmentVariable(System.String,System.String)?displayProperty=nameWithType> method on both Windows and Unix-based systems.</span></span>

<span data-ttu-id="2e8ae-144">В следующих примерах показано, как задать переменную среды в командной строке:</span><span class="sxs-lookup"><span data-stu-id="2e8ae-144">The following examples show how to set an environment variable at the command line:</span></span>

```shell
# Windows
set COMPlus_GCRetainVM=1

# Powershell
$env:COMPlus_GCRetainVM="1"

# Unix
export COMPlus_GCRetainVM=1
```
