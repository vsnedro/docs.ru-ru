---
title: Интерфейс ICorProfilerCallback5
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback5
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback5
helpviewer_keywords:
- ICorProfilerCallback5 interface [.NET Framework profiling]
ms.assetid: 61d2e9ef-5f1f-4771-8847-239616e35d84
topic_type:
- apiref
ms.openlocfilehash: 02a690503d7b6323f19dcb66247d8a552b760b1c
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499211"
---
# <a name="icorprofilercallback5-interface"></a><span data-ttu-id="fc6ee-102">Интерфейс ICorProfilerCallback5</span><span class="sxs-lookup"><span data-stu-id="fc6ee-102">ICorProfilerCallback5 Interface</span></span>
<span data-ttu-id="fc6ee-103">Дополняет сведения, чтобы помочь профилировщику определить полное закрытие динамических объектов при использовании метода [ICorProfilerCallback:: RootReferences](icorprofilercallback-rootreferences-method.md) или [ICorProfilerCallback2:: RootReferences2](icorprofilercallback2-rootreferences2-method.md) вместе с методами [ICorProfilerCallback:: ObjectReferences](icorprofilercallback-objectreferences-method.md) и [ConditionalWeakTableElementReferences](icorprofilercallback5-conditionalweaktableelementreferences-method.md) .</span><span class="sxs-lookup"><span data-stu-id="fc6ee-103">Supplements information to help a profiler identify the full closure of live objects, when used with either the [ICorProfilerCallback::RootReferences](icorprofilercallback-rootreferences-method.md) or [ICorProfilerCallback2::RootReferences2](icorprofilercallback2-rootreferences2-method.md) method together with the [ICorProfilerCallback::ObjectReferences](icorprofilercallback-objectreferences-method.md) and [ConditionalWeakTableElementReferences](icorprofilercallback5-conditionalweaktableelementreferences-method.md) methods.</span></span>  
  
 <span data-ttu-id="fc6ee-104">Для подписки на уведомления, связанные с зависимыми дескрипторами профилировщик управляемой памяти должен реализовать `ICorProfilerCallback5`.</span><span class="sxs-lookup"><span data-stu-id="fc6ee-104">`ICorProfilerCallback5` must be implemented by a managed memory profiler to subscribe to notifications related to dependent handles.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fc6ee-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="fc6ee-105">Remarks</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fc6ee-106">Методы</span><span class="sxs-lookup"><span data-stu-id="fc6ee-106">Methods</span></span>  
  
|<span data-ttu-id="fc6ee-107">Метод</span><span class="sxs-lookup"><span data-stu-id="fc6ee-107">Method</span></span>|<span data-ttu-id="fc6ee-108">Описание</span><span class="sxs-lookup"><span data-stu-id="fc6ee-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fc6ee-109">Метод ConditionalWeakTableElementReferences</span><span class="sxs-lookup"><span data-stu-id="fc6ee-109">ConditionalWeakTableElementReferences Method</span></span>](icorprofilercallback5-conditionalweaktableelementreferences-method.md)|<span data-ttu-id="fc6ee-110">Идентифицирует транзитивное замыкание объектов, на которые ссылаются эти корневые элементы как через прямые ссылки на поля члена, так и через зависимости `ConditionalWeakTable`.</span><span class="sxs-lookup"><span data-stu-id="fc6ee-110">Identifies the transitive closure of objects referenced by those roots through both direct member field references and through `ConditionalWeakTable` dependencies.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fc6ee-111">Требования</span><span class="sxs-lookup"><span data-stu-id="fc6ee-111">Requirements</span></span>  
 <span data-ttu-id="fc6ee-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fc6ee-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc6ee-113">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fc6ee-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="fc6ee-114">**.NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc6ee-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc6ee-115">См. также</span><span class="sxs-lookup"><span data-stu-id="fc6ee-115">See also</span></span>

- [<span data-ttu-id="fc6ee-116">Профилирующие интерфейсы</span><span class="sxs-lookup"><span data-stu-id="fc6ee-116">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="fc6ee-117">Интерфейс ICorProfilerCallback2</span><span class="sxs-lookup"><span data-stu-id="fc6ee-117">ICorProfilerCallback2 Interface</span></span>](icorprofilercallback2-interface.md)
