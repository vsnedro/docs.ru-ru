---
title: Интерфейс ICorProfilerCallback6
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback6
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.assetid: edc420b7-96d1-4dec-ace0-36d907f644bc
topic_type:
- apiref
ms.openlocfilehash: 0156a7dfa2a67ce9e62b502df00fc6bc5fccf925
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499185"
---
# <a name="icorprofilercallback6-interface"></a><span data-ttu-id="960f7-102">Интерфейс ICorProfilerCallback6</span><span class="sxs-lookup"><span data-stu-id="960f7-102">ICorProfilerCallback6 Interface</span></span>
<span data-ttu-id="960f7-103">[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="960f7-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="960f7-104">Подкласс [ICorProfilerCallback5](icorprofilercallback5-interface.md) , предоставляющий метод обратного вызова, который среда CLR использует для уведомления профилировщика о загрузке сборки.</span><span class="sxs-lookup"><span data-stu-id="960f7-104">A subclass of [ICorProfilerCallback5](icorprofilercallback5-interface.md) that provides a callback method that the common language runtime uses to notify a profiler that an assembly is loading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="960f7-105">Методы</span><span class="sxs-lookup"><span data-stu-id="960f7-105">Methods</span></span>  
  
|<span data-ttu-id="960f7-106">Метод</span><span class="sxs-lookup"><span data-stu-id="960f7-106">Method</span></span>|<span data-ttu-id="960f7-107">Описание</span><span class="sxs-lookup"><span data-stu-id="960f7-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="960f7-108">Метод GetAssemblyReferences</span><span class="sxs-lookup"><span data-stu-id="960f7-108">GetAssemblyReferences Method</span></span>](icorprofilercallback6-getassemblyreferences-method.md)|<span data-ttu-id="960f7-109">Уведомляет профилировщика о том, что сборка находится на очень ранней стадии загрузки, когда среда CLR выполняет обход замыкания ссылки на сборку.</span><span class="sxs-lookup"><span data-stu-id="960f7-109">Notifies the profiler that an assembly is in a very early loading stage, when the common language runtime performs an assembly reference closure walk.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="960f7-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="960f7-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="960f7-111">Требования</span><span class="sxs-lookup"><span data-stu-id="960f7-111">Requirements</span></span>  
 <span data-ttu-id="960f7-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="960f7-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="960f7-113">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="960f7-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="960f7-114">**.NET Framework версии:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="960f7-114">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="960f7-115">См. также</span><span class="sxs-lookup"><span data-stu-id="960f7-115">See also</span></span>

- [<span data-ttu-id="960f7-116">Профилирующие интерфейсы</span><span class="sxs-lookup"><span data-stu-id="960f7-116">Profiling Interfaces</span></span>](profiling-interfaces.md)
