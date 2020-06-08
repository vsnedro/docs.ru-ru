---
title: Метод ICLRDebugManager::BeginConnection
ms.date: 03/30/2017
api_name:
- ICLRDebugManager.BeginConnection
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager::BeginConnection
helpviewer_keywords:
- ICLRDebugManager::BeginConnection method [.NET Framework hosting]
- BeginConnection method [.NET Framework hosting]
ms.assetid: bdd98146-ff4d-4150-a264-a4c1a32d31f3
topic_type:
- apiref
ms.openlocfilehash: 98e4efe149cab1b822c9993e4df28806f773c61d
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504255"
---
# <a name="iclrdebugmanagerbeginconnection-method"></a><span data-ttu-id="fcc15-102">Метод ICLRDebugManager::BeginConnection</span><span class="sxs-lookup"><span data-stu-id="fcc15-102">ICLRDebugManager::BeginConnection Method</span></span>
<span data-ttu-id="fcc15-103">Устанавливает новое соединение между узлом и отладчиком, чтобы связать список задач с идентификатором и понятным именем.</span><span class="sxs-lookup"><span data-stu-id="fcc15-103">Establishes a new connection between the host and the debugger to associate a list of tasks with an identifier and a friendly name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fcc15-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fcc15-104">Syntax</span></span>  
  
```cpp  
HRESULT BeginConnection (  
    [in] CONNID dwConnectionId,  
    [in, string] wchar_t* szConnectionName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fcc15-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="fcc15-105">Parameters</span></span>  
 `dwConnectionId`  
 <span data-ttu-id="fcc15-106">окне Идентификатор, связываемый со списком задач среды CLR.</span><span class="sxs-lookup"><span data-stu-id="fcc15-106">[in] An identifier to associate with the list of common language runtime (CLR) tasks.</span></span>  
  
 `szConnectionName`  
 <span data-ttu-id="fcc15-107">окне Понятное имя, связываемое со списком задач среды CLR.</span><span class="sxs-lookup"><span data-stu-id="fcc15-107">[in] A friendly name to associate with the list of CLR tasks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fcc15-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="fcc15-108">Return Value</span></span>  
  
|<span data-ttu-id="fcc15-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fcc15-109">HRESULT</span></span>|<span data-ttu-id="fcc15-110">Описание</span><span class="sxs-lookup"><span data-stu-id="fcc15-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fcc15-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="fcc15-111">S_OK</span></span>|<span data-ttu-id="fcc15-112">`BeginConnection`успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="fcc15-112">`BeginConnection` returned successfully.</span></span>|  
|<span data-ttu-id="fcc15-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="fcc15-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="fcc15-114">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="fcc15-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="fcc15-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="fcc15-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="fcc15-116">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="fcc15-116">The call timed out.</span></span>|  
|<span data-ttu-id="fcc15-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="fcc15-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="fcc15-118">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="fcc15-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="fcc15-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="fcc15-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="fcc15-120">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="fcc15-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="fcc15-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="fcc15-121">E_FAIL</span></span>|<span data-ttu-id="fcc15-122">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="fcc15-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="fcc15-123">После того как метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="fcc15-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="fcc15-124">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="fcc15-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="fcc15-125">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="fcc15-125">E_INVALIDARG</span></span>|<span data-ttu-id="fcc15-126">`dwConnectionId`был равен нулю или `BeginConnection` уже был вызван с помощью этого `dwConnectionId` значения или `szConnectionName` был равен null.</span><span class="sxs-lookup"><span data-stu-id="fcc15-126">`dwConnectionId` was zero, or `BeginConnection` was already called using this `dwConnectionId` value, or `szConnectionName` was null.</span></span>|  
|<span data-ttu-id="fcc15-127">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="fcc15-127">E_OUTOFMEMORY</span></span>|<span data-ttu-id="fcc15-128">Не удалось выделить достаточно памяти для размещения списка задач, связанных с этим соединением.</span><span class="sxs-lookup"><span data-stu-id="fcc15-128">Not enough memory could be allocated to hold the list of tasks associated with this connection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fcc15-129">Примечания</span><span class="sxs-lookup"><span data-stu-id="fcc15-129">Remarks</span></span>  
 <span data-ttu-id="fcc15-130">[ICLRDebugManager](iclrdebugmanager-interface.md) предоставляет три метода, `BeginConnection` , [SetConnectionTasks](iclrdebugmanager-setconnectiontasks-method.md)и [ендконнектион](iclrdebugmanager-endconnection-method.md)для связывания списков задач с идентификаторами и понятными именами.</span><span class="sxs-lookup"><span data-stu-id="fcc15-130">[ICLRDebugManager](iclrdebugmanager-interface.md) provides three methods, `BeginConnection`, [SetConnectionTasks](iclrdebugmanager-setconnectiontasks-method.md), and [EndConnection](iclrdebugmanager-endconnection-method.md), for associating task lists with identifiers and friendly names.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="fcc15-131">Эти три метода должны вызываться в определенном порядке для каждого набора задач.</span><span class="sxs-lookup"><span data-stu-id="fcc15-131">These three methods must be called in a specific order for each set of tasks.</span></span> <span data-ttu-id="fcc15-132">`BeginConnection`вызывается первым для установления нового соединения.</span><span class="sxs-lookup"><span data-stu-id="fcc15-132">`BeginConnection` is called first to establish a new connection.</span></span> <span data-ttu-id="fcc15-133">`SetConnectionTasks`вызывается далее для предоставления набора задач, которые должны быть связаны с этим соединением.</span><span class="sxs-lookup"><span data-stu-id="fcc15-133">`SetConnectionTasks` is called next to provide the set of tasks to be associated with that connection.</span></span> <span data-ttu-id="fcc15-134">`EndConnection`вызывается последним, чтобы удалить связь между списком задач и идентификатором и понятным именем. Однако вызовы для различных соединений могут быть вложенными.</span><span class="sxs-lookup"><span data-stu-id="fcc15-134">`EndConnection` is called last to remove the association between the task list and the identifier and friendly name.However, calls for different connections can be nested.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fcc15-135">Требования</span><span class="sxs-lookup"><span data-stu-id="fcc15-135">Requirements</span></span>  
 <span data-ttu-id="fcc15-136">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fcc15-136">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fcc15-137">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="fcc15-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fcc15-138">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="fcc15-138">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fcc15-139">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fcc15-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcc15-140">См. также</span><span class="sxs-lookup"><span data-stu-id="fcc15-140">See also</span></span>

- [<span data-ttu-id="fcc15-141">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="fcc15-141">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="fcc15-142">Интерфейс ICLRDebugManager</span><span class="sxs-lookup"><span data-stu-id="fcc15-142">ICLRDebugManager Interface</span></span>](iclrdebugmanager-interface.md)
- [<span data-ttu-id="fcc15-143">Метод EndConnection</span><span class="sxs-lookup"><span data-stu-id="fcc15-143">EndConnection Method</span></span>](iclrdebugmanager-endconnection-method.md)
- [<span data-ttu-id="fcc15-144">Метод SetConnectionTasks</span><span class="sxs-lookup"><span data-stu-id="fcc15-144">SetConnectionTasks Method</span></span>](iclrdebugmanager-setconnectiontasks-method.md)
- [<span data-ttu-id="fcc15-145">Интерфейс IHostControl</span><span class="sxs-lookup"><span data-stu-id="fcc15-145">IHostControl Interface</span></span>](ihostcontrol-interface.md)
