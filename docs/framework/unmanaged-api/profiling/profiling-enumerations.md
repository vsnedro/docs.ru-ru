---
title: Перечисления профилирования
ms.date: 03/30/2017
helpviewer_keywords:
- profiling enumerations [.NET Framework]
- enumerations [.NET Framework profiling]
- unmanaged enumerations [.NET Framework], profiling
ms.assetid: 8d5f9570-9853-4ce8-8101-df235d5b258e
ms.openlocfilehash: 8956a09cf76aa54452e8c020239e650e55d8a0d1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95701618"
---
# <a name="profiling-enumerations"></a><span data-ttu-id="2f132-102">Перечисления профилирования</span><span class="sxs-lookup"><span data-stu-id="2f132-102">Profiling Enumerations</span></span>

<span data-ttu-id="2f132-103">В этом разделе описываются неуправляемые перечисления, которые использует API профилирования.</span><span class="sxs-lookup"><span data-stu-id="2f132-103">This section describes the unmanaged enumerations that the profiling API uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2f132-104">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="2f132-104">In This Section</span></span>  

 [<span data-ttu-id="2f132-105">Перечисление COR_PRF_CLAUSE_TYPE</span><span class="sxs-lookup"><span data-stu-id="2f132-105">COR_PRF_CLAUSE_TYPE Enumeration</span></span>](cor-prf-clause-type-enumeration.md)  
 <span data-ttu-id="2f132-106">Указывает тип предложения исключения, код которого был только что введен или удален.</span><span class="sxs-lookup"><span data-stu-id="2f132-106">Indicates the type of exception clause that the code has just entered or left.</span></span>  
  
 [<span data-ttu-id="2f132-107">Перечисление COR_PRF_CODEGEN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="2f132-107">COR_PRF_CODEGEN_FLAGS Enumeration</span></span>](cor-prf-codegen-flags-enumeration.md)  
 <span data-ttu-id="2f132-108">Определяет флаги создания кода, которые можно задать с помощью метода [икорпрофилерфунктионконтрол:: SetCodegenFlags](icorprofilerfunctioncontrol-setcodegenflags-method.md) .</span><span class="sxs-lookup"><span data-stu-id="2f132-108">Defines the code generation flags that can be set with the [ICorProfilerFunctionControl::SetCodegenFlags](icorprofilerfunctioncontrol-setcodegenflags-method.md) method.</span></span>  
  
 [<span data-ttu-id="2f132-109">Перечисление COR_PRF_FINALIZER_FLAGS</span><span class="sxs-lookup"><span data-stu-id="2f132-109">COR_PRF_FINALIZER_FLAGS Enumeration</span></span>](cor-prf-finalizer-flags-enumeration.md)  
 <span data-ttu-id="2f132-110">Описывает метод завершения для объекта.</span><span class="sxs-lookup"><span data-stu-id="2f132-110">Describes the finalizer for an object.</span></span>  
  
 [<span data-ttu-id="2f132-111">Перечисление COR_PRF_GC_GENERATION</span><span class="sxs-lookup"><span data-stu-id="2f132-111">COR_PRF_GC_GENERATION Enumeration</span></span>](cor-prf-gc-generation-enumeration.md)  
 <span data-ttu-id="2f132-112">Идентифицирует создание сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="2f132-112">Identifies a garbage collection generation.</span></span>  
  
 [<span data-ttu-id="2f132-113">Перечисление COR_PRF_GC_REASON</span><span class="sxs-lookup"><span data-stu-id="2f132-113">COR_PRF_GC_REASON Enumeration</span></span>](cor-prf-gc-reason-enumeration.md)  
 <span data-ttu-id="2f132-114">Указывает причину возникновения сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="2f132-114">Indicates the reason that garbage collection is occurring.</span></span>  
  
 [<span data-ttu-id="2f132-115">Перечисление COR_PRF_GC_ROOT_FLAGS</span><span class="sxs-lookup"><span data-stu-id="2f132-115">COR_PRF_GC_ROOT_FLAGS Enumeration</span></span>](cor-prf-gc-root-flags-enumeration.md)  
 <span data-ttu-id="2f132-116">Указывает свойства корня сборщика мусора.</span><span class="sxs-lookup"><span data-stu-id="2f132-116">Indicates properties of a garbage collector root.</span></span>  
  
 [<span data-ttu-id="2f132-117">Перечисление COR_PRF_GC_ROOT_KIND</span><span class="sxs-lookup"><span data-stu-id="2f132-117">COR_PRF_GC_ROOT_KIND Enumeration</span></span>](cor-prf-gc-root-kind-enumeration.md)  
 <span data-ttu-id="2f132-118">Указывает тип корня сборщика мусора, предоставляемый обратным вызовом [ICorProfilerCallback2:: RootReferences2](icorprofilercallback2-rootreferences2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="2f132-118">Indicates the kind of garbage collector root that is exposed by the [ICorProfilerCallback2::RootReferences2](icorprofilercallback2-rootreferences2-method.md) callback.</span></span>  
  
 [<span data-ttu-id="2f132-119">Перечисление COR_PRF_HIGH_MONITOR</span><span class="sxs-lookup"><span data-stu-id="2f132-119">COR_PRF_HIGH_MONITOR Enumeration</span></span>](cor-prf-high-monitor-enumeration.md)  
 <span data-ttu-id="2f132-120">Предоставляет флаги в дополнение к тем, которые находятся в перечислении [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) , которые профилировщик может указать в методе [ICorProfilerInfo5:: SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) при загрузке.</span><span class="sxs-lookup"><span data-stu-id="2f132-120">Provides flags in addition to those found in the [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) enumeration that the profiler can specify to the [ICorProfilerInfo5::SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) method when it is loading.</span></span>  
  
 [<span data-ttu-id="2f132-121">Перечисление COR_PRF_JIT_CACHE</span><span class="sxs-lookup"><span data-stu-id="2f132-121">COR_PRF_JIT_CACHE Enumeration</span></span>](cor-prf-jit-cache-enumeration.md)  
 <span data-ttu-id="2f132-122">Указывает результат кэшированной функции поиска.</span><span class="sxs-lookup"><span data-stu-id="2f132-122">Indicates the result of a cached function search.</span></span>  
  
 [<span data-ttu-id="2f132-123">Перечисление COR_PRF_MISC</span><span class="sxs-lookup"><span data-stu-id="2f132-123">COR_PRF_MISC Enumeration</span></span>](cor-prf-misc-enumeration.md)  
 <span data-ttu-id="2f132-124">Содержит постоянные значения, которые указывают специальные идентификаторы.</span><span class="sxs-lookup"><span data-stu-id="2f132-124">Contains constant values that specify special identifiers.</span></span>  
  
 [<span data-ttu-id="2f132-125">Перечисление COR_PRF_MODULE_FLAGS</span><span class="sxs-lookup"><span data-stu-id="2f132-125">COR_PRF_MODULE_FLAGS Enumeration</span></span>](cor-prf-module-flags-enumeration.md)  
 <span data-ttu-id="2f132-126">Указывает свойства модуля.</span><span class="sxs-lookup"><span data-stu-id="2f132-126">Specifies the properties of a module.</span></span>  
  
 [<span data-ttu-id="2f132-127">Перечисление COR_PRF_MONITOR</span><span class="sxs-lookup"><span data-stu-id="2f132-127">COR_PRF_MONITOR Enumeration</span></span>](cor-prf-monitor-enumeration.md)  
 <span data-ttu-id="2f132-128">Содержит значения, используемые для указания поведения, возможностей или событий, на которые желает подписаться профилировщик.</span><span class="sxs-lookup"><span data-stu-id="2f132-128">Contains values that are used to specify behavior, capabilities, or events to which the profiler wishes to subscribe.</span></span>  
  
 [<span data-ttu-id="2f132-129">Перечисление COR_PRF_RUNTIME_TYPE</span><span class="sxs-lookup"><span data-stu-id="2f132-129">COR_PRF_RUNTIME_TYPE Enumeration</span></span>](cor-prf-runtime-type-enumeration.md)  
 <span data-ttu-id="2f132-130">Содержит значения, которые указывают версию среды CLR.</span><span class="sxs-lookup"><span data-stu-id="2f132-130">Contains values that indicate the version of the common language runtime.</span></span>  
  
 [<span data-ttu-id="2f132-131">Перечисление COR_PRF_SNAPSHOT_INFO</span><span class="sxs-lookup"><span data-stu-id="2f132-131">COR_PRF_SNAPSHOT_INFO Enumeration</span></span>](cor-prf-snapshot-info-enumeration.md)  
 <span data-ttu-id="2f132-132">Указывает количество данных для обратной передачи со снимком стека в каждом вызове функции профилировщика `StackSnapshotCallback`.</span><span class="sxs-lookup"><span data-stu-id="2f132-132">Specifies how much data to pass back with a stack snapshot in each call to the profiler's `StackSnapshotCallback` function.</span></span>  
  
 [<span data-ttu-id="2f132-133">Перечисление COR_PRF_STATIC_TYPE</span><span class="sxs-lookup"><span data-stu-id="2f132-133">COR_PRF_STATIC_TYPE Enumeration</span></span>](cor-prf-static-type-enumeration.md)  
 <span data-ttu-id="2f132-134">Указывает, является ли поле статическим и, если да, относящееся к этому полю статическое качество.</span><span class="sxs-lookup"><span data-stu-id="2f132-134">Indicates whether a field is static and, if so, the static quality that applies to the field.</span></span>  
  
 [<span data-ttu-id="2f132-135">Перечисление COR_PRF_SUSPEND_REASON</span><span class="sxs-lookup"><span data-stu-id="2f132-135">COR_PRF_SUSPEND_REASON Enumeration</span></span>](cor-prf-suspend-reason-enumeration.md)  
 <span data-ttu-id="2f132-136">Указывает причину приостановки среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="2f132-136">Indicates the reason that the runtime was suspended.</span></span>  
  
 [<span data-ttu-id="2f132-137">Перечисление COR_PRF_TRANSITION_REASON</span><span class="sxs-lookup"><span data-stu-id="2f132-137">COR_PRF_TRANSITION_REASON Enumeration</span></span>](cor-prf-transition-reason-enumeration.md)  
 <span data-ttu-id="2f132-138">Указывает причину перехода из управляемого в неуправляемый код или наоборот.</span><span class="sxs-lookup"><span data-stu-id="2f132-138">Indicates the reason for a transition from managed to unmanaged code, or vice versa.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="2f132-139">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="2f132-139">Related Sections</span></span>  

 [<span data-ttu-id="2f132-140">Общие сведения о профилировании</span><span class="sxs-lookup"><span data-stu-id="2f132-140">Profiling Overview</span></span>](profiling-overview.md)  
  
 [<span data-ttu-id="2f132-141">Профилирующие интерфейсы</span><span class="sxs-lookup"><span data-stu-id="2f132-141">Profiling Interfaces</span></span>](profiling-interfaces.md)  
  
 [<span data-ttu-id="2f132-142">Глобальные статические функции профилирования</span><span class="sxs-lookup"><span data-stu-id="2f132-142">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)  
  
 [<span data-ttu-id="2f132-143">Структуры профилирования</span><span class="sxs-lookup"><span data-stu-id="2f132-143">Profiling Structures</span></span>](profiling-structures.md)
