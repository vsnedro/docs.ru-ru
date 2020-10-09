---
title: Параметры конфигурации компиляции
description: Сведения о параметрах времени выполнения, определяющих, как JIT-компилятор работает для приложений .NET Core.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: e5f9e1245b749864787fb808527d022665197edf
ms.sourcegitcommit: 4d45bda8cd9558ea8af4be591e3d5a29360c1ece
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/02/2020
ms.locfileid: "91654846"
---
# <a name="run-time-configuration-options-for-compilation"></a><span data-ttu-id="bce76-103">Параметры конфигурации времени выполнения для компиляции</span><span class="sxs-lookup"><span data-stu-id="bce76-103">Run-time configuration options for compilation</span></span>

## <a name="tiered-compilation"></a><span data-ttu-id="bce76-104">Многоуровневая компиляция</span><span class="sxs-lookup"><span data-stu-id="bce76-104">Tiered compilation</span></span>

- <span data-ttu-id="bce76-105">Указывает, использует ли JIT-компилятор [многоуровневую компиляцию](../whats-new/dotnet-core-3-0.md#tiered-compilation).</span><span class="sxs-lookup"><span data-stu-id="bce76-105">Configures whether the just-in-time (JIT) compiler uses [tiered compilation](../whats-new/dotnet-core-3-0.md#tiered-compilation).</span></span> <span data-ttu-id="bce76-106">Многоуровневая компиляция обеспечивает переход методов по двум уровням.</span><span class="sxs-lookup"><span data-stu-id="bce76-106">Tiered compilation transitions methods through two tiers:</span></span>
  - <span data-ttu-id="bce76-107">Первый уровень создает код быстрее ([быстрая JIT-компиляция](#quick-jit)) или загружает предварительно скомпилированный код ([ReadyToRun](#readytorun)).</span><span class="sxs-lookup"><span data-stu-id="bce76-107">The first tier generates code more quickly ([quick JIT](#quick-jit)) or loads pre-compiled code ([ReadyToRun](#readytorun)).</span></span>
  - <span data-ttu-id="bce76-108">Второй уровень создает оптимизированный код в фоновом режиме (JIT-компиляция с оптимизацией).</span><span class="sxs-lookup"><span data-stu-id="bce76-108">The second tier generates optimized code in the background ("optimizing JIT").</span></span>
- <span data-ttu-id="bce76-109">В .NET Core 3.0 и более поздних версий многоуровневая компиляция включена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="bce76-109">In .NET Core 3.0 and later, tiered compilation is enabled by default.</span></span>
- <span data-ttu-id="bce76-110">В .NET Core 2.1 и 2.2 многоуровневая компиляция отключена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="bce76-110">In .NET Core 2.1 and 2.2, tiered compilation is disabled by default.</span></span>
- <span data-ttu-id="bce76-111">Дополнительные сведения см. в [руководстве по многоуровневой компиляции](https://github.com/dotnet/runtime/blob/master/docs/design/features/tiered-compilation.md).</span><span class="sxs-lookup"><span data-stu-id="bce76-111">For more information, see the [Tiered compilation guide](https://github.com/dotnet/runtime/blob/master/docs/design/features/tiered-compilation.md).</span></span>

| | <span data-ttu-id="bce76-112">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="bce76-112">Setting name</span></span> | <span data-ttu-id="bce76-113">Значения</span><span class="sxs-lookup"><span data-stu-id="bce76-113">Values</span></span> |
| - | - | - |
| <span data-ttu-id="bce76-114">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="bce76-114">**runtimeconfig.json**</span></span> | `System.Runtime.TieredCompilation` | <span data-ttu-id="bce76-115">`true` — включено</span><span class="sxs-lookup"><span data-stu-id="bce76-115">`true` - enabled</span></span><br/><span data-ttu-id="bce76-116">`false` — отключено</span><span class="sxs-lookup"><span data-stu-id="bce76-116">`false` - disabled</span></span> |
| <span data-ttu-id="bce76-117">**Свойство MSBuild**</span><span class="sxs-lookup"><span data-stu-id="bce76-117">**MSBuild property**</span></span> | `TieredCompilation` | <span data-ttu-id="bce76-118">`true` — включено</span><span class="sxs-lookup"><span data-stu-id="bce76-118">`true` - enabled</span></span><br/><span data-ttu-id="bce76-119">`false` — отключено</span><span class="sxs-lookup"><span data-stu-id="bce76-119">`false` - disabled</span></span> |
| <span data-ttu-id="bce76-120">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="bce76-120">**Environment variable**</span></span> | `COMPlus_TieredCompilation` | <span data-ttu-id="bce76-121">`1` — включено</span><span class="sxs-lookup"><span data-stu-id="bce76-121">`1` - enabled</span></span><br/><span data-ttu-id="bce76-122">`0` — отключено</span><span class="sxs-lookup"><span data-stu-id="bce76-122">`0` - disabled</span></span> |

### <a name="examples"></a><span data-ttu-id="bce76-123">Примеры</span><span class="sxs-lookup"><span data-stu-id="bce76-123">Examples</span></span>

<span data-ttu-id="bce76-124">Файл *runtimeconfig.json*</span><span class="sxs-lookup"><span data-stu-id="bce76-124">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Runtime.TieredCompilation": false
      }
   }
}
```

<span data-ttu-id="bce76-125">Файл проекта:</span><span class="sxs-lookup"><span data-stu-id="bce76-125">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TieredCompilation>false</TieredCompilation>
  </PropertyGroup>

</Project>
```

## <a name="quick-jit"></a><span data-ttu-id="bce76-126">Быстрая JIT-компиляция</span><span class="sxs-lookup"><span data-stu-id="bce76-126">Quick JIT</span></span>

- <span data-ttu-id="bce76-127">Указывает, использует ли JIT-компилятор *быструю JIT-компиляцию*.</span><span class="sxs-lookup"><span data-stu-id="bce76-127">Configures whether the JIT compiler uses *quick JIT*.</span></span> <span data-ttu-id="bce76-128">Для методов, которые не содержат циклы и для которых предварительно скомпилированный код недоступен, быстрая JIT-компиляция компилирует их быстрее, но без оптимизации.</span><span class="sxs-lookup"><span data-stu-id="bce76-128">For methods that don't contain loops and for which pre-compiled code is not available, quick JIT compiles them more quickly but without optimizations.</span></span>
- <span data-ttu-id="bce76-129">Включение быстрой JIT-компиляции сокращает время запуска, однако создаваемый код может обладать низкой производительностью.</span><span class="sxs-lookup"><span data-stu-id="bce76-129">Enabling quick JIT decreases startup time but can produce code with degraded performance characteristics.</span></span> <span data-ttu-id="bce76-130">Например, код может использовать больше пространства стека, выделять больше памяти и работать медленнее.</span><span class="sxs-lookup"><span data-stu-id="bce76-130">For example, the code may use more stack space, allocate more memory, and run slower.</span></span>
- <span data-ttu-id="bce76-131">Если быстрая JIT-компиляция отключена, но включена [многоуровневая компиляция](#tiered-compilation), в многоуровневой компиляции участвует только предварительно скомпилированный код.</span><span class="sxs-lookup"><span data-stu-id="bce76-131">If quick JIT is disabled but [tiered compilation](#tiered-compilation) is enabled, only pre-compiled code participates in tiered compilation.</span></span> <span data-ttu-id="bce76-132">Если метод не был предварительно скомпилирован с помощью [ReadyToRun](#readytorun), то поведение JIT будет таким же, как если бы [многоуровневая компиляция](#tiered-compilation) была отключена.</span><span class="sxs-lookup"><span data-stu-id="bce76-132">If a method is not pre-compiled with [ReadyToRun](#readytorun), the JIT behavior is the same as if [tiered compilation](#tiered-compilation) were disabled.</span></span>
- <span data-ttu-id="bce76-133">В .NET Core 3.0 и более поздних версий быстрая JIT-компиляция включена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="bce76-133">In .NET Core 3.0 and later, quick JIT is enabled by default.</span></span>
- <span data-ttu-id="bce76-134">В .NET Core 2.1 и 2.2 быстрая JIT-компиляция отключена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="bce76-134">In .NET Core 2.1 and 2.2, quick JIT is disabled by default.</span></span>

| | <span data-ttu-id="bce76-135">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="bce76-135">Setting name</span></span> | <span data-ttu-id="bce76-136">Значения</span><span class="sxs-lookup"><span data-stu-id="bce76-136">Values</span></span> |
| - | - | - |
| <span data-ttu-id="bce76-137">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="bce76-137">**runtimeconfig.json**</span></span> | `System.Runtime.TieredCompilation.QuickJit` | <span data-ttu-id="bce76-138">`true` — включено</span><span class="sxs-lookup"><span data-stu-id="bce76-138">`true` - enabled</span></span><br/><span data-ttu-id="bce76-139">`false` — отключено</span><span class="sxs-lookup"><span data-stu-id="bce76-139">`false` - disabled</span></span> |
| <span data-ttu-id="bce76-140">**Свойство MSBuild**</span><span class="sxs-lookup"><span data-stu-id="bce76-140">**MSBuild property**</span></span> | `TieredCompilationQuickJit` | <span data-ttu-id="bce76-141">`true` — включено</span><span class="sxs-lookup"><span data-stu-id="bce76-141">`true` - enabled</span></span><br/><span data-ttu-id="bce76-142">`false` — отключено</span><span class="sxs-lookup"><span data-stu-id="bce76-142">`false` - disabled</span></span> |
| <span data-ttu-id="bce76-143">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="bce76-143">**Environment variable**</span></span> | `COMPlus_TC_QuickJit` | <span data-ttu-id="bce76-144">`1` — включено</span><span class="sxs-lookup"><span data-stu-id="bce76-144">`1` - enabled</span></span><br/><span data-ttu-id="bce76-145">`0` — отключено</span><span class="sxs-lookup"><span data-stu-id="bce76-145">`0` - disabled</span></span> |

### <a name="examples"></a><span data-ttu-id="bce76-146">Примеры</span><span class="sxs-lookup"><span data-stu-id="bce76-146">Examples</span></span>

<span data-ttu-id="bce76-147">Файл *runtimeconfig.json*</span><span class="sxs-lookup"><span data-stu-id="bce76-147">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Runtime.TieredCompilation.QuickJit": false
      }
   }
}
```

<span data-ttu-id="bce76-148">Файл проекта:</span><span class="sxs-lookup"><span data-stu-id="bce76-148">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TieredCompilationQuickJit>false</TieredCompilationQuickJit>
  </PropertyGroup>

</Project>
```

## <a name="quick-jit-for-loops"></a><span data-ttu-id="bce76-149">Быстрая JIT-компиляция для циклов</span><span class="sxs-lookup"><span data-stu-id="bce76-149">Quick JIT for loops</span></span>

- <span data-ttu-id="bce76-150">Указывает, использует ли JIT-компилятор быструю JIT-компиляцию для методов, содержащих циклы.</span><span class="sxs-lookup"><span data-stu-id="bce76-150">Configures whether the JIT compiler uses quick JIT on methods that contain loops.</span></span>
- <span data-ttu-id="bce76-151">Включение быстрой JIT-компиляции для циклов может повысить производительность при запуске.</span><span class="sxs-lookup"><span data-stu-id="bce76-151">Enabling quick JIT for loops may improve startup performance.</span></span> <span data-ttu-id="bce76-152">Однако длительные циклы могут задерживаться на участках менее оптимизированного кода.</span><span class="sxs-lookup"><span data-stu-id="bce76-152">However, long-running loops can get stuck in less-optimized code for long periods.</span></span>
- <span data-ttu-id="bce76-153">Если [быстрая JIT-компиляция](#quick-jit) отключена, этот параметр не действует.</span><span class="sxs-lookup"><span data-stu-id="bce76-153">If [quick JIT](#quick-jit) is disabled, this setting has no effect.</span></span>
- <span data-ttu-id="bce76-154">Если этот параметр не задан, быстрая JIT-компиляция не используется для методов, содержащих циклы.</span><span class="sxs-lookup"><span data-stu-id="bce76-154">If you omit this setting, quick JIT is not used for methods that contain loops.</span></span> <span data-ttu-id="bce76-155">Это эквивалентно присвоению значения `false`.</span><span class="sxs-lookup"><span data-stu-id="bce76-155">This is equivalent to setting the value to `false`.</span></span>

| | <span data-ttu-id="bce76-156">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="bce76-156">Setting name</span></span> | <span data-ttu-id="bce76-157">Значения</span><span class="sxs-lookup"><span data-stu-id="bce76-157">Values</span></span> |
| - | - | - |
| <span data-ttu-id="bce76-158">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="bce76-158">**runtimeconfig.json**</span></span> | `System.Runtime.TieredCompilation.QuickJitForLoops` | <span data-ttu-id="bce76-159">`false` — отключено</span><span class="sxs-lookup"><span data-stu-id="bce76-159">`false` - disabled</span></span><br/><span data-ttu-id="bce76-160">`true` — включено</span><span class="sxs-lookup"><span data-stu-id="bce76-160">`true` - enabled</span></span> |
| <span data-ttu-id="bce76-161">**Свойство MSBuild**</span><span class="sxs-lookup"><span data-stu-id="bce76-161">**MSBuild property**</span></span> | `TieredCompilationQuickJitForLoops` | <span data-ttu-id="bce76-162">`false` — отключено</span><span class="sxs-lookup"><span data-stu-id="bce76-162">`false` - disabled</span></span><br/><span data-ttu-id="bce76-163">`true` — включено</span><span class="sxs-lookup"><span data-stu-id="bce76-163">`true` - enabled</span></span> |
| <span data-ttu-id="bce76-164">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="bce76-164">**Environment variable**</span></span> | `COMPlus_TC_QuickJitForLoops` | <span data-ttu-id="bce76-165">`0` — отключено</span><span class="sxs-lookup"><span data-stu-id="bce76-165">`0` - disabled</span></span><br/><span data-ttu-id="bce76-166">`1` — включено</span><span class="sxs-lookup"><span data-stu-id="bce76-166">`1` - enabled</span></span> |

### <a name="examples"></a><span data-ttu-id="bce76-167">Примеры</span><span class="sxs-lookup"><span data-stu-id="bce76-167">Examples</span></span>

<span data-ttu-id="bce76-168">Файл *runtimeconfig.json*</span><span class="sxs-lookup"><span data-stu-id="bce76-168">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Runtime.TieredCompilation.QuickJitForLoops": false
      }
   }
}
```

<span data-ttu-id="bce76-169">Файл проекта:</span><span class="sxs-lookup"><span data-stu-id="bce76-169">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TieredCompilationQuickJitForLoops>true</TieredCompilationQuickJitForLoops>
  </PropertyGroup>

</Project>
```

## <a name="readytorun"></a><span data-ttu-id="bce76-170">ReadyToRun</span><span class="sxs-lookup"><span data-stu-id="bce76-170">ReadyToRun</span></span>

- <span data-ttu-id="bce76-171">Указывает, использует ли среда выполнения .NET Core предварительно скомпилированный код для образов с доступными данными ReadyToRun.</span><span class="sxs-lookup"><span data-stu-id="bce76-171">Configures whether the .NET Core runtime uses pre-compiled code for images with available ReadyToRun data.</span></span> <span data-ttu-id="bce76-172">При отключении этого параметра среда выполнения будет принудительно выполнять JIT-компиляцию платформенного кода.</span><span class="sxs-lookup"><span data-stu-id="bce76-172">Disabling this option forces the runtime to JIT-compile framework code.</span></span>
- <span data-ttu-id="bce76-173">Дополнительные сведения см. в статье о [ReadyToRun](../deploying/ready-to-run.md).</span><span class="sxs-lookup"><span data-stu-id="bce76-173">For more information, see [Ready to Run](../deploying/ready-to-run.md).</span></span>
- <span data-ttu-id="bce76-174">Если этот параметр не задан, .NET использует данные ReadyToRun, когда они доступны.</span><span class="sxs-lookup"><span data-stu-id="bce76-174">If you omit this setting, .NET uses ReadyToRun data when it's available.</span></span> <span data-ttu-id="bce76-175">Это эквивалентно присвоению значения `1`.</span><span class="sxs-lookup"><span data-stu-id="bce76-175">This is equivalent to setting the value to `1`.</span></span>

| | <span data-ttu-id="bce76-176">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="bce76-176">Setting name</span></span> | <span data-ttu-id="bce76-177">Значения</span><span class="sxs-lookup"><span data-stu-id="bce76-177">Values</span></span> |
| - | - | - |
| <span data-ttu-id="bce76-178">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="bce76-178">**Environment variable**</span></span> | `COMPlus_ReadyToRun` | <span data-ttu-id="bce76-179">`1` — включено</span><span class="sxs-lookup"><span data-stu-id="bce76-179">`1` - enabled</span></span><br/><span data-ttu-id="bce76-180">`0` — отключено</span><span class="sxs-lookup"><span data-stu-id="bce76-180">`0` - disabled</span></span> |
