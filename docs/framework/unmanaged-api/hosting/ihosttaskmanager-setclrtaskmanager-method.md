---
title: Метод IHostTaskManager::SetCLRTaskManager
ms.date: 03/30/2017
api_name:
- IHostTaskManager.SetCLRTaskManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::SetCLRTaskManager
helpviewer_keywords:
- IHostTaskManager::SetCLRTaskManager method [.NET Framework hosting]
- SetCLRTaskManager method [.NET Framework hosting]
ms.assetid: ec90ee83-bd4b-408b-9274-62a923ab86a1
topic_type:
- apiref
ms.openlocfilehash: 23d0679599c681468caa2507518d0ae3144ac26a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95669813"
---
# <a name="ihosttaskmanagersetclrtaskmanager-method"></a><span data-ttu-id="e49f6-102">Метод IHostTaskManager::SetCLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="e49f6-102">IHostTaskManager::SetCLRTaskManager Method</span></span>

<span data-ttu-id="e49f6-103">Предоставляет узлу указатель интерфейса на экземпляр [ICLRTaskManager](iclrtaskmanager-interface.md) , реализованный средой CLR.</span><span class="sxs-lookup"><span data-stu-id="e49f6-103">Provides the host with an interface pointer to an [ICLRTaskManager](iclrtaskmanager-interface.md) instance implemented by the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e49f6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e49f6-104">Syntax</span></span>  
  
```cpp  
HRESULT SetCLRTaskManager (  
    [in] ICLRTaskManager *pManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e49f6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e49f6-105">Parameters</span></span>  

 `pManager`  
 <span data-ttu-id="e49f6-106">окне Указатель на `ICLRTaskManager` экземпляр, реализованный средой CLR.</span><span class="sxs-lookup"><span data-stu-id="e49f6-106">[in] A pointer to an `ICLRTaskManager` instance implemented by the common language runtime.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e49f6-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e49f6-107">Return Value</span></span>  
  
|<span data-ttu-id="e49f6-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e49f6-108">HRESULT</span></span>|<span data-ttu-id="e49f6-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="e49f6-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e49f6-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="e49f6-110">S_OK</span></span>|<span data-ttu-id="e49f6-111">`SetCLRTaskManager` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="e49f6-111">`SetCLRTaskManager` returned successfully.</span></span>|  
|<span data-ttu-id="e49f6-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e49f6-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e49f6-113">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="e49f6-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e49f6-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e49f6-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e49f6-115">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="e49f6-115">The call timed out.</span></span>|  
|<span data-ttu-id="e49f6-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e49f6-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e49f6-117">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="e49f6-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e49f6-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e49f6-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e49f6-119">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="e49f6-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e49f6-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e49f6-120">E_FAIL</span></span>|<span data-ttu-id="e49f6-121">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="e49f6-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e49f6-122">Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="e49f6-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e49f6-123">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="e49f6-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e49f6-124">Комментарии</span><span class="sxs-lookup"><span data-stu-id="e49f6-124">Remarks</span></span>  

 <span data-ttu-id="e49f6-125">Среда выполнения вызывает метод `SetCLRTaskManager` , чтобы предоставить узлу указатель интерфейса на `ICLRTaskManager` экземпляр.</span><span class="sxs-lookup"><span data-stu-id="e49f6-125">The runtime calls `SetCLRTaskManager` to provide the host with an interface pointer to an `ICLRTaskManager` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e49f6-126">Требования</span><span class="sxs-lookup"><span data-stu-id="e49f6-126">Requirements</span></span>  

 <span data-ttu-id="e49f6-127">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e49f6-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e49f6-128">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="e49f6-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e49f6-129">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e49f6-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e49f6-130">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e49f6-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e49f6-131">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e49f6-131">See also</span></span>

- [<span data-ttu-id="e49f6-132">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="e49f6-132">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="e49f6-133">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="e49f6-133">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="e49f6-134">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="e49f6-134">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="e49f6-135">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="e49f6-135">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
