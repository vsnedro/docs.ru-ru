---
title: Параметры конфигурации сборщика мусора
description: Сведения о параметрах времени выполнения, определяющих, как сборщик мусора управляет памятью для приложений .NET Core.
ms.date: 01/09/2020
ms.topic: reference
ms.openlocfilehash: dfb641eeda03d1acaa4771bd6253fcb33c4082a6
ms.sourcegitcommit: d9470d8b2278b33108332c05224d86049cb9484b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/17/2020
ms.locfileid: "81607814"
---
# <a name="run-time-configuration-options-for-garbage-collection"></a><span data-ttu-id="bb2ba-103">Параметры конфигурации времени выполнения для сборки мусора</span><span class="sxs-lookup"><span data-stu-id="bb2ba-103">Run-time configuration options for garbage collection</span></span>

<span data-ttu-id="bb2ba-104">Эта страница содержит сведения о параметрах сборщика мусора (GC), которые можно изменить во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="bb2ba-104">This page contains information about garbage collector (GC) settings that can be changed at run time.</span></span> <span data-ttu-id="bb2ba-105">Если вы пытаетесь добиться пиковой производительности запущенных приложений, рекомендуется использовать эти параметры.</span><span class="sxs-lookup"><span data-stu-id="bb2ba-105">If you're trying to achieve peak performance of a running app, consider using these settings.</span></span> <span data-ttu-id="bb2ba-106">Однако значения по умолчанию обеспечивают оптимальную производительность для большинства приложений в типичных ситуациях.</span><span class="sxs-lookup"><span data-stu-id="bb2ba-106">However, the defaults provide optimum performance for most applications in typical situations.</span></span>

<span data-ttu-id="bb2ba-107">На этой странице параметры упорядочены по группам.</span><span class="sxs-lookup"><span data-stu-id="bb2ba-107">Settings are arranged into groups on this page.</span></span> <span data-ttu-id="bb2ba-108">Параметры в каждой группе обычно используются совместно друг с другом для достижения определенного результата.</span><span class="sxs-lookup"><span data-stu-id="bb2ba-108">The settings within each group are commonly used in conjunction with each other to achieve a specific result.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="bb2ba-109">Эти параметры также могут динамически изменяться приложением во время его выполнения, поэтому любые заданные параметры времени выполнения могут быть переопределены.</span><span class="sxs-lookup"><span data-stu-id="bb2ba-109">These settings can also be changed dynamically by the app as it's running, so any run-time settings you set may be overridden.</span></span>
> - <span data-ttu-id="bb2ba-110">Некоторые параметры, такие как [уровень задержки](../../standard/garbage-collection/latency.md), обычно задаются только через API во время разработки.</span><span class="sxs-lookup"><span data-stu-id="bb2ba-110">Some settings, such as [latency level](../../standard/garbage-collection/latency.md), are typically set only through the API at design time.</span></span> <span data-ttu-id="bb2ba-111">Такие параметры будут пропущены на этой странице.</span><span class="sxs-lookup"><span data-stu-id="bb2ba-111">Such settings are omitted from this page.</span></span>
> - <span data-ttu-id="bb2ba-112">Для числовых значений используйте десятичную нотацию для параметров в файле *runtimeconfig.json* и шестнадцатеричную нотацию для параметров переменных среды.</span><span class="sxs-lookup"><span data-stu-id="bb2ba-112">For number values, use decimal notation for settings in the *runtimeconfig.json* file and hexadecimal notation for environment variable settings.</span></span> <span data-ttu-id="bb2ba-113">Шестнадцатеричные значения можно указать с помощью префикса "0x" или без него.</span><span class="sxs-lookup"><span data-stu-id="bb2ba-113">For hexadecimal values, you can specify them with or without the "0x" prefix.</span></span>

## <a name="flavors-of-garbage-collection"></a><span data-ttu-id="bb2ba-114">Варианты сборки мусора</span><span class="sxs-lookup"><span data-stu-id="bb2ba-114">Flavors of garbage collection</span></span>

<span data-ttu-id="bb2ba-115">Два основных варианта сборки мусора — это сборка мусора рабочей станции и сборка мусора сервера.</span><span class="sxs-lookup"><span data-stu-id="bb2ba-115">The two main flavors of garbage collection are workstation GC and server GC.</span></span> <span data-ttu-id="bb2ba-116">Дополнительные сведения о различиях между этими двумя вариантами см. в статье [Основы сборки мусора](../../standard/garbage-collection/fundamentals.md#workstation-and-server-garbage-collection).</span><span class="sxs-lookup"><span data-stu-id="bb2ba-116">For more information about differences between the two, see [Fundamentals of garbage collection](../../standard/garbage-collection/fundamentals.md#workstation-and-server-garbage-collection).</span></span>

<span data-ttu-id="bb2ba-117">Подвиды сборки мусора представлены фоновым и непараллельным выполнением.</span><span class="sxs-lookup"><span data-stu-id="bb2ba-117">The subflavors of garbage collection are background and non-concurrent.</span></span>

<span data-ttu-id="bb2ba-118">Чтобы выбрать варианты сборки мусора, используйте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="bb2ba-118">Use the following settings to select flavors of garbage collection:</span></span>

### <a name="systemgcservercomplus_gcserver"></a><span data-ttu-id="bb2ba-119">System.GC.Server/COMPlus_gcServer</span><span class="sxs-lookup"><span data-stu-id="bb2ba-119">System.GC.Server/COMPlus_gcServer</span></span>

- <span data-ttu-id="bb2ba-120">Указывает, использует ли приложение сборку мусора рабочей станции или сборку мусора сервера.</span><span class="sxs-lookup"><span data-stu-id="bb2ba-120">Configures whether the application uses workstation garbage collection or server garbage collection.</span></span>
- <span data-ttu-id="bb2ba-121">По умолчанию: сборка мусора рабочей станции (`false`).</span><span class="sxs-lookup"><span data-stu-id="bb2ba-121">Default: Workstation garbage collection (`false`).</span></span>

| | <span data-ttu-id="bb2ba-122">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="bb2ba-122">Setting name</span></span> | <span data-ttu-id="bb2ba-123">Значения</span><span class="sxs-lookup"><span data-stu-id="bb2ba-123">Values</span></span> | <span data-ttu-id="bb2ba-124">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="bb2ba-124">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="bb2ba-125">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="bb2ba-125">**runtimeconfig.json**</span></span> | `System.GC.Server` | <span data-ttu-id="bb2ba-126">`false` — рабочая станция</span><span class="sxs-lookup"><span data-stu-id="bb2ba-126">`false` - workstation</span></span><br/><span data-ttu-id="bb2ba-127">`true` — сервер</span><span class="sxs-lookup"><span data-stu-id="bb2ba-127">`true` - server</span></span> | <span data-ttu-id="bb2ba-128">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="bb2ba-128">.NET Core 1.0</span></span> |
| <span data-ttu-id="bb2ba-129">**Свойство MSBuild**</span><span class="sxs-lookup"><span data-stu-id="bb2ba-129">**MSBuild property**</span></span> | `ServerGarbageCollection` | <span data-ttu-id="bb2ba-130">`false` — рабочая станция</span><span class="sxs-lookup"><span data-stu-id="bb2ba-130">`false` - workstation</span></span><br/><span data-ttu-id="bb2ba-131">`true` — сервер</span><span class="sxs-lookup"><span data-stu-id="bb2ba-131">`true` - server</span></span> | <span data-ttu-id="bb2ba-132">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="bb2ba-132">.NET Core 1.0</span></span> |
| <span data-ttu-id="bb2ba-133">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="bb2ba-133">**Environment variable**</span></span> | `COMPlus_gcServer` | <span data-ttu-id="bb2ba-134">`0` — рабочая станция</span><span class="sxs-lookup"><span data-stu-id="bb2ba-134">`0` - workstation</span></span><br/><span data-ttu-id="bb2ba-135">`1` — сервер</span><span class="sxs-lookup"><span data-stu-id="bb2ba-135">`1` - server</span></span> | <span data-ttu-id="bb2ba-136">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="bb2ba-136">.NET Core 1.0</span></span> |
| <span data-ttu-id="bb2ba-137">**app.config для .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="bb2ba-137">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="bb2ba-138">GCServer</span><span class="sxs-lookup"><span data-stu-id="bb2ba-138">GCServer</span></span>](../../framework/configure-apps/file-schema/runtime/gcserver-element.md) | <span data-ttu-id="bb2ba-139">`false` — рабочая станция</span><span class="sxs-lookup"><span data-stu-id="bb2ba-139">`false` - workstation</span></span><br/><span data-ttu-id="bb2ba-140">`true` — сервер</span><span class="sxs-lookup"><span data-stu-id="bb2ba-140">`true` - server</span></span> |  |

### <a name="examples"></a><span data-ttu-id="bb2ba-141">Примеры</span><span class="sxs-lookup"><span data-stu-id="bb2ba-141">Examples</span></span>

<span data-ttu-id="bb2ba-142">Файл *runtimeconfig.json*</span><span class="sxs-lookup"><span data-stu-id="bb2ba-142">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Server": true
      }
   }
}
```

<span data-ttu-id="bb2ba-143">Файл проекта:</span><span class="sxs-lookup"><span data-stu-id="bb2ba-143">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ServerGarbageCollection>true</ServerGarbageCollection>
  </PropertyGroup>

</Project>
```

### <a name="systemgcconcurrentcomplus_gcconcurrent"></a><span data-ttu-id="bb2ba-144">System.GC.Concurrent/COMPlus_gcConcurrent</span><span class="sxs-lookup"><span data-stu-id="bb2ba-144">System.GC.Concurrent/COMPlus_gcConcurrent</span></span>

- <span data-ttu-id="bb2ba-145">Указывает, включена ли фоновая (параллельная) сборка мусора.</span><span class="sxs-lookup"><span data-stu-id="bb2ba-145">Configures whether background (concurrent) garbage collection is enabled.</span></span>
- <span data-ttu-id="bb2ba-146">По умолчанию: включено (`true`).</span><span class="sxs-lookup"><span data-stu-id="bb2ba-146">Default: Enabled (`true`).</span></span>
- <span data-ttu-id="bb2ba-147">Дополнительные сведения см. в статьях [Фоновая сборка мусора](../../standard/garbage-collection/fundamentals.md#background-workstation-garbage-collection) и [Фоновая сборка мусора сервера](../../standard/garbage-collection/fundamentals.md#background-server-garbage-collection).</span><span class="sxs-lookup"><span data-stu-id="bb2ba-147">For more information, see [Background garbage collection](../../standard/garbage-collection/fundamentals.md#background-workstation-garbage-collection) and [Background server garbage collection](../../standard/garbage-collection/fundamentals.md#background-server-garbage-collection).</span></span>

| | <span data-ttu-id="bb2ba-148">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="bb2ba-148">Setting name</span></span> | <span data-ttu-id="bb2ba-149">Значения</span><span class="sxs-lookup"><span data-stu-id="bb2ba-149">Values</span></span> | <span data-ttu-id="bb2ba-150">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="bb2ba-150">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="bb2ba-151">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="bb2ba-151">**runtimeconfig.json**</span></span> | `System.GC.Concurrent` | <span data-ttu-id="bb2ba-152">`true` —фоновая сборка мусора</span><span class="sxs-lookup"><span data-stu-id="bb2ba-152">`true` - background GC</span></span><br/><span data-ttu-id="bb2ba-153">`false` — непараллельная сборка мусора</span><span class="sxs-lookup"><span data-stu-id="bb2ba-153">`false` - non-concurrent GC</span></span> | <span data-ttu-id="bb2ba-154">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="bb2ba-154">.NET Core 1.0</span></span> |
| <span data-ttu-id="bb2ba-155">**Свойство MSBuild**</span><span class="sxs-lookup"><span data-stu-id="bb2ba-155">**MSBuild property**</span></span> | `ConcurrentGarbageCollection` | <span data-ttu-id="bb2ba-156">`true` —фоновая сборка мусора</span><span class="sxs-lookup"><span data-stu-id="bb2ba-156">`true` - background GC</span></span><br/><span data-ttu-id="bb2ba-157">`false` — непараллельная сборка мусора</span><span class="sxs-lookup"><span data-stu-id="bb2ba-157">`false` - non-concurrent GC</span></span> | <span data-ttu-id="bb2ba-158">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="bb2ba-158">.NET Core 1.0</span></span> |
| <span data-ttu-id="bb2ba-159">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="bb2ba-159">**Environment variable**</span></span> | `COMPlus_gcConcurrent` | <span data-ttu-id="bb2ba-160">`true` —фоновая сборка мусора</span><span class="sxs-lookup"><span data-stu-id="bb2ba-160">`true` - background GC</span></span><br/><span data-ttu-id="bb2ba-161">`false` — непараллельная сборка мусора</span><span class="sxs-lookup"><span data-stu-id="bb2ba-161">`false` - non-concurrent GC</span></span> | <span data-ttu-id="bb2ba-162">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="bb2ba-162">.NET Core 1.0</span></span> |
| <span data-ttu-id="bb2ba-163">**app.config для .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="bb2ba-163">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="bb2ba-164">gcConcurrent</span><span class="sxs-lookup"><span data-stu-id="bb2ba-164">gcConcurrent</span></span>](../../framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) | <span data-ttu-id="bb2ba-165">`true` —фоновая сборка мусора</span><span class="sxs-lookup"><span data-stu-id="bb2ba-165">`true` - background GC</span></span><br/><span data-ttu-id="bb2ba-166">`false` — непараллельная сборка мусора</span><span class="sxs-lookup"><span data-stu-id="bb2ba-166">`false` - non-concurrent GC</span></span> |  |

### <a name="examples"></a><span data-ttu-id="bb2ba-167">Примеры</span><span class="sxs-lookup"><span data-stu-id="bb2ba-167">Examples</span></span>

<span data-ttu-id="bb2ba-168">Файл *runtimeconfig.json*</span><span class="sxs-lookup"><span data-stu-id="bb2ba-168">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Concurrent": false
      }
   }
}
```

<span data-ttu-id="bb2ba-169">Файл проекта:</span><span class="sxs-lookup"><span data-stu-id="bb2ba-169">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ConcurrentGarbageCollection>false</ConcurrentGarbageCollection>
  </PropertyGroup>

</Project>
```

## <a name="manage-resource-usage"></a><span data-ttu-id="bb2ba-170">Управление использованием ресурсов</span><span class="sxs-lookup"><span data-stu-id="bb2ba-170">Manage resource usage</span></span>

<span data-ttu-id="bb2ba-171">Используйте параметры, описанные в этом разделе, для управления использованием памяти и ЦП в сборщике мусора.</span><span class="sxs-lookup"><span data-stu-id="bb2ba-171">Use the settings described in this section to manage the garbage collector's memory and processor usage.</span></span>

<span data-ttu-id="bb2ba-172">Дополнительные сведения о некоторых из этих параметров см. в записи блога о [компромиссе между сборкой мусора рабочей станции и сервера](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/).</span><span class="sxs-lookup"><span data-stu-id="bb2ba-172">For more information about some of these settings, see the [Middle ground between workstation and server GC](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/) blog entry.</span></span>

### <a name="systemgcheapcountcomplus_gcheapcount"></a><span data-ttu-id="bb2ba-173">System.GC.HeapCount/COMPlus_GCHeapCount</span><span class="sxs-lookup"><span data-stu-id="bb2ba-173">System.GC.HeapCount/COMPlus_GCHeapCount</span></span>

- <span data-ttu-id="bb2ba-174">Ограничивает число куч, создаваемых сборщиком мусора.</span><span class="sxs-lookup"><span data-stu-id="bb2ba-174">Limits the number of heaps created by the garbage collector.</span></span>
- <span data-ttu-id="bb2ba-175">Применяется только к сборке мусора сервера.</span><span class="sxs-lookup"><span data-stu-id="bb2ba-175">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="bb2ba-176">Если включено [сходство процессоров сборки мусора](#systemgcnoaffinitizecomplus_gcnoaffinitize), что используется по умолчанию, параметр счетчика куч реализует сходство `n` куч/потоков сборки мусора с первыми `n` процессорами.</span><span class="sxs-lookup"><span data-stu-id="bb2ba-176">If [GC processor affinity](#systemgcnoaffinitizecomplus_gcnoaffinitize) is enabled, which is the default, the heap count setting affinitizes `n` GC heaps/threads to the first `n` processors.</span></span> <span data-ttu-id="bb2ba-177">(Используйте параметры [сходства маски](#systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask) или [сходства диапазонов](#systemgcgcheapaffinitizerangescomplus_gcheapaffinitizeranges), чтобы указать, для каких именно процессоров следует реализовать сходство.)</span><span class="sxs-lookup"><span data-stu-id="bb2ba-177">(Use the [affinitize mask](#systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask) or [affinitize ranges](#systemgcgcheapaffinitizerangescomplus_gcheapaffinitizeranges) settings to specify exactly which processors to affinitize.)</span></span>
- <span data-ttu-id="bb2ba-178">Если [сходство процессоров сборки мусора](#systemgcnoaffinitizecomplus_gcnoaffinitize) отключено, этот параметр будет ограничивать количество куч сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="bb2ba-178">If [GC processor affinity](#systemgcnoaffinitizecomplus_gcnoaffinitize) is disabled, this setting limits the number of GC heaps.</span></span>
- <span data-ttu-id="bb2ba-179">Дополнительные сведения см. в [примечаниях по GCHeapCount](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md#remarks).</span><span class="sxs-lookup"><span data-stu-id="bb2ba-179">For more information, see the [GCHeapCount remarks](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md#remarks).</span></span>

| | <span data-ttu-id="bb2ba-180">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="bb2ba-180">Setting name</span></span> | <span data-ttu-id="bb2ba-181">Значения</span><span class="sxs-lookup"><span data-stu-id="bb2ba-181">Values</span></span> | <span data-ttu-id="bb2ba-182">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="bb2ba-182">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="bb2ba-183">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="bb2ba-183">**runtimeconfig.json**</span></span> | `System.GC.HeapCount` | <span data-ttu-id="bb2ba-184">*Десятичное значение*</span><span class="sxs-lookup"><span data-stu-id="bb2ba-184">*decimal value*</span></span> | <span data-ttu-id="bb2ba-185">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="bb2ba-185">.NET Core 3.0</span></span> |
| <span data-ttu-id="bb2ba-186">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="bb2ba-186">**Environment variable**</span></span> | `COMPlus_GCHeapCount` | <span data-ttu-id="bb2ba-187">*Шестнадцатеричное значение*</span><span class="sxs-lookup"><span data-stu-id="bb2ba-187">*hexadecimal value*</span></span> | <span data-ttu-id="bb2ba-188">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="bb2ba-188">.NET Core 3.0</span></span> |
| <span data-ttu-id="bb2ba-189">**app.config для .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="bb2ba-189">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="bb2ba-190">GCHeapCount</span><span class="sxs-lookup"><span data-stu-id="bb2ba-190">GCHeapCount</span></span>](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md) | <span data-ttu-id="bb2ba-191">*Десятичное значение*</span><span class="sxs-lookup"><span data-stu-id="bb2ba-191">*decimal value*</span></span> | <span data-ttu-id="bb2ba-192">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="bb2ba-192">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="bb2ba-193">Пример.</span><span class="sxs-lookup"><span data-stu-id="bb2ba-193">Example:</span></span>

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
> <span data-ttu-id="bb2ba-194">Если вы задаете параметр в *runtimeconfig.json*, укажите десятичное значение.</span><span class="sxs-lookup"><span data-stu-id="bb2ba-194">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="bb2ba-195">Если вы задаете параметр в виде переменной среды, укажите шестнадцатеричное значение.</span><span class="sxs-lookup"><span data-stu-id="bb2ba-195">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="bb2ba-196">Например, чтобы ограничить число куч значением 16, для JSON-файла нужно указать 16, а для переменной среды — 0x10 или 10.</span><span class="sxs-lookup"><span data-stu-id="bb2ba-196">For example, to limit the number of heaps to 16, the values would be 16 for the JSON file and 0x10 or 10 for the environment variable.</span></span>

### <a name="systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask"></a><span data-ttu-id="bb2ba-197">System.GC.HeapAffinitizeMask/COMPlus_GCHeapAffinitizeMask</span><span class="sxs-lookup"><span data-stu-id="bb2ba-197">System.GC.HeapAffinitizeMask/COMPlus_GCHeapAffinitizeMask</span></span>

- <span data-ttu-id="bb2ba-198">Указывает конкретные процессоры, которые должны использоваться потоками сборщика мусора.</span><span class="sxs-lookup"><span data-stu-id="bb2ba-198">Specifies the exact processors that garbage collector threads should use.</span></span>
- <span data-ttu-id="bb2ba-199">Если [сходство процессоров](#systemgcnoaffinitizecomplus_gcnoaffinitize) отключено, этот параметр игнорируется.</span><span class="sxs-lookup"><span data-stu-id="bb2ba-199">If [GC processor affinity](#systemgcnoaffinitizecomplus_gcnoaffinitize) is disabled, this setting is ignored.</span></span>
- <span data-ttu-id="bb2ba-200">Применяется только к сборке мусора сервера.</span><span class="sxs-lookup"><span data-stu-id="bb2ba-200">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="bb2ba-201">Это значение представляет собой битовую маску, которая определяет доступные процессу процессоры.</span><span class="sxs-lookup"><span data-stu-id="bb2ba-201">The value is a bit mask that defines the processors that are available to the process.</span></span> <span data-ttu-id="bb2ba-202">Например, десятичное значение 1023 (или шестнадцатеричное значение 0x3FF или 3FF, если вы используете переменную среды), равно 0011 1111 1111 в двоичной нотации.</span><span class="sxs-lookup"><span data-stu-id="bb2ba-202">For example, a decimal value of 1023 (or a hexadecimal value of 0x3FF or 3FF if you're using the environment variable) is 0011 1111 1111 in binary notation.</span></span> <span data-ttu-id="bb2ba-203">При этом будут использоваться первые 10 процессоров.</span><span class="sxs-lookup"><span data-stu-id="bb2ba-203">This specifies that the first 10 processors are to be used.</span></span> <span data-ttu-id="bb2ba-204">Чтобы указать следующие 10 процессоров, то есть процессоры 10–19, задайте десятичное значение 1047552 (или шестнадцатеричное значение 0xFFC00 или FFC00), которое эквивалентно двоичному значению 1111 1111 1100 0000 0000.</span><span class="sxs-lookup"><span data-stu-id="bb2ba-204">To specify the next 10 processors, that is, processors 10-19, specify a decimal value of 1047552 (or a hexadecimal value of 0xFFC00 or FFC00), which is equivalent to a binary value of 1111 1111 1100 0000 0000.</span></span>

| | <span data-ttu-id="bb2ba-205">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="bb2ba-205">Setting name</span></span> | <span data-ttu-id="bb2ba-206">Значения</span><span class="sxs-lookup"><span data-stu-id="bb2ba-206">Values</span></span> | <span data-ttu-id="bb2ba-207">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="bb2ba-207">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="bb2ba-208">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="bb2ba-208">**runtimeconfig.json**</span></span> | `System.GC.HeapAffinitizeMask` | <span data-ttu-id="bb2ba-209">*Десятичное значение*</span><span class="sxs-lookup"><span data-stu-id="bb2ba-209">*decimal value*</span></span> | <span data-ttu-id="bb2ba-210">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="bb2ba-210">.NET Core 3.0</span></span> |
| <span data-ttu-id="bb2ba-211">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="bb2ba-211">**Environment variable**</span></span> | `COMPlus_GCHeapAffinitizeMask` | <span data-ttu-id="bb2ba-212">*Шестнадцатеричное значение*</span><span class="sxs-lookup"><span data-stu-id="bb2ba-212">*hexadecimal value*</span></span> | <span data-ttu-id="bb2ba-213">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="bb2ba-213">.NET Core 3.0</span></span> |
| <span data-ttu-id="bb2ba-214">**app.config для .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="bb2ba-214">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="bb2ba-215">GCHeapAffinitizeMask</span><span class="sxs-lookup"><span data-stu-id="bb2ba-215">GCHeapAffinitizeMask</span></span>](../../framework/configure-apps/file-schema/runtime/gcheapaffinitizemask-element.md) | <span data-ttu-id="bb2ba-216">*Десятичное значение*</span><span class="sxs-lookup"><span data-stu-id="bb2ba-216">*decimal value*</span></span> | <span data-ttu-id="bb2ba-217">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="bb2ba-217">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="bb2ba-218">Пример.</span><span class="sxs-lookup"><span data-stu-id="bb2ba-218">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.HeapAffinitizeMask": 1023
      }
   }
}
```

### <a name="systemgcgcheapaffinitizerangescomplus_gcheapaffinitizeranges"></a><span data-ttu-id="bb2ba-219">System.GC.GCHeapAffinitizeRanges/COMPlus_GCHeapAffinitizeRanges</span><span class="sxs-lookup"><span data-stu-id="bb2ba-219">System.GC.GCHeapAffinitizeRanges/COMPlus_GCHeapAffinitizeRanges</span></span>

- <span data-ttu-id="bb2ba-220">Указывает список процессоров, используемых для потоков сборщика мусора.</span><span class="sxs-lookup"><span data-stu-id="bb2ba-220">Specifies the list of processors to use for garbage collector threads.</span></span>
- <span data-ttu-id="bb2ba-221">Этот параметр аналогичен [System.GC.HeapAffinitizeMask](#systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask), за исключением того, что он позволяет указать больше 64 процессоров.</span><span class="sxs-lookup"><span data-stu-id="bb2ba-221">This setting is similar to [System.GC.HeapAffinitizeMask](#systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask), except it allows you to specify more than 64 processors.</span></span>
- <span data-ttu-id="bb2ba-222">Для операционных систем Windows добавьте к номеру или диапазону процессоров префикс в виде соответствующей [группы ЦП](/windows/win32/procthread/processor-groups), например "0:1-10,0:12,1:50-52,1:70".</span><span class="sxs-lookup"><span data-stu-id="bb2ba-222">For Windows operating systems, prefix the processor number or range with the corresponding [CPU group](/windows/win32/procthread/processor-groups), for example, "0:1-10,0:12,1:50-52,1:70".</span></span>
- <span data-ttu-id="bb2ba-223">Если [сходство процессоров](#systemgcnoaffinitizecomplus_gcnoaffinitize) отключено, этот параметр игнорируется.</span><span class="sxs-lookup"><span data-stu-id="bb2ba-223">If [GC processor affinity](#systemgcnoaffinitizecomplus_gcnoaffinitize) is disabled, this setting is ignored.</span></span>
- <span data-ttu-id="bb2ba-224">Применяется только к сборке мусора сервера.</span><span class="sxs-lookup"><span data-stu-id="bb2ba-224">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="bb2ba-225">Дополнительные сведения см. в записи об [улучшении конфигурации ЦП для сборки мусора на компьютерах, имеющих более 64 ЦП](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/), в блоге Майони Стивенс (Maoni Stephens).</span><span class="sxs-lookup"><span data-stu-id="bb2ba-225">For more information, see [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) on Maoni Stephens' blog.</span></span>

| | <span data-ttu-id="bb2ba-226">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="bb2ba-226">Setting name</span></span> | <span data-ttu-id="bb2ba-227">Значения</span><span class="sxs-lookup"><span data-stu-id="bb2ba-227">Values</span></span> | <span data-ttu-id="bb2ba-228">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="bb2ba-228">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="bb2ba-229">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="bb2ba-229">**runtimeconfig.json**</span></span> | `System.GC.GCHeapAffinitizeRanges` | <span data-ttu-id="bb2ba-230">Разделенный запятыми список номеров процессоров или диапазонов номеров процессоров.</span><span class="sxs-lookup"><span data-stu-id="bb2ba-230">Comma-separated list of processor numbers or ranges of processor numbers.</span></span><br/><span data-ttu-id="bb2ba-231">Пример для Unix: "1-10,12,50-52,70"</span><span class="sxs-lookup"><span data-stu-id="bb2ba-231">Unix example: "1-10,12,50-52,70"</span></span><br/><span data-ttu-id="bb2ba-232">Пример для Windows: "0:1-10,0:12,1:50-52,1:70"</span><span class="sxs-lookup"><span data-stu-id="bb2ba-232">Windows example: "0:1-10,0:12,1:50-52,1:70"</span></span> | <span data-ttu-id="bb2ba-233">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="bb2ba-233">.NET Core 3.0</span></span> |
| <span data-ttu-id="bb2ba-234">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="bb2ba-234">**Environment variable**</span></span> | `COMPlus_GCHeapAffinitizeRanges` | <span data-ttu-id="bb2ba-235">Разделенный запятыми список номеров процессоров или диапазонов номеров процессоров.</span><span class="sxs-lookup"><span data-stu-id="bb2ba-235">Comma-separated list of processor numbers or ranges of processor numbers.</span></span><br/><span data-ttu-id="bb2ba-236">Пример для Unix: "1-10,12,50-52,70"</span><span class="sxs-lookup"><span data-stu-id="bb2ba-236">Unix example: "1-10,12,50-52,70"</span></span><br/><span data-ttu-id="bb2ba-237">Пример для Windows: "0:1-10,0:12,1:50-52,1:70"</span><span class="sxs-lookup"><span data-stu-id="bb2ba-237">Windows example: "0:1-10,0:12,1:50-52,1:70"</span></span> | <span data-ttu-id="bb2ba-238">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="bb2ba-238">.NET Core 3.0</span></span> |

<span data-ttu-id="bb2ba-239">Пример.</span><span class="sxs-lookup"><span data-stu-id="bb2ba-239">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.GCHeapAffinitizeRanges": "0:1-10,0:12,1:50-52,1:70"
      }
   }
}
```

### <a name="complus_gccpugroup"></a><span data-ttu-id="bb2ba-240">COMPlus_GCCpuGroup</span><span class="sxs-lookup"><span data-stu-id="bb2ba-240">COMPlus_GCCpuGroup</span></span>

- <span data-ttu-id="bb2ba-241">Указывает, использует ли сборщик мусора [группы ЦП](/windows/win32/procthread/processor-groups).</span><span class="sxs-lookup"><span data-stu-id="bb2ba-241">Configures whether the garbage collector uses [CPU groups](/windows/win32/procthread/processor-groups) or not.</span></span>

  <span data-ttu-id="bb2ba-242">Когда 64-разрядный компьютер с Windows имеет несколько групп ЦП, то есть доступно более 64 процессоров, включение этого элемента расширяет действие сборки мусора на все группы ЦП.</span><span class="sxs-lookup"><span data-stu-id="bb2ba-242">When a 64-bit Windows computer has multiple CPU groups, that is, there are more than 64 processors, enabling this element extends garbage collection across all CPU groups.</span></span> <span data-ttu-id="bb2ba-243">Сборщик мусора использует все ядра для создания и балансировки куч.</span><span class="sxs-lookup"><span data-stu-id="bb2ba-243">The garbage collector uses all cores to create and balance heaps.</span></span>

- <span data-ttu-id="bb2ba-244">Применяется только к сборке мусора сервера в 64-разрядных операционных системах Windows.</span><span class="sxs-lookup"><span data-stu-id="bb2ba-244">Applies to server garbage collection on 64-bit Windows operation systems only.</span></span>
- <span data-ttu-id="bb2ba-245">По умолчанию: отключено (`0`).</span><span class="sxs-lookup"><span data-stu-id="bb2ba-245">Default: Disabled (`0`).</span></span>
- <span data-ttu-id="bb2ba-246">Дополнительные сведения см. в записи об [улучшении конфигурации ЦП для сборки мусора на компьютерах, имеющих более 64 ЦП](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/), в блоге Майони Стивенс (Maoni Stephens).</span><span class="sxs-lookup"><span data-stu-id="bb2ba-246">For more information, see [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) on Maoni Stephens' blog.</span></span>

| | <span data-ttu-id="bb2ba-247">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="bb2ba-247">Setting name</span></span> | <span data-ttu-id="bb2ba-248">Значения</span><span class="sxs-lookup"><span data-stu-id="bb2ba-248">Values</span></span> | <span data-ttu-id="bb2ba-249">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="bb2ba-249">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="bb2ba-250">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="bb2ba-250">**runtimeconfig.json**</span></span> | <span data-ttu-id="bb2ba-251">Н/Д</span><span class="sxs-lookup"><span data-stu-id="bb2ba-251">N/A</span></span> | <span data-ttu-id="bb2ba-252">Н/Д</span><span class="sxs-lookup"><span data-stu-id="bb2ba-252">N/A</span></span> | <span data-ttu-id="bb2ba-253">Н/Д</span><span class="sxs-lookup"><span data-stu-id="bb2ba-253">N/A</span></span> |
| <span data-ttu-id="bb2ba-254">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="bb2ba-254">**Environment variable**</span></span> | `COMPlus_GCCpuGroup` | <span data-ttu-id="bb2ba-255">`0` — отключено</span><span class="sxs-lookup"><span data-stu-id="bb2ba-255">`0` - disabled</span></span><br/><span data-ttu-id="bb2ba-256">`1` — включено</span><span class="sxs-lookup"><span data-stu-id="bb2ba-256">`1` - enabled</span></span> | <span data-ttu-id="bb2ba-257">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="bb2ba-257">.NET Core 1.0</span></span> |
| <span data-ttu-id="bb2ba-258">**app.config для .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="bb2ba-258">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="bb2ba-259">GCCpuGroup</span><span class="sxs-lookup"><span data-stu-id="bb2ba-259">GCCpuGroup</span></span>](../../framework/configure-apps/file-schema/runtime/gccpugroup-element.md) | <span data-ttu-id="bb2ba-260">`false` — отключено</span><span class="sxs-lookup"><span data-stu-id="bb2ba-260">`false` - disabled</span></span><br/><span data-ttu-id="bb2ba-261">`true` — включено</span><span class="sxs-lookup"><span data-stu-id="bb2ba-261">`true` - enabled</span></span> |  |

> [!NOTE]
> <span data-ttu-id="bb2ba-262">Чтобы настроить среду CLR для распределения потоков из пула потоков по всем группам ЦП, включите параметр [Элемент Thread_UseAllCpuGroups](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md).</span><span class="sxs-lookup"><span data-stu-id="bb2ba-262">To configure the common language runtime (CLR) to also distribute threads from the thread pool across all CPU groups, enable the [Thread_UseAllCpuGroups element](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md) option.</span></span> <span data-ttu-id="bb2ba-263">Для приложений .NET Core этот параметр можно включить, задав для переменной среды `COMPlus_Thread_UseAllCpuGroups` значение `1`.</span><span class="sxs-lookup"><span data-stu-id="bb2ba-263">For .NET Core apps, you can enable this option by setting the value of the `COMPlus_Thread_UseAllCpuGroups` environment variable to `1`.</span></span>

### <a name="systemgcnoaffinitizecomplus_gcnoaffinitize"></a><span data-ttu-id="bb2ba-264">System.GC.NoAffinitize/COMPlus_GCNoAffinitize</span><span class="sxs-lookup"><span data-stu-id="bb2ba-264">System.GC.NoAffinitize/COMPlus_GCNoAffinitize</span></span>

- <span data-ttu-id="bb2ba-265">Указывает, следует ли *реализовать сходство* потоков сборки мусора с процессорами.</span><span class="sxs-lookup"><span data-stu-id="bb2ba-265">Specifies whether to *affinitize* garbage collection threads with processors.</span></span> <span data-ttu-id="bb2ba-266">Реализация сходства потока сборки мусора означает, что он может выполняться только на определенном ЦП.</span><span class="sxs-lookup"><span data-stu-id="bb2ba-266">To affinitize a GC thread means that it can only run on its specific CPU.</span></span> <span data-ttu-id="bb2ba-267">Куча создается для каждого потока сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="bb2ba-267">A heap is created for each GC thread.</span></span>
- <span data-ttu-id="bb2ba-268">Применяется только к сборке мусора сервера.</span><span class="sxs-lookup"><span data-stu-id="bb2ba-268">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="bb2ba-269">По умолчанию: реализация сходства потоков сборки мусора с процессорами (`false`).</span><span class="sxs-lookup"><span data-stu-id="bb2ba-269">Default: Affinitize garbage collection threads with processors (`false`).</span></span>

| | <span data-ttu-id="bb2ba-270">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="bb2ba-270">Setting name</span></span> | <span data-ttu-id="bb2ba-271">Значения</span><span class="sxs-lookup"><span data-stu-id="bb2ba-271">Values</span></span> | <span data-ttu-id="bb2ba-272">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="bb2ba-272">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="bb2ba-273">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="bb2ba-273">**runtimeconfig.json**</span></span> | `System.GC.NoAffinitize` | <span data-ttu-id="bb2ba-274">`false` — реализовать сходство</span><span class="sxs-lookup"><span data-stu-id="bb2ba-274">`false` - affinitize</span></span><br/><span data-ttu-id="bb2ba-275">`true` — не реализовывать сходство</span><span class="sxs-lookup"><span data-stu-id="bb2ba-275">`true` - don't affinitize</span></span> | <span data-ttu-id="bb2ba-276">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="bb2ba-276">.NET Core 3.0</span></span> |
| <span data-ttu-id="bb2ba-277">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="bb2ba-277">**Environment variable**</span></span> | `COMPlus_GCNoAffinitize` | <span data-ttu-id="bb2ba-278">`0` — реализовать сходство</span><span class="sxs-lookup"><span data-stu-id="bb2ba-278">`0` - affinitize</span></span><br/><span data-ttu-id="bb2ba-279">`1` — не реализовывать сходство</span><span class="sxs-lookup"><span data-stu-id="bb2ba-279">`1` - don't affinitize</span></span> | <span data-ttu-id="bb2ba-280">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="bb2ba-280">.NET Core 3.0</span></span> |
| <span data-ttu-id="bb2ba-281">**app.config для .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="bb2ba-281">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="bb2ba-282">GCNoAffinitize</span><span class="sxs-lookup"><span data-stu-id="bb2ba-282">GCNoAffinitize</span></span>](../../framework/configure-apps/file-schema/runtime/gcnoaffinitize-element.md) | <span data-ttu-id="bb2ba-283">`false` — реализовать сходство</span><span class="sxs-lookup"><span data-stu-id="bb2ba-283">`false` - affinitize</span></span><br/><span data-ttu-id="bb2ba-284">`true` — не реализовывать сходство</span><span class="sxs-lookup"><span data-stu-id="bb2ba-284">`true` - don't affinitize</span></span> | <span data-ttu-id="bb2ba-285">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="bb2ba-285">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="bb2ba-286">Пример.</span><span class="sxs-lookup"><span data-stu-id="bb2ba-286">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.NoAffinitize": true
      }
   }
}
```

### <a name="systemgcheaphardlimitcomplus_gcheaphardlimit"></a><span data-ttu-id="bb2ba-287">System.GC.HeapHardLimit/COMPlus_GCHeapHardLimit</span><span class="sxs-lookup"><span data-stu-id="bb2ba-287">System.GC.HeapHardLimit/COMPlus_GCHeapHardLimit</span></span>

- <span data-ttu-id="bb2ba-288">Указывает максимальный размер фиксации в байтах для кучи сборки мусора и учета сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="bb2ba-288">Specifies the maximum commit size, in bytes, for the GC heap and GC bookkeeping.</span></span>
- <span data-ttu-id="bb2ba-289">Этот параметр применим только к 64-разрядным компьютерам.</span><span class="sxs-lookup"><span data-stu-id="bb2ba-289">This setting only applies to 64-bit computers.</span></span>
- <span data-ttu-id="bb2ba-290">Значение по умолчанию, которое применяется только в определенных случаях, не превышает 20 МБ или 75 % предельного объема памяти в контейнере.</span><span class="sxs-lookup"><span data-stu-id="bb2ba-290">The default value, which only applies in certain cases, is the lesser of 20 MB or 75% of the memory limit on the container.</span></span> <span data-ttu-id="bb2ba-291">Значение по умолчанию применяется, если:</span><span class="sxs-lookup"><span data-stu-id="bb2ba-291">The default value applies if:</span></span>

  - <span data-ttu-id="bb2ba-292">процесс выполняется в контейнере с заданным предельным объемом памяти;</span><span class="sxs-lookup"><span data-stu-id="bb2ba-292">The process is running inside a container that has a specified memory limit.</span></span>
  - <span data-ttu-id="bb2ba-293">параметр [System.GC.HeapHardLimitPercent](#systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent) не задан.</span><span class="sxs-lookup"><span data-stu-id="bb2ba-293">[System.GC.HeapHardLimitPercent](#systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent) is not set.</span></span>

| | <span data-ttu-id="bb2ba-294">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="bb2ba-294">Setting name</span></span> | <span data-ttu-id="bb2ba-295">Значения</span><span class="sxs-lookup"><span data-stu-id="bb2ba-295">Values</span></span> | <span data-ttu-id="bb2ba-296">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="bb2ba-296">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="bb2ba-297">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="bb2ba-297">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimit` | <span data-ttu-id="bb2ba-298">*Десятичное значение*</span><span class="sxs-lookup"><span data-stu-id="bb2ba-298">*decimal value*</span></span> | <span data-ttu-id="bb2ba-299">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="bb2ba-299">.NET Core 3.0</span></span> |
| <span data-ttu-id="bb2ba-300">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="bb2ba-300">**Environment variable**</span></span> | `COMPlus_GCHeapHardLimit` | <span data-ttu-id="bb2ba-301">*Шестнадцатеричное значение*</span><span class="sxs-lookup"><span data-stu-id="bb2ba-301">*hexadecimal value*</span></span> | <span data-ttu-id="bb2ba-302">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="bb2ba-302">.NET Core 3.0</span></span> |

<span data-ttu-id="bb2ba-303">Пример.</span><span class="sxs-lookup"><span data-stu-id="bb2ba-303">Example:</span></span>

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
> <span data-ttu-id="bb2ba-304">Если вы задаете параметр в *runtimeconfig.json*, укажите десятичное значение.</span><span class="sxs-lookup"><span data-stu-id="bb2ba-304">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="bb2ba-305">Если вы задаете параметр в виде переменной среды, укажите шестнадцатеричное значение.</span><span class="sxs-lookup"><span data-stu-id="bb2ba-305">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="bb2ba-306">Например, чтобы задать для куч жесткое ограничение в 200 мебибайт (Миб), для JSON-файла нужно указать значение 209715200, а для переменной среды — значение 0xC800000 или C800000.</span><span class="sxs-lookup"><span data-stu-id="bb2ba-306">For example, to specify a heap hard limit of 200 mebibytes (MiB), the values would be 209715200 for the JSON file and 0xC800000 or C800000 for the environment variable.</span></span>

### <a name="systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent"></a><span data-ttu-id="bb2ba-307">System.GC.HeapHardLimitPercent/COMPlus_GCHeapHardLimitPercent</span><span class="sxs-lookup"><span data-stu-id="bb2ba-307">System.GC.HeapHardLimitPercent/COMPlus_GCHeapHardLimitPercent</span></span>

- <span data-ttu-id="bb2ba-308">Указывает допустимое использование кучи сборки мусора в процентах от общего объема физической памяти.</span><span class="sxs-lookup"><span data-stu-id="bb2ba-308">Specifies the allowable GC heap usage as a percentage of the total physical memory.</span></span>
- <span data-ttu-id="bb2ba-309">Если также задан параметр [System.GC.HeapHardLimit](#systemgcheaphardlimitcomplus_gcheaphardlimit), этот параметр игнорируется.</span><span class="sxs-lookup"><span data-stu-id="bb2ba-309">If [System.GC.HeapHardLimit](#systemgcheaphardlimitcomplus_gcheaphardlimit) is also set, this setting is ignored.</span></span>
- <span data-ttu-id="bb2ba-310">Этот параметр применим только к 64-разрядным компьютерам.</span><span class="sxs-lookup"><span data-stu-id="bb2ba-310">This setting only applies to 64-bit computers.</span></span>
- <span data-ttu-id="bb2ba-311">Если процесс выполняется в контейнере с заданным предельным объемом памяти, процентная доля вычисляется как процент от этого объема памяти.</span><span class="sxs-lookup"><span data-stu-id="bb2ba-311">If the process is running inside a container that has a specified memory limit, the percentage is calculated as a percentage of that memory limit.</span></span>
- <span data-ttu-id="bb2ba-312">Значение по умолчанию, которое применяется только в определенных случаях, не превышает 20 МБ или 75 % предельного объема памяти в контейнере.</span><span class="sxs-lookup"><span data-stu-id="bb2ba-312">The default value, which only applies in certain cases, is the lesser of 20 MB or 75% of the memory limit on the container.</span></span> <span data-ttu-id="bb2ba-313">Значение по умолчанию применяется, если:</span><span class="sxs-lookup"><span data-stu-id="bb2ba-313">The default value applies if:</span></span>

  - <span data-ttu-id="bb2ba-314">процесс выполняется в контейнере с заданным предельным объемом памяти;</span><span class="sxs-lookup"><span data-stu-id="bb2ba-314">The process is running inside a container that has a specified memory limit.</span></span>
  - <span data-ttu-id="bb2ba-315">параметр [System.GC.HeapHardLimit](#systemgcheaphardlimitcomplus_gcheaphardlimit) не задан.</span><span class="sxs-lookup"><span data-stu-id="bb2ba-315">[System.GC.HeapHardLimit](#systemgcheaphardlimitcomplus_gcheaphardlimit) is not set.</span></span>

| | <span data-ttu-id="bb2ba-316">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="bb2ba-316">Setting name</span></span> | <span data-ttu-id="bb2ba-317">Значения</span><span class="sxs-lookup"><span data-stu-id="bb2ba-317">Values</span></span> | <span data-ttu-id="bb2ba-318">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="bb2ba-318">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="bb2ba-319">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="bb2ba-319">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimitPercent` | <span data-ttu-id="bb2ba-320">*Десятичное значение*</span><span class="sxs-lookup"><span data-stu-id="bb2ba-320">*decimal value*</span></span> | <span data-ttu-id="bb2ba-321">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="bb2ba-321">.NET Core 3.0</span></span> |
| <span data-ttu-id="bb2ba-322">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="bb2ba-322">**Environment variable**</span></span> | `COMPlus_GCHeapHardLimitPercent` | <span data-ttu-id="bb2ba-323">*Шестнадцатеричное значение*</span><span class="sxs-lookup"><span data-stu-id="bb2ba-323">*hexadecimal value*</span></span> | <span data-ttu-id="bb2ba-324">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="bb2ba-324">.NET Core 3.0</span></span> |

<span data-ttu-id="bb2ba-325">Пример.</span><span class="sxs-lookup"><span data-stu-id="bb2ba-325">Example:</span></span>

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
> <span data-ttu-id="bb2ba-326">Если вы задаете параметр в *runtimeconfig.json*, укажите десятичное значение.</span><span class="sxs-lookup"><span data-stu-id="bb2ba-326">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="bb2ba-327">Если вы задаете параметр в виде переменной среды, укажите шестнадцатеричное значение.</span><span class="sxs-lookup"><span data-stu-id="bb2ba-327">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="bb2ba-328">Например, чтобы ограничить использование кучи значением 30 %, для JSON-файла нужно указать 30, а для переменной среды — 0x1E или 1E.</span><span class="sxs-lookup"><span data-stu-id="bb2ba-328">For example, to limit the heap usage to 30%, the values would be 30 for the JSON file and 0x1E or 1E for the environment variable.</span></span>

### <a name="systemgcretainvmcomplus_gcretainvm"></a><span data-ttu-id="bb2ba-329">System.GC.RetainVM/COMPlus_GCRetainVM</span><span class="sxs-lookup"><span data-stu-id="bb2ba-329">System.GC.RetainVM/COMPlus_GCRetainVM</span></span>

- <span data-ttu-id="bb2ba-330">Настраивает, будут ли удаляемые сегменты помещаться в список ожидания для будущего использования или возвращаться операционной системе (ОС).</span><span class="sxs-lookup"><span data-stu-id="bb2ba-330">Configures whether segments that should be deleted are put on a standby list for future use or are released back to the operating system (OS).</span></span>
- <span data-ttu-id="bb2ba-331">По умолчанию: возвращение сегментов операционной системе (`false`).</span><span class="sxs-lookup"><span data-stu-id="bb2ba-331">Default: Release segments back to the operating system (`false`).</span></span>

| | <span data-ttu-id="bb2ba-332">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="bb2ba-332">Setting name</span></span> | <span data-ttu-id="bb2ba-333">Значения</span><span class="sxs-lookup"><span data-stu-id="bb2ba-333">Values</span></span> | <span data-ttu-id="bb2ba-334">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="bb2ba-334">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="bb2ba-335">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="bb2ba-335">**runtimeconfig.json**</span></span> | `System.GC.RetainVM` | <span data-ttu-id="bb2ba-336">`false` — возвращение операционной системе</span><span class="sxs-lookup"><span data-stu-id="bb2ba-336">`false` - release to OS</span></span><br/><span data-ttu-id="bb2ba-337">`true` — помещение в режим ожидания</span><span class="sxs-lookup"><span data-stu-id="bb2ba-337">`true` - put on standby</span></span> | <span data-ttu-id="bb2ba-338">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="bb2ba-338">.NET Core 1.0</span></span> |
| <span data-ttu-id="bb2ba-339">**Свойство MSBuild**</span><span class="sxs-lookup"><span data-stu-id="bb2ba-339">**MSBuild property**</span></span> | `RetainVMGarbageCollection` | <span data-ttu-id="bb2ba-340">`false` — возвращение операционной системе</span><span class="sxs-lookup"><span data-stu-id="bb2ba-340">`false` - release to OS</span></span><br/><span data-ttu-id="bb2ba-341">`true` — помещение в режим ожидания</span><span class="sxs-lookup"><span data-stu-id="bb2ba-341">`true` - put on standby</span></span> | <span data-ttu-id="bb2ba-342">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="bb2ba-342">.NET Core 1.0</span></span> |
| <span data-ttu-id="bb2ba-343">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="bb2ba-343">**Environment variable**</span></span> | `COMPlus_GCRetainVM` | <span data-ttu-id="bb2ba-344">`0` — возвращение операционной системе</span><span class="sxs-lookup"><span data-stu-id="bb2ba-344">`0` - release to OS</span></span><br/><span data-ttu-id="bb2ba-345">`1` — помещение в режим ожидания</span><span class="sxs-lookup"><span data-stu-id="bb2ba-345">`1` - put on standby</span></span> | <span data-ttu-id="bb2ba-346">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="bb2ba-346">.NET Core 1.0</span></span> |

### <a name="examples"></a><span data-ttu-id="bb2ba-347">Примеры</span><span class="sxs-lookup"><span data-stu-id="bb2ba-347">Examples</span></span>

<span data-ttu-id="bb2ba-348">Файл *runtimeconfig.json*</span><span class="sxs-lookup"><span data-stu-id="bb2ba-348">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.RetainVM": true
      }
   }
}
```

<span data-ttu-id="bb2ba-349">Файл проекта:</span><span class="sxs-lookup"><span data-stu-id="bb2ba-349">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <RetainVMGarbageCollection>true</RetainVMGarbageCollection>
  </PropertyGroup>

</Project>
```

## <a name="large-pages"></a><span data-ttu-id="bb2ba-350">Большие страницы</span><span class="sxs-lookup"><span data-stu-id="bb2ba-350">Large pages</span></span>

### <a name="complus_gclargepages"></a><span data-ttu-id="bb2ba-351">COMPlus_GCLargePages</span><span class="sxs-lookup"><span data-stu-id="bb2ba-351">COMPlus_GCLargePages</span></span>

- <span data-ttu-id="bb2ba-352">Указывает, следует ли использовать большие страницы, когда задано жесткое ограничение куч.</span><span class="sxs-lookup"><span data-stu-id="bb2ba-352">Specifies whether large pages should be used when a heap hard limit is set.</span></span>
- <span data-ttu-id="bb2ba-353">По умолчанию: отключено (`0`).</span><span class="sxs-lookup"><span data-stu-id="bb2ba-353">Default: Disabled (`0`).</span></span>
- <span data-ttu-id="bb2ba-354">Это экспериментальный параметр.</span><span class="sxs-lookup"><span data-stu-id="bb2ba-354">This is an experimental setting.</span></span>

| | <span data-ttu-id="bb2ba-355">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="bb2ba-355">Setting name</span></span> | <span data-ttu-id="bb2ba-356">Значения</span><span class="sxs-lookup"><span data-stu-id="bb2ba-356">Values</span></span> | <span data-ttu-id="bb2ba-357">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="bb2ba-357">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="bb2ba-358">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="bb2ba-358">**runtimeconfig.json**</span></span> | <span data-ttu-id="bb2ba-359">Н/Д</span><span class="sxs-lookup"><span data-stu-id="bb2ba-359">N/A</span></span> | <span data-ttu-id="bb2ba-360">Н/Д</span><span class="sxs-lookup"><span data-stu-id="bb2ba-360">N/A</span></span> | <span data-ttu-id="bb2ba-361">Н/Д</span><span class="sxs-lookup"><span data-stu-id="bb2ba-361">N/A</span></span> |
| <span data-ttu-id="bb2ba-362">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="bb2ba-362">**Environment variable**</span></span> | `COMPlus_GCLargePages` | <span data-ttu-id="bb2ba-363">`0` — отключено</span><span class="sxs-lookup"><span data-stu-id="bb2ba-363">`0` - disabled</span></span><br/><span data-ttu-id="bb2ba-364">`1` — включено</span><span class="sxs-lookup"><span data-stu-id="bb2ba-364">`1` - enabled</span></span> | <span data-ttu-id="bb2ba-365">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="bb2ba-365">.NET Core 3.0</span></span> |

## <a name="large-objects"></a><span data-ttu-id="bb2ba-366">Большие объекты</span><span class="sxs-lookup"><span data-stu-id="bb2ba-366">Large objects</span></span>

### <a name="complus_gcallowverylargeobjects"></a><span data-ttu-id="bb2ba-367">COMPlus_gcAllowVeryLargeObjects</span><span class="sxs-lookup"><span data-stu-id="bb2ba-367">COMPlus_gcAllowVeryLargeObjects</span></span>

- <span data-ttu-id="bb2ba-368">Настраивает для сборщика мусора на 64-разрядных платформах поддержку массивов, размер которых превышает 2 гигабайта (ГБ).</span><span class="sxs-lookup"><span data-stu-id="bb2ba-368">Configures garbage collector support on 64-bit platforms for arrays that are greater than 2 gigabytes (GB) in total size.</span></span>
- <span data-ttu-id="bb2ba-369">По умолчанию: включено (`1`).</span><span class="sxs-lookup"><span data-stu-id="bb2ba-369">Default: Enabled (`1`).</span></span>
- <span data-ttu-id="bb2ba-370">В будущей версии .NET этот параметр может быть объявлен устаревшим.</span><span class="sxs-lookup"><span data-stu-id="bb2ba-370">This option may become obsolete in a future version of .NET.</span></span>

| | <span data-ttu-id="bb2ba-371">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="bb2ba-371">Setting name</span></span> | <span data-ttu-id="bb2ba-372">Значения</span><span class="sxs-lookup"><span data-stu-id="bb2ba-372">Values</span></span> | <span data-ttu-id="bb2ba-373">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="bb2ba-373">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="bb2ba-374">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="bb2ba-374">**runtimeconfig.json**</span></span> | <span data-ttu-id="bb2ba-375">Н/Д</span><span class="sxs-lookup"><span data-stu-id="bb2ba-375">N/A</span></span> | <span data-ttu-id="bb2ba-376">Н/Д</span><span class="sxs-lookup"><span data-stu-id="bb2ba-376">N/A</span></span> | <span data-ttu-id="bb2ba-377">Н/Д</span><span class="sxs-lookup"><span data-stu-id="bb2ba-377">N/A</span></span> |
| <span data-ttu-id="bb2ba-378">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="bb2ba-378">**Environment variable**</span></span> | `COMPlus_gcAllowVeryLargeObjects` | <span data-ttu-id="bb2ba-379">`1` — включено</span><span class="sxs-lookup"><span data-stu-id="bb2ba-379">`1` - enabled</span></span><br/> <span data-ttu-id="bb2ba-380">`0` — отключено</span><span class="sxs-lookup"><span data-stu-id="bb2ba-380">`0` - disabled</span></span> | <span data-ttu-id="bb2ba-381">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="bb2ba-381">.NET Core 1.0</span></span> |
| <span data-ttu-id="bb2ba-382">**app.config для .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="bb2ba-382">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="bb2ba-383">gcAllowVeryLargeObjects</span><span class="sxs-lookup"><span data-stu-id="bb2ba-383">gcAllowVeryLargeObjects</span></span>](../../framework/configure-apps/file-schema/runtime/gcallowverylargeobjects-element.md) | <span data-ttu-id="bb2ba-384">`1` — включено</span><span class="sxs-lookup"><span data-stu-id="bb2ba-384">`1` - enabled</span></span><br/> <span data-ttu-id="bb2ba-385">`0` — отключено</span><span class="sxs-lookup"><span data-stu-id="bb2ba-385">`0` - disabled</span></span> | <span data-ttu-id="bb2ba-386">.NET Framework 4,5</span><span class="sxs-lookup"><span data-stu-id="bb2ba-386">.NET Framework 4.5</span></span> |

## <a name="large-object-heap-threshold"></a><span data-ttu-id="bb2ba-387">Пороговое значение кучи больших объектов</span><span class="sxs-lookup"><span data-stu-id="bb2ba-387">Large object heap threshold</span></span>

### <a name="systemgclohthresholdcomplus_gclohthreshold"></a><span data-ttu-id="bb2ba-388">System.GC.LOHThreshold/COMPlus_GCLOHThreshold</span><span class="sxs-lookup"><span data-stu-id="bb2ba-388">System.GC.LOHThreshold/COMPlus_GCLOHThreshold</span></span>

- <span data-ttu-id="bb2ba-389">Указывает пороговый размер (в байтах), при котором объекты попадают в кучу больших объектов (LOH).</span><span class="sxs-lookup"><span data-stu-id="bb2ba-389">Specifies the threshold size, in bytes, that causes objects to go on the large object heap (LOH).</span></span>
- <span data-ttu-id="bb2ba-390">Пороговое значение по умолчанию — 85 000 байт.</span><span class="sxs-lookup"><span data-stu-id="bb2ba-390">The default threshold is 85,000 bytes.</span></span>
- <span data-ttu-id="bb2ba-391">Указанное значение должно быть больше порогового значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="bb2ba-391">The value you specify must be larger than the default threshold.</span></span>

| | <span data-ttu-id="bb2ba-392">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="bb2ba-392">Setting name</span></span> | <span data-ttu-id="bb2ba-393">Значения</span><span class="sxs-lookup"><span data-stu-id="bb2ba-393">Values</span></span> | <span data-ttu-id="bb2ba-394">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="bb2ba-394">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="bb2ba-395">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="bb2ba-395">**runtimeconfig.json**</span></span> | `System.GC.LOHThreshold` | <span data-ttu-id="bb2ba-396">*Десятичное значение*</span><span class="sxs-lookup"><span data-stu-id="bb2ba-396">*decimal value*</span></span> | <span data-ttu-id="bb2ba-397">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="bb2ba-397">.NET Core 1.0</span></span> |
| <span data-ttu-id="bb2ba-398">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="bb2ba-398">**Environment variable**</span></span> | `COMPlus_GCLOHThreshold` | <span data-ttu-id="bb2ba-399">*Шестнадцатеричное значение*</span><span class="sxs-lookup"><span data-stu-id="bb2ba-399">*hexadecimal value*</span></span> | <span data-ttu-id="bb2ba-400">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="bb2ba-400">.NET Core 1.0</span></span> |
| <span data-ttu-id="bb2ba-401">**app.config для .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="bb2ba-401">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="bb2ba-402">GCLOHThreshold</span><span class="sxs-lookup"><span data-stu-id="bb2ba-402">GCLOHThreshold</span></span>](../../framework/configure-apps/file-schema/runtime/gclohthreshold-element.md) | <span data-ttu-id="bb2ba-403">*Десятичное значение*</span><span class="sxs-lookup"><span data-stu-id="bb2ba-403">*decimal value*</span></span> | <span data-ttu-id="bb2ba-404">.NET Framework 4.8</span><span class="sxs-lookup"><span data-stu-id="bb2ba-404">.NET Framework 4.8</span></span> |

<span data-ttu-id="bb2ba-405">Пример.</span><span class="sxs-lookup"><span data-stu-id="bb2ba-405">Example:</span></span>

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
> <span data-ttu-id="bb2ba-406">Если вы задаете параметр в *runtimeconfig.json*, укажите десятичное значение.</span><span class="sxs-lookup"><span data-stu-id="bb2ba-406">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="bb2ba-407">Если вы задаете параметр в виде переменной среды, укажите шестнадцатеричное значение.</span><span class="sxs-lookup"><span data-stu-id="bb2ba-407">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="bb2ba-408">Например, чтобы задать порог размера в 120 000 байт, для JSON-файла нужно указать значение 120000, а для переменной среды — значение 0x1D4C0 или 1D4C0.</span><span class="sxs-lookup"><span data-stu-id="bb2ba-408">For example, to set a threshold size of 120,000 bytes, the values would be 120000 for the JSON file and 0x1D4C0 or 1D4C0 for the environment variable.</span></span>

## <a name="standalone-gc"></a><span data-ttu-id="bb2ba-409">Автономный сборщик мусора</span><span class="sxs-lookup"><span data-stu-id="bb2ba-409">Standalone GC</span></span>

### <a name="complus_gcname"></a><span data-ttu-id="bb2ba-410">COMPlus_GCName</span><span class="sxs-lookup"><span data-stu-id="bb2ba-410">COMPlus_GCName</span></span>

- <span data-ttu-id="bb2ba-411">Указывает путь к библиотеке, содержащей сборщик мусора, который среда выполнения намеревается загрузить.</span><span class="sxs-lookup"><span data-stu-id="bb2ba-411">Specifies a path to the library containing the garbage collector that the runtime intends to load.</span></span>
- <span data-ttu-id="bb2ba-412">Дополнительные сведения см. в статье [Проектирования загрузчика автономного сборщика мусора](https://github.com/dotnet/runtime/blob/master/docs/design/features/standalone-gc-loading.md).</span><span class="sxs-lookup"><span data-stu-id="bb2ba-412">For more information, see [Standalone GC loader design](https://github.com/dotnet/runtime/blob/master/docs/design/features/standalone-gc-loading.md).</span></span>

| | <span data-ttu-id="bb2ba-413">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="bb2ba-413">Setting name</span></span> | <span data-ttu-id="bb2ba-414">Значения</span><span class="sxs-lookup"><span data-stu-id="bb2ba-414">Values</span></span> | <span data-ttu-id="bb2ba-415">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="bb2ba-415">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="bb2ba-416">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="bb2ba-416">**runtimeconfig.json**</span></span> | <span data-ttu-id="bb2ba-417">Н/Д</span><span class="sxs-lookup"><span data-stu-id="bb2ba-417">N/A</span></span> | <span data-ttu-id="bb2ba-418">Н/Д</span><span class="sxs-lookup"><span data-stu-id="bb2ba-418">N/A</span></span> | <span data-ttu-id="bb2ba-419">Н/Д</span><span class="sxs-lookup"><span data-stu-id="bb2ba-419">N/A</span></span> |
| <span data-ttu-id="bb2ba-420">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="bb2ba-420">**Environment variable**</span></span> | `COMPlus_GCName` | <span data-ttu-id="bb2ba-421">*string_path*</span><span class="sxs-lookup"><span data-stu-id="bb2ba-421">*string_path*</span></span> | <span data-ttu-id="bb2ba-422">.NET Core 2.0;</span><span class="sxs-lookup"><span data-stu-id="bb2ba-422">.NET Core 2.0</span></span> |
