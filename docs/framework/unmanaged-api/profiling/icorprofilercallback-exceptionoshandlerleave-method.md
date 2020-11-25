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
ms.openlocfilehash: 37e3c9139a202e3cb31bd824d182389ae10b7389
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699941"
---
# <a name="icorprofilercallbackexceptionoshandlerleave-method"></a><span data-ttu-id="4fceb-102">Метод ICorProfilerCallback::ExceptionOSHandlerLeave</span><span class="sxs-lookup"><span data-stu-id="4fceb-102">ICorProfilerCallback::ExceptionOSHandlerLeave Method</span></span>

<span data-ttu-id="4fceb-103">Не реализован.</span><span class="sxs-lookup"><span data-stu-id="4fceb-103">Not implemented.</span></span> <span data-ttu-id="4fceb-104">Профилировщик, которому требуются сведения о неуправляемом исключении, должен получить эти сведения с помощью других средств.</span><span class="sxs-lookup"><span data-stu-id="4fceb-104">A profiler that needs unmanaged exception information must obtain this information through other means.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4fceb-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4fceb-105">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionOSHandlerLeave(  
    [in] UINT_PTR __unused);  
```  
  
## <a name="requirements"></a><span data-ttu-id="4fceb-106">Требования</span><span class="sxs-lookup"><span data-stu-id="4fceb-106">Requirements</span></span>  

 <span data-ttu-id="4fceb-107">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4fceb-107">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4fceb-108">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4fceb-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4fceb-109">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4fceb-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4fceb-110">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4fceb-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4fceb-111">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="4fceb-111">See also</span></span>

- [<span data-ttu-id="4fceb-112">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="4fceb-112">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
