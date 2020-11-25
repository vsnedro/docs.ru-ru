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
ms.openlocfilehash: 273c3cefa2e67a7d8c429982b4da4126168b2830
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699967"
---
# <a name="icorprofilercallbackexceptionoshandlerenter-method"></a><span data-ttu-id="49312-102">Метод ICorProfilerCallback::ExceptionOSHandlerEnter</span><span class="sxs-lookup"><span data-stu-id="49312-102">ICorProfilerCallback::ExceptionOSHandlerEnter Method</span></span>

<span data-ttu-id="49312-103">Не реализован.</span><span class="sxs-lookup"><span data-stu-id="49312-103">Not implemented.</span></span> <span data-ttu-id="49312-104">Профилировщик, которому требуются сведения о неуправляемом исключении, должен получить эти сведения с помощью других средств.</span><span class="sxs-lookup"><span data-stu-id="49312-104">A profiler that needs unmanaged exception information must obtain this information through other means.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49312-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="49312-105">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionOSHandlerEnter(  
    [in] UINT_PTR __unused);  
```  
  
## <a name="requirements"></a><span data-ttu-id="49312-106">Требования</span><span class="sxs-lookup"><span data-stu-id="49312-106">Requirements</span></span>  

 <span data-ttu-id="49312-107">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="49312-107">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49312-108">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="49312-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="49312-109">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="49312-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="49312-110">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49312-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49312-111">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="49312-111">See also</span></span>

- [<span data-ttu-id="49312-112">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="49312-112">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
