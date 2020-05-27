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
ms.openlocfilehash: 049a0ae6d860c7c431d08af8ba4539656b8e5592
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804575"
---
# <a name="ihostmanualeventreset-method"></a><span data-ttu-id="4c6e9-102">Метод IHostManualEvent::Reset</span><span class="sxs-lookup"><span data-stu-id="4c6e9-102">IHostManualEvent::Reset Method</span></span>
<span data-ttu-id="4c6e9-103">Сбрасывает текущий экземпляр [ихостмануалевент](ihostmanualevent-interface.md) в несигнальное состояние.</span><span class="sxs-lookup"><span data-stu-id="4c6e9-103">Resets the current [IHostManualEvent](ihostmanualevent-interface.md) instance to a non-signaled state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c6e9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4c6e9-104">Syntax</span></span>  
  
```cpp  
HRESULT Reset ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="4c6e9-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="4c6e9-105">Return Value</span></span>  
  
|<span data-ttu-id="4c6e9-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4c6e9-106">HRESULT</span></span>|<span data-ttu-id="4c6e9-107">Описание</span><span class="sxs-lookup"><span data-stu-id="4c6e9-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4c6e9-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="4c6e9-108">S_OK</span></span>|<span data-ttu-id="4c6e9-109">`Reset`успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="4c6e9-109">`Reset` returned successfully.</span></span>|  
|<span data-ttu-id="4c6e9-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4c6e9-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4c6e9-111">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="4c6e9-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4c6e9-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4c6e9-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4c6e9-113">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="4c6e9-113">The call timed out.</span></span>|  
|<span data-ttu-id="4c6e9-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4c6e9-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4c6e9-115">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="4c6e9-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4c6e9-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4c6e9-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4c6e9-117">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="4c6e9-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4c6e9-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4c6e9-118">E_FAIL</span></span>|<span data-ttu-id="4c6e9-119">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="4c6e9-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4c6e9-120">Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="4c6e9-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4c6e9-121">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="4c6e9-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4c6e9-122">Требования</span><span class="sxs-lookup"><span data-stu-id="4c6e9-122">Requirements</span></span>  
 <span data-ttu-id="4c6e9-123">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4c6e9-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4c6e9-124">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="4c6e9-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4c6e9-125">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="4c6e9-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4c6e9-126">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4c6e9-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c6e9-127">См. также статью</span><span class="sxs-lookup"><span data-stu-id="4c6e9-127">See also</span></span>

- [<span data-ttu-id="4c6e9-128">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="4c6e9-128">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="4c6e9-129">Интерфейс IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="4c6e9-129">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="4c6e9-130">Интерфейс IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="4c6e9-130">IHostManualEvent Interface</span></span>](ihostmanualevent-interface.md)
- [<span data-ttu-id="4c6e9-131">Интерфейс IHostSemaphore</span><span class="sxs-lookup"><span data-stu-id="4c6e9-131">IHostSemaphore Interface</span></span>](ihostsemaphore-interface.md)
- [<span data-ttu-id="4c6e9-132">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="4c6e9-132">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
