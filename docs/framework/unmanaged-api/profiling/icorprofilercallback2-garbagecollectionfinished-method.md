---
title: Метод ICorProfilerCallback2::GarbageCollectionFinished
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.GarbageCollectionFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::GarbageCollectionFinished
helpviewer_keywords:
- ICorProfilerCallback2::GarbageCollectionFinished method [.NET Framework profiling]
- GarbageCollectionFinished method [.NET Framework profiling]
ms.assetid: 1a5758ea-2354-43c0-92a3-32c9909d64e1
topic_type:
- apiref
ms.openlocfilehash: 84a71853ba2ccc8b95e4a8936005f2790d09a2c4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717319"
---
# <a name="icorprofilercallback2garbagecollectionfinished-method"></a><span data-ttu-id="52dc2-102">Метод ICorProfilerCallback2::GarbageCollectionFinished</span><span class="sxs-lookup"><span data-stu-id="52dc2-102">ICorProfilerCallback2::GarbageCollectionFinished Method</span></span>

<span data-ttu-id="52dc2-103">Уведомляет профилировщик о завершении сборки мусора и выдает для него все обратные вызовы сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="52dc2-103">Notifies the profiler that garbage collection has completed and all garbage collection callbacks have been issued for it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52dc2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="52dc2-104">Syntax</span></span>  
  
```cpp  
HRESULT GarbageCollectionFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="52dc2-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="52dc2-105">Remarks</span></span>  

 <span data-ttu-id="52dc2-106">Профилировщик может быть защищен для проверки объектов в их конечном расположении при `GarbageCollectionFinished` вызове метода.</span><span class="sxs-lookup"><span data-stu-id="52dc2-106">It is safe for the profiler to inspect objects in their final locations when the `GarbageCollectionFinished` method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52dc2-107">Требования</span><span class="sxs-lookup"><span data-stu-id="52dc2-107">Requirements</span></span>  

 <span data-ttu-id="52dc2-108">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="52dc2-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52dc2-109">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="52dc2-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="52dc2-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="52dc2-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="52dc2-111">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="52dc2-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52dc2-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="52dc2-112">See also</span></span>

- [<span data-ttu-id="52dc2-113">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="52dc2-113">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="52dc2-114">Интерфейс ICorProfilerCallback2</span><span class="sxs-lookup"><span data-stu-id="52dc2-114">ICorProfilerCallback2 Interface</span></span>](icorprofilercallback2-interface.md)
