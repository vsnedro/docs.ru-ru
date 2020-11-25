---
title: Метод ICorProfilerCallback::ExceptionSearchFilterEnter
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionSearchFilterEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionSearchFilterEnter
helpviewer_keywords:
- ExceptionSearchFilterEnter method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionSearchFilterEnter method [.NET Framework profiling]
ms.assetid: acc239ce-3eef-418c-b1df-c5a6dd8e8a4c
topic_type:
- apiref
ms.openlocfilehash: d58f2013e93eb1c7030d26ec60b0ab5ab08d0524
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699863"
---
# <a name="icorprofilercallbackexceptionsearchfilterenter-method"></a><span data-ttu-id="bf7bb-102">Метод ICorProfilerCallback::ExceptionSearchFilterEnter</span><span class="sxs-lookup"><span data-stu-id="bf7bb-102">ICorProfilerCallback::ExceptionSearchFilterEnter Method</span></span>

<span data-ttu-id="bf7bb-103">Уведомляет профилировщик о том, что фаза поиска обработки исключений начала выполнять пользовательский фильтр исключений.</span><span class="sxs-lookup"><span data-stu-id="bf7bb-103">Notifies the profiler that the search phase of exception handling has begun executing a user-defined exception filter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf7bb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bf7bb-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionSearchFilterEnter(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bf7bb-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="bf7bb-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="bf7bb-106">\[in] идентификатор функции, которая содержит фильтр.</span><span class="sxs-lookup"><span data-stu-id="bf7bb-106">\[in] The ID of the function that contains the filter.</span></span>

## <a name="requirements"></a><span data-ttu-id="bf7bb-107">Требования</span><span class="sxs-lookup"><span data-stu-id="bf7bb-107">Requirements</span></span>  

 <span data-ttu-id="bf7bb-108">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bf7bb-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf7bb-109">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bf7bb-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bf7bb-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bf7bb-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bf7bb-111">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf7bb-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf7bb-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="bf7bb-112">See also</span></span>

- [<span data-ttu-id="bf7bb-113">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="bf7bb-113">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="bf7bb-114">Метод ExceptionSearchFilterLeave</span><span class="sxs-lookup"><span data-stu-id="bf7bb-114">ExceptionSearchFilterLeave Method</span></span>](icorprofilercallback-exceptionsearchfilterleave-method.md)
