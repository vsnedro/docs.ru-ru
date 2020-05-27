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
ms.openlocfilehash: ea3269d06fdd3f5a2e365465d45ba6e569127b0a
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/26/2020
ms.locfileid: "83842378"
---
# <a name="ihosttaskmanagerbegindelayabort-method"></a><span data-ttu-id="7488d-102">Метод IHostTaskManager::BeginDelayAbort</span><span class="sxs-lookup"><span data-stu-id="7488d-102">IHostTaskManager::BeginDelayAbort Method</span></span>
<span data-ttu-id="7488d-103">Уведомляет узел о том, что управляемый код вводит точку, в которой не нужно прерывать текущую задачу.</span><span class="sxs-lookup"><span data-stu-id="7488d-103">Notifies the host that managed code is entering a period in which the current task must not be aborted.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7488d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7488d-104">Syntax</span></span>  
  
```cpp  
HRESULT BeginDelayAbort ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="7488d-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="7488d-105">Return Value</span></span>  
  
|<span data-ttu-id="7488d-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7488d-106">HRESULT</span></span>|<span data-ttu-id="7488d-107">Описание</span><span class="sxs-lookup"><span data-stu-id="7488d-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7488d-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="7488d-108">S_OK</span></span>|<span data-ttu-id="7488d-109">`BeginDelayAbort`успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="7488d-109">`BeginDelayAbort` returned successfully.</span></span>|  
|<span data-ttu-id="7488d-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7488d-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7488d-111">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="7488d-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7488d-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7488d-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7488d-113">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="7488d-113">The call timed out.</span></span>|  
|<span data-ttu-id="7488d-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7488d-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7488d-115">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="7488d-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7488d-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7488d-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7488d-117">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="7488d-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7488d-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7488d-118">E_FAIL</span></span>|<span data-ttu-id="7488d-119">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="7488d-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7488d-120">Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="7488d-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7488d-121">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="7488d-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="7488d-122">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="7488d-122">E_UNEXPECTED</span></span>|<span data-ttu-id="7488d-123">`BeginDelayAbort`уже вызван, но соответствующий вызов [EndDelayAbort](ihosttaskmanager-enddelayabort-method.md) еще не получен.</span><span class="sxs-lookup"><span data-stu-id="7488d-123">`BeginDelayAbort` has already been called, but the corresponding call to [EndDelayAbort](ihosttaskmanager-enddelayabort-method.md) has not yet been received.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7488d-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="7488d-124">Remarks</span></span>  
 <span data-ttu-id="7488d-125">Узел не должен прерывать текущую задачу до `EndDelayAbort` вызова метода.</span><span class="sxs-lookup"><span data-stu-id="7488d-125">The host must not abort the current task until `EndDelayAbort` is called.</span></span> <span data-ttu-id="7488d-126">Если другой вызов выполняется `BeginDelayAbort` без промежуточного вызова `EndDelayAbort` , узел должен возвращать E_UNEXPECTED из `BeginDelayAbort` и не должен предпринимать никаких действий.</span><span class="sxs-lookup"><span data-stu-id="7488d-126">If another call to `BeginDelayAbort` is made without an intervening call to `EndDelayAbort`, the host should return E_UNEXPECTED from `BeginDelayAbort`, and should take no action.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7488d-127">Требования</span><span class="sxs-lookup"><span data-stu-id="7488d-127">Requirements</span></span>  
 <span data-ttu-id="7488d-128">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7488d-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7488d-129">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="7488d-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7488d-130">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="7488d-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7488d-131">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7488d-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7488d-132">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="7488d-132">See also</span></span>

- [<span data-ttu-id="7488d-133">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="7488d-133">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="7488d-134">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="7488d-134">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="7488d-135">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="7488d-135">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
