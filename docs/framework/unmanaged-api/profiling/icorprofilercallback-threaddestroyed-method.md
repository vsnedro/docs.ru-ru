---
title: Метод ICorProfilerCallback::ThreadDestroyed
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ThreadDestroyed
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ThreadDestroyed
helpviewer_keywords:
- ThreadDestroyed method [.NET Framework profiling]
- ICorProfilerCallback::ThreadDestroyed method [.NET Framework profiling]
ms.assetid: 4c2b66fd-0595-40a3-8931-f9c4fff97ac8
topic_type:
- apiref
ms.openlocfilehash: c63b91c39ded58ed208f6920c2bfaeba410c093c
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499861"
---
# <a name="icorprofilercallbackthreaddestroyed-method"></a><span data-ttu-id="f4ac1-102">Метод ICorProfilerCallback::ThreadDestroyed</span><span class="sxs-lookup"><span data-stu-id="f4ac1-102">ICorProfilerCallback::ThreadDestroyed Method</span></span>
<span data-ttu-id="f4ac1-103">Уведомляет профилировщик о том, что поток был уничтожен.</span><span class="sxs-lookup"><span data-stu-id="f4ac1-103">Notifies the profiler that a thread has been destroyed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4ac1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f4ac1-104">Syntax</span></span>  
  
```cpp  
HRESULT ThreadDestroyed(  
    [in] ThreadID threadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f4ac1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f4ac1-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="f4ac1-106">окне Идентификатор уничтоженного потока.</span><span class="sxs-lookup"><span data-stu-id="f4ac1-106">[in] The ID of the thread that has been destroyed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f4ac1-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="f4ac1-107">Remarks</span></span>  
 <span data-ttu-id="f4ac1-108">`threadId`Значение больше не является допустимым во время этого вызова.</span><span class="sxs-lookup"><span data-stu-id="f4ac1-108">The `threadId` value is no longer valid at the time of this call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f4ac1-109">Требования</span><span class="sxs-lookup"><span data-stu-id="f4ac1-109">Requirements</span></span>  
 <span data-ttu-id="f4ac1-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f4ac1-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4ac1-111">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f4ac1-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f4ac1-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f4ac1-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f4ac1-113">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f4ac1-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4ac1-114">См. также</span><span class="sxs-lookup"><span data-stu-id="f4ac1-114">See also</span></span>

- [<span data-ttu-id="f4ac1-115">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="f4ac1-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="f4ac1-116">Метод ThreadCreated</span><span class="sxs-lookup"><span data-stu-id="f4ac1-116">ThreadCreated Method</span></span>](icorprofilercallback-threadcreated-method.md)
