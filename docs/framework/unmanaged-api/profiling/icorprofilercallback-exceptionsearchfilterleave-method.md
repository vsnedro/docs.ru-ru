---
title: Метод ICorProfilerCallback::ExceptionSearchFilterLeave
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionSearchFilterLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionSearchFilterLeave
helpviewer_keywords:
- ICorProfilerCallback::ExceptionSearchFilterLeave method [.NET Framework profiling]
- ExceptionSearchFilterLeave method [.NET Framework profiling]
ms.assetid: c28a2a82-dd11-4385-843f-b509fb61753b
topic_type:
- apiref
ms.openlocfilehash: fbece20701fbde5551e025b4f116f9873abf444d
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500212"
---
# <a name="icorprofilercallbackexceptionsearchfilterleave-method"></a><span data-ttu-id="79c73-102">Метод ICorProfilerCallback::ExceptionSearchFilterLeave</span><span class="sxs-lookup"><span data-stu-id="79c73-102">ICorProfilerCallback::ExceptionSearchFilterLeave Method</span></span>
<span data-ttu-id="79c73-103">Уведомляет профилировщик о завершении выполнения фильтра пользователем.</span><span class="sxs-lookup"><span data-stu-id="79c73-103">Notifies the profiler that a user filter has just finished executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79c73-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="79c73-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionSearchFilterLeave();  
```  
  
## <a name="requirements"></a><span data-ttu-id="79c73-105">Требования</span><span class="sxs-lookup"><span data-stu-id="79c73-105">Requirements</span></span>  
 <span data-ttu-id="79c73-106">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="79c73-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="79c73-107">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="79c73-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="79c73-108">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="79c73-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="79c73-109">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="79c73-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79c73-110">См. также</span><span class="sxs-lookup"><span data-stu-id="79c73-110">See also</span></span>

- [<span data-ttu-id="79c73-111">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="79c73-111">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="79c73-112">Метод ExceptionSearchFilterEnter</span><span class="sxs-lookup"><span data-stu-id="79c73-112">ExceptionSearchFilterEnter Method</span></span>](icorprofilercallback-exceptionsearchfilterenter-method.md)
