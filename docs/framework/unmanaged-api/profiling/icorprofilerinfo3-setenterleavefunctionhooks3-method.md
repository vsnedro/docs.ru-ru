---
title: Метод ICorProfilerInfo3::SetEnterLeaveFunctionHooks3
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.SetEnterLeaveFunctionHooks3 Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::SetEnterLeaveFunctionHooks3
helpviewer_keywords:
- SetEnterLeaveFunctionHooks3 method [.NET Framework profiling]
- ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 method [.NET Framework profiling]
ms.assetid: f0621465-b84f-40ab-a4e5-56a7abc776a7
topic_type:
- apiref
ms.openlocfilehash: eb658d682ce589b7dfdcfc0228d0c657310e6f7a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84496273"
---
# <a name="icorprofilerinfo3setenterleavefunctionhooks3-method"></a><span data-ttu-id="86903-102">Метод ICorProfilerInfo3::SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="86903-102">ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 Method</span></span>
<span data-ttu-id="86903-103">Задает реализованные профилировщиком функции, которые будут вызываться для функций [FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md)и [FunctionTailcall3](functiontailcall3-function.md) .</span><span class="sxs-lookup"><span data-stu-id="86903-103">Specifies the profiler-implemented functions that will be called on the [FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md), and [FunctionTailcall3](functiontailcall3-function.md) functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86903-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="86903-104">Syntax</span></span>  
  
```cpp  
HRESULT SetEnterLeaveFunctionHooks3(  
            [in] FunctionEnter3    *pFuncEnter3,  
            [in] FunctionLeave3    *pFuncLeave3,  
            [in] FunctionTailcall3 *pFuncTailcall3);  
```  
  
## <a name="parameters"></a><span data-ttu-id="86903-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="86903-105">Parameters</span></span>  
 `pFuncEnter3`  
 <span data-ttu-id="86903-106">окне Указатель на реализацию, которая будет использоваться в качестве `FunctionEnter3` обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="86903-106">[in] A pointer to the implementation to be used as the `FunctionEnter3` callback.</span></span>  
  
 `pFuncLeave3`  
 <span data-ttu-id="86903-107">окне Указатель на реализацию, которая будет использоваться в качестве `FunctionLeave3` обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="86903-107">[in] A pointer to the implementation to be used as the `FunctionLeave3` callback.</span></span>  
  
 `pFuncTailcall3`  
 <span data-ttu-id="86903-108">окне Указатель на реализацию, которая будет использоваться в качестве `FunctionTailcall3` обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="86903-108">[in] A pointer to the implementation to be used as the `FunctionTailcall3` callback.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="86903-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="86903-109">Remarks</span></span>  
 <span data-ttu-id="86903-110">Обработчики [FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md)и [FunctionTailcall3](functiontailcall3-function.md) не предоставляют кадры стека и проверку аргументов.</span><span class="sxs-lookup"><span data-stu-id="86903-110">[FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md), and [FunctionTailcall3](functiontailcall3-function.md) hooks do not provide stack frame and argument inspection.</span></span> <span data-ttu-id="86903-111">Для доступа к этим сведениям `COR_PRF_ENABLE_FUNCTION_ARGS` необходимо `COR_PRF_ENABLE_FUNCTION_RETVAL` задать флаги, и (или) `COR_PRF_ENABLE_FRAME_INFO` .</span><span class="sxs-lookup"><span data-stu-id="86903-111">To access that information, the `COR_PRF_ENABLE_FUNCTION_ARGS`, `COR_PRF_ENABLE_FUNCTION_RETVAL`, and/or  `COR_PRF_ENABLE_FRAME_INFO` flags have to be set.</span></span> <span data-ttu-id="86903-112">Профилировщик может использовать метод [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) для установки флагов событий, а затем использовать метод [ICorProfilerInfo3:: SetEnterLeaveFunctionHooks3WithInfo](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) для регистрации реализации этой функции.</span><span class="sxs-lookup"><span data-stu-id="86903-112">The profiler can use the [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md) method to set the event flags, and then use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) method to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="86903-113">В каждый момент времени активным может быть только один набор обратных вызовов, а последняя версия имеет приоритет.</span><span class="sxs-lookup"><span data-stu-id="86903-113">Only one set of callbacks may be active at a time, and the newest version takes precedence.</span></span> <span data-ttu-id="86903-114">Таким образом, если профилировщик вызывает [метод SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md) и `SetEnterLeaveFunctionHooks3` метод, `SetEnterLeaveFunctionHooks3` используется.</span><span class="sxs-lookup"><span data-stu-id="86903-114">Therefore, if a profiler calls both the [SetEnterLeaveFunctionHooks2 Method](icorprofilerinfo2-setenterleavefunctionhooks2-method.md) and the `SetEnterLeaveFunctionHooks3` method, `SetEnterLeaveFunctionHooks3` is used.</span></span>  
  
 <span data-ttu-id="86903-115">`SetEnterLeaveFunctionHooks3`Метод может быть вызван только из обратного вызова [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md) профилировщика.</span><span class="sxs-lookup"><span data-stu-id="86903-115">The `SetEnterLeaveFunctionHooks3` method may be called only from the profiler's [ICorProfilerCallback::Initialize](icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="86903-116">Требования</span><span class="sxs-lookup"><span data-stu-id="86903-116">Requirements</span></span>  
 <span data-ttu-id="86903-117">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="86903-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="86903-118">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="86903-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="86903-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="86903-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="86903-120">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="86903-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86903-121">См. также</span><span class="sxs-lookup"><span data-stu-id="86903-121">See also</span></span>

- [<span data-ttu-id="86903-122">SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="86903-122">SetEnterLeaveFunctionHooks3WithInfo</span></span>](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [<span data-ttu-id="86903-123">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="86903-123">FunctionEnter3</span></span>](functionenter3-function.md)
- [<span data-ttu-id="86903-124">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="86903-124">FunctionLeave3</span></span>](functionleave3-function.md)
- [<span data-ttu-id="86903-125">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="86903-125">FunctionTailcall3</span></span>](functiontailcall3-function.md)
- [<span data-ttu-id="86903-126">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="86903-126">FunctionEnter3WithInfo</span></span>](functionenter3withinfo-function.md)
- [<span data-ttu-id="86903-127">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="86903-127">FunctionLeave3WithInfo</span></span>](functionleave3withinfo-function.md)
- [<span data-ttu-id="86903-128">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="86903-128">FunctionTailcall3WithInfo</span></span>](functiontailcall3withinfo-function.md)
- [<span data-ttu-id="86903-129">Глобальные статические функции профилирования</span><span class="sxs-lookup"><span data-stu-id="86903-129">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
- [<span data-ttu-id="86903-130">ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="86903-130">ICorProfilerInfo3</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="86903-131">Профилирующие интерфейсы</span><span class="sxs-lookup"><span data-stu-id="86903-131">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="86903-132">Профилирование</span><span class="sxs-lookup"><span data-stu-id="86903-132">Profiling</span></span>](index.md)
