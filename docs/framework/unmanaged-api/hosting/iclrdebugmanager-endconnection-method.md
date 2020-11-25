---
title: Метод ICLRDebugManager::EndConnection
ms.date: 03/30/2017
api_name:
- ICLRDebugManager.EndConnection
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager::EndConnection
helpviewer_keywords:
- ICLRDebugManager::EndConnection method [.NET Framework hosting]
- EndConnection method [.NET Framework hosting]
ms.assetid: 89dc7363-2f29-4eb2-8f23-fccdda6a76a6
topic_type:
- apiref
ms.openlocfilehash: d6f22d6185f4063078463043a6ffd46e56289267
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719857"
---
# <a name="iclrdebugmanagerendconnection-method"></a><span data-ttu-id="6bd9d-102">Метод ICLRDebugManager::EndConnection</span><span class="sxs-lookup"><span data-stu-id="6bd9d-102">ICLRDebugManager::EndConnection Method</span></span>

<span data-ttu-id="6bd9d-103">Удаляет связь между списком задач и идентификатором и понятным именем.</span><span class="sxs-lookup"><span data-stu-id="6bd9d-103">Removes the association between a list of tasks and an identifier and a friendly name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6bd9d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6bd9d-104">Syntax</span></span>  
  
```cpp  
HRESULT EndConnection (  
    [in] CONNID dwConnectionId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6bd9d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6bd9d-105">Parameters</span></span>  

 `dwConnectionId`  
 <span data-ttu-id="6bd9d-106">окне Специфический для узла идентификатор соединения и связанный список задач среды CLR.</span><span class="sxs-lookup"><span data-stu-id="6bd9d-106">[in] The host-specific identifier for the connection and the associated list of common language runtime (CLR) tasks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6bd9d-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="6bd9d-107">Return Value</span></span>  
  
|<span data-ttu-id="6bd9d-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6bd9d-108">HRESULT</span></span>|<span data-ttu-id="6bd9d-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="6bd9d-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6bd9d-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="6bd9d-110">S_OK</span></span>|<span data-ttu-id="6bd9d-111">`EndConnection` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="6bd9d-111">`EndConnection` returned successfully.</span></span>|  
|<span data-ttu-id="6bd9d-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6bd9d-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6bd9d-113">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="6bd9d-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="6bd9d-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6bd9d-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="6bd9d-115">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="6bd9d-115">The call timed out.</span></span>|  
|<span data-ttu-id="6bd9d-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="6bd9d-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="6bd9d-117">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="6bd9d-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="6bd9d-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="6bd9d-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="6bd9d-119">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="6bd9d-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="6bd9d-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6bd9d-120">E_FAIL</span></span>|<span data-ttu-id="6bd9d-121">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="6bd9d-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="6bd9d-122">После того как метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="6bd9d-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="6bd9d-123">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="6bd9d-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="6bd9d-124">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="6bd9d-124">E_INVALIDARG</span></span>|<span data-ttu-id="6bd9d-125">[Бегинконнектион](iclrdebugmanager-beginconnection-method.md) никогда не вызывался с помощью `dwConnectionId` , или `dwConnectionId` равен нулю.</span><span class="sxs-lookup"><span data-stu-id="6bd9d-125">[BeginConnection](iclrdebugmanager-beginconnection-method.md) was never called using `dwConnectionId`, or `dwConnectionId` was zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6bd9d-126">Комментарии</span><span class="sxs-lookup"><span data-stu-id="6bd9d-126">Remarks</span></span>  

 <span data-ttu-id="6bd9d-127">[ICLRDebugManager](iclrdebugmanager-interface.md) предоставляет три метода, `BeginConnection` , [SetConnectionTasks](iclrdebugmanager-setconnectiontasks-method.md)и `EndConnection` , для связывания списков задач с идентификаторами и понятными именами.</span><span class="sxs-lookup"><span data-stu-id="6bd9d-127">[ICLRDebugManager](iclrdebugmanager-interface.md) provides three methods, `BeginConnection`, [SetConnectionTasks](iclrdebugmanager-setconnectiontasks-method.md), and `EndConnection`, for associating task lists with identifiers and friendly names.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="6bd9d-128">Эти три метода должны вызываться в определенном порядке для каждого набора задач.</span><span class="sxs-lookup"><span data-stu-id="6bd9d-128">These three methods must be called in a specific order for each set of tasks.</span></span> <span data-ttu-id="6bd9d-129">`BeginConnection` вызывается первым для установления нового соединения.</span><span class="sxs-lookup"><span data-stu-id="6bd9d-129">`BeginConnection` is called first to establish a new connection.</span></span> <span data-ttu-id="6bd9d-130">`SetConnectionTasks` вызывается далее для предоставления набора задач, которые должны быть связаны с этим соединением.</span><span class="sxs-lookup"><span data-stu-id="6bd9d-130">`SetConnectionTasks` is called next to provide the set of tasks to be associated with that connection.</span></span> <span data-ttu-id="6bd9d-131">`EndConnection` вызывается последним, чтобы удалить связь между списком задач и идентификатором и понятным именем. Однако вызовы для различных соединений могут быть вложенными.</span><span class="sxs-lookup"><span data-stu-id="6bd9d-131">`EndConnection` is called last to remove the association between the task list and the identifier and friendly name.However, calls for different connections can be nested.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6bd9d-132">Требования</span><span class="sxs-lookup"><span data-stu-id="6bd9d-132">Requirements</span></span>  

 <span data-ttu-id="6bd9d-133">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6bd9d-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6bd9d-134">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="6bd9d-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6bd9d-135">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6bd9d-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6bd9d-136">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6bd9d-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bd9d-137">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="6bd9d-137">See also</span></span>

- [<span data-ttu-id="6bd9d-138">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="6bd9d-138">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="6bd9d-139">Интерфейс ICLRDebugManager</span><span class="sxs-lookup"><span data-stu-id="6bd9d-139">ICLRDebugManager Interface</span></span>](iclrdebugmanager-interface.md)
- [<span data-ttu-id="6bd9d-140">Метод BeginConnection</span><span class="sxs-lookup"><span data-stu-id="6bd9d-140">BeginConnection Method</span></span>](iclrdebugmanager-beginconnection-method.md)
- [<span data-ttu-id="6bd9d-141">Метод SetConnectionTasks</span><span class="sxs-lookup"><span data-stu-id="6bd9d-141">SetConnectionTasks Method</span></span>](iclrdebugmanager-setconnectiontasks-method.md)
- [<span data-ttu-id="6bd9d-142">Интерфейс IHostControl</span><span class="sxs-lookup"><span data-stu-id="6bd9d-142">IHostControl Interface</span></span>](ihostcontrol-interface.md)
