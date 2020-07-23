---
title: Параметры конфигурации сборщика мусора
description: Сведения о параметрах времени выполнения, определяющих, как сборщик мусора управляет памятью для приложений .NET Core.
ms.date: 07/10/2020
ms.topic: reference
ms.openlocfilehash: 6ae5b7447fb0df4978ea9dcaa5e76fcc7a6cc4ca
ms.sourcegitcommit: 2543a78be6e246aa010a01decf58889de53d1636
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/17/2020
ms.locfileid: "86441415"
---
# <a name="run-time-configuration-options-for-garbage-collection"></a><span data-ttu-id="aa0db-103">Параметры конфигурации времени выполнения для сборки мусора</span><span class="sxs-lookup"><span data-stu-id="aa0db-103">Run-time configuration options for garbage collection</span></span>

<span data-ttu-id="aa0db-104">Эта страница содержит сведения о параметрах сборщика мусора (GC), которые можно изменить во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="aa0db-104">This page contains information about garbage collector (GC) settings that can be changed at run time.</span></span> <span data-ttu-id="aa0db-105">Если вы пытаетесь добиться пиковой производительности запущенных приложений, рекомендуется использовать эти параметры.</span><span class="sxs-lookup"><span data-stu-id="aa0db-105">If you're trying to achieve peak performance of a running app, consider using these settings.</span></span> <span data-ttu-id="aa0db-106">Однако значения по умолчанию обеспечивают оптимальную производительность для большинства приложений в типичных ситуациях.</span><span class="sxs-lookup"><span data-stu-id="aa0db-106">However, the defaults provide optimum performance for most applications in typical situations.</span></span>

<span data-ttu-id="aa0db-107">На этой странице параметры упорядочены по группам.</span><span class="sxs-lookup"><span data-stu-id="aa0db-107">Settings are arranged into groups on this page.</span></span> <span data-ttu-id="aa0db-108">Параметры в каждой группе обычно используются совместно друг с другом для достижения определенного результата.</span><span class="sxs-lookup"><span data-stu-id="aa0db-108">The settings within each group are commonly used in conjunction with each other to achieve a specific result.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="aa0db-109">Эти параметры также могут динамически изменяться приложением во время его выполнения, поэтому любые заданные параметры времени выполнения могут быть переопределены.</span><span class="sxs-lookup"><span data-stu-id="aa0db-109">These settings can also be changed dynamically by the app as it's running, so any run-time settings you set may be overridden.</span></span>
> - <span data-ttu-id="aa0db-110">Некоторые параметры, такие как [уровень задержки](../../standard/garbage-collection/latency.md), обычно задаются только через API во время разработки.</span><span class="sxs-lookup"><span data-stu-id="aa0db-110">Some settings, such as [latency level](../../standard/garbage-collection/latency.md), are typically set only through the API at design time.</span></span> <span data-ttu-id="aa0db-111">Такие параметры будут пропущены на этой странице.</span><span class="sxs-lookup"><span data-stu-id="aa0db-111">Such settings are omitted from this page.</span></span>
> - <span data-ttu-id="aa0db-112">Для числовых значений используйте десятичную нотацию для параметров в файле *runtimeconfig.json* и шестнадцатеричную нотацию для параметров переменных среды.</span><span class="sxs-lookup"><span data-stu-id="aa0db-112">For number values, use decimal notation for settings in the *runtimeconfig.json* file and hexadecimal notation for environment variable settings.</span></span> <span data-ttu-id="aa0db-113">Шестнадцатеричные значения можно указать с помощью префикса "0x" или без него.</span><span class="sxs-lookup"><span data-stu-id="aa0db-113">For hexadecimal values, you can specify them with or without the "0x" prefix.</span></span>

## <a name="flavors-of-garbage-collection"></a><span data-ttu-id="aa0db-114">Варианты сборки мусора</span><span class="sxs-lookup"><span data-stu-id="aa0db-114">Flavors of garbage collection</span></span>

<span data-ttu-id="aa0db-115">Два основных варианта сборки мусора — это сборка мусора рабочей станции и сборка мусора сервера.</span><span class="sxs-lookup"><span data-stu-id="aa0db-115">The two main flavors of garbage collection are workstation GC and server GC.</span></span> <span data-ttu-id="aa0db-116">Дополнительные сведения о различиях между этими двумя вариантами см. в статье [Сборка мусора рабочей станции и сборка мусора сервера](../../standard/garbage-collection/workstation-server-gc.md).</span><span class="sxs-lookup"><span data-stu-id="aa0db-116">For more information about differences between the two, see [Workstation and server garbage collection](../../standard/garbage-collection/workstation-server-gc.md).</span></span>

<span data-ttu-id="aa0db-117">Подвиды сборки мусора представлены фоновым и непараллельным выполнением.</span><span class="sxs-lookup"><span data-stu-id="aa0db-117">The subflavors of garbage collection are background and non-concurrent.</span></span>

<span data-ttu-id="aa0db-118">Чтобы выбрать варианты сборки мусора, используйте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="aa0db-118">Use the following settings to select flavors of garbage collection:</span></span>

### <a name="systemgcservercomplus_gcserver"></a><span data-ttu-id="aa0db-119">System.GC.Server/COMPlus_gcServer</span><span class="sxs-lookup"><span data-stu-id="aa0db-119">System.GC.Server/COMPlus_gcServer</span></span>

- <span data-ttu-id="aa0db-120">Указывает, использует ли приложение сборку мусора рабочей станции или сборку мусора сервера.</span><span class="sxs-lookup"><span data-stu-id="aa0db-120">Configures whether the application uses workstation garbage collection or server garbage collection.</span></span>
- <span data-ttu-id="aa0db-121">По умолчанию: сборка мусора рабочей станции.</span><span class="sxs-lookup"><span data-stu-id="aa0db-121">Default: Workstation garbage collection.</span></span> <span data-ttu-id="aa0db-122">Это эквивалентно присвоению значения `false`.</span><span class="sxs-lookup"><span data-stu-id="aa0db-122">This is equivalent to setting the value to `false`.</span></span>

| | <span data-ttu-id="aa0db-123">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="aa0db-123">Setting name</span></span> | <span data-ttu-id="aa0db-124">Значения</span><span class="sxs-lookup"><span data-stu-id="aa0db-124">Values</span></span> | <span data-ttu-id="aa0db-125">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="aa0db-125">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="aa0db-126">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="aa0db-126">**runtimeconfig.json**</span></span> | `System.GC.Server` | <span data-ttu-id="aa0db-127">`false` — рабочая станция</span><span class="sxs-lookup"><span data-stu-id="aa0db-127">`false` - workstation</span></span><br/><span data-ttu-id="aa0db-128">`true` — сервер</span><span class="sxs-lookup"><span data-stu-id="aa0db-128">`true` - server</span></span> | <span data-ttu-id="aa0db-129">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="aa0db-129">.NET Core 1.0</span></span> |
| <span data-ttu-id="aa0db-130">**Свойство MSBuild**</span><span class="sxs-lookup"><span data-stu-id="aa0db-130">**MSBuild property**</span></span> | `ServerGarbageCollection` | <span data-ttu-id="aa0db-131">`false` — рабочая станция</span><span class="sxs-lookup"><span data-stu-id="aa0db-131">`false` - workstation</span></span><br/><span data-ttu-id="aa0db-132">`true` — сервер</span><span class="sxs-lookup"><span data-stu-id="aa0db-132">`true` - server</span></span> | <span data-ttu-id="aa0db-133">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="aa0db-133">.NET Core 1.0</span></span> |
| <span data-ttu-id="aa0db-134">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="aa0db-134">**Environment variable**</span></span> | `COMPlus_gcServer` | <span data-ttu-id="aa0db-135">`0` — рабочая станция</span><span class="sxs-lookup"><span data-stu-id="aa0db-135">`0` - workstation</span></span><br/><span data-ttu-id="aa0db-136">`1` — сервер</span><span class="sxs-lookup"><span data-stu-id="aa0db-136">`1` - server</span></span> | <span data-ttu-id="aa0db-137">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="aa0db-137">.NET Core 1.0</span></span> |
| <span data-ttu-id="aa0db-138">**app.config для .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="aa0db-138">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="aa0db-139">GCServer</span><span class="sxs-lookup"><span data-stu-id="aa0db-139">GCServer</span></span>](../../framework/configure-apps/file-schema/runtime/gcserver-element.md) | <span data-ttu-id="aa0db-140">`false` — рабочая станция</span><span class="sxs-lookup"><span data-stu-id="aa0db-140">`false` - workstation</span></span><br/><span data-ttu-id="aa0db-141">`true` — сервер</span><span class="sxs-lookup"><span data-stu-id="aa0db-141">`true` - server</span></span> |  |

### <a name="examples"></a><span data-ttu-id="aa0db-142">Примеры</span><span class="sxs-lookup"><span data-stu-id="aa0db-142">Examples</span></span>

<span data-ttu-id="aa0db-143">Файл *runtimeconfig.json*</span><span class="sxs-lookup"><span data-stu-id="aa0db-143">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Server": true
      }
   }
}
```

<span data-ttu-id="aa0db-144">Файл проекта:</span><span class="sxs-lookup"><span data-stu-id="aa0db-144">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ServerGarbageCollection>true</ServerGarbageCollection>
  </PropertyGroup>

</Project>
```

### <a name="systemgcconcurrentcomplus_gcconcurrent"></a><span data-ttu-id="aa0db-145">System.GC.Concurrent/COMPlus_gcConcurrent</span><span class="sxs-lookup"><span data-stu-id="aa0db-145">System.GC.Concurrent/COMPlus_gcConcurrent</span></span>

- <span data-ttu-id="aa0db-146">Указывает, включена ли фоновая (параллельная) сборка мусора.</span><span class="sxs-lookup"><span data-stu-id="aa0db-146">Configures whether background (concurrent) garbage collection is enabled.</span></span>
- <span data-ttu-id="aa0db-147">По умолчанию: фоновая сборка мусора.</span><span class="sxs-lookup"><span data-stu-id="aa0db-147">Default: Use background GC.</span></span> <span data-ttu-id="aa0db-148">Это эквивалентно присвоению значения `true`.</span><span class="sxs-lookup"><span data-stu-id="aa0db-148">This is equivalent to setting the value to `true`.</span></span>
- <span data-ttu-id="aa0db-149">Дополнительные сведения см. в статье [Фоновая сборка мусора](../../standard/garbage-collection/background-gc.md).</span><span class="sxs-lookup"><span data-stu-id="aa0db-149">For more information, see [Background garbage collection](../../standard/garbage-collection/background-gc.md).</span></span>

| | <span data-ttu-id="aa0db-150">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="aa0db-150">Setting name</span></span> | <span data-ttu-id="aa0db-151">Значения</span><span class="sxs-lookup"><span data-stu-id="aa0db-151">Values</span></span> | <span data-ttu-id="aa0db-152">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="aa0db-152">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="aa0db-153">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="aa0db-153">**runtimeconfig.json**</span></span> | `System.GC.Concurrent` | <span data-ttu-id="aa0db-154">`true` —фоновая сборка мусора</span><span class="sxs-lookup"><span data-stu-id="aa0db-154">`true` - background GC</span></span><br/><span data-ttu-id="aa0db-155">`false` — непараллельная сборка мусора</span><span class="sxs-lookup"><span data-stu-id="aa0db-155">`false` - non-concurrent GC</span></span> | <span data-ttu-id="aa0db-156">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="aa0db-156">.NET Core 1.0</span></span> |
| <span data-ttu-id="aa0db-157">**Свойство MSBuild**</span><span class="sxs-lookup"><span data-stu-id="aa0db-157">**MSBuild property**</span></span> | `ConcurrentGarbageCollection` | <span data-ttu-id="aa0db-158">`true` —фоновая сборка мусора</span><span class="sxs-lookup"><span data-stu-id="aa0db-158">`true` - background GC</span></span><br/><span data-ttu-id="aa0db-159">`false` — непараллельная сборка мусора</span><span class="sxs-lookup"><span data-stu-id="aa0db-159">`false` - non-concurrent GC</span></span> | <span data-ttu-id="aa0db-160">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="aa0db-160">.NET Core 1.0</span></span> |
| <span data-ttu-id="aa0db-161">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="aa0db-161">**Environment variable**</span></span> | `COMPlus_gcConcurrent` | <span data-ttu-id="aa0db-162">`1` —фоновая сборка мусора</span><span class="sxs-lookup"><span data-stu-id="aa0db-162">`1` - background GC</span></span><br/><span data-ttu-id="aa0db-163">`0` — непараллельная сборка мусора</span><span class="sxs-lookup"><span data-stu-id="aa0db-163">`0` - non-concurrent GC</span></span> | <span data-ttu-id="aa0db-164">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="aa0db-164">.NET Core 1.0</span></span> |
| <span data-ttu-id="aa0db-165">**app.config для .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="aa0db-165">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="aa0db-166">gcConcurrent</span><span class="sxs-lookup"><span data-stu-id="aa0db-166">gcConcurrent</span></span>](../../framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) | <span data-ttu-id="aa0db-167">`true` —фоновая сборка мусора</span><span class="sxs-lookup"><span data-stu-id="aa0db-167">`true` - background GC</span></span><br/><span data-ttu-id="aa0db-168">`false` — непараллельная сборка мусора</span><span class="sxs-lookup"><span data-stu-id="aa0db-168">`false` - non-concurrent GC</span></span> |  |

### <a name="examples"></a><span data-ttu-id="aa0db-169">Примеры</span><span class="sxs-lookup"><span data-stu-id="aa0db-169">Examples</span></span>

<span data-ttu-id="aa0db-170">Файл *runtimeconfig.json*</span><span class="sxs-lookup"><span data-stu-id="aa0db-170">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Concurrent": false
      }
   }
}
```

<span data-ttu-id="aa0db-171">Файл проекта:</span><span class="sxs-lookup"><span data-stu-id="aa0db-171">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ConcurrentGarbageCollection>false</ConcurrentGarbageCollection>
  </PropertyGroup>

</Project>
```

## <a name="manage-resource-usage"></a><span data-ttu-id="aa0db-172">Управление использованием ресурсов</span><span class="sxs-lookup"><span data-stu-id="aa0db-172">Manage resource usage</span></span>

<span data-ttu-id="aa0db-173">Используйте параметры, описанные в этом разделе, для управления использованием памяти и ЦП в сборщике мусора.</span><span class="sxs-lookup"><span data-stu-id="aa0db-173">Use the settings described in this section to manage the garbage collector's memory and processor usage.</span></span>

<span data-ttu-id="aa0db-174">Дополнительные сведения о некоторых из этих параметров см. в записи блога о [компромиссе между сборкой мусора рабочей станции и сервера](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/).</span><span class="sxs-lookup"><span data-stu-id="aa0db-174">For more information about some of these settings, see the [Middle ground between workstation and server GC](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/) blog entry.</span></span>

### <a name="systemgcheapcountcomplus_gcheapcount"></a><span data-ttu-id="aa0db-175">System.GC.HeapCount/COMPlus_GCHeapCount</span><span class="sxs-lookup"><span data-stu-id="aa0db-175">System.GC.HeapCount/COMPlus_GCHeapCount</span></span>

- <span data-ttu-id="aa0db-176">Ограничивает число куч, создаваемых сборщиком мусора.</span><span class="sxs-lookup"><span data-stu-id="aa0db-176">Limits the number of heaps created by the garbage collector.</span></span>
- <span data-ttu-id="aa0db-177">Применяется только к сборке мусора сервера.</span><span class="sxs-lookup"><span data-stu-id="aa0db-177">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="aa0db-178">Если включено [сходство процессоров сборки мусора](#systemgcnoaffinitizecomplus_gcnoaffinitize), что используется по умолчанию, параметр счетчика куч реализует сходство `n` куч/потоков сборки мусора с первыми `n` процессорами.</span><span class="sxs-lookup"><span data-stu-id="aa0db-178">If [GC processor affinity](#systemgcnoaffinitizecomplus_gcnoaffinitize) is enabled, which is the default, the heap count setting affinitizes `n` GC heaps/threads to the first `n` processors.</span></span> <span data-ttu-id="aa0db-179">(Используйте параметры [сходства маски](#systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask) или [сходства диапазонов](#systemgcgcheapaffinitizerangescomplus_gcheapaffinitizeranges), чтобы указать, для каких именно процессоров следует реализовать сходство.)</span><span class="sxs-lookup"><span data-stu-id="aa0db-179">(Use the [affinitize mask](#systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask) or [affinitize ranges](#systemgcgcheapaffinitizerangescomplus_gcheapaffinitizeranges) settings to specify exactly which processors to affinitize.)</span></span>
- <span data-ttu-id="aa0db-180">Если [сходство процессоров сборки мусора](#systemgcnoaffinitizecomplus_gcnoaffinitize) отключено, этот параметр будет ограничивать количество куч сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="aa0db-180">If [GC processor affinity](#systemgcnoaffinitizecomplus_gcnoaffinitize) is disabled, this setting limits the number of GC heaps.</span></span>
- <span data-ttu-id="aa0db-181">Дополнительные сведения см. в [примечаниях по GCHeapCount](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md#remarks).</span><span class="sxs-lookup"><span data-stu-id="aa0db-181">For more information, see the [GCHeapCount remarks](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md#remarks).</span></span>

| | <span data-ttu-id="aa0db-182">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="aa0db-182">Setting name</span></span> | <span data-ttu-id="aa0db-183">Значения</span><span class="sxs-lookup"><span data-stu-id="aa0db-183">Values</span></span> | <span data-ttu-id="aa0db-184">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="aa0db-184">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="aa0db-185">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="aa0db-185">**runtimeconfig.json**</span></span> | `System.GC.HeapCount` | <span data-ttu-id="aa0db-186">*Десятичное значение*</span><span class="sxs-lookup"><span data-stu-id="aa0db-186">*decimal value*</span></span> | <span data-ttu-id="aa0db-187">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="aa0db-187">.NET Core 3.0</span></span> |
| <span data-ttu-id="aa0db-188">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="aa0db-188">**Environment variable**</span></span> | `COMPlus_GCHeapCount` | <span data-ttu-id="aa0db-189">*Шестнадцатеричное значение*</span><span class="sxs-lookup"><span data-stu-id="aa0db-189">*hexadecimal value*</span></span> | <span data-ttu-id="aa0db-190">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="aa0db-190">.NET Core 3.0</span></span> |
| <span data-ttu-id="aa0db-191">**app.config для .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="aa0db-191">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="aa0db-192">GCHeapCount</span><span class="sxs-lookup"><span data-stu-id="aa0db-192">GCHeapCount</span></span>](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md) | <span data-ttu-id="aa0db-193">*Десятичное значение*</span><span class="sxs-lookup"><span data-stu-id="aa0db-193">*decimal value*</span></span> | <span data-ttu-id="aa0db-194">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="aa0db-194">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="aa0db-195">Пример.</span><span class="sxs-lookup"><span data-stu-id="aa0db-195">Example:</span></span>

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
> <span data-ttu-id="aa0db-196">Если вы задаете параметр в *runtimeconfig.json*, укажите десятичное значение.</span><span class="sxs-lookup"><span data-stu-id="aa0db-196">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="aa0db-197">Если вы задаете параметр в виде переменной среды, укажите шестнадцатеричное значение.</span><span class="sxs-lookup"><span data-stu-id="aa0db-197">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="aa0db-198">Например, чтобы ограничить число куч значением 16, для JSON-файла нужно указать 16, а для переменной среды — 0x10 или 10.</span><span class="sxs-lookup"><span data-stu-id="aa0db-198">For example, to limit the number of heaps to 16, the values would be 16 for the JSON file and 0x10 or 10 for the environment variable.</span></span>

### <a name="systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask"></a><span data-ttu-id="aa0db-199">System.GC.HeapAffinitizeMask/COMPlus_GCHeapAffinitizeMask</span><span class="sxs-lookup"><span data-stu-id="aa0db-199">System.GC.HeapAffinitizeMask/COMPlus_GCHeapAffinitizeMask</span></span>

- <span data-ttu-id="aa0db-200">Указывает конкретные процессоры, которые должны использоваться потоками сборщика мусора.</span><span class="sxs-lookup"><span data-stu-id="aa0db-200">Specifies the exact processors that garbage collector threads should use.</span></span>
- <span data-ttu-id="aa0db-201">Если [сходство процессоров](#systemgcnoaffinitizecomplus_gcnoaffinitize) отключено, этот параметр игнорируется.</span><span class="sxs-lookup"><span data-stu-id="aa0db-201">If [GC processor affinity](#systemgcnoaffinitizecomplus_gcnoaffinitize) is disabled, this setting is ignored.</span></span>
- <span data-ttu-id="aa0db-202">Применяется только к сборке мусора сервера.</span><span class="sxs-lookup"><span data-stu-id="aa0db-202">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="aa0db-203">Это значение представляет собой битовую маску, которая определяет доступные процессу процессоры.</span><span class="sxs-lookup"><span data-stu-id="aa0db-203">The value is a bit mask that defines the processors that are available to the process.</span></span> <span data-ttu-id="aa0db-204">Например, десятичное значение 1023 (или шестнадцатеричное значение 0x3FF или 3FF, если вы используете переменную среды), равно 0011 1111 1111 в двоичной нотации.</span><span class="sxs-lookup"><span data-stu-id="aa0db-204">For example, a decimal value of 1023 (or a hexadecimal value of 0x3FF or 3FF if you're using the environment variable) is 0011 1111 1111 in binary notation.</span></span> <span data-ttu-id="aa0db-205">При этом будут использоваться первые 10 процессоров.</span><span class="sxs-lookup"><span data-stu-id="aa0db-205">This specifies that the first 10 processors are to be used.</span></span> <span data-ttu-id="aa0db-206">Чтобы указать следующие 10 процессоров, то есть процессоры 10–19, задайте десятичное значение 1047552 (или шестнадцатеричное значение 0xFFC00 или FFC00), которое эквивалентно двоичному значению 1111 1111 1100 0000 0000.</span><span class="sxs-lookup"><span data-stu-id="aa0db-206">To specify the next 10 processors, that is, processors 10-19, specify a decimal value of 1047552 (or a hexadecimal value of 0xFFC00 or FFC00), which is equivalent to a binary value of 1111 1111 1100 0000 0000.</span></span>

| | <span data-ttu-id="aa0db-207">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="aa0db-207">Setting name</span></span> | <span data-ttu-id="aa0db-208">Значения</span><span class="sxs-lookup"><span data-stu-id="aa0db-208">Values</span></span> | <span data-ttu-id="aa0db-209">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="aa0db-209">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="aa0db-210">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="aa0db-210">**runtimeconfig.json**</span></span> | `System.GC.HeapAffinitizeMask` | <span data-ttu-id="aa0db-211">*Десятичное значение*</span><span class="sxs-lookup"><span data-stu-id="aa0db-211">*decimal value*</span></span> | <span data-ttu-id="aa0db-212">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="aa0db-212">.NET Core 3.0</span></span> |
| <span data-ttu-id="aa0db-213">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="aa0db-213">**Environment variable**</span></span> | `COMPlus_GCHeapAffinitizeMask` | <span data-ttu-id="aa0db-214">*Шестнадцатеричное значение*</span><span class="sxs-lookup"><span data-stu-id="aa0db-214">*hexadecimal value*</span></span> | <span data-ttu-id="aa0db-215">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="aa0db-215">.NET Core 3.0</span></span> |
| <span data-ttu-id="aa0db-216">**app.config для .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="aa0db-216">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="aa0db-217">GCHeapAffinitizeMask</span><span class="sxs-lookup"><span data-stu-id="aa0db-217">GCHeapAffinitizeMask</span></span>](../../framework/configure-apps/file-schema/runtime/gcheapaffinitizemask-element.md) | <span data-ttu-id="aa0db-218">*Десятичное значение*</span><span class="sxs-lookup"><span data-stu-id="aa0db-218">*decimal value*</span></span> | <span data-ttu-id="aa0db-219">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="aa0db-219">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="aa0db-220">Пример.</span><span class="sxs-lookup"><span data-stu-id="aa0db-220">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.HeapAffinitizeMask": 1023
      }
   }
}
```

### <a name="systemgcgcheapaffinitizerangescomplus_gcheapaffinitizeranges"></a><span data-ttu-id="aa0db-221">System.GC.GCHeapAffinitizeRanges/COMPlus_GCHeapAffinitizeRanges</span><span class="sxs-lookup"><span data-stu-id="aa0db-221">System.GC.GCHeapAffinitizeRanges/COMPlus_GCHeapAffinitizeRanges</span></span>

- <span data-ttu-id="aa0db-222">Указывает список процессоров, используемых для потоков сборщика мусора.</span><span class="sxs-lookup"><span data-stu-id="aa0db-222">Specifies the list of processors to use for garbage collector threads.</span></span>
- <span data-ttu-id="aa0db-223">Этот параметр аналогичен [System.GC.HeapAffinitizeMask](#systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask), за исключением того, что он позволяет указать больше 64 процессоров.</span><span class="sxs-lookup"><span data-stu-id="aa0db-223">This setting is similar to [System.GC.HeapAffinitizeMask](#systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask), except it allows you to specify more than 64 processors.</span></span>
- <span data-ttu-id="aa0db-224">Для операционных систем Windows добавьте к номеру или диапазону процессоров префикс в виде соответствующей [группы ЦП](/windows/win32/procthread/processor-groups), например "0:1-10,0:12,1:50-52,1:70".</span><span class="sxs-lookup"><span data-stu-id="aa0db-224">For Windows operating systems, prefix the processor number or range with the corresponding [CPU group](/windows/win32/procthread/processor-groups), for example, "0:1-10,0:12,1:50-52,1:70".</span></span>
- <span data-ttu-id="aa0db-225">Если [сходство процессоров](#systemgcnoaffinitizecomplus_gcnoaffinitize) отключено, этот параметр игнорируется.</span><span class="sxs-lookup"><span data-stu-id="aa0db-225">If [GC processor affinity](#systemgcnoaffinitizecomplus_gcnoaffinitize) is disabled, this setting is ignored.</span></span>
- <span data-ttu-id="aa0db-226">Применяется только к сборке мусора сервера.</span><span class="sxs-lookup"><span data-stu-id="aa0db-226">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="aa0db-227">Дополнительные сведения см. в записи об [улучшении конфигурации ЦП для сборки мусора на компьютерах, имеющих более 64 ЦП](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/), в блоге Майони Стивенс (Maoni Stephens).</span><span class="sxs-lookup"><span data-stu-id="aa0db-227">For more information, see [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) on Maoni Stephens' blog.</span></span>

| | <span data-ttu-id="aa0db-228">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="aa0db-228">Setting name</span></span> | <span data-ttu-id="aa0db-229">Значения</span><span class="sxs-lookup"><span data-stu-id="aa0db-229">Values</span></span> | <span data-ttu-id="aa0db-230">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="aa0db-230">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="aa0db-231">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="aa0db-231">**runtimeconfig.json**</span></span> | `System.GC.GCHeapAffinitizeRanges` | <span data-ttu-id="aa0db-232">Разделенный запятыми список номеров процессоров или диапазонов номеров процессоров.</span><span class="sxs-lookup"><span data-stu-id="aa0db-232">Comma-separated list of processor numbers or ranges of processor numbers.</span></span><br/><span data-ttu-id="aa0db-233">Пример для Unix: "1-10,12,50-52,70"</span><span class="sxs-lookup"><span data-stu-id="aa0db-233">Unix example: "1-10,12,50-52,70"</span></span><br/><span data-ttu-id="aa0db-234">Пример для Windows: "0:1-10,0:12,1:50-52,1:70"</span><span class="sxs-lookup"><span data-stu-id="aa0db-234">Windows example: "0:1-10,0:12,1:50-52,1:70"</span></span> | <span data-ttu-id="aa0db-235">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="aa0db-235">.NET Core 3.0</span></span> |
| <span data-ttu-id="aa0db-236">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="aa0db-236">**Environment variable**</span></span> | `COMPlus_GCHeapAffinitizeRanges` | <span data-ttu-id="aa0db-237">Разделенный запятыми список номеров процессоров или диапазонов номеров процессоров.</span><span class="sxs-lookup"><span data-stu-id="aa0db-237">Comma-separated list of processor numbers or ranges of processor numbers.</span></span><br/><span data-ttu-id="aa0db-238">Пример для Unix: "1-10,12,50-52,70"</span><span class="sxs-lookup"><span data-stu-id="aa0db-238">Unix example: "1-10,12,50-52,70"</span></span><br/><span data-ttu-id="aa0db-239">Пример для Windows: "0:1-10,0:12,1:50-52,1:70"</span><span class="sxs-lookup"><span data-stu-id="aa0db-239">Windows example: "0:1-10,0:12,1:50-52,1:70"</span></span> | <span data-ttu-id="aa0db-240">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="aa0db-240">.NET Core 3.0</span></span> |

<span data-ttu-id="aa0db-241">Пример.</span><span class="sxs-lookup"><span data-stu-id="aa0db-241">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.GCHeapAffinitizeRanges": "0:1-10,0:12,1:50-52,1:70"
      }
   }
}
```

### <a name="complus_gccpugroup"></a><span data-ttu-id="aa0db-242">COMPlus_GCCpuGroup</span><span class="sxs-lookup"><span data-stu-id="aa0db-242">COMPlus_GCCpuGroup</span></span>

- <span data-ttu-id="aa0db-243">Указывает, использует ли сборщик мусора [группы ЦП](/windows/win32/procthread/processor-groups).</span><span class="sxs-lookup"><span data-stu-id="aa0db-243">Configures whether the garbage collector uses [CPU groups](/windows/win32/procthread/processor-groups) or not.</span></span>

  <span data-ttu-id="aa0db-244">Когда 64-разрядный компьютер с Windows имеет несколько групп ЦП, то есть доступно более 64 процессоров, включение этого элемента расширяет действие сборки мусора на все группы ЦП.</span><span class="sxs-lookup"><span data-stu-id="aa0db-244">When a 64-bit Windows computer has multiple CPU groups, that is, there are more than 64 processors, enabling this element extends garbage collection across all CPU groups.</span></span> <span data-ttu-id="aa0db-245">Сборщик мусора использует все ядра для создания и балансировки куч.</span><span class="sxs-lookup"><span data-stu-id="aa0db-245">The garbage collector uses all cores to create and balance heaps.</span></span>

- <span data-ttu-id="aa0db-246">Применяется только к сборке мусора сервера в 64-разрядных операционных системах Windows.</span><span class="sxs-lookup"><span data-stu-id="aa0db-246">Applies to server garbage collection on 64-bit Windows operation systems only.</span></span>
- <span data-ttu-id="aa0db-247">По умолчанию: сборка мусора не распространяется на группы ЦП.</span><span class="sxs-lookup"><span data-stu-id="aa0db-247">Default: GC does not extend across CPU groups.</span></span> <span data-ttu-id="aa0db-248">Это эквивалентно присвоению значения `0`.</span><span class="sxs-lookup"><span data-stu-id="aa0db-248">This is equivalent to setting the value to `0`.</span></span>
- <span data-ttu-id="aa0db-249">Дополнительные сведения см. в записи об [улучшении конфигурации ЦП для сборки мусора на компьютерах, имеющих более 64 ЦП](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/), в блоге Майони Стивенс (Maoni Stephens).</span><span class="sxs-lookup"><span data-stu-id="aa0db-249">For more information, see [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) on Maoni Stephens' blog.</span></span>

| | <span data-ttu-id="aa0db-250">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="aa0db-250">Setting name</span></span> | <span data-ttu-id="aa0db-251">Значения</span><span class="sxs-lookup"><span data-stu-id="aa0db-251">Values</span></span> | <span data-ttu-id="aa0db-252">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="aa0db-252">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="aa0db-253">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="aa0db-253">**runtimeconfig.json**</span></span> | <span data-ttu-id="aa0db-254">Н/Д</span><span class="sxs-lookup"><span data-stu-id="aa0db-254">N/A</span></span> | <span data-ttu-id="aa0db-255">Н/Д</span><span class="sxs-lookup"><span data-stu-id="aa0db-255">N/A</span></span> | <span data-ttu-id="aa0db-256">Н/Д</span><span class="sxs-lookup"><span data-stu-id="aa0db-256">N/A</span></span> |
| <span data-ttu-id="aa0db-257">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="aa0db-257">**Environment variable**</span></span> | `COMPlus_GCCpuGroup` | <span data-ttu-id="aa0db-258">`0` — отключено</span><span class="sxs-lookup"><span data-stu-id="aa0db-258">`0` - disabled</span></span><br/><span data-ttu-id="aa0db-259">`1` — включено</span><span class="sxs-lookup"><span data-stu-id="aa0db-259">`1` - enabled</span></span> | <span data-ttu-id="aa0db-260">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="aa0db-260">.NET Core 1.0</span></span> |
| <span data-ttu-id="aa0db-261">**app.config для .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="aa0db-261">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="aa0db-262">GCCpuGroup</span><span class="sxs-lookup"><span data-stu-id="aa0db-262">GCCpuGroup</span></span>](../../framework/configure-apps/file-schema/runtime/gccpugroup-element.md) | <span data-ttu-id="aa0db-263">`false` — отключено</span><span class="sxs-lookup"><span data-stu-id="aa0db-263">`false` - disabled</span></span><br/><span data-ttu-id="aa0db-264">`true` — включено</span><span class="sxs-lookup"><span data-stu-id="aa0db-264">`true` - enabled</span></span> |  |

> [!NOTE]
> <span data-ttu-id="aa0db-265">Чтобы настроить среду CLR для распределения потоков из пула потоков по всем группам ЦП, включите параметр [Элемент Thread_UseAllCpuGroups](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md).</span><span class="sxs-lookup"><span data-stu-id="aa0db-265">To configure the common language runtime (CLR) to also distribute threads from the thread pool across all CPU groups, enable the [Thread_UseAllCpuGroups element](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md) option.</span></span> <span data-ttu-id="aa0db-266">Для приложений .NET Core этот параметр можно включить, задав для переменной среды `COMPlus_Thread_UseAllCpuGroups` значение `1`.</span><span class="sxs-lookup"><span data-stu-id="aa0db-266">For .NET Core apps, you can enable this option by setting the value of the `COMPlus_Thread_UseAllCpuGroups` environment variable to `1`.</span></span>

### <a name="systemgcnoaffinitizecomplus_gcnoaffinitize"></a><span data-ttu-id="aa0db-267">System.GC.NoAffinitize/COMPlus_GCNoAffinitize</span><span class="sxs-lookup"><span data-stu-id="aa0db-267">System.GC.NoAffinitize/COMPlus_GCNoAffinitize</span></span>

- <span data-ttu-id="aa0db-268">Указывает, следует ли *реализовать сходство* потоков сборки мусора с процессорами.</span><span class="sxs-lookup"><span data-stu-id="aa0db-268">Specifies whether to *affinitize* garbage collection threads with processors.</span></span> <span data-ttu-id="aa0db-269">Реализация сходства потока сборки мусора означает, что он может выполняться только на определенном ЦП.</span><span class="sxs-lookup"><span data-stu-id="aa0db-269">To affinitize a GC thread means that it can only run on its specific CPU.</span></span> <span data-ttu-id="aa0db-270">Куча создается для каждого потока сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="aa0db-270">A heap is created for each GC thread.</span></span>
- <span data-ttu-id="aa0db-271">Применяется только к сборке мусора сервера.</span><span class="sxs-lookup"><span data-stu-id="aa0db-271">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="aa0db-272">По умолчанию: реализация сходства потоков сборки мусора с процессорами.</span><span class="sxs-lookup"><span data-stu-id="aa0db-272">Default: Affinitize garbage collection threads with processors.</span></span> <span data-ttu-id="aa0db-273">Это эквивалентно присвоению значения `false`.</span><span class="sxs-lookup"><span data-stu-id="aa0db-273">This is equivalent to setting the value to `false`.</span></span>

| | <span data-ttu-id="aa0db-274">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="aa0db-274">Setting name</span></span> | <span data-ttu-id="aa0db-275">Значения</span><span class="sxs-lookup"><span data-stu-id="aa0db-275">Values</span></span> | <span data-ttu-id="aa0db-276">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="aa0db-276">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="aa0db-277">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="aa0db-277">**runtimeconfig.json**</span></span> | `System.GC.NoAffinitize` | <span data-ttu-id="aa0db-278">`false` — реализовать сходство</span><span class="sxs-lookup"><span data-stu-id="aa0db-278">`false` - affinitize</span></span><br/><span data-ttu-id="aa0db-279">`true` — не реализовывать сходство</span><span class="sxs-lookup"><span data-stu-id="aa0db-279">`true` - don't affinitize</span></span> | <span data-ttu-id="aa0db-280">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="aa0db-280">.NET Core 3.0</span></span> |
| <span data-ttu-id="aa0db-281">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="aa0db-281">**Environment variable**</span></span> | `COMPlus_GCNoAffinitize` | <span data-ttu-id="aa0db-282">`0` — реализовать сходство</span><span class="sxs-lookup"><span data-stu-id="aa0db-282">`0` - affinitize</span></span><br/><span data-ttu-id="aa0db-283">`1` — не реализовывать сходство</span><span class="sxs-lookup"><span data-stu-id="aa0db-283">`1` - don't affinitize</span></span> | <span data-ttu-id="aa0db-284">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="aa0db-284">.NET Core 3.0</span></span> |
| <span data-ttu-id="aa0db-285">**app.config для .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="aa0db-285">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="aa0db-286">GCNoAffinitize</span><span class="sxs-lookup"><span data-stu-id="aa0db-286">GCNoAffinitize</span></span>](../../framework/configure-apps/file-schema/runtime/gcnoaffinitize-element.md) | <span data-ttu-id="aa0db-287">`false` — реализовать сходство</span><span class="sxs-lookup"><span data-stu-id="aa0db-287">`false` - affinitize</span></span><br/><span data-ttu-id="aa0db-288">`true` — не реализовывать сходство</span><span class="sxs-lookup"><span data-stu-id="aa0db-288">`true` - don't affinitize</span></span> | <span data-ttu-id="aa0db-289">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="aa0db-289">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="aa0db-290">Пример.</span><span class="sxs-lookup"><span data-stu-id="aa0db-290">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.NoAffinitize": true
      }
   }
}
```

### <a name="systemgcheaphardlimitcomplus_gcheaphardlimit"></a><span data-ttu-id="aa0db-291">System.GC.HeapHardLimit/COMPlus_GCHeapHardLimit</span><span class="sxs-lookup"><span data-stu-id="aa0db-291">System.GC.HeapHardLimit/COMPlus_GCHeapHardLimit</span></span>

- <span data-ttu-id="aa0db-292">Указывает максимальный размер фиксации в байтах для кучи сборки мусора и учета сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="aa0db-292">Specifies the maximum commit size, in bytes, for the GC heap and GC bookkeeping.</span></span>
- <span data-ttu-id="aa0db-293">Этот параметр применим только к 64-разрядным компьютерам.</span><span class="sxs-lookup"><span data-stu-id="aa0db-293">This setting only applies to 64-bit computers.</span></span>
- <span data-ttu-id="aa0db-294">Если настроены [ограничения для отдельных куч объектов](#per-object-heap-limits), этот параметр игнорируется.</span><span class="sxs-lookup"><span data-stu-id="aa0db-294">This setting is ignored if the [Per-object-heap limits](#per-object-heap-limits) are configured.</span></span>
- <span data-ttu-id="aa0db-295">Значение по умолчанию, которое применяется только в определенных случаях, превышает 20 МБ или 75 % предельного объема памяти в контейнере.</span><span class="sxs-lookup"><span data-stu-id="aa0db-295">The default value, which only applies in certain cases, is the greater of 20 MB or 75% of the memory limit on the container.</span></span> <span data-ttu-id="aa0db-296">Значение по умолчанию применяется, если:</span><span class="sxs-lookup"><span data-stu-id="aa0db-296">The default value applies if:</span></span>

  - <span data-ttu-id="aa0db-297">процесс выполняется в контейнере с заданным предельным объемом памяти;</span><span class="sxs-lookup"><span data-stu-id="aa0db-297">The process is running inside a container that has a specified memory limit.</span></span>
  - <span data-ttu-id="aa0db-298">параметр [System.GC.HeapHardLimitPercent](#systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent) не задан.</span><span class="sxs-lookup"><span data-stu-id="aa0db-298">[System.GC.HeapHardLimitPercent](#systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent) is not set.</span></span>

| | <span data-ttu-id="aa0db-299">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="aa0db-299">Setting name</span></span> | <span data-ttu-id="aa0db-300">Значения</span><span class="sxs-lookup"><span data-stu-id="aa0db-300">Values</span></span> | <span data-ttu-id="aa0db-301">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="aa0db-301">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="aa0db-302">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="aa0db-302">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimit` | <span data-ttu-id="aa0db-303">*Десятичное значение*</span><span class="sxs-lookup"><span data-stu-id="aa0db-303">*decimal value*</span></span> | <span data-ttu-id="aa0db-304">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="aa0db-304">.NET Core 3.0</span></span> |
| <span data-ttu-id="aa0db-305">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="aa0db-305">**Environment variable**</span></span> | `COMPlus_GCHeapHardLimit` | <span data-ttu-id="aa0db-306">*Шестнадцатеричное значение*</span><span class="sxs-lookup"><span data-stu-id="aa0db-306">*hexadecimal value*</span></span> | <span data-ttu-id="aa0db-307">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="aa0db-307">.NET Core 3.0</span></span> |

<span data-ttu-id="aa0db-308">Пример.</span><span class="sxs-lookup"><span data-stu-id="aa0db-308">Example:</span></span>

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
> <span data-ttu-id="aa0db-309">Если вы задаете параметр в *runtimeconfig.json*, укажите десятичное значение.</span><span class="sxs-lookup"><span data-stu-id="aa0db-309">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="aa0db-310">Если вы задаете параметр в виде переменной среды, укажите шестнадцатеричное значение.</span><span class="sxs-lookup"><span data-stu-id="aa0db-310">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="aa0db-311">Например, чтобы задать для куч жесткое ограничение в 200 мебибайт (Миб), для JSON-файла нужно указать значение 209715200, а для переменной среды — значение 0xC800000 или C800000.</span><span class="sxs-lookup"><span data-stu-id="aa0db-311">For example, to specify a heap hard limit of 200 mebibytes (MiB), the values would be 209715200 for the JSON file and 0xC800000 or C800000 for the environment variable.</span></span>

### <a name="systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent"></a><span data-ttu-id="aa0db-312">System.GC.HeapHardLimitPercent/COMPlus_GCHeapHardLimitPercent</span><span class="sxs-lookup"><span data-stu-id="aa0db-312">System.GC.HeapHardLimitPercent/COMPlus_GCHeapHardLimitPercent</span></span>

- <span data-ttu-id="aa0db-313">Указывает допустимое использование кучи сборки мусора в процентах от общего объема физической памяти.</span><span class="sxs-lookup"><span data-stu-id="aa0db-313">Specifies the allowable GC heap usage as a percentage of the total physical memory.</span></span>
- <span data-ttu-id="aa0db-314">Если также задан параметр [System.GC.HeapHardLimit](#systemgcheaphardlimitcomplus_gcheaphardlimit), этот параметр игнорируется.</span><span class="sxs-lookup"><span data-stu-id="aa0db-314">If [System.GC.HeapHardLimit](#systemgcheaphardlimitcomplus_gcheaphardlimit) is also set, this setting is ignored.</span></span>
- <span data-ttu-id="aa0db-315">Этот параметр применим только к 64-разрядным компьютерам.</span><span class="sxs-lookup"><span data-stu-id="aa0db-315">This setting only applies to 64-bit computers.</span></span>
- <span data-ttu-id="aa0db-316">Если процесс выполняется в контейнере с заданным предельным объемом памяти, процентная доля вычисляется как процент от этого объема памяти.</span><span class="sxs-lookup"><span data-stu-id="aa0db-316">If the process is running inside a container that has a specified memory limit, the percentage is calculated as a percentage of that memory limit.</span></span>
- <span data-ttu-id="aa0db-317">Если настроены [ограничения для отдельных куч объектов](#per-object-heap-limits), этот параметр игнорируется.</span><span class="sxs-lookup"><span data-stu-id="aa0db-317">This setting is ignored if the [Per-object-heap limits](#per-object-heap-limits) are configured.</span></span>
- <span data-ttu-id="aa0db-318">Значение по умолчанию, которое применяется только в определенных случаях, не превышает 20 МБ или 75 % предельного объема памяти в контейнере.</span><span class="sxs-lookup"><span data-stu-id="aa0db-318">The default value, which only applies in certain cases, is the lesser of 20 MB or 75% of the memory limit on the container.</span></span> <span data-ttu-id="aa0db-319">Значение по умолчанию применяется, если:</span><span class="sxs-lookup"><span data-stu-id="aa0db-319">The default value applies if:</span></span>

  - <span data-ttu-id="aa0db-320">процесс выполняется в контейнере с заданным предельным объемом памяти;</span><span class="sxs-lookup"><span data-stu-id="aa0db-320">The process is running inside a container that has a specified memory limit.</span></span>
  - <span data-ttu-id="aa0db-321">параметр [System.GC.HeapHardLimit](#systemgcheaphardlimitcomplus_gcheaphardlimit) не задан.</span><span class="sxs-lookup"><span data-stu-id="aa0db-321">[System.GC.HeapHardLimit](#systemgcheaphardlimitcomplus_gcheaphardlimit) is not set.</span></span>

| | <span data-ttu-id="aa0db-322">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="aa0db-322">Setting name</span></span> | <span data-ttu-id="aa0db-323">Значения</span><span class="sxs-lookup"><span data-stu-id="aa0db-323">Values</span></span> | <span data-ttu-id="aa0db-324">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="aa0db-324">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="aa0db-325">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="aa0db-325">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimitPercent` | <span data-ttu-id="aa0db-326">*Десятичное значение*</span><span class="sxs-lookup"><span data-stu-id="aa0db-326">*decimal value*</span></span> | <span data-ttu-id="aa0db-327">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="aa0db-327">.NET Core 3.0</span></span> |
| <span data-ttu-id="aa0db-328">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="aa0db-328">**Environment variable**</span></span> | `COMPlus_GCHeapHardLimitPercent` | <span data-ttu-id="aa0db-329">*Шестнадцатеричное значение*</span><span class="sxs-lookup"><span data-stu-id="aa0db-329">*hexadecimal value*</span></span> | <span data-ttu-id="aa0db-330">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="aa0db-330">.NET Core 3.0</span></span> |

<span data-ttu-id="aa0db-331">Пример.</span><span class="sxs-lookup"><span data-stu-id="aa0db-331">Example:</span></span>

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
> <span data-ttu-id="aa0db-332">Если вы задаете параметр в *runtimeconfig.json*, укажите десятичное значение.</span><span class="sxs-lookup"><span data-stu-id="aa0db-332">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="aa0db-333">Если вы задаете параметр в виде переменной среды, укажите шестнадцатеричное значение.</span><span class="sxs-lookup"><span data-stu-id="aa0db-333">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="aa0db-334">Например, чтобы ограничить использование кучи значением 30 %, для JSON-файла нужно указать 30, а для переменной среды — 0x1E или 1E.</span><span class="sxs-lookup"><span data-stu-id="aa0db-334">For example, to limit the heap usage to 30%, the values would be 30 for the JSON file and 0x1E or 1E for the environment variable.</span></span>

### <a name="per-object-heap-limits"></a><span data-ttu-id="aa0db-335">Ограничения для отдельных куч объектов</span><span class="sxs-lookup"><span data-stu-id="aa0db-335">Per-object-heap limits</span></span>

<span data-ttu-id="aa0db-336">Вы можете настраивать допустимый объем использования кучи в ходе сборки мусора для отдельных куч объектов.</span><span class="sxs-lookup"><span data-stu-id="aa0db-336">You can specify the GC's allowable heap usage on a per-object-heap basis.</span></span> <span data-ttu-id="aa0db-337">Это можно сделать для кучи больших (LOH), малых (SOH) и закрепленных (POH) объектов.</span><span class="sxs-lookup"><span data-stu-id="aa0db-337">The different heaps are the large object heap (LOH), small object heap (SOH), and pinned object heap (POH).</span></span>

#### <a name="complus_gcheaphardlimitsoh-complus_gcheaphardlimitloh-complus_gcheaphardlimitpoh"></a><span data-ttu-id="aa0db-338">COMPLUS_GCHeapHardLimitSOH, COMPLUS_GCHeapHardLimitLOH, COMPLUS_GCHeapHardLimitPOH</span><span class="sxs-lookup"><span data-stu-id="aa0db-338">COMPLUS_GCHeapHardLimitSOH, COMPLUS_GCHeapHardLimitLOH, COMPLUS_GCHeapHardLimitPOH</span></span>

- <span data-ttu-id="aa0db-339">Если задано значение любого из этих параметров (`COMPLUS_GCHeapHardLimitSOH`, `COMPLUS_GCHeapHardLimitLOH` или `COMPLUS_GCHeapHardLimitPOH`), также необходимо указать значения `COMPLUS_GCHeapHardLimitSOH` и `COMPLUS_GCHeapHardLimitLOH`.</span><span class="sxs-lookup"><span data-stu-id="aa0db-339">If you specify a value for any of the `COMPLUS_GCHeapHardLimitSOH`, `COMPLUS_GCHeapHardLimitLOH`, or `COMPLUS_GCHeapHardLimitPOH` settings, you must also specify a value for `COMPLUS_GCHeapHardLimitSOH` and `COMPLUS_GCHeapHardLimitLOH`.</span></span> <span data-ttu-id="aa0db-340">Если этого не сделать, во время выполнения произойдет сбой инициализации.</span><span class="sxs-lookup"><span data-stu-id="aa0db-340">If you don't, the runtime will fail to initialize.</span></span>
- <span data-ttu-id="aa0db-341">Значение по умолчанию для `COMPLUS_GCHeapHardLimitPOH` равно 0.</span><span class="sxs-lookup"><span data-stu-id="aa0db-341">The default value for `COMPLUS_GCHeapHardLimitPOH` is 0.</span></span> <span data-ttu-id="aa0db-342">Параметры `COMPLUS_GCHeapHardLimitSOH` и `COMPLUS_GCHeapHardLimitLOH` не имеют значений по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="aa0db-342">`COMPLUS_GCHeapHardLimitSOH` and `COMPLUS_GCHeapHardLimitLOH` don't have default values.</span></span>

| | <span data-ttu-id="aa0db-343">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="aa0db-343">Setting name</span></span> | <span data-ttu-id="aa0db-344">Значения</span><span class="sxs-lookup"><span data-stu-id="aa0db-344">Values</span></span> | <span data-ttu-id="aa0db-345">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="aa0db-345">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="aa0db-346">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="aa0db-346">**Environment variable**</span></span> | `COMPLUS_GCHeapHardLimitSOH` | <span data-ttu-id="aa0db-347">*Шестнадцатеричное значение*</span><span class="sxs-lookup"><span data-stu-id="aa0db-347">*hexadecimal value*</span></span> | <span data-ttu-id="aa0db-348">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="aa0db-348">.NET 5.0</span></span> |
| <span data-ttu-id="aa0db-349">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="aa0db-349">**Environment variable**</span></span> | `COMPLUS_GCHeapHardLimitLOH` | <span data-ttu-id="aa0db-350">*Шестнадцатеричное значение*</span><span class="sxs-lookup"><span data-stu-id="aa0db-350">*hexadecimal value*</span></span> | <span data-ttu-id="aa0db-351">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="aa0db-351">.NET 5.0</span></span> |
| <span data-ttu-id="aa0db-352">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="aa0db-352">**Environment variable**</span></span> | `COMPLUS_GCHeapHardLimitPOH` | <span data-ttu-id="aa0db-353">*Шестнадцатеричное значение*</span><span class="sxs-lookup"><span data-stu-id="aa0db-353">*hexadecimal value*</span></span> | <span data-ttu-id="aa0db-354">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="aa0db-354">.NET 5.0</span></span> |

> [!TIP]
> <span data-ttu-id="aa0db-355">Если вы задаете параметр в виде переменной среды, укажите шестнадцатеричное значение.</span><span class="sxs-lookup"><span data-stu-id="aa0db-355">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="aa0db-356">Например, чтобы указать для куч жесткое ограничение в 200 мебибайт (МиБ), необходимо использовать значение 0xC800000 или C800000.</span><span class="sxs-lookup"><span data-stu-id="aa0db-356">For example, to specify a heap hard limit of 200 mebibytes (MiB), the value would be 0xC800000 or C800000.</span></span>

#### <a name="complus_gcheaphardlimitsohpercent-complus_gcheaphardlimitlohpercent-complus_gcheaphardlimitpohpercent"></a><span data-ttu-id="aa0db-357">COMPLUS_GCHeapHardLimitSOHPercent, COMPLUS_GCHeapHardLimitLOHPercent, COMPLUS_GCHeapHardLimitPOHPercent</span><span class="sxs-lookup"><span data-stu-id="aa0db-357">COMPLUS_GCHeapHardLimitSOHPercent, COMPLUS_GCHeapHardLimitLOHPercent, COMPLUS_GCHeapHardLimitPOHPercent</span></span>

- <span data-ttu-id="aa0db-358">Если задано значение любого из этих параметров (`COMPLUS_GCHeapHardLimitSOHPercent`, `COMPLUS_GCHeapHardLimitLOHPercent` или `COMPLUS_GCHeapHardLimitPOHPercent`), также необходимо указать значения `COMPLUS_GCHeapHardLimitSOHPercent` и `COMPLUS_GCHeapHardLimitLOHPercent`.</span><span class="sxs-lookup"><span data-stu-id="aa0db-358">If you specify a value for any of the `COMPLUS_GCHeapHardLimitSOHPercent`, `COMPLUS_GCHeapHardLimitLOHPercent`, or `COMPLUS_GCHeapHardLimitPOHPercent` settings, you must also specify a value for `COMPLUS_GCHeapHardLimitSOHPercent` and `COMPLUS_GCHeapHardLimitLOHPercent`.</span></span> <span data-ttu-id="aa0db-359">Если этого не сделать, во время выполнения произойдет сбой инициализации.</span><span class="sxs-lookup"><span data-stu-id="aa0db-359">If you don't, the runtime will fail to initialize.</span></span>
- <span data-ttu-id="aa0db-360">Эти параметры игнорируются, если заданы значения параметров `COMPLUS_GCHeapHardLimitSOH`, `COMPLUS_GCHeapHardLimitLOH` и `COMPLUS_GCHeapHardLimitPOH`.</span><span class="sxs-lookup"><span data-stu-id="aa0db-360">These settings are ignored if `COMPLUS_GCHeapHardLimitSOH`, `COMPLUS_GCHeapHardLimitLOH`, and `COMPLUS_GCHeapHardLimitPOH` are specified.</span></span>
- <span data-ttu-id="aa0db-361">Значение 1 означает, что при сборке мусора используется 1 % от общего объема физической памяти для соответствующей кучи объектов.</span><span class="sxs-lookup"><span data-stu-id="aa0db-361">A value of 1 means that GC uses 1% of total physical memory for that object heap.</span></span>
- <span data-ttu-id="aa0db-362">Задаваемое значение должно быть больше нуля и меньше 100.</span><span class="sxs-lookup"><span data-stu-id="aa0db-362">Each value must be greater than zero and less than 100.</span></span> <span data-ttu-id="aa0db-363">Кроме того, сумма всех трех процентных значений должна быть меньше 100.</span><span class="sxs-lookup"><span data-stu-id="aa0db-363">Additionally, the sum of the three percentage values must be less than 100.</span></span> <span data-ttu-id="aa0db-364">В противном случае во время выполнения произойдет сбой инициализации.</span><span class="sxs-lookup"><span data-stu-id="aa0db-364">Otherwise, the runtime will fail to initialize.</span></span>

| | <span data-ttu-id="aa0db-365">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="aa0db-365">Setting name</span></span> | <span data-ttu-id="aa0db-366">Значения</span><span class="sxs-lookup"><span data-stu-id="aa0db-366">Values</span></span> | <span data-ttu-id="aa0db-367">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="aa0db-367">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="aa0db-368">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="aa0db-368">**Environment variable**</span></span> | `COMPLUS_GCHeapHardLimitSOHPercent` | <span data-ttu-id="aa0db-369">*Шестнадцатеричное значение*</span><span class="sxs-lookup"><span data-stu-id="aa0db-369">*hexadecimal value*</span></span> | <span data-ttu-id="aa0db-370">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="aa0db-370">.NET 5.0</span></span> |
| <span data-ttu-id="aa0db-371">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="aa0db-371">**Environment variable**</span></span> | `COMPLUS_GCHeapHardLimitLOHPercent` | <span data-ttu-id="aa0db-372">*Шестнадцатеричное значение*</span><span class="sxs-lookup"><span data-stu-id="aa0db-372">*hexadecimal value*</span></span> | <span data-ttu-id="aa0db-373">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="aa0db-373">.NET 5.0</span></span> |
| <span data-ttu-id="aa0db-374">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="aa0db-374">**Environment variable**</span></span> | `COMPLUS_GCHeapHardLimitPOHPercent` | <span data-ttu-id="aa0db-375">*Шестнадцатеричное значение*</span><span class="sxs-lookup"><span data-stu-id="aa0db-375">*hexadecimal value*</span></span> | <span data-ttu-id="aa0db-376">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="aa0db-376">.NET 5.0</span></span> |

> [!TIP]
> <span data-ttu-id="aa0db-377">Если вы задаете параметр в виде переменной среды, укажите шестнадцатеричное значение.</span><span class="sxs-lookup"><span data-stu-id="aa0db-377">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="aa0db-378">Например, чтобы задать ограничение на использование кучи в 30 %, необходимо использовать значение 0x1E или 1E.</span><span class="sxs-lookup"><span data-stu-id="aa0db-378">For example, to limit the heap usage to 30%, the value would be 0x1E or 1E.</span></span>

### <a name="systemgcretainvmcomplus_gcretainvm"></a><span data-ttu-id="aa0db-379">System.GC.RetainVM/COMPlus_GCRetainVM</span><span class="sxs-lookup"><span data-stu-id="aa0db-379">System.GC.RetainVM/COMPlus_GCRetainVM</span></span>

- <span data-ttu-id="aa0db-380">Настраивает, будут ли удаляемые сегменты помещаться в список ожидания для будущего использования или возвращаться операционной системе (ОС).</span><span class="sxs-lookup"><span data-stu-id="aa0db-380">Configures whether segments that should be deleted are put on a standby list for future use or are released back to the operating system (OS).</span></span>
- <span data-ttu-id="aa0db-381">По умолчанию: возвращение сегментов операционной системе.</span><span class="sxs-lookup"><span data-stu-id="aa0db-381">Default: Release segments back to the operating system.</span></span> <span data-ttu-id="aa0db-382">Это эквивалентно присвоению значения `false`.</span><span class="sxs-lookup"><span data-stu-id="aa0db-382">This is equivalent to setting the value to `false`.</span></span>

| | <span data-ttu-id="aa0db-383">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="aa0db-383">Setting name</span></span> | <span data-ttu-id="aa0db-384">Значения</span><span class="sxs-lookup"><span data-stu-id="aa0db-384">Values</span></span> | <span data-ttu-id="aa0db-385">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="aa0db-385">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="aa0db-386">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="aa0db-386">**runtimeconfig.json**</span></span> | `System.GC.RetainVM` | <span data-ttu-id="aa0db-387">`false` — возвращение операционной системе</span><span class="sxs-lookup"><span data-stu-id="aa0db-387">`false` - release to OS</span></span><br/><span data-ttu-id="aa0db-388">`true` — помещение в режим ожидания</span><span class="sxs-lookup"><span data-stu-id="aa0db-388">`true` - put on standby</span></span> | <span data-ttu-id="aa0db-389">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="aa0db-389">.NET Core 1.0</span></span> |
| <span data-ttu-id="aa0db-390">**Свойство MSBuild**</span><span class="sxs-lookup"><span data-stu-id="aa0db-390">**MSBuild property**</span></span> | `RetainVMGarbageCollection` | <span data-ttu-id="aa0db-391">`false` — возвращение операционной системе</span><span class="sxs-lookup"><span data-stu-id="aa0db-391">`false` - release to OS</span></span><br/><span data-ttu-id="aa0db-392">`true` — помещение в режим ожидания</span><span class="sxs-lookup"><span data-stu-id="aa0db-392">`true` - put on standby</span></span> | <span data-ttu-id="aa0db-393">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="aa0db-393">.NET Core 1.0</span></span> |
| <span data-ttu-id="aa0db-394">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="aa0db-394">**Environment variable**</span></span> | `COMPlus_GCRetainVM` | <span data-ttu-id="aa0db-395">`0` — возвращение операционной системе</span><span class="sxs-lookup"><span data-stu-id="aa0db-395">`0` - release to OS</span></span><br/><span data-ttu-id="aa0db-396">`1` — помещение в режим ожидания</span><span class="sxs-lookup"><span data-stu-id="aa0db-396">`1` - put on standby</span></span> | <span data-ttu-id="aa0db-397">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="aa0db-397">.NET Core 1.0</span></span> |

### <a name="examples"></a><span data-ttu-id="aa0db-398">Примеры</span><span class="sxs-lookup"><span data-stu-id="aa0db-398">Examples</span></span>

<span data-ttu-id="aa0db-399">Файл *runtimeconfig.json*</span><span class="sxs-lookup"><span data-stu-id="aa0db-399">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.RetainVM": true
      }
   }
}
```

<span data-ttu-id="aa0db-400">Файл проекта:</span><span class="sxs-lookup"><span data-stu-id="aa0db-400">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <RetainVMGarbageCollection>true</RetainVMGarbageCollection>
  </PropertyGroup>

</Project>
```

## <a name="large-pages"></a><span data-ttu-id="aa0db-401">Большие страницы</span><span class="sxs-lookup"><span data-stu-id="aa0db-401">Large pages</span></span>

### <a name="complus_gclargepages"></a><span data-ttu-id="aa0db-402">COMPlus_GCLargePages</span><span class="sxs-lookup"><span data-stu-id="aa0db-402">COMPlus_GCLargePages</span></span>

- <span data-ttu-id="aa0db-403">Указывает, следует ли использовать большие страницы, когда задано жесткое ограничение куч.</span><span class="sxs-lookup"><span data-stu-id="aa0db-403">Specifies whether large pages should be used when a heap hard limit is set.</span></span>
- <span data-ttu-id="aa0db-404">По умолчанию: не следует использовать большие страницы, если задан фиксированный предел кучи.</span><span class="sxs-lookup"><span data-stu-id="aa0db-404">Default: Don't use large pages when a heap hard limit is set.</span></span> <span data-ttu-id="aa0db-405">Это эквивалентно присвоению значения `0`.</span><span class="sxs-lookup"><span data-stu-id="aa0db-405">This is equivalent to setting the value to `0`.</span></span>
- <span data-ttu-id="aa0db-406">Это экспериментальный параметр.</span><span class="sxs-lookup"><span data-stu-id="aa0db-406">This is an experimental setting.</span></span>

| | <span data-ttu-id="aa0db-407">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="aa0db-407">Setting name</span></span> | <span data-ttu-id="aa0db-408">Значения</span><span class="sxs-lookup"><span data-stu-id="aa0db-408">Values</span></span> | <span data-ttu-id="aa0db-409">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="aa0db-409">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="aa0db-410">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="aa0db-410">**runtimeconfig.json**</span></span> | <span data-ttu-id="aa0db-411">Н/Д</span><span class="sxs-lookup"><span data-stu-id="aa0db-411">N/A</span></span> | <span data-ttu-id="aa0db-412">Н/Д</span><span class="sxs-lookup"><span data-stu-id="aa0db-412">N/A</span></span> | <span data-ttu-id="aa0db-413">Н/Д</span><span class="sxs-lookup"><span data-stu-id="aa0db-413">N/A</span></span> |
| <span data-ttu-id="aa0db-414">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="aa0db-414">**Environment variable**</span></span> | `COMPlus_GCLargePages` | <span data-ttu-id="aa0db-415">`0` — отключено</span><span class="sxs-lookup"><span data-stu-id="aa0db-415">`0` - disabled</span></span><br/><span data-ttu-id="aa0db-416">`1` — включено</span><span class="sxs-lookup"><span data-stu-id="aa0db-416">`1` - enabled</span></span> | <span data-ttu-id="aa0db-417">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="aa0db-417">.NET Core 3.0</span></span> |

## <a name="large-objects"></a><span data-ttu-id="aa0db-418">Большие объекты</span><span class="sxs-lookup"><span data-stu-id="aa0db-418">Large objects</span></span>

### <a name="complus_gcallowverylargeobjects"></a><span data-ttu-id="aa0db-419">COMPlus_gcAllowVeryLargeObjects</span><span class="sxs-lookup"><span data-stu-id="aa0db-419">COMPlus_gcAllowVeryLargeObjects</span></span>

- <span data-ttu-id="aa0db-420">Настраивает для сборщика мусора на 64-разрядных платформах поддержку массивов, размер которых превышает 2 гигабайта (ГБ).</span><span class="sxs-lookup"><span data-stu-id="aa0db-420">Configures garbage collector support on 64-bit platforms for arrays that are greater than 2 gigabytes (GB) in total size.</span></span>
- <span data-ttu-id="aa0db-421">По умолчанию: сборка мусора поддерживает массивы размером более 2 ГБ.</span><span class="sxs-lookup"><span data-stu-id="aa0db-421">Default: GC supports arrays greater than 2-GB.</span></span> <span data-ttu-id="aa0db-422">Это эквивалентно присвоению значения `1`.</span><span class="sxs-lookup"><span data-stu-id="aa0db-422">This is equivalent to setting the value to `1`.</span></span>
- <span data-ttu-id="aa0db-423">В будущей версии .NET этот параметр может быть объявлен устаревшим.</span><span class="sxs-lookup"><span data-stu-id="aa0db-423">This option may become obsolete in a future version of .NET.</span></span>

| | <span data-ttu-id="aa0db-424">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="aa0db-424">Setting name</span></span> | <span data-ttu-id="aa0db-425">Значения</span><span class="sxs-lookup"><span data-stu-id="aa0db-425">Values</span></span> | <span data-ttu-id="aa0db-426">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="aa0db-426">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="aa0db-427">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="aa0db-427">**runtimeconfig.json**</span></span> | <span data-ttu-id="aa0db-428">Н/Д</span><span class="sxs-lookup"><span data-stu-id="aa0db-428">N/A</span></span> | <span data-ttu-id="aa0db-429">Н/Д</span><span class="sxs-lookup"><span data-stu-id="aa0db-429">N/A</span></span> | <span data-ttu-id="aa0db-430">Н/Д</span><span class="sxs-lookup"><span data-stu-id="aa0db-430">N/A</span></span> |
| <span data-ttu-id="aa0db-431">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="aa0db-431">**Environment variable**</span></span> | `COMPlus_gcAllowVeryLargeObjects` | <span data-ttu-id="aa0db-432">`1` — включено</span><span class="sxs-lookup"><span data-stu-id="aa0db-432">`1` - enabled</span></span><br/> <span data-ttu-id="aa0db-433">`0` — отключено</span><span class="sxs-lookup"><span data-stu-id="aa0db-433">`0` - disabled</span></span> | <span data-ttu-id="aa0db-434">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="aa0db-434">.NET Core 1.0</span></span> |
| <span data-ttu-id="aa0db-435">**app.config для .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="aa0db-435">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="aa0db-436">gcAllowVeryLargeObjects</span><span class="sxs-lookup"><span data-stu-id="aa0db-436">gcAllowVeryLargeObjects</span></span>](../../framework/configure-apps/file-schema/runtime/gcallowverylargeobjects-element.md) | <span data-ttu-id="aa0db-437">`1` — включено</span><span class="sxs-lookup"><span data-stu-id="aa0db-437">`1` - enabled</span></span><br/> <span data-ttu-id="aa0db-438">`0` — отключено</span><span class="sxs-lookup"><span data-stu-id="aa0db-438">`0` - disabled</span></span> | <span data-ttu-id="aa0db-439">.NET Framework 4,5</span><span class="sxs-lookup"><span data-stu-id="aa0db-439">.NET Framework 4.5</span></span> |

## <a name="large-object-heap-threshold"></a><span data-ttu-id="aa0db-440">Пороговое значение кучи больших объектов</span><span class="sxs-lookup"><span data-stu-id="aa0db-440">Large object heap threshold</span></span>

### <a name="systemgclohthresholdcomplus_gclohthreshold"></a><span data-ttu-id="aa0db-441">System.GC.LOHThreshold/COMPlus_GCLOHThreshold</span><span class="sxs-lookup"><span data-stu-id="aa0db-441">System.GC.LOHThreshold/COMPlus_GCLOHThreshold</span></span>

- <span data-ttu-id="aa0db-442">Указывает пороговый размер (в байтах), при котором объекты попадают в кучу больших объектов (LOH).</span><span class="sxs-lookup"><span data-stu-id="aa0db-442">Specifies the threshold size, in bytes, that causes objects to go on the large object heap (LOH).</span></span>
- <span data-ttu-id="aa0db-443">Пороговое значение по умолчанию — 85 000 байт.</span><span class="sxs-lookup"><span data-stu-id="aa0db-443">The default threshold is 85,000 bytes.</span></span>
- <span data-ttu-id="aa0db-444">Указанное значение должно быть больше порогового значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="aa0db-444">The value you specify must be larger than the default threshold.</span></span>

| | <span data-ttu-id="aa0db-445">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="aa0db-445">Setting name</span></span> | <span data-ttu-id="aa0db-446">Значения</span><span class="sxs-lookup"><span data-stu-id="aa0db-446">Values</span></span> | <span data-ttu-id="aa0db-447">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="aa0db-447">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="aa0db-448">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="aa0db-448">**runtimeconfig.json**</span></span> | `System.GC.LOHThreshold` | <span data-ttu-id="aa0db-449">*Десятичное значение*</span><span class="sxs-lookup"><span data-stu-id="aa0db-449">*decimal value*</span></span> | <span data-ttu-id="aa0db-450">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="aa0db-450">.NET Core 1.0</span></span> |
| <span data-ttu-id="aa0db-451">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="aa0db-451">**Environment variable**</span></span> | `COMPlus_GCLOHThreshold` | <span data-ttu-id="aa0db-452">*Шестнадцатеричное значение*</span><span class="sxs-lookup"><span data-stu-id="aa0db-452">*hexadecimal value*</span></span> | <span data-ttu-id="aa0db-453">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="aa0db-453">.NET Core 1.0</span></span> |
| <span data-ttu-id="aa0db-454">**app.config для .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="aa0db-454">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="aa0db-455">GCLOHThreshold</span><span class="sxs-lookup"><span data-stu-id="aa0db-455">GCLOHThreshold</span></span>](../../framework/configure-apps/file-schema/runtime/gclohthreshold-element.md) | <span data-ttu-id="aa0db-456">*Десятичное значение*</span><span class="sxs-lookup"><span data-stu-id="aa0db-456">*decimal value*</span></span> | <span data-ttu-id="aa0db-457">.NET Framework 4.8</span><span class="sxs-lookup"><span data-stu-id="aa0db-457">.NET Framework 4.8</span></span> |

<span data-ttu-id="aa0db-458">Пример.</span><span class="sxs-lookup"><span data-stu-id="aa0db-458">Example:</span></span>

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
> <span data-ttu-id="aa0db-459">Если вы задаете параметр в *runtimeconfig.json*, укажите десятичное значение.</span><span class="sxs-lookup"><span data-stu-id="aa0db-459">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="aa0db-460">Если вы задаете параметр в виде переменной среды, укажите шестнадцатеричное значение.</span><span class="sxs-lookup"><span data-stu-id="aa0db-460">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="aa0db-461">Например, чтобы задать порог размера в 120 000 байт, для JSON-файла нужно указать значение 120000, а для переменной среды — значение 0x1D4C0 или 1D4C0.</span><span class="sxs-lookup"><span data-stu-id="aa0db-461">For example, to set a threshold size of 120,000 bytes, the values would be 120000 for the JSON file and 0x1D4C0 or 1D4C0 for the environment variable.</span></span>

## <a name="standalone-gc"></a><span data-ttu-id="aa0db-462">Автономный сборщик мусора</span><span class="sxs-lookup"><span data-stu-id="aa0db-462">Standalone GC</span></span>

### <a name="complus_gcname"></a><span data-ttu-id="aa0db-463">COMPlus_GCName</span><span class="sxs-lookup"><span data-stu-id="aa0db-463">COMPlus_GCName</span></span>

- <span data-ttu-id="aa0db-464">Указывает путь к библиотеке, содержащей сборщик мусора, который среда выполнения намеревается загрузить.</span><span class="sxs-lookup"><span data-stu-id="aa0db-464">Specifies a path to the library containing the garbage collector that the runtime intends to load.</span></span>
- <span data-ttu-id="aa0db-465">Дополнительные сведения см. в статье [Проектирования загрузчика автономного сборщика мусора](https://github.com/dotnet/runtime/blob/master/docs/design/features/standalone-gc-loading.md).</span><span class="sxs-lookup"><span data-stu-id="aa0db-465">For more information, see [Standalone GC loader design](https://github.com/dotnet/runtime/blob/master/docs/design/features/standalone-gc-loading.md).</span></span>

| | <span data-ttu-id="aa0db-466">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="aa0db-466">Setting name</span></span> | <span data-ttu-id="aa0db-467">Значения</span><span class="sxs-lookup"><span data-stu-id="aa0db-467">Values</span></span> | <span data-ttu-id="aa0db-468">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="aa0db-468">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="aa0db-469">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="aa0db-469">**runtimeconfig.json**</span></span> | <span data-ttu-id="aa0db-470">Н/Д</span><span class="sxs-lookup"><span data-stu-id="aa0db-470">N/A</span></span> | <span data-ttu-id="aa0db-471">Н/Д</span><span class="sxs-lookup"><span data-stu-id="aa0db-471">N/A</span></span> | <span data-ttu-id="aa0db-472">Н/Д</span><span class="sxs-lookup"><span data-stu-id="aa0db-472">N/A</span></span> |
| <span data-ttu-id="aa0db-473">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="aa0db-473">**Environment variable**</span></span> | `COMPlus_GCName` | <span data-ttu-id="aa0db-474">*string_path*</span><span class="sxs-lookup"><span data-stu-id="aa0db-474">*string_path*</span></span> | <span data-ttu-id="aa0db-475">.NET Core 2.0;</span><span class="sxs-lookup"><span data-stu-id="aa0db-475">.NET Core 2.0</span></span> |
