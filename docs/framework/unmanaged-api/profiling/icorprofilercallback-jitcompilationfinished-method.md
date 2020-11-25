---
title: Метод ICorProfilerCallback::JITCompilationFinished
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITCompilationFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITCompilationFinished
helpviewer_keywords:
- JITCompilationFinished method [.NET Framework profiling]
- ICorProfilerCallback::JITCompilationFinished method [.NET Framework profiling]
ms.assetid: 8dcd7537-d0c6-498c-8a56-2c060310ef65
topic_type:
- apiref
ms.openlocfilehash: 98e81d2d02a9495b678d49fb916f99068dd604f8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725538"
---
# <a name="icorprofilercallbackjitcompilationfinished-method"></a><span data-ttu-id="431b8-102">Метод ICorProfilerCallback::JITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="431b8-102">ICorProfilerCallback::JITCompilationFinished Method</span></span>

<span data-ttu-id="431b8-103">Уведомляет профилировщик о том, что JIT-компилятор завершил компиляцию функции.</span><span class="sxs-lookup"><span data-stu-id="431b8-103">Notifies the profiler that the just-in-time (JIT) compiler has finished compiling a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="431b8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="431b8-104">Syntax</span></span>  
  
```cpp  
HRESULT JITCompilationFinished(  
    [in] FunctionID functionId,  
    [in] HRESULT    hrStatus,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a><span data-ttu-id="431b8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="431b8-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="431b8-106">\[in] идентификатор скомпилированной функции.</span><span class="sxs-lookup"><span data-stu-id="431b8-106">\[in] The ID of the function that was compiled.</span></span>

- `hrStatus`

  <span data-ttu-id="431b8-107">\[в] значение, указывающее, успешно ли выполнена компиляция.</span><span class="sxs-lookup"><span data-stu-id="431b8-107">\[in] A value indicating whether compilation was successful.</span></span>

- `fIsSafeToBlock`

  <span data-ttu-id="431b8-108">\[в] значение, указывающее профилировщику, будет ли блокировка влиять на работу среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="431b8-108">\[in] A value indicating to the profiler whether blocking will affect the operation of the runtime.</span></span> <span data-ttu-id="431b8-109">Значение равно `true` , если блокировка может привести к тому, что среда выполнения будет ожидать возврата вызывающим потоком из этого обратного вызова; в противном случае — `false` .</span><span class="sxs-lookup"><span data-stu-id="431b8-109">The value is `true` if blocking may cause the runtime to wait for the calling thread to return from this callback; otherwise, `false`.</span></span>

  <span data-ttu-id="431b8-110">Хотя значение `true` не будет нанести вред среде выполнения, оно может наклонять результаты профилирования.</span><span class="sxs-lookup"><span data-stu-id="431b8-110">Although a value of `true` will not harm the runtime, it can skew the profiling results.</span></span>

## <a name="requirements"></a><span data-ttu-id="431b8-111">Требования</span><span class="sxs-lookup"><span data-stu-id="431b8-111">Requirements</span></span>  

 <span data-ttu-id="431b8-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="431b8-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="431b8-113">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="431b8-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="431b8-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="431b8-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="431b8-115">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="431b8-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="431b8-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="431b8-116">See also</span></span>

- [<span data-ttu-id="431b8-117">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="431b8-117">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="431b8-118">Метод JITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="431b8-118">JITCompilationStarted Method</span></span>](icorprofilercallback-jitcompilationstarted-method.md)
