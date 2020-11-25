---
title: Метод IHostTask::SetCLRTask
ms.date: 03/30/2017
api_name:
- IHostTask.SetCLRTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::SetCLRTask
helpviewer_keywords:
- SetCLRTask method [.NET Framework hosting]
- IHostTask::SetCLRTask method [.NET Framework hosting]
ms.assetid: e9d39c80-41a1-49e7-bb5e-ea3433bfb5d7
topic_type:
- apiref
ms.openlocfilehash: e6b9a4015a6139d6c8d7101fa7811c7ad9134e4c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720468"
---
# <a name="ihosttasksetclrtask-method"></a><span data-ttu-id="9b7bb-102">Метод IHostTask::SetCLRTask</span><span class="sxs-lookup"><span data-stu-id="9b7bb-102">IHostTask::SetCLRTask Method</span></span>

<span data-ttu-id="9b7bb-103">Связывает `ICLRTask` экземпляр с текущим экземпляром [IHostTask](ihosttask-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="9b7bb-103">Associates an `ICLRTask` instance with the current [IHostTask](ihosttask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b7bb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9b7bb-104">Syntax</span></span>  
  
```cpp  
HRESULT SetCLRTask (  
    [in] ICLRTask *pCLRTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9b7bb-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9b7bb-105">Parameters</span></span>  

 `pCLRTask`  
 <span data-ttu-id="9b7bb-106">окне Указатель интерфейса на экземпляр, `ICLRTask` который должен быть связан с текущим `IHostTask` экземпляром.</span><span class="sxs-lookup"><span data-stu-id="9b7bb-106">[in] An interface pointer to the `ICLRTask` instance to be associated with the current `IHostTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9b7bb-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="9b7bb-107">Return Value</span></span>  
  
|<span data-ttu-id="9b7bb-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9b7bb-108">HRESULT</span></span>|<span data-ttu-id="9b7bb-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="9b7bb-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9b7bb-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="9b7bb-110">S_OK</span></span>|<span data-ttu-id="9b7bb-111">`SetCLRTask` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="9b7bb-111">`SetCLRTask` returned successfully.</span></span>|  
|<span data-ttu-id="9b7bb-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9b7bb-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9b7bb-113">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="9b7bb-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9b7bb-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9b7bb-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9b7bb-115">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="9b7bb-115">The call timed out.</span></span>|  
|<span data-ttu-id="9b7bb-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9b7bb-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9b7bb-117">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="9b7bb-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9b7bb-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9b7bb-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9b7bb-119">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="9b7bb-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9b7bb-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9b7bb-120">E_FAIL</span></span>|<span data-ttu-id="9b7bb-121">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="9b7bb-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9b7bb-122">Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="9b7bb-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9b7bb-123">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="9b7bb-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9b7bb-124">Комментарии</span><span class="sxs-lookup"><span data-stu-id="9b7bb-124">Remarks</span></span>  

 <span data-ttu-id="9b7bb-125">Среда CLR вызывает метод `SetCLRTask` , чтобы связать `ICLRTask` экземпляр с текущим `IHostTask` экземпляром, который был создан с помощью вызова [IHostTaskManager:: CreateTask](ihosttaskmanager-createtask-method.md).</span><span class="sxs-lookup"><span data-stu-id="9b7bb-125">The CLR calls `SetCLRTask` to associate an `ICLRTask` instance with the current `IHostTask` instance, which was created by a call to [IHostTaskManager::CreateTask](ihosttaskmanager-createtask-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b7bb-126">Требования</span><span class="sxs-lookup"><span data-stu-id="9b7bb-126">Requirements</span></span>  

 <span data-ttu-id="9b7bb-127">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9b7bb-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b7bb-128">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="9b7bb-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9b7bb-129">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9b7bb-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9b7bb-130">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b7bb-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b7bb-131">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="9b7bb-131">See also</span></span>

- [<span data-ttu-id="9b7bb-132">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="9b7bb-132">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="9b7bb-133">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="9b7bb-133">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="9b7bb-134">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="9b7bb-134">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="9b7bb-135">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="9b7bb-135">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
