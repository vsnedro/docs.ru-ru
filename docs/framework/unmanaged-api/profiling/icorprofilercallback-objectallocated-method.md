---
title: Метод ICorProfilerCallback::ObjectAllocated
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ObjectAllocated
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ObjectAllocated
helpviewer_keywords:
- ObjectAllocated method [.NET Framework profiling]
- ICorProfilerCallback::ObjectAllocated method [.NET Framework profiling]
ms.assetid: eb412622-77cc-4abd-a2cd-c910fe8edd54
topic_type:
- apiref
ms.openlocfilehash: 9a402b7dfc3ece9d38994ed897162fe0d81ff0b9
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503306"
---
# <a name="icorprofilercallbackobjectallocated-method"></a><span data-ttu-id="5b0cb-102">Метод ICorProfilerCallback::ObjectAllocated</span><span class="sxs-lookup"><span data-stu-id="5b0cb-102">ICorProfilerCallback::ObjectAllocated Method</span></span>
<span data-ttu-id="5b0cb-103">Уведомляет профилировщик о том, что память в куче была выделена для объекта.</span><span class="sxs-lookup"><span data-stu-id="5b0cb-103">Notifies the profiler that memory within the heap has been allocated for an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b0cb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5b0cb-104">Syntax</span></span>  
  
```cpp  
HRESULT ObjectAllocated(  
    [in] ObjectID objectId,  
    [in] ClassID classId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5b0cb-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5b0cb-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="5b0cb-106">окне Идентификатор объекта, для которого была выделена память.</span><span class="sxs-lookup"><span data-stu-id="5b0cb-106">[in] The ID of the object for which memory was allocated.</span></span>  
  
 `classId`  
 <span data-ttu-id="5b0cb-107">окне Идентификатор класса, экземпляр которого является объектом.</span><span class="sxs-lookup"><span data-stu-id="5b0cb-107">[in] The ID of the class of which the object is an instance.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5b0cb-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="5b0cb-108">Remarks</span></span>  
 <span data-ttu-id="5b0cb-109">`ObjectedAllocated`Метод не вызывается для выделений из стека или неуправляемой памяти.</span><span class="sxs-lookup"><span data-stu-id="5b0cb-109">The `ObjectedAllocated` method is not called for allocations from either the stack or unmanaged memory.</span></span> <span data-ttu-id="5b0cb-110">`classId`Параметр может ссылаться на класс в управляемом коде, который еще не был загружен.</span><span class="sxs-lookup"><span data-stu-id="5b0cb-110">The `classId` parameter can refer to a class in managed code that has not been loaded yet.</span></span> <span data-ttu-id="5b0cb-111">Профилировщик получит обратный вызов загрузки класса для этого класса сразу после `ObjectAllocated` обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="5b0cb-111">The profiler will receive a class load callback for that class immediately after the `ObjectAllocated` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b0cb-112">Требования</span><span class="sxs-lookup"><span data-stu-id="5b0cb-112">Requirements</span></span>  
 <span data-ttu-id="5b0cb-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5b0cb-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b0cb-114">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5b0cb-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5b0cb-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5b0cb-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5b0cb-116">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b0cb-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b0cb-117">См. также</span><span class="sxs-lookup"><span data-stu-id="5b0cb-117">See also</span></span>

- [<span data-ttu-id="5b0cb-118">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="5b0cb-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="5b0cb-119">Метод ClassLoadStarted</span><span class="sxs-lookup"><span data-stu-id="5b0cb-119">ClassLoadStarted Method</span></span>](icorprofilercallback-classloadstarted-method.md)
- [<span data-ttu-id="5b0cb-120">Метод ClassLoadFinished</span><span class="sxs-lookup"><span data-stu-id="5b0cb-120">ClassLoadFinished Method</span></span>](icorprofilercallback-classloadfinished-method.md)
