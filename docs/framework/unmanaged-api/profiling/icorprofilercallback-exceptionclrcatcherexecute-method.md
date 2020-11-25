---
title: Метод ICorProfilerCallback::ExceptionCLRCatcherExecute
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionCLRCatcherExecute
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionCLRCatcherExecute
helpviewer_keywords:
- ExceptionCLRCatcherExecute method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionCLRCatcherExecute method [.NET Framework profiling]
ms.assetid: aaac8f98-5cf4-42c7-b04b-556cce367e36
topic_type:
- apiref
ms.openlocfilehash: 1a9e377ba98c0c2302e341149bd5acb46c24051a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699993"
---
# <a name="icorprofilercallbackexceptionclrcatcherexecute-method"></a><span data-ttu-id="cd3f8-102">Метод ICorProfilerCallback::ExceptionCLRCatcherExecute</span><span class="sxs-lookup"><span data-stu-id="cd3f8-102">ICorProfilerCallback::ExceptionCLRCatcherExecute Method</span></span>

<span data-ttu-id="cd3f8-103">Вызывается, когда `catch` блок для исключения выполняется в самой среде CLR.</span><span class="sxs-lookup"><span data-stu-id="cd3f8-103">Called when a `catch` block for an exception is executed inside the common language runtime (CLR) itself.</span></span> <span data-ttu-id="cd3f8-104">Этот метод является устаревшим в .NET Framework версии 2,0.</span><span class="sxs-lookup"><span data-stu-id="cd3f8-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd3f8-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cd3f8-105">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionCLRCatcherExecute();  
```  
  
## <a name="requirements"></a><span data-ttu-id="cd3f8-106">Требования</span><span class="sxs-lookup"><span data-stu-id="cd3f8-106">Requirements</span></span>  

 <span data-ttu-id="cd3f8-107">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cd3f8-107">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd3f8-108">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="cd3f8-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="cd3f8-109">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cd3f8-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cd3f8-110">**.NET Framework версии:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="cd3f8-110">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd3f8-111">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="cd3f8-111">See also</span></span>

- [<span data-ttu-id="cd3f8-112">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="cd3f8-112">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="cd3f8-113">Метод ExceptionCLRCatcherFound</span><span class="sxs-lookup"><span data-stu-id="cd3f8-113">ExceptionCLRCatcherFound Method</span></span>](icorprofilercallback-exceptionclrcatcherfound-method.md)
