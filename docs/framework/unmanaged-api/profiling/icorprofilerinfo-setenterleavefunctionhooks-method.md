---
title: Метод ICorProfilerInfo::SetEnterLeaveFunctionHooks
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.SetEnterLeaveFunctionHooks
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::SetEnterLeaveFunctionHooks
helpviewer_keywords:
- SetEnterLeaveFunctionHooks method [.NET Framework profiling]
- ICorProfilerInfo::SetEnterLeaveFunctionHooks method [.NET Framework profiling]
ms.assetid: 72399636-c219-4ffd-8ac8-39432c9d4641
topic_type:
- apiref
ms.openlocfilehash: cf0726a12b0274fd7a38e82b66c33430d26b031a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84497456"
---
# <a name="icorprofilerinfosetenterleavefunctionhooks-method"></a><span data-ttu-id="1f5ac-102">Метод ICorProfilerInfo::SetEnterLeaveFunctionHooks</span><span class="sxs-lookup"><span data-stu-id="1f5ac-102">ICorProfilerInfo::SetEnterLeaveFunctionHooks Method</span></span>
<span data-ttu-id="1f5ac-103">Задает реализованные профилировщиком функции, которые должны вызываться для обработчиков "Ввод", "Leave" и "таилкалл" управляемых функций.</span><span class="sxs-lookup"><span data-stu-id="1f5ac-103">Specifies profiler-implemented functions to be called on "enter", "leave", and "tailcall" hooks of managed functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f5ac-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1f5ac-104">Syntax</span></span>  
  
```cpp  
HRESULT SetEnterLeaveFunctionHooks(  
    [in] FunctionEnter    *pFuncEnter,  
    [in] FunctionLeave    *pFuncLeave,  
    [in] FunctionTailcall *pFuncTailcall);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1f5ac-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1f5ac-105">Parameters</span></span>  
 `pFuncEnter`  
 <span data-ttu-id="1f5ac-106">окне Указатель на реализацию, которая будет использоваться в качестве обратного вызова [FunctionEnter](functionenter-function.md) .</span><span class="sxs-lookup"><span data-stu-id="1f5ac-106">[in] A pointer to the implementation to be used as the [FunctionEnter](functionenter-function.md) callback.</span></span>  
  
 `pFuncLeave`  
 <span data-ttu-id="1f5ac-107">окне Указатель на реализацию, которая будет использоваться в качестве обратного вызова [FunctionLeave](functionleave-function.md) .</span><span class="sxs-lookup"><span data-stu-id="1f5ac-107">[in] A pointer to the implementation to be used as the [FunctionLeave](functionleave-function.md) callback.</span></span>  
  
 `pFuncTailcall`  
 <span data-ttu-id="1f5ac-108">окне Указатель на реализацию, которая будет использоваться в качестве обратного вызова [функтионтаилкалл](functiontailcall-function.md) .</span><span class="sxs-lookup"><span data-stu-id="1f5ac-108">[in] A pointer to the implementation to be used as the [FunctionTailcall](functiontailcall-function.md) callback.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1f5ac-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="1f5ac-109">Remarks</span></span>  
 <span data-ttu-id="1f5ac-110">В .NET Framework версии 1,0 каждый указатель функции может иметь значение null, чтобы отключить соответствующий обратный вызов.</span><span class="sxs-lookup"><span data-stu-id="1f5ac-110">In the .NET Framework version 1.0, each function pointer can be null to disable that corresponding callback.</span></span>  
  
 <span data-ttu-id="1f5ac-111">Одновременно может быть активным только один набор обратных вызовов.</span><span class="sxs-lookup"><span data-stu-id="1f5ac-111">Only one set of callbacks can be active at a time.</span></span> <span data-ttu-id="1f5ac-112">Таким образом, если профилировщик вызывает `SetEnterLeaveFunctionHooks` и [ICorProfilerInfo2:: SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md), то `SetEnterLeaveFunctionHooks2` имеет приоритет.</span><span class="sxs-lookup"><span data-stu-id="1f5ac-112">Thus, if a profiler calls both `SetEnterLeaveFunctionHooks` and [ICorProfilerInfo2::SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md), then `SetEnterLeaveFunctionHooks2` takes precedence.</span></span>  
  
 <span data-ttu-id="1f5ac-113">`SetEnterLeaveFunctionHooks`Метод может быть вызван только из обратного вызова [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md) профилировщика.</span><span class="sxs-lookup"><span data-stu-id="1f5ac-113">The `SetEnterLeaveFunctionHooks` method can be called only from the profiler's [ICorProfilerCallback::Initialize](icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1f5ac-114">Требования</span><span class="sxs-lookup"><span data-stu-id="1f5ac-114">Requirements</span></span>  
 <span data-ttu-id="1f5ac-115">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1f5ac-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1f5ac-116">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1f5ac-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1f5ac-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1f5ac-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1f5ac-118">**.NET Framework версии:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1f5ac-118">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f5ac-119">См. также</span><span class="sxs-lookup"><span data-stu-id="1f5ac-119">See also</span></span>

- [<span data-ttu-id="1f5ac-120">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="1f5ac-120">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
