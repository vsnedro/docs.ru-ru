---
title: Метод ICorProfilerCallback4::ReJITCompilationFinished
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4.ReJITCompilationFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4::ReJITCompilationFinished
helpviewer_keywords:
- ICorProfilerCallback4::ReJITCompilationFinished method [.NET Framework profiling]
- ReJITCompilationFinished method, ICorProfilerCallback4 interface [.NET Framework profiling]
ms.assetid: 3b5cff02-2005-44eb-a2bc-50214c4b0e1d
topic_type:
- apiref
ms.openlocfilehash: a6c2209433a652523fd8e3a7cc2db1272600e1bd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730270"
---
# <a name="icorprofilercallback4rejitcompilationfinished-method"></a><span data-ttu-id="4013d-102">Метод ICorProfilerCallback4::ReJITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="4013d-102">ICorProfilerCallback4::ReJITCompilationFinished Method</span></span>

<span data-ttu-id="4013d-103">Уведомляет профилировщик о том, что JIT-компилятор завершил повторную компиляцию функции.</span><span class="sxs-lookup"><span data-stu-id="4013d-103">Notifies the profiler that the just-in-time (JIT) compiler has finished recompiling a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4013d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4013d-104">Syntax</span></span>  
  
```cpp  
HRESULT ReJITCompilationFinished(  
    [in] FunctionID functionId,    [in] ReJITID rejitId,  
    [in] HRESULT    hrStatus,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4013d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4013d-105">Parameters</span></span>  

 `functionId`  
 <span data-ttu-id="4013d-106">окне Идентификатор перекомпилированной функции.</span><span class="sxs-lookup"><span data-stu-id="4013d-106">[in] The ID of the function that was recompiled.</span></span>  
  
 `rejitId`  
 <span data-ttu-id="4013d-107">[in] Идентификатор функции, перекомпилированной с помощью JIT-компилятора.</span><span class="sxs-lookup"><span data-stu-id="4013d-107">[in] The identity of the JIT-recompiled function.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="4013d-108">окне Значение, указывающее, успешно ли выполнена повторная компиляция JIT.</span><span class="sxs-lookup"><span data-stu-id="4013d-108">[in] A value that indicates whether the JIT recompilation was successful.</span></span>  
  
 `fIsSafeToBlock`  
 <span data-ttu-id="4013d-109">[входные] `true` чтобы указать, что блокировка может привести к тому, что среда выполнения будет ожидать возврата вызывающим потоком из этого обратного вызова. `false` чтобы указать, что блокировка не повлияет на работу среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="4013d-109">[in] `true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span>  
  
 <span data-ttu-id="4013d-110">Значение `true` не нанесет вред исполняющей среде, но может повлиять на результаты профилирования.</span><span class="sxs-lookup"><span data-stu-id="4013d-110">A value of `true` does not harm the runtime, but can affect the profiling results.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4013d-111">Требования</span><span class="sxs-lookup"><span data-stu-id="4013d-111">Requirements</span></span>  

 <span data-ttu-id="4013d-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4013d-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4013d-113">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4013d-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4013d-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4013d-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4013d-115">**.NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4013d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4013d-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="4013d-116">See also</span></span>

- [<span data-ttu-id="4013d-117">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="4013d-117">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="4013d-118">Интерфейс ICorProfilerCallback4</span><span class="sxs-lookup"><span data-stu-id="4013d-118">ICorProfilerCallback4 Interface</span></span>](icorprofilercallback4-interface.md)
- [<span data-ttu-id="4013d-119">Метод JITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="4013d-119">JITCompilationStarted Method</span></span>](icorprofilercallback-jitcompilationstarted-method.md)
- [<span data-ttu-id="4013d-120">Метод ReJITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="4013d-120">ReJITCompilationStarted Method</span></span>](icorprofilercallback4-rejitcompilationstarted-method.md)
