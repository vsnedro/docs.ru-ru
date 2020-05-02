---
title: Параметры конфигурации сборщика мусора
description: Сведения о параметрах времени выполнения, определяющих, как сборщик мусора управляет памятью для приложений .NET Core.
ms.date: 01/09/2020
ms.topic: reference
ms.openlocfilehash: ec575bdd17c8a7c290673b7085074bbba94cedef
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102870"
---
# <a name="run-time-configuration-options-for-garbage-collection"></a><span data-ttu-id="30d67-103">Параметры конфигурации времени выполнения для сборки мусора</span><span class="sxs-lookup"><span data-stu-id="30d67-103">Run-time configuration options for garbage collection</span></span>

<span data-ttu-id="30d67-104">Эта страница содержит сведения о параметрах сборщика мусора (GC), которые можно изменить во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="30d67-104">This page contains information about garbage collector (GC) settings that can be changed at run time.</span></span> <span data-ttu-id="30d67-105">Если вы пытаетесь добиться пиковой производительности запущенных приложений, рекомендуется использовать эти параметры.</span><span class="sxs-lookup"><span data-stu-id="30d67-105">If you're trying to achieve peak performance of a running app, consider using these settings.</span></span> <span data-ttu-id="30d67-106">Однако значения по умолчанию обеспечивают оптимальную производительность для большинства приложений в типичных ситуациях.</span><span class="sxs-lookup"><span data-stu-id="30d67-106">However, the defaults provide optimum performance for most applications in typical situations.</span></span>

<span data-ttu-id="30d67-107">На этой странице параметры упорядочены по группам.</span><span class="sxs-lookup"><span data-stu-id="30d67-107">Settings are arranged into groups on this page.</span></span> <span data-ttu-id="30d67-108">Параметры в каждой группе обычно используются совместно друг с другом для достижения определенного результата.</span><span class="sxs-lookup"><span data-stu-id="30d67-108">The settings within each group are commonly used in conjunction with each other to achieve a specific result.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="30d67-109">Эти параметры также могут динамически изменяться приложением во время его выполнения, поэтому любые заданные параметры времени выполнения могут быть переопределены.</span><span class="sxs-lookup"><span data-stu-id="30d67-109">These settings can also be changed dynamically by the app as it's running, so any run-time settings you set may be overridden.</span></span>
> - <span data-ttu-id="30d67-110">Некоторые параметры, такие как [уровень задержки](../../standard/garbage-collection/latency.md), обычно задаются только через API во время разработки.</span><span class="sxs-lookup"><span data-stu-id="30d67-110">Some settings, such as [latency level](../../standard/garbage-collection/latency.md), are typically set only through the API at design time.</span></span> <span data-ttu-id="30d67-111">Такие параметры будут пропущены на этой странице.</span><span class="sxs-lookup"><span data-stu-id="30d67-111">Such settings are omitted from this page.</span></span>
> - <span data-ttu-id="30d67-112">Для числовых значений используйте десятичную нотацию для параметров в файле *runtimeconfig.json* и шестнадцатеричную нотацию для параметров переменных среды.</span><span class="sxs-lookup"><span data-stu-id="30d67-112">For number values, use decimal notation for settings in the *runtimeconfig.json* file and hexadecimal notation for environment variable settings.</span></span> <span data-ttu-id="30d67-113">Шестнадцатеричные значения можно указать с помощью префикса "0x" или без него.</span><span class="sxs-lookup"><span data-stu-id="30d67-113">For hexadecimal values, you can specify them with or without the "0x" prefix.</span></span>

## <a name="flavors-of-garbage-collection"></a><span data-ttu-id="30d67-114">Варианты сборки мусора</span><span class="sxs-lookup"><span data-stu-id="30d67-114">Flavors of garbage collection</span></span>

<span data-ttu-id="30d67-115">Два основных варианта сборки мусора — это сборка мусора рабочей станции и сборка мусора сервера.</span><span class="sxs-lookup"><span data-stu-id="30d67-115">The two main flavors of garbage collection are workstation GC and server GC.</span></span> <span data-ttu-id="30d67-116">Дополнительные сведения о различиях между этими двумя вариантами см. в статье [Сборка мусора рабочей станции и сборка мусора сервера](../../standard/garbage-collection/workstation-server-gc.md).</span><span class="sxs-lookup"><span data-stu-id="30d67-116">For more information about differences between the two, see [Workstation and server garbage collection](../../standard/garbage-collection/workstation-server-gc.md).</span></span>

<span data-ttu-id="30d67-117">Подвиды сборки мусора представлены фоновым и непараллельным выполнением.</span><span class="sxs-lookup"><span data-stu-id="30d67-117">The subflavors of garbage collection are background and non-concurrent.</span></span>

<span data-ttu-id="30d67-118">Чтобы выбрать варианты сборки мусора, используйте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="30d67-118">Use the following settings to select flavors of garbage collection:</span></span>

### <a name="systemgcservercomplus_gcserver"></a><span data-ttu-id="30d67-119">System.GC.Server/COMPlus_gcServer</span><span class="sxs-lookup"><span data-stu-id="30d67-119">System.GC.Server/COMPlus_gcServer</span></span>

- <span data-ttu-id="30d67-120">Указывает, использует ли приложение сборку мусора рабочей станции или сборку мусора сервера.</span><span class="sxs-lookup"><span data-stu-id="30d67-120">Configures whether the application uses workstation garbage collection or server garbage collection.</span></span>
- <span data-ttu-id="30d67-121">По умолчанию: сборка мусора рабочей станции (`false`).</span><span class="sxs-lookup"><span data-stu-id="30d67-121">Default: Workstation garbage collection (`false`).</span></span>

| | <span data-ttu-id="30d67-122">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="30d67-122">Setting name</span></span> | <span data-ttu-id="30d67-123">Значения</span><span class="sxs-lookup"><span data-stu-id="30d67-123">Values</span></span> | <span data-ttu-id="30d67-124">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="30d67-124">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="30d67-125">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="30d67-125">**runtimeconfig.json**</span></span> | `System.GC.Server` | <span data-ttu-id="30d67-126">`false` — рабочая станция</span><span class="sxs-lookup"><span data-stu-id="30d67-126">`false` - workstation</span></span><br/><span data-ttu-id="30d67-127">`true` — сервер</span><span class="sxs-lookup"><span data-stu-id="30d67-127">`true` - server</span></span> | <span data-ttu-id="30d67-128">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="30d67-128">.NET Core 1.0</span></span> |
| <span data-ttu-id="30d67-129">**Свойство MSBuild**</span><span class="sxs-lookup"><span data-stu-id="30d67-129">**MSBuild property**</span></span> | `ServerGarbageCollection` | <span data-ttu-id="30d67-130">`false` — рабочая станция</span><span class="sxs-lookup"><span data-stu-id="30d67-130">`false` - workstation</span></span><br/><span data-ttu-id="30d67-131">`true` — сервер</span><span class="sxs-lookup"><span data-stu-id="30d67-131">`true` - server</span></span> | <span data-ttu-id="30d67-132">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="30d67-132">.NET Core 1.0</span></span> |
| <span data-ttu-id="30d67-133">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="30d67-133">**Environment variable**</span></span> | `COMPlus_gcServer` | <span data-ttu-id="30d67-134">`0` — рабочая станция</span><span class="sxs-lookup"><span data-stu-id="30d67-134">`0` - workstation</span></span><br/><span data-ttu-id="30d67-135">`1` — сервер</span><span class="sxs-lookup"><span data-stu-id="30d67-135">`1` - server</span></span> | <span data-ttu-id="30d67-136">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="30d67-136">.NET Core 1.0</span></span> |
| <span data-ttu-id="30d67-137">**app.config для .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="30d67-137">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="30d67-138">GCServer</span><span class="sxs-lookup"><span data-stu-id="30d67-138">GCServer</span></span>](../../framework/configure-apps/file-schema/runtime/gcserver-element.md) | <span data-ttu-id="30d67-139">`false` — рабочая станция</span><span class="sxs-lookup"><span data-stu-id="30d67-139">`false` - workstation</span></span><br/><span data-ttu-id="30d67-140">`true` — сервер</span><span class="sxs-lookup"><span data-stu-id="30d67-140">`true` - server</span></span> |  |

### <a name="examples"></a><span data-ttu-id="30d67-141">Примеры</span><span class="sxs-lookup"><span data-stu-id="30d67-141">Examples</span></span>

<span data-ttu-id="30d67-142">Файл *runtimeconfig.json*</span><span class="sxs-lookup"><span data-stu-id="30d67-142">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Server": true
      }
   }
}
```

<span data-ttu-id="30d67-143">Файл проекта:</span><span class="sxs-lookup"><span data-stu-id="30d67-143">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ServerGarbageCollection>true</ServerGarbageCollection>
  </PropertyGroup>

</Project>
```

### <a name="systemgcconcurrentcomplus_gcconcurrent"></a><span data-ttu-id="30d67-144">System.GC.Concurrent/COMPlus_gcConcurrent</span><span class="sxs-lookup"><span data-stu-id="30d67-144">System.GC.Concurrent/COMPlus_gcConcurrent</span></span>

- <span data-ttu-id="30d67-145">Указывает, включена ли фоновая (параллельная) сборка мусора.</span><span class="sxs-lookup"><span data-stu-id="30d67-145">Configures whether background (concurrent) garbage collection is enabled.</span></span>
- <span data-ttu-id="30d67-146">По умолчанию: включено (`true`).</span><span class="sxs-lookup"><span data-stu-id="30d67-146">Default: Enabled (`true`).</span></span>
- <span data-ttu-id="30d67-147">Дополнительные сведения см. в статье [Фоновая сборка мусора](../../standard/garbage-collection/background-gc.md).</span><span class="sxs-lookup"><span data-stu-id="30d67-147">For more information, see [Background garbage collection](../../standard/garbage-collection/background-gc.md).</span></span>

| | <span data-ttu-id="30d67-148">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="30d67-148">Setting name</span></span> | <span data-ttu-id="30d67-149">Значения</span><span class="sxs-lookup"><span data-stu-id="30d67-149">Values</span></span> | <span data-ttu-id="30d67-150">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="30d67-150">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="30d67-151">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="30d67-151">**runtimeconfig.json**</span></span> | `System.GC.Concurrent` | <span data-ttu-id="30d67-152">`true` —фоновая сборка мусора</span><span class="sxs-lookup"><span data-stu-id="30d67-152">`true` - background GC</span></span><br/><span data-ttu-id="30d67-153">`false` — непараллельная сборка мусора</span><span class="sxs-lookup"><span data-stu-id="30d67-153">`false` - non-concurrent GC</span></span> | <span data-ttu-id="30d67-154">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="30d67-154">.NET Core 1.0</span></span> |
| <span data-ttu-id="30d67-155">**Свойство MSBuild**</span><span class="sxs-lookup"><span data-stu-id="30d67-155">**MSBuild property**</span></span> | `ConcurrentGarbageCollection` | <span data-ttu-id="30d67-156">`true` —фоновая сборка мусора</span><span class="sxs-lookup"><span data-stu-id="30d67-156">`true` - background GC</span></span><br/><span data-ttu-id="30d67-157">`false` — непараллельная сборка мусора</span><span class="sxs-lookup"><span data-stu-id="30d67-157">`false` - non-concurrent GC</span></span> | <span data-ttu-id="30d67-158">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="30d67-158">.NET Core 1.0</span></span> |
| <span data-ttu-id="30d67-159">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="30d67-159">**Environment variable**</span></span> | `COMPlus_gcConcurrent` | <span data-ttu-id="30d67-160">`true` —фоновая сборка мусора</span><span class="sxs-lookup"><span data-stu-id="30d67-160">`true` - background GC</span></span><br/><span data-ttu-id="30d67-161">`false` — непараллельная сборка мусора</span><span class="sxs-lookup"><span data-stu-id="30d67-161">`false` - non-concurrent GC</span></span> | <span data-ttu-id="30d67-162">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="30d67-162">.NET Core 1.0</span></span> |
| <span data-ttu-id="30d67-163">**app.config для .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="30d67-163">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="30d67-164">gcConcurrent</span><span class="sxs-lookup"><span data-stu-id="30d67-164">gcConcurrent</span></span>](../../framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) | <span data-ttu-id="30d67-165">`true` —фоновая сборка мусора</span><span class="sxs-lookup"><span data-stu-id="30d67-165">`true` - background GC</span></span><br/><span data-ttu-id="30d67-166">`false` — непараллельная сборка мусора</span><span class="sxs-lookup"><span data-stu-id="30d67-166">`false` - non-concurrent GC</span></span> |  |

### <a name="examples"></a><span data-ttu-id="30d67-167">Примеры</span><span class="sxs-lookup"><span data-stu-id="30d67-167">Examples</span></span>

<span data-ttu-id="30d67-168">Файл *runtimeconfig.json*</span><span class="sxs-lookup"><span data-stu-id="30d67-168">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Concurrent": false
      }
   }
}
```

<span data-ttu-id="30d67-169">Файл проекта:</span><span class="sxs-lookup"><span data-stu-id="30d67-169">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ConcurrentGarbageCollection>false</ConcurrentGarbageCollection>
  </PropertyGroup>

</Project>
```

## <a name="manage-resource-usage"></a><span data-ttu-id="30d67-170">Управление использованием ресурсов</span><span class="sxs-lookup"><span data-stu-id="30d67-170">Manage resource usage</span></span>

<span data-ttu-id="30d67-171">Используйте параметры, описанные в этом разделе, для управления использованием памяти и ЦП в сборщике мусора.</span><span class="sxs-lookup"><span data-stu-id="30d67-171">Use the settings described in this section to manage the garbage collector's memory and processor usage.</span></span>

<span data-ttu-id="30d67-172">Дополнительные сведения о некоторых из этих параметров см. в записи блога о [компромиссе между сборкой мусора рабочей станции и сервера](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/).</span><span class="sxs-lookup"><span data-stu-id="30d67-172">For more information about some of these settings, see the [Middle ground between workstation and server GC](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/) blog entry.</span></span>

### <a name="systemgcheapcountcomplus_gcheapcount"></a><span data-ttu-id="30d67-173">System.GC.HeapCount/COMPlus_GCHeapCount</span><span class="sxs-lookup"><span data-stu-id="30d67-173">System.GC.HeapCount/COMPlus_GCHeapCount</span></span>

- <span data-ttu-id="30d67-174">Ограничивает число куч, создаваемых сборщиком мусора.</span><span class="sxs-lookup"><span data-stu-id="30d67-174">Limits the number of heaps created by the garbage collector.</span></span>
- <span data-ttu-id="30d67-175">Применяется только к сборке мусора сервера.</span><span class="sxs-lookup"><span data-stu-id="30d67-175">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="30d67-176">Если включено [сходство процессоров сборки мусора](#systemgcnoaffinitizecomplus_gcnoaffinitize), что используется по умолчанию, параметр счетчика куч реализует сходство `n` куч/потоков сборки мусора с первыми `n` процессорами.</span><span class="sxs-lookup"><span data-stu-id="30d67-176">If [GC processor affinity](#systemgcnoaffinitizecomplus_gcnoaffinitize) is enabled, which is the default, the heap count setting affinitizes `n` GC heaps/threads to the first `n` processors.</span></span> <span data-ttu-id="30d67-177">(Используйте параметры [сходства маски](#systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask) или [сходства диапазонов](#systemgcgcheapaffinitizerangescomplus_gcheapaffinitizeranges), чтобы указать, для каких именно процессоров следует реализовать сходство.)</span><span class="sxs-lookup"><span data-stu-id="30d67-177">(Use the [affinitize mask](#systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask) or [affinitize ranges](#systemgcgcheapaffinitizerangescomplus_gcheapaffinitizeranges) settings to specify exactly which processors to affinitize.)</span></span>
- <span data-ttu-id="30d67-178">Если [сходство процессоров сборки мусора](#systemgcnoaffinitizecomplus_gcnoaffinitize) отключено, этот параметр будет ограничивать количество куч сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="30d67-178">If [GC processor affinity](#systemgcnoaffinitizecomplus_gcnoaffinitize) is disabled, this setting limits the number of GC heaps.</span></span>
- <span data-ttu-id="30d67-179">Дополнительные сведения см. в [примечаниях по GCHeapCount](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md#remarks).</span><span class="sxs-lookup"><span data-stu-id="30d67-179">For more information, see the [GCHeapCount remarks](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md#remarks).</span></span>

| | <span data-ttu-id="30d67-180">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="30d67-180">Setting name</span></span> | <span data-ttu-id="30d67-181">Значения</span><span class="sxs-lookup"><span data-stu-id="30d67-181">Values</span></span> | <span data-ttu-id="30d67-182">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="30d67-182">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="30d67-183">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="30d67-183">**runtimeconfig.json**</span></span> | `System.GC.HeapCount` | <span data-ttu-id="30d67-184">*Десятичное значение*</span><span class="sxs-lookup"><span data-stu-id="30d67-184">*decimal value*</span></span> | <span data-ttu-id="30d67-185">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="30d67-185">.NET Core 3.0</span></span> |
| <span data-ttu-id="30d67-186">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="30d67-186">**Environment variable**</span></span> | `COMPlus_GCHeapCount` | <span data-ttu-id="30d67-187">*Шестнадцатеричное значение*</span><span class="sxs-lookup"><span data-stu-id="30d67-187">*hexadecimal value*</span></span> | <span data-ttu-id="30d67-188">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="30d67-188">.NET Core 3.0</span></span> |
| <span data-ttu-id="30d67-189">**app.config для .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="30d67-189">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="30d67-190">GCHeapCount</span><span class="sxs-lookup"><span data-stu-id="30d67-190">GCHeapCount</span></span>](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md) | <span data-ttu-id="30d67-191">*Десятичное значение*</span><span class="sxs-lookup"><span data-stu-id="30d67-191">*decimal value*</span></span> | <span data-ttu-id="30d67-192">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="30d67-192">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="30d67-193">Пример.</span><span class="sxs-lookup"><span data-stu-id="30d67-193">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.HeapCount": 16
      }
   }
}
```

> [!TIP]
> <span data-ttu-id="30d67-194">Если вы задаете параметр в *runtimeconfig.json*, укажите десятичное значение.</span><span class="sxs-lookup"><span data-stu-id="30d67-194">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="30d67-195">Если вы задаете параметр в виде переменной среды, укажите шестнадцатеричное значение.</span><span class="sxs-lookup"><span data-stu-id="30d67-195">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="30d67-196">Например, чтобы ограничить число куч значением 16, для JSON-файла нужно указать 16, а для переменной среды — 0x10 или 10.</span><span class="sxs-lookup"><span data-stu-id="30d67-196">For example, to limit the number of heaps to 16, the values would be 16 for the JSON file and 0x10 or 10 for the environment variable.</span></span>

### <a name="systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask"></a><span data-ttu-id="30d67-197">System.GC.HeapAffinitizeMask/COMPlus_GCHeapAffinitizeMask</span><span class="sxs-lookup"><span data-stu-id="30d67-197">System.GC.HeapAffinitizeMask/COMPlus_GCHeapAffinitizeMask</span></span>

- <span data-ttu-id="30d67-198">Указывает конкретные процессоры, которые должны использоваться потоками сборщика мусора.</span><span class="sxs-lookup"><span data-stu-id="30d67-198">Specifies the exact processors that garbage collector threads should use.</span></span>
- <span data-ttu-id="30d67-199">Если [сходство процессоров](#systemgcnoaffinitizecomplus_gcnoaffinitize) отключено, этот параметр игнорируется.</span><span class="sxs-lookup"><span data-stu-id="30d67-199">If [GC processor affinity](#systemgcnoaffinitizecomplus_gcnoaffinitize) is disabled, this setting is ignored.</span></span>
- <span data-ttu-id="30d67-200">Применяется только к сборке мусора сервера.</span><span class="sxs-lookup"><span data-stu-id="30d67-200">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="30d67-201">Это значение представляет собой битовую маску, которая определяет доступные процессу процессоры.</span><span class="sxs-lookup"><span data-stu-id="30d67-201">The value is a bit mask that defines the processors that are available to the process.</span></span> <span data-ttu-id="30d67-202">Например, десятичное значение 1023 (или шестнадцатеричное значение 0x3FF или 3FF, если вы используете переменную среды), равно 0011 1111 1111 в двоичной нотации.</span><span class="sxs-lookup"><span data-stu-id="30d67-202">For example, a decimal value of 1023 (or a hexadecimal value of 0x3FF or 3FF if you're using the environment variable) is 0011 1111 1111 in binary notation.</span></span> <span data-ttu-id="30d67-203">При этом будут использоваться первые 10 процессоров.</span><span class="sxs-lookup"><span data-stu-id="30d67-203">This specifies that the first 10 processors are to be used.</span></span> <span data-ttu-id="30d67-204">Чтобы указать следующие 10 процессоров, то есть процессоры 10–19, задайте десятичное значение 1047552 (или шестнадцатеричное значение 0xFFC00 или FFC00), которое эквивалентно двоичному значению 1111 1111 1100 0000 0000.</span><span class="sxs-lookup"><span data-stu-id="30d67-204">To specify the next 10 processors, that is, processors 10-19, specify a decimal value of 1047552 (or a hexadecimal value of 0xFFC00 or FFC00), which is equivalent to a binary value of 1111 1111 1100 0000 0000.</span></span>

| | <span data-ttu-id="30d67-205">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="30d67-205">Setting name</span></span> | <span data-ttu-id="30d67-206">Значения</span><span class="sxs-lookup"><span data-stu-id="30d67-206">Values</span></span> | <span data-ttu-id="30d67-207">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="30d67-207">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="30d67-208">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="30d67-208">**runtimeconfig.json**</span></span> | `System.GC.HeapAffinitizeMask` | <span data-ttu-id="30d67-209">*Десятичное значение*</span><span class="sxs-lookup"><span data-stu-id="30d67-209">*decimal value*</span></span> | <span data-ttu-id="30d67-210">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="30d67-210">.NET Core 3.0</span></span> |
| <span data-ttu-id="30d67-211">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="30d67-211">**Environment variable**</span></span> | `COMPlus_GCHeapAffinitizeMask` | <span data-ttu-id="30d67-212">*Шестнадцатеричное значение*</span><span class="sxs-lookup"><span data-stu-id="30d67-212">*hexadecimal value*</span></span> | <span data-ttu-id="30d67-213">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="30d67-213">.NET Core 3.0</span></span> |
| <span data-ttu-id="30d67-214">**app.config для .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="30d67-214">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="30d67-215">GCHeapAffinitizeMask</span><span class="sxs-lookup"><span data-stu-id="30d67-215">GCHeapAffinitizeMask</span></span>](../../framework/configure-apps/file-schema/runtime/gcheapaffinitizemask-element.md) | <span data-ttu-id="30d67-216">*Десятичное значение*</span><span class="sxs-lookup"><span data-stu-id="30d67-216">*decimal value*</span></span> | <span data-ttu-id="30d67-217">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="30d67-217">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="30d67-218">Пример.</span><span class="sxs-lookup"><span data-stu-id="30d67-218">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.HeapAffinitizeMask": 1023
      }
   }
}
```

### <a name="systemgcgcheapaffinitizerangescomplus_gcheapaffinitizeranges"></a><span data-ttu-id="30d67-219">System.GC.GCHeapAffinitizeRanges/COMPlus_GCHeapAffinitizeRanges</span><span class="sxs-lookup"><span data-stu-id="30d67-219">System.GC.GCHeapAffinitizeRanges/COMPlus_GCHeapAffinitizeRanges</span></span>

- <span data-ttu-id="30d67-220">Указывает список процессоров, используемых для потоков сборщика мусора.</span><span class="sxs-lookup"><span data-stu-id="30d67-220">Specifies the list of processors to use for garbage collector threads.</span></span>
- <span data-ttu-id="30d67-221">Этот параметр аналогичен [System.GC.HeapAffinitizeMask](#systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask), за исключением того, что он позволяет указать больше 64 процессоров.</span><span class="sxs-lookup"><span data-stu-id="30d67-221">This setting is similar to [System.GC.HeapAffinitizeMask](#systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask), except it allows you to specify more than 64 processors.</span></span>
- <span data-ttu-id="30d67-222">Для операционных систем Windows добавьте к номеру или диапазону процессоров префикс в виде соответствующей [группы ЦП](/windows/win32/procthread/processor-groups), например "0:1-10,0:12,1:50-52,1:70".</span><span class="sxs-lookup"><span data-stu-id="30d67-222">For Windows operating systems, prefix the processor number or range with the corresponding [CPU group](/windows/win32/procthread/processor-groups), for example, "0:1-10,0:12,1:50-52,1:70".</span></span>
- <span data-ttu-id="30d67-223">Если [сходство процессоров](#systemgcnoaffinitizecomplus_gcnoaffinitize) отключено, этот параметр игнорируется.</span><span class="sxs-lookup"><span data-stu-id="30d67-223">If [GC processor affinity](#systemgcnoaffinitizecomplus_gcnoaffinitize) is disabled, this setting is ignored.</span></span>
- <span data-ttu-id="30d67-224">Применяется только к сборке мусора сервера.</span><span class="sxs-lookup"><span data-stu-id="30d67-224">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="30d67-225">Дополнительные сведения см. в записи об [улучшении конфигурации ЦП для сборки мусора на компьютерах, имеющих более 64 ЦП](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/), в блоге Майони Стивенс (Maoni Stephens).</span><span class="sxs-lookup"><span data-stu-id="30d67-225">For more information, see [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) on Maoni Stephens' blog.</span></span>

| | <span data-ttu-id="30d67-226">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="30d67-226">Setting name</span></span> | <span data-ttu-id="30d67-227">Значения</span><span class="sxs-lookup"><span data-stu-id="30d67-227">Values</span></span> | <span data-ttu-id="30d67-228">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="30d67-228">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="30d67-229">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="30d67-229">**runtimeconfig.json**</span></span> | `System.GC.GCHeapAffinitizeRanges` | <span data-ttu-id="30d67-230">Разделенный запятыми список номеров процессоров или диапазонов номеров процессоров.</span><span class="sxs-lookup"><span data-stu-id="30d67-230">Comma-separated list of processor numbers or ranges of processor numbers.</span></span><br/><span data-ttu-id="30d67-231">Пример для Unix: "1-10,12,50-52,70"</span><span class="sxs-lookup"><span data-stu-id="30d67-231">Unix example: "1-10,12,50-52,70"</span></span><br/><span data-ttu-id="30d67-232">Пример для Windows: "0:1-10,0:12,1:50-52,1:70"</span><span class="sxs-lookup"><span data-stu-id="30d67-232">Windows example: "0:1-10,0:12,1:50-52,1:70"</span></span> | <span data-ttu-id="30d67-233">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="30d67-233">.NET Core 3.0</span></span> |
| <span data-ttu-id="30d67-234">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="30d67-234">**Environment variable**</span></span> | `COMPlus_GCHeapAffinitizeRanges` | <span data-ttu-id="30d67-235">Разделенный запятыми список номеров процессоров или диапазонов номеров процессоров.</span><span class="sxs-lookup"><span data-stu-id="30d67-235">Comma-separated list of processor numbers or ranges of processor numbers.</span></span><br/><span data-ttu-id="30d67-236">Пример для Unix: "1-10,12,50-52,70"</span><span class="sxs-lookup"><span data-stu-id="30d67-236">Unix example: "1-10,12,50-52,70"</span></span><br/><span data-ttu-id="30d67-237">Пример для Windows: "0:1-10,0:12,1:50-52,1:70"</span><span class="sxs-lookup"><span data-stu-id="30d67-237">Windows example: "0:1-10,0:12,1:50-52,1:70"</span></span> | <span data-ttu-id="30d67-238">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="30d67-238">.NET Core 3.0</span></span> |

<span data-ttu-id="30d67-239">Пример.</span><span class="sxs-lookup"><span data-stu-id="30d67-239">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.GCHeapAffinitizeRanges": "0:1-10,0:12,1:50-52,1:70"
      }
   }
}
```

### <a name="complus_gccpugroup"></a><span data-ttu-id="30d67-240">COMPlus_GCCpuGroup</span><span class="sxs-lookup"><span data-stu-id="30d67-240">COMPlus_GCCpuGroup</span></span>

- <span data-ttu-id="30d67-241">Указывает, использует ли сборщик мусора [группы ЦП](/windows/win32/procthread/processor-groups).</span><span class="sxs-lookup"><span data-stu-id="30d67-241">Configures whether the garbage collector uses [CPU groups](/windows/win32/procthread/processor-groups) or not.</span></span>

  <span data-ttu-id="30d67-242">Когда 64-разрядный компьютер с Windows имеет несколько групп ЦП, то есть доступно более 64 процессоров, включение этого элемента расширяет действие сборки мусора на все группы ЦП.</span><span class="sxs-lookup"><span data-stu-id="30d67-242">When a 64-bit Windows computer has multiple CPU groups, that is, there are more than 64 processors, enabling this element extends garbage collection across all CPU groups.</span></span> <span data-ttu-id="30d67-243">Сборщик мусора использует все ядра для создания и балансировки куч.</span><span class="sxs-lookup"><span data-stu-id="30d67-243">The garbage collector uses all cores to create and balance heaps.</span></span>

- <span data-ttu-id="30d67-244">Применяется только к сборке мусора сервера в 64-разрядных операционных системах Windows.</span><span class="sxs-lookup"><span data-stu-id="30d67-244">Applies to server garbage collection on 64-bit Windows operation systems only.</span></span>
- <span data-ttu-id="30d67-245">По умолчанию: отключено (`0`).</span><span class="sxs-lookup"><span data-stu-id="30d67-245">Default: Disabled (`0`).</span></span>
- <span data-ttu-id="30d67-246">Дополнительные сведения см. в записи об [улучшении конфигурации ЦП для сборки мусора на компьютерах, имеющих более 64 ЦП](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/), в блоге Майони Стивенс (Maoni Stephens).</span><span class="sxs-lookup"><span data-stu-id="30d67-246">For more information, see [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) on Maoni Stephens' blog.</span></span>

| | <span data-ttu-id="30d67-247">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="30d67-247">Setting name</span></span> | <span data-ttu-id="30d67-248">Значения</span><span class="sxs-lookup"><span data-stu-id="30d67-248">Values</span></span> | <span data-ttu-id="30d67-249">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="30d67-249">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="30d67-250">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="30d67-250">**runtimeconfig.json**</span></span> | <span data-ttu-id="30d67-251">Н/Д</span><span class="sxs-lookup"><span data-stu-id="30d67-251">N/A</span></span> | <span data-ttu-id="30d67-252">Н/Д</span><span class="sxs-lookup"><span data-stu-id="30d67-252">N/A</span></span> | <span data-ttu-id="30d67-253">Н/Д</span><span class="sxs-lookup"><span data-stu-id="30d67-253">N/A</span></span> |
| <span data-ttu-id="30d67-254">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="30d67-254">**Environment variable**</span></span> | `COMPlus_GCCpuGroup` | <span data-ttu-id="30d67-255">`0` — отключено</span><span class="sxs-lookup"><span data-stu-id="30d67-255">`0` - disabled</span></span><br/><span data-ttu-id="30d67-256">`1` — включено</span><span class="sxs-lookup"><span data-stu-id="30d67-256">`1` - enabled</span></span> | <span data-ttu-id="30d67-257">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="30d67-257">.NET Core 1.0</span></span> |
| <span data-ttu-id="30d67-258">**app.config для .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="30d67-258">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="30d67-259">GCCpuGroup</span><span class="sxs-lookup"><span data-stu-id="30d67-259">GCCpuGroup</span></span>](../../framework/configure-apps/file-schema/runtime/gccpugroup-element.md) | <span data-ttu-id="30d67-260">`false` — отключено</span><span class="sxs-lookup"><span data-stu-id="30d67-260">`false` - disabled</span></span><br/><span data-ttu-id="30d67-261">`true` — включено</span><span class="sxs-lookup"><span data-stu-id="30d67-261">`true` - enabled</span></span> |  |

> [!NOTE]
> <span data-ttu-id="30d67-262">Чтобы настроить среду CLR для распределения потоков из пула потоков по всем группам ЦП, включите параметр [Элемент Thread_UseAllCpuGroups](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md).</span><span class="sxs-lookup"><span data-stu-id="30d67-262">To configure the common language runtime (CLR) to also distribute threads from the thread pool across all CPU groups, enable the [Thread_UseAllCpuGroups element](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md) option.</span></span> <span data-ttu-id="30d67-263">Для приложений .NET Core этот параметр можно включить, задав для переменной среды `COMPlus_Thread_UseAllCpuGroups` значение `1`.</span><span class="sxs-lookup"><span data-stu-id="30d67-263">For .NET Core apps, you can enable this option by setting the value of the `COMPlus_Thread_UseAllCpuGroups` environment variable to `1`.</span></span>

### <a name="systemgcnoaffinitizecomplus_gcnoaffinitize"></a><span data-ttu-id="30d67-264">System.GC.NoAffinitize/COMPlus_GCNoAffinitize</span><span class="sxs-lookup"><span data-stu-id="30d67-264">System.GC.NoAffinitize/COMPlus_GCNoAffinitize</span></span>

- <span data-ttu-id="30d67-265">Указывает, следует ли *реализовать сходство* потоков сборки мусора с процессорами.</span><span class="sxs-lookup"><span data-stu-id="30d67-265">Specifies whether to *affinitize* garbage collection threads with processors.</span></span> <span data-ttu-id="30d67-266">Реализация сходства потока сборки мусора означает, что он может выполняться только на определенном ЦП.</span><span class="sxs-lookup"><span data-stu-id="30d67-266">To affinitize a GC thread means that it can only run on its specific CPU.</span></span> <span data-ttu-id="30d67-267">Куча создается для каждого потока сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="30d67-267">A heap is created for each GC thread.</span></span>
- <span data-ttu-id="30d67-268">Применяется только к сборке мусора сервера.</span><span class="sxs-lookup"><span data-stu-id="30d67-268">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="30d67-269">По умолчанию: реализация сходства потоков сборки мусора с процессорами (`false`).</span><span class="sxs-lookup"><span data-stu-id="30d67-269">Default: Affinitize garbage collection threads with processors (`false`).</span></span>

| | <span data-ttu-id="30d67-270">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="30d67-270">Setting name</span></span> | <span data-ttu-id="30d67-271">Значения</span><span class="sxs-lookup"><span data-stu-id="30d67-271">Values</span></span> | <span data-ttu-id="30d67-272">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="30d67-272">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="30d67-273">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="30d67-273">**runtimeconfig.json**</span></span> | `System.GC.NoAffinitize` | <span data-ttu-id="30d67-274">`false` — реализовать сходство</span><span class="sxs-lookup"><span data-stu-id="30d67-274">`false` - affinitize</span></span><br/><span data-ttu-id="30d67-275">`true` — не реализовывать сходство</span><span class="sxs-lookup"><span data-stu-id="30d67-275">`true` - don't affinitize</span></span> | <span data-ttu-id="30d67-276">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="30d67-276">.NET Core 3.0</span></span> |
| <span data-ttu-id="30d67-277">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="30d67-277">**Environment variable**</span></span> | `COMPlus_GCNoAffinitize` | <span data-ttu-id="30d67-278">`0` — реализовать сходство</span><span class="sxs-lookup"><span data-stu-id="30d67-278">`0` - affinitize</span></span><br/><span data-ttu-id="30d67-279">`1` — не реализовывать сходство</span><span class="sxs-lookup"><span data-stu-id="30d67-279">`1` - don't affinitize</span></span> | <span data-ttu-id="30d67-280">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="30d67-280">.NET Core 3.0</span></span> |
| <span data-ttu-id="30d67-281">**app.config для .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="30d67-281">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="30d67-282">GCNoAffinitize</span><span class="sxs-lookup"><span data-stu-id="30d67-282">GCNoAffinitize</span></span>](../../framework/configure-apps/file-schema/runtime/gcnoaffinitize-element.md) | <span data-ttu-id="30d67-283">`false` — реализовать сходство</span><span class="sxs-lookup"><span data-stu-id="30d67-283">`false` - affinitize</span></span><br/><span data-ttu-id="30d67-284">`true` — не реализовывать сходство</span><span class="sxs-lookup"><span data-stu-id="30d67-284">`true` - don't affinitize</span></span> | <span data-ttu-id="30d67-285">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="30d67-285">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="30d67-286">Пример.</span><span class="sxs-lookup"><span data-stu-id="30d67-286">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.NoAffinitize": true
      }
   }
}
```

### <a name="systemgcheaphardlimitcomplus_gcheaphardlimit"></a><span data-ttu-id="30d67-287">System.GC.HeapHardLimit/COMPlus_GCHeapHardLimit</span><span class="sxs-lookup"><span data-stu-id="30d67-287">System.GC.HeapHardLimit/COMPlus_GCHeapHardLimit</span></span>

- <span data-ttu-id="30d67-288">Указывает максимальный размер фиксации в байтах для кучи сборки мусора и учета сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="30d67-288">Specifies the maximum commit size, in bytes, for the GC heap and GC bookkeeping.</span></span>
- <span data-ttu-id="30d67-289">Этот параметр применим только к 64-разрядным компьютерам.</span><span class="sxs-lookup"><span data-stu-id="30d67-289">This setting only applies to 64-bit computers.</span></span>
- <span data-ttu-id="30d67-290">Значение по умолчанию, которое применяется только в определенных случаях, превышает 20 МБ или 75 % предельного объема памяти в контейнере.</span><span class="sxs-lookup"><span data-stu-id="30d67-290">The default value, which only applies in certain cases, is the greater of 20 MB or 75% of the memory limit on the container.</span></span> <span data-ttu-id="30d67-291">Значение по умолчанию применяется, если:</span><span class="sxs-lookup"><span data-stu-id="30d67-291">The default value applies if:</span></span>

  - <span data-ttu-id="30d67-292">процесс выполняется в контейнере с заданным предельным объемом памяти;</span><span class="sxs-lookup"><span data-stu-id="30d67-292">The process is running inside a container that has a specified memory limit.</span></span>
  - <span data-ttu-id="30d67-293">параметр [System.GC.HeapHardLimitPercent](#systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent) не задан.</span><span class="sxs-lookup"><span data-stu-id="30d67-293">[System.GC.HeapHardLimitPercent](#systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent) is not set.</span></span>

| | <span data-ttu-id="30d67-294">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="30d67-294">Setting name</span></span> | <span data-ttu-id="30d67-295">Значения</span><span class="sxs-lookup"><span data-stu-id="30d67-295">Values</span></span> | <span data-ttu-id="30d67-296">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="30d67-296">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="30d67-297">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="30d67-297">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimit` | <span data-ttu-id="30d67-298">*Десятичное значение*</span><span class="sxs-lookup"><span data-stu-id="30d67-298">*decimal value*</span></span> | <span data-ttu-id="30d67-299">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="30d67-299">.NET Core 3.0</span></span> |
| <span data-ttu-id="30d67-300">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="30d67-300">**Environment variable**</span></span> | `COMPlus_GCHeapHardLimit` | <span data-ttu-id="30d67-301">*Шестнадцатеричное значение*</span><span class="sxs-lookup"><span data-stu-id="30d67-301">*hexadecimal value*</span></span> | <span data-ttu-id="30d67-302">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="30d67-302">.NET Core 3.0</span></span> |

<span data-ttu-id="30d67-303">Пример.</span><span class="sxs-lookup"><span data-stu-id="30d67-303">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.HeapHardLimit": 209715200
      }
   }
}
```

> [!TIP]
> <span data-ttu-id="30d67-304">Если вы задаете параметр в *runtimeconfig.json*, укажите десятичное значение.</span><span class="sxs-lookup"><span data-stu-id="30d67-304">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="30d67-305">Если вы задаете параметр в виде переменной среды, укажите шестнадцатеричное значение.</span><span class="sxs-lookup"><span data-stu-id="30d67-305">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="30d67-306">Например, чтобы задать для куч жесткое ограничение в 200 мебибайт (Миб), для JSON-файла нужно указать значение 209715200, а для переменной среды — значение 0xC800000 или C800000.</span><span class="sxs-lookup"><span data-stu-id="30d67-306">For example, to specify a heap hard limit of 200 mebibytes (MiB), the values would be 209715200 for the JSON file and 0xC800000 or C800000 for the environment variable.</span></span>

### <a name="systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent"></a><span data-ttu-id="30d67-307">System.GC.HeapHardLimitPercent/COMPlus_GCHeapHardLimitPercent</span><span class="sxs-lookup"><span data-stu-id="30d67-307">System.GC.HeapHardLimitPercent/COMPlus_GCHeapHardLimitPercent</span></span>

- <span data-ttu-id="30d67-308">Указывает допустимое использование кучи сборки мусора в процентах от общего объема физической памяти.</span><span class="sxs-lookup"><span data-stu-id="30d67-308">Specifies the allowable GC heap usage as a percentage of the total physical memory.</span></span>
- <span data-ttu-id="30d67-309">Если также задан параметр [System.GC.HeapHardLimit](#systemgcheaphardlimitcomplus_gcheaphardlimit), этот параметр игнорируется.</span><span class="sxs-lookup"><span data-stu-id="30d67-309">If [System.GC.HeapHardLimit](#systemgcheaphardlimitcomplus_gcheaphardlimit) is also set, this setting is ignored.</span></span>
- <span data-ttu-id="30d67-310">Этот параметр применим только к 64-разрядным компьютерам.</span><span class="sxs-lookup"><span data-stu-id="30d67-310">This setting only applies to 64-bit computers.</span></span>
- <span data-ttu-id="30d67-311">Если процесс выполняется в контейнере с заданным предельным объемом памяти, процентная доля вычисляется как процент от этого объема памяти.</span><span class="sxs-lookup"><span data-stu-id="30d67-311">If the process is running inside a container that has a specified memory limit, the percentage is calculated as a percentage of that memory limit.</span></span>
- <span data-ttu-id="30d67-312">Значение по умолчанию, которое применяется только в определенных случаях, не превышает 20 МБ или 75 % предельного объема памяти в контейнере.</span><span class="sxs-lookup"><span data-stu-id="30d67-312">The default value, which only applies in certain cases, is the lesser of 20 MB or 75% of the memory limit on the container.</span></span> <span data-ttu-id="30d67-313">Значение по умолчанию применяется, если:</span><span class="sxs-lookup"><span data-stu-id="30d67-313">The default value applies if:</span></span>

  - <span data-ttu-id="30d67-314">процесс выполняется в контейнере с заданным предельным объемом памяти;</span><span class="sxs-lookup"><span data-stu-id="30d67-314">The process is running inside a container that has a specified memory limit.</span></span>
  - <span data-ttu-id="30d67-315">параметр [System.GC.HeapHardLimit](#systemgcheaphardlimitcomplus_gcheaphardlimit) не задан.</span><span class="sxs-lookup"><span data-stu-id="30d67-315">[System.GC.HeapHardLimit](#systemgcheaphardlimitcomplus_gcheaphardlimit) is not set.</span></span>

| | <span data-ttu-id="30d67-316">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="30d67-316">Setting name</span></span> | <span data-ttu-id="30d67-317">Значения</span><span class="sxs-lookup"><span data-stu-id="30d67-317">Values</span></span> | <span data-ttu-id="30d67-318">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="30d67-318">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="30d67-319">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="30d67-319">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimitPercent` | <span data-ttu-id="30d67-320">*Десятичное значение*</span><span class="sxs-lookup"><span data-stu-id="30d67-320">*decimal value*</span></span> | <span data-ttu-id="30d67-321">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="30d67-321">.NET Core 3.0</span></span> |
| <span data-ttu-id="30d67-322">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="30d67-322">**Environment variable**</span></span> | `COMPlus_GCHeapHardLimitPercent` | <span data-ttu-id="30d67-323">*Шестнадцатеричное значение*</span><span class="sxs-lookup"><span data-stu-id="30d67-323">*hexadecimal value*</span></span> | <span data-ttu-id="30d67-324">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="30d67-324">.NET Core 3.0</span></span> |

<span data-ttu-id="30d67-325">Пример.</span><span class="sxs-lookup"><span data-stu-id="30d67-325">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.HeapHardLimitPercent": 30
      }
   }
}
```

> [!TIP]
> <span data-ttu-id="30d67-326">Если вы задаете параметр в *runtimeconfig.json*, укажите десятичное значение.</span><span class="sxs-lookup"><span data-stu-id="30d67-326">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="30d67-327">Если вы задаете параметр в виде переменной среды, укажите шестнадцатеричное значение.</span><span class="sxs-lookup"><span data-stu-id="30d67-327">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="30d67-328">Например, чтобы ограничить использование кучи значением 30 %, для JSON-файла нужно указать 30, а для переменной среды — 0x1E или 1E.</span><span class="sxs-lookup"><span data-stu-id="30d67-328">For example, to limit the heap usage to 30%, the values would be 30 for the JSON file and 0x1E or 1E for the environment variable.</span></span>

### <a name="systemgcretainvmcomplus_gcretainvm"></a><span data-ttu-id="30d67-329">System.GC.RetainVM/COMPlus_GCRetainVM</span><span class="sxs-lookup"><span data-stu-id="30d67-329">System.GC.RetainVM/COMPlus_GCRetainVM</span></span>

- <span data-ttu-id="30d67-330">Настраивает, будут ли удаляемые сегменты помещаться в список ожидания для будущего использования или возвращаться операционной системе (ОС).</span><span class="sxs-lookup"><span data-stu-id="30d67-330">Configures whether segments that should be deleted are put on a standby list for future use or are released back to the operating system (OS).</span></span>
- <span data-ttu-id="30d67-331">По умолчанию: возвращение сегментов операционной системе (`false`).</span><span class="sxs-lookup"><span data-stu-id="30d67-331">Default: Release segments back to the operating system (`false`).</span></span>

| | <span data-ttu-id="30d67-332">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="30d67-332">Setting name</span></span> | <span data-ttu-id="30d67-333">Значения</span><span class="sxs-lookup"><span data-stu-id="30d67-333">Values</span></span> | <span data-ttu-id="30d67-334">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="30d67-334">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="30d67-335">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="30d67-335">**runtimeconfig.json**</span></span> | `System.GC.RetainVM` | <span data-ttu-id="30d67-336">`false` — возвращение операционной системе</span><span class="sxs-lookup"><span data-stu-id="30d67-336">`false` - release to OS</span></span><br/><span data-ttu-id="30d67-337">`true` — помещение в режим ожидания</span><span class="sxs-lookup"><span data-stu-id="30d67-337">`true` - put on standby</span></span> | <span data-ttu-id="30d67-338">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="30d67-338">.NET Core 1.0</span></span> |
| <span data-ttu-id="30d67-339">**Свойство MSBuild**</span><span class="sxs-lookup"><span data-stu-id="30d67-339">**MSBuild property**</span></span> | `RetainVMGarbageCollection` | <span data-ttu-id="30d67-340">`false` — возвращение операционной системе</span><span class="sxs-lookup"><span data-stu-id="30d67-340">`false` - release to OS</span></span><br/><span data-ttu-id="30d67-341">`true` — помещение в режим ожидания</span><span class="sxs-lookup"><span data-stu-id="30d67-341">`true` - put on standby</span></span> | <span data-ttu-id="30d67-342">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="30d67-342">.NET Core 1.0</span></span> |
| <span data-ttu-id="30d67-343">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="30d67-343">**Environment variable**</span></span> | `COMPlus_GCRetainVM` | <span data-ttu-id="30d67-344">`0` — возвращение операционной системе</span><span class="sxs-lookup"><span data-stu-id="30d67-344">`0` - release to OS</span></span><br/><span data-ttu-id="30d67-345">`1` — помещение в режим ожидания</span><span class="sxs-lookup"><span data-stu-id="30d67-345">`1` - put on standby</span></span> | <span data-ttu-id="30d67-346">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="30d67-346">.NET Core 1.0</span></span> |

### <a name="examples"></a><span data-ttu-id="30d67-347">Примеры</span><span class="sxs-lookup"><span data-stu-id="30d67-347">Examples</span></span>

<span data-ttu-id="30d67-348">Файл *runtimeconfig.json*</span><span class="sxs-lookup"><span data-stu-id="30d67-348">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.RetainVM": true
      }
   }
}
```

<span data-ttu-id="30d67-349">Файл проекта:</span><span class="sxs-lookup"><span data-stu-id="30d67-349">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <RetainVMGarbageCollection>true</RetainVMGarbageCollection>
  </PropertyGroup>

</Project>
```

## <a name="large-pages"></a><span data-ttu-id="30d67-350">Большие страницы</span><span class="sxs-lookup"><span data-stu-id="30d67-350">Large pages</span></span>

### <a name="complus_gclargepages"></a><span data-ttu-id="30d67-351">COMPlus_GCLargePages</span><span class="sxs-lookup"><span data-stu-id="30d67-351">COMPlus_GCLargePages</span></span>

- <span data-ttu-id="30d67-352">Указывает, следует ли использовать большие страницы, когда задано жесткое ограничение куч.</span><span class="sxs-lookup"><span data-stu-id="30d67-352">Specifies whether large pages should be used when a heap hard limit is set.</span></span>
- <span data-ttu-id="30d67-353">По умолчанию: отключено (`0`).</span><span class="sxs-lookup"><span data-stu-id="30d67-353">Default: Disabled (`0`).</span></span>
- <span data-ttu-id="30d67-354">Это экспериментальный параметр.</span><span class="sxs-lookup"><span data-stu-id="30d67-354">This is an experimental setting.</span></span>

| | <span data-ttu-id="30d67-355">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="30d67-355">Setting name</span></span> | <span data-ttu-id="30d67-356">Значения</span><span class="sxs-lookup"><span data-stu-id="30d67-356">Values</span></span> | <span data-ttu-id="30d67-357">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="30d67-357">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="30d67-358">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="30d67-358">**runtimeconfig.json**</span></span> | <span data-ttu-id="30d67-359">Н/Д</span><span class="sxs-lookup"><span data-stu-id="30d67-359">N/A</span></span> | <span data-ttu-id="30d67-360">Н/Д</span><span class="sxs-lookup"><span data-stu-id="30d67-360">N/A</span></span> | <span data-ttu-id="30d67-361">Н/Д</span><span class="sxs-lookup"><span data-stu-id="30d67-361">N/A</span></span> |
| <span data-ttu-id="30d67-362">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="30d67-362">**Environment variable**</span></span> | `COMPlus_GCLargePages` | <span data-ttu-id="30d67-363">`0` — отключено</span><span class="sxs-lookup"><span data-stu-id="30d67-363">`0` - disabled</span></span><br/><span data-ttu-id="30d67-364">`1` — включено</span><span class="sxs-lookup"><span data-stu-id="30d67-364">`1` - enabled</span></span> | <span data-ttu-id="30d67-365">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="30d67-365">.NET Core 3.0</span></span> |

## <a name="large-objects"></a><span data-ttu-id="30d67-366">Большие объекты</span><span class="sxs-lookup"><span data-stu-id="30d67-366">Large objects</span></span>

### <a name="complus_gcallowverylargeobjects"></a><span data-ttu-id="30d67-367">COMPlus_gcAllowVeryLargeObjects</span><span class="sxs-lookup"><span data-stu-id="30d67-367">COMPlus_gcAllowVeryLargeObjects</span></span>

- <span data-ttu-id="30d67-368">Настраивает для сборщика мусора на 64-разрядных платформах поддержку массивов, размер которых превышает 2 гигабайта (ГБ).</span><span class="sxs-lookup"><span data-stu-id="30d67-368">Configures garbage collector support on 64-bit platforms for arrays that are greater than 2 gigabytes (GB) in total size.</span></span>
- <span data-ttu-id="30d67-369">По умолчанию: включено (`1`).</span><span class="sxs-lookup"><span data-stu-id="30d67-369">Default: Enabled (`1`).</span></span>
- <span data-ttu-id="30d67-370">В будущей версии .NET этот параметр может быть объявлен устаревшим.</span><span class="sxs-lookup"><span data-stu-id="30d67-370">This option may become obsolete in a future version of .NET.</span></span>

| | <span data-ttu-id="30d67-371">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="30d67-371">Setting name</span></span> | <span data-ttu-id="30d67-372">Значения</span><span class="sxs-lookup"><span data-stu-id="30d67-372">Values</span></span> | <span data-ttu-id="30d67-373">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="30d67-373">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="30d67-374">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="30d67-374">**runtimeconfig.json**</span></span> | <span data-ttu-id="30d67-375">Н/Д</span><span class="sxs-lookup"><span data-stu-id="30d67-375">N/A</span></span> | <span data-ttu-id="30d67-376">Н/Д</span><span class="sxs-lookup"><span data-stu-id="30d67-376">N/A</span></span> | <span data-ttu-id="30d67-377">Н/Д</span><span class="sxs-lookup"><span data-stu-id="30d67-377">N/A</span></span> |
| <span data-ttu-id="30d67-378">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="30d67-378">**Environment variable**</span></span> | `COMPlus_gcAllowVeryLargeObjects` | <span data-ttu-id="30d67-379">`1` — включено</span><span class="sxs-lookup"><span data-stu-id="30d67-379">`1` - enabled</span></span><br/> <span data-ttu-id="30d67-380">`0` — отключено</span><span class="sxs-lookup"><span data-stu-id="30d67-380">`0` - disabled</span></span> | <span data-ttu-id="30d67-381">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="30d67-381">.NET Core 1.0</span></span> |
| <span data-ttu-id="30d67-382">**app.config для .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="30d67-382">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="30d67-383">gcAllowVeryLargeObjects</span><span class="sxs-lookup"><span data-stu-id="30d67-383">gcAllowVeryLargeObjects</span></span>](../../framework/configure-apps/file-schema/runtime/gcallowverylargeobjects-element.md) | <span data-ttu-id="30d67-384">`1` — включено</span><span class="sxs-lookup"><span data-stu-id="30d67-384">`1` - enabled</span></span><br/> <span data-ttu-id="30d67-385">`0` — отключено</span><span class="sxs-lookup"><span data-stu-id="30d67-385">`0` - disabled</span></span> | <span data-ttu-id="30d67-386">.NET Framework 4,5</span><span class="sxs-lookup"><span data-stu-id="30d67-386">.NET Framework 4.5</span></span> |

## <a name="large-object-heap-threshold"></a><span data-ttu-id="30d67-387">Пороговое значение кучи больших объектов</span><span class="sxs-lookup"><span data-stu-id="30d67-387">Large object heap threshold</span></span>

### <a name="systemgclohthresholdcomplus_gclohthreshold"></a><span data-ttu-id="30d67-388">System.GC.LOHThreshold/COMPlus_GCLOHThreshold</span><span class="sxs-lookup"><span data-stu-id="30d67-388">System.GC.LOHThreshold/COMPlus_GCLOHThreshold</span></span>

- <span data-ttu-id="30d67-389">Указывает пороговый размер (в байтах), при котором объекты попадают в кучу больших объектов (LOH).</span><span class="sxs-lookup"><span data-stu-id="30d67-389">Specifies the threshold size, in bytes, that causes objects to go on the large object heap (LOH).</span></span>
- <span data-ttu-id="30d67-390">Пороговое значение по умолчанию — 85 000 байт.</span><span class="sxs-lookup"><span data-stu-id="30d67-390">The default threshold is 85,000 bytes.</span></span>
- <span data-ttu-id="30d67-391">Указанное значение должно быть больше порогового значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="30d67-391">The value you specify must be larger than the default threshold.</span></span>

| | <span data-ttu-id="30d67-392">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="30d67-392">Setting name</span></span> | <span data-ttu-id="30d67-393">Значения</span><span class="sxs-lookup"><span data-stu-id="30d67-393">Values</span></span> | <span data-ttu-id="30d67-394">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="30d67-394">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="30d67-395">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="30d67-395">**runtimeconfig.json**</span></span> | `System.GC.LOHThreshold` | <span data-ttu-id="30d67-396">*Десятичное значение*</span><span class="sxs-lookup"><span data-stu-id="30d67-396">*decimal value*</span></span> | <span data-ttu-id="30d67-397">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="30d67-397">.NET Core 1.0</span></span> |
| <span data-ttu-id="30d67-398">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="30d67-398">**Environment variable**</span></span> | `COMPlus_GCLOHThreshold` | <span data-ttu-id="30d67-399">*Шестнадцатеричное значение*</span><span class="sxs-lookup"><span data-stu-id="30d67-399">*hexadecimal value*</span></span> | <span data-ttu-id="30d67-400">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="30d67-400">.NET Core 1.0</span></span> |
| <span data-ttu-id="30d67-401">**app.config для .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="30d67-401">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="30d67-402">GCLOHThreshold</span><span class="sxs-lookup"><span data-stu-id="30d67-402">GCLOHThreshold</span></span>](../../framework/configure-apps/file-schema/runtime/gclohthreshold-element.md) | <span data-ttu-id="30d67-403">*Десятичное значение*</span><span class="sxs-lookup"><span data-stu-id="30d67-403">*decimal value*</span></span> | <span data-ttu-id="30d67-404">.NET Framework 4.8</span><span class="sxs-lookup"><span data-stu-id="30d67-404">.NET Framework 4.8</span></span> |

<span data-ttu-id="30d67-405">Пример.</span><span class="sxs-lookup"><span data-stu-id="30d67-405">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.LOHThreshold": 120000
      }
   }
}
```

> [!TIP]
> <span data-ttu-id="30d67-406">Если вы задаете параметр в *runtimeconfig.json*, укажите десятичное значение.</span><span class="sxs-lookup"><span data-stu-id="30d67-406">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="30d67-407">Если вы задаете параметр в виде переменной среды, укажите шестнадцатеричное значение.</span><span class="sxs-lookup"><span data-stu-id="30d67-407">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="30d67-408">Например, чтобы задать порог размера в 120 000 байт, для JSON-файла нужно указать значение 120000, а для переменной среды — значение 0x1D4C0 или 1D4C0.</span><span class="sxs-lookup"><span data-stu-id="30d67-408">For example, to set a threshold size of 120,000 bytes, the values would be 120000 for the JSON file and 0x1D4C0 or 1D4C0 for the environment variable.</span></span>

## <a name="standalone-gc"></a><span data-ttu-id="30d67-409">Автономный сборщик мусора</span><span class="sxs-lookup"><span data-stu-id="30d67-409">Standalone GC</span></span>

### <a name="complus_gcname"></a><span data-ttu-id="30d67-410">COMPlus_GCName</span><span class="sxs-lookup"><span data-stu-id="30d67-410">COMPlus_GCName</span></span>

- <span data-ttu-id="30d67-411">Указывает путь к библиотеке, содержащей сборщик мусора, который среда выполнения намеревается загрузить.</span><span class="sxs-lookup"><span data-stu-id="30d67-411">Specifies a path to the library containing the garbage collector that the runtime intends to load.</span></span>
- <span data-ttu-id="30d67-412">Дополнительные сведения см. в статье [Проектирования загрузчика автономного сборщика мусора](https://github.com/dotnet/runtime/blob/master/docs/design/features/standalone-gc-loading.md).</span><span class="sxs-lookup"><span data-stu-id="30d67-412">For more information, see [Standalone GC loader design](https://github.com/dotnet/runtime/blob/master/docs/design/features/standalone-gc-loading.md).</span></span>

| | <span data-ttu-id="30d67-413">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="30d67-413">Setting name</span></span> | <span data-ttu-id="30d67-414">Значения</span><span class="sxs-lookup"><span data-stu-id="30d67-414">Values</span></span> | <span data-ttu-id="30d67-415">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="30d67-415">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="30d67-416">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="30d67-416">**runtimeconfig.json**</span></span> | <span data-ttu-id="30d67-417">Н/Д</span><span class="sxs-lookup"><span data-stu-id="30d67-417">N/A</span></span> | <span data-ttu-id="30d67-418">Н/Д</span><span class="sxs-lookup"><span data-stu-id="30d67-418">N/A</span></span> | <span data-ttu-id="30d67-419">Н/Д</span><span class="sxs-lookup"><span data-stu-id="30d67-419">N/A</span></span> |
| <span data-ttu-id="30d67-420">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="30d67-420">**Environment variable**</span></span> | `COMPlus_GCName` | <span data-ttu-id="30d67-421">*string_path*</span><span class="sxs-lookup"><span data-stu-id="30d67-421">*string_path*</span></span> | <span data-ttu-id="30d67-422">.NET Core 2.0;</span><span class="sxs-lookup"><span data-stu-id="30d67-422">.NET Core 2.0</span></span> |
