---
title: Метод ICorProfilerCallback::JITFunctionPitched
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITFunctionPitched
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITFunctionPitched
helpviewer_keywords:
- JITFunctionPitched method [.NET Framework profiling]
- ICorProfilerCallback::JITFunctionPitched method [.NET Framework profiling]
ms.assetid: 116085df-7a77-404a-afac-d0557a12b986
topic_type:
- apiref
ms.openlocfilehash: 51fec26837b3c7f0a0328a7b64ff4a02148283da
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725519"
---
# <a name="icorprofilercallbackjitfunctionpitched-method"></a><span data-ttu-id="8856c-102">Метод ICorProfilerCallback::JITFunctionPitched</span><span class="sxs-lookup"><span data-stu-id="8856c-102">ICorProfilerCallback::JITFunctionPitched Method</span></span>

<span data-ttu-id="8856c-103">Оповещает профилировщик о том, что JIT-скомпилированная функция была удалена из памяти.</span><span class="sxs-lookup"><span data-stu-id="8856c-103">Notifies the profiler that a function that has been just-in-time (JIT)-compiled has been removed from memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8856c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8856c-104">Syntax</span></span>  
  
```cpp  
HRESULT JITFunctionPitched(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8856c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8856c-105">Parameters</span></span>  

 `functionId`  
 <span data-ttu-id="8856c-106">окне Идентификатор удаленной функции.</span><span class="sxs-lookup"><span data-stu-id="8856c-106">[in] The ID of the function that was removed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8856c-107">Комментарии</span><span class="sxs-lookup"><span data-stu-id="8856c-107">Remarks</span></span>  

 <span data-ttu-id="8856c-108">Если вызывается Удаленная функция, профилировщик получит новые события JIT-компиляции при повторной компиляции функции.</span><span class="sxs-lookup"><span data-stu-id="8856c-108">If the removed function is called, the profiler will receive new JIT-compilation events when the function is recompiled.</span></span> <span data-ttu-id="8856c-109">В настоящее время JIT-компилятор среды CLR не удаляет функции из памяти, поэтому этот обратный вызов сейчас не используется и не будет получен профилировщиком.</span><span class="sxs-lookup"><span data-stu-id="8856c-109">Currently, the common language runtime (CLR) JIT compiler does not remove functions from memory, so this callback is currently not used and will not be received by the profiler.</span></span>  
  
 <span data-ttu-id="8856c-110">Значение недопустимо `functionId` до повторной компиляции функции.</span><span class="sxs-lookup"><span data-stu-id="8856c-110">The value of `functionId` is not valid until the function is recompiled.</span></span> <span data-ttu-id="8856c-111">При повторной компиляции функции `functionId` будет использоваться то же значение.</span><span class="sxs-lookup"><span data-stu-id="8856c-111">When the function is recompiled, the same `functionId` value will be used.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8856c-112">Требования</span><span class="sxs-lookup"><span data-stu-id="8856c-112">Requirements</span></span>  

 <span data-ttu-id="8856c-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8856c-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8856c-114">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8856c-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8856c-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8856c-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8856c-116">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8856c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8856c-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="8856c-117">See also</span></span>

- [<span data-ttu-id="8856c-118">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="8856c-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
