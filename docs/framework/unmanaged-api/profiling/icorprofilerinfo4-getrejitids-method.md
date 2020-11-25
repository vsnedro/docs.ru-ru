---
title: Метод ICorProfilerInfo4::GetReJITIDs
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.GetReJITIDs
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::GetReJITIDs
helpviewer_keywords:
- GetReJITIDs method, ICorProfilerInfo4 interface [.NET Framework profiling]
- ICorProfilerInfo4::GetReJITIDs method [.NET Framework profiling]
ms.assetid: 634ac28c-a5b7-4fc3-af84-256c24ca8177
topic_type:
- apiref
ms.openlocfilehash: 2ac645cbaaa45554568874653be016e4691bbd2f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707481"
---
# <a name="icorprofilerinfo4getrejitids-method"></a><span data-ttu-id="fb9f7-102">Метод ICorProfilerInfo4::GetReJITIDs</span><span class="sxs-lookup"><span data-stu-id="fb9f7-102">ICorProfilerInfo4::GetReJITIDs Method</span></span>

<span data-ttu-id="fb9f7-103">Возвращает массив идентификаторов, которые определяют все все повторно скомпилированные версии указанной функции, которые все еще выделены.</span><span class="sxs-lookup"><span data-stu-id="fb9f7-103">Returns an array of IDs that identify all JIT-recompiled versions of the specified function that are still allocated.</span></span> <span data-ttu-id="fb9f7-104">Сюда входят JIT-повторно скомпилированные версии функций, которые впоследствии были отменены, но еще не освобождены (например, если домен приложения, содержащий функцию, которая содержит возвращенные функции, все еще используется).</span><span class="sxs-lookup"><span data-stu-id="fb9f7-104">This includes JIT-recompiled versions of functions that have been subsequently reverted but not yet freed (for example, when the application domain that contains the reverted function is still in use).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb9f7-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fb9f7-105">Syntax</span></span>  
  
```cpp
HRESULT GetReJITIDs (  
     [in]  FunctionID          functionId,  
     [in]  ULONG               cReJitIds,  
     [out] ULONG *             pcReJitIds,  
     [out, size_is(cReJitIds), length_is(*pcReJitIds)]   ReJITID        reJitIds[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fb9f7-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="fb9f7-106">Parameters</span></span>  

 `functionId`  
 <span data-ttu-id="fb9f7-107">окне Объект `FunctionID` экземпляра функции, для которого требуется перечислить версии.</span><span class="sxs-lookup"><span data-stu-id="fb9f7-107">[in] The `FunctionID` of the function instance for which to enumerate versions.</span></span>  
  
 `cReJitIds`  
 <span data-ttu-id="fb9f7-108">окне Число идентификаторов, перекомпилированных с помощью JIT-компилятора, выделенных в `reJitIds` массиве.</span><span class="sxs-lookup"><span data-stu-id="fb9f7-108">[in] The number of JIT-recompiled IDs allocated in the `reJitIds` array.</span></span>  
  
 `pcReJitIds`  
 <span data-ttu-id="fb9f7-109">заполняет Фактическое число повторно скомпилированных идентификаторов с JIT-рекомпиляцией.</span><span class="sxs-lookup"><span data-stu-id="fb9f7-109">[out] The actual number of JIT-recompiled IDs.</span></span>  
  
 `reJitIds`  
 <span data-ttu-id="fb9f7-110">заполняет Выделенный вызывающим объектом массив, который будет содержать JIT-перекомпилированные идентификаторы для указанной функции.</span><span class="sxs-lookup"><span data-stu-id="fb9f7-110">[out] A caller-allocated array that will contain the JIT-recompiled IDs for the specified function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fb9f7-111">Комментарии</span><span class="sxs-lookup"><span data-stu-id="fb9f7-111">Remarks</span></span>  

 <span data-ttu-id="fb9f7-112">`GetReJITIDs` Перечисляет активные JIT-повторно скомпилированные идентификаторы для заданного экземпляра функции.</span><span class="sxs-lookup"><span data-stu-id="fb9f7-112">`GetReJITIDs` enumerates the active JIT-recompiled IDs for a given function instance.</span></span> <span data-ttu-id="fb9f7-113">Он следует той же схеме использования, что и другие `ICorProfilerInfo` функции, принимающие буферы, выделенные вызывающим объектом.</span><span class="sxs-lookup"><span data-stu-id="fb9f7-113">It follows the same usage pattern as other `ICorProfilerInfo` functions that accept caller-allocated buffers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb9f7-114">Требования</span><span class="sxs-lookup"><span data-stu-id="fb9f7-114">Requirements</span></span>  

 <span data-ttu-id="fb9f7-115">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fb9f7-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb9f7-116">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fb9f7-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="fb9f7-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fb9f7-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fb9f7-118">**.NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fb9f7-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb9f7-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="fb9f7-119">See also</span></span>

- [<span data-ttu-id="fb9f7-120">Интерфейс ICorProfilerInfo4</span><span class="sxs-lookup"><span data-stu-id="fb9f7-120">ICorProfilerInfo4 Interface</span></span>](icorprofilerinfo4-interface.md)
- [<span data-ttu-id="fb9f7-121">Профилирующие интерфейсы</span><span class="sxs-lookup"><span data-stu-id="fb9f7-121">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="fb9f7-122">Профилирование</span><span class="sxs-lookup"><span data-stu-id="fb9f7-122">Profiling</span></span>](index.md)
