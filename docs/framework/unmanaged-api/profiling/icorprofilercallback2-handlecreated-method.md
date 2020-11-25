---
title: Метод ICorProfilerCallback2::HandleCreated
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.HandleCreated
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::HandleCreated
helpviewer_keywords:
- HandleCreated method [.NET Framework profiling]
- ICorProfilerCallback2::HandleCreated method [.NET Framework profiling]
ms.assetid: 6bbb7786-7c38-490f-9834-91aa2795c355
topic_type:
- apiref
ms.openlocfilehash: 6cd931f6c680a07327915ab4680702af298ca1ef
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717320"
---
# <a name="icorprofilercallback2handlecreated-method"></a><span data-ttu-id="f5fb6-102">Метод ICorProfilerCallback2::HandleCreated</span><span class="sxs-lookup"><span data-stu-id="f5fb6-102">ICorProfilerCallback2::HandleCreated Method</span></span>

<span data-ttu-id="f5fb6-103">Уведомляет профилировщик кода о создании обработчика сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="f5fb6-103">Notifies the code profiler that a garbage collection handle has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5fb6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f5fb6-104">Syntax</span></span>  
  
```cpp  
HRESULT HandleCreated(  
    [in] GCHandleID handleId,  
    [in] ObjectID initialObjectId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f5fb6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f5fb6-105">Parameters</span></span>  

 `handleId`  
 <span data-ttu-id="f5fb6-106">окне Идентификатор обработчика для сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="f5fb6-106">[in] The ID of the handle for the garbage collection.</span></span>  
  
 `initialObjectId`  
 <span data-ttu-id="f5fb6-107">окне Идентификатор объекта, для которого был создан маркер сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="f5fb6-107">[in] The ID of the object for which the garbage collection handle was created.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5fb6-108">Требования</span><span class="sxs-lookup"><span data-stu-id="f5fb6-108">Requirements</span></span>  

 <span data-ttu-id="f5fb6-109">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f5fb6-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5fb6-110">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f5fb6-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f5fb6-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f5fb6-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f5fb6-112">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5fb6-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5fb6-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f5fb6-113">See also</span></span>

- [<span data-ttu-id="f5fb6-114">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="f5fb6-114">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="f5fb6-115">Интерфейс ICorProfilerCallback2</span><span class="sxs-lookup"><span data-stu-id="f5fb6-115">ICorProfilerCallback2 Interface</span></span>](icorprofilercallback2-interface.md)
