---
title: Метод ICorProfilerCallback::UnmanagedToManagedTransition
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.UnmanagedToManagedTransition
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::UnmanagedToManagedTransition
helpviewer_keywords:
- ICorProfilerCallback::UnmanagedToManagedTransition method [.NET Framework profiling]
- UnmanagedToManagedTransition method [.NET Framework profiling]
ms.assetid: ade2cc01-9b81-4e09-a5f9-b3b9dda27e96
topic_type:
- apiref
ms.openlocfilehash: 8734fa9c9418b818cbe14ebe87ce2af6fa59c078
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499848"
---
# <a name="icorprofilercallbackunmanagedtomanagedtransition-method"></a><span data-ttu-id="96d36-102">Метод ICorProfilerCallback::UnmanagedToManagedTransition</span><span class="sxs-lookup"><span data-stu-id="96d36-102">ICorProfilerCallback::UnmanagedToManagedTransition Method</span></span>
<span data-ttu-id="96d36-103">Уведомляет профилировщик о том, что произошел переход из неуправляемого кода в управляемый код.</span><span class="sxs-lookup"><span data-stu-id="96d36-103">Notifies the profiler that a transition from unmanaged code to managed code has occurred.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96d36-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="96d36-104">Syntax</span></span>  
  
```cpp  
HRESULT UnmanagedToManagedTransition(  
    [in] FunctionID functionId,  
    [in] COR_PRF_TRANSITION_REASON reason);  
```  
  
## <a name="parameters"></a><span data-ttu-id="96d36-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="96d36-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="96d36-106">окне Идентификатор вызываемой функции.</span><span class="sxs-lookup"><span data-stu-id="96d36-106">[in] The ID of the function that is being called.</span></span>  
  
 `reason`  
 <span data-ttu-id="96d36-107">окне Значение перечисления [COR_PRF_TRANSITION_REASON](cor-prf-transition-reason-enumeration.md) , указывающее, произошло ли переход из-за вызова управляемого кода из неуправляемого кода или из-за возврата из неуправляемой функции, вызванной управляемой.</span><span class="sxs-lookup"><span data-stu-id="96d36-107">[in] A value of the [COR_PRF_TRANSITION_REASON](cor-prf-transition-reason-enumeration.md) enumeration that indicates whether the transition occurred because of a call into managed code from unmanaged code, or because of a return from an unmanaged function called by a managed one.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="96d36-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="96d36-108">Remarks</span></span>  
 <span data-ttu-id="96d36-109">Если значение `reason` равно COR_PRF_TRANSITION_RETURN и `functionId` не равно null, идентификатор функции является неуправляемой функцией и никогда не будет компилироваться с помощью JIT-компилятора.</span><span class="sxs-lookup"><span data-stu-id="96d36-109">If the value of `reason` is COR_PRF_TRANSITION_RETURN and `functionId` is not null, the function ID is that of the unmanaged function, and will never have been compiled using the just-in-time (JIT) compiler.</span></span> <span data-ttu-id="96d36-110">С неуправляемыми функциями связаны некоторые основные сведения, такие как имя и некоторые метаданные.</span><span class="sxs-lookup"><span data-stu-id="96d36-110">Unmanaged functions have some basic information associated with them, such as a name and some metadata.</span></span>  
  
 <span data-ttu-id="96d36-111">Если значение `reason` равно COR_PRF_TRANSITION_CALL, возможно, что вызванная функция (то есть управляемая функция) еще не скомпилирована с помощью JIT-компилятора.</span><span class="sxs-lookup"><span data-stu-id="96d36-111">If the value of `reason` is COR_PRF_TRANSITION_CALL, it may be possible that the called function (that is, the managed function) has not yet been JIT-compiled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="96d36-112">Требования</span><span class="sxs-lookup"><span data-stu-id="96d36-112">Requirements</span></span>  
 <span data-ttu-id="96d36-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="96d36-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="96d36-114">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="96d36-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="96d36-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="96d36-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="96d36-116">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96d36-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96d36-117">См. также</span><span class="sxs-lookup"><span data-stu-id="96d36-117">See also</span></span>

- [<span data-ttu-id="96d36-118">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="96d36-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="96d36-119">Метод ManagedToUnmanagedTransition</span><span class="sxs-lookup"><span data-stu-id="96d36-119">ManagedToUnmanagedTransition Method</span></span>](icorprofilercallback-managedtounmanagedtransition-method.md)
- [<span data-ttu-id="96d36-120">Использование явного вызова PInvoke в C++ (атрибут DllImport)</span><span class="sxs-lookup"><span data-stu-id="96d36-120">Using Explicit PInvoke in C++ (DllImport Attribute)</span></span>](/cpp/dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute)
- [<span data-ttu-id="96d36-121">Использование взаимодействия C++ (неявный PInvoke)</span><span class="sxs-lookup"><span data-stu-id="96d36-121">Using C++ Interop (Implicit PInvoke)</span></span>](/cpp/dotnet/using-cpp-interop-implicit-pinvoke)
