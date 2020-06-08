---
title: Метод ICorProfilerCallback::ExceptionOSHandlerLeave
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionOSHandlerLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionOSHandlerLeave
helpviewer_keywords:
- ExceptionOSHandlerLeave method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionOSHandlerLeave method [.NET Framework profiling]
ms.assetid: 4d164676-0ee9-4f67-a8ea-cb474db09053
topic_type:
- apiref
ms.openlocfilehash: 5ba45cf526a6ebca6975a75d06308d089770ad5b
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500277"
---
# <a name="icorprofilercallbackexceptionoshandlerleave-method"></a><span data-ttu-id="46838-102">Метод ICorProfilerCallback::ExceptionOSHandlerLeave</span><span class="sxs-lookup"><span data-stu-id="46838-102">ICorProfilerCallback::ExceptionOSHandlerLeave Method</span></span>
<span data-ttu-id="46838-103">Не реализовано.</span><span class="sxs-lookup"><span data-stu-id="46838-103">Not implemented.</span></span> <span data-ttu-id="46838-104">Профилировщик, которому требуются сведения о неуправляемом исключении, должен получить эти сведения с помощью других средств.</span><span class="sxs-lookup"><span data-stu-id="46838-104">A profiler that needs unmanaged exception information must obtain this information through other means.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46838-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="46838-105">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionOSHandlerLeave(  
    [in] UINT_PTR __unused);  
```  
  
## <a name="requirements"></a><span data-ttu-id="46838-106">Требования</span><span class="sxs-lookup"><span data-stu-id="46838-106">Requirements</span></span>  
 <span data-ttu-id="46838-107">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="46838-107">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46838-108">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="46838-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="46838-109">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="46838-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="46838-110">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="46838-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46838-111">См. также</span><span class="sxs-lookup"><span data-stu-id="46838-111">See also</span></span>

- [<span data-ttu-id="46838-112">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="46838-112">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
