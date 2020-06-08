---
title: Метод ICorProfilerCallback::ExceptionUnwindFinallyLeave
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionUnwindFinallyLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionUnwindFinallyLeave
helpviewer_keywords:
- ICorProfilerCallback::ExceptionUnwindFinallyLeave method [.NET Framework profiling]
- ExceptionUnwindFinallyLeave method [.NET Framework profiling]
ms.assetid: 2350351e-f253-4c0c-a191-f952bc5700e6
topic_type:
- apiref
ms.openlocfilehash: 8da9098e882dd4b4c1f60e4428ebe68421e629e1
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500147"
---
# <a name="icorprofilercallbackexceptionunwindfinallyleave-method"></a><span data-ttu-id="97593-102">Метод ICorProfilerCallback::ExceptionUnwindFinallyLeave</span><span class="sxs-lookup"><span data-stu-id="97593-102">ICorProfilerCallback::ExceptionUnwindFinallyLeave Method</span></span>
<span data-ttu-id="97593-103">Уведомляет профилировщик о том, что фаза очистки в обработке исключений содержит `finally` предложение.</span><span class="sxs-lookup"><span data-stu-id="97593-103">Notifies the profiler that the unwind phase of exception handling has left a `finally` clause.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97593-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="97593-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionUnwindFinallyLeave();  
```  
  
## <a name="remarks"></a><span data-ttu-id="97593-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="97593-105">Remarks</span></span>  
 <span data-ttu-id="97593-106">Профилировщик не должен блокироваться во время этого вызова, так как стек может не находиться в состоянии, допускающем сборку мусора, поэтому невозможно включить вытесненную сборку мусора.</span><span class="sxs-lookup"><span data-stu-id="97593-106">The profiler should not block during this call because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="97593-107">Если профилировщик блокируется здесь и выполняется сборка мусора, среда выполнения будет блокироваться до тех пор, пока этот обратный вызов не вернет значение.</span><span class="sxs-lookup"><span data-stu-id="97593-107">If the profiler blocks here and a garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="97593-108">Кроме того, во время этого вызова профилировщик не должен вызывать управляемый код или каким-либо образом вызывает выделение управляемой памяти.</span><span class="sxs-lookup"><span data-stu-id="97593-108">Also, during this call, the profiler must not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97593-109">Требования</span><span class="sxs-lookup"><span data-stu-id="97593-109">Requirements</span></span>  
 <span data-ttu-id="97593-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="97593-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97593-111">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="97593-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="97593-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="97593-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="97593-113">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="97593-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97593-114">См. также</span><span class="sxs-lookup"><span data-stu-id="97593-114">See also</span></span>

- [<span data-ttu-id="97593-115">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="97593-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="97593-116">Метод ExceptionUnwindFinallyEnter</span><span class="sxs-lookup"><span data-stu-id="97593-116">ExceptionUnwindFinallyEnter Method</span></span>](icorprofilercallback-exceptionunwindfinallyenter-method.md)
