---
title: Метод ICorProfilerCallback::RuntimeSuspendStarted
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeSuspendStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeSuspendStarted
helpviewer_keywords:
- ICorProfilerCallback::RuntimeSuspendStarted method [.NET Framework profiling]
- RuntimeSuspendStarted method [.NET Framework profiling]
ms.assetid: c8461cac-e31b-4efa-ad2c-26598173eb96
topic_type:
- apiref
ms.openlocfilehash: cc01254d9604ce39c964c7d78059ef4087483c77
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503228"
---
# <a name="icorprofilercallbackruntimesuspendstarted-method"></a><span data-ttu-id="92f1b-102">Метод ICorProfilerCallback::RuntimeSuspendStarted</span><span class="sxs-lookup"><span data-stu-id="92f1b-102">ICorProfilerCallback::RuntimeSuspendStarted Method</span></span>
<span data-ttu-id="92f1b-103">Уведомляет профилировщик о том, что среда выполнения собирается приостановить все потоки среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="92f1b-103">Notifies the profiler that the runtime is about to suspend all runtime threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92f1b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="92f1b-104">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeSuspendStarted(  
    [in] COR_PRF_SUSPEND_REASON suspendReason);  
```  
  
## <a name="parameters"></a><span data-ttu-id="92f1b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="92f1b-105">Parameters</span></span>  
 `suspendReason`  
 <span data-ttu-id="92f1b-106">окне Значение перечисления [COR_PRF_SUSPEND_REASON](cor-prf-suspend-reason-enumeration.md) , указывающее причину приостановки.</span><span class="sxs-lookup"><span data-stu-id="92f1b-106">[in] A value of the [COR_PRF_SUSPEND_REASON](cor-prf-suspend-reason-enumeration.md) enumeration that indicates the reason for the suspension.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="92f1b-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="92f1b-107">Remarks</span></span>  
 <span data-ttu-id="92f1b-108">Все потоки среды выполнения, наявляющиеся в неуправляемом коде, могут продолжать выполняться до тех пор, пока они не попытаются повторно войти в среду выполнения.</span><span class="sxs-lookup"><span data-stu-id="92f1b-108">All runtime threads that are in unmanaged code are allowed to continue running until they try to re-enter the runtime.</span></span> <span data-ttu-id="92f1b-109">На этом этапе они также будут приостановлены до тех пор, пока среда выполнения не возобновит работу.</span><span class="sxs-lookup"><span data-stu-id="92f1b-109">At that point they will also be suspended until the runtime resumes.</span></span> <span data-ttu-id="92f1b-110">Это также относится к новым потокам, которые вводят среду выполнения.</span><span class="sxs-lookup"><span data-stu-id="92f1b-110">This also applies to new threads that enter the runtime.</span></span> <span data-ttu-id="92f1b-111">Все потоки в среде выполнения либо приостанавливаются немедленно, если они уже находятся в коде для преобразования, либо если они запросят приостановить работу в случае, если они достигают кода источника.</span><span class="sxs-lookup"><span data-stu-id="92f1b-111">All threads in the runtime are either suspended immediately if they are already in interruptible code, or they are asked to suspend when they reach interruptible code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="92f1b-112">Требования</span><span class="sxs-lookup"><span data-stu-id="92f1b-112">Requirements</span></span>  
 <span data-ttu-id="92f1b-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="92f1b-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="92f1b-114">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="92f1b-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="92f1b-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="92f1b-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="92f1b-116">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="92f1b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92f1b-117">См. также</span><span class="sxs-lookup"><span data-stu-id="92f1b-117">See also</span></span>

- [<span data-ttu-id="92f1b-118">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="92f1b-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="92f1b-119">Метод RuntimeSuspendAborted</span><span class="sxs-lookup"><span data-stu-id="92f1b-119">RuntimeSuspendAborted Method</span></span>](icorprofilercallback-runtimesuspendaborted-method.md)
- [<span data-ttu-id="92f1b-120">Метод RuntimeSuspendFinished</span><span class="sxs-lookup"><span data-stu-id="92f1b-120">RuntimeSuspendFinished Method</span></span>](icorprofilercallback-runtimesuspendfinished-method.md)
