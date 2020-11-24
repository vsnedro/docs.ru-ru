---
title: Метод IHostManualEvent::Reset
ms.date: 03/30/2017
api_name:
- IHostManualEvent.Reset
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostManualEvent::Reset
helpviewer_keywords:
- Reset method, IHostManualEvent interface [.NET Framework hosting]
- IHostManualEvent::Reset method [.NET Framework hosting]
ms.assetid: 0d101168-b5e3-49ce-90c7-85cf2db83c4c
topic_type:
- apiref
ms.openlocfilehash: 5653f874ef7a681f6667b3508b82ac493234cc4e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673154"
---
# <a name="ihostmanualeventreset-method"></a><span data-ttu-id="8595b-102">Метод IHostManualEvent::Reset</span><span class="sxs-lookup"><span data-stu-id="8595b-102">IHostManualEvent::Reset Method</span></span>

<span data-ttu-id="8595b-103">Сбрасывает текущий экземпляр [ихостмануалевент](ihostmanualevent-interface.md) в несигнальное состояние.</span><span class="sxs-lookup"><span data-stu-id="8595b-103">Resets the current [IHostManualEvent](ihostmanualevent-interface.md) instance to a non-signaled state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8595b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8595b-104">Syntax</span></span>  
  
```cpp  
HRESULT Reset ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="8595b-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="8595b-105">Return Value</span></span>  
  
|<span data-ttu-id="8595b-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8595b-106">HRESULT</span></span>|<span data-ttu-id="8595b-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="8595b-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8595b-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="8595b-108">S_OK</span></span>|<span data-ttu-id="8595b-109">`Reset` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="8595b-109">`Reset` returned successfully.</span></span>|  
|<span data-ttu-id="8595b-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8595b-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8595b-111">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="8595b-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8595b-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8595b-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8595b-113">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="8595b-113">The call timed out.</span></span>|  
|<span data-ttu-id="8595b-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8595b-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8595b-115">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="8595b-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8595b-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8595b-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8595b-117">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="8595b-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8595b-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8595b-118">E_FAIL</span></span>|<span data-ttu-id="8595b-119">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="8595b-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8595b-120">Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="8595b-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8595b-121">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="8595b-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8595b-122">Требования</span><span class="sxs-lookup"><span data-stu-id="8595b-122">Requirements</span></span>  

 <span data-ttu-id="8595b-123">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8595b-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8595b-124">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="8595b-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8595b-125">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8595b-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8595b-126">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8595b-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8595b-127">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="8595b-127">See also</span></span>

- [<span data-ttu-id="8595b-128">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="8595b-128">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="8595b-129">Интерфейс IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="8595b-129">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="8595b-130">Интерфейс IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="8595b-130">IHostManualEvent Interface</span></span>](ihostmanualevent-interface.md)
- [<span data-ttu-id="8595b-131">Интерфейс IHostSemaphore</span><span class="sxs-lookup"><span data-stu-id="8595b-131">IHostSemaphore Interface</span></span>](ihostsemaphore-interface.md)
- [<span data-ttu-id="8595b-132">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="8595b-132">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
