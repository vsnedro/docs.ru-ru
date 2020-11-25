---
title: Интерфейс ICorProfilerCallback9
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback9
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 23b91a2a58c6e76b31b94e0fa3661dfbc8e18e33
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712772"
---
# <a name="icorprofilercallback9-interface"></a><span data-ttu-id="ce8cd-102">Интерфейс ICorProfilerCallback9</span><span class="sxs-lookup"><span data-stu-id="ce8cd-102">ICorProfilerCallback9 Interface</span></span>

<span data-ttu-id="ce8cd-103">[Поддерживается в .NET Framework 4.7.2 и более поздних версиях]</span><span class="sxs-lookup"><span data-stu-id="ce8cd-103">[Supported in the .NET Framework 4.7.2 and later versions]</span></span>  

 <span data-ttu-id="ce8cd-104">Подкласс [ICorProfilerCallback8](icorprofilercallback8-interface.md) , предоставляющий метод обратного вызова, используемый средой CLR для уведомления профилировщика о том, что динамический метод был собран в мусор и затем выгружен.</span><span class="sxs-lookup"><span data-stu-id="ce8cd-104">A subclass of [ICorProfilerCallback8](icorprofilercallback8-interface.md) that provides a callback method used by the common language runtime to notify the profiler that a dynamic method has been garbage collected and subsequently unloaded.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ce8cd-105">Методы</span><span class="sxs-lookup"><span data-stu-id="ce8cd-105">Methods</span></span>  
  
|<span data-ttu-id="ce8cd-106">Метод</span><span class="sxs-lookup"><span data-stu-id="ce8cd-106">Method</span></span>|<span data-ttu-id="ce8cd-107">Описание</span><span class="sxs-lookup"><span data-stu-id="ce8cd-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ce8cd-108">Метод DynamicMethodUnloaded</span><span class="sxs-lookup"><span data-stu-id="ce8cd-108">DynamicMethodUnloaded Method</span></span>](ICorProfilerCallback9-dynamicmethodunloaded-method.md)|<span data-ttu-id="ce8cd-109">Уведомляет профилировщик о том, что динамический метод был собран в мусор и затем выгружен.</span><span class="sxs-lookup"><span data-stu-id="ce8cd-109">Notifies the profiler that a dynamic method has been garbage collected and subsequently unloaded.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ce8cd-110">Требования</span><span class="sxs-lookup"><span data-stu-id="ce8cd-110">Requirements</span></span>  

 <span data-ttu-id="ce8cd-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ce8cd-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce8cd-112">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ce8cd-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
<span data-ttu-id="ce8cd-113">**.NET Framework версии:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="ce8cd-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="ce8cd-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ce8cd-114">See also</span></span>

- [<span data-ttu-id="ce8cd-115">Профилирующие интерфейсы</span><span class="sxs-lookup"><span data-stu-id="ce8cd-115">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="ce8cd-116">Интерфейс ICorProfilerCallback8</span><span class="sxs-lookup"><span data-stu-id="ce8cd-116">ICorProfilerCallback8 Interface</span></span>](icorprofilercallback9-interface.md)
- [<span data-ttu-id="ce8cd-117">ICorProfilerCallback8. Динамикмесоджиткомпилатионстартед, метод</span><span class="sxs-lookup"><span data-stu-id="ce8cd-117">ICorProfilerCallback8.DynamicMethodJITCompilationStarted method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [<span data-ttu-id="ce8cd-118">ICorProfilerCallback8. Динамикмесоджиткомпилатионфинишед, метод</span><span class="sxs-lookup"><span data-stu-id="ce8cd-118">ICorProfilerCallback8.DynamicMethodJITCompilationFinished method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
