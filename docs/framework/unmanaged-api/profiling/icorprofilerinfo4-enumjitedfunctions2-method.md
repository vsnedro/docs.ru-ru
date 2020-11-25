---
title: Метод ICorProfilerInfo4::EnumJITedFunctions2
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.EnumJITedFunctions2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::EnumJITedFunctions2
helpviewer_keywords:
- EnumJITedFunctions2 method, ICorProfilerInfo4 interface [.NET Framework profiling]
- ICorProfilerInfo4::EnumJITedFunctions2 method [.NET Framework profiling]
ms.assetid: 40e9a1be-9bd2-4fad-9921-34a84b61c1e3
topic_type:
- apiref
ms.openlocfilehash: 2a6ddaef7b64427f8349abedbbd85b4d82a0b88c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95697796"
---
# <a name="icorprofilerinfo4enumjitedfunctions2-method"></a><span data-ttu-id="3ff6d-102">Метод ICorProfilerInfo4::EnumJITedFunctions2</span><span class="sxs-lookup"><span data-stu-id="3ff6d-102">ICorProfilerInfo4::EnumJITedFunctions2 Method</span></span>

<span data-ttu-id="3ff6d-103">Возвращает перечислитель для всех функций, которые были ранее скомпилированы JIT-компилятором и повторно скомпилированы.</span><span class="sxs-lookup"><span data-stu-id="3ff6d-103">Returns an enumerator for all functions that were previously JIT-compiled and JIT-recompiled.</span></span> <span data-ttu-id="3ff6d-104">Этот метод заменяет метод [ICorProfilerInfo3:: EnumJITedFunctions](icorprofilerinfo3-enumjitedfunctions-method.md) , который не перечисляет идентификаторы, перекомпилированные с помощью JIT-компилятора.</span><span class="sxs-lookup"><span data-stu-id="3ff6d-104">This method replaces the [ICorProfilerInfo3::EnumJITedFunctions](icorprofilerinfo3-enumjitedfunctions-method.md) method, which does not enumerate JIT-recompiled IDs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ff6d-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3ff6d-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumJITedFunctions([out] ICorProfilerFunctionEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3ff6d-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="3ff6d-106">Parameters</span></span>  

 `ppEnum`  
 <span data-ttu-id="3ff6d-107">заполняет Указатель на перечислитель [ICorProfilerFunctionEnum](icorprofilerfunctionenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="3ff6d-107">[out] A pointer to the [ICorProfilerFunctionEnum](icorprofilerfunctionenum-interface.md) enumerator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3ff6d-108">Комментарии</span><span class="sxs-lookup"><span data-stu-id="3ff6d-108">Remarks</span></span>  

 <span data-ttu-id="3ff6d-109">Этот метод может пересекаться с `JITCompilation` обратными вызовами, такими как метод [ICorProfilerCallback:: JITCompilationStarted](icorprofilercallback-jitcompilationstarted-method.md) .</span><span class="sxs-lookup"><span data-stu-id="3ff6d-109">This method may overlap with `JITCompilation` callbacks such as the [ICorProfilerCallback::JITCompilationStarted](icorprofilercallback-jitcompilationstarted-method.md) method.</span></span> <span data-ttu-id="3ff6d-110">Возвращаемое перечисление содержит значения для `COR_PRF_FUNCTION::reJitId` поля.</span><span class="sxs-lookup"><span data-stu-id="3ff6d-110">The returned enumeration includes values for the `COR_PRF_FUNCTION::reJitId` field.</span></span> <span data-ttu-id="3ff6d-111">Метод [ICorProfilerInfo3:: EnumJITedFunctions](icorprofilerinfo3-enumjitedfunctions-method.md) , который заменяет этот метод, не перечисляет идентификаторы, перекомпилированные с помощью JIT-компилятора, поскольку `COR_PRF_FUNCTION::reJitId` поле всегда имеет значение 0.</span><span class="sxs-lookup"><span data-stu-id="3ff6d-111">The [ICorProfilerInfo3::EnumJITedFunctions](icorprofilerinfo3-enumjitedfunctions-method.md) method, which this method replaces, does not enumerate JIT-recompiled IDs, because the `COR_PRF_FUNCTION::reJitId` field is always set to 0.</span></span> <span data-ttu-id="3ff6d-112">`ICorProfilerInfo4::EnumJITedFunctions`Метод выполняет перечисление идентификаторов, перекомпилированных JIT-компилятором, так как `COR_PRF_FUNCTION::reJitId` поле задано правильно.</span><span class="sxs-lookup"><span data-stu-id="3ff6d-112">The `ICorProfilerInfo4::EnumJITedFunctions` method does enumerate JIT-recompiled IDs, because the `COR_PRF_FUNCTION::reJitId` field is set properly.</span></span> <span data-ttu-id="3ff6d-113">Обратите внимание, что метод [метод icorprofilerinfo4:: EnumJITedFunctions2](icorprofilerinfo4-enumjitedfunctions2-method.md) может запускать сборку мусора, в то время как [метод ICorProfilerInfo3:: EnumJITedFunctions](icorprofilerinfo3-enumjitedfunctions-method.md) не будет.</span><span class="sxs-lookup"><span data-stu-id="3ff6d-113">Note that the [ICorProfilerInfo4::EnumJITedFunctions2](icorprofilerinfo4-enumjitedfunctions2-method.md) method can trigger a garbage collection, whereas [ICorProfilerInfo3::EnumJITedFunctions method](icorprofilerinfo3-enumjitedfunctions-method.md) will not.</span></span>  <span data-ttu-id="3ff6d-114">Дополнительные сведения см. в разделе [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](corprof-e-unsupported-call-sequence-hresult.md).</span><span class="sxs-lookup"><span data-stu-id="3ff6d-114">For more information, see [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](corprof-e-unsupported-call-sequence-hresult.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ff6d-115">Требования</span><span class="sxs-lookup"><span data-stu-id="3ff6d-115">Requirements</span></span>  

 <span data-ttu-id="3ff6d-116">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3ff6d-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3ff6d-117">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3ff6d-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3ff6d-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3ff6d-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3ff6d-119">**.NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3ff6d-119">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ff6d-120">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="3ff6d-120">See also</span></span>

- [<span data-ttu-id="3ff6d-121">Метод EnumJITedFunctions</span><span class="sxs-lookup"><span data-stu-id="3ff6d-121">EnumJITedFunctions Method</span></span>](icorprofilerinfo3-enumjitedfunctions-method.md)
- [<span data-ttu-id="3ff6d-122">Интерфейс ICorProfilerInfo4</span><span class="sxs-lookup"><span data-stu-id="3ff6d-122">ICorProfilerInfo4 Interface</span></span>](icorprofilerinfo4-interface.md)
- [<span data-ttu-id="3ff6d-123">Профилирующие интерфейсы</span><span class="sxs-lookup"><span data-stu-id="3ff6d-123">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="3ff6d-124">Профилирование</span><span class="sxs-lookup"><span data-stu-id="3ff6d-124">Profiling</span></span>](index.md)
