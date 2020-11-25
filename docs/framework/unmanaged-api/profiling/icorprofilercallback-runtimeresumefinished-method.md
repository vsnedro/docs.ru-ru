---
title: Метод ICorProfilerCallback::RuntimeResumeFinished
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeResumeFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeResumeFinished
helpviewer_keywords:
- RuntimeResumeFinished method [.NET Framework profiling]
- ICorProfilerCallback::RuntimeResumeFinished method [.NET Framework profiling]
ms.assetid: 76de0494-dc49-426b-887d-bee98806a982
topic_type:
- apiref
ms.openlocfilehash: e7bd07205a87ecefb658e01db17100a48681b54b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732038"
---
# <a name="icorprofilercallbackruntimeresumefinished-method"></a><span data-ttu-id="3715c-102">Метод ICorProfilerCallback::RuntimeResumeFinished</span><span class="sxs-lookup"><span data-stu-id="3715c-102">ICorProfilerCallback::RuntimeResumeFinished Method</span></span>

<span data-ttu-id="3715c-103">Уведомляет профилировщик о том, что среда выполнения возобновила все потоки среды выполнения и вернула нормальную работу.</span><span class="sxs-lookup"><span data-stu-id="3715c-103">Notifies the profiler that the runtime has resumed all runtime threads and has returned to normal operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3715c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3715c-104">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeResumeFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="3715c-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="3715c-105">Remarks</span></span>  

 <span data-ttu-id="3715c-106">`RuntimeResumeFinished`Обратный вызов не гарантируется в том же потоке, что и обратный вызов [ICorProfilerCallback:: рунтимесуспендстартед](icorprofilercallback-runtimesuspendstarted-method.md) .</span><span class="sxs-lookup"><span data-stu-id="3715c-106">The `RuntimeResumeFinished` callback is not guaranteed to occur on the same thread as the [ICorProfilerCallback::RuntimeSuspendStarted](icorprofilercallback-runtimesuspendstarted-method.md) callback.</span></span> <span data-ttu-id="3715c-107">Однако гарантируется, что она будет выполняться в том же потоке, что и обратный вызов [ICorProfilerCallback:: RuntimeResumeStarted](icorprofilercallback-runtimeresumestarted-method.md) .</span><span class="sxs-lookup"><span data-stu-id="3715c-107">However, it is guaranteed to occur on the same thread as the [ICorProfilerCallback::RuntimeResumeStarted](icorprofilercallback-runtimeresumestarted-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3715c-108">Требования</span><span class="sxs-lookup"><span data-stu-id="3715c-108">Requirements</span></span>  

 <span data-ttu-id="3715c-109">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3715c-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3715c-110">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3715c-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3715c-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3715c-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3715c-112">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3715c-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3715c-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="3715c-113">See also</span></span>

- [<span data-ttu-id="3715c-114">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="3715c-114">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
