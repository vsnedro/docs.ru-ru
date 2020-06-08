---
title: Функция FunctionLeave2
ms.date: 03/30/2017
api_name:
- FunctionLeave2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionLeave2
helpviewer_keywords:
- FunctionLeave2 function [.NET Framework profiling]
ms.assetid: 8cdac941-8b94-4497-b874-4e571785f3fe
topic_type:
- apiref
ms.openlocfilehash: a2a3d58e0631fceab96c32f9d86fef25973fed84
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500667"
---
# <a name="functionleave2-function"></a><span data-ttu-id="664da-102">Функция FunctionLeave2</span><span class="sxs-lookup"><span data-stu-id="664da-102">FunctionLeave2 Function</span></span>
<span data-ttu-id="664da-103">Уведомляет профилировщик о том, что функция собирается вернуться к вызывающему объекту, и предоставляет сведения о кадре стека и возвращаемом значении функции.</span><span class="sxs-lookup"><span data-stu-id="664da-103">Notifies the profiler that a function is about to return to the caller and provides information about the stack frame and function return value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="664da-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="664da-104">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionLeave2 (  
    [in]  FunctionID                        funcId,  
    [in]  UINT_PTR                          clientData,  
    [in]  COR_PRF_FRAME_INFO                func,  
    [in]  COR_PRF_FUNCTION_ARGUMENT_RANGE  *retvalRange  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="664da-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="664da-105">Parameters</span></span>

- `funcId`

  <span data-ttu-id="664da-106">\[in] Идентификатор возвращаемой функции.</span><span class="sxs-lookup"><span data-stu-id="664da-106">\[in] The identifier of the function that is returning.</span></span>

- `clientData`

  <span data-ttu-id="664da-107">\[in] идентификатор повторно сопоставленной функции, который профилировщик ранее указал с помощью функции [FunctionIDMapper](functionidmapper-function.md) .</span><span class="sxs-lookup"><span data-stu-id="664da-107">\[in] The remapped function identifier, which the profiler previously specified via the [FunctionIDMapper](functionidmapper-function.md) function.</span></span>

- `func`

  <span data-ttu-id="664da-108">\[в] `COR_PRF_FRAME_INFO` значение, указывающее на сведения о кадре стека.</span><span class="sxs-lookup"><span data-stu-id="664da-108">\[in] A `COR_PRF_FRAME_INFO` value that points to information about the stack frame.</span></span>

  <span data-ttu-id="664da-109">Профилировщик должен рассматривать это как непрозрачный маркер, который можно передать обратно в подсистему выполнения метода [ICorProfilerInfo2:: GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="664da-109">The profiler should treat this as an opaque handle that can be passed back to the execution engine in the [ICorProfilerInfo2::GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) method.</span></span>  
  
- `retvalRange`

  <span data-ttu-id="664da-110">\[in] указатель на структуру [COR_PRF_FUNCTION_ARGUMENT_RANGE](cor-prf-function-argument-range-structure.md) , указывающую расположение в памяти возвращаемого значения функции.</span><span class="sxs-lookup"><span data-stu-id="664da-110">\[in] A pointer to a [COR_PRF_FUNCTION_ARGUMENT_RANGE](cor-prf-function-argument-range-structure.md) structure that specifies the memory location of the function's return value.</span></span>

  <span data-ttu-id="664da-111">Чтобы получить доступ к сведениям о возвращаемом значении, `COR_PRF_ENABLE_FUNCTION_RETVAL` необходимо установить флаг.</span><span class="sxs-lookup"><span data-stu-id="664da-111">In order to access return value information, the `COR_PRF_ENABLE_FUNCTION_RETVAL` flag must be set.</span></span> <span data-ttu-id="664da-112">Профилировщик может использовать метод [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) для установки флагов событий.</span><span class="sxs-lookup"><span data-stu-id="664da-112">The profiler can use the [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md) method to set the event flags.</span></span>

## <a name="remarks"></a><span data-ttu-id="664da-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="664da-113">Remarks</span></span>  
 <span data-ttu-id="664da-114">Значения `func` `retvalRange` параметров и недопустимы после `FunctionLeave2` возврата функции, так как значения могут измениться или быть уничтожены.</span><span class="sxs-lookup"><span data-stu-id="664da-114">The values of the `func` and `retvalRange` parameters are not valid after the `FunctionLeave2` function returns because the values may change or be destroyed.</span></span>  
  
 <span data-ttu-id="664da-115">`FunctionLeave2`Функция является обратным вызовом. ее необходимо реализовать.</span><span class="sxs-lookup"><span data-stu-id="664da-115">The `FunctionLeave2` function is a callback; you must implement it.</span></span> <span data-ttu-id="664da-116">Реализация должна использовать `__declspec` `naked` атрибут класса хранения ().</span><span class="sxs-lookup"><span data-stu-id="664da-116">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="664da-117">Подсистема выполнения не сохраняет никакие регистры перед вызовом этой функции.</span><span class="sxs-lookup"><span data-stu-id="664da-117">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="664da-118">Во время записи необходимо сохранить все используемые регистры, включая те, которые находятся в блоке с плавающей запятой (FPU).</span><span class="sxs-lookup"><span data-stu-id="664da-118">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="664da-119">При выходе необходимо восстановить стек, выключив все параметры, которые были переданы его вызывающим.</span><span class="sxs-lookup"><span data-stu-id="664da-119">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="664da-120">Реализация `FunctionLeave2` не должна блокироваться, так как она приведет к задержке сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="664da-120">The implementation of `FunctionLeave2` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="664da-121">Реализация не должна пытаться выполнить сборку мусора, так как стек может не находиться в состоянии, понятном для сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="664da-121">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="664da-122">Если выполняется сборка мусора, среда выполнения будет блокироваться до тех пор, пока не `FunctionLeave2` вернет.</span><span class="sxs-lookup"><span data-stu-id="664da-122">If a garbage collection is attempted, the runtime will block until `FunctionLeave2` returns.</span></span>  
  
 <span data-ttu-id="664da-123">Кроме того, `FunctionLeave2` функция не должна вызывать управляемый код или каким-либо образом приводит к выделению управляемой памяти.</span><span class="sxs-lookup"><span data-stu-id="664da-123">Also, the `FunctionLeave2` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="664da-124">Требования</span><span class="sxs-lookup"><span data-stu-id="664da-124">Requirements</span></span>  
 <span data-ttu-id="664da-125">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="664da-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="664da-126">**Заголовок:** CorProf. idl</span><span class="sxs-lookup"><span data-stu-id="664da-126">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="664da-127">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="664da-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="664da-128">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="664da-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="664da-129">См. также</span><span class="sxs-lookup"><span data-stu-id="664da-129">See also</span></span>

- [<span data-ttu-id="664da-130">Функция FunctionEnter2</span><span class="sxs-lookup"><span data-stu-id="664da-130">FunctionEnter2 Function</span></span>](functionenter2-function.md)
- [<span data-ttu-id="664da-131">Функция FunctionTailcall2</span><span class="sxs-lookup"><span data-stu-id="664da-131">FunctionTailcall2 Function</span></span>](functiontailcall2-function.md)
- [<span data-ttu-id="664da-132">Метод SetEnterLeaveFunctionHooks2</span><span class="sxs-lookup"><span data-stu-id="664da-132">SetEnterLeaveFunctionHooks2 Method</span></span>](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="664da-133">Глобальные статические функции профилирования</span><span class="sxs-lookup"><span data-stu-id="664da-133">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
