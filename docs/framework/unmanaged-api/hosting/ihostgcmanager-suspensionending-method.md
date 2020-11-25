---
title: Метод IHostGCManager::SuspensionEnding
ms.date: 03/30/2017
api_name:
- IHostGCManager.SuspensionEnding
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostGCManager::SuspensionEnding
helpviewer_keywords:
- SuspensionEnding method, IHostGCManager interface [.NET Framework hosting]
- IHostGCManager::SuspensionEnding method [.NET Framework hosting]
ms.assetid: 8849a1db-17f0-44b7-880a-bd36d431eb91
topic_type:
- apiref
ms.openlocfilehash: e2624f5fce168662fac8fd5f4324617c7acf802c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729555"
---
# <a name="ihostgcmanagersuspensionending-method"></a><span data-ttu-id="43c27-102">Метод IHostGCManager::SuspensionEnding</span><span class="sxs-lookup"><span data-stu-id="43c27-102">IHostGCManager::SuspensionEnding Method</span></span>

<span data-ttu-id="43c27-103">Уведомляет основное приложение о том, что среда CLR возобновляет выполнение задач в потоках, которые были приостановлены для сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="43c27-103">Notifies the host that the common language runtime (CLR) is resuming execution of tasks on threads that had been suspended for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43c27-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="43c27-104">Syntax</span></span>  
  
```cpp  
HRESULT SuspensionEnding (  
    [in] DWORD generation  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="43c27-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="43c27-105">Parameters</span></span>  

 `generation`  
 <span data-ttu-id="43c27-106">окне Поколение сборки мусора, которое только что завершается, из которого происходит возобновление работы потока.</span><span class="sxs-lookup"><span data-stu-id="43c27-106">[in] The garbage collection generation that is just finishing, from which the thread is resuming.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="43c27-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="43c27-107">Return Value</span></span>  
  
|<span data-ttu-id="43c27-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="43c27-108">HRESULT</span></span>|<span data-ttu-id="43c27-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="43c27-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="43c27-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="43c27-110">S_OK</span></span>|<span data-ttu-id="43c27-111">`SuspensionEnding` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="43c27-111">`SuspensionEnding` returned successfully.</span></span>|  
|<span data-ttu-id="43c27-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="43c27-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="43c27-113">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="43c27-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="43c27-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="43c27-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="43c27-115">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="43c27-115">The call timed out.</span></span>|  
|<span data-ttu-id="43c27-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="43c27-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="43c27-117">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="43c27-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="43c27-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="43c27-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="43c27-119">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="43c27-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="43c27-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="43c27-120">E_FAIL</span></span>|<span data-ttu-id="43c27-121">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="43c27-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="43c27-122">Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="43c27-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="43c27-123">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="43c27-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="43c27-124">Комментарии</span><span class="sxs-lookup"><span data-stu-id="43c27-124">Remarks</span></span>  

 <span data-ttu-id="43c27-125">Среда CLR вызывает `SuspensionEnding` после выполнения сборки мусора, чтобы уведомить узел о том, что поток возобновляет выполнение.</span><span class="sxs-lookup"><span data-stu-id="43c27-125">The CLR calls `SuspensionEnding` after it performs a garbage collection, to inform the host that the thread is resuming execution.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="43c27-126">Не Перепланируйте поток, из которого был сделан вызов метода.</span><span class="sxs-lookup"><span data-stu-id="43c27-126">Do not reschedule the thread the method call was made from.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43c27-127">Требования</span><span class="sxs-lookup"><span data-stu-id="43c27-127">Requirements</span></span>  

 <span data-ttu-id="43c27-128">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="43c27-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43c27-129">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="43c27-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="43c27-130">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="43c27-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="43c27-131">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43c27-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43c27-132">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="43c27-132">See also</span></span>

- [<span data-ttu-id="43c27-133">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="43c27-133">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="43c27-134">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="43c27-134">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="43c27-135">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="43c27-135">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="43c27-136">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="43c27-136">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="43c27-137">Интерфейс IHostGCManager</span><span class="sxs-lookup"><span data-stu-id="43c27-137">IHostGCManager Interface</span></span>](ihostgcmanager-interface.md)
