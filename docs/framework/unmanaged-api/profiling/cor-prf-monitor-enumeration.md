---
title: Перечисление COR_PRF_MONITOR
ms.date: 03/30/2017
api_name:
- COR_PRF_MONITOR
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_MONITOR
helpviewer_keywords:
- COR_PRF_MONITOR enumeration [.NET Framework profiling]
ms.assetid: 9294d702-b4e5-441c-a930-e63d27b86bfd
topic_type:
- apiref
ms.openlocfilehash: 1ff167121a5bb752c70edd2c5901133503326bea
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500810"
---
# <a name="cor_prf_monitor-enumeration"></a><span data-ttu-id="0e2f0-102">Перечисление COR_PRF_MONITOR</span><span class="sxs-lookup"><span data-stu-id="0e2f0-102">COR_PRF_MONITOR Enumeration</span></span>
<span data-ttu-id="0e2f0-103">Содержит значения, используемые для указания поведения, возможностей или событий, на которые желает подписаться профилировщик.</span><span class="sxs-lookup"><span data-stu-id="0e2f0-103">Contains values that are used to specify behavior, capabilities, or events to which the profiler wishes to subscribe.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e2f0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0e2f0-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_MONITOR_NONE                = 0x00000000,  
    COR_PRF_MONITOR_FUNCTION_UNLOADS    = 0x00000001,  
    COR_PRF_MONITOR_CLASS_LOADS         = 0x00000002,  
    COR_PRF_MONITOR_MODULE_LOADS        = 0x00000004,  
    COR_PRF_MONITOR_ASSEMBLY_LOADS      = 0x00000008,  
    COR_PRF_MONITOR_APPDOMAIN_LOADS     = 0x00000010,  
    COR_PRF_MONITOR_JIT_COMPILATION     = 0x00000020,  
    COR_PRF_MONITOR_EXCEPTIONS          = 0x00000040,  
    COR_PRF_MONITOR_GC                  = 0x00000080,  
    COR_PRF_MONITOR_OBJECT_ALLOCATED    = 0x00000100,  
    COR_PRF_MONITOR_THREADS             = 0x00000200,  
    COR_PRF_MONITOR_REMOTING            = 0x00000400,  
    COR_PRF_MONITOR_CODE_TRANSITIONS    = 0x00000800,  
    COR_PRF_MONITOR_ENTERLEAVE          = 0x00001000,  
    COR_PRF_MONITOR_CCW                 = 0x00002000,  
    COR_PRF_MONITOR_REMOTING_COOKIE     = 0x00004000 |
                                          COR_PRF_MONITOR_REMOTING,  
    COR_PRF_MONITOR_REMOTING_ASYNC      = 0x00008000 |
                                          COR_PRF_MONITOR_REMOTING,  
    COR_PRF_MONITOR_SUSPENDS            = 0x00010000,  
    COR_PRF_MONITOR_CACHE_SEARCHES      = 0x00020000,  
    COR_PRF_ENABLE_REJIT                = 0x00040000,  
    COR_PRF_ENABLE_INPROC_DEBUGGING     = 0x00080000,  
    COR_PRF_ENABLE_JIT_MAPS             = 0x00100000,  
    COR_PRF_DISABLE_INLINING            = 0x00200000,  
    COR_PRF_DISABLE_OPTIMIZATIONS       = 0x00400000,  
    COR_PRF_ENABLE_OBJECT_ALLOCATED     = 0x00800000,  
    COR_PRF_MONITOR_CLR_EXCEPTIONS      = 0x01000000,  
    COR_PRF_MONITOR_ALL                 = 0x0107FFFF,  
    COR_PRF_ENABLE_FUNCTION_ARGS        = 0X02000000,  
    COR_PRF_ENABLE_FUNCTION_RETVAL      = 0X04000000,  
    COR_PRF_ENABLE_FRAME_INFO           = 0X08000000,  
    COR_PRF_ENABLE_STACK_SNAPSHOT       = 0X10000000,  
    COR_PRF_USE_PROFILE_IMAGES          = 0x20000000,  
    COR_PRF_DISABLE_TRANSPARENCY_CHECKS_UNDER_FULL_TRUST  
                                        = 0x40000000,  
    COR_PRF_DISABLE_ALL_NGEN_IMAGES     = 0x80000000,  
    COR_PRF_ALL                         = 0x8FFFFFFF,  
    COR_PRF_REQUIRE_PROFILE_IMAGE       = COR_PRF_USE_PROFILE_IMAGES |
                                          COR_PRF_MONITOR_CODE_TRANSITIONS |
                                          COR_PRF_MONITOR_ENTERLEAVE,  
    COR_PRF_ALLOWABLE_AFTER_ATTACH      = COR_PRF_MONITOR_THREADS |  
                                          COR_PRF_MONITOR_MODULE_LOADS |  
                                          COR_PRF_MONITOR_ASSEMBLY_LOADS |  
                                          COR_PRF_MONITOR_APPDOMAIN_LOADS |  
                                          COR_PRF_ENABLE_STACK_SNAPSHOT |  
                                          COR_PRF_MONITOR_GC |  
                                          COR_PRF_MONITOR_SUSPENDS |  
                                          COR_PRF_MONITOR_CLASS_LOADS |  
                                          COR_PRF_MONITOR_JIT_COMPILATION,  
    COR_PRF_MONITOR_IMMUTABLE           = COR_PRF_MONITOR_CODE_TRANSITIONS |  
                                          COR_PRF_MONITOR_REMOTING |  
                                          COR_PRF_MONITOR_REMOTING_COOKIE |  
                                          COR_PRF_MONITOR_REMOTING_ASYNC |  
                                          COR_PRF_ENABLE_REJIT |  
                                          COR_PRF_ENABLE_INPROC_DEBUGGING |  
                                          COR_PRF_ENABLE_JIT_MAPS |  
                                          COR_PRF_DISABLE_OPTIMIZATIONS |  
                                          COR_PRF_DISABLE_INLINING |  
                                          COR_PRF_ENABLE_OBJECT_ALLOCATED |  
                                          COR_PRF_ENABLE_FUNCTION_ARGS |  
                                          COR_PRF_ENABLE_FUNCTION_RETVAL |  
                                          COR_PRF_ENABLE_FRAME_INFO |  
                                          COR_PRF_USE_PROFILE_IMAGES |  
                     COR_PRF_DISABLE_TRANSPARENCY_CHECKS_UNDER_FULL_TRUST |  
                                          COR_PRF_DISABLE_ALL_NGEN_IMAGES  
} COR_PRF_MONITOR;  
```  
  
## <a name="members"></a><span data-ttu-id="0e2f0-105">Участники</span><span class="sxs-lookup"><span data-stu-id="0e2f0-105">Members</span></span>  
 <span data-ttu-id="0e2f0-106">В следующих разделах перечислены `COR_PRF_MONITOR` члены перечисления по категориям.</span><span class="sxs-lookup"><span data-stu-id="0e2f0-106">The following sections list `COR_PRF_MONITOR` enumeration members by category.</span></span> <span data-ttu-id="0e2f0-107">Категории:</span><span class="sxs-lookup"><span data-stu-id="0e2f0-107">The categories are:</span></span>  
  
- [<span data-ttu-id="0e2f0-108">Флаги не заданы</span><span class="sxs-lookup"><span data-stu-id="0e2f0-108">No flags set</span></span>](#None)  
  
- [<span data-ttu-id="0e2f0-109">Флаги обратного вызова</span><span class="sxs-lookup"><span data-stu-id="0e2f0-109">Callback flags</span></span>](#Callback)  
  
- [<span data-ttu-id="0e2f0-110">Флаги включения компонентов</span><span class="sxs-lookup"><span data-stu-id="0e2f0-110">Feature-enabling flags</span></span>](#Feature)  
  
- [<span data-ttu-id="0e2f0-111">Флаги конфигурации</span><span class="sxs-lookup"><span data-stu-id="0e2f0-111">Configuration flags</span></span>](#Config)  
  
- [<span data-ttu-id="0e2f0-112">Составные флаги</span><span class="sxs-lookup"><span data-stu-id="0e2f0-112">Composite flags</span></span>](#Composite)  
  
<a name="None"></a>
### <a name="no-flags-set"></a><span data-ttu-id="0e2f0-113">Флаги не заданы</span><span class="sxs-lookup"><span data-stu-id="0e2f0-113">No flags set</span></span>  
  
|<span data-ttu-id="0e2f0-114">Член</span><span class="sxs-lookup"><span data-stu-id="0e2f0-114">Member</span></span>|<span data-ttu-id="0e2f0-115">Описание</span><span class="sxs-lookup"><span data-stu-id="0e2f0-115">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_MONITOR_NONE`|<span data-ttu-id="0e2f0-116">Флаги не установлены.</span><span class="sxs-lookup"><span data-stu-id="0e2f0-116">No flags are set.</span></span>|  
  
<a name="Callback"></a>
### <a name="callback-flags"></a><span data-ttu-id="0e2f0-117">Флаги обратного вызова</span><span class="sxs-lookup"><span data-stu-id="0e2f0-117">Callback flags</span></span>  
  
|<span data-ttu-id="0e2f0-118">Член</span><span class="sxs-lookup"><span data-stu-id="0e2f0-118">Member</span></span>|<span data-ttu-id="0e2f0-119">Описание</span><span class="sxs-lookup"><span data-stu-id="0e2f0-119">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_MONITOR_ALL`|<span data-ttu-id="0e2f0-120">Активирует все события обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="0e2f0-120">Enables all callback events.</span></span>|  
|`COR_PRF_MONITOR_APPDOMAIN_LOADS`|<span data-ttu-id="0e2f0-121">Управляет `AppDomainCreation*` `AppDomainShutdown*` обратными вызовами и в интерфейсе [ICorProfilerCallback](icorprofilercallback-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="0e2f0-121">Controls the `AppDomainCreation*` and `AppDomainShutdown*` callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_ASSEMBLY_LOADS`|<span data-ttu-id="0e2f0-122">Управляет `AssemblyLoad*` `AssemblyUnload*` обратными вызовами и в интерфейсе [ICorProfilerCallback](icorprofilercallback-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="0e2f0-122">Controls the `AssemblyLoad*` and `AssemblyUnload*` callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_CACHE_SEARCHES`|<span data-ttu-id="0e2f0-123">Управляет `JITCachedFunctionSearch*` обратными вызовами в интерфейсе [ICorProfilerCallback](icorprofilercallback-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="0e2f0-123">Controls the `JITCachedFunctionSearch*` callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span><br /><br /> <span data-ttu-id="0e2f0-124">Поведение этого флага в платформе .NET Framework версии 2.0 изменено.</span><span class="sxs-lookup"><span data-stu-id="0e2f0-124">The behavior of this flag is changed in the .NET Framework version 2.0.</span></span>|  
|`COR_PRF_MONITOR_CCW`|<span data-ttu-id="0e2f0-125">Управляет `COMClassicVTable*` обратными вызовами в интерфейсе [ICorProfilerCallback](icorprofilercallback-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="0e2f0-125">Controls the `COMClassicVTable*` callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_CLASS_LOADS`|<span data-ttu-id="0e2f0-126">Управляет `ClassLoad*` `ClassUnload*` обратными вызовами и в интерфейсе [ICorProfilerCallback](icorprofilercallback-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="0e2f0-126">Controls the `ClassLoad*` and `ClassUnload*` callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_CLR_EXCEPTIONS`|<span data-ttu-id="0e2f0-127">Управляет `ExceptionCLRCatcher*` обратными вызовами в интерфейсе [ICorProfilerCallback](icorprofilercallback-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="0e2f0-127">Controls the `ExceptionCLRCatcher*` callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_CODE_TRANSITIONS`|<span data-ttu-id="0e2f0-128">Управляет обратными вызовами [унманажедтоманажедтранситион](icorprofilercallback-unmanagedtomanagedtransition-method.md) и [манажедтаунманажедтранситион](icorprofilercallback-managedtounmanagedtransition-method.md) в интерфейсе [ICorProfilerCallback](icorprofilercallback-interface.md)</span><span class="sxs-lookup"><span data-stu-id="0e2f0-128">Controls the [UnmanagedToManagedTransition](icorprofilercallback-unmanagedtomanagedtransition-method.md) and [ManagedToUnmanagedTransition](icorprofilercallback-managedtounmanagedtransition-method.md) callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface</span></span>|  
|`COR_PRF_MONITOR_ENTERLEAVE`|<span data-ttu-id="0e2f0-129">Управляет `FunctionEnter*` `FunctionLeave*` `FunctionTailCall*` [глобальными статическими функциями профилирования](profiling-global-static-functions.md), и.</span><span class="sxs-lookup"><span data-stu-id="0e2f0-129">Controls the `FunctionEnter*`,  `FunctionLeave*`, and `FunctionTailCall*`[profiling global static functions](profiling-global-static-functions.md).</span></span>|  
|`COR_PRF_MONITOR_EXCEPTIONS`|<span data-ttu-id="0e2f0-130">Управляет обратным вызовом [ExceptionThrown](icorprofilercallback-exceptionthrown-method.md) и `ExceptionSearch*` `ExceptionOSHandler*` `ExceptionUnwind*` `ExceptionCatcher*` обратными вызовами,, и в интерфейсе [ICorProfilerCallback](icorprofilercallback-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="0e2f0-130">Controls the [ExceptionThrown](icorprofilercallback-exceptionthrown-method.md) callback and the `ExceptionSearch*`, `ExceptionOSHandler*`, `ExceptionUnwind*`, and `ExceptionCatcher*` callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_FUNCTION_UNLOADS`|<span data-ttu-id="0e2f0-131">Управляет обратным вызовом [FunctionUnloadStarted](icorprofilercallback-functionunloadstarted-method.md) в интерфейсе [ICorProfilerCallback](icorprofilercallback-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="0e2f0-131">Controls the [FunctionUnloadStarted](icorprofilercallback-functionunloadstarted-method.md) callback in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_GC`|<span data-ttu-id="0e2f0-132">Контролирует обратные вызовы [GarbageCollectionStarted](icorprofilercallback2-garbagecollectionstarted-method.md), [GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md), [MovedReferences](icorprofilercallback-movedreferences-method.md), [MovedReferences2](icorprofilercallback4-movedreferences2-method.md), [SurvivingReferences](icorprofilercallback2-survivingreferences-method.md) [, SurvivingReferences2](icorprofilercallback4-survivingreferences2-method.md) [, ObjectReferences,](icorprofilercallback-objectreferences-method.md) [обжектсаллокатедбикласс,](icorprofilercallback-objectsallocatedbyclass-method.md) [RootReferences](icorprofilercallback-rootreferences-method.md), [RootReferences2](icorprofilercallback2-rootreferences2-method.md), [хандлекреатед](icorprofilercallback2-handlecreated-method.md), [хандледестройед](icorprofilercallback2-handledestroyed-method.md)и [финализеаблеобжекткуеуед](icorprofilercallback2-finalizeableobjectqueued-method.md) в `ICorProfilerCallback*` интерфейсах.</span><span class="sxs-lookup"><span data-stu-id="0e2f0-132">Controls the [GarbageCollectionStarted](icorprofilercallback2-garbagecollectionstarted-method.md),   [GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md),  [MovedReferences](icorprofilercallback-movedreferences-method.md), [MovedReferences2](icorprofilercallback4-movedreferences2-method.md),    [SurvivingReferences](icorprofilercallback2-survivingreferences-method.md),  [SurvivingReferences2](icorprofilercallback4-survivingreferences2-method.md), [ObjectReferences](icorprofilercallback-objectreferences-method.md),   [ObjectsAllocatedByClass](icorprofilercallback-objectsallocatedbyclass-method.md),  [RootReferences](icorprofilercallback-rootreferences-method.md), [RootReferences2](icorprofilercallback2-rootreferences2-method.md), [HandleCreated](icorprofilercallback2-handlecreated-method.md),  [HandleDestroyed](icorprofilercallback2-handledestroyed-method.md), and [FinalizeableObjectQueued](icorprofilercallback2-finalizeableobjectqueued-method.md) callbacks in the `ICorProfilerCallback*` interfaces.</span></span> <span data-ttu-id="0e2f0-133">При `COR_PRF_MONITOR_GC` выделении параллельная сборка мусора отключена.</span><span class="sxs-lookup"><span data-stu-id="0e2f0-133">When `COR_PRF_MONITOR_GC` is allocated, concurrent garbage collection is turned off.</span></span>|  
|`COR_PRF_MONITOR_JIT_COMPILATION`|<span data-ttu-id="0e2f0-134">Управляет `JITCompilation*` обратными вызовами, [JITFunctionPitched](icorprofilercallback-jitfunctionpitched-method.md)и [Житинлининг](icorprofilercallback-jitinlining-method.md) в интерфейсе [ICorProfilerCallback](icorprofilercallback-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="0e2f0-134">Controls the `JITCompilation*`, [JITFunctionPitched](icorprofilercallback-jitfunctionpitched-method.md), and [JITInlining](icorprofilercallback-jitinlining-method.md) callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_MODULE_LOADS`|<span data-ttu-id="0e2f0-135">Управляет `ModuleLoad*` `ModuleUnload*` обратными вызовами, и [модулеаттачедтоассембли](icorprofilercallback-moduleattachedtoassembly-method.md) в интерфейсе [ICorProfilerCallback](icorprofilercallback-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="0e2f0-135">Controls the `ModuleLoad*`,  `ModuleUnload*`, and [ModuleAttachedToAssembly](icorprofilercallback-moduleattachedtoassembly-method.md) callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_OBJECT_ALLOCATED`|<span data-ttu-id="0e2f0-136">Управляет обратным вызовом [ObjectAllocated](icorprofilercallback-objectallocated-method.md) в интерфейсе [ICorProfilerCallback](icorprofilercallback-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="0e2f0-136">Controls the [ObjectAllocated](icorprofilercallback-objectallocated-method.md) callback in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_REMOTING`|<span data-ttu-id="0e2f0-137">Управляет `Remoting*` обратными вызовами в интерфейсе [ICorProfilerCallback](icorprofilercallback-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="0e2f0-137">Controls the `Remoting*` callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_REMOTING_ASYNC`|<span data-ttu-id="0e2f0-138">Определяет, будут ли обратные вызовы `Remoting*` отслеживать асинхронные события.</span><span class="sxs-lookup"><span data-stu-id="0e2f0-138">Controls whether the `Remoting*` callbacks will monitor asynchronous events.</span></span>|  
|`COR_PRF_MONITOR_REMOTING_COOKIE`|<span data-ttu-id="0e2f0-139">Определяет, будут ли передаваться файлы cookie для обратных вызовов `Remoting*`.</span><span class="sxs-lookup"><span data-stu-id="0e2f0-139">Controls whether a cookie is passed to the `Remoting*` callbacks.</span></span>|  
|`COR_PRF_MONITOR_SUSPENDS`|<span data-ttu-id="0e2f0-140">Управляет `RuntimeSuspend*` `RuntimeResume*` обратными вызовами,, [RuntimeThreadSuspended](icorprofilercallback-runtimethreadsuspended-method.md)и [RuntimeThreadResumed](icorprofilercallback-runtimethreadresumed-method.md) в интерфейсе [ICorProfilerCallback](icorprofilercallback-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="0e2f0-140">Controls the `RuntimeSuspend*`, `RuntimeResume*`, [RuntimeThreadSuspended](icorprofilercallback-runtimethreadsuspended-method.md), and [RuntimeThreadResumed](icorprofilercallback-runtimethreadresumed-method.md) callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_THREADS`|<span data-ttu-id="0e2f0-141">Управляет обратными вызовами [ThreadCreated](icorprofilercallback-threadcreated-method.md), [ThreadDestroyed](icorprofilercallback-threaddestroyed-method.md), [ThreadAssignedToOSThread](icorprofilercallback-threadassignedtoosthread-method.md)и [ThreadNameChanged](icorprofilercallback2-threadnamechanged-method.md) в интерфейсах [ICorProfilerCallback](icorprofilercallback-interface.md) и [ICorProfilerCallback2](icorprofilercallback2-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="0e2f0-141">Controls the [ThreadCreated](icorprofilercallback-threadcreated-method.md),  [ThreadDestroyed](icorprofilercallback-threaddestroyed-method.md),  [ThreadAssignedToOSThread](icorprofilercallback-threadassignedtoosthread-method.md), and [ThreadNameChanged](icorprofilercallback2-threadnamechanged-method.md) callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) and [ICorProfilerCallback2](icorprofilercallback2-interface.md) interfaces.</span></span>|  
  
<a name="Feature"></a>
### <a name="feature-enabling-flags"></a><span data-ttu-id="0e2f0-142">Флаги включения компонентов</span><span class="sxs-lookup"><span data-stu-id="0e2f0-142">Feature-enabling flags</span></span>  
  
|<span data-ttu-id="0e2f0-143">Член</span><span class="sxs-lookup"><span data-stu-id="0e2f0-143">Member</span></span>|<span data-ttu-id="0e2f0-144">Описание</span><span class="sxs-lookup"><span data-stu-id="0e2f0-144">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_ENABLE_FRAME_INFO`|<span data-ttu-id="0e2f0-145">Включает извлечение точного `ClassID` значения для универсальной функции путем вызова метода [GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) со `COR_PRF_FRAME_INFO` значением, возвращенным обратным вызовом [FunctionEnter2](functionenter2-function.md) .</span><span class="sxs-lookup"><span data-stu-id="0e2f0-145">Enables the retrieval of an exact `ClassID` for a generic function by calling the [GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) method with a `COR_PRF_FRAME_INFO` value returned by the [FunctionEnter2](functionenter2-function.md) callback.</span></span>|  
|`COR_PRF_ENABLE_FUNCTION_ARGS`|<span data-ttu-id="0e2f0-146">Включает трассировку аргументов с помощью обратного вызова [FunctionEnter2](functionenter2-function.md) или [FunctionEnter3WithInfo](functionenter3withinfo-function.md) и метода [GetFunctionEnter3Info](icorprofilerinfo3-getfunctionenter3info-method.md) .</span><span class="sxs-lookup"><span data-stu-id="0e2f0-146">Enables argument tracing using the [FunctionEnter2](functionenter2-function.md) callback or the [FunctionEnter3WithInfo](functionenter3withinfo-function.md) callback and the [GetFunctionEnter3Info](icorprofilerinfo3-getfunctionenter3info-method.md) method.</span></span>|  
|`COR_PRF_ENABLE_FUNCTION_RETVAL`|<span data-ttu-id="0e2f0-147">Включает трассировку возвращаемых значений с помощью обратного вызова [FunctionLeave2](functionleave2-function.md) или метода обратного вызова [FunctionLeave3WithInfo](functionleave3withinfo-function.md) и [GetFunctionLeave3Info](icorprofilerinfo3-getfunctionleave3info-method.md) .</span><span class="sxs-lookup"><span data-stu-id="0e2f0-147">Enables tracing of return values by using the [FunctionLeave2](functionleave2-function.md) callback or the [FunctionLeave3WithInfo](functionleave3withinfo-function.md) callback and [GetFunctionLeave3Info](icorprofilerinfo3-getfunctionleave3info-method.md) method.</span></span>|  
|`COR_PRF_ENABLE_INPROC_DEBUGGING`|<span data-ttu-id="0e2f0-148">Не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="0e2f0-148">Deprecated.</span></span><br /><br /> <span data-ttu-id="0e2f0-149">Отладка в процессе работы не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="0e2f0-149">In process debugging is not supported.</span></span> <span data-ttu-id="0e2f0-150">Этот флаг ни на что не влияет.</span><span class="sxs-lookup"><span data-stu-id="0e2f0-150">This flag has no effect.</span></span>|  
|`COR_PRF_ENABLE_JIT_MAPS`|<span data-ttu-id="0e2f0-151">Не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="0e2f0-151">Deprecated.</span></span><br /><br /> <span data-ttu-id="0e2f0-152">Позволяет профилировщику получать карты из IL в машинный код с помощью [GetILToNativeMapping](icorprofilerinfo-getiltonativemapping-method.md).</span><span class="sxs-lookup"><span data-stu-id="0e2f0-152">Allows the profiler to obtain IL-to-native maps by using [GetILToNativeMapping](icorprofilerinfo-getiltonativemapping-method.md).</span></span> <span data-ttu-id="0e2f0-153">Начиная с платформы .NET Framework версии 2.0, среда выполнения всегда отслеживает сопоставления промежуточного и машинного языков, поэтому данный флаг всегда считается установленным.</span><span class="sxs-lookup"><span data-stu-id="0e2f0-153">Starting with the .NET Framework 2.0, the runtime always tracks IL-to-native maps; therefore, this flag is always considered to be set.</span></span>|  
|`COR_PRF_ENABLE_OBJECT_ALLOCATED`|<span data-ttu-id="0e2f0-154">Сообщает среде выполнения о том, что профилировщик может захотеть получать уведомления о распределениях объекта.</span><span class="sxs-lookup"><span data-stu-id="0e2f0-154">Informs the runtime that the profiler may want object allocation notifications.</span></span> <span data-ttu-id="0e2f0-155">Этот флаг должен быть установлен во время инициализации.</span><span class="sxs-lookup"><span data-stu-id="0e2f0-155">This flag must be set during initialization.</span></span> <span data-ttu-id="0e2f0-156">Он позволяет профилировщику впоследствии использовать `COR_PRF_MONITOR_OBJECT_ALLOCATED` флаг для получения обратных вызовов [ObjectAllocated](icorprofilercallback-objectallocated-method.md) .</span><span class="sxs-lookup"><span data-stu-id="0e2f0-156">It allows the profiler to subsequently use the `COR_PRF_MONITOR_OBJECT_ALLOCATED` flag to receive [ObjectAllocated](icorprofilercallback-objectallocated-method.md) callbacks.</span></span>|  
|`COR_PRF_ENABLE_REJIT`|<span data-ttu-id="0e2f0-157">Разрешает вызовы методов [рекуестрежит](icorprofilerinfo4-requestrejit-method.md) и [рекуестреверт](icorprofilerinfo4-requestrevert-method.md) .</span><span class="sxs-lookup"><span data-stu-id="0e2f0-157">Enables calls to the [RequestReJIT](icorprofilerinfo4-requestrejit-method.md) and [RequestRevert](icorprofilerinfo4-requestrevert-method.md) methods.</span></span> <span data-ttu-id="0e2f0-158">Профилировщик должен установить этот флаг при запуске.</span><span class="sxs-lookup"><span data-stu-id="0e2f0-158">The profiler must set this flag on startup.</span></span>  <span data-ttu-id="0e2f0-159">Если профилировщик указывает этот флаг, он также должен указать и `COR_PRF_DISABLE_ALL_NGEN_IMAGES`.</span><span class="sxs-lookup"><span data-stu-id="0e2f0-159">If the profiler specifies this flag, it must also specify `COR_PRF_DISABLE_ALL_NGEN_IMAGES`.</span></span>|  
|`COR_PRF_ENABLE_STACK_SNAPSHOT`|<span data-ttu-id="0e2f0-160">Разрешает вызовы метода [DoStackSnapshot](icorprofilerinfo2-dostacksnapshot-method.md) .</span><span class="sxs-lookup"><span data-stu-id="0e2f0-160">Enables calls to the [DoStackSnapshot](icorprofilerinfo2-dostacksnapshot-method.md) method.</span></span>|  
  
<a name="Config"></a>
### <a name="configuration-flags"></a><span data-ttu-id="0e2f0-161">Флаги конфигурации</span><span class="sxs-lookup"><span data-stu-id="0e2f0-161">Configuration flags</span></span>  
  
|<span data-ttu-id="0e2f0-162">Член</span><span class="sxs-lookup"><span data-stu-id="0e2f0-162">Member</span></span>|<span data-ttu-id="0e2f0-163">Описание</span><span class="sxs-lookup"><span data-stu-id="0e2f0-163">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_DISABLE_ALL_NGEN_IMAGES`|<span data-ttu-id="0e2f0-164">Запрещает загрузку всех машинных образов (включая образы, улучшенные профилировщиком).</span><span class="sxs-lookup"><span data-stu-id="0e2f0-164">Prevents all native images (including profiler-enhanced images) from loading.</span></span>  <span data-ttu-id="0e2f0-165">Если этот флаг и флаг `COR_PRF_USE_PROFILE_IMAGES` указаны, используется `COR_PRF_DISABLE_ALL_NGEN_IMAGES`.</span><span class="sxs-lookup"><span data-stu-id="0e2f0-165">If this flag and the `COR_PRF_USE_PROFILE_IMAGES` flag are both specified, `COR_PRF_DISABLE_ALL_NGEN_IMAGES` is used.</span></span>|  
|`COR_PRF_DISABLE_INLINING`|<span data-ttu-id="0e2f0-166">Отключает все встраивания.</span><span class="sxs-lookup"><span data-stu-id="0e2f0-166">Disables all inlining.</span></span>|  
|`COR_PRF_DISABLE_OPTIMIZATIONS`|<span data-ttu-id="0e2f0-167">Отключает все оптимизации кода.</span><span class="sxs-lookup"><span data-stu-id="0e2f0-167">Disables all code optimizations.</span></span>|  
|`COR_PRF_DISABLE_TRANSPARENCY_CHECKS_UNDER_FULL_TRUST`|<span data-ttu-id="0e2f0-168">Отключает проверки прозрачности безопасности, которые обычно производятся во время JIT-компиляции и загрузки классов для обеспечения полного доверия к сборкам.</span><span class="sxs-lookup"><span data-stu-id="0e2f0-168">Disables security transparency checks that are normally done during just-in-time (JIT) compilation and class loading for full-trust assemblies.</span></span> <span data-ttu-id="0e2f0-169">Это может облегчить выполнение некоторых инструментирований.</span><span class="sxs-lookup"><span data-stu-id="0e2f0-169">This can make some instrumentation easier to perform.</span></span>|  
|`COR_PRF_USE_PROFILE_IMAGES`|<span data-ttu-id="0e2f0-170">Вызывает поиск машинного образа для поиска образов, улучшенных профилировщиком.</span><span class="sxs-lookup"><span data-stu-id="0e2f0-170">Causes the native image search to look for profiler-enhanced images.</span></span> <span data-ttu-id="0e2f0-171">Если для данной сборки образов, улучшенных профилировщиком, не найдено, среда CLR возвращается к JIT для этой сборки.</span><span class="sxs-lookup"><span data-stu-id="0e2f0-171">If no profiler-enhanced image is found for a given assembly, the common language runtime falls back to JIT for that assembly.</span></span> <span data-ttu-id="0e2f0-172">Если этот флаг и флаг `COR_PRF_DISABLE_ALL_NGEN_IMAGES` указаны, используется `COR_PRF_DISABLE_ALL_NGEN_IMAGES`.</span><span class="sxs-lookup"><span data-stu-id="0e2f0-172">If this flag and the `COR_PRF_DISABLE_ALL_NGEN_IMAGES` flag are both specified, `COR_PRF_DISABLE_ALL_NGEN_IMAGES` is used.</span></span>|  
  
<a name="Composite"></a>
### <a name="composite-flags"></a><span data-ttu-id="0e2f0-173">Составные флаги</span><span class="sxs-lookup"><span data-stu-id="0e2f0-173">Composite flags</span></span>  
  
|<span data-ttu-id="0e2f0-174">Член</span><span class="sxs-lookup"><span data-stu-id="0e2f0-174">Member</span></span>|<span data-ttu-id="0e2f0-175">Описание</span><span class="sxs-lookup"><span data-stu-id="0e2f0-175">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_ALL`|<span data-ttu-id="0e2f0-176">Представляет все значения флагов `COR_PRF_MONITOR`.</span><span class="sxs-lookup"><span data-stu-id="0e2f0-176">Represents all `COR_PRF_MONITOR` flag values.</span></span>|  
|`COR_PRF_ALLOWABLE_AFTER_ATTACH`|<span data-ttu-id="0e2f0-177">Представляет все флаги `COR_PRF_MONITOR`, которые могут быть установлены после присоединения профилировщика к выполняющемуся приложению.</span><span class="sxs-lookup"><span data-stu-id="0e2f0-177">Represents all `COR_PRF_MONITOR` flags that can be set after the profiler is attached to a running app.</span></span> <span data-ttu-id="0e2f0-178">В разделе "Синтаксис" указываются отдельные флаги, которые присутствуют в этой битовой маске.</span><span class="sxs-lookup"><span data-stu-id="0e2f0-178">The syntax section indicates the individual flags that are present in this bitmask.</span></span>|  
|`COR_PRF_MONITOR_ALL`|<span data-ttu-id="0e2f0-179">Активирует все события обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="0e2f0-179">Enables all callback events.</span></span>|  
|`COR_PRF_MONITOR_IMMUTABLE`|<span data-ttu-id="0e2f0-180">Представляет все флаги `COR_PRF_MONITOR`, которые могут быть установлены только во время инициализации.</span><span class="sxs-lookup"><span data-stu-id="0e2f0-180">Represents all `COR_PRF_MONITOR` flags that can be set only during initialization.</span></span> <span data-ttu-id="0e2f0-181">Попытка изменить какой-нибудь из этих флагов после инициализации вызовет значение `HRESULT`, указывающее на сбой.</span><span class="sxs-lookup"><span data-stu-id="0e2f0-181">Trying to change any of these flags after initialization returns an `HRESULT` value that indicates failure.</span></span>|  
|`COR_PRF_REQUIRE_PROFILE_IMAGE`|<span data-ttu-id="0e2f0-182">Представляет все флаги `COR_PRF_MONITOR`, для которых необходимы улучшенные профилировщиком изображения.</span><span class="sxs-lookup"><span data-stu-id="0e2f0-182">Represents all `COR_PRF_MONITOR` flags that require profile-enhanced images.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0e2f0-183">Примечания</span><span class="sxs-lookup"><span data-stu-id="0e2f0-183">Remarks</span></span>  
 <span data-ttu-id="0e2f0-184">`COR_PRF_MONITOR`Значение используется с методами [ICorProfilerInfo:: GetEventMask](icorprofilerinfo-geteventmask-method.md) и [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) для определения уведомлений о событиях, которые среда CLR делает в профилировщике.</span><span class="sxs-lookup"><span data-stu-id="0e2f0-184">A `COR_PRF_MONITOR` value is used with the [ICorProfilerInfo::GetEventMask](icorprofilerinfo-geteventmask-method.md) and [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md) methods to define the event notifications that the common language runtime makes to the profiler.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e2f0-185">Требования</span><span class="sxs-lookup"><span data-stu-id="0e2f0-185">Requirements</span></span>  
 <span data-ttu-id="0e2f0-186">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0e2f0-186">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e2f0-187">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0e2f0-187">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0e2f0-188">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0e2f0-188">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0e2f0-189">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0e2f0-189">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e2f0-190">См. также</span><span class="sxs-lookup"><span data-stu-id="0e2f0-190">See also</span></span>

- [<span data-ttu-id="0e2f0-191">Перечисления профилирования</span><span class="sxs-lookup"><span data-stu-id="0e2f0-191">Profiling Enumerations</span></span>](profiling-enumerations.md)
- [<span data-ttu-id="0e2f0-192">Метод GetEventMask</span><span class="sxs-lookup"><span data-stu-id="0e2f0-192">GetEventMask Method</span></span>](icorprofilerinfo-geteventmask-method.md)
- [<span data-ttu-id="0e2f0-193">Метод SetEventMask</span><span class="sxs-lookup"><span data-stu-id="0e2f0-193">SetEventMask Method</span></span>](icorprofilerinfo-seteventmask-method.md)
