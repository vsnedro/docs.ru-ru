---
title: Метод ICorProfilerCallback2::FinalizeableObjectQueued
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.FinalizeableObjectQueued
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::FinalizeableObjectQueued
helpviewer_keywords:
- FinalizeableObjectQueued method [.NET Framework profiling]
- ICorProfilerCallback2::FinalizeableObjectQueued method [.NET Framework profiling]
ms.assetid: 92d76893-683c-475d-9996-5bff03cdb10f
topic_type:
- apiref
ms.openlocfilehash: e2e01c396a67614464e3d4ca50de992388961463
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499831"
---
# <a name="icorprofilercallback2finalizeableobjectqueued-method"></a><span data-ttu-id="d1ffc-102">Метод ICorProfilerCallback2::FinalizeableObjectQueued</span><span class="sxs-lookup"><span data-stu-id="d1ffc-102">ICorProfilerCallback2::FinalizeableObjectQueued Method</span></span>
<span data-ttu-id="d1ffc-103">Уведомляет профилировщик кода о том, что объект с методом завершения был помещен в очередь в поток метода завершения для выполнения своего `Finalize` метода.</span><span class="sxs-lookup"><span data-stu-id="d1ffc-103">Notifies the code profiler that an object with a finalizer has been queued to the finalizer thread for execution of its `Finalize` method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1ffc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d1ffc-104">Syntax</span></span>  
  
```cpp  
HRESULT FinalizeableObjectQueued(  
    [in] DWORD finalizerFlags,  
    [in] ObjectID objectID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d1ffc-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d1ffc-105">Parameters</span></span>  
 `finalizerFlags`  
 <span data-ttu-id="d1ffc-106">окне Значение перечисления [COR_PRF_FINALIZER_FLAGS](cor-prf-finalizer-flags-enumeration.md) , описывающее аспекты метода завершения.</span><span class="sxs-lookup"><span data-stu-id="d1ffc-106">[in] A value of the [COR_PRF_FINALIZER_FLAGS](cor-prf-finalizer-flags-enumeration.md) enumeration that describes aspects of the finalizer.</span></span>  
  
 `objectID`  
 <span data-ttu-id="d1ffc-107">окне Идентификатор объекта, который был поставлен в очередь.</span><span class="sxs-lookup"><span data-stu-id="d1ffc-107">[in] The ID of the object that has been queued.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1ffc-108">Требования</span><span class="sxs-lookup"><span data-stu-id="d1ffc-108">Requirements</span></span>  
 <span data-ttu-id="d1ffc-109">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d1ffc-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d1ffc-110">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d1ffc-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d1ffc-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d1ffc-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d1ffc-112">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d1ffc-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1ffc-113">См. также</span><span class="sxs-lookup"><span data-stu-id="d1ffc-113">See also</span></span>

- [<span data-ttu-id="d1ffc-114">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="d1ffc-114">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="d1ffc-115">Интерфейс ICorProfilerCallback2</span><span class="sxs-lookup"><span data-stu-id="d1ffc-115">ICorProfilerCallback2 Interface</span></span>](icorprofilercallback2-interface.md)
