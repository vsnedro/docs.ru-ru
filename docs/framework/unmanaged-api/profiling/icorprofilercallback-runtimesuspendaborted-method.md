---
title: Метод ICorProfilerCallback::RuntimeSuspendAborted
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeSuspendAborted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeSuspendAborted
helpviewer_keywords:
- ICorProfilerCallback::RuntimeSuspendAborted method [.NET Framework profiling]
- RuntimeSuspendAborted method [.NET Framework profiling]
ms.assetid: 5a8a4277-345b-448b-a028-fc8cff9998aa
topic_type:
- apiref
ms.openlocfilehash: 4b6eb59dd771e4013106e6a77fc7475b77b2b007
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732025"
---
# <a name="icorprofilercallbackruntimesuspendaborted-method"></a><span data-ttu-id="555ee-102">Метод ICorProfilerCallback::RuntimeSuspendAborted</span><span class="sxs-lookup"><span data-stu-id="555ee-102">ICorProfilerCallback::RuntimeSuspendAborted Method</span></span>

<span data-ttu-id="555ee-103">Уведомляет профилировщик о том, что среда выполнения прервал приостановленную приостановку среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="555ee-103">Notifies the profiler that the runtime has aborted the runtime suspension that was occurring.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="555ee-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="555ee-104">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeSuspendAborted();  
```  
  
## <a name="remarks"></a><span data-ttu-id="555ee-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="555ee-105">Remarks</span></span>  

 <span data-ttu-id="555ee-106">Приостановка во время выполнения может быть прервана, если два потока одновременно пытаются приостановить выполнение.</span><span class="sxs-lookup"><span data-stu-id="555ee-106">The run-time suspension might be aborted if two threads simultaneously attempt to suspend the runtime.</span></span>  
  
 <span data-ttu-id="555ee-107">Обратный вызов [ICorProfilerCallback:: RuntimeSuspendFinished](icorprofilercallback-runtimesuspendfinished-method.md) или `RuntimeSuspendAborted` обратный вызов будет выполняться в одном потоке после обратного вызова [ICorProfilerCallback:: рунтимесуспендстартед](icorprofilercallback-runtimesuspendstarted-method.md) .</span><span class="sxs-lookup"><span data-stu-id="555ee-107">Either the [ICorProfilerCallback::RuntimeSuspendFinished](icorprofilercallback-runtimesuspendfinished-method.md) callback or the `RuntimeSuspendAborted` callback will occur on a single thread following a [ICorProfilerCallback::RuntimeSuspendStarted](icorprofilercallback-runtimesuspendstarted-method.md) callback.</span></span>  
  
 <span data-ttu-id="555ee-108">`RuntimeSuspendAborted`Обратный вызов гарантированно выполняется в том же потоке, что и `RuntimeSuspendStarted` обратный вызов.</span><span class="sxs-lookup"><span data-stu-id="555ee-108">The `RuntimeSuspendAborted` callback is guaranteed to occur on the same thread as the `RuntimeSuspendStarted` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="555ee-109">Требования</span><span class="sxs-lookup"><span data-stu-id="555ee-109">Requirements</span></span>  

 <span data-ttu-id="555ee-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="555ee-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="555ee-111">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="555ee-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="555ee-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="555ee-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="555ee-113">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="555ee-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="555ee-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="555ee-114">See also</span></span>

- [<span data-ttu-id="555ee-115">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="555ee-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
