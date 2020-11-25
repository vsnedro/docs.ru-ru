---
title: Метод IHostManualEvent::Wait
ms.date: 03/30/2017
api_name:
- IHostManualEvent.Wait
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostManualEvent::Wait
helpviewer_keywords:
- IHostManualEvent::Wait method [.NET Framework hosting]
- Wait method, IHostManualEvent interface [.NET Framework hosting]
ms.assetid: 1fbb7d8b-8a23-4c2b-8376-1a70cd2d6030
topic_type:
- apiref
ms.openlocfilehash: 3fe8434ba4a7fc49b99bdf3084ce4f3981f25a9b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719831"
---
# <a name="ihostmanualeventwait-method"></a><span data-ttu-id="6fa00-102">Метод IHostManualEvent::Wait</span><span class="sxs-lookup"><span data-stu-id="6fa00-102">IHostManualEvent::Wait Method</span></span>

<span data-ttu-id="6fa00-103">Заставляет текущий экземпляр [ихостмануалевент](ihostmanualevent-interface.md) ожидать его признания или истечения указанного времени.</span><span class="sxs-lookup"><span data-stu-id="6fa00-103">Causes the current [IHostManualEvent](ihostmanualevent-interface.md) instance to wait until it is owned, or a specified amount of time elapses.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6fa00-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6fa00-104">Syntax</span></span>  
  
```cpp  
HRESULT Wait (  
    [in] DWORD dwMilliseconds,  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6fa00-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6fa00-105">Parameters</span></span>  

 `dwMilliseconds`  
 <span data-ttu-id="6fa00-106">окне Число миллисекунд ожидания перед возвратом, если текущий `IHostManualEvent` экземпляр не принадлежит.</span><span class="sxs-lookup"><span data-stu-id="6fa00-106">[in] The number of milliseconds to wait before returning, if the current `IHostManualEvent` instance is not owned.</span></span>  
  
 `option`  
 <span data-ttu-id="6fa00-107">окне Одно из значений [WAIT_OPTION](wait-option-enumeration.md) , указывающее действие, которое должен выполнить узел, если эта операция блокируется.</span><span class="sxs-lookup"><span data-stu-id="6fa00-107">[in] One of the [WAIT_OPTION](wait-option-enumeration.md) values, indicating the action the host should take if this operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6fa00-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="6fa00-108">Return Value</span></span>  
  
|<span data-ttu-id="6fa00-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6fa00-109">HRESULT</span></span>|<span data-ttu-id="6fa00-110">Описание:</span><span class="sxs-lookup"><span data-stu-id="6fa00-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6fa00-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="6fa00-111">S_OK</span></span>|<span data-ttu-id="6fa00-112">`Wait` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="6fa00-112">`Wait` returned successfully.</span></span>|  
|<span data-ttu-id="6fa00-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6fa00-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6fa00-114">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="6fa00-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="6fa00-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6fa00-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="6fa00-116">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="6fa00-116">The call timed out.</span></span>|  
|<span data-ttu-id="6fa00-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="6fa00-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="6fa00-118">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="6fa00-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="6fa00-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="6fa00-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="6fa00-120">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="6fa00-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="6fa00-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6fa00-121">E_FAIL</span></span>|<span data-ttu-id="6fa00-122">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="6fa00-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="6fa00-123">Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="6fa00-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="6fa00-124">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="6fa00-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="6fa00-125">HOST_E_DEADLOCK</span><span class="sxs-lookup"><span data-stu-id="6fa00-125">HOST_E_DEADLOCK</span></span>|<span data-ttu-id="6fa00-126">Узел обнаружил взаимоблокировку в течение интервала ожидания и выбрал текущий экземпляр в `IHostManualEvent` качестве жертвы взаимоблокировки.</span><span class="sxs-lookup"><span data-stu-id="6fa00-126">The host detected a deadlock during the wait interval, and chose the current `IHostManualEvent` instance as the deadlock victim.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6fa00-127">Требования</span><span class="sxs-lookup"><span data-stu-id="6fa00-127">Requirements</span></span>  

 <span data-ttu-id="6fa00-128">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6fa00-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6fa00-129">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="6fa00-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6fa00-130">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6fa00-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6fa00-131">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6fa00-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fa00-132">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="6fa00-132">See also</span></span>

- [<span data-ttu-id="6fa00-133">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="6fa00-133">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="6fa00-134">Интерфейс IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="6fa00-134">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="6fa00-135">Интерфейс IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="6fa00-135">IHostManualEvent Interface</span></span>](ihostmanualevent-interface.md)
- [<span data-ttu-id="6fa00-136">Интерфейс IHostSemaphore</span><span class="sxs-lookup"><span data-stu-id="6fa00-136">IHostSemaphore Interface</span></span>](ihostsemaphore-interface.md)
- [<span data-ttu-id="6fa00-137">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="6fa00-137">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
