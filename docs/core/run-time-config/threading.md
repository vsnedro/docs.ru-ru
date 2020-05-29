---
title: Параметры конфигурации потоков
description: Сведения о параметрах времени выполнения, определяющих использование потоков для приложений .NET Core.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 1c7c16993a07ef95223481791153b75ab2f61533
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/21/2020
ms.locfileid: "83761932"
---
# <a name="run-time-configuration-options-for-threading"></a><span data-ttu-id="8979c-103">Параметры конфигурации времени выполнения для потоков</span><span class="sxs-lookup"><span data-stu-id="8979c-103">Run-time configuration options for threading</span></span>

## <a name="cpu-groups"></a><span data-ttu-id="8979c-104">Группы ЦП</span><span class="sxs-lookup"><span data-stu-id="8979c-104">CPU groups</span></span>

- <span data-ttu-id="8979c-105">Определяет, выполняется ли автоматическое распределение потоков между группами ЦП.</span><span class="sxs-lookup"><span data-stu-id="8979c-105">Configures whether threads are automatically distributed across CPU groups.</span></span>
- <span data-ttu-id="8979c-106">Если этот параметр не задан, потоки не распределяются между группами ЦП.</span><span class="sxs-lookup"><span data-stu-id="8979c-106">If you omit this setting, threads are not distributed across CPU groups.</span></span> <span data-ttu-id="8979c-107">Это эквивалентно присвоению значения `0`.</span><span class="sxs-lookup"><span data-stu-id="8979c-107">This is equivalent to setting the value to `0`.</span></span>

| | <span data-ttu-id="8979c-108">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="8979c-108">Setting name</span></span> | <span data-ttu-id="8979c-109">Значения</span><span class="sxs-lookup"><span data-stu-id="8979c-109">Values</span></span> |
| - | - | - |
| <span data-ttu-id="8979c-110">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="8979c-110">**runtimeconfig.json**</span></span> | <span data-ttu-id="8979c-111">Н/Д</span><span class="sxs-lookup"><span data-stu-id="8979c-111">N/A</span></span> | <span data-ttu-id="8979c-112">Н/Д</span><span class="sxs-lookup"><span data-stu-id="8979c-112">N/A</span></span> |
| <span data-ttu-id="8979c-113">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="8979c-113">**Environment variable**</span></span> | `COMPlus_Thread_UseAllCpuGroups` | <span data-ttu-id="8979c-114">`0` — отключено</span><span class="sxs-lookup"><span data-stu-id="8979c-114">`0` - disabled</span></span><br/><span data-ttu-id="8979c-115">`1` — включено</span><span class="sxs-lookup"><span data-stu-id="8979c-115">`1` - enabled</span></span> |

## <a name="minimum-threads"></a><span data-ttu-id="8979c-116">Минимальное число потоков</span><span class="sxs-lookup"><span data-stu-id="8979c-116">Minimum threads</span></span>

- <span data-ttu-id="8979c-117">Указывает минимальное число потоков для рабочего пула потоков.</span><span class="sxs-lookup"><span data-stu-id="8979c-117">Specifies the minimum number of threads for the worker thread pool.</span></span>
- <span data-ttu-id="8979c-118">Соответствует методу <xref:System.Threading.ThreadPool.SetMinThreads%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="8979c-118">Corresponds to the <xref:System.Threading.ThreadPool.SetMinThreads%2A?displayProperty=nameWithType> method.</span></span>

| | <span data-ttu-id="8979c-119">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="8979c-119">Setting name</span></span> | <span data-ttu-id="8979c-120">Значения</span><span class="sxs-lookup"><span data-stu-id="8979c-120">Values</span></span> |
| - | - | - |
| <span data-ttu-id="8979c-121">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="8979c-121">**runtimeconfig.json**</span></span> | `System.Threading.ThreadPool.MinThreads` | <span data-ttu-id="8979c-122">Целочисленное значение, представляющее минимальное число потоков.</span><span class="sxs-lookup"><span data-stu-id="8979c-122">An integer that represents the minimum number of threads</span></span> |
| <span data-ttu-id="8979c-123">**Свойство MSBuild**</span><span class="sxs-lookup"><span data-stu-id="8979c-123">**MSBuild property**</span></span> | `ThreadPoolMinThreads` | <span data-ttu-id="8979c-124">Целочисленное значение, представляющее минимальное число потоков.</span><span class="sxs-lookup"><span data-stu-id="8979c-124">An integer that represents the minimum number of threads</span></span> |
| <span data-ttu-id="8979c-125">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="8979c-125">**Environment variable**</span></span> | <span data-ttu-id="8979c-126">Н/Д</span><span class="sxs-lookup"><span data-stu-id="8979c-126">N/A</span></span> | <span data-ttu-id="8979c-127">Н/Д</span><span class="sxs-lookup"><span data-stu-id="8979c-127">N/A</span></span> |

### <a name="examples"></a><span data-ttu-id="8979c-128">Примеры</span><span class="sxs-lookup"><span data-stu-id="8979c-128">Examples</span></span>

<span data-ttu-id="8979c-129">Файл *runtimeconfig.json*</span><span class="sxs-lookup"><span data-stu-id="8979c-129">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Threading.ThreadPool.MinThreads": 4
      }
   }
}
```

<span data-ttu-id="8979c-130">Файл проекта:</span><span class="sxs-lookup"><span data-stu-id="8979c-130">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ThreadPoolMinThreads>4</ThreadPoolMinThreads>
  </PropertyGroup>

</Project>
```

## <a name="maximum-threads"></a><span data-ttu-id="8979c-131">Максимальное число потоков</span><span class="sxs-lookup"><span data-stu-id="8979c-131">Maximum threads</span></span>

- <span data-ttu-id="8979c-132">Указывает максимальное число потоков для рабочего пула потоков.</span><span class="sxs-lookup"><span data-stu-id="8979c-132">Specifies the maximum number of threads for the worker thread pool.</span></span>
- <span data-ttu-id="8979c-133">Соответствует методу <xref:System.Threading.ThreadPool.SetMaxThreads%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="8979c-133">Corresponds to the <xref:System.Threading.ThreadPool.SetMaxThreads%2A?displayProperty=nameWithType> method.</span></span>

| | <span data-ttu-id="8979c-134">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="8979c-134">Setting name</span></span> | <span data-ttu-id="8979c-135">Значения</span><span class="sxs-lookup"><span data-stu-id="8979c-135">Values</span></span> |
| - | - | - |
| <span data-ttu-id="8979c-136">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="8979c-136">**runtimeconfig.json**</span></span> | `System.Threading.ThreadPool.MaxThreads` | <span data-ttu-id="8979c-137">Целочисленное значение, представляющее максимальное число потоков.</span><span class="sxs-lookup"><span data-stu-id="8979c-137">An integer that represents the maximum number of threads</span></span> |
| <span data-ttu-id="8979c-138">**Свойство MSBuild**</span><span class="sxs-lookup"><span data-stu-id="8979c-138">**MSBuild property**</span></span> | `ThreadPoolMaxThreads` | <span data-ttu-id="8979c-139">Целочисленное значение, представляющее максимальное число потоков.</span><span class="sxs-lookup"><span data-stu-id="8979c-139">An integer that represents the maximum number of threads</span></span> |
| <span data-ttu-id="8979c-140">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="8979c-140">**Environment variable**</span></span> | <span data-ttu-id="8979c-141">Н/Д</span><span class="sxs-lookup"><span data-stu-id="8979c-141">N/A</span></span> | <span data-ttu-id="8979c-142">Н/Д</span><span class="sxs-lookup"><span data-stu-id="8979c-142">N/A</span></span> |

### <a name="examples"></a><span data-ttu-id="8979c-143">Примеры</span><span class="sxs-lookup"><span data-stu-id="8979c-143">Examples</span></span>

<span data-ttu-id="8979c-144">Файл *runtimeconfig.json*</span><span class="sxs-lookup"><span data-stu-id="8979c-144">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Threading.ThreadPool.MaxThreads": 20
      }
   }
}
```

<span data-ttu-id="8979c-145">Файл проекта:</span><span class="sxs-lookup"><span data-stu-id="8979c-145">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ThreadPoolMaxThreads>20</ThreadPoolMaxThreads>
  </PropertyGroup>

</Project>
```
