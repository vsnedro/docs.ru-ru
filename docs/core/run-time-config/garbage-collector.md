---
title: Параметры конфигурации сборщика мусора
description: Сведения о параметрах времени выполнения, определяющих, как сборщик мусора управляет памятью для приложений .NET Core.
ms.date: 01/09/2020
ms.topic: reference
ms.openlocfilehash: d7e3d040cd634eeb020beff806c60f834cc02585
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/21/2020
ms.locfileid: "83761984"
---
# <a name="run-time-configuration-options-for-garbage-collection"></a><span data-ttu-id="59048-103">Параметры конфигурации времени выполнения для сборки мусора</span><span class="sxs-lookup"><span data-stu-id="59048-103">Run-time configuration options for garbage collection</span></span>

<span data-ttu-id="59048-104">Эта страница содержит сведения о параметрах сборщика мусора (GC), которые можно изменить во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="59048-104">This page contains information about garbage collector (GC) settings that can be changed at run time.</span></span> <span data-ttu-id="59048-105">Если вы пытаетесь добиться пиковой производительности запущенных приложений, рекомендуется использовать эти параметры.</span><span class="sxs-lookup"><span data-stu-id="59048-105">If you're trying to achieve peak performance of a running app, consider using these settings.</span></span> <span data-ttu-id="59048-106">Однако значения по умолчанию обеспечивают оптимальную производительность для большинства приложений в типичных ситуациях.</span><span class="sxs-lookup"><span data-stu-id="59048-106">However, the defaults provide optimum performance for most applications in typical situations.</span></span>

<span data-ttu-id="59048-107">На этой странице параметры упорядочены по группам.</span><span class="sxs-lookup"><span data-stu-id="59048-107">Settings are arranged into groups on this page.</span></span> <span data-ttu-id="59048-108">Параметры в каждой группе обычно используются совместно друг с другом для достижения определенного результата.</span><span class="sxs-lookup"><span data-stu-id="59048-108">The settings within each group are commonly used in conjunction with each other to achieve a specific result.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="59048-109">Эти параметры также могут динамически изменяться приложением во время его выполнения, поэтому любые заданные параметры времени выполнения могут быть переопределены.</span><span class="sxs-lookup"><span data-stu-id="59048-109">These settings can also be changed dynamically by the app as it's running, so any run-time settings you set may be overridden.</span></span>
> - <span data-ttu-id="59048-110">Некоторые параметры, такие как [уровень задержки](../../standard/garbage-collection/latency.md), обычно задаются только через API во время разработки.</span><span class="sxs-lookup"><span data-stu-id="59048-110">Some settings, such as [latency level](../../standard/garbage-collection/latency.md), are typically set only through the API at design time.</span></span> <span data-ttu-id="59048-111">Такие параметры будут пропущены на этой странице.</span><span class="sxs-lookup"><span data-stu-id="59048-111">Such settings are omitted from this page.</span></span>
> - <span data-ttu-id="59048-112">Для числовых значений используйте десятичную нотацию для параметров в файле *runtimeconfig.json* и шестнадцатеричную нотацию для параметров переменных среды.</span><span class="sxs-lookup"><span data-stu-id="59048-112">For number values, use decimal notation for settings in the *runtimeconfig.json* file and hexadecimal notation for environment variable settings.</span></span> <span data-ttu-id="59048-113">Шестнадцатеричные значения можно указать с помощью префикса "0x" или без него.</span><span class="sxs-lookup"><span data-stu-id="59048-113">For hexadecimal values, you can specify them with or without the "0x" prefix.</span></span>

## <a name="flavors-of-garbage-collection"></a><span data-ttu-id="59048-114">Варианты сборки мусора</span><span class="sxs-lookup"><span data-stu-id="59048-114">Flavors of garbage collection</span></span>

<span data-ttu-id="59048-115">Два основных варианта сборки мусора — это сборка мусора рабочей станции и сборка мусора сервера.</span><span class="sxs-lookup"><span data-stu-id="59048-115">The two main flavors of garbage collection are workstation GC and server GC.</span></span> <span data-ttu-id="59048-116">Дополнительные сведения о различиях между этими двумя вариантами см. в статье [Сборка мусора рабочей станции и сборка мусора сервера](../../standard/garbage-collection/workstation-server-gc.md).</span><span class="sxs-lookup"><span data-stu-id="59048-116">For more information about differences between the two, see [Workstation and server garbage collection](../../standard/garbage-collection/workstation-server-gc.md).</span></span>

<span data-ttu-id="59048-117">Подвиды сборки мусора представлены фоновым и непараллельным выполнением.</span><span class="sxs-lookup"><span data-stu-id="59048-117">The subflavors of garbage collection are background and non-concurrent.</span></span>

<span data-ttu-id="59048-118">Чтобы выбрать варианты сборки мусора, используйте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="59048-118">Use the following settings to select flavors of garbage collection:</span></span>

### <a name="systemgcservercomplus_gcserver"></a><span data-ttu-id="59048-119">System.GC.Server/COMPlus_gcServer</span><span class="sxs-lookup"><span data-stu-id="59048-119">System.GC.Server/COMPlus_gcServer</span></span>

- <span data-ttu-id="59048-120">Указывает, использует ли приложение сборку мусора рабочей станции или сборку мусора сервера.</span><span class="sxs-lookup"><span data-stu-id="59048-120">Configures whether the application uses workstation garbage collection or server garbage collection.</span></span>
- <span data-ttu-id="59048-121">По умолчанию: сборка мусора рабочей станции.</span><span class="sxs-lookup"><span data-stu-id="59048-121">Default: Workstation garbage collection.</span></span> <span data-ttu-id="59048-122">Это эквивалентно присвоению значения `false`.</span><span class="sxs-lookup"><span data-stu-id="59048-122">This is equivalent to setting the value to `false`.</span></span>

| | <span data-ttu-id="59048-123">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="59048-123">Setting name</span></span> | <span data-ttu-id="59048-124">Значения</span><span class="sxs-lookup"><span data-stu-id="59048-124">Values</span></span> | <span data-ttu-id="59048-125">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="59048-125">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="59048-126">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="59048-126">**runtimeconfig.json**</span></span> | `System.GC.Server` | <span data-ttu-id="59048-127">`false` — рабочая станция</span><span class="sxs-lookup"><span data-stu-id="59048-127">`false` - workstation</span></span><br/><span data-ttu-id="59048-128">`true` — сервер</span><span class="sxs-lookup"><span data-stu-id="59048-128">`true` - server</span></span> | <span data-ttu-id="59048-129">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="59048-129">.NET Core 1.0</span></span> |
| <span data-ttu-id="59048-130">**Свойство MSBuild**</span><span class="sxs-lookup"><span data-stu-id="59048-130">**MSBuild property**</span></span> | `ServerGarbageCollection` | <span data-ttu-id="59048-131">`false` — рабочая станция</span><span class="sxs-lookup"><span data-stu-id="59048-131">`false` - workstation</span></span><br/><span data-ttu-id="59048-132">`true` — сервер</span><span class="sxs-lookup"><span data-stu-id="59048-132">`true` - server</span></span> | <span data-ttu-id="59048-133">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="59048-133">.NET Core 1.0</span></span> |
| <span data-ttu-id="59048-134">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="59048-134">**Environment variable**</span></span> | `COMPlus_gcServer` | <span data-ttu-id="59048-135">`0` — рабочая станция</span><span class="sxs-lookup"><span data-stu-id="59048-135">`0` - workstation</span></span><br/><span data-ttu-id="59048-136">`1` — сервер</span><span class="sxs-lookup"><span data-stu-id="59048-136">`1` - server</span></span> | <span data-ttu-id="59048-137">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="59048-137">.NET Core 1.0</span></span> |
| <span data-ttu-id="59048-138">**app.config для .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="59048-138">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="59048-139">GCServer</span><span class="sxs-lookup"><span data-stu-id="59048-139">GCServer</span></span>](../../framework/configure-apps/file-schema/runtime/gcserver-element.md) | <span data-ttu-id="59048-140">`false` — рабочая станция</span><span class="sxs-lookup"><span data-stu-id="59048-140">`false` - workstation</span></span><br/><span data-ttu-id="59048-141">`true` — сервер</span><span class="sxs-lookup"><span data-stu-id="59048-141">`true` - server</span></span> |  |

### <a name="examples"></a><span data-ttu-id="59048-142">Примеры</span><span class="sxs-lookup"><span data-stu-id="59048-142">Examples</span></span>

<span data-ttu-id="59048-143">Файл *runtimeconfig.json*</span><span class="sxs-lookup"><span data-stu-id="59048-143">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Server": true
      }
   }
}
```

<span data-ttu-id="59048-144">Файл проекта:</span><span class="sxs-lookup"><span data-stu-id="59048-144">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ServerGarbageCollection>true</ServerGarbageCollection>
  </PropertyGroup>

</Project>
```

### <a name="systemgcconcurrentcomplus_gcconcurrent"></a><span data-ttu-id="59048-145">System.GC.Concurrent/COMPlus_gcConcurrent</span><span class="sxs-lookup"><span data-stu-id="59048-145">System.GC.Concurrent/COMPlus_gcConcurrent</span></span>

- <span data-ttu-id="59048-146">Указывает, включена ли фоновая (параллельная) сборка мусора.</span><span class="sxs-lookup"><span data-stu-id="59048-146">Configures whether background (concurrent) garbage collection is enabled.</span></span>
- <span data-ttu-id="59048-147">По умолчанию: фоновая сборка мусора.</span><span class="sxs-lookup"><span data-stu-id="59048-147">Default: Use background GC.</span></span> <span data-ttu-id="59048-148">Это эквивалентно присвоению значения `true`.</span><span class="sxs-lookup"><span data-stu-id="59048-148">This is equivalent to setting the value to `true`.</span></span>
- <span data-ttu-id="59048-149">Дополнительные сведения см. в статье [Фоновая сборка мусора](../../standard/garbage-collection/background-gc.md).</span><span class="sxs-lookup"><span data-stu-id="59048-149">For more information, see [Background garbage collection](../../standard/garbage-collection/background-gc.md).</span></span>

| | <span data-ttu-id="59048-150">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="59048-150">Setting name</span></span> | <span data-ttu-id="59048-151">Значения</span><span class="sxs-lookup"><span data-stu-id="59048-151">Values</span></span> | <span data-ttu-id="59048-152">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="59048-152">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="59048-153">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="59048-153">**runtimeconfig.json**</span></span> | `System.GC.Concurrent` | <span data-ttu-id="59048-154">`true` —фоновая сборка мусора</span><span class="sxs-lookup"><span data-stu-id="59048-154">`true` - background GC</span></span><br/><span data-ttu-id="59048-155">`false` — непараллельная сборка мусора</span><span class="sxs-lookup"><span data-stu-id="59048-155">`false` - non-concurrent GC</span></span> | <span data-ttu-id="59048-156">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="59048-156">.NET Core 1.0</span></span> |
| <span data-ttu-id="59048-157">**Свойство MSBuild**</span><span class="sxs-lookup"><span data-stu-id="59048-157">**MSBuild property**</span></span> | `ConcurrentGarbageCollection` | <span data-ttu-id="59048-158">`true` —фоновая сборка мусора</span><span class="sxs-lookup"><span data-stu-id="59048-158">`true` - background GC</span></span><br/><span data-ttu-id="59048-159">`false` — непараллельная сборка мусора</span><span class="sxs-lookup"><span data-stu-id="59048-159">`false` - non-concurrent GC</span></span> | <span data-ttu-id="59048-160">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="59048-160">.NET Core 1.0</span></span> |
| <span data-ttu-id="59048-161">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="59048-161">**Environment variable**</span></span> | `COMPlus_gcConcurrent` | <span data-ttu-id="59048-162">`true` —фоновая сборка мусора</span><span class="sxs-lookup"><span data-stu-id="59048-162">`true` - background GC</span></span><br/><span data-ttu-id="59048-163">`false` — непараллельная сборка мусора</span><span class="sxs-lookup"><span data-stu-id="59048-163">`false` - non-concurrent GC</span></span> | <span data-ttu-id="59048-164">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="59048-164">.NET Core 1.0</span></span> |
| <span data-ttu-id="59048-165">**app.config для .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="59048-165">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="59048-166">gcConcurrent</span><span class="sxs-lookup"><span data-stu-id="59048-166">gcConcurrent</span></span>](../../framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) | <span data-ttu-id="59048-167">`true` —фоновая сборка мусора</span><span class="sxs-lookup"><span data-stu-id="59048-167">`true` - background GC</span></span><br/><span data-ttu-id="59048-168">`false` — непараллельная сборка мусора</span><span class="sxs-lookup"><span data-stu-id="59048-168">`false` - non-concurrent GC</span></span> |  |

### <a name="examples"></a><span data-ttu-id="59048-169">Примеры</span><span class="sxs-lookup"><span data-stu-id="59048-169">Examples</span></span>

<span data-ttu-id="59048-170">Файл *runtimeconfig.json*</span><span class="sxs-lookup"><span data-stu-id="59048-170">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Concurrent": false
      }
   }
}
```

<span data-ttu-id="59048-171">Файл проекта:</span><span class="sxs-lookup"><span data-stu-id="59048-171">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ConcurrentGarbageCollection>false</ConcurrentGarbageCollection>
  </PropertyGroup>

</Project>
```

## <a name="manage-resource-usage"></a><span data-ttu-id="59048-172">Управление использованием ресурсов</span><span class="sxs-lookup"><span data-stu-id="59048-172">Manage resource usage</span></span>

<span data-ttu-id="59048-173">Используйте параметры, описанные в этом разделе, для управления использованием памяти и ЦП в сборщике мусора.</span><span class="sxs-lookup"><span data-stu-id="59048-173">Use the settings described in this section to manage the garbage collector's memory and processor usage.</span></span>

<span data-ttu-id="59048-174">Дополнительные сведения о некоторых из этих параметров см. в записи блога о [компромиссе между сборкой мусора рабочей станции и сервера](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/).</span><span class="sxs-lookup"><span data-stu-id="59048-174">For more information about some of these settings, see the [Middle ground between workstation and server GC](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/) blog entry.</span></span>

### <a name="systemgcheapcountcomplus_gcheapcount"></a><span data-ttu-id="59048-175">System.GC.HeapCount/COMPlus_GCHeapCount</span><span class="sxs-lookup"><span data-stu-id="59048-175">System.GC.HeapCount/COMPlus_GCHeapCount</span></span>

- <span data-ttu-id="59048-176">Ограничивает число куч, создаваемых сборщиком мусора.</span><span class="sxs-lookup"><span data-stu-id="59048-176">Limits the number of heaps created by the garbage collector.</span></span>
- <span data-ttu-id="59048-177">Применяется только к сборке мусора сервера.</span><span class="sxs-lookup"><span data-stu-id="59048-177">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="59048-178">Если включено [сходство процессоров сборки мусора](#systemgcnoaffinitizecomplus_gcnoaffinitize), что используется по умолчанию, параметр счетчика куч реализует сходство `n` куч/потоков сборки мусора с первыми `n` процессорами.</span><span class="sxs-lookup"><span data-stu-id="59048-178">If [GC processor affinity](#systemgcnoaffinitizecomplus_gcnoaffinitize) is enabled, which is the default, the heap count setting affinitizes `n` GC heaps/threads to the first `n` processors.</span></span> <span data-ttu-id="59048-179">(Используйте параметры [сходства маски](#systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask) или [сходства диапазонов](#systemgcgcheapaffinitizerangescomplus_gcheapaffinitizeranges), чтобы указать, для каких именно процессоров следует реализовать сходство.)</span><span class="sxs-lookup"><span data-stu-id="59048-179">(Use the [affinitize mask](#systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask) or [affinitize ranges](#systemgcgcheapaffinitizerangescomplus_gcheapaffinitizeranges) settings to specify exactly which processors to affinitize.)</span></span>
- <span data-ttu-id="59048-180">Если [сходство процессоров сборки мусора](#systemgcnoaffinitizecomplus_gcnoaffinitize) отключено, этот параметр будет ограничивать количество куч сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="59048-180">If [GC processor affinity](#systemgcnoaffinitizecomplus_gcnoaffinitize) is disabled, this setting limits the number of GC heaps.</span></span>
- <span data-ttu-id="59048-181">Дополнительные сведения см. в [примечаниях по GCHeapCount](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md#remarks).</span><span class="sxs-lookup"><span data-stu-id="59048-181">For more information, see the [GCHeapCount remarks](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md#remarks).</span></span>

| | <span data-ttu-id="59048-182">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="59048-182">Setting name</span></span> | <span data-ttu-id="59048-183">Значения</span><span class="sxs-lookup"><span data-stu-id="59048-183">Values</span></span> | <span data-ttu-id="59048-184">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="59048-184">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="59048-185">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="59048-185">**runtimeconfig.json**</span></span> | `System.GC.HeapCount` | <span data-ttu-id="59048-186">*Десятичное значение*</span><span class="sxs-lookup"><span data-stu-id="59048-186">*decimal value*</span></span> | <span data-ttu-id="59048-187">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="59048-187">.NET Core 3.0</span></span> |
| <span data-ttu-id="59048-188">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="59048-188">**Environment variable**</span></span> | `COMPlus_GCHeapCount` | <span data-ttu-id="59048-189">*Шестнадцатеричное значение*</span><span class="sxs-lookup"><span data-stu-id="59048-189">*hexadecimal value*</span></span> | <span data-ttu-id="59048-190">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="59048-190">.NET Core 3.0</span></span> |
| <span data-ttu-id="59048-191">**app.config для .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="59048-191">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="59048-192">GCHeapCount</span><span class="sxs-lookup"><span data-stu-id="59048-192">GCHeapCount</span></span>](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md) | <span data-ttu-id="59048-193">*Десятичное значение*</span><span class="sxs-lookup"><span data-stu-id="59048-193">*decimal value*</span></span> | <span data-ttu-id="59048-194">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="59048-194">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="59048-195">Пример.</span><span class="sxs-lookup"><span data-stu-id="59048-195">Example:</span></span>

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
> <span data-ttu-id="59048-196">Если вы задаете параметр в *runtimeconfig.json*, укажите десятичное значение.</span><span class="sxs-lookup"><span data-stu-id="59048-196">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="59048-197">Если вы задаете параметр в виде переменной среды, укажите шестнадцатеричное значение.</span><span class="sxs-lookup"><span data-stu-id="59048-197">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="59048-198">Например, чтобы ограничить число куч значением 16, для JSON-файла нужно указать 16, а для переменной среды — 0x10 или 10.</span><span class="sxs-lookup"><span data-stu-id="59048-198">For example, to limit the number of heaps to 16, the values would be 16 for the JSON file and 0x10 or 10 for the environment variable.</span></span>

### <a name="systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask"></a><span data-ttu-id="59048-199">System.GC.HeapAffinitizeMask/COMPlus_GCHeapAffinitizeMask</span><span class="sxs-lookup"><span data-stu-id="59048-199">System.GC.HeapAffinitizeMask/COMPlus_GCHeapAffinitizeMask</span></span>

- <span data-ttu-id="59048-200">Указывает конкретные процессоры, которые должны использоваться потоками сборщика мусора.</span><span class="sxs-lookup"><span data-stu-id="59048-200">Specifies the exact processors that garbage collector threads should use.</span></span>
- <span data-ttu-id="59048-201">Если [сходство процессоров](#systemgcnoaffinitizecomplus_gcnoaffinitize) отключено, этот параметр игнорируется.</span><span class="sxs-lookup"><span data-stu-id="59048-201">If [GC processor affinity](#systemgcnoaffinitizecomplus_gcnoaffinitize) is disabled, this setting is ignored.</span></span>
- <span data-ttu-id="59048-202">Применяется только к сборке мусора сервера.</span><span class="sxs-lookup"><span data-stu-id="59048-202">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="59048-203">Это значение представляет собой битовую маску, которая определяет доступные процессу процессоры.</span><span class="sxs-lookup"><span data-stu-id="59048-203">The value is a bit mask that defines the processors that are available to the process.</span></span> <span data-ttu-id="59048-204">Например, десятичное значение 1023 (или шестнадцатеричное значение 0x3FF или 3FF, если вы используете переменную среды), равно 0011 1111 1111 в двоичной нотации.</span><span class="sxs-lookup"><span data-stu-id="59048-204">For example, a decimal value of 1023 (or a hexadecimal value of 0x3FF or 3FF if you're using the environment variable) is 0011 1111 1111 in binary notation.</span></span> <span data-ttu-id="59048-205">При этом будут использоваться первые 10 процессоров.</span><span class="sxs-lookup"><span data-stu-id="59048-205">This specifies that the first 10 processors are to be used.</span></span> <span data-ttu-id="59048-206">Чтобы указать следующие 10 процессоров, то есть процессоры 10–19, задайте десятичное значение 1047552 (или шестнадцатеричное значение 0xFFC00 или FFC00), которое эквивалентно двоичному значению 1111 1111 1100 0000 0000.</span><span class="sxs-lookup"><span data-stu-id="59048-206">To specify the next 10 processors, that is, processors 10-19, specify a decimal value of 1047552 (or a hexadecimal value of 0xFFC00 or FFC00), which is equivalent to a binary value of 1111 1111 1100 0000 0000.</span></span>

| | <span data-ttu-id="59048-207">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="59048-207">Setting name</span></span> | <span data-ttu-id="59048-208">Значения</span><span class="sxs-lookup"><span data-stu-id="59048-208">Values</span></span> | <span data-ttu-id="59048-209">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="59048-209">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="59048-210">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="59048-210">**runtimeconfig.json**</span></span> | `System.GC.HeapAffinitizeMask` | <span data-ttu-id="59048-211">*Десятичное значение*</span><span class="sxs-lookup"><span data-stu-id="59048-211">*decimal value*</span></span> | <span data-ttu-id="59048-212">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="59048-212">.NET Core 3.0</span></span> |
| <span data-ttu-id="59048-213">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="59048-213">**Environment variable**</span></span> | `COMPlus_GCHeapAffinitizeMask` | <span data-ttu-id="59048-214">*Шестнадцатеричное значение*</span><span class="sxs-lookup"><span data-stu-id="59048-214">*hexadecimal value*</span></span> | <span data-ttu-id="59048-215">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="59048-215">.NET Core 3.0</span></span> |
| <span data-ttu-id="59048-216">**app.config для .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="59048-216">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="59048-217">GCHeapAffinitizeMask</span><span class="sxs-lookup"><span data-stu-id="59048-217">GCHeapAffinitizeMask</span></span>](../../framework/configure-apps/file-schema/runtime/gcheapaffinitizemask-element.md) | <span data-ttu-id="59048-218">*Десятичное значение*</span><span class="sxs-lookup"><span data-stu-id="59048-218">*decimal value*</span></span> | <span data-ttu-id="59048-219">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="59048-219">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="59048-220">Пример.</span><span class="sxs-lookup"><span data-stu-id="59048-220">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.HeapAffinitizeMask": 1023
      }
   }
}
```

### <a name="systemgcgcheapaffinitizerangescomplus_gcheapaffinitizeranges"></a><span data-ttu-id="59048-221">System.GC.GCHeapAffinitizeRanges/COMPlus_GCHeapAffinitizeRanges</span><span class="sxs-lookup"><span data-stu-id="59048-221">System.GC.GCHeapAffinitizeRanges/COMPlus_GCHeapAffinitizeRanges</span></span>

- <span data-ttu-id="59048-222">Указывает список процессоров, используемых для потоков сборщика мусора.</span><span class="sxs-lookup"><span data-stu-id="59048-222">Specifies the list of processors to use for garbage collector threads.</span></span>
- <span data-ttu-id="59048-223">Этот параметр аналогичен [System.GC.HeapAffinitizeMask](#systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask), за исключением того, что он позволяет указать больше 64 процессоров.</span><span class="sxs-lookup"><span data-stu-id="59048-223">This setting is similar to [System.GC.HeapAffinitizeMask](#systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask), except it allows you to specify more than 64 processors.</span></span>
- <span data-ttu-id="59048-224">Для операционных систем Windows добавьте к номеру или диапазону процессоров префикс в виде соответствующей [группы ЦП](/windows/win32/procthread/processor-groups), например "0:1-10,0:12,1:50-52,1:70".</span><span class="sxs-lookup"><span data-stu-id="59048-224">For Windows operating systems, prefix the processor number or range with the corresponding [CPU group](/windows/win32/procthread/processor-groups), for example, "0:1-10,0:12,1:50-52,1:70".</span></span>
- <span data-ttu-id="59048-225">Если [сходство процессоров](#systemgcnoaffinitizecomplus_gcnoaffinitize) отключено, этот параметр игнорируется.</span><span class="sxs-lookup"><span data-stu-id="59048-225">If [GC processor affinity](#systemgcnoaffinitizecomplus_gcnoaffinitize) is disabled, this setting is ignored.</span></span>
- <span data-ttu-id="59048-226">Применяется только к сборке мусора сервера.</span><span class="sxs-lookup"><span data-stu-id="59048-226">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="59048-227">Дополнительные сведения см. в записи об [улучшении конфигурации ЦП для сборки мусора на компьютерах, имеющих более 64 ЦП](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/), в блоге Майони Стивенс (Maoni Stephens).</span><span class="sxs-lookup"><span data-stu-id="59048-227">For more information, see [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) on Maoni Stephens' blog.</span></span>

| | <span data-ttu-id="59048-228">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="59048-228">Setting name</span></span> | <span data-ttu-id="59048-229">Значения</span><span class="sxs-lookup"><span data-stu-id="59048-229">Values</span></span> | <span data-ttu-id="59048-230">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="59048-230">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="59048-231">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="59048-231">**runtimeconfig.json**</span></span> | `System.GC.GCHeapAffinitizeRanges` | <span data-ttu-id="59048-232">Разделенный запятыми список номеров процессоров или диапазонов номеров процессоров.</span><span class="sxs-lookup"><span data-stu-id="59048-232">Comma-separated list of processor numbers or ranges of processor numbers.</span></span><br/><span data-ttu-id="59048-233">Пример для Unix: "1-10,12,50-52,70"</span><span class="sxs-lookup"><span data-stu-id="59048-233">Unix example: "1-10,12,50-52,70"</span></span><br/><span data-ttu-id="59048-234">Пример для Windows: "0:1-10,0:12,1:50-52,1:70"</span><span class="sxs-lookup"><span data-stu-id="59048-234">Windows example: "0:1-10,0:12,1:50-52,1:70"</span></span> | <span data-ttu-id="59048-235">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="59048-235">.NET Core 3.0</span></span> |
| <span data-ttu-id="59048-236">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="59048-236">**Environment variable**</span></span> | `COMPlus_GCHeapAffinitizeRanges` | <span data-ttu-id="59048-237">Разделенный запятыми список номеров процессоров или диапазонов номеров процессоров.</span><span class="sxs-lookup"><span data-stu-id="59048-237">Comma-separated list of processor numbers or ranges of processor numbers.</span></span><br/><span data-ttu-id="59048-238">Пример для Unix: "1-10,12,50-52,70"</span><span class="sxs-lookup"><span data-stu-id="59048-238">Unix example: "1-10,12,50-52,70"</span></span><br/><span data-ttu-id="59048-239">Пример для Windows: "0:1-10,0:12,1:50-52,1:70"</span><span class="sxs-lookup"><span data-stu-id="59048-239">Windows example: "0:1-10,0:12,1:50-52,1:70"</span></span> | <span data-ttu-id="59048-240">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="59048-240">.NET Core 3.0</span></span> |

<span data-ttu-id="59048-241">Пример.</span><span class="sxs-lookup"><span data-stu-id="59048-241">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.GCHeapAffinitizeRanges": "0:1-10,0:12,1:50-52,1:70"
      }
   }
}
```

### <a name="complus_gccpugroup"></a><span data-ttu-id="59048-242">COMPlus_GCCpuGroup</span><span class="sxs-lookup"><span data-stu-id="59048-242">COMPlus_GCCpuGroup</span></span>

- <span data-ttu-id="59048-243">Указывает, использует ли сборщик мусора [группы ЦП](/windows/win32/procthread/processor-groups).</span><span class="sxs-lookup"><span data-stu-id="59048-243">Configures whether the garbage collector uses [CPU groups](/windows/win32/procthread/processor-groups) or not.</span></span>

  <span data-ttu-id="59048-244">Когда 64-разрядный компьютер с Windows имеет несколько групп ЦП, то есть доступно более 64 процессоров, включение этого элемента расширяет действие сборки мусора на все группы ЦП.</span><span class="sxs-lookup"><span data-stu-id="59048-244">When a 64-bit Windows computer has multiple CPU groups, that is, there are more than 64 processors, enabling this element extends garbage collection across all CPU groups.</span></span> <span data-ttu-id="59048-245">Сборщик мусора использует все ядра для создания и балансировки куч.</span><span class="sxs-lookup"><span data-stu-id="59048-245">The garbage collector uses all cores to create and balance heaps.</span></span>

- <span data-ttu-id="59048-246">Применяется только к сборке мусора сервера в 64-разрядных операционных системах Windows.</span><span class="sxs-lookup"><span data-stu-id="59048-246">Applies to server garbage collection on 64-bit Windows operation systems only.</span></span>
- <span data-ttu-id="59048-247">По умолчанию: сборка мусора не распространяется на группы ЦП.</span><span class="sxs-lookup"><span data-stu-id="59048-247">Default: GC does not extend across CPU groups.</span></span> <span data-ttu-id="59048-248">Это эквивалентно присвоению значения `0`.</span><span class="sxs-lookup"><span data-stu-id="59048-248">This is equivalent to setting the value to `0`.</span></span>
- <span data-ttu-id="59048-249">Дополнительные сведения см. в записи об [улучшении конфигурации ЦП для сборки мусора на компьютерах, имеющих более 64 ЦП](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/), в блоге Майони Стивенс (Maoni Stephens).</span><span class="sxs-lookup"><span data-stu-id="59048-249">For more information, see [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) on Maoni Stephens' blog.</span></span>

| | <span data-ttu-id="59048-250">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="59048-250">Setting name</span></span> | <span data-ttu-id="59048-251">Значения</span><span class="sxs-lookup"><span data-stu-id="59048-251">Values</span></span> | <span data-ttu-id="59048-252">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="59048-252">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="59048-253">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="59048-253">**runtimeconfig.json**</span></span> | <span data-ttu-id="59048-254">Н/Д</span><span class="sxs-lookup"><span data-stu-id="59048-254">N/A</span></span> | <span data-ttu-id="59048-255">Н/Д</span><span class="sxs-lookup"><span data-stu-id="59048-255">N/A</span></span> | <span data-ttu-id="59048-256">Н/Д</span><span class="sxs-lookup"><span data-stu-id="59048-256">N/A</span></span> |
| <span data-ttu-id="59048-257">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="59048-257">**Environment variable**</span></span> | `COMPlus_GCCpuGroup` | <span data-ttu-id="59048-258">`0` — отключено</span><span class="sxs-lookup"><span data-stu-id="59048-258">`0` - disabled</span></span><br/><span data-ttu-id="59048-259">`1` — включено</span><span class="sxs-lookup"><span data-stu-id="59048-259">`1` - enabled</span></span> | <span data-ttu-id="59048-260">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="59048-260">.NET Core 1.0</span></span> |
| <span data-ttu-id="59048-261">**app.config для .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="59048-261">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="59048-262">GCCpuGroup</span><span class="sxs-lookup"><span data-stu-id="59048-262">GCCpuGroup</span></span>](../../framework/configure-apps/file-schema/runtime/gccpugroup-element.md) | <span data-ttu-id="59048-263">`false` — отключено</span><span class="sxs-lookup"><span data-stu-id="59048-263">`false` - disabled</span></span><br/><span data-ttu-id="59048-264">`true` — включено</span><span class="sxs-lookup"><span data-stu-id="59048-264">`true` - enabled</span></span> |  |

> [!NOTE]
> <span data-ttu-id="59048-265">Чтобы настроить среду CLR для распределения потоков из пула потоков по всем группам ЦП, включите параметр [Элемент Thread_UseAllCpuGroups](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md).</span><span class="sxs-lookup"><span data-stu-id="59048-265">To configure the common language runtime (CLR) to also distribute threads from the thread pool across all CPU groups, enable the [Thread_UseAllCpuGroups element](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md) option.</span></span> <span data-ttu-id="59048-266">Для приложений .NET Core этот параметр можно включить, задав для переменной среды `COMPlus_Thread_UseAllCpuGroups` значение `1`.</span><span class="sxs-lookup"><span data-stu-id="59048-266">For .NET Core apps, you can enable this option by setting the value of the `COMPlus_Thread_UseAllCpuGroups` environment variable to `1`.</span></span>

### <a name="systemgcnoaffinitizecomplus_gcnoaffinitize"></a><span data-ttu-id="59048-267">System.GC.NoAffinitize/COMPlus_GCNoAffinitize</span><span class="sxs-lookup"><span data-stu-id="59048-267">System.GC.NoAffinitize/COMPlus_GCNoAffinitize</span></span>

- <span data-ttu-id="59048-268">Указывает, следует ли *реализовать сходство* потоков сборки мусора с процессорами.</span><span class="sxs-lookup"><span data-stu-id="59048-268">Specifies whether to *affinitize* garbage collection threads with processors.</span></span> <span data-ttu-id="59048-269">Реализация сходства потока сборки мусора означает, что он может выполняться только на определенном ЦП.</span><span class="sxs-lookup"><span data-stu-id="59048-269">To affinitize a GC thread means that it can only run on its specific CPU.</span></span> <span data-ttu-id="59048-270">Куча создается для каждого потока сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="59048-270">A heap is created for each GC thread.</span></span>
- <span data-ttu-id="59048-271">Применяется только к сборке мусора сервера.</span><span class="sxs-lookup"><span data-stu-id="59048-271">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="59048-272">По умолчанию: реализация сходства потоков сборки мусора с процессорами.</span><span class="sxs-lookup"><span data-stu-id="59048-272">Default: Affinitize garbage collection threads with processors.</span></span> <span data-ttu-id="59048-273">Это эквивалентно присвоению значения `false`.</span><span class="sxs-lookup"><span data-stu-id="59048-273">This is equivalent to setting the value to `false`.</span></span>

| | <span data-ttu-id="59048-274">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="59048-274">Setting name</span></span> | <span data-ttu-id="59048-275">Значения</span><span class="sxs-lookup"><span data-stu-id="59048-275">Values</span></span> | <span data-ttu-id="59048-276">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="59048-276">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="59048-277">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="59048-277">**runtimeconfig.json**</span></span> | `System.GC.NoAffinitize` | <span data-ttu-id="59048-278">`false` — реализовать сходство</span><span class="sxs-lookup"><span data-stu-id="59048-278">`false` - affinitize</span></span><br/><span data-ttu-id="59048-279">`true` — не реализовывать сходство</span><span class="sxs-lookup"><span data-stu-id="59048-279">`true` - don't affinitize</span></span> | <span data-ttu-id="59048-280">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="59048-280">.NET Core 3.0</span></span> |
| <span data-ttu-id="59048-281">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="59048-281">**Environment variable**</span></span> | `COMPlus_GCNoAffinitize` | <span data-ttu-id="59048-282">`0` — реализовать сходство</span><span class="sxs-lookup"><span data-stu-id="59048-282">`0` - affinitize</span></span><br/><span data-ttu-id="59048-283">`1` — не реализовывать сходство</span><span class="sxs-lookup"><span data-stu-id="59048-283">`1` - don't affinitize</span></span> | <span data-ttu-id="59048-284">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="59048-284">.NET Core 3.0</span></span> |
| <span data-ttu-id="59048-285">**app.config для .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="59048-285">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="59048-286">GCNoAffinitize</span><span class="sxs-lookup"><span data-stu-id="59048-286">GCNoAffinitize</span></span>](../../framework/configure-apps/file-schema/runtime/gcnoaffinitize-element.md) | <span data-ttu-id="59048-287">`false` — реализовать сходство</span><span class="sxs-lookup"><span data-stu-id="59048-287">`false` - affinitize</span></span><br/><span data-ttu-id="59048-288">`true` — не реализовывать сходство</span><span class="sxs-lookup"><span data-stu-id="59048-288">`true` - don't affinitize</span></span> | <span data-ttu-id="59048-289">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="59048-289">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="59048-290">Пример.</span><span class="sxs-lookup"><span data-stu-id="59048-290">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.NoAffinitize": true
      }
   }
}
```

### <a name="systemgcheaphardlimitcomplus_gcheaphardlimit"></a><span data-ttu-id="59048-291">System.GC.HeapHardLimit/COMPlus_GCHeapHardLimit</span><span class="sxs-lookup"><span data-stu-id="59048-291">System.GC.HeapHardLimit/COMPlus_GCHeapHardLimit</span></span>

- <span data-ttu-id="59048-292">Указывает максимальный размер фиксации в байтах для кучи сборки мусора и учета сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="59048-292">Specifies the maximum commit size, in bytes, for the GC heap and GC bookkeeping.</span></span>
- <span data-ttu-id="59048-293">Этот параметр применим только к 64-разрядным компьютерам.</span><span class="sxs-lookup"><span data-stu-id="59048-293">This setting only applies to 64-bit computers.</span></span>
- <span data-ttu-id="59048-294">Значение по умолчанию, которое применяется только в определенных случаях, превышает 20 МБ или 75 % предельного объема памяти в контейнере.</span><span class="sxs-lookup"><span data-stu-id="59048-294">The default value, which only applies in certain cases, is the greater of 20 MB or 75% of the memory limit on the container.</span></span> <span data-ttu-id="59048-295">Значение по умолчанию применяется, если:</span><span class="sxs-lookup"><span data-stu-id="59048-295">The default value applies if:</span></span>

  - <span data-ttu-id="59048-296">процесс выполняется в контейнере с заданным предельным объемом памяти;</span><span class="sxs-lookup"><span data-stu-id="59048-296">The process is running inside a container that has a specified memory limit.</span></span>
  - <span data-ttu-id="59048-297">параметр [System.GC.HeapHardLimitPercent](#systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent) не задан.</span><span class="sxs-lookup"><span data-stu-id="59048-297">[System.GC.HeapHardLimitPercent](#systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent) is not set.</span></span>

| | <span data-ttu-id="59048-298">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="59048-298">Setting name</span></span> | <span data-ttu-id="59048-299">Значения</span><span class="sxs-lookup"><span data-stu-id="59048-299">Values</span></span> | <span data-ttu-id="59048-300">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="59048-300">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="59048-301">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="59048-301">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimit` | <span data-ttu-id="59048-302">*Десятичное значение*</span><span class="sxs-lookup"><span data-stu-id="59048-302">*decimal value*</span></span> | <span data-ttu-id="59048-303">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="59048-303">.NET Core 3.0</span></span> |
| <span data-ttu-id="59048-304">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="59048-304">**Environment variable**</span></span> | `COMPlus_GCHeapHardLimit` | <span data-ttu-id="59048-305">*Шестнадцатеричное значение*</span><span class="sxs-lookup"><span data-stu-id="59048-305">*hexadecimal value*</span></span> | <span data-ttu-id="59048-306">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="59048-306">.NET Core 3.0</span></span> |

<span data-ttu-id="59048-307">Пример.</span><span class="sxs-lookup"><span data-stu-id="59048-307">Example:</span></span>

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
> <span data-ttu-id="59048-308">Если вы задаете параметр в *runtimeconfig.json*, укажите десятичное значение.</span><span class="sxs-lookup"><span data-stu-id="59048-308">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="59048-309">Если вы задаете параметр в виде переменной среды, укажите шестнадцатеричное значение.</span><span class="sxs-lookup"><span data-stu-id="59048-309">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="59048-310">Например, чтобы задать для куч жесткое ограничение в 200 мебибайт (Миб), для JSON-файла нужно указать значение 209715200, а для переменной среды — значение 0xC800000 или C800000.</span><span class="sxs-lookup"><span data-stu-id="59048-310">For example, to specify a heap hard limit of 200 mebibytes (MiB), the values would be 209715200 for the JSON file and 0xC800000 or C800000 for the environment variable.</span></span>

### <a name="systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent"></a><span data-ttu-id="59048-311">System.GC.HeapHardLimitPercent/COMPlus_GCHeapHardLimitPercent</span><span class="sxs-lookup"><span data-stu-id="59048-311">System.GC.HeapHardLimitPercent/COMPlus_GCHeapHardLimitPercent</span></span>

- <span data-ttu-id="59048-312">Указывает допустимое использование кучи сборки мусора в процентах от общего объема физической памяти.</span><span class="sxs-lookup"><span data-stu-id="59048-312">Specifies the allowable GC heap usage as a percentage of the total physical memory.</span></span>
- <span data-ttu-id="59048-313">Если также задан параметр [System.GC.HeapHardLimit](#systemgcheaphardlimitcomplus_gcheaphardlimit), этот параметр игнорируется.</span><span class="sxs-lookup"><span data-stu-id="59048-313">If [System.GC.HeapHardLimit](#systemgcheaphardlimitcomplus_gcheaphardlimit) is also set, this setting is ignored.</span></span>
- <span data-ttu-id="59048-314">Этот параметр применим только к 64-разрядным компьютерам.</span><span class="sxs-lookup"><span data-stu-id="59048-314">This setting only applies to 64-bit computers.</span></span>
- <span data-ttu-id="59048-315">Если процесс выполняется в контейнере с заданным предельным объемом памяти, процентная доля вычисляется как процент от этого объема памяти.</span><span class="sxs-lookup"><span data-stu-id="59048-315">If the process is running inside a container that has a specified memory limit, the percentage is calculated as a percentage of that memory limit.</span></span>
- <span data-ttu-id="59048-316">Значение по умолчанию, которое применяется только в определенных случаях, не превышает 20 МБ или 75 % предельного объема памяти в контейнере.</span><span class="sxs-lookup"><span data-stu-id="59048-316">The default value, which only applies in certain cases, is the lesser of 20 MB or 75% of the memory limit on the container.</span></span> <span data-ttu-id="59048-317">Значение по умолчанию применяется, если:</span><span class="sxs-lookup"><span data-stu-id="59048-317">The default value applies if:</span></span>

  - <span data-ttu-id="59048-318">процесс выполняется в контейнере с заданным предельным объемом памяти;</span><span class="sxs-lookup"><span data-stu-id="59048-318">The process is running inside a container that has a specified memory limit.</span></span>
  - <span data-ttu-id="59048-319">параметр [System.GC.HeapHardLimit](#systemgcheaphardlimitcomplus_gcheaphardlimit) не задан.</span><span class="sxs-lookup"><span data-stu-id="59048-319">[System.GC.HeapHardLimit](#systemgcheaphardlimitcomplus_gcheaphardlimit) is not set.</span></span>

| | <span data-ttu-id="59048-320">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="59048-320">Setting name</span></span> | <span data-ttu-id="59048-321">Значения</span><span class="sxs-lookup"><span data-stu-id="59048-321">Values</span></span> | <span data-ttu-id="59048-322">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="59048-322">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="59048-323">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="59048-323">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimitPercent` | <span data-ttu-id="59048-324">*Десятичное значение*</span><span class="sxs-lookup"><span data-stu-id="59048-324">*decimal value*</span></span> | <span data-ttu-id="59048-325">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="59048-325">.NET Core 3.0</span></span> |
| <span data-ttu-id="59048-326">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="59048-326">**Environment variable**</span></span> | `COMPlus_GCHeapHardLimitPercent` | <span data-ttu-id="59048-327">*Шестнадцатеричное значение*</span><span class="sxs-lookup"><span data-stu-id="59048-327">*hexadecimal value*</span></span> | <span data-ttu-id="59048-328">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="59048-328">.NET Core 3.0</span></span> |

<span data-ttu-id="59048-329">Пример.</span><span class="sxs-lookup"><span data-stu-id="59048-329">Example:</span></span>

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
> <span data-ttu-id="59048-330">Если вы задаете параметр в *runtimeconfig.json*, укажите десятичное значение.</span><span class="sxs-lookup"><span data-stu-id="59048-330">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="59048-331">Если вы задаете параметр в виде переменной среды, укажите шестнадцатеричное значение.</span><span class="sxs-lookup"><span data-stu-id="59048-331">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="59048-332">Например, чтобы ограничить использование кучи значением 30 %, для JSON-файла нужно указать 30, а для переменной среды — 0x1E или 1E.</span><span class="sxs-lookup"><span data-stu-id="59048-332">For example, to limit the heap usage to 30%, the values would be 30 for the JSON file and 0x1E or 1E for the environment variable.</span></span>

### <a name="systemgcretainvmcomplus_gcretainvm"></a><span data-ttu-id="59048-333">System.GC.RetainVM/COMPlus_GCRetainVM</span><span class="sxs-lookup"><span data-stu-id="59048-333">System.GC.RetainVM/COMPlus_GCRetainVM</span></span>

- <span data-ttu-id="59048-334">Настраивает, будут ли удаляемые сегменты помещаться в список ожидания для будущего использования или возвращаться операционной системе (ОС).</span><span class="sxs-lookup"><span data-stu-id="59048-334">Configures whether segments that should be deleted are put on a standby list for future use or are released back to the operating system (OS).</span></span>
- <span data-ttu-id="59048-335">По умолчанию: возвращение сегментов операционной системе.</span><span class="sxs-lookup"><span data-stu-id="59048-335">Default: Release segments back to the operating system.</span></span> <span data-ttu-id="59048-336">Это эквивалентно присвоению значения `false`.</span><span class="sxs-lookup"><span data-stu-id="59048-336">This is equivalent to setting the value to `false`.</span></span>

| | <span data-ttu-id="59048-337">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="59048-337">Setting name</span></span> | <span data-ttu-id="59048-338">Значения</span><span class="sxs-lookup"><span data-stu-id="59048-338">Values</span></span> | <span data-ttu-id="59048-339">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="59048-339">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="59048-340">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="59048-340">**runtimeconfig.json**</span></span> | `System.GC.RetainVM` | <span data-ttu-id="59048-341">`false` — возвращение операционной системе</span><span class="sxs-lookup"><span data-stu-id="59048-341">`false` - release to OS</span></span><br/><span data-ttu-id="59048-342">`true` — помещение в режим ожидания</span><span class="sxs-lookup"><span data-stu-id="59048-342">`true` - put on standby</span></span> | <span data-ttu-id="59048-343">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="59048-343">.NET Core 1.0</span></span> |
| <span data-ttu-id="59048-344">**Свойство MSBuild**</span><span class="sxs-lookup"><span data-stu-id="59048-344">**MSBuild property**</span></span> | `RetainVMGarbageCollection` | <span data-ttu-id="59048-345">`false` — возвращение операционной системе</span><span class="sxs-lookup"><span data-stu-id="59048-345">`false` - release to OS</span></span><br/><span data-ttu-id="59048-346">`true` — помещение в режим ожидания</span><span class="sxs-lookup"><span data-stu-id="59048-346">`true` - put on standby</span></span> | <span data-ttu-id="59048-347">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="59048-347">.NET Core 1.0</span></span> |
| <span data-ttu-id="59048-348">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="59048-348">**Environment variable**</span></span> | `COMPlus_GCRetainVM` | <span data-ttu-id="59048-349">`0` — возвращение операционной системе</span><span class="sxs-lookup"><span data-stu-id="59048-349">`0` - release to OS</span></span><br/><span data-ttu-id="59048-350">`1` — помещение в режим ожидания</span><span class="sxs-lookup"><span data-stu-id="59048-350">`1` - put on standby</span></span> | <span data-ttu-id="59048-351">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="59048-351">.NET Core 1.0</span></span> |

### <a name="examples"></a><span data-ttu-id="59048-352">Примеры</span><span class="sxs-lookup"><span data-stu-id="59048-352">Examples</span></span>

<span data-ttu-id="59048-353">Файл *runtimeconfig.json*</span><span class="sxs-lookup"><span data-stu-id="59048-353">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.RetainVM": true
      }
   }
}
```

<span data-ttu-id="59048-354">Файл проекта:</span><span class="sxs-lookup"><span data-stu-id="59048-354">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <RetainVMGarbageCollection>true</RetainVMGarbageCollection>
  </PropertyGroup>

</Project>
```

## <a name="large-pages"></a><span data-ttu-id="59048-355">Большие страницы</span><span class="sxs-lookup"><span data-stu-id="59048-355">Large pages</span></span>

### <a name="complus_gclargepages"></a><span data-ttu-id="59048-356">COMPlus_GCLargePages</span><span class="sxs-lookup"><span data-stu-id="59048-356">COMPlus_GCLargePages</span></span>

- <span data-ttu-id="59048-357">Указывает, следует ли использовать большие страницы, когда задано жесткое ограничение куч.</span><span class="sxs-lookup"><span data-stu-id="59048-357">Specifies whether large pages should be used when a heap hard limit is set.</span></span>
- <span data-ttu-id="59048-358">По умолчанию: не следует использовать большие страницы, если задан фиксированный предел кучи.</span><span class="sxs-lookup"><span data-stu-id="59048-358">Default: Don't use large pages when a heap hard limit is set.</span></span> <span data-ttu-id="59048-359">Это эквивалентно присвоению значения `0`.</span><span class="sxs-lookup"><span data-stu-id="59048-359">This is equivalent to setting the value to `0`.</span></span>
- <span data-ttu-id="59048-360">Это экспериментальный параметр.</span><span class="sxs-lookup"><span data-stu-id="59048-360">This is an experimental setting.</span></span>

| | <span data-ttu-id="59048-361">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="59048-361">Setting name</span></span> | <span data-ttu-id="59048-362">Значения</span><span class="sxs-lookup"><span data-stu-id="59048-362">Values</span></span> | <span data-ttu-id="59048-363">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="59048-363">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="59048-364">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="59048-364">**runtimeconfig.json**</span></span> | <span data-ttu-id="59048-365">Н/Д</span><span class="sxs-lookup"><span data-stu-id="59048-365">N/A</span></span> | <span data-ttu-id="59048-366">Н/Д</span><span class="sxs-lookup"><span data-stu-id="59048-366">N/A</span></span> | <span data-ttu-id="59048-367">Н/Д</span><span class="sxs-lookup"><span data-stu-id="59048-367">N/A</span></span> |
| <span data-ttu-id="59048-368">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="59048-368">**Environment variable**</span></span> | `COMPlus_GCLargePages` | <span data-ttu-id="59048-369">`0` — отключено</span><span class="sxs-lookup"><span data-stu-id="59048-369">`0` - disabled</span></span><br/><span data-ttu-id="59048-370">`1` — включено</span><span class="sxs-lookup"><span data-stu-id="59048-370">`1` - enabled</span></span> | <span data-ttu-id="59048-371">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="59048-371">.NET Core 3.0</span></span> |

## <a name="large-objects"></a><span data-ttu-id="59048-372">Большие объекты</span><span class="sxs-lookup"><span data-stu-id="59048-372">Large objects</span></span>

### <a name="complus_gcallowverylargeobjects"></a><span data-ttu-id="59048-373">COMPlus_gcAllowVeryLargeObjects</span><span class="sxs-lookup"><span data-stu-id="59048-373">COMPlus_gcAllowVeryLargeObjects</span></span>

- <span data-ttu-id="59048-374">Настраивает для сборщика мусора на 64-разрядных платформах поддержку массивов, размер которых превышает 2 гигабайта (ГБ).</span><span class="sxs-lookup"><span data-stu-id="59048-374">Configures garbage collector support on 64-bit platforms for arrays that are greater than 2 gigabytes (GB) in total size.</span></span>
- <span data-ttu-id="59048-375">По умолчанию: сборка мусора поддерживает массивы размером более 2 ГБ.</span><span class="sxs-lookup"><span data-stu-id="59048-375">Default: GC supports arrays greater than 2-GB.</span></span> <span data-ttu-id="59048-376">Это эквивалентно присвоению значения `1`.</span><span class="sxs-lookup"><span data-stu-id="59048-376">This is equivalent to setting the value to `1`.</span></span>
- <span data-ttu-id="59048-377">В будущей версии .NET этот параметр может быть объявлен устаревшим.</span><span class="sxs-lookup"><span data-stu-id="59048-377">This option may become obsolete in a future version of .NET.</span></span>

| | <span data-ttu-id="59048-378">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="59048-378">Setting name</span></span> | <span data-ttu-id="59048-379">Значения</span><span class="sxs-lookup"><span data-stu-id="59048-379">Values</span></span> | <span data-ttu-id="59048-380">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="59048-380">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="59048-381">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="59048-381">**runtimeconfig.json**</span></span> | <span data-ttu-id="59048-382">Н/Д</span><span class="sxs-lookup"><span data-stu-id="59048-382">N/A</span></span> | <span data-ttu-id="59048-383">Н/Д</span><span class="sxs-lookup"><span data-stu-id="59048-383">N/A</span></span> | <span data-ttu-id="59048-384">Н/Д</span><span class="sxs-lookup"><span data-stu-id="59048-384">N/A</span></span> |
| <span data-ttu-id="59048-385">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="59048-385">**Environment variable**</span></span> | `COMPlus_gcAllowVeryLargeObjects` | <span data-ttu-id="59048-386">`1` — включено</span><span class="sxs-lookup"><span data-stu-id="59048-386">`1` - enabled</span></span><br/> <span data-ttu-id="59048-387">`0` — отключено</span><span class="sxs-lookup"><span data-stu-id="59048-387">`0` - disabled</span></span> | <span data-ttu-id="59048-388">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="59048-388">.NET Core 1.0</span></span> |
| <span data-ttu-id="59048-389">**app.config для .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="59048-389">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="59048-390">gcAllowVeryLargeObjects</span><span class="sxs-lookup"><span data-stu-id="59048-390">gcAllowVeryLargeObjects</span></span>](../../framework/configure-apps/file-schema/runtime/gcallowverylargeobjects-element.md) | <span data-ttu-id="59048-391">`1` — включено</span><span class="sxs-lookup"><span data-stu-id="59048-391">`1` - enabled</span></span><br/> <span data-ttu-id="59048-392">`0` — отключено</span><span class="sxs-lookup"><span data-stu-id="59048-392">`0` - disabled</span></span> | <span data-ttu-id="59048-393">.NET Framework 4,5</span><span class="sxs-lookup"><span data-stu-id="59048-393">.NET Framework 4.5</span></span> |

## <a name="large-object-heap-threshold"></a><span data-ttu-id="59048-394">Пороговое значение кучи больших объектов</span><span class="sxs-lookup"><span data-stu-id="59048-394">Large object heap threshold</span></span>

### <a name="systemgclohthresholdcomplus_gclohthreshold"></a><span data-ttu-id="59048-395">System.GC.LOHThreshold/COMPlus_GCLOHThreshold</span><span class="sxs-lookup"><span data-stu-id="59048-395">System.GC.LOHThreshold/COMPlus_GCLOHThreshold</span></span>

- <span data-ttu-id="59048-396">Указывает пороговый размер (в байтах), при котором объекты попадают в кучу больших объектов (LOH).</span><span class="sxs-lookup"><span data-stu-id="59048-396">Specifies the threshold size, in bytes, that causes objects to go on the large object heap (LOH).</span></span>
- <span data-ttu-id="59048-397">Пороговое значение по умолчанию — 85 000 байт.</span><span class="sxs-lookup"><span data-stu-id="59048-397">The default threshold is 85,000 bytes.</span></span>
- <span data-ttu-id="59048-398">Указанное значение должно быть больше порогового значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="59048-398">The value you specify must be larger than the default threshold.</span></span>

| | <span data-ttu-id="59048-399">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="59048-399">Setting name</span></span> | <span data-ttu-id="59048-400">Значения</span><span class="sxs-lookup"><span data-stu-id="59048-400">Values</span></span> | <span data-ttu-id="59048-401">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="59048-401">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="59048-402">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="59048-402">**runtimeconfig.json**</span></span> | `System.GC.LOHThreshold` | <span data-ttu-id="59048-403">*Десятичное значение*</span><span class="sxs-lookup"><span data-stu-id="59048-403">*decimal value*</span></span> | <span data-ttu-id="59048-404">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="59048-404">.NET Core 1.0</span></span> |
| <span data-ttu-id="59048-405">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="59048-405">**Environment variable**</span></span> | `COMPlus_GCLOHThreshold` | <span data-ttu-id="59048-406">*Шестнадцатеричное значение*</span><span class="sxs-lookup"><span data-stu-id="59048-406">*hexadecimal value*</span></span> | <span data-ttu-id="59048-407">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="59048-407">.NET Core 1.0</span></span> |
| <span data-ttu-id="59048-408">**app.config для .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="59048-408">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="59048-409">GCLOHThreshold</span><span class="sxs-lookup"><span data-stu-id="59048-409">GCLOHThreshold</span></span>](../../framework/configure-apps/file-schema/runtime/gclohthreshold-element.md) | <span data-ttu-id="59048-410">*Десятичное значение*</span><span class="sxs-lookup"><span data-stu-id="59048-410">*decimal value*</span></span> | <span data-ttu-id="59048-411">.NET Framework 4.8</span><span class="sxs-lookup"><span data-stu-id="59048-411">.NET Framework 4.8</span></span> |

<span data-ttu-id="59048-412">Пример.</span><span class="sxs-lookup"><span data-stu-id="59048-412">Example:</span></span>

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
> <span data-ttu-id="59048-413">Если вы задаете параметр в *runtimeconfig.json*, укажите десятичное значение.</span><span class="sxs-lookup"><span data-stu-id="59048-413">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="59048-414">Если вы задаете параметр в виде переменной среды, укажите шестнадцатеричное значение.</span><span class="sxs-lookup"><span data-stu-id="59048-414">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="59048-415">Например, чтобы задать порог размера в 120 000 байт, для JSON-файла нужно указать значение 120000, а для переменной среды — значение 0x1D4C0 или 1D4C0.</span><span class="sxs-lookup"><span data-stu-id="59048-415">For example, to set a threshold size of 120,000 bytes, the values would be 120000 for the JSON file and 0x1D4C0 or 1D4C0 for the environment variable.</span></span>

## <a name="standalone-gc"></a><span data-ttu-id="59048-416">Автономный сборщик мусора</span><span class="sxs-lookup"><span data-stu-id="59048-416">Standalone GC</span></span>

### <a name="complus_gcname"></a><span data-ttu-id="59048-417">COMPlus_GCName</span><span class="sxs-lookup"><span data-stu-id="59048-417">COMPlus_GCName</span></span>

- <span data-ttu-id="59048-418">Указывает путь к библиотеке, содержащей сборщик мусора, который среда выполнения намеревается загрузить.</span><span class="sxs-lookup"><span data-stu-id="59048-418">Specifies a path to the library containing the garbage collector that the runtime intends to load.</span></span>
- <span data-ttu-id="59048-419">Дополнительные сведения см. в статье [Проектирования загрузчика автономного сборщика мусора](https://github.com/dotnet/runtime/blob/master/docs/design/features/standalone-gc-loading.md).</span><span class="sxs-lookup"><span data-stu-id="59048-419">For more information, see [Standalone GC loader design](https://github.com/dotnet/runtime/blob/master/docs/design/features/standalone-gc-loading.md).</span></span>

| | <span data-ttu-id="59048-420">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="59048-420">Setting name</span></span> | <span data-ttu-id="59048-421">Значения</span><span class="sxs-lookup"><span data-stu-id="59048-421">Values</span></span> | <span data-ttu-id="59048-422">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="59048-422">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="59048-423">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="59048-423">**runtimeconfig.json**</span></span> | <span data-ttu-id="59048-424">Н/Д</span><span class="sxs-lookup"><span data-stu-id="59048-424">N/A</span></span> | <span data-ttu-id="59048-425">Н/Д</span><span class="sxs-lookup"><span data-stu-id="59048-425">N/A</span></span> | <span data-ttu-id="59048-426">Н/Д</span><span class="sxs-lookup"><span data-stu-id="59048-426">N/A</span></span> |
| <span data-ttu-id="59048-427">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="59048-427">**Environment variable**</span></span> | `COMPlus_GCName` | <span data-ttu-id="59048-428">*string_path*</span><span class="sxs-lookup"><span data-stu-id="59048-428">*string_path*</span></span> | <span data-ttu-id="59048-429">.NET Core 2.0;</span><span class="sxs-lookup"><span data-stu-id="59048-429">.NET Core 2.0</span></span> |
