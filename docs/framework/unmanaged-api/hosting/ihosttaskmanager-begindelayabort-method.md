---
title: Метод IHostTaskManager::BeginDelayAbort
ms.date: 03/30/2017
api_name:
- IHostTaskManager.BeginDelayAbort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::BeginDelayAbort
helpviewer_keywords:
- BeginDelayAbort method [.NET Framework hosting]
- IHostTaskManager::BeginDelayAbort method [.NET Framework hosting]
ms.assetid: 75f42a8b-ed68-4718-a030-a179cfba7d72
topic_type:
- apiref
ms.openlocfilehash: f72cc15904d098e159dd7f75f673d43ae987998d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727332"
---
# <a name="ihosttaskmanagerbegindelayabort-method"></a><span data-ttu-id="db62e-102">Метод IHostTaskManager::BeginDelayAbort</span><span class="sxs-lookup"><span data-stu-id="db62e-102">IHostTaskManager::BeginDelayAbort Method</span></span>

<span data-ttu-id="db62e-103">Уведомляет узел о том, что управляемый код вводит точку, в которой не нужно прерывать текущую задачу.</span><span class="sxs-lookup"><span data-stu-id="db62e-103">Notifies the host that managed code is entering a period in which the current task must not be aborted.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db62e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="db62e-104">Syntax</span></span>  
  
```cpp  
HRESULT BeginDelayAbort ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="db62e-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="db62e-105">Return Value</span></span>  
  
|<span data-ttu-id="db62e-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="db62e-106">HRESULT</span></span>|<span data-ttu-id="db62e-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="db62e-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="db62e-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="db62e-108">S_OK</span></span>|<span data-ttu-id="db62e-109">`BeginDelayAbort` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="db62e-109">`BeginDelayAbort` returned successfully.</span></span>|  
|<span data-ttu-id="db62e-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="db62e-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="db62e-111">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="db62e-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="db62e-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="db62e-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="db62e-113">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="db62e-113">The call timed out.</span></span>|  
|<span data-ttu-id="db62e-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="db62e-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="db62e-115">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="db62e-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="db62e-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="db62e-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="db62e-117">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="db62e-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="db62e-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="db62e-118">E_FAIL</span></span>|<span data-ttu-id="db62e-119">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="db62e-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="db62e-120">Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="db62e-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="db62e-121">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="db62e-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="db62e-122">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="db62e-122">E_UNEXPECTED</span></span>|<span data-ttu-id="db62e-123">`BeginDelayAbort` уже вызван, но соответствующий вызов [EndDelayAbort](ihosttaskmanager-enddelayabort-method.md) еще не получен.</span><span class="sxs-lookup"><span data-stu-id="db62e-123">`BeginDelayAbort` has already been called, but the corresponding call to [EndDelayAbort](ihosttaskmanager-enddelayabort-method.md) has not yet been received.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="db62e-124">Комментарии</span><span class="sxs-lookup"><span data-stu-id="db62e-124">Remarks</span></span>  

 <span data-ttu-id="db62e-125">Узел не должен прерывать текущую задачу до `EndDelayAbort` вызова метода.</span><span class="sxs-lookup"><span data-stu-id="db62e-125">The host must not abort the current task until `EndDelayAbort` is called.</span></span> <span data-ttu-id="db62e-126">Если другой вызов выполняется `BeginDelayAbort` без промежуточного вызова `EndDelayAbort` , узел должен возвращать E_UNEXPECTED из `BeginDelayAbort` и не должен предпринимать никаких действий.</span><span class="sxs-lookup"><span data-stu-id="db62e-126">If another call to `BeginDelayAbort` is made without an intervening call to `EndDelayAbort`, the host should return E_UNEXPECTED from `BeginDelayAbort`, and should take no action.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db62e-127">Требования</span><span class="sxs-lookup"><span data-stu-id="db62e-127">Requirements</span></span>  

 <span data-ttu-id="db62e-128">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="db62e-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db62e-129">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="db62e-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="db62e-130">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="db62e-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="db62e-131">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db62e-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db62e-132">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="db62e-132">See also</span></span>

- [<span data-ttu-id="db62e-133">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="db62e-133">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="db62e-134">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="db62e-134">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="db62e-135">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="db62e-135">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
