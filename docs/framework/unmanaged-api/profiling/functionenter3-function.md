---
title: Функция FunctionEnter3
ms.date: 03/30/2017
api_name:
- FunctionEnter3
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionEnter3
helpviewer_keywords:
- FunctionEnter3 function [.NET Framework profiling]
ms.assetid: ef782c53-dae7-4990-b4ad-fddb1e690d4e
topic_type:
- apiref
ms.openlocfilehash: b435e1a3504dd623421f977ffc48264f8b0dcb5a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500706"
---
# <a name="functionenter3-function"></a><span data-ttu-id="9b196-102">Функция FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="9b196-102">FunctionEnter3 Function</span></span>
<span data-ttu-id="9b196-103">Уведомляет профилировщик о передаче управления в функцию.</span><span class="sxs-lookup"><span data-stu-id="9b196-103">Notifies the profiler that control is being passed to a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b196-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9b196-104">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionEnter3(FunctionOrRemappedID functionOrRemappedID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9b196-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9b196-105">Parameters</span></span>

- `functionOrRemappedID`

  <span data-ttu-id="9b196-106">\[in] идентификатор функции, для которой передается элемент управления.</span><span class="sxs-lookup"><span data-stu-id="9b196-106">\[in] The identifier of the function to which control is passed.</span></span>

## <a name="remarks"></a><span data-ttu-id="9b196-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="9b196-107">Remarks</span></span>  
 <span data-ttu-id="9b196-108">`FunctionEnter3`Функция обратного вызова уведомляет профилировщик о вызове функций, но не поддерживает проверку аргументов.</span><span class="sxs-lookup"><span data-stu-id="9b196-108">The `FunctionEnter3` callback function notifies the profiler as functions are being called, but does not support argument inspection.</span></span> <span data-ttu-id="9b196-109">Чтобы зарегистрировать реализацию этой функции, используйте [метод ICorProfilerInfo3:: SetEnterLeaveFunctionHooks3](icorprofilerinfo3-setenterleavefunctionhooks3-method.md) .</span><span class="sxs-lookup"><span data-stu-id="9b196-109">Use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 method](icorprofilerinfo3-setenterleavefunctionhooks3-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="9b196-110">`FunctionEnter3`Функция является обратным вызовом. ее необходимо реализовать.</span><span class="sxs-lookup"><span data-stu-id="9b196-110">The `FunctionEnter3` function is a callback; you must implement it.</span></span> <span data-ttu-id="9b196-111">Реализация должна использовать `__declspec(naked)` атрибут класса хранения.</span><span class="sxs-lookup"><span data-stu-id="9b196-111">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="9b196-112">Подсистема выполнения не сохраняет никакие регистры перед вызовом этой функции.</span><span class="sxs-lookup"><span data-stu-id="9b196-112">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="9b196-113">Во время записи необходимо сохранить все используемые регистры, включая те, которые находятся в блоке с плавающей запятой (FPU).</span><span class="sxs-lookup"><span data-stu-id="9b196-113">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="9b196-114">При выходе необходимо восстановить стек, выключив все параметры, которые были переданы его вызывающим.</span><span class="sxs-lookup"><span data-stu-id="9b196-114">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b196-115">Требования</span><span class="sxs-lookup"><span data-stu-id="9b196-115">Requirements</span></span>  
 <span data-ttu-id="9b196-116">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9b196-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b196-117">**Заголовок:** CorProf. idl</span><span class="sxs-lookup"><span data-stu-id="9b196-117">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="9b196-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9b196-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9b196-119">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b196-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b196-120">См. также</span><span class="sxs-lookup"><span data-stu-id="9b196-120">See also</span></span>

- [<span data-ttu-id="9b196-121">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="9b196-121">FunctionLeave3</span></span>](functionleave3-function.md)
- [<span data-ttu-id="9b196-122">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="9b196-122">FunctionTailcall3</span></span>](functiontailcall3-function.md)
- [<span data-ttu-id="9b196-123">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="9b196-123">FunctionEnter3WithInfo</span></span>](functionenter3withinfo-function.md)
- [<span data-ttu-id="9b196-124">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="9b196-124">FunctionLeave3WithInfo</span></span>](functionleave3withinfo-function.md)
- [<span data-ttu-id="9b196-125">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="9b196-125">FunctionTailcall3WithInfo</span></span>](functiontailcall3withinfo-function.md)
- [<span data-ttu-id="9b196-126">SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="9b196-126">SetEnterLeaveFunctionHooks3</span></span>](icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [<span data-ttu-id="9b196-127">SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="9b196-127">SetEnterLeaveFunctionHooks3WithInfo</span></span>](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [<span data-ttu-id="9b196-128">SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="9b196-128">SetFunctionIDMapper</span></span>](icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="9b196-129">SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="9b196-129">SetFunctionIDMapper2</span></span>](icorprofilerinfo3-setfunctionidmapper2-method.md)
- [<span data-ttu-id="9b196-130">Глобальные статические функции профилирования</span><span class="sxs-lookup"><span data-stu-id="9b196-130">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
