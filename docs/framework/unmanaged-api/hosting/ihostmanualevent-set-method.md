---
title: Метод IHostManualEvent::Set
ms.date: 03/30/2017
api_name:
- IHostManualEvent.Set
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostManualEvent::Set
helpviewer_keywords:
- Set method, IHostManualEvent interface [.NET Framework hosting]
- IHostManualEvent::Set method [.NET Framework hosting]
ms.assetid: e930c174-f71d-4faa-bb59-f0fb3df4d77b
topic_type:
- apiref
ms.openlocfilehash: bc2b178c6c26a6de62982c35d5aeb9ea5359c2bf
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679134"
---
# <a name="ihostmanualeventset-method"></a><span data-ttu-id="42d98-102">Метод IHostManualEvent::Set</span><span class="sxs-lookup"><span data-stu-id="42d98-102">IHostManualEvent::Set Method</span></span>

<span data-ttu-id="42d98-103">Устанавливает для текущего экземпляра [ихостмануалевент](ihostmanualevent-interface.md) сигнальное состояние.</span><span class="sxs-lookup"><span data-stu-id="42d98-103">Sets the current [IHostManualEvent](ihostmanualevent-interface.md) instance to a signaled state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42d98-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="42d98-104">Syntax</span></span>  
  
```cpp  
HRESULT Set ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="42d98-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="42d98-105">Return Value</span></span>  
  
|<span data-ttu-id="42d98-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="42d98-106">HRESULT</span></span>|<span data-ttu-id="42d98-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="42d98-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="42d98-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="42d98-108">S_OK</span></span>|<span data-ttu-id="42d98-109">`Set` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="42d98-109">`Set` returned successfully.</span></span>|  
|<span data-ttu-id="42d98-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="42d98-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="42d98-111">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="42d98-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="42d98-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="42d98-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="42d98-113">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="42d98-113">The call timed out.</span></span>|  
|<span data-ttu-id="42d98-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="42d98-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="42d98-115">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="42d98-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="42d98-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="42d98-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="42d98-117">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="42d98-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="42d98-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="42d98-118">E_FAIL</span></span>|<span data-ttu-id="42d98-119">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="42d98-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="42d98-120">Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="42d98-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="42d98-121">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="42d98-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="42d98-122">Требования</span><span class="sxs-lookup"><span data-stu-id="42d98-122">Requirements</span></span>  

 <span data-ttu-id="42d98-123">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="42d98-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42d98-124">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="42d98-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="42d98-125">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="42d98-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="42d98-126">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42d98-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42d98-127">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="42d98-127">See also</span></span>

- [<span data-ttu-id="42d98-128">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="42d98-128">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="42d98-129">Интерфейс IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="42d98-129">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="42d98-130">Интерфейс IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="42d98-130">IHostManualEvent Interface</span></span>](ihostmanualevent-interface.md)
- [<span data-ttu-id="42d98-131">Интерфейс IHostSemaphore</span><span class="sxs-lookup"><span data-stu-id="42d98-131">IHostSemaphore Interface</span></span>](ihostsemaphore-interface.md)
- [<span data-ttu-id="42d98-132">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="42d98-132">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
