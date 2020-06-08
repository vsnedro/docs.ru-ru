---
title: Метод ICorProfilerCallback::ExceptionCatcherEnter
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionCatcherEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionCatcherEnter
helpviewer_keywords:
- ICorProfilerCallback::ExceptionCatcherEnter method [.NET Framework profiling]
- ExceptionCatcherEnter method [.NET Framework profiling]
ms.assetid: 41462329-a648-46f0-ae6d-728b94c31aa9
topic_type:
- apiref
ms.openlocfilehash: 9d0ef4da4ba6c8db49bcb0b40911756f7d9db66d
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500326"
---
# <a name="icorprofilercallbackexceptioncatcherenter-method"></a><span data-ttu-id="bbb2d-102">Метод ICorProfilerCallback::ExceptionCatcherEnter</span><span class="sxs-lookup"><span data-stu-id="bbb2d-102">ICorProfilerCallback::ExceptionCatcherEnter Method</span></span>
<span data-ttu-id="bbb2d-103">Уведомляет профилировщик о том, что управление передается соответствующему `catch` блоку.</span><span class="sxs-lookup"><span data-stu-id="bbb2d-103">Notifies the profiler that control is being passed to the appropriate `catch` block.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bbb2d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bbb2d-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionCatcherEnter(  
    [in] FunctionID functionId,  
    [in] ObjectID   objectId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bbb2d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="bbb2d-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="bbb2d-106">\[in] идентификатор функции, содержащей `catch` блок.</span><span class="sxs-lookup"><span data-stu-id="bbb2d-106">\[in] The identifier of the function containing the `catch` block.</span></span>
  
- `objectId`

  <span data-ttu-id="bbb2d-107">\[в] идентификатор обрабатываемого исключения.</span><span class="sxs-lookup"><span data-stu-id="bbb2d-107">\[in] The identifier of the exception being handled.</span></span>

## <a name="remarks"></a><span data-ttu-id="bbb2d-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="bbb2d-108">Remarks</span></span>  
 <span data-ttu-id="bbb2d-109">`ExceptionCatcherEnter`Метод вызывается только в том случае, если точка перехвата находится в коде, скомпилированном с JIT-компилятором.</span><span class="sxs-lookup"><span data-stu-id="bbb2d-109">The `ExceptionCatcherEnter` method is called only if the catch point is in code compiled with the just-in-time (JIT) compiler.</span></span> <span data-ttu-id="bbb2d-110">Исключение, перехваченное в неуправляемом коде или во внутреннем коде среды выполнения, не будет вызывать это уведомление.</span><span class="sxs-lookup"><span data-stu-id="bbb2d-110">An exception that is caught in unmanaged code or in the internal code of the runtime will not call this notification.</span></span> <span data-ttu-id="bbb2d-111">`objectId`Значение передается снова, так как сборка мусора могла переместить объект с момента получения `ExceptionThrown` уведомления.</span><span class="sxs-lookup"><span data-stu-id="bbb2d-111">The `objectId` value is passed again since a garbage collection could have moved the object since the `ExceptionThrown` notification.</span></span>  
  
 <span data-ttu-id="bbb2d-112">Профилировщик не должен блокировать реализацию этого метода, так как стек может не находиться в состоянии, допускающем сборку мусора, поэтому невозможно включить вытесненную сборку мусора.</span><span class="sxs-lookup"><span data-stu-id="bbb2d-112">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="bbb2d-113">Если профилировщик блокируется здесь и выполняется сборка мусора, среда выполнения блокируется до тех пор, пока этот обратный вызов не вернет значение.</span><span class="sxs-lookup"><span data-stu-id="bbb2d-113">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="bbb2d-114">Реализация этого метода профилировщиком не должна вызывать управляемый код или каким-либо образом приводит к выделению управляемой памяти.</span><span class="sxs-lookup"><span data-stu-id="bbb2d-114">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bbb2d-115">Требования</span><span class="sxs-lookup"><span data-stu-id="bbb2d-115">Requirements</span></span>  
 <span data-ttu-id="bbb2d-116">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bbb2d-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bbb2d-117">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bbb2d-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bbb2d-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bbb2d-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bbb2d-119">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bbb2d-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbb2d-120">См. также</span><span class="sxs-lookup"><span data-stu-id="bbb2d-120">See also</span></span>

- [<span data-ttu-id="bbb2d-121">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="bbb2d-121">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="bbb2d-122">Метод ExceptionCatcherLeave</span><span class="sxs-lookup"><span data-stu-id="bbb2d-122">ExceptionCatcherLeave Method</span></span>](icorprofilercallback-exceptioncatcherleave-method.md)
