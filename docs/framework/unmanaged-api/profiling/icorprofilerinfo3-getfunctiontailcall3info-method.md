---
title: Метод ICorProfilerInfo3::GetFunctionTailcall3Info
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetFunctionTailcall3Info Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetFunctionTailcall3Info
helpviewer_keywords:
- ICorProfilerInfo3::GetFunctionTailcall3Info method [.NET Framework profiling]
- GetFunctionTailcall3Info method [.NET Framework profiling]
ms.assetid: afdb5ac9-5bf5-4b91-b7cb-f81db23d7da3
topic_type:
- apiref
ms.openlocfilehash: 27bbb1aac376866be7458a3737af9d89bf761411
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721619"
---
# <a name="icorprofilerinfo3getfunctiontailcall3info-method"></a><span data-ttu-id="24835-102">Метод ICorProfilerInfo3::GetFunctionTailcall3Info</span><span class="sxs-lookup"><span data-stu-id="24835-102">ICorProfilerInfo3::GetFunctionTailcall3Info Method</span></span>

<span data-ttu-id="24835-103">Предоставляет кадр стека функции, о которой сообщается профилировщику функцией [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) .</span><span class="sxs-lookup"><span data-stu-id="24835-103">Provides the stack frame of the function that is being reported to the profiler by the [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) function.</span></span> <span data-ttu-id="24835-104">Этот метод может быть вызван только во время обратного вызова `FunctionTailcall3WithInfo`.</span><span class="sxs-lookup"><span data-stu-id="24835-104">This method can be called only during the `FunctionTailcall3WithInfo` callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24835-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="24835-105">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionTailcall3Info(
            [in]  FunctionID functionId,
            [in]  COR_PRF_ELT_INFO eltInfo,  
            [out] COR_PRF_FRAME_INFO *pFrameInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="24835-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="24835-106">Parameters</span></span>  

 `functionId`  
 <span data-ttu-id="24835-107">окне Возвращаемое значение `FunctionID` функции.</span><span class="sxs-lookup"><span data-stu-id="24835-107">[in] The `FunctionID` of the function that is returning.</span></span>  
  
 `eltInfo`  
 <span data-ttu-id="24835-108">[in] Непрозрачный дескриптор, представляющий сведения об указанном кадре стека.</span><span class="sxs-lookup"><span data-stu-id="24835-108">[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="24835-109">Профилировщик должен предоставить `eltInfo` профилировщику тот же, который был передан `FunctionTailcall3WithInfo` функцией.</span><span class="sxs-lookup"><span data-stu-id="24835-109">The profiler should provide the same `eltInfo` that was given to the profiler by the `FunctionTailcall3WithInfo` function.</span></span>  
  
 `pFrameInfo`  
 <span data-ttu-id="24835-110">[out] Непрозрачный дескриптор, представляющий универсальные сведения об указанном кадре стека.</span><span class="sxs-lookup"><span data-stu-id="24835-110">[out] An opaque handle that represents generics information about a given stack frame.</span></span> <span data-ttu-id="24835-111">Этот дескриптор допустим только во время обратного вызова `FunctionTailcall3WithInfo`, в котором профилировщик вызывал метод `GetFunctionTailcall3Info`.</span><span class="sxs-lookup"><span data-stu-id="24835-111">This handle is valid only during the `FunctionTailcall3WithInfo` callback in which the profiler called the `GetFunctionTailcall3Info` method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="24835-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="24835-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="24835-113">Требования</span><span class="sxs-lookup"><span data-stu-id="24835-113">Requirements</span></span>  

 <span data-ttu-id="24835-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="24835-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24835-115">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="24835-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="24835-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="24835-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="24835-117">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="24835-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24835-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="24835-118">See also</span></span>

- [<span data-ttu-id="24835-119">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="24835-119">FunctionEnter3WithInfo</span></span>](functionenter3withinfo-function.md)
- [<span data-ttu-id="24835-120">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="24835-120">FunctionLeave3WithInfo</span></span>](functionleave3withinfo-function.md)
- [<span data-ttu-id="24835-121">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="24835-121">FunctionTailcall3WithInfo</span></span>](functiontailcall3withinfo-function.md)
- [<span data-ttu-id="24835-122">Интерфейс ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="24835-122">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="24835-123">Профилирующие интерфейсы</span><span class="sxs-lookup"><span data-stu-id="24835-123">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="24835-124">Профилирование</span><span class="sxs-lookup"><span data-stu-id="24835-124">Profiling</span></span>](index.md)
