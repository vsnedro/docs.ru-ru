---
title: Интерфейс ICorProfilerCallback7
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback7
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.assetid: a0be019e-aaa1-4036-990f-565f114d4b5c
ms.openlocfilehash: 9a49d8e1ff31942c6564ab560d6726b9ede26466
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499146"
---
# <a name="icorprofilercallback7-interface"></a><span data-ttu-id="6ce66-102">Интерфейс ICorProfilerCallback7</span><span class="sxs-lookup"><span data-stu-id="6ce66-102">ICorProfilerCallback7 Interface</span></span>
<span data-ttu-id="6ce66-103">[Поддерживается в .NET Framework 4.6.1 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="6ce66-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="6ce66-104">Подкласс [ICorProfilerCallback6](icorprofilercallback6-interface.md) , который предоставляет метод обратного вызова, используемый средой CLR для уведомления профилировщика, что обновляется поток символов, связанный с модулем в памяти.</span><span class="sxs-lookup"><span data-stu-id="6ce66-104">A subclass of [ICorProfilerCallback6](icorprofilercallback6-interface.md) that provides a callback method that the common language runtime uses to notify the profiler that the symbol stream associated with an in-memory module is updated.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6ce66-105">Методы</span><span class="sxs-lookup"><span data-stu-id="6ce66-105">Methods</span></span>  
  
|<span data-ttu-id="6ce66-106">Метод</span><span class="sxs-lookup"><span data-stu-id="6ce66-106">Method</span></span>|<span data-ttu-id="6ce66-107">Описание</span><span class="sxs-lookup"><span data-stu-id="6ce66-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6ce66-108">Метод ModuleInMemorySymbolsUpdated</span><span class="sxs-lookup"><span data-stu-id="6ce66-108">ModuleInMemorySymbolsUpdated Method</span></span>](icorprofilercallback7-moduleinmemorysymbolsupdated-method.md)|<span data-ttu-id="6ce66-109">Уведомляет профилировщик об обновлении потока символов, связанного с модулем в памяти.</span><span class="sxs-lookup"><span data-stu-id="6ce66-109">Notifies the profiler that the symbol stream associated with an in-memory module is updated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6ce66-110">Требования</span><span class="sxs-lookup"><span data-stu-id="6ce66-110">Requirements</span></span>  
 <span data-ttu-id="6ce66-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6ce66-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ce66-112">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6ce66-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6ce66-113">**.NET Framework версии:**[!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ce66-113">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ce66-114">См. также</span><span class="sxs-lookup"><span data-stu-id="6ce66-114">See also</span></span>

- [<span data-ttu-id="6ce66-115">Профилирующие интерфейсы</span><span class="sxs-lookup"><span data-stu-id="6ce66-115">Profiling Interfaces</span></span>](profiling-interfaces.md)
