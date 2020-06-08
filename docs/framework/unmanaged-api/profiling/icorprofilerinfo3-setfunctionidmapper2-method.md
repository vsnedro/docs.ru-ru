---
title: Метод ICorProfilerInfo3::SetFunctionIDMapper2
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.SetFunctionIDMapper2 Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::SetFunctionIDMapper2
helpviewer_keywords:
- SetFunctionIDMapper2 method [.NET Framework profiling]
- ICorProfilerInfo3::SetFunctionIDMapper2 method [.NET Framework profiling]
ms.assetid: 8cdb1188-952a-4ba8-9f05-bfebc18cdd29
topic_type:
- apiref
ms.openlocfilehash: 723cb277a7df592e0494505018f7422e4e40f5f6
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84496156"
---
# <a name="icorprofilerinfo3setfunctionidmapper2-method"></a><span data-ttu-id="0f60d-102">Метод ICorProfilerInfo3::SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="0f60d-102">ICorProfilerInfo3::SetFunctionIDMapper2 Method</span></span>
<span data-ttu-id="0f60d-103">Задает реализуемую профилировщиком функцию, которая будет вызвана для сопоставления значений `FunctionID` с альтернативными значениями, передаваемыми обработчикам входа и выхода для функции профилировщика.</span><span class="sxs-lookup"><span data-stu-id="0f60d-103">Specifies the profiler-implemented function that will be called to map `FunctionID` values to alternative values, which are passed to the profiler's function entry/exit hooks.</span></span> <span data-ttu-id="0f60d-104">Этот метод расширяет метод [ICorProfilerInfo:: SetFunctionIDMapper](icorprofilerinfo-setfunctionidmapper-method.md) с дополнительным параметром данных, который профилировщики могут использовать для устранения неоднозначности между средами выполнения.</span><span class="sxs-lookup"><span data-stu-id="0f60d-104">This method extends the [ICorProfilerInfo::SetFunctionIDMapper](icorprofilerinfo-setfunctionidmapper-method.md) method with an additional data parameter, which profilers may use to disambiguate among runtimes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f60d-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0f60d-105">Syntax</span></span>  
  
```cpp  
HRESULT SetFunctionIDMapper2(  
       [in] FunctionIDMapper2 *pFunc,  
       [in] void *clientData);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0f60d-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="0f60d-106">Parameters</span></span>  
 `pFunc`  
 <span data-ttu-id="0f60d-107">окне Указатель на реализацию [FunctionIDMapper2](functionidmapper2-function.md) , которая будет вызываться для соответствия `FunctionID` значений их альтернативным значениям.</span><span class="sxs-lookup"><span data-stu-id="0f60d-107">[in] A pointer to a [FunctionIDMapper2](functionidmapper2-function.md) implementation that will be called to map the `FunctionID` values to their alternative values.</span></span>  
  
 `clientData`  
 <span data-ttu-id="0f60d-108">окне Указатель, который передается в каждый вызов функции [FunctionIDMapper2](functionidmapper2-function.md) , выполненной текущей средой выполнения.</span><span class="sxs-lookup"><span data-stu-id="0f60d-108">[in] A pointer that is passed to every [FunctionIDMapper2](functionidmapper2-function.md) function call made by the current runtime.</span></span> <span data-ttu-id="0f60d-109">Профилировщик может использовать эти сведения для устранения неоднозначности между средами выполнения.</span><span class="sxs-lookup"><span data-stu-id="0f60d-109">The profiler can use this information to disambiguate among runtimes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0f60d-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="0f60d-110">Return Value</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0f60d-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="0f60d-111">Remarks</span></span>  
 <span data-ttu-id="0f60d-112">Альтернативы значениям FunctionID будут переданы обработчикам входа и выхода функций профилировщика ([FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md)и [FunctionTailcall3](functiontailcall3-function.md); или [FunctionEnter3WithInfo](functionenter3withinfo-function.md), [FunctionLeave3WithInfo](functionleave3withinfo-function.md)и [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md)), которые указаны в методе [SetEnterLeaveFunctionHooks3](icorprofilerinfo3-setenterleavefunctionhooks3-method.md) или [SetEnterLeaveFunctionHooks3WithInfo](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) .</span><span class="sxs-lookup"><span data-stu-id="0f60d-112">The alternatives for the FunctionID values will be passed to the profiler's function entry/exit hooks ([FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md), and [FunctionTailcall3](functiontailcall3-function.md); or [FunctionEnter3WithInfo](functionenter3withinfo-function.md), [FunctionLeave3WithInfo](functionleave3withinfo-function.md), and [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md)) that are specified by the [SetEnterLeaveFunctionHooks3](icorprofilerinfo3-setenterleavefunctionhooks3-method.md) or [SetEnterLeaveFunctionHooks3WithInfo](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) method.</span></span>  
  
 <span data-ttu-id="0f60d-113">`FunctionIDMapper2`Метод можно задать только один раз. рекомендуется задать его в обратном вызове метода [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md) .</span><span class="sxs-lookup"><span data-stu-id="0f60d-113">The `FunctionIDMapper2` method can be set only once; we recommend that you set it in the [ICorProfilerCallback::Initialize](icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f60d-114">Требования</span><span class="sxs-lookup"><span data-stu-id="0f60d-114">Requirements</span></span>  
 <span data-ttu-id="0f60d-115">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0f60d-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f60d-116">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0f60d-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0f60d-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0f60d-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0f60d-118">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f60d-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f60d-119">См. также</span><span class="sxs-lookup"><span data-stu-id="0f60d-119">See also</span></span>

- [<span data-ttu-id="0f60d-120">SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="0f60d-120">SetFunctionIDMapper</span></span>](icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="0f60d-121">Интерфейс ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="0f60d-121">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="0f60d-122">Профилирующие интерфейсы</span><span class="sxs-lookup"><span data-stu-id="0f60d-122">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="0f60d-123">Профилирование</span><span class="sxs-lookup"><span data-stu-id="0f60d-123">Profiling</span></span>](index.md)
