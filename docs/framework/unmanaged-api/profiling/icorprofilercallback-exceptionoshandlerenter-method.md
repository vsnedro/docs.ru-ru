---
title: Метод ICorProfilerCallback::ExceptionOSHandlerEnter
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionOSHandlerEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionOSHandlerEnter
helpviewer_keywords:
- ExceptionOSHandlerEnter method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionOSHandlerEnter method [.NET Framework profiling]
ms.assetid: 09238b9b-9359-4780-89dc-2f5e4f57920e
topic_type:
- apiref
ms.openlocfilehash: c2c9ed848984d36ddf10d32d120deda76a4d47cc
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500290"
---
# <a name="icorprofilercallbackexceptionoshandlerenter-method"></a><span data-ttu-id="4b486-102">Метод ICorProfilerCallback::ExceptionOSHandlerEnter</span><span class="sxs-lookup"><span data-stu-id="4b486-102">ICorProfilerCallback::ExceptionOSHandlerEnter Method</span></span>
<span data-ttu-id="4b486-103">Не реализовано.</span><span class="sxs-lookup"><span data-stu-id="4b486-103">Not implemented.</span></span> <span data-ttu-id="4b486-104">Профилировщик, которому требуются сведения о неуправляемом исключении, должен получить эти сведения с помощью других средств.</span><span class="sxs-lookup"><span data-stu-id="4b486-104">A profiler that needs unmanaged exception information must obtain this information through other means.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b486-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4b486-105">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionOSHandlerEnter(  
    [in] UINT_PTR __unused);  
```  
  
## <a name="requirements"></a><span data-ttu-id="4b486-106">Требования</span><span class="sxs-lookup"><span data-stu-id="4b486-106">Requirements</span></span>  
 <span data-ttu-id="4b486-107">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4b486-107">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b486-108">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4b486-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4b486-109">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4b486-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4b486-110">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4b486-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b486-111">См. также</span><span class="sxs-lookup"><span data-stu-id="4b486-111">See also</span></span>

- [<span data-ttu-id="4b486-112">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="4b486-112">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
