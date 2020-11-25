---
title: Метод ICorProfilerCallback::ExceptionSearchFunctionLeave
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionSearchFunctionLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionSearchFunctionLeave
helpviewer_keywords:
- ExceptionSearchFunctionLeave method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionSearchFunctionLeave method [.NET Framework profiling]
ms.assetid: 01de7ac6-0aad-42ef-bf93-50737667b0a4
topic_type:
- apiref
ms.openlocfilehash: 064f87fe0cee8d0ad7efcba478e9cf1954a3f291
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699772"
---
# <a name="icorprofilercallbackexceptionsearchfunctionleave-method"></a><span data-ttu-id="3a11a-102">Метод ICorProfilerCallback::ExceptionSearchFunctionLeave</span><span class="sxs-lookup"><span data-stu-id="3a11a-102">ICorProfilerCallback::ExceptionSearchFunctionLeave Method</span></span>

<span data-ttu-id="3a11a-103">Уведомляет профилировщик о завершении фазы поиска обработки исключений при поиске функции.</span><span class="sxs-lookup"><span data-stu-id="3a11a-103">Notifies the profiler that the search phase of exception handling has finished searching a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a11a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3a11a-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionSearchFunctionLeave();  
```  
  
## <a name="requirements"></a><span data-ttu-id="3a11a-105">Требования</span><span class="sxs-lookup"><span data-stu-id="3a11a-105">Requirements</span></span>  

 <span data-ttu-id="3a11a-106">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3a11a-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a11a-107">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3a11a-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3a11a-108">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3a11a-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3a11a-109">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a11a-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a11a-110">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="3a11a-110">See also</span></span>

- [<span data-ttu-id="3a11a-111">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="3a11a-111">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="3a11a-112">Метод ExceptionSearchFunctionEnter</span><span class="sxs-lookup"><span data-stu-id="3a11a-112">ExceptionSearchFunctionEnter Method</span></span>](icorprofilercallback-exceptionsearchfunctionenter-method.md)
