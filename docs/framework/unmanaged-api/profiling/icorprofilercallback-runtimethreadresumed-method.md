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
ms.openlocfilehash: 0996d7eb5b7354a67106ec7aa8818d5e4d46232e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717285"
---
# <a name="icorprofilercallbackruntimethreadresumed-method"></a><span data-ttu-id="dd623-102">Метод ICorProfilerCallback::RuntimeThreadResumed</span><span class="sxs-lookup"><span data-stu-id="dd623-102">ICorProfilerCallback::RuntimeThreadResumed Method</span></span>

<span data-ttu-id="dd623-103">Уведомляет профилировщик о том, что указанный поток возобновил работу после приостановки.</span><span class="sxs-lookup"><span data-stu-id="dd623-103">Notifies the profiler that the specified thread has resumed after being suspended.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd623-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dd623-104">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeThreadResumed(  
    [in] ThreadID threadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dd623-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="dd623-105">Parameters</span></span>  

 `threadId`  
 <span data-ttu-id="dd623-106">окне Идентификатор возобновленного потока.</span><span class="sxs-lookup"><span data-stu-id="dd623-106">[in] The ID of the thread that has been resumed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dd623-107">Требования</span><span class="sxs-lookup"><span data-stu-id="dd623-107">Requirements</span></span>  

 <span data-ttu-id="dd623-108">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dd623-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd623-109">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="dd623-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="dd623-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dd623-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dd623-111">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd623-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd623-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="dd623-112">See also</span></span>

- [<span data-ttu-id="dd623-113">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="dd623-113">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="dd623-114">Метод RuntimeThreadSuspended</span><span class="sxs-lookup"><span data-stu-id="dd623-114">RuntimeThreadSuspended Method</span></span>](icorprofilercallback-runtimethreadsuspended-method.md)
