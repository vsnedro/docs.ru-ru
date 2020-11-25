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
ms.openlocfilehash: ef25d55defee2fdcfc7d744e481060eb7a7782ef
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699889"
---
# <a name="icorprofilercallbackexceptionsearchcatcherfound-method"></a><span data-ttu-id="19dc1-102">Метод ICorProfilerCallback::ExceptionSearchCatcherFound</span><span class="sxs-lookup"><span data-stu-id="19dc1-102">ICorProfilerCallback::ExceptionSearchCatcherFound Method</span></span>

<span data-ttu-id="19dc1-103">Уведомляет профилировщик о том, что на фазе поиска исключений обнаружен обработчик для созданного исключения.</span><span class="sxs-lookup"><span data-stu-id="19dc1-103">Notifies the profiler that the search phase of exception handling has located a handler for the exception that was thrown.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19dc1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="19dc1-104">Syntax</span></span>  
  
```cpp  
RESULT ExceptionSearchCatcherFound(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="19dc1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="19dc1-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="19dc1-106">\[in] идентификатор функции, которая содержит обработчик исключений.</span><span class="sxs-lookup"><span data-stu-id="19dc1-106">\[in] The ID of the function that contains the exception handler.</span></span>

## <a name="requirements"></a><span data-ttu-id="19dc1-107">Требования</span><span class="sxs-lookup"><span data-stu-id="19dc1-107">Requirements</span></span>  

 <span data-ttu-id="19dc1-108">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="19dc1-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19dc1-109">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="19dc1-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="19dc1-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="19dc1-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="19dc1-111">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19dc1-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19dc1-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="19dc1-112">See also</span></span>

- [<span data-ttu-id="19dc1-113">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="19dc1-113">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
