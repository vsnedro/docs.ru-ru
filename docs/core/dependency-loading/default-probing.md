---
title: Стандартное зондирование (.NET Core)
description: Общие сведения о логике зондирования для поиска зависимостей в System.Runtime.Loader.AssemblyLoadContext.Default (.NET Core).
ms.date: 08/09/2019
author: sdmaclea
ms.author: stmaclea
ms.openlocfilehash: 13ce4c7de5f6ce1b76b2e61db810c0f19717540f
ms.sourcegitcommit: cbb19e56d48cf88375d35d0c27554d4722761e0d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2020
ms.locfileid: "88608424"
---
# <a name="default-probing"></a><span data-ttu-id="41cb2-103">Стандартное зондирование</span><span class="sxs-lookup"><span data-stu-id="41cb2-103">Default probing</span></span>

<span data-ttu-id="41cb2-104">Экземпляр <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> отвечает за поиск зависимостей сборки.</span><span class="sxs-lookup"><span data-stu-id="41cb2-104">The <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> instance is responsible for locating an assembly's dependencies.</span></span> <span data-ttu-id="41cb2-105">В этой статье описана логика зондирования этого экземпляра <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="41cb2-105">This article describes the <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> instance's probing logic.</span></span>

## <a name="host-configured-probing-properties"></a><span data-ttu-id="41cb2-106">Свойства зондирования, настроенные узлом</span><span class="sxs-lookup"><span data-stu-id="41cb2-106">Host configured probing properties</span></span>

<span data-ttu-id="41cb2-107">Когда запускается среда выполнения, узел среды выполнения предоставляет набор именованных свойств зондирования, которые позволяют настроить пути зондирования в <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="41cb2-107">When the runtime is started, the runtime host provides a set of named probing properties that configure <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> probe paths.</span></span>

<span data-ttu-id="41cb2-108">Все свойства зондирования являются необязательными.</span><span class="sxs-lookup"><span data-stu-id="41cb2-108">Each probing property is optional.</span></span> <span data-ttu-id="41cb2-109">Если свойство есть, оно представляет собой строковое значение со списком абсолютных путей с разделителями.</span><span class="sxs-lookup"><span data-stu-id="41cb2-109">If present, each property is a string value that contains a delimited list of absolute paths.</span></span> <span data-ttu-id="41cb2-110">В качестве разделителя используется символ ";" в ОС Windows или ":" на всех других платформах.</span><span class="sxs-lookup"><span data-stu-id="41cb2-110">The delimiter is ';' on Windows and ':' on all other platforms.</span></span>

|<span data-ttu-id="41cb2-111">Имя свойства</span><span class="sxs-lookup"><span data-stu-id="41cb2-111">Property Name</span></span>                 |<span data-ttu-id="41cb2-112">Описание</span><span class="sxs-lookup"><span data-stu-id="41cb2-112">Description</span></span>  |
|------------------------------|---------|
|`TRUSTED_PLATFORM_ASSEMBLIES`   | <span data-ttu-id="41cb2-113">Список путей к файлам сборок платформы и приложения.</span><span class="sxs-lookup"><span data-stu-id="41cb2-113">List of platform and application assembly file paths.</span></span> |
|`PLATFORM_RESOURCE_ROOTS`       | <span data-ttu-id="41cb2-114">Список путей к каталогам, в которых выполняется поиск вспомогательных сборок ресурсов.</span><span class="sxs-lookup"><span data-stu-id="41cb2-114">List of directory paths to search for satellite resource assemblies.</span></span> |
|`NATIVE_DLL_SEARCH_DIRECTORIES` | <span data-ttu-id="41cb2-115">Список путей к каталогам, в которых выполняется поиск неуправляемых (собственных) сборок.</span><span class="sxs-lookup"><span data-stu-id="41cb2-115">List of directory paths to search for unmanaged (native) libraries.</span></span>        |
|`APP_PATHS`                     | <span data-ttu-id="41cb2-116">Список путей к каталогам, в которых выполняется поиск управляемых сборок.</span><span class="sxs-lookup"><span data-stu-id="41cb2-116">List of directory paths to search for managed assemblies.</span></span> |
|`APP_NI_PATHS`                  | <span data-ttu-id="41cb2-117">Список путей к каталогам, в которых выполняется поиск собственных образов для управляемых сборок.</span><span class="sxs-lookup"><span data-stu-id="41cb2-117">List of directory paths to search for native images of managed assemblies.</span></span> |

### <a name="how-are-the-properties-populated"></a><span data-ttu-id="41cb2-118">Как задаются свойства?</span><span class="sxs-lookup"><span data-stu-id="41cb2-118">How are the properties populated?</span></span>

<span data-ttu-id="41cb2-119">Для установки значений свойств есть два основных сценария. Выбор между ними зависит от наличия файла *\<myapp>.deps.json*.</span><span class="sxs-lookup"><span data-stu-id="41cb2-119">There are two main scenarios for populating the properties depending on whether the *\<myapp>.deps.json* file exists.</span></span>

- <span data-ttu-id="41cb2-120">Если файл *\*.deps.json* есть, для свойств зондирования задаются данные из этого файла.</span><span class="sxs-lookup"><span data-stu-id="41cb2-120">When the *\*.deps.json* file is present, it's parsed to populate the probing properties.</span></span>
- <span data-ttu-id="41cb2-121">Если файла *\*.deps.json* нет, предполагается, что все зависимости размещаются в каталоге приложения.</span><span class="sxs-lookup"><span data-stu-id="41cb2-121">When the *\*.deps.json* file isn't present, the application's directory is assumed to contain all the dependencies.</span></span> <span data-ttu-id="41cb2-122">В этом случае для свойств зондирования задается содержимое этого каталога.</span><span class="sxs-lookup"><span data-stu-id="41cb2-122">The directory's contents are used to populate the probing properties.</span></span>

<span data-ttu-id="41cb2-123">Кроме того, аналогичным образом обрабатываются файлы *\*.deps.json* для всех упоминаемых платформ.</span><span class="sxs-lookup"><span data-stu-id="41cb2-123">Additionally, the *\*.deps.json* files for any referenced frameworks are similarly parsed.</span></span>

<span data-ttu-id="41cb2-124">И, наконец, могут добавляться дополнительные зависимости из переменной среды `ADDITIONAL_DEPS`.</span><span class="sxs-lookup"><span data-stu-id="41cb2-124">Finally the environment variable `ADDITIONAL_DEPS` can be used to add additional dependencies.</span></span>  <span data-ttu-id="41cb2-125">`dotnet.exe` также содержит необязательный параметр `--additional-deps` для задания этого значения при запуске приложения.</span><span class="sxs-lookup"><span data-stu-id="41cb2-125">`dotnet.exe` also contains an `--additional-deps` optional parameter to set this value on application startup.</span></span>

<span data-ttu-id="41cb2-126">Свойства `APP_PATHS` и `APP_NI_PATHS` не заполняются по умолчанию и опускаются для большинства приложений.</span><span class="sxs-lookup"><span data-stu-id="41cb2-126">The `APP_PATHS` and `APP_NI_PATHS` properties are not populated by default and are omitted for most applications.</span></span>

<span data-ttu-id="41cb2-127">Список всех файлов *\*.deps.json*, используемых приложением, можно получить через `System.AppContext.GetData("APP_CONTEXT_DEPS_FILES")`.</span><span class="sxs-lookup"><span data-stu-id="41cb2-127">The list of all *\*.deps.json* files used by the application can be accessed via `System.AppContext.GetData("APP_CONTEXT_DEPS_FILES")`.</span></span>

### <a name="how-do-i-see-the-probing-properties-from-managed-code"></a><span data-ttu-id="41cb2-128">Как узнать свойства зондирования из управляемого кода?</span><span class="sxs-lookup"><span data-stu-id="41cb2-128">How do I see the probing properties from managed code?</span></span>

<span data-ttu-id="41cb2-129">Каждое свойство можно получить, вызвав функцию <xref:System.AppContext.GetData(System.String)?displayProperty=nameWithType> с именем свойства. Список имен содержится в приведенной выше таблице.</span><span class="sxs-lookup"><span data-stu-id="41cb2-129">Each property is available by calling the <xref:System.AppContext.GetData(System.String)?displayProperty=nameWithType> function with the property name from the table above.</span></span>

### <a name="how-do-i-debug-the-probing-properties-construction"></a><span data-ttu-id="41cb2-130">Как выполнять отладку формирования свойств зондирования?</span><span class="sxs-lookup"><span data-stu-id="41cb2-130">How do I debug the probing properties' construction?</span></span>

<span data-ttu-id="41cb2-131">Среда выполнения .NET Core будет выводить полезные сообщения трассировки, если настроены определенные переменные среды:</span><span class="sxs-lookup"><span data-stu-id="41cb2-131">The .NET Core runtime host will output useful trace messages when certain environment variables are enabled:</span></span>

|<span data-ttu-id="41cb2-132">Переменная среды</span><span class="sxs-lookup"><span data-stu-id="41cb2-132">Environment Variable</span></span>        |<span data-ttu-id="41cb2-133">Описание</span><span class="sxs-lookup"><span data-stu-id="41cb2-133">Description</span></span>  |
|----------------------------|---------|
|`COREHOST_TRACE=1`          |<span data-ttu-id="41cb2-134">Включение трассировки.</span><span class="sxs-lookup"><span data-stu-id="41cb2-134">Enables tracing.</span></span>|
|`COREHOST_TRACEFILE=<path>` |<span data-ttu-id="41cb2-135">Трассировка по указанному пути вместо стандартного `stderr`.</span><span class="sxs-lookup"><span data-stu-id="41cb2-135">Traces to a file path instead of the default `stderr`.</span></span>|
|`COREHOST_TRACE_VERBOSITY`  |<span data-ttu-id="41cb2-136">Настройка уровня детализации в диапазоне от 1 (минимальный) до 4 (максимальный).</span><span class="sxs-lookup"><span data-stu-id="41cb2-136">Sets the verbosity from 1 (lowest) to 4 (highest).</span></span>|

## <a name="managed-assembly-default-probing"></a><span data-ttu-id="41cb2-137">Стандартное зондирование для управляемой сборки</span><span class="sxs-lookup"><span data-stu-id="41cb2-137">Managed assembly default probing</span></span>

<span data-ttu-id="41cb2-138">При зондировании для поиска управляемой сборки <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> выполняет перебор в следующем порядке:</span><span class="sxs-lookup"><span data-stu-id="41cb2-138">When probing to locate a managed assembly, the <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> looks in order at:</span></span>

- <span data-ttu-id="41cb2-139">файлы, соответствующие <xref:System.Reflection.AssemblyName.Name?displayProperty=nameWithType> в `TRUSTED_PLATFORM_ASSEMBLIES` (без учета расширений);</span><span class="sxs-lookup"><span data-stu-id="41cb2-139">Files matching the <xref:System.Reflection.AssemblyName.Name?displayProperty=nameWithType> in `TRUSTED_PLATFORM_ASSEMBLIES` (after removing file extensions).</span></span>
- <span data-ttu-id="41cb2-140">собственные сборки в файлах образов, расположенных в `APP_NI_PATHS`, с известным расширением файла;</span><span class="sxs-lookup"><span data-stu-id="41cb2-140">Native image assembly files in `APP_NI_PATHS` with common file extensions.</span></span>
- <span data-ttu-id="41cb2-141">файлы сборок, расположенные в `APP_PATHS`, с известным расширением файла.</span><span class="sxs-lookup"><span data-stu-id="41cb2-141">Assembly files in `APP_PATHS` with common file extensions.</span></span>

## <a name="satellite-resource-assembly-probing"></a><span data-ttu-id="41cb2-142">Зондирование для поиска вспомогательной сборки (ресурса)</span><span class="sxs-lookup"><span data-stu-id="41cb2-142">Satellite (resource) assembly probing</span></span>

<span data-ttu-id="41cb2-143">Чтобы найти вспомогательную сборку для определенного языка и региональных параметров, создайте структуру путей к файлам.</span><span class="sxs-lookup"><span data-stu-id="41cb2-143">To find a satellite assembly for a specific culture, construct a set of file paths.</span></span>

<span data-ttu-id="41cb2-144">Для каждого пути в `PLATFORM_RESOURCE_ROOTS` и далее в `APP_PATHS` добавьте строку <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType>, затем символ разделения каталогов, строку <xref:System.Reflection.AssemblyName.Name?displayProperty=nameWithType> и расширение .dll.</span><span class="sxs-lookup"><span data-stu-id="41cb2-144">For each path in `PLATFORM_RESOURCE_ROOTS` and then `APP_PATHS`, append the <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType> string, a directory separator, the <xref:System.Reflection.AssemblyName.Name?displayProperty=nameWithType> string, and the extension '.dll'.</span></span>

<span data-ttu-id="41cb2-145">Если есть любой файл с одним из таких имен, попробуйте загрузить и вернуть его.</span><span class="sxs-lookup"><span data-stu-id="41cb2-145">If any matching file exists, attempt to load and return it.</span></span>

## <a name="unmanaged-native-library-probing"></a><span data-ttu-id="41cb2-146">Зондирование для поиска неуправляемых (собственных) библиотек</span><span class="sxs-lookup"><span data-stu-id="41cb2-146">Unmanaged (native) library probing</span></span>

<span data-ttu-id="41cb2-147">При зондировании для поиска неуправляемой библиотеки, подходящие варианты проверяются в `NATIVE_DLL_SEARCH_DIRECTORIES`.</span><span class="sxs-lookup"><span data-stu-id="41cb2-147">When probing to locate an unmanaged library, the `NATIVE_DLL_SEARCH_DIRECTORIES` are searched looking for a matching library.</span></span>
