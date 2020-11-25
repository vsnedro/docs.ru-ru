---
title: 'ICorProfilerCallback9: метод:D Инамикмесодунлоадед'
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback9.DynamicMethodUnloaded
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 0e6fe3430696c16405d4ae414436bb12882c08a5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732352"
---
# <a name="icorprofilercallback9dynamicmethodunloaded-method"></a><span data-ttu-id="0acf7-102">ICorProfilerCallback9: метод:D Инамикмесодунлоадед</span><span class="sxs-lookup"><span data-stu-id="0acf7-102">ICorProfilerCallback9::DynamicMethodUnloaded Method</span></span>

<span data-ttu-id="0acf7-103">[Поддерживается в .NET Framework 4.7.2 и более поздних версиях]</span><span class="sxs-lookup"><span data-stu-id="0acf7-103">[Supported in the .NET Framework 4.7.2 and later versions]</span></span>  
  
<span data-ttu-id="0acf7-104">Уведомляет профилировщик каждый раз, когда динамический метод уничтожается сборщиком мусора и затем выгружается.</span><span class="sxs-lookup"><span data-stu-id="0acf7-104">Notifies the profiler whenever a dynamic method is garbage collected and subsequently unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0acf7-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0acf7-105">Syntax</span></span>  
  
```cpp  
HRESULT DynamicMethodUnloaded(  
     [in]  FunctionID  functionId
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0acf7-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="0acf7-106">Parameters</span></span>  

<span data-ttu-id="0acf7-107">[in] `functionId`</span><span class="sxs-lookup"><span data-stu-id="0acf7-107">[in] `functionId`</span></span>  
<span data-ttu-id="0acf7-108">Идентификатор функции в памяти, которая была собрана и выгружена сборщиком мусора.</span><span class="sxs-lookup"><span data-stu-id="0acf7-108">The identifier of the in-memory function that has been garbage collected and unloaded.</span></span>

## <a name="requirements"></a><span data-ttu-id="0acf7-109">Требования</span><span class="sxs-lookup"><span data-stu-id="0acf7-109">Requirements</span></span>  

 <span data-ttu-id="0acf7-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0acf7-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0acf7-111">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0acf7-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0acf7-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0acf7-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0acf7-113">**.NET Framework версии:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="0acf7-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0acf7-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="0acf7-114">See also</span></span>

- [<span data-ttu-id="0acf7-115">ICorProfilerCallback8. Динамикмесоджиткомпилатионстартед, метод</span><span class="sxs-lookup"><span data-stu-id="0acf7-115">ICorProfilerCallback8.DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [<span data-ttu-id="0acf7-116">ICorProfilerCallback8. Динамикмесоджиткомпилатионфинишед, метод</span><span class="sxs-lookup"><span data-stu-id="0acf7-116">ICorProfilerCallback8.DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
- [<span data-ttu-id="0acf7-117">Интерфейс ICorProfilerCallback9</span><span class="sxs-lookup"><span data-stu-id="0acf7-117">ICorProfilerCallback9 Interface</span></span>](icorprofilercallback9-interface.md)
- [<span data-ttu-id="0acf7-118">COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS</span><span class="sxs-lookup"><span data-stu-id="0acf7-118">COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS</span></span>](cor-prf-high-monitor-enumeration.md)
