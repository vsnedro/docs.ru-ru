---
title: Параметры конфигурации сборщика мусора
description: Сведения о параметрах времени выполнения, определяющих, как сборщик мусора управляет памятью для приложений .NET Core.
ms.date: 01/09/2020
ms.topic: reference
ms.openlocfilehash: 0ce2f70204463c1525ef7d29de21ddf5384d0238
ms.sourcegitcommit: 71b8f5a2108a0f1a4ef1d8d75c5b3e129ec5ca1e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/29/2020
ms.locfileid: "84202098"
---
# <a name="run-time-configuration-options-for-garbage-collection"></a><span data-ttu-id="66dec-103">Параметры конфигурации времени выполнения для сборки мусора</span><span class="sxs-lookup"><span data-stu-id="66dec-103">Run-time configuration options for garbage collection</span></span>

<span data-ttu-id="66dec-104">Эта страница содержит сведения о параметрах сборщика мусора (GC), которые можно изменить во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="66dec-104">This page contains information about garbage collector (GC) settings that can be changed at run time.</span></span> <span data-ttu-id="66dec-105">Если вы пытаетесь добиться пиковой производительности запущенных приложений, рекомендуется использовать эти параметры.</span><span class="sxs-lookup"><span data-stu-id="66dec-105">If you're trying to achieve peak performance of a running app, consider using these settings.</span></span> <span data-ttu-id="66dec-106">Однако значения по умолчанию обеспечивают оптимальную производительность для большинства приложений в типичных ситуациях.</span><span class="sxs-lookup"><span data-stu-id="66dec-106">However, the defaults provide optimum performance for most applications in typical situations.</span></span>

<span data-ttu-id="66dec-107">На этой странице параметры упорядочены по группам.</span><span class="sxs-lookup"><span data-stu-id="66dec-107">Settings are arranged into groups on this page.</span></span> <span data-ttu-id="66dec-108">Параметры в каждой группе обычно используются совместно друг с другом для достижения определенного результата.</span><span class="sxs-lookup"><span data-stu-id="66dec-108">The settings within each group are commonly used in conjunction with each other to achieve a specific result.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="66dec-109">Эти параметры также могут динамически изменяться приложением во время его выполнения, поэтому любые заданные параметры времени выполнения могут быть переопределены.</span><span class="sxs-lookup"><span data-stu-id="66dec-109">These settings can also be changed dynamically by the app as it's running, so any run-time settings you set may be overridden.</span></span>
> - <span data-ttu-id="66dec-110">Некоторые параметры, такие как [уровень задержки](../../standard/garbage-collection/latency.md), обычно задаются только через API во время разработки.</span><span class="sxs-lookup"><span data-stu-id="66dec-110">Some settings, such as [latency level](../../standard/garbage-collection/latency.md), are typically set only through the API at design time.</span></span> <span data-ttu-id="66dec-111">Такие параметры будут пропущены на этой странице.</span><span class="sxs-lookup"><span data-stu-id="66dec-111">Such settings are omitted from this page.</span></span>
> - <span data-ttu-id="66dec-112">Для числовых значений используйте десятичную нотацию для параметров в файле *runtimeconfig.json* и шестнадцатеричную нотацию для параметров переменных среды.</span><span class="sxs-lookup"><span data-stu-id="66dec-112">For number values, use decimal notation for settings in the *runtimeconfig.json* file and hexadecimal notation for environment variable settings.</span></span> <span data-ttu-id="66dec-113">Шестнадцатеричные значения можно указать с помощью префикса "0x" или без него.</span><span class="sxs-lookup"><span data-stu-id="66dec-113">For hexadecimal values, you can specify them with or without the "0x" prefix.</span></span>

## <a name="flavors-of-garbage-collection"></a><span data-ttu-id="66dec-114">Варианты сборки мусора</span><span class="sxs-lookup"><span data-stu-id="66dec-114">Flavors of garbage collection</span></span>

<span data-ttu-id="66dec-115">Два основных варианта сборки мусора — это сборка мусора рабочей станции и сборка мусора сервера.</span><span class="sxs-lookup"><span data-stu-id="66dec-115">The two main flavors of garbage collection are workstation GC and server GC.</span></span> <span data-ttu-id="66dec-116">Дополнительные сведения о различиях между этими двумя вариантами см. в статье [Сборка мусора рабочей станции и сборка мусора сервера](../../standard/garbage-collection/workstation-server-gc.md).</span><span class="sxs-lookup"><span data-stu-id="66dec-116">For more information about differences between the two, see [Workstation and server garbage collection](../../standard/garbage-collection/workstation-server-gc.md).</span></span>

<span data-ttu-id="66dec-117">Подвиды сборки мусора представлены фоновым и непараллельным выполнением.</span><span class="sxs-lookup"><span data-stu-id="66dec-117">The subflavors of garbage collection are background and non-concurrent.</span></span>

<span data-ttu-id="66dec-118">Чтобы выбрать варианты сборки мусора, используйте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="66dec-118">Use the following settings to select flavors of garbage collection:</span></span>

### <a name="systemgcservercomplus_gcserver"></a><span data-ttu-id="66dec-119">System.GC.Server/COMPlus_gcServer</span><span class="sxs-lookup"><span data-stu-id="66dec-119">System.GC.Server/COMPlus_gcServer</span></span>

- <span data-ttu-id="66dec-120">Указывает, использует ли приложение сборку мусора рабочей станции или сборку мусора сервера.</span><span class="sxs-lookup"><span data-stu-id="66dec-120">Configures whether the application uses workstation garbage collection or server garbage collection.</span></span>
- <span data-ttu-id="66dec-121">По умолчанию: сборка мусора рабочей станции.</span><span class="sxs-lookup"><span data-stu-id="66dec-121">Default: Workstation garbage collection.</span></span> <span data-ttu-id="66dec-122">Это эквивалентно присвоению значения `false`.</span><span class="sxs-lookup"><span data-stu-id="66dec-122">This is equivalent to setting the value to `false`.</span></span>

| | <span data-ttu-id="66dec-123">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="66dec-123">Setting name</span></span> | <span data-ttu-id="66dec-124">Значения</span><span class="sxs-lookup"><span data-stu-id="66dec-124">Values</span></span> | <span data-ttu-id="66dec-125">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="66dec-125">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="66dec-126">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="66dec-126">**runtimeconfig.json**</span></span> | `System.GC.Server` | <span data-ttu-id="66dec-127">`false` — рабочая станция</span><span class="sxs-lookup"><span data-stu-id="66dec-127">`false` - workstation</span></span><br/><span data-ttu-id="66dec-128">`true` — сервер</span><span class="sxs-lookup"><span data-stu-id="66dec-128">`true` - server</span></span> | <span data-ttu-id="66dec-129">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="66dec-129">.NET Core 1.0</span></span> |
| <span data-ttu-id="66dec-130">**Свойство MSBuild**</span><span class="sxs-lookup"><span data-stu-id="66dec-130">**MSBuild property**</span></span> | `ServerGarbageCollection` | <span data-ttu-id="66dec-131">`false` — рабочая станция</span><span class="sxs-lookup"><span data-stu-id="66dec-131">`false` - workstation</span></span><br/><span data-ttu-id="66dec-132">`true` — сервер</span><span class="sxs-lookup"><span data-stu-id="66dec-132">`true` - server</span></span> | <span data-ttu-id="66dec-133">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="66dec-133">.NET Core 1.0</span></span> |
| <span data-ttu-id="66dec-134">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="66dec-134">**Environment variable**</span></span> | `COMPlus_gcServer` | <span data-ttu-id="66dec-135">`0` — рабочая станция</span><span class="sxs-lookup"><span data-stu-id="66dec-135">`0` - workstation</span></span><br/><span data-ttu-id="66dec-136">`1` — сервер</span><span class="sxs-lookup"><span data-stu-id="66dec-136">`1` - server</span></span> | <span data-ttu-id="66dec-137">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="66dec-137">.NET Core 1.0</span></span> |
| <span data-ttu-id="66dec-138">**app.config для .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="66dec-138">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="66dec-139">GCServer</span><span class="sxs-lookup"><span data-stu-id="66dec-139">GCServer</span></span>](../../framework/configure-apps/file-schema/runtime/gcserver-element.md) | <span data-ttu-id="66dec-140">`false` — рабочая станция</span><span class="sxs-lookup"><span data-stu-id="66dec-140">`false` - workstation</span></span><br/><span data-ttu-id="66dec-141">`true` — сервер</span><span class="sxs-lookup"><span data-stu-id="66dec-141">`true` - server</span></span> |  |

### <a name="examples"></a><span data-ttu-id="66dec-142">Примеры</span><span class="sxs-lookup"><span data-stu-id="66dec-142">Examples</span></span>

<span data-ttu-id="66dec-143">Файл *runtimeconfig.json*</span><span class="sxs-lookup"><span data-stu-id="66dec-143">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Server": true
      }
   }
}
```

<span data-ttu-id="66dec-144">Файл проекта:</span><span class="sxs-lookup"><span data-stu-id="66dec-144">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ServerGarbageCollection>true</ServerGarbageCollection>
  </PropertyGroup>

</Project>
```

### <a name="systemgcconcurrentcomplus_gcconcurrent"></a><span data-ttu-id="66dec-145">System.GC.Concurrent/COMPlus_gcConcurrent</span><span class="sxs-lookup"><span data-stu-id="66dec-145">System.GC.Concurrent/COMPlus_gcConcurrent</span></span>

- <span data-ttu-id="66dec-146">Указывает, включена ли фоновая (параллельная) сборка мусора.</span><span class="sxs-lookup"><span data-stu-id="66dec-146">Configures whether background (concurrent) garbage collection is enabled.</span></span>
- <span data-ttu-id="66dec-147">По умолчанию: фоновая сборка мусора.</span><span class="sxs-lookup"><span data-stu-id="66dec-147">Default: Use background GC.</span></span> <span data-ttu-id="66dec-148">Это эквивалентно присвоению значения `true`.</span><span class="sxs-lookup"><span data-stu-id="66dec-148">This is equivalent to setting the value to `true`.</span></span>
- <span data-ttu-id="66dec-149">Дополнительные сведения см. в статье [Фоновая сборка мусора](../../standard/garbage-collection/background-gc.md).</span><span class="sxs-lookup"><span data-stu-id="66dec-149">For more information, see [Background garbage collection](../../standard/garbage-collection/background-gc.md).</span></span>

| | <span data-ttu-id="66dec-150">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="66dec-150">Setting name</span></span> | <span data-ttu-id="66dec-151">Значения</span><span class="sxs-lookup"><span data-stu-id="66dec-151">Values</span></span> | <span data-ttu-id="66dec-152">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="66dec-152">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="66dec-153">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="66dec-153">**runtimeconfig.json**</span></span> | `System.GC.Concurrent` | <span data-ttu-id="66dec-154">`true` —фоновая сборка мусора</span><span class="sxs-lookup"><span data-stu-id="66dec-154">`true` - background GC</span></span><br/><span data-ttu-id="66dec-155">`false` — непараллельная сборка мусора</span><span class="sxs-lookup"><span data-stu-id="66dec-155">`false` - non-concurrent GC</span></span> | <span data-ttu-id="66dec-156">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="66dec-156">.NET Core 1.0</span></span> |
| <span data-ttu-id="66dec-157">**Свойство MSBuild**</span><span class="sxs-lookup"><span data-stu-id="66dec-157">**MSBuild property**</span></span> | `ConcurrentGarbageCollection` | <span data-ttu-id="66dec-158">`true` —фоновая сборка мусора</span><span class="sxs-lookup"><span data-stu-id="66dec-158">`true` - background GC</span></span><br/><span data-ttu-id="66dec-159">`false` — непараллельная сборка мусора</span><span class="sxs-lookup"><span data-stu-id="66dec-159">`false` - non-concurrent GC</span></span> | <span data-ttu-id="66dec-160">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="66dec-160">.NET Core 1.0</span></span> |
| <span data-ttu-id="66dec-161">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="66dec-161">**Environment variable**</span></span> | `COMPlus_gcConcurrent` | <span data-ttu-id="66dec-162">`1` —фоновая сборка мусора</span><span class="sxs-lookup"><span data-stu-id="66dec-162">`1` - background GC</span></span><br/><span data-ttu-id="66dec-163">`0` — непараллельная сборка мусора</span><span class="sxs-lookup"><span data-stu-id="66dec-163">`0` - non-concurrent GC</span></span> | <span data-ttu-id="66dec-164">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="66dec-164">.NET Core 1.0</span></span> |
| <span data-ttu-id="66dec-165">**app.config для .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="66dec-165">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="66dec-166">gcConcurrent</span><span class="sxs-lookup"><span data-stu-id="66dec-166">gcConcurrent</span></span>](../../framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) | <span data-ttu-id="66dec-167">`true` —фоновая сборка мусора</span><span class="sxs-lookup"><span data-stu-id="66dec-167">`true` - background GC</span></span><br/><span data-ttu-id="66dec-168">`false` — непараллельная сборка мусора</span><span class="sxs-lookup"><span data-stu-id="66dec-168">`false` - non-concurrent GC</span></span> |  |

### <a name="examples"></a><span data-ttu-id="66dec-169">Примеры</span><span class="sxs-lookup"><span data-stu-id="66dec-169">Examples</span></span>

<span data-ttu-id="66dec-170">Файл *runtimeconfig.json*</span><span class="sxs-lookup"><span data-stu-id="66dec-170">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Concurrent": false
      }
   }
}
```

<span data-ttu-id="66dec-171">Файл проекта:</span><span class="sxs-lookup"><span data-stu-id="66dec-171">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ConcurrentGarbageCollection>false</ConcurrentGarbageCollection>
  </PropertyGroup>

</Project>
```

## <a name="manage-resource-usage"></a><span data-ttu-id="66dec-172">Управление использованием ресурсов</span><span class="sxs-lookup"><span data-stu-id="66dec-172">Manage resource usage</span></span>

<span data-ttu-id="66dec-173">Используйте параметры, описанные в этом разделе, для управления использованием памяти и ЦП в сборщике мусора.</span><span class="sxs-lookup"><span data-stu-id="66dec-173">Use the settings described in this section to manage the garbage collector's memory and processor usage.</span></span>

<span data-ttu-id="66dec-174">Дополнительные сведения о некоторых из этих параметров см. в записи блога о [компромиссе между сборкой мусора рабочей станции и сервера](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/).</span><span class="sxs-lookup"><span data-stu-id="66dec-174">For more information about some of these settings, see the [Middle ground between workstation and server GC](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/) blog entry.</span></span>

### <a name="systemgcheapcountcomplus_gcheapcount"></a><span data-ttu-id="66dec-175">System.GC.HeapCount/COMPlus_GCHeapCount</span><span class="sxs-lookup"><span data-stu-id="66dec-175">System.GC.HeapCount/COMPlus_GCHeapCount</span></span>

- <span data-ttu-id="66dec-176">Ограничивает число куч, создаваемых сборщиком мусора.</span><span class="sxs-lookup"><span data-stu-id="66dec-176">Limits the number of heaps created by the garbage collector.</span></span>
- <span data-ttu-id="66dec-177">Применяется только к сборке мусора сервера.</span><span class="sxs-lookup"><span data-stu-id="66dec-177">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="66dec-178">Если включено [сходство процессоров сборки мусора](#systemgcnoaffinitizecomplus_gcnoaffinitize), что используется по умолчанию, параметр счетчика куч реализует сходство `n` куч/потоков сборки мусора с первыми `n` процессорами.</span><span class="sxs-lookup"><span data-stu-id="66dec-178">If [GC processor affinity](#systemgcnoaffinitizecomplus_gcnoaffinitize) is enabled, which is the default, the heap count setting affinitizes `n` GC heaps/threads to the first `n` processors.</span></span> <span data-ttu-id="66dec-179">(Используйте параметры [сходства маски](#systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask) или [сходства диапазонов](#systemgcgcheapaffinitizerangescomplus_gcheapaffinitizeranges), чтобы указать, для каких именно процессоров следует реализовать сходство.)</span><span class="sxs-lookup"><span data-stu-id="66dec-179">(Use the [affinitize mask](#systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask) or [affinitize ranges](#systemgcgcheapaffinitizerangescomplus_gcheapaffinitizeranges) settings to specify exactly which processors to affinitize.)</span></span>
- <span data-ttu-id="66dec-180">Если [сходство процессоров сборки мусора](#systemgcnoaffinitizecomplus_gcnoaffinitize) отключено, этот параметр будет ограничивать количество куч сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="66dec-180">If [GC processor affinity](#systemgcnoaffinitizecomplus_gcnoaffinitize) is disabled, this setting limits the number of GC heaps.</span></span>
- <span data-ttu-id="66dec-181">Дополнительные сведения см. в [примечаниях по GCHeapCount](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md#remarks).</span><span class="sxs-lookup"><span data-stu-id="66dec-181">For more information, see the [GCHeapCount remarks](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md#remarks).</span></span>

| | <span data-ttu-id="66dec-182">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="66dec-182">Setting name</span></span> | <span data-ttu-id="66dec-183">Значения</span><span class="sxs-lookup"><span data-stu-id="66dec-183">Values</span></span> | <span data-ttu-id="66dec-184">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="66dec-184">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="66dec-185">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="66dec-185">**runtimeconfig.json**</span></span> | `System.GC.HeapCount` | <span data-ttu-id="66dec-186">*Десятичное значение*</span><span class="sxs-lookup"><span data-stu-id="66dec-186">*decimal value*</span></span> | <span data-ttu-id="66dec-187">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="66dec-187">.NET Core 3.0</span></span> |
| <span data-ttu-id="66dec-188">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="66dec-188">**Environment variable**</span></span> | `COMPlus_GCHeapCount` | <span data-ttu-id="66dec-189">*Шестнадцатеричное значение*</span><span class="sxs-lookup"><span data-stu-id="66dec-189">*hexadecimal value*</span></span> | <span data-ttu-id="66dec-190">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="66dec-190">.NET Core 3.0</span></span> |
| <span data-ttu-id="66dec-191">**app.config для .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="66dec-191">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="66dec-192">GCHeapCount</span><span class="sxs-lookup"><span data-stu-id="66dec-192">GCHeapCount</span></span>](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md) | <span data-ttu-id="66dec-193">*Десятичное значение*</span><span class="sxs-lookup"><span data-stu-id="66dec-193">*decimal value*</span></span> | <span data-ttu-id="66dec-194">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="66dec-194">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="66dec-195">Пример.</span><span class="sxs-lookup"><span data-stu-id="66dec-195">Example:</span></span>

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
> <span data-ttu-id="66dec-196">Если вы задаете параметр в *runtimeconfig.json*, укажите десятичное значение.</span><span class="sxs-lookup"><span data-stu-id="66dec-196">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="66dec-197">Если вы задаете параметр в виде переменной среды, укажите шестнадцатеричное значение.</span><span class="sxs-lookup"><span data-stu-id="66dec-197">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="66dec-198">Например, чтобы ограничить число куч значением 16, для JSON-файла нужно указать 16, а для переменной среды — 0x10 или 10.</span><span class="sxs-lookup"><span data-stu-id="66dec-198">For example, to limit the number of heaps to 16, the values would be 16 for the JSON file and 0x10 or 10 for the environment variable.</span></span>

### <a name="systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask"></a><span data-ttu-id="66dec-199">System.GC.HeapAffinitizeMask/COMPlus_GCHeapAffinitizeMask</span><span class="sxs-lookup"><span data-stu-id="66dec-199">System.GC.HeapAffinitizeMask/COMPlus_GCHeapAffinitizeMask</span></span>

- <span data-ttu-id="66dec-200">Указывает конкретные процессоры, которые должны использоваться потоками сборщика мусора.</span><span class="sxs-lookup"><span data-stu-id="66dec-200">Specifies the exact processors that garbage collector threads should use.</span></span>
- <span data-ttu-id="66dec-201">Если [сходство процессоров](#systemgcnoaffinitizecomplus_gcnoaffinitize) отключено, этот параметр игнорируется.</span><span class="sxs-lookup"><span data-stu-id="66dec-201">If [GC processor affinity](#systemgcnoaffinitizecomplus_gcnoaffinitize) is disabled, this setting is ignored.</span></span>
- <span data-ttu-id="66dec-202">Применяется только к сборке мусора сервера.</span><span class="sxs-lookup"><span data-stu-id="66dec-202">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="66dec-203">Это значение представляет собой битовую маску, которая определяет доступные процессу процессоры.</span><span class="sxs-lookup"><span data-stu-id="66dec-203">The value is a bit mask that defines the processors that are available to the process.</span></span> <span data-ttu-id="66dec-204">Например, десятичное значение 1023 (или шестнадцатеричное значение 0x3FF или 3FF, если вы используете переменную среды), равно 0011 1111 1111 в двоичной нотации.</span><span class="sxs-lookup"><span data-stu-id="66dec-204">For example, a decimal value of 1023 (or a hexadecimal value of 0x3FF or 3FF if you're using the environment variable) is 0011 1111 1111 in binary notation.</span></span> <span data-ttu-id="66dec-205">При этом будут использоваться первые 10 процессоров.</span><span class="sxs-lookup"><span data-stu-id="66dec-205">This specifies that the first 10 processors are to be used.</span></span> <span data-ttu-id="66dec-206">Чтобы указать следующие 10 процессоров, то есть процессоры 10–19, задайте десятичное значение 1047552 (или шестнадцатеричное значение 0xFFC00 или FFC00), которое эквивалентно двоичному значению 1111 1111 1100 0000 0000.</span><span class="sxs-lookup"><span data-stu-id="66dec-206">To specify the next 10 processors, that is, processors 10-19, specify a decimal value of 1047552 (or a hexadecimal value of 0xFFC00 or FFC00), which is equivalent to a binary value of 1111 1111 1100 0000 0000.</span></span>

| | <span data-ttu-id="66dec-207">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="66dec-207">Setting name</span></span> | <span data-ttu-id="66dec-208">Значения</span><span class="sxs-lookup"><span data-stu-id="66dec-208">Values</span></span> | <span data-ttu-id="66dec-209">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="66dec-209">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="66dec-210">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="66dec-210">**runtimeconfig.json**</span></span> | `System.GC.HeapAffinitizeMask` | <span data-ttu-id="66dec-211">*Десятичное значение*</span><span class="sxs-lookup"><span data-stu-id="66dec-211">*decimal value*</span></span> | <span data-ttu-id="66dec-212">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="66dec-212">.NET Core 3.0</span></span> |
| <span data-ttu-id="66dec-213">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="66dec-213">**Environment variable**</span></span> | `COMPlus_GCHeapAffinitizeMask` | <span data-ttu-id="66dec-214">*Шестнадцатеричное значение*</span><span class="sxs-lookup"><span data-stu-id="66dec-214">*hexadecimal value*</span></span> | <span data-ttu-id="66dec-215">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="66dec-215">.NET Core 3.0</span></span> |
| <span data-ttu-id="66dec-216">**app.config для .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="66dec-216">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="66dec-217">GCHeapAffinitizeMask</span><span class="sxs-lookup"><span data-stu-id="66dec-217">GCHeapAffinitizeMask</span></span>](../../framework/configure-apps/file-schema/runtime/gcheapaffinitizemask-element.md) | <span data-ttu-id="66dec-218">*Десятичное значение*</span><span class="sxs-lookup"><span data-stu-id="66dec-218">*decimal value*</span></span> | <span data-ttu-id="66dec-219">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="66dec-219">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="66dec-220">Пример.</span><span class="sxs-lookup"><span data-stu-id="66dec-220">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.HeapAffinitizeMask": 1023
      }
   }
}
```

### <a name="systemgcgcheapaffinitizerangescomplus_gcheapaffinitizeranges"></a><span data-ttu-id="66dec-221">System.GC.GCHeapAffinitizeRanges/COMPlus_GCHeapAffinitizeRanges</span><span class="sxs-lookup"><span data-stu-id="66dec-221">System.GC.GCHeapAffinitizeRanges/COMPlus_GCHeapAffinitizeRanges</span></span>

- <span data-ttu-id="66dec-222">Указывает список процессоров, используемых для потоков сборщика мусора.</span><span class="sxs-lookup"><span data-stu-id="66dec-222">Specifies the list of processors to use for garbage collector threads.</span></span>
- <span data-ttu-id="66dec-223">Этот параметр аналогичен [System.GC.HeapAffinitizeMask](#systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask), за исключением того, что он позволяет указать больше 64 процессоров.</span><span class="sxs-lookup"><span data-stu-id="66dec-223">This setting is similar to [System.GC.HeapAffinitizeMask](#systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask), except it allows you to specify more than 64 processors.</span></span>
- <span data-ttu-id="66dec-224">Для операционных систем Windows добавьте к номеру или диапазону процессоров префикс в виде соответствующей [группы ЦП](/windows/win32/procthread/processor-groups), например "0:1-10,0:12,1:50-52,1:70".</span><span class="sxs-lookup"><span data-stu-id="66dec-224">For Windows operating systems, prefix the processor number or range with the corresponding [CPU group](/windows/win32/procthread/processor-groups), for example, "0:1-10,0:12,1:50-52,1:70".</span></span>
- <span data-ttu-id="66dec-225">Если [сходство процессоров](#systemgcnoaffinitizecomplus_gcnoaffinitize) отключено, этот параметр игнорируется.</span><span class="sxs-lookup"><span data-stu-id="66dec-225">If [GC processor affinity](#systemgcnoaffinitizecomplus_gcnoaffinitize) is disabled, this setting is ignored.</span></span>
- <span data-ttu-id="66dec-226">Применяется только к сборке мусора сервера.</span><span class="sxs-lookup"><span data-stu-id="66dec-226">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="66dec-227">Дополнительные сведения см. в записи об [улучшении конфигурации ЦП для сборки мусора на компьютерах, имеющих более 64 ЦП](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/), в блоге Майони Стивенс (Maoni Stephens).</span><span class="sxs-lookup"><span data-stu-id="66dec-227">For more information, see [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) on Maoni Stephens' blog.</span></span>

| | <span data-ttu-id="66dec-228">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="66dec-228">Setting name</span></span> | <span data-ttu-id="66dec-229">Значения</span><span class="sxs-lookup"><span data-stu-id="66dec-229">Values</span></span> | <span data-ttu-id="66dec-230">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="66dec-230">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="66dec-231">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="66dec-231">**runtimeconfig.json**</span></span> | `System.GC.GCHeapAffinitizeRanges` | <span data-ttu-id="66dec-232">Разделенный запятыми список номеров процессоров или диапазонов номеров процессоров.</span><span class="sxs-lookup"><span data-stu-id="66dec-232">Comma-separated list of processor numbers or ranges of processor numbers.</span></span><br/><span data-ttu-id="66dec-233">Пример для Unix: "1-10,12,50-52,70"</span><span class="sxs-lookup"><span data-stu-id="66dec-233">Unix example: "1-10,12,50-52,70"</span></span><br/><span data-ttu-id="66dec-234">Пример для Windows: "0:1-10,0:12,1:50-52,1:70"</span><span class="sxs-lookup"><span data-stu-id="66dec-234">Windows example: "0:1-10,0:12,1:50-52,1:70"</span></span> | <span data-ttu-id="66dec-235">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="66dec-235">.NET Core 3.0</span></span> |
| <span data-ttu-id="66dec-236">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="66dec-236">**Environment variable**</span></span> | `COMPlus_GCHeapAffinitizeRanges` | <span data-ttu-id="66dec-237">Разделенный запятыми список номеров процессоров или диапазонов номеров процессоров.</span><span class="sxs-lookup"><span data-stu-id="66dec-237">Comma-separated list of processor numbers or ranges of processor numbers.</span></span><br/><span data-ttu-id="66dec-238">Пример для Unix: "1-10,12,50-52,70"</span><span class="sxs-lookup"><span data-stu-id="66dec-238">Unix example: "1-10,12,50-52,70"</span></span><br/><span data-ttu-id="66dec-239">Пример для Windows: "0:1-10,0:12,1:50-52,1:70"</span><span class="sxs-lookup"><span data-stu-id="66dec-239">Windows example: "0:1-10,0:12,1:50-52,1:70"</span></span> | <span data-ttu-id="66dec-240">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="66dec-240">.NET Core 3.0</span></span> |

<span data-ttu-id="66dec-241">Пример.</span><span class="sxs-lookup"><span data-stu-id="66dec-241">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.GCHeapAffinitizeRanges": "0:1-10,0:12,1:50-52,1:70"
      }
   }
}
```

### <a name="complus_gccpugroup"></a><span data-ttu-id="66dec-242">COMPlus_GCCpuGroup</span><span class="sxs-lookup"><span data-stu-id="66dec-242">COMPlus_GCCpuGroup</span></span>

- <span data-ttu-id="66dec-243">Указывает, использует ли сборщик мусора [группы ЦП](/windows/win32/procthread/processor-groups).</span><span class="sxs-lookup"><span data-stu-id="66dec-243">Configures whether the garbage collector uses [CPU groups](/windows/win32/procthread/processor-groups) or not.</span></span>

  <span data-ttu-id="66dec-244">Когда 64-разрядный компьютер с Windows имеет несколько групп ЦП, то есть доступно более 64 процессоров, включение этого элемента расширяет действие сборки мусора на все группы ЦП.</span><span class="sxs-lookup"><span data-stu-id="66dec-244">When a 64-bit Windows computer has multiple CPU groups, that is, there are more than 64 processors, enabling this element extends garbage collection across all CPU groups.</span></span> <span data-ttu-id="66dec-245">Сборщик мусора использует все ядра для создания и балансировки куч.</span><span class="sxs-lookup"><span data-stu-id="66dec-245">The garbage collector uses all cores to create and balance heaps.</span></span>

- <span data-ttu-id="66dec-246">Применяется только к сборке мусора сервера в 64-разрядных операционных системах Windows.</span><span class="sxs-lookup"><span data-stu-id="66dec-246">Applies to server garbage collection on 64-bit Windows operation systems only.</span></span>
- <span data-ttu-id="66dec-247">По умолчанию: сборка мусора не распространяется на группы ЦП.</span><span class="sxs-lookup"><span data-stu-id="66dec-247">Default: GC does not extend across CPU groups.</span></span> <span data-ttu-id="66dec-248">Это эквивалентно присвоению значения `0`.</span><span class="sxs-lookup"><span data-stu-id="66dec-248">This is equivalent to setting the value to `0`.</span></span>
- <span data-ttu-id="66dec-249">Дополнительные сведения см. в записи об [улучшении конфигурации ЦП для сборки мусора на компьютерах, имеющих более 64 ЦП](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/), в блоге Майони Стивенс (Maoni Stephens).</span><span class="sxs-lookup"><span data-stu-id="66dec-249">For more information, see [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) on Maoni Stephens' blog.</span></span>

| | <span data-ttu-id="66dec-250">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="66dec-250">Setting name</span></span> | <span data-ttu-id="66dec-251">Значения</span><span class="sxs-lookup"><span data-stu-id="66dec-251">Values</span></span> | <span data-ttu-id="66dec-252">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="66dec-252">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="66dec-253">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="66dec-253">**runtimeconfig.json**</span></span> | <span data-ttu-id="66dec-254">Н/Д</span><span class="sxs-lookup"><span data-stu-id="66dec-254">N/A</span></span> | <span data-ttu-id="66dec-255">Н/Д</span><span class="sxs-lookup"><span data-stu-id="66dec-255">N/A</span></span> | <span data-ttu-id="66dec-256">Н/Д</span><span class="sxs-lookup"><span data-stu-id="66dec-256">N/A</span></span> |
| <span data-ttu-id="66dec-257">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="66dec-257">**Environment variable**</span></span> | `COMPlus_GCCpuGroup` | <span data-ttu-id="66dec-258">`0` — отключено</span><span class="sxs-lookup"><span data-stu-id="66dec-258">`0` - disabled</span></span><br/><span data-ttu-id="66dec-259">`1` — включено</span><span class="sxs-lookup"><span data-stu-id="66dec-259">`1` - enabled</span></span> | <span data-ttu-id="66dec-260">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="66dec-260">.NET Core 1.0</span></span> |
| <span data-ttu-id="66dec-261">**app.config для .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="66dec-261">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="66dec-262">GCCpuGroup</span><span class="sxs-lookup"><span data-stu-id="66dec-262">GCCpuGroup</span></span>](../../framework/configure-apps/file-schema/runtime/gccpugroup-element.md) | <span data-ttu-id="66dec-263">`false` — отключено</span><span class="sxs-lookup"><span data-stu-id="66dec-263">`false` - disabled</span></span><br/><span data-ttu-id="66dec-264">`true` — включено</span><span class="sxs-lookup"><span data-stu-id="66dec-264">`true` - enabled</span></span> |  |

> [!NOTE]
> <span data-ttu-id="66dec-265">Чтобы настроить среду CLR для распределения потоков из пула потоков по всем группам ЦП, включите параметр [Элемент Thread_UseAllCpuGroups](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md).</span><span class="sxs-lookup"><span data-stu-id="66dec-265">To configure the common language runtime (CLR) to also distribute threads from the thread pool across all CPU groups, enable the [Thread_UseAllCpuGroups element](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md) option.</span></span> <span data-ttu-id="66dec-266">Для приложений .NET Core этот параметр можно включить, задав для переменной среды `COMPlus_Thread_UseAllCpuGroups` значение `1`.</span><span class="sxs-lookup"><span data-stu-id="66dec-266">For .NET Core apps, you can enable this option by setting the value of the `COMPlus_Thread_UseAllCpuGroups` environment variable to `1`.</span></span>

### <a name="systemgcnoaffinitizecomplus_gcnoaffinitize"></a><span data-ttu-id="66dec-267">System.GC.NoAffinitize/COMPlus_GCNoAffinitize</span><span class="sxs-lookup"><span data-stu-id="66dec-267">System.GC.NoAffinitize/COMPlus_GCNoAffinitize</span></span>

- <span data-ttu-id="66dec-268">Указывает, следует ли *реализовать сходство* потоков сборки мусора с процессорами.</span><span class="sxs-lookup"><span data-stu-id="66dec-268">Specifies whether to *affinitize* garbage collection threads with processors.</span></span> <span data-ttu-id="66dec-269">Реализация сходства потока сборки мусора означает, что он может выполняться только на определенном ЦП.</span><span class="sxs-lookup"><span data-stu-id="66dec-269">To affinitize a GC thread means that it can only run on its specific CPU.</span></span> <span data-ttu-id="66dec-270">Куча создается для каждого потока сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="66dec-270">A heap is created for each GC thread.</span></span>
- <span data-ttu-id="66dec-271">Применяется только к сборке мусора сервера.</span><span class="sxs-lookup"><span data-stu-id="66dec-271">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="66dec-272">По умолчанию: реализация сходства потоков сборки мусора с процессорами.</span><span class="sxs-lookup"><span data-stu-id="66dec-272">Default: Affinitize garbage collection threads with processors.</span></span> <span data-ttu-id="66dec-273">Это эквивалентно присвоению значения `false`.</span><span class="sxs-lookup"><span data-stu-id="66dec-273">This is equivalent to setting the value to `false`.</span></span>

| | <span data-ttu-id="66dec-274">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="66dec-274">Setting name</span></span> | <span data-ttu-id="66dec-275">Значения</span><span class="sxs-lookup"><span data-stu-id="66dec-275">Values</span></span> | <span data-ttu-id="66dec-276">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="66dec-276">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="66dec-277">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="66dec-277">**runtimeconfig.json**</span></span> | `System.GC.NoAffinitize` | <span data-ttu-id="66dec-278">`false` — реализовать сходство</span><span class="sxs-lookup"><span data-stu-id="66dec-278">`false` - affinitize</span></span><br/><span data-ttu-id="66dec-279">`true` — не реализовывать сходство</span><span class="sxs-lookup"><span data-stu-id="66dec-279">`true` - don't affinitize</span></span> | <span data-ttu-id="66dec-280">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="66dec-280">.NET Core 3.0</span></span> |
| <span data-ttu-id="66dec-281">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="66dec-281">**Environment variable**</span></span> | `COMPlus_GCNoAffinitize` | <span data-ttu-id="66dec-282">`0` — реализовать сходство</span><span class="sxs-lookup"><span data-stu-id="66dec-282">`0` - affinitize</span></span><br/><span data-ttu-id="66dec-283">`1` — не реализовывать сходство</span><span class="sxs-lookup"><span data-stu-id="66dec-283">`1` - don't affinitize</span></span> | <span data-ttu-id="66dec-284">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="66dec-284">.NET Core 3.0</span></span> |
| <span data-ttu-id="66dec-285">**app.config для .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="66dec-285">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="66dec-286">GCNoAffinitize</span><span class="sxs-lookup"><span data-stu-id="66dec-286">GCNoAffinitize</span></span>](../../framework/configure-apps/file-schema/runtime/gcnoaffinitize-element.md) | <span data-ttu-id="66dec-287">`false` — реализовать сходство</span><span class="sxs-lookup"><span data-stu-id="66dec-287">`false` - affinitize</span></span><br/><span data-ttu-id="66dec-288">`true` — не реализовывать сходство</span><span class="sxs-lookup"><span data-stu-id="66dec-288">`true` - don't affinitize</span></span> | <span data-ttu-id="66dec-289">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="66dec-289">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="66dec-290">Пример.</span><span class="sxs-lookup"><span data-stu-id="66dec-290">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.NoAffinitize": true
      }
   }
}
```

### <a name="systemgcheaphardlimitcomplus_gcheaphardlimit"></a><span data-ttu-id="66dec-291">System.GC.HeapHardLimit/COMPlus_GCHeapHardLimit</span><span class="sxs-lookup"><span data-stu-id="66dec-291">System.GC.HeapHardLimit/COMPlus_GCHeapHardLimit</span></span>

- <span data-ttu-id="66dec-292">Указывает максимальный размер фиксации в байтах для кучи сборки мусора и учета сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="66dec-292">Specifies the maximum commit size, in bytes, for the GC heap and GC bookkeeping.</span></span>
- <span data-ttu-id="66dec-293">Этот параметр применим только к 64-разрядным компьютерам.</span><span class="sxs-lookup"><span data-stu-id="66dec-293">This setting only applies to 64-bit computers.</span></span>
- <span data-ttu-id="66dec-294">Значение по умолчанию, которое применяется только в определенных случаях, превышает 20 МБ или 75 % предельного объема памяти в контейнере.</span><span class="sxs-lookup"><span data-stu-id="66dec-294">The default value, which only applies in certain cases, is the greater of 20 MB or 75% of the memory limit on the container.</span></span> <span data-ttu-id="66dec-295">Значение по умолчанию применяется, если:</span><span class="sxs-lookup"><span data-stu-id="66dec-295">The default value applies if:</span></span>

  - <span data-ttu-id="66dec-296">процесс выполняется в контейнере с заданным предельным объемом памяти;</span><span class="sxs-lookup"><span data-stu-id="66dec-296">The process is running inside a container that has a specified memory limit.</span></span>
  - <span data-ttu-id="66dec-297">параметр [System.GC.HeapHardLimitPercent](#systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent) не задан.</span><span class="sxs-lookup"><span data-stu-id="66dec-297">[System.GC.HeapHardLimitPercent](#systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent) is not set.</span></span>

| | <span data-ttu-id="66dec-298">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="66dec-298">Setting name</span></span> | <span data-ttu-id="66dec-299">Значения</span><span class="sxs-lookup"><span data-stu-id="66dec-299">Values</span></span> | <span data-ttu-id="66dec-300">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="66dec-300">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="66dec-301">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="66dec-301">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimit` | <span data-ttu-id="66dec-302">*Десятичное значение*</span><span class="sxs-lookup"><span data-stu-id="66dec-302">*decimal value*</span></span> | <span data-ttu-id="66dec-303">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="66dec-303">.NET Core 3.0</span></span> |
| <span data-ttu-id="66dec-304">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="66dec-304">**Environment variable**</span></span> | `COMPlus_GCHeapHardLimit` | <span data-ttu-id="66dec-305">*Шестнадцатеричное значение*</span><span class="sxs-lookup"><span data-stu-id="66dec-305">*hexadecimal value*</span></span> | <span data-ttu-id="66dec-306">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="66dec-306">.NET Core 3.0</span></span> |

<span data-ttu-id="66dec-307">Пример.</span><span class="sxs-lookup"><span data-stu-id="66dec-307">Example:</span></span>

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
> <span data-ttu-id="66dec-308">Если вы задаете параметр в *runtimeconfig.json*, укажите десятичное значение.</span><span class="sxs-lookup"><span data-stu-id="66dec-308">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="66dec-309">Если вы задаете параметр в виде переменной среды, укажите шестнадцатеричное значение.</span><span class="sxs-lookup"><span data-stu-id="66dec-309">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="66dec-310">Например, чтобы задать для куч жесткое ограничение в 200 мебибайт (Миб), для JSON-файла нужно указать значение 209715200, а для переменной среды — значение 0xC800000 или C800000.</span><span class="sxs-lookup"><span data-stu-id="66dec-310">For example, to specify a heap hard limit of 200 mebibytes (MiB), the values would be 209715200 for the JSON file and 0xC800000 or C800000 for the environment variable.</span></span>

### <a name="systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent"></a><span data-ttu-id="66dec-311">System.GC.HeapHardLimitPercent/COMPlus_GCHeapHardLimitPercent</span><span class="sxs-lookup"><span data-stu-id="66dec-311">System.GC.HeapHardLimitPercent/COMPlus_GCHeapHardLimitPercent</span></span>

- <span data-ttu-id="66dec-312">Указывает допустимое использование кучи сборки мусора в процентах от общего объема физической памяти.</span><span class="sxs-lookup"><span data-stu-id="66dec-312">Specifies the allowable GC heap usage as a percentage of the total physical memory.</span></span>
- <span data-ttu-id="66dec-313">Если также задан параметр [System.GC.HeapHardLimit](#systemgcheaphardlimitcomplus_gcheaphardlimit), этот параметр игнорируется.</span><span class="sxs-lookup"><span data-stu-id="66dec-313">If [System.GC.HeapHardLimit](#systemgcheaphardlimitcomplus_gcheaphardlimit) is also set, this setting is ignored.</span></span>
- <span data-ttu-id="66dec-314">Этот параметр применим только к 64-разрядным компьютерам.</span><span class="sxs-lookup"><span data-stu-id="66dec-314">This setting only applies to 64-bit computers.</span></span>
- <span data-ttu-id="66dec-315">Если процесс выполняется в контейнере с заданным предельным объемом памяти, процентная доля вычисляется как процент от этого объема памяти.</span><span class="sxs-lookup"><span data-stu-id="66dec-315">If the process is running inside a container that has a specified memory limit, the percentage is calculated as a percentage of that memory limit.</span></span>
- <span data-ttu-id="66dec-316">Значение по умолчанию, которое применяется только в определенных случаях, не превышает 20 МБ или 75 % предельного объема памяти в контейнере.</span><span class="sxs-lookup"><span data-stu-id="66dec-316">The default value, which only applies in certain cases, is the lesser of 20 MB or 75% of the memory limit on the container.</span></span> <span data-ttu-id="66dec-317">Значение по умолчанию применяется, если:</span><span class="sxs-lookup"><span data-stu-id="66dec-317">The default value applies if:</span></span>

  - <span data-ttu-id="66dec-318">процесс выполняется в контейнере с заданным предельным объемом памяти;</span><span class="sxs-lookup"><span data-stu-id="66dec-318">The process is running inside a container that has a specified memory limit.</span></span>
  - <span data-ttu-id="66dec-319">параметр [System.GC.HeapHardLimit](#systemgcheaphardlimitcomplus_gcheaphardlimit) не задан.</span><span class="sxs-lookup"><span data-stu-id="66dec-319">[System.GC.HeapHardLimit](#systemgcheaphardlimitcomplus_gcheaphardlimit) is not set.</span></span>

| | <span data-ttu-id="66dec-320">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="66dec-320">Setting name</span></span> | <span data-ttu-id="66dec-321">Значения</span><span class="sxs-lookup"><span data-stu-id="66dec-321">Values</span></span> | <span data-ttu-id="66dec-322">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="66dec-322">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="66dec-323">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="66dec-323">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimitPercent` | <span data-ttu-id="66dec-324">*Десятичное значение*</span><span class="sxs-lookup"><span data-stu-id="66dec-324">*decimal value*</span></span> | <span data-ttu-id="66dec-325">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="66dec-325">.NET Core 3.0</span></span> |
| <span data-ttu-id="66dec-326">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="66dec-326">**Environment variable**</span></span> | `COMPlus_GCHeapHardLimitPercent` | <span data-ttu-id="66dec-327">*Шестнадцатеричное значение*</span><span class="sxs-lookup"><span data-stu-id="66dec-327">*hexadecimal value*</span></span> | <span data-ttu-id="66dec-328">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="66dec-328">.NET Core 3.0</span></span> |

<span data-ttu-id="66dec-329">Пример.</span><span class="sxs-lookup"><span data-stu-id="66dec-329">Example:</span></span>

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
> <span data-ttu-id="66dec-330">Если вы задаете параметр в *runtimeconfig.json*, укажите десятичное значение.</span><span class="sxs-lookup"><span data-stu-id="66dec-330">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="66dec-331">Если вы задаете параметр в виде переменной среды, укажите шестнадцатеричное значение.</span><span class="sxs-lookup"><span data-stu-id="66dec-331">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="66dec-332">Например, чтобы ограничить использование кучи значением 30 %, для JSON-файла нужно указать 30, а для переменной среды — 0x1E или 1E.</span><span class="sxs-lookup"><span data-stu-id="66dec-332">For example, to limit the heap usage to 30%, the values would be 30 for the JSON file and 0x1E or 1E for the environment variable.</span></span>

### <a name="systemgcretainvmcomplus_gcretainvm"></a><span data-ttu-id="66dec-333">System.GC.RetainVM/COMPlus_GCRetainVM</span><span class="sxs-lookup"><span data-stu-id="66dec-333">System.GC.RetainVM/COMPlus_GCRetainVM</span></span>

- <span data-ttu-id="66dec-334">Настраивает, будут ли удаляемые сегменты помещаться в список ожидания для будущего использования или возвращаться операционной системе (ОС).</span><span class="sxs-lookup"><span data-stu-id="66dec-334">Configures whether segments that should be deleted are put on a standby list for future use or are released back to the operating system (OS).</span></span>
- <span data-ttu-id="66dec-335">По умолчанию: возвращение сегментов операционной системе.</span><span class="sxs-lookup"><span data-stu-id="66dec-335">Default: Release segments back to the operating system.</span></span> <span data-ttu-id="66dec-336">Это эквивалентно присвоению значения `false`.</span><span class="sxs-lookup"><span data-stu-id="66dec-336">This is equivalent to setting the value to `false`.</span></span>

| | <span data-ttu-id="66dec-337">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="66dec-337">Setting name</span></span> | <span data-ttu-id="66dec-338">Значения</span><span class="sxs-lookup"><span data-stu-id="66dec-338">Values</span></span> | <span data-ttu-id="66dec-339">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="66dec-339">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="66dec-340">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="66dec-340">**runtimeconfig.json**</span></span> | `System.GC.RetainVM` | <span data-ttu-id="66dec-341">`false` — возвращение операционной системе</span><span class="sxs-lookup"><span data-stu-id="66dec-341">`false` - release to OS</span></span><br/><span data-ttu-id="66dec-342">`true` — помещение в режим ожидания</span><span class="sxs-lookup"><span data-stu-id="66dec-342">`true` - put on standby</span></span> | <span data-ttu-id="66dec-343">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="66dec-343">.NET Core 1.0</span></span> |
| <span data-ttu-id="66dec-344">**Свойство MSBuild**</span><span class="sxs-lookup"><span data-stu-id="66dec-344">**MSBuild property**</span></span> | `RetainVMGarbageCollection` | <span data-ttu-id="66dec-345">`false` — возвращение операционной системе</span><span class="sxs-lookup"><span data-stu-id="66dec-345">`false` - release to OS</span></span><br/><span data-ttu-id="66dec-346">`true` — помещение в режим ожидания</span><span class="sxs-lookup"><span data-stu-id="66dec-346">`true` - put on standby</span></span> | <span data-ttu-id="66dec-347">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="66dec-347">.NET Core 1.0</span></span> |
| <span data-ttu-id="66dec-348">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="66dec-348">**Environment variable**</span></span> | `COMPlus_GCRetainVM` | <span data-ttu-id="66dec-349">`0` — возвращение операционной системе</span><span class="sxs-lookup"><span data-stu-id="66dec-349">`0` - release to OS</span></span><br/><span data-ttu-id="66dec-350">`1` — помещение в режим ожидания</span><span class="sxs-lookup"><span data-stu-id="66dec-350">`1` - put on standby</span></span> | <span data-ttu-id="66dec-351">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="66dec-351">.NET Core 1.0</span></span> |

### <a name="examples"></a><span data-ttu-id="66dec-352">Примеры</span><span class="sxs-lookup"><span data-stu-id="66dec-352">Examples</span></span>

<span data-ttu-id="66dec-353">Файл *runtimeconfig.json*</span><span class="sxs-lookup"><span data-stu-id="66dec-353">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.RetainVM": true
      }
   }
}
```

<span data-ttu-id="66dec-354">Файл проекта:</span><span class="sxs-lookup"><span data-stu-id="66dec-354">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <RetainVMGarbageCollection>true</RetainVMGarbageCollection>
  </PropertyGroup>

</Project>
```

## <a name="large-pages"></a><span data-ttu-id="66dec-355">Большие страницы</span><span class="sxs-lookup"><span data-stu-id="66dec-355">Large pages</span></span>

### <a name="complus_gclargepages"></a><span data-ttu-id="66dec-356">COMPlus_GCLargePages</span><span class="sxs-lookup"><span data-stu-id="66dec-356">COMPlus_GCLargePages</span></span>

- <span data-ttu-id="66dec-357">Указывает, следует ли использовать большие страницы, когда задано жесткое ограничение куч.</span><span class="sxs-lookup"><span data-stu-id="66dec-357">Specifies whether large pages should be used when a heap hard limit is set.</span></span>
- <span data-ttu-id="66dec-358">По умолчанию: не следует использовать большие страницы, если задан фиксированный предел кучи.</span><span class="sxs-lookup"><span data-stu-id="66dec-358">Default: Don't use large pages when a heap hard limit is set.</span></span> <span data-ttu-id="66dec-359">Это эквивалентно присвоению значения `0`.</span><span class="sxs-lookup"><span data-stu-id="66dec-359">This is equivalent to setting the value to `0`.</span></span>
- <span data-ttu-id="66dec-360">Это экспериментальный параметр.</span><span class="sxs-lookup"><span data-stu-id="66dec-360">This is an experimental setting.</span></span>

| | <span data-ttu-id="66dec-361">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="66dec-361">Setting name</span></span> | <span data-ttu-id="66dec-362">Значения</span><span class="sxs-lookup"><span data-stu-id="66dec-362">Values</span></span> | <span data-ttu-id="66dec-363">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="66dec-363">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="66dec-364">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="66dec-364">**runtimeconfig.json**</span></span> | <span data-ttu-id="66dec-365">Н/Д</span><span class="sxs-lookup"><span data-stu-id="66dec-365">N/A</span></span> | <span data-ttu-id="66dec-366">Н/Д</span><span class="sxs-lookup"><span data-stu-id="66dec-366">N/A</span></span> | <span data-ttu-id="66dec-367">Н/Д</span><span class="sxs-lookup"><span data-stu-id="66dec-367">N/A</span></span> |
| <span data-ttu-id="66dec-368">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="66dec-368">**Environment variable**</span></span> | `COMPlus_GCLargePages` | <span data-ttu-id="66dec-369">`0` — отключено</span><span class="sxs-lookup"><span data-stu-id="66dec-369">`0` - disabled</span></span><br/><span data-ttu-id="66dec-370">`1` — включено</span><span class="sxs-lookup"><span data-stu-id="66dec-370">`1` - enabled</span></span> | <span data-ttu-id="66dec-371">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="66dec-371">.NET Core 3.0</span></span> |

## <a name="large-objects"></a><span data-ttu-id="66dec-372">Большие объекты</span><span class="sxs-lookup"><span data-stu-id="66dec-372">Large objects</span></span>

### <a name="complus_gcallowverylargeobjects"></a><span data-ttu-id="66dec-373">COMPlus_gcAllowVeryLargeObjects</span><span class="sxs-lookup"><span data-stu-id="66dec-373">COMPlus_gcAllowVeryLargeObjects</span></span>

- <span data-ttu-id="66dec-374">Настраивает для сборщика мусора на 64-разрядных платформах поддержку массивов, размер которых превышает 2 гигабайта (ГБ).</span><span class="sxs-lookup"><span data-stu-id="66dec-374">Configures garbage collector support on 64-bit platforms for arrays that are greater than 2 gigabytes (GB) in total size.</span></span>
- <span data-ttu-id="66dec-375">По умолчанию: сборка мусора поддерживает массивы размером более 2 ГБ.</span><span class="sxs-lookup"><span data-stu-id="66dec-375">Default: GC supports arrays greater than 2-GB.</span></span> <span data-ttu-id="66dec-376">Это эквивалентно присвоению значения `1`.</span><span class="sxs-lookup"><span data-stu-id="66dec-376">This is equivalent to setting the value to `1`.</span></span>
- <span data-ttu-id="66dec-377">В будущей версии .NET этот параметр может быть объявлен устаревшим.</span><span class="sxs-lookup"><span data-stu-id="66dec-377">This option may become obsolete in a future version of .NET.</span></span>

| | <span data-ttu-id="66dec-378">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="66dec-378">Setting name</span></span> | <span data-ttu-id="66dec-379">Значения</span><span class="sxs-lookup"><span data-stu-id="66dec-379">Values</span></span> | <span data-ttu-id="66dec-380">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="66dec-380">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="66dec-381">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="66dec-381">**runtimeconfig.json**</span></span> | <span data-ttu-id="66dec-382">Н/Д</span><span class="sxs-lookup"><span data-stu-id="66dec-382">N/A</span></span> | <span data-ttu-id="66dec-383">Н/Д</span><span class="sxs-lookup"><span data-stu-id="66dec-383">N/A</span></span> | <span data-ttu-id="66dec-384">Н/Д</span><span class="sxs-lookup"><span data-stu-id="66dec-384">N/A</span></span> |
| <span data-ttu-id="66dec-385">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="66dec-385">**Environment variable**</span></span> | `COMPlus_gcAllowVeryLargeObjects` | <span data-ttu-id="66dec-386">`1` — включено</span><span class="sxs-lookup"><span data-stu-id="66dec-386">`1` - enabled</span></span><br/> <span data-ttu-id="66dec-387">`0` — отключено</span><span class="sxs-lookup"><span data-stu-id="66dec-387">`0` - disabled</span></span> | <span data-ttu-id="66dec-388">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="66dec-388">.NET Core 1.0</span></span> |
| <span data-ttu-id="66dec-389">**app.config для .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="66dec-389">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="66dec-390">gcAllowVeryLargeObjects</span><span class="sxs-lookup"><span data-stu-id="66dec-390">gcAllowVeryLargeObjects</span></span>](../../framework/configure-apps/file-schema/runtime/gcallowverylargeobjects-element.md) | <span data-ttu-id="66dec-391">`1` — включено</span><span class="sxs-lookup"><span data-stu-id="66dec-391">`1` - enabled</span></span><br/> <span data-ttu-id="66dec-392">`0` — отключено</span><span class="sxs-lookup"><span data-stu-id="66dec-392">`0` - disabled</span></span> | <span data-ttu-id="66dec-393">.NET Framework 4,5</span><span class="sxs-lookup"><span data-stu-id="66dec-393">.NET Framework 4.5</span></span> |

## <a name="large-object-heap-threshold"></a><span data-ttu-id="66dec-394">Пороговое значение кучи больших объектов</span><span class="sxs-lookup"><span data-stu-id="66dec-394">Large object heap threshold</span></span>

### <a name="systemgclohthresholdcomplus_gclohthreshold"></a><span data-ttu-id="66dec-395">System.GC.LOHThreshold/COMPlus_GCLOHThreshold</span><span class="sxs-lookup"><span data-stu-id="66dec-395">System.GC.LOHThreshold/COMPlus_GCLOHThreshold</span></span>

- <span data-ttu-id="66dec-396">Указывает пороговый размер (в байтах), при котором объекты попадают в кучу больших объектов (LOH).</span><span class="sxs-lookup"><span data-stu-id="66dec-396">Specifies the threshold size, in bytes, that causes objects to go on the large object heap (LOH).</span></span>
- <span data-ttu-id="66dec-397">Пороговое значение по умолчанию — 85 000 байт.</span><span class="sxs-lookup"><span data-stu-id="66dec-397">The default threshold is 85,000 bytes.</span></span>
- <span data-ttu-id="66dec-398">Указанное значение должно быть больше порогового значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="66dec-398">The value you specify must be larger than the default threshold.</span></span>

| | <span data-ttu-id="66dec-399">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="66dec-399">Setting name</span></span> | <span data-ttu-id="66dec-400">Значения</span><span class="sxs-lookup"><span data-stu-id="66dec-400">Values</span></span> | <span data-ttu-id="66dec-401">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="66dec-401">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="66dec-402">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="66dec-402">**runtimeconfig.json**</span></span> | `System.GC.LOHThreshold` | <span data-ttu-id="66dec-403">*Десятичное значение*</span><span class="sxs-lookup"><span data-stu-id="66dec-403">*decimal value*</span></span> | <span data-ttu-id="66dec-404">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="66dec-404">.NET Core 1.0</span></span> |
| <span data-ttu-id="66dec-405">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="66dec-405">**Environment variable**</span></span> | `COMPlus_GCLOHThreshold` | <span data-ttu-id="66dec-406">*Шестнадцатеричное значение*</span><span class="sxs-lookup"><span data-stu-id="66dec-406">*hexadecimal value*</span></span> | <span data-ttu-id="66dec-407">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="66dec-407">.NET Core 1.0</span></span> |
| <span data-ttu-id="66dec-408">**app.config для .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="66dec-408">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="66dec-409">GCLOHThreshold</span><span class="sxs-lookup"><span data-stu-id="66dec-409">GCLOHThreshold</span></span>](../../framework/configure-apps/file-schema/runtime/gclohthreshold-element.md) | <span data-ttu-id="66dec-410">*Десятичное значение*</span><span class="sxs-lookup"><span data-stu-id="66dec-410">*decimal value*</span></span> | <span data-ttu-id="66dec-411">.NET Framework 4.8</span><span class="sxs-lookup"><span data-stu-id="66dec-411">.NET Framework 4.8</span></span> |

<span data-ttu-id="66dec-412">Пример.</span><span class="sxs-lookup"><span data-stu-id="66dec-412">Example:</span></span>

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
> <span data-ttu-id="66dec-413">Если вы задаете параметр в *runtimeconfig.json*, укажите десятичное значение.</span><span class="sxs-lookup"><span data-stu-id="66dec-413">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="66dec-414">Если вы задаете параметр в виде переменной среды, укажите шестнадцатеричное значение.</span><span class="sxs-lookup"><span data-stu-id="66dec-414">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="66dec-415">Например, чтобы задать порог размера в 120 000 байт, для JSON-файла нужно указать значение 120000, а для переменной среды — значение 0x1D4C0 или 1D4C0.</span><span class="sxs-lookup"><span data-stu-id="66dec-415">For example, to set a threshold size of 120,000 bytes, the values would be 120000 for the JSON file and 0x1D4C0 or 1D4C0 for the environment variable.</span></span>

## <a name="standalone-gc"></a><span data-ttu-id="66dec-416">Автономный сборщик мусора</span><span class="sxs-lookup"><span data-stu-id="66dec-416">Standalone GC</span></span>

### <a name="complus_gcname"></a><span data-ttu-id="66dec-417">COMPlus_GCName</span><span class="sxs-lookup"><span data-stu-id="66dec-417">COMPlus_GCName</span></span>

- <span data-ttu-id="66dec-418">Указывает путь к библиотеке, содержащей сборщик мусора, который среда выполнения намеревается загрузить.</span><span class="sxs-lookup"><span data-stu-id="66dec-418">Specifies a path to the library containing the garbage collector that the runtime intends to load.</span></span>
- <span data-ttu-id="66dec-419">Дополнительные сведения см. в статье [Проектирования загрузчика автономного сборщика мусора](https://github.com/dotnet/runtime/blob/master/docs/design/features/standalone-gc-loading.md).</span><span class="sxs-lookup"><span data-stu-id="66dec-419">For more information, see [Standalone GC loader design](https://github.com/dotnet/runtime/blob/master/docs/design/features/standalone-gc-loading.md).</span></span>

| | <span data-ttu-id="66dec-420">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="66dec-420">Setting name</span></span> | <span data-ttu-id="66dec-421">Значения</span><span class="sxs-lookup"><span data-stu-id="66dec-421">Values</span></span> | <span data-ttu-id="66dec-422">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="66dec-422">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="66dec-423">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="66dec-423">**runtimeconfig.json**</span></span> | <span data-ttu-id="66dec-424">Н/Д</span><span class="sxs-lookup"><span data-stu-id="66dec-424">N/A</span></span> | <span data-ttu-id="66dec-425">Н/Д</span><span class="sxs-lookup"><span data-stu-id="66dec-425">N/A</span></span> | <span data-ttu-id="66dec-426">Н/Д</span><span class="sxs-lookup"><span data-stu-id="66dec-426">N/A</span></span> |
| <span data-ttu-id="66dec-427">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="66dec-427">**Environment variable**</span></span> | `COMPlus_GCName` | <span data-ttu-id="66dec-428">*string_path*</span><span class="sxs-lookup"><span data-stu-id="66dec-428">*string_path*</span></span> | <span data-ttu-id="66dec-429">.NET Core 2.0;</span><span class="sxs-lookup"><span data-stu-id="66dec-429">.NET Core 2.0</span></span> |
