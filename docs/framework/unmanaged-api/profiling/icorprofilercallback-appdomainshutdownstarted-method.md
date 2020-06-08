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
ms.openlocfilehash: 1b973cdeaffbec0dad1f2d082c44e8001647fdcc
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500459"
---
# <a name="icorprofilercallbackappdomainshutdownstarted-method"></a><span data-ttu-id="4bd57-102">Метод ICorProfilerCallback::AppDomainShutdownStarted</span><span class="sxs-lookup"><span data-stu-id="4bd57-102">ICorProfilerCallback::AppDomainShutdownStarted Method</span></span>
<span data-ttu-id="4bd57-103">Уведомляет профилировщик о том, что домен приложения выгружается из процесса.</span><span class="sxs-lookup"><span data-stu-id="4bd57-103">Notifies the profiler that an application domain is being unloaded from a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4bd57-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4bd57-104">Syntax</span></span>  
  
```cpp  
HRESULT AppDomainShutdownStarted(  
    [in] AppDomainID appDomainId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4bd57-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4bd57-105">Parameters</span></span>

- `appDomainId`

  <span data-ttu-id="4bd57-106">\[в] определяет домен, в котором хранятся сборки приложения.</span><span class="sxs-lookup"><span data-stu-id="4bd57-106">\[in] Identifies the domain in which the application's assemblies are stored.</span></span>

## <a name="remarks"></a><span data-ttu-id="4bd57-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="4bd57-107">Remarks</span></span>  
 <span data-ttu-id="4bd57-108">Значение недопустимо `appDomainId` для любого запроса информации после `AppDomainShutdownStarted` возврата метода — это последний шанс профилировщика получить сведения об этом домене приложения.</span><span class="sxs-lookup"><span data-stu-id="4bd57-108">The value of `appDomainId` is not valid for any information request after the `AppDomainShutdownStarted` method returns — this is the profiler's last chance to get information about this application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4bd57-109">Требования</span><span class="sxs-lookup"><span data-stu-id="4bd57-109">Requirements</span></span>  
 <span data-ttu-id="4bd57-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4bd57-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4bd57-111">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4bd57-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4bd57-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4bd57-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4bd57-113">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4bd57-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bd57-114">См. также</span><span class="sxs-lookup"><span data-stu-id="4bd57-114">See also</span></span>

- [<span data-ttu-id="4bd57-115">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="4bd57-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
