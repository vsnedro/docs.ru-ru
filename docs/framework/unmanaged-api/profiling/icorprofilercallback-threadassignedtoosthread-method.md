---
title: Метод ICorProfilerCallback::ThreadAssignedToOSThread
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ThreadAssignedToOSThread
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ThreadAssignedToOSThread
helpviewer_keywords:
- ThreadAssignedToOSThread method [.NET Framework profiling]
- ICorProfilerCallback::ThreadAssignedToOSThread method [.NET Framework profiling]
ms.assetid: f9671e5a-7b14-4f5b-8404-58136422c8b2
topic_type:
- apiref
ms.openlocfilehash: 2d6f34d88dd79fe350f1c018e3afa55e5b180c46
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732012"
---
# <a name="icorprofilercallbackthreadassignedtoosthread-method"></a><span data-ttu-id="5deb3-102">Метод ICorProfilerCallback::ThreadAssignedToOSThread</span><span class="sxs-lookup"><span data-stu-id="5deb3-102">ICorProfilerCallback::ThreadAssignedToOSThread Method</span></span>

<span data-ttu-id="5deb3-103">Уведомляет профилировщик о том, что управляемый поток реализуется с помощью определенного потока операционной системы.</span><span class="sxs-lookup"><span data-stu-id="5deb3-103">Notifies the profiler that a managed thread is being implemented using a particular operating system thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5deb3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5deb3-104">Syntax</span></span>  
  
```cpp  
HRESULT ThreadAssignedToOSThread(  
    [in] ThreadID managedThreadId,  
    [in] DWORD    osThreadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5deb3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5deb3-105">Parameters</span></span>  

 `managedThreadId`  
 <span data-ttu-id="5deb3-106">окне Идентификатор управляемого потока.</span><span class="sxs-lookup"><span data-stu-id="5deb3-106">[in] The identifier of the managed thread.</span></span>  
  
 `osThreadId`  
 <span data-ttu-id="5deb3-107">окне Идентификатор потока операционной системы.</span><span class="sxs-lookup"><span data-stu-id="5deb3-107">[in] The identifier of the operating system thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5deb3-108">Комментарии</span><span class="sxs-lookup"><span data-stu-id="5deb3-108">Remarks</span></span>  

 <span data-ttu-id="5deb3-109">`ThreadAssignedToOSThread`Обратный вызов существует, чтобы профилировщик мог поддерживать точное сопоставление по волокнам потоков операционной системы с управляемыми потоками.</span><span class="sxs-lookup"><span data-stu-id="5deb3-109">The `ThreadAssignedToOSThread` callback exists so that the profiler can maintain an accurate mapping across fibers of operating system threads to managed threads.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5deb3-110">Требования</span><span class="sxs-lookup"><span data-stu-id="5deb3-110">Requirements</span></span>  

 <span data-ttu-id="5deb3-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5deb3-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5deb3-112">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5deb3-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5deb3-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5deb3-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5deb3-114">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5deb3-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5deb3-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="5deb3-115">See also</span></span>

- [<span data-ttu-id="5deb3-116">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="5deb3-116">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
