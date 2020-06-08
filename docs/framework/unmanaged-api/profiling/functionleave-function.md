---
title: Функция FunctionLeave
ms.date: 03/30/2017
api_name:
- FunctionLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionLeave
helpviewer_keywords:
- FunctionLeave function [.NET Framework profiling]
ms.assetid: 18e89f45-e068-426a-be16-9f53a4346860
topic_type:
- apiref
ms.openlocfilehash: 836e4843ead940bc9f76ff6bdd0433e21e400afd
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500641"
---
# <a name="functionleave-function"></a><span data-ttu-id="05058-102">Функция FunctionLeave</span><span class="sxs-lookup"><span data-stu-id="05058-102">FunctionLeave Function</span></span>
<span data-ttu-id="05058-103">Уведомляет профилировщик о том, что функция собирается вернуть вызывающему объекту.</span><span class="sxs-lookup"><span data-stu-id="05058-103">Notifies the profiler that a function is about to return to the caller.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="05058-104">`FunctionLeave`Функция является устаревшей в .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="05058-104">The `FunctionLeave` function is deprecated in the .NET Framework 2.0.</span></span> <span data-ttu-id="05058-105">Он будет продолжать работать, но будет приводить к снижению производительности.</span><span class="sxs-lookup"><span data-stu-id="05058-105">It will continue to work, but will incur a performance penalty.</span></span> <span data-ttu-id="05058-106">Вместо этого используйте функцию [FunctionLeave2](functionleave2-function.md) .</span><span class="sxs-lookup"><span data-stu-id="05058-106">Use the [FunctionLeave2](functionleave2-function.md) function instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05058-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="05058-107">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionLeave (  
    [in] FunctionID funcID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="05058-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="05058-108">Parameters</span></span>

- `funcID`

  <span data-ttu-id="05058-109">\[in] Идентификатор возвращаемой функции.</span><span class="sxs-lookup"><span data-stu-id="05058-109">\[in] The identifier of the function that is returning.</span></span>

## <a name="remarks"></a><span data-ttu-id="05058-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="05058-110">Remarks</span></span>  
 <span data-ttu-id="05058-111">`FunctionLeave`Функция является обратным вызовом. ее необходимо реализовать.</span><span class="sxs-lookup"><span data-stu-id="05058-111">The `FunctionLeave` function is a callback; you must implement it.</span></span> <span data-ttu-id="05058-112">Реализация должна использовать `__declspec` `naked` атрибут класса хранения ().</span><span class="sxs-lookup"><span data-stu-id="05058-112">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="05058-113">Подсистема выполнения не сохраняет никакие регистры перед вызовом этой функции.</span><span class="sxs-lookup"><span data-stu-id="05058-113">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="05058-114">Во время записи необходимо сохранить все используемые регистры, включая те, которые находятся в блоке с плавающей запятой (FPU).</span><span class="sxs-lookup"><span data-stu-id="05058-114">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="05058-115">При выходе необходимо восстановить стек, выключив все параметры, которые были переданы его вызывающим.</span><span class="sxs-lookup"><span data-stu-id="05058-115">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="05058-116">Реализация `FunctionLeave` не должна блокироваться, так как она приведет к задержке сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="05058-116">The implementation of `FunctionLeave` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="05058-117">Реализация не должна пытаться выполнить сборку мусора, так как стек может не находиться в состоянии, понятном для сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="05058-117">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="05058-118">Если выполняется сборка мусора, среда выполнения будет блокироваться до тех пор, пока не `FunctionLeave` вернет.</span><span class="sxs-lookup"><span data-stu-id="05058-118">If a garbage collection is attempted, the runtime will block until `FunctionLeave` returns.</span></span>  
  
 <span data-ttu-id="05058-119">Кроме того, `FunctionLeave` функция не должна вызывать управляемый код или каким-либо образом приводит к выделению управляемой памяти.</span><span class="sxs-lookup"><span data-stu-id="05058-119">Also, the `FunctionLeave` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="05058-120">Требования</span><span class="sxs-lookup"><span data-stu-id="05058-120">Requirements</span></span>  
 <span data-ttu-id="05058-121">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="05058-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="05058-122">**Заголовок:** CorProf. idl</span><span class="sxs-lookup"><span data-stu-id="05058-122">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="05058-123">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="05058-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="05058-124">**.NET Framework версии:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="05058-124">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05058-125">См. также</span><span class="sxs-lookup"><span data-stu-id="05058-125">See also</span></span>

- [<span data-ttu-id="05058-126">Функция FunctionEnter2</span><span class="sxs-lookup"><span data-stu-id="05058-126">FunctionEnter2 Function</span></span>](functionenter2-function.md)
- [<span data-ttu-id="05058-127">Функция FunctionLeave2</span><span class="sxs-lookup"><span data-stu-id="05058-127">FunctionLeave2 Function</span></span>](functionleave2-function.md)
- [<span data-ttu-id="05058-128">Функция FunctionTailcall2</span><span class="sxs-lookup"><span data-stu-id="05058-128">FunctionTailcall2 Function</span></span>](functiontailcall2-function.md)
- [<span data-ttu-id="05058-129">Метод SetEnterLeaveFunctionHooks2</span><span class="sxs-lookup"><span data-stu-id="05058-129">SetEnterLeaveFunctionHooks2 Method</span></span>](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="05058-130">Глобальные статические функции профилирования</span><span class="sxs-lookup"><span data-stu-id="05058-130">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
