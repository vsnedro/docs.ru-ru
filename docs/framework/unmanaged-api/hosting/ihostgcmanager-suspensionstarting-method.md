---
title: Метод IHostGCManager::SuspensionStarting
ms.date: 03/30/2017
api_name:
- IHostGCManager.SuspensionStarting
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostGCManager::SuspensionStarting
helpviewer_keywords:
- SuspensionStarting method, IHostGCManager interface [.NET Framework hosting]
- IHostGCManager::SuspensionStarting method [.NET Framework hosting]
ms.assetid: c381f524-94cf-4fa2-9298-50f847a03431
topic_type:
- apiref
ms.openlocfilehash: 7e610676e86dde3ab0bdea2ce2314f02b3da9976
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729503"
---
# <a name="ihostgcmanagersuspensionstarting-method"></a><span data-ttu-id="10541-102">Метод IHostGCManager::SuspensionStarting</span><span class="sxs-lookup"><span data-stu-id="10541-102">IHostGCManager::SuspensionStarting Method</span></span>

<span data-ttu-id="10541-103">Уведомляет основное приложение о том, что среда CLR приостанавливает выполнение задач, для выполнения сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="10541-103">Notifies the host that the common language runtime (CLR) is suspending execution of tasks, to perform a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10541-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="10541-104">Syntax</span></span>  
  
```cpp  
HRESULT SuspensionStarting ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="10541-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="10541-105">Return Value</span></span>  
  
|<span data-ttu-id="10541-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="10541-106">HRESULT</span></span>|<span data-ttu-id="10541-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="10541-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="10541-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="10541-108">S_OK</span></span>|<span data-ttu-id="10541-109">`SuspensionStarting` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="10541-109">`SuspensionStarting` returned successfully.</span></span>|  
|<span data-ttu-id="10541-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="10541-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="10541-111">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="10541-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="10541-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="10541-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="10541-113">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="10541-113">The call timed out.</span></span>|  
|<span data-ttu-id="10541-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="10541-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="10541-115">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="10541-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="10541-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="10541-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="10541-117">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="10541-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="10541-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="10541-118">E_FAIL</span></span>|<span data-ttu-id="10541-119">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="10541-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="10541-120">Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="10541-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="10541-121">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="10541-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="10541-122">Комментарии</span><span class="sxs-lookup"><span data-stu-id="10541-122">Remarks</span></span>  

 <span data-ttu-id="10541-123">Вызовы CLR `SuspensionStarting` для информирования узла о сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="10541-123">The CLR calls `SuspensionStarting` to inform the host that garbage collection is occurring.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="10541-124">Не Перепланируйте эту задачу.</span><span class="sxs-lookup"><span data-stu-id="10541-124">Do not reschedule this task.</span></span> <span data-ttu-id="10541-125">Узел должен перепланировать задачу при вызове [среадисблоккингфорсуспенсион](ihostgcmanager-threadisblockingforsuspension-method.md) .</span><span class="sxs-lookup"><span data-stu-id="10541-125">The host must reschedule a task when [ThreadIsBlockingForSuspension](ihostgcmanager-threadisblockingforsuspension-method.md) is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10541-126">Требования</span><span class="sxs-lookup"><span data-stu-id="10541-126">Requirements</span></span>  

 <span data-ttu-id="10541-127">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="10541-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10541-128">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="10541-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="10541-129">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="10541-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="10541-130">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10541-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10541-131">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="10541-131">See also</span></span>

- [<span data-ttu-id="10541-132">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="10541-132">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="10541-133">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="10541-133">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="10541-134">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="10541-134">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="10541-135">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="10541-135">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="10541-136">Интерфейс IHostGCManager</span><span class="sxs-lookup"><span data-stu-id="10541-136">IHostGCManager Interface</span></span>](ihostgcmanager-interface.md)
