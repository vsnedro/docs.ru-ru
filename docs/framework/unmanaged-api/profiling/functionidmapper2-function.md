---
title: Функция FunctionIDMapper2
ms.date: 03/30/2017
api_name:
- FunctionIDMapper2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionIDMapper2
helpviewer_keywords:
- FunctionIDMapper2 function [.NET Framework profiling]
ms.assetid: 466ad51b-8f0c-41d9-81f7-371aac3374cb
topic_type:
- apiref
ms.openlocfilehash: 65c5d2d4f288d927d79c233374edfec54c0b77ae
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500654"
---
# <a name="functionidmapper2-function"></a><span data-ttu-id="4f0e7-102">Функция FunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="4f0e7-102">FunctionIDMapper2 Function</span></span>
<span data-ttu-id="4f0e7-103">Уведомляет профилировщик о том, что заданный идентификатор функции может быть повторно сопоставлен с альтернативным ИДЕНТИФИКАТОРом для использования в ответных вызовах [FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md), [FunctionTailcall3](functiontailcall3-function.md)или[FunctionEnter3WithInfo](functionenter3withinfo-function.md), [FunctionLeave3WithInfo](functionleave3withinfo-function.md)и [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) для этой функции.</span><span class="sxs-lookup"><span data-stu-id="4f0e7-103">Notifies the profiler that the given identifier of a function may be remapped to an alternative ID to be used in the [FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md), and [FunctionTailcall3](functiontailcall3-function.md), or[FunctionEnter3WithInfo](functionenter3withinfo-function.md), [FunctionLeave3WithInfo](functionleave3withinfo-function.md), and [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) callbacks for that function.</span></span> <span data-ttu-id="4f0e7-104">`FunctionIDMapper2` также позволяет профилировщику указать, желает ли он получать обратные вызовы для этой функции.</span><span class="sxs-lookup"><span data-stu-id="4f0e7-104">`FunctionIDMapper2` also enables the profiler to indicate whether it wants to receive callbacks for that function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f0e7-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4f0e7-105">Syntax</span></span>  
  
```cpp  
UINT_PTR __stdcall FunctionIDMapper2 (  
    [in]  FunctionID  funcId,  
    [in]  void * clientData,  
    [out] BOOL       *pbHookFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4f0e7-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="4f0e7-106">Parameters</span></span>

- `funcId`

  <span data-ttu-id="4f0e7-107">\[in] идентификатор функции для повторного сопоставления.</span><span class="sxs-lookup"><span data-stu-id="4f0e7-107">\[in] The function identifier to be remapped.</span></span>

- `clientData`

  <span data-ttu-id="4f0e7-108">\[in] указатель на данные, которые используются для однозначного определения между средами выполнения.</span><span class="sxs-lookup"><span data-stu-id="4f0e7-108">\[in] A pointer to data that is used to disambiguate among runtimes.</span></span>

- `pbHookFunction`

  <span data-ttu-id="4f0e7-109">\[out] указатель на значение, которое задает профилировщик `true` , если он хочет получить `FunctionEnter3` `FunctionLeave3` обратные вызовы,, и, `FunctionTailcall3` или `FunctionEnter3WithInfo` , `FunctionLeave3WithInfo` и, `FunctionTailcall3WithInfo` в противном случае, присваивает этому значению значение `false` .</span><span class="sxs-lookup"><span data-stu-id="4f0e7-109">\[out] A pointer to a value that the profiler sets to `true` if it wants to receive `FunctionEnter3`, `FunctionLeave3`, and `FunctionTailcall3`, or `FunctionEnter3WithInfo`, `FunctionLeave3WithInfo`, and `FunctionTailcall3WithInfo` callbacks; otherwise, it sets this value to `false`.</span></span>

## <a name="return-value"></a><span data-ttu-id="4f0e7-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="4f0e7-110">Return Value</span></span>  
 <span data-ttu-id="4f0e7-111">Профилировщик возвращает значение, которое использует подсистема выполнения в качестве альтернативного идентификатора функции.</span><span class="sxs-lookup"><span data-stu-id="4f0e7-111">The profiler returns a value that the execution engine uses as an alternative function identifier.</span></span> <span data-ttu-id="4f0e7-112">Это возвращаемое значение не может быть значением null, если указатель `pbHookFunction` возвращает значение `false`.</span><span class="sxs-lookup"><span data-stu-id="4f0e7-112">The return value cannot be null unless `false` is returned in `pbHookFunction`.</span></span> <span data-ttu-id="4f0e7-113">В противном случае возвращаемое значение null приводит к непредсказуемым результатам, включая возможное прерывание процесса.</span><span class="sxs-lookup"><span data-stu-id="4f0e7-113">Otherwise, a null return value produces unpredictable results, including possibly halting the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4f0e7-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="4f0e7-114">Remarks</span></span>  
 <span data-ttu-id="4f0e7-115">Этот метод расширяет функцию [FunctionIDMapper](functionidmapper-function.md) с помощью дополнительного параметра, который используется для передачи данных клиента.</span><span class="sxs-lookup"><span data-stu-id="4f0e7-115">This method extends the [FunctionIDMapper](functionidmapper-function.md) function with an additional parameter that is used to pass client data.</span></span> <span data-ttu-id="4f0e7-116">Эти данные клиента служат для однозначного определения среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="4f0e7-116">The client data is used to disambiguate among runtimes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f0e7-117">Требования</span><span class="sxs-lookup"><span data-stu-id="4f0e7-117">Requirements</span></span>  
 <span data-ttu-id="4f0e7-118">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4f0e7-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f0e7-119">**Заголовок:** CorProf. idl</span><span class="sxs-lookup"><span data-stu-id="4f0e7-119">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="4f0e7-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4f0e7-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4f0e7-121">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f0e7-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f0e7-122">См. также</span><span class="sxs-lookup"><span data-stu-id="4f0e7-122">See also</span></span>

- [<span data-ttu-id="4f0e7-123">ICorProfilerInfo::SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="4f0e7-123">ICorProfilerInfo::SetFunctionIDMapper</span></span>](icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="4f0e7-124">ICorProfilerInfo3::SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="4f0e7-124">ICorProfilerInfo3::SetFunctionIDMapper2</span></span>](icorprofilerinfo3-setfunctionidmapper2-method.md)
- [<span data-ttu-id="4f0e7-125">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="4f0e7-125">FunctionEnter3</span></span>](functionenter3-function.md)
- [<span data-ttu-id="4f0e7-126">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="4f0e7-126">FunctionLeave3</span></span>](functionleave3-function.md)
- [<span data-ttu-id="4f0e7-127">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="4f0e7-127">FunctionTailcall3</span></span>](functiontailcall3-function.md)
- [<span data-ttu-id="4f0e7-128">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="4f0e7-128">FunctionEnter3WithInfo</span></span>](functionenter3withinfo-function.md)
- [<span data-ttu-id="4f0e7-129">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="4f0e7-129">FunctionLeave3WithInfo</span></span>](functionleave3withinfo-function.md)
- [<span data-ttu-id="4f0e7-130">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="4f0e7-130">FunctionTailcall3WithInfo</span></span>](functiontailcall3withinfo-function.md)
- [<span data-ttu-id="4f0e7-131">Глобальные статические функции профилирования</span><span class="sxs-lookup"><span data-stu-id="4f0e7-131">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
