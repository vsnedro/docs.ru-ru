---
title: Метод ICorProfilerCallback::ExceptionSearchFunctionEnter
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionSearchFunctionEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionSearchFunctionEnter
helpviewer_keywords:
- ExceptionSearchFunctionEnter method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionSearchFunctionEnter method [.NET Framework profiling]
ms.assetid: bfd54573-b7e6-4bd1-a184-7f08a8b39fae
topic_type:
- apiref
ms.openlocfilehash: 244227aadb50720514f7511be563089d520b4bf5
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500199"
---
# <a name="icorprofilercallbackexceptionsearchfunctionenter-method"></a><span data-ttu-id="ad8d8-102">Метод ICorProfilerCallback::ExceptionSearchFunctionEnter</span><span class="sxs-lookup"><span data-stu-id="ad8d8-102">ICorProfilerCallback::ExceptionSearchFunctionEnter Method</span></span>
<span data-ttu-id="ad8d8-103">Уведомляет профилировщик о том, что фаза поиска обработки исключений начала Поиск функции для поиска обработчика для текущего исключения.</span><span class="sxs-lookup"><span data-stu-id="ad8d8-103">Notifies the profiler that the search phase of exception handling has begun searching a function to find a handler for the current exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad8d8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ad8d8-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionSearchFunctionEnter(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ad8d8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ad8d8-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="ad8d8-106">\[in] идентификатор введенной функции.</span><span class="sxs-lookup"><span data-stu-id="ad8d8-106">\[in] The ID of the function that has been entered.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="ad8d8-107">Требования</span><span class="sxs-lookup"><span data-stu-id="ad8d8-107">Requirements</span></span>  
 <span data-ttu-id="ad8d8-108">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ad8d8-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad8d8-109">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ad8d8-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ad8d8-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ad8d8-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ad8d8-111">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad8d8-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad8d8-112">См. также</span><span class="sxs-lookup"><span data-stu-id="ad8d8-112">See also</span></span>

- [<span data-ttu-id="ad8d8-113">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="ad8d8-113">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="ad8d8-114">Метод ExceptionSearchFunctionLeave</span><span class="sxs-lookup"><span data-stu-id="ad8d8-114">ExceptionSearchFunctionLeave Method</span></span>](icorprofilercallback-exceptionsearchfunctionleave-method.md)
