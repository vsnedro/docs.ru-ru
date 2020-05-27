---
title: Метод IHostAutoEvent::Wait
ms.date: 03/30/2017
api_name:
- IHostAutoEvent.Wait
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAutoEvent::Wait
helpviewer_keywords:
- Wait method, IHostAutoEvent interface [.NET Framework hosting]
- IHostAutoEvent::Wait method [.NET Framework hosting]
ms.assetid: 535d51c5-9112-401b-8c36-85f35d7ee609
topic_type:
- apiref
ms.openlocfilehash: 7baabafc61e14d127ff3f0cdb7453be6f1a2abeb
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804976"
---
# <a name="ihostautoeventwait-method"></a><span data-ttu-id="55b66-102">Метод IHostAutoEvent::Wait</span><span class="sxs-lookup"><span data-stu-id="55b66-102">IHostAutoEvent::Wait Method</span></span>
<span data-ttu-id="55b66-103">Приводит к тому, что текущий экземпляр [ихостаутоевент](ihostautoevent-interface.md) ожидает его признания или истечения указанного периода времени.</span><span class="sxs-lookup"><span data-stu-id="55b66-103">Causes the current [IHostAutoEvent](ihostautoevent-interface.md) instance to wait until it is owned or a specified amount of time elapses.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55b66-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="55b66-104">Syntax</span></span>  
  
```cpp  
HRESULT Wait (  
    [in] DWORD dwMilliseconds,  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="55b66-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="55b66-105">Parameters</span></span>  
 `dwMilliseconds`  
 <span data-ttu-id="55b66-106">окне Число миллисекунд, в течение которых текущий `IHostAutoEvent` экземпляр должен ожидать перед возвратом, если ни один из потоков или волокон не получает владение.</span><span class="sxs-lookup"><span data-stu-id="55b66-106">[in] The number of milliseconds the current `IHostAutoEvent` instance should wait before returning, if no thread or fiber takes ownership.</span></span>  
  
 `option`  
 <span data-ttu-id="55b66-107">окне Одно из значений [WAIT_OPTION](wait-option-enumeration.md) , определяющее действие, которое должен выполнить узел, если эта операция блокируется.</span><span class="sxs-lookup"><span data-stu-id="55b66-107">[in] One of the [WAIT_OPTION](wait-option-enumeration.md) values, specifying the action the host should take if this operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="55b66-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="55b66-108">Return Value</span></span>  
  
|<span data-ttu-id="55b66-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="55b66-109">HRESULT</span></span>|<span data-ttu-id="55b66-110">Описание</span><span class="sxs-lookup"><span data-stu-id="55b66-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="55b66-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="55b66-111">S_OK</span></span>|<span data-ttu-id="55b66-112">`Wait`успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="55b66-112">`Wait` returned successfully.</span></span>|  
|<span data-ttu-id="55b66-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="55b66-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="55b66-114">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="55b66-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="55b66-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="55b66-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="55b66-116">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="55b66-116">The call timed out.</span></span>|  
|<span data-ttu-id="55b66-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="55b66-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="55b66-118">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="55b66-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="55b66-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="55b66-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="55b66-120">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="55b66-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="55b66-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="55b66-121">E_FAIL</span></span>|<span data-ttu-id="55b66-122">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="55b66-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="55b66-123">Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="55b66-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="55b66-124">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="55b66-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="55b66-125">HOST_E_DEADLOCK</span><span class="sxs-lookup"><span data-stu-id="55b66-125">HOST_E_DEADLOCK</span></span>|<span data-ttu-id="55b66-126">Узел обнаружил взаимоблокировку в течение интервала ожидания и выбрал событие, представленное текущим `IHostAutoEvent` экземпляром в качестве жертвы взаимоблокировки.</span><span class="sxs-lookup"><span data-stu-id="55b66-126">The host detected a deadlock during the wait interval, and chose the event represented by the current `IHostAutoEvent` instance as the deadlock victim.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="55b66-127">Требования</span><span class="sxs-lookup"><span data-stu-id="55b66-127">Requirements</span></span>  
 <span data-ttu-id="55b66-128">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="55b66-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55b66-129">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="55b66-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="55b66-130">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="55b66-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="55b66-131">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55b66-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55b66-132">См. также статью</span><span class="sxs-lookup"><span data-stu-id="55b66-132">See also</span></span>

- [<span data-ttu-id="55b66-133">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="55b66-133">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="55b66-134">Интерфейс IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="55b66-134">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="55b66-135">Интерфейс IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="55b66-135">IHostManualEvent Interface</span></span>](ihostmanualevent-interface.md)
- [<span data-ttu-id="55b66-136">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="55b66-136">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
