---
title: Интерфейс ICorProfilerCallback4
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4
helpviewer_keywords:
- ICorProfilerCallback4 interface [.NET Framework profiling]
ms.assetid: 665f3cfc-cd6f-4880-906c-ea65ad384783
topic_type:
- apiref
ms.openlocfilehash: 295d3d440529623f4569fd6c5f4debe7e4558990
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499445"
---
# <a name="icorprofilercallback4-interface"></a><span data-ttu-id="2e0ca-102">Интерфейс ICorProfilerCallback4</span><span class="sxs-lookup"><span data-stu-id="2e0ca-102">ICorProfilerCallback4 Interface</span></span>
<span data-ttu-id="2e0ca-103">Предоставляет методы обратного вызова, используемые средой CLR для передачи информации в профилировщик.</span><span class="sxs-lookup"><span data-stu-id="2e0ca-103">Provides callback methods that the common language runtime (CLR) uses to communicate information to the profiler.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2e0ca-104">Методы</span><span class="sxs-lookup"><span data-stu-id="2e0ca-104">Methods</span></span>  
  
|<span data-ttu-id="2e0ca-105">Метод</span><span class="sxs-lookup"><span data-stu-id="2e0ca-105">Method</span></span>|<span data-ttu-id="2e0ca-106">Описание</span><span class="sxs-lookup"><span data-stu-id="2e0ca-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2e0ca-107">Метод GetReJITParameters</span><span class="sxs-lookup"><span data-stu-id="2e0ca-107">GetReJITParameters Method</span></span>](icorprofilercallback4-getrejitparameters-method.md)|<span data-ttu-id="2e0ca-108">Позволяет профилировщику кода устанавливать альтернативные флаги создания кода для нового текста перекомпилированного метода.</span><span class="sxs-lookup"><span data-stu-id="2e0ca-108">Allows the code profiler to set alternate code generation flags for a new recompiled method body.</span></span>|  
|[<span data-ttu-id="2e0ca-109">Метод MovedReferences2</span><span class="sxs-lookup"><span data-stu-id="2e0ca-109">MovedReferences2 Method</span></span>](icorprofilercallback4-movedreferences2-method.md)|<span data-ttu-id="2e0ca-110">Сообщает о новом макете объектов в куче в результате сборки мусора для сжатия.</span><span class="sxs-lookup"><span data-stu-id="2e0ca-110">Reports the new layout of objects in the heap as a result of a compacting garbage collection.</span></span>|  
|[<span data-ttu-id="2e0ca-111">Метод ReJITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="2e0ca-111">ReJITCompilationFinished Method</span></span>](icorprofilercallback4-rejitcompilationfinished-method.md)|<span data-ttu-id="2e0ca-112">Уведомляет профилировщик о том, что JIT-компилятор завершил повторную компиляцию функции.</span><span class="sxs-lookup"><span data-stu-id="2e0ca-112">Notifies the profiler that the just-in-time (JIT) compiler has finished the recompilation of a function.</span></span>|  
|[<span data-ttu-id="2e0ca-113">Метод ReJITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="2e0ca-113">ReJITCompilationStarted Method</span></span>](icorprofilercallback4-rejitcompilationstarted-method.md)|<span data-ttu-id="2e0ca-114">Уведомляет профилировщик о том, что JIT-компилятор начал перекомпилировать функцию.</span><span class="sxs-lookup"><span data-stu-id="2e0ca-114">Notifies the profiler that the just-in-time (JIT) compiler has started to recompile a function.</span></span>|  
|[<span data-ttu-id="2e0ca-115">Метод ReJITError</span><span class="sxs-lookup"><span data-stu-id="2e0ca-115">ReJITError Method</span></span>](icorprofilercallback4-rejiterror-method.md)|<span data-ttu-id="2e0ca-116">Сообщает об ошибке, возникшей при обработке запроса на перекомпиляцию.</span><span class="sxs-lookup"><span data-stu-id="2e0ca-116">Reports an error encountered while processing a recompile request.</span></span>|  
|[<span data-ttu-id="2e0ca-117">Метод SurvivingReferences2</span><span class="sxs-lookup"><span data-stu-id="2e0ca-117">SurvivingReferences2 Method</span></span>](icorprofilercallback4-survivingreferences2-method.md)|<span data-ttu-id="2e0ca-118">Предоставляет информацию о структуре объектов в куче в результате сборки мусора без сжатия.</span><span class="sxs-lookup"><span data-stu-id="2e0ca-118">Reports the layout of objects in the heap as a result of a non-compacting garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2e0ca-119">Remarks</span><span class="sxs-lookup"><span data-stu-id="2e0ca-119">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e0ca-120">Требования</span><span class="sxs-lookup"><span data-stu-id="2e0ca-120">Requirements</span></span>  
 <span data-ttu-id="2e0ca-121">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2e0ca-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e0ca-122">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2e0ca-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2e0ca-123">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2e0ca-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2e0ca-124">**.NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e0ca-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e0ca-125">См. также</span><span class="sxs-lookup"><span data-stu-id="2e0ca-125">See also</span></span>

- [<span data-ttu-id="2e0ca-126">Интерфейс ICorProfilerCallback2</span><span class="sxs-lookup"><span data-stu-id="2e0ca-126">ICorProfilerCallback2 Interface</span></span>](icorprofilercallback2-interface.md)
- [<span data-ttu-id="2e0ca-127">Профилирующие интерфейсы</span><span class="sxs-lookup"><span data-stu-id="2e0ca-127">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="2e0ca-128">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="2e0ca-128">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
