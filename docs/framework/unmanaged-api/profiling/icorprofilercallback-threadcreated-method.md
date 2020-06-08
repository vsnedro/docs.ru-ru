---
title: Метод ICorProfilerCallback::ThreadCreated
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ThreadCreated
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ThreadCreated
helpviewer_keywords:
- ICorProfilerCallback::ThreadCreated method [.NET Framework profiling]
- ThreadCreated method [.NET Framework profiling]
ms.assetid: cca0f799-09b8-4689-a33c-6d6537943a9b
topic_type:
- apiref
ms.openlocfilehash: 25a4b101388bfc0151ba7c9c52da6561d48f806b
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503163"
---
# <a name="icorprofilercallbackthreadcreated-method"></a><span data-ttu-id="1af9b-102">Метод ICorProfilerCallback::ThreadCreated</span><span class="sxs-lookup"><span data-stu-id="1af9b-102">ICorProfilerCallback::ThreadCreated Method</span></span>
<span data-ttu-id="1af9b-103">Уведомляет профилировщик о том, что поток был создан.</span><span class="sxs-lookup"><span data-stu-id="1af9b-103">Notifies the profiler that a thread has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1af9b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1af9b-104">Syntax</span></span>  
  
```cpp  
HRESULT ThreadCreated(  
    [in] ThreadID threadId);
```  
  
## <a name="parameters"></a><span data-ttu-id="1af9b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1af9b-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="1af9b-106">окне Идентификатор созданного потока.</span><span class="sxs-lookup"><span data-stu-id="1af9b-106">[in] The ID of the thread that has been created.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1af9b-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="1af9b-107">Remarks</span></span>  
 <span data-ttu-id="1af9b-108">`threadId`Значение немедленно является допустимым.</span><span class="sxs-lookup"><span data-stu-id="1af9b-108">The `threadId` value is immediately valid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1af9b-109">Требования</span><span class="sxs-lookup"><span data-stu-id="1af9b-109">Requirements</span></span>  
 <span data-ttu-id="1af9b-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1af9b-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1af9b-111">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1af9b-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1af9b-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1af9b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1af9b-113">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1af9b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1af9b-114">См. также</span><span class="sxs-lookup"><span data-stu-id="1af9b-114">See also</span></span>

- [<span data-ttu-id="1af9b-115">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="1af9b-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="1af9b-116">Метод ThreadDestroyed</span><span class="sxs-lookup"><span data-stu-id="1af9b-116">ThreadDestroyed Method</span></span>](icorprofilercallback-threaddestroyed-method.md)
