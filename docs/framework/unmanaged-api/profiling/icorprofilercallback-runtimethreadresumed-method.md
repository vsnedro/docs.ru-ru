---
title: Метод ICorProfilerCallback::RuntimeThreadResumed
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeThreadResumed
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeThreadResumed
helpviewer_keywords:
- ICorProfilerCallback::RuntimeThreadResumed method [.NET Framework profiling]
- RuntimeThreadResumed method [.NET Framework profiling]
ms.assetid: da984f89-4f53-4ab0-ae6f-3e2ee6085994
topic_type:
- apiref
ms.openlocfilehash: d3949189a72583ebb50b67a270694a31f1eb23dc
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503215"
---
# <a name="icorprofilercallbackruntimethreadresumed-method"></a><span data-ttu-id="f1a5a-102">Метод ICorProfilerCallback::RuntimeThreadResumed</span><span class="sxs-lookup"><span data-stu-id="f1a5a-102">ICorProfilerCallback::RuntimeThreadResumed Method</span></span>
<span data-ttu-id="f1a5a-103">Уведомляет профилировщик о том, что указанный поток возобновил работу после приостановки.</span><span class="sxs-lookup"><span data-stu-id="f1a5a-103">Notifies the profiler that the specified thread has resumed after being suspended.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1a5a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f1a5a-104">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeThreadResumed(  
    [in] ThreadID threadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f1a5a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f1a5a-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="f1a5a-106">окне Идентификатор возобновленного потока.</span><span class="sxs-lookup"><span data-stu-id="f1a5a-106">[in] The ID of the thread that has been resumed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1a5a-107">Требования</span><span class="sxs-lookup"><span data-stu-id="f1a5a-107">Requirements</span></span>  
 <span data-ttu-id="f1a5a-108">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f1a5a-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1a5a-109">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f1a5a-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f1a5a-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f1a5a-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f1a5a-111">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1a5a-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1a5a-112">См. также</span><span class="sxs-lookup"><span data-stu-id="f1a5a-112">See also</span></span>

- [<span data-ttu-id="f1a5a-113">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="f1a5a-113">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="f1a5a-114">Метод RuntimeThreadSuspended</span><span class="sxs-lookup"><span data-stu-id="f1a5a-114">RuntimeThreadSuspended Method</span></span>](icorprofilercallback-runtimethreadsuspended-method.md)
