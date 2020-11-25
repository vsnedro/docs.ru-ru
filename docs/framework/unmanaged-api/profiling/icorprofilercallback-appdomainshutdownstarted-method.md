---
title: Метод ICorProfilerCallback::AppDomainShutdownStarted
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AppDomainShutdownStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AppDomainShutdownStarted
helpviewer_keywords:
- AppDomainShutdownStarted method [.NET Framework profiling]
- ICorProfilerCallback::AppDomainShutdownStarted method [.NET Framework profiling]
ms.assetid: d23a3408-b525-4aec-a186-2ac7ca65d7a4
topic_type:
- apiref
ms.openlocfilehash: cb0b763059c787b8f3e93e6c46b0e7fb2f8f8b2c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718466"
---
# <a name="icorprofilercallbackappdomainshutdownstarted-method"></a><span data-ttu-id="a6e49-102">Метод ICorProfilerCallback::AppDomainShutdownStarted</span><span class="sxs-lookup"><span data-stu-id="a6e49-102">ICorProfilerCallback::AppDomainShutdownStarted Method</span></span>

<span data-ttu-id="a6e49-103">Уведомляет профилировщик о том, что домен приложения выгружается из процесса.</span><span class="sxs-lookup"><span data-stu-id="a6e49-103">Notifies the profiler that an application domain is being unloaded from a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6e49-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a6e49-104">Syntax</span></span>  
  
```cpp  
HRESULT AppDomainShutdownStarted(  
    [in] AppDomainID appDomainId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a6e49-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a6e49-105">Parameters</span></span>

- `appDomainId`

  <span data-ttu-id="a6e49-106">\[в] определяет домен, в котором хранятся сборки приложения.</span><span class="sxs-lookup"><span data-stu-id="a6e49-106">\[in] Identifies the domain in which the application's assemblies are stored.</span></span>

## <a name="remarks"></a><span data-ttu-id="a6e49-107">Комментарии</span><span class="sxs-lookup"><span data-stu-id="a6e49-107">Remarks</span></span>  

 <span data-ttu-id="a6e49-108">Значение недопустимо `appDomainId` для любого запроса информации после `AppDomainShutdownStarted` возврата метода — это последний шанс профилировщика получить сведения об этом домене приложения.</span><span class="sxs-lookup"><span data-stu-id="a6e49-108">The value of `appDomainId` is not valid for any information request after the `AppDomainShutdownStarted` method returns — this is the profiler's last chance to get information about this application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a6e49-109">Требования</span><span class="sxs-lookup"><span data-stu-id="a6e49-109">Requirements</span></span>  

 <span data-ttu-id="a6e49-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a6e49-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6e49-111">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a6e49-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a6e49-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a6e49-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a6e49-113">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6e49-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6e49-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="a6e49-114">See also</span></span>

- [<span data-ttu-id="a6e49-115">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="a6e49-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
