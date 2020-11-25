---
title: Интерфейс ICorProfilerCallback8
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 22a133d02bb69026190428905379323362943d40
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732389"
---
# <a name="icorprofilercallback8-interface"></a><span data-ttu-id="d8d82-102">Интерфейс ICorProfilerCallback8</span><span class="sxs-lookup"><span data-stu-id="d8d82-102">ICorProfilerCallback8 Interface</span></span>

<span data-ttu-id="d8d82-103">[Поддерживается в .NET Framework 4,7 и более поздних версиях]</span><span class="sxs-lookup"><span data-stu-id="d8d82-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  

 <span data-ttu-id="d8d82-104">Подкласс [ICorProfilerCallback7](icorprofilercallback7-interface.md) , предоставляющий методы обратного вызова, используемые средой CLR для уведомления профилировщика о начале и завершении JIT-компиляции динамического метода.</span><span class="sxs-lookup"><span data-stu-id="d8d82-104">A subclass of [ICorProfilerCallback7](icorprofilercallback7-interface.md) that provides callback methods used by the common language runtime to notify the profiler that JIT compilation of a dynamic method has started and finished.</span></span>
  
## <a name="methods"></a><span data-ttu-id="d8d82-105">Методы</span><span class="sxs-lookup"><span data-stu-id="d8d82-105">Methods</span></span>  
  
|<span data-ttu-id="d8d82-106">Метод</span><span class="sxs-lookup"><span data-stu-id="d8d82-106">Method</span></span>|<span data-ttu-id="d8d82-107">Описание</span><span class="sxs-lookup"><span data-stu-id="d8d82-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d8d82-108">Метод DynamicMethodJITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="d8d82-108">DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)|<span data-ttu-id="d8d82-109">Уведомляет профилировщик о запуске JIT-компиляции динамического метода.</span><span class="sxs-lookup"><span data-stu-id="d8d82-109">Notifies the profiler that JIT compilation of a dynamic method has started.</span></span>|  
|[<span data-ttu-id="d8d82-110">Метод DynamicMethodJITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="d8d82-110">DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)|<span data-ttu-id="d8d82-111">Уведомляет профилировщик о завершении JIT-компиляции динамического метода.</span><span class="sxs-lookup"><span data-stu-id="d8d82-111">Notifies the profiler that JIT compilation of a dynamic method has finished.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d8d82-112">Требования</span><span class="sxs-lookup"><span data-stu-id="d8d82-112">Requirements</span></span>  

 <span data-ttu-id="d8d82-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d8d82-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8d82-114">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d8d82-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
<span data-ttu-id="d8d82-115">**.NET Framework версии:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="d8d82-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="d8d82-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="d8d82-116">See also</span></span>

- [<span data-ttu-id="d8d82-117">Профилирующие интерфейсы</span><span class="sxs-lookup"><span data-stu-id="d8d82-117">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="d8d82-118">Интерфейс ICorProfilerCallback9</span><span class="sxs-lookup"><span data-stu-id="d8d82-118">ICorProfilerCallback9 Interface</span></span>](icorprofilercallback9-interface.md)
