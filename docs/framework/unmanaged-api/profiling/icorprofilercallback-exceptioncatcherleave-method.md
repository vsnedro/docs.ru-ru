---
title: Метод ICorProfilerCallback::ExceptionCatcherLeave
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionCatcherLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionCatcherLeave
helpviewer_keywords:
- ExceptionCatcherLeave method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionCatcherLeave method [.NET Framework profiling]
ms.assetid: 1f3dbdf5-db0c-4b07-bbb7-375de2a63673
topic_type:
- apiref
ms.openlocfilehash: c0a24a8f9b7c40d87f9b9b6fe77eba7d6c0ea89f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95700032"
---
# <a name="icorprofilercallbackexceptioncatcherleave-method"></a><span data-ttu-id="cccf4-102">Метод ICorProfilerCallback::ExceptionCatcherLeave</span><span class="sxs-lookup"><span data-stu-id="cccf4-102">ICorProfilerCallback::ExceptionCatcherLeave Method</span></span>

<span data-ttu-id="cccf4-103">Уведомляет профилировщик о том, что управление передается из соответствующего `catch` блока.</span><span class="sxs-lookup"><span data-stu-id="cccf4-103">Notifies the profiler that control is being passed out of the appropriate `catch` block.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cccf4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cccf4-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionCatcherLeave();  
```  
  
## <a name="remarks"></a><span data-ttu-id="cccf4-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="cccf4-105">Remarks</span></span>  

 <span data-ttu-id="cccf4-106">Профилировщик не должен блокировать реализацию этого метода, так как стек может не находиться в состоянии, допускающем сборку мусора, поэтому невозможно включить вытесненную сборку мусора.</span><span class="sxs-lookup"><span data-stu-id="cccf4-106">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="cccf4-107">Если профилировщик блокируется здесь и выполняется сборка мусора, среда выполнения блокируется до тех пор, пока этот обратный вызов не вернет значение.</span><span class="sxs-lookup"><span data-stu-id="cccf4-107">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="cccf4-108">Реализация этого метода профилировщиком не должна вызывать управляемый код или каким-либо образом приводит к выделению управляемой памяти.</span><span class="sxs-lookup"><span data-stu-id="cccf4-108">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cccf4-109">Требования</span><span class="sxs-lookup"><span data-stu-id="cccf4-109">Requirements</span></span>  

 <span data-ttu-id="cccf4-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cccf4-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cccf4-111">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="cccf4-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="cccf4-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cccf4-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cccf4-113">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cccf4-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cccf4-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="cccf4-114">See also</span></span>

- [<span data-ttu-id="cccf4-115">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="cccf4-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="cccf4-116">Метод ExceptionCatcherEnter</span><span class="sxs-lookup"><span data-stu-id="cccf4-116">ExceptionCatcherEnter Method</span></span>](icorprofilercallback-exceptioncatcherenter-method.md)
