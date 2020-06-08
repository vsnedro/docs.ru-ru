---
title: Метод ICorProfilerCallback::ExceptionSearchCatcherFound
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionSearchCatcherFound
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionSearchCatcherFound
helpviewer_keywords:
- ExceptionSearchCatcherFound method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionSearchCatcherFound method [.NET Framework profiling]
ms.assetid: 190f424d-5e37-4163-a191-0895686e9476
topic_type:
- apiref
ms.openlocfilehash: 70c03d34bdf9bd315994b2bfa09631efac2565ef
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500225"
---
# <a name="icorprofilercallbackexceptionsearchcatcherfound-method"></a><span data-ttu-id="248c4-102">Метод ICorProfilerCallback::ExceptionSearchCatcherFound</span><span class="sxs-lookup"><span data-stu-id="248c4-102">ICorProfilerCallback::ExceptionSearchCatcherFound Method</span></span>
<span data-ttu-id="248c4-103">Уведомляет профилировщик о том, что на фазе поиска исключений обнаружен обработчик для созданного исключения.</span><span class="sxs-lookup"><span data-stu-id="248c4-103">Notifies the profiler that the search phase of exception handling has located a handler for the exception that was thrown.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="248c4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="248c4-104">Syntax</span></span>  
  
```cpp  
RESULT ExceptionSearchCatcherFound(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="248c4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="248c4-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="248c4-106">\[in] идентификатор функции, которая содержит обработчик исключений.</span><span class="sxs-lookup"><span data-stu-id="248c4-106">\[in] The ID of the function that contains the exception handler.</span></span>

## <a name="requirements"></a><span data-ttu-id="248c4-107">Требования</span><span class="sxs-lookup"><span data-stu-id="248c4-107">Requirements</span></span>  
 <span data-ttu-id="248c4-108">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="248c4-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="248c4-109">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="248c4-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="248c4-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="248c4-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="248c4-111">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="248c4-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="248c4-112">См. также</span><span class="sxs-lookup"><span data-stu-id="248c4-112">See also</span></span>

- [<span data-ttu-id="248c4-113">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="248c4-113">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
