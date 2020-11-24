---
title: Метод ICorProfilerInfo3::EnumJITedFunctions
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.EnumJITedFunctions Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::EnumJITedFunctions
helpviewer_keywords:
- ICorProfilerInfo3::EnumJITedFunctions method [.NET Framework profiling]
- EnumJITedFunctions method [.NET Framework profiling]
ms.assetid: e2847a36-f460-45e2-9b6c-b33b008f40d9
topic_type:
- apiref
ms.openlocfilehash: 6227baaead518eae2de5913369b72de1072ac052
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95681500"
---
# <a name="icorprofilerinfo3enumjitedfunctions-method"></a><span data-ttu-id="57e26-102">Метод ICorProfilerInfo3::EnumJITedFunctions</span><span class="sxs-lookup"><span data-stu-id="57e26-102">ICorProfilerInfo3::EnumJITedFunctions Method</span></span>

<span data-ttu-id="57e26-103">Возвращает перечислитель для всех функций, которые были ранее скомпилированы JIT-компилятором.</span><span class="sxs-lookup"><span data-stu-id="57e26-103">Returns an enumerator for all functions that were previously JIT-compiled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57e26-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="57e26-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumJITedFunctions([out] ICorProfilerFunctionEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="57e26-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="57e26-105">Parameters</span></span>  

 `ppEnum`  
 <span data-ttu-id="57e26-106">заполняет Указатель на перечислитель [ICorProfilerFunctionEnum](icorprofilerfunctionenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="57e26-106">[out] A pointer to the [ICorProfilerFunctionEnum](icorprofilerfunctionenum-interface.md) enumerator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="57e26-107">Комментарии</span><span class="sxs-lookup"><span data-stu-id="57e26-107">Remarks</span></span>  

 <span data-ttu-id="57e26-108">Этот метод может пересекаться с `JITCompilation` обратными вызовами, такими как метод [ICorProfilerCallback:: JITCompilationStarted](icorprofilercallback-jitcompilationstarted-method.md) .</span><span class="sxs-lookup"><span data-stu-id="57e26-108">This method may overlap with `JITCompilation` callbacks such as the [ICorProfilerCallback::JITCompilationStarted](icorprofilercallback-jitcompilationstarted-method.md) method.</span></span> <span data-ttu-id="57e26-109">Перечислитель, возвращаемый этим методом, не включает функции, загруженные из образов в машинном кодах, созданных с помощью Ngen.exe.</span><span class="sxs-lookup"><span data-stu-id="57e26-109">The enumerator returned by this method does not include functions that are loaded from native images generated with Ngen.exe.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="57e26-110">Возвращаемое перечисление содержит только значение "0" для значения `COR_PRF_FUNCTION::reJitId` поля.</span><span class="sxs-lookup"><span data-stu-id="57e26-110">The returned enumeration includes only "0" for the value of the `COR_PRF_FUNCTION::reJitId` field.</span></span>  <span data-ttu-id="57e26-111">Если требуются допустимые `COR_PRF_FUNCTION::reJitId` значения, используйте метод [метод icorprofilerinfo4:: EnumJITedFunctions2](icorprofilerinfo4-enumjitedfunctions2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="57e26-111">If you require valid `COR_PRF_FUNCTION::reJitId` values, use the [ICorProfilerInfo4::EnumJITedFunctions2](icorprofilerinfo4-enumjitedfunctions2-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="57e26-112">Требования</span><span class="sxs-lookup"><span data-stu-id="57e26-112">Requirements</span></span>  

 <span data-ttu-id="57e26-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="57e26-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="57e26-114">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="57e26-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="57e26-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="57e26-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="57e26-116">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="57e26-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57e26-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="57e26-117">See also</span></span>

- [<span data-ttu-id="57e26-118">Интерфейс ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="57e26-118">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="57e26-119">Профилирующие интерфейсы</span><span class="sxs-lookup"><span data-stu-id="57e26-119">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="57e26-120">Профилирование</span><span class="sxs-lookup"><span data-stu-id="57e26-120">Profiling</span></span>](index.md)
