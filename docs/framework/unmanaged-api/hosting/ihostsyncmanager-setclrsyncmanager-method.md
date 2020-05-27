---
title: Метод IHostSyncManager::SetCLRSyncManager
ms.date: 03/30/2017
api_name:
- IHostSyncManager.SetCLRSyncManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::SetCLRSyncManager
helpviewer_keywords:
- IHostSyncManager::SetCLRSyncManager method [.NET Framework hosting]
- SetCLRSyncManager method [.NET Framework hosting]
ms.assetid: 2b8bbe76-a45d-4989-bacb-11df42f8798c
topic_type:
- apiref
ms.openlocfilehash: bbeae2561d2d340c1a7dfed38e740dcc6838e4da
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/22/2020
ms.locfileid: "83803099"
---
# <a name="ihostsyncmanagersetclrsyncmanager-method"></a><span data-ttu-id="1987c-102">Метод IHostSyncManager::SetCLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="1987c-102">IHostSyncManager::SetCLRSyncManager Method</span></span>
<span data-ttu-id="1987c-103">Задает экземпляр [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) , связываемый с текущим экземпляром [метод ihostsyncmanager](ihostsyncmanager-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="1987c-103">Sets the [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) instance to associate with the current [IHostSyncManager](ihostsyncmanager-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1987c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1987c-104">Syntax</span></span>  
  
```cpp  
HRESULT SetCLRSyncManager (  
    [in] ICLRSyncManager *pManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1987c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1987c-105">Parameters</span></span>  
 `pManager`  
 <span data-ttu-id="1987c-106">окне Указатель на `ICLRSyncManager` экземпляр, предоставленный средой CLR.</span><span class="sxs-lookup"><span data-stu-id="1987c-106">[in] A pointer to an `ICLRSyncManager` instance supplied by the common language runtime (CLR).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1987c-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="1987c-107">Return Value</span></span>  
  
|<span data-ttu-id="1987c-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1987c-108">HRESULT</span></span>|<span data-ttu-id="1987c-109">Описание</span><span class="sxs-lookup"><span data-stu-id="1987c-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1987c-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="1987c-110">S_OK</span></span>|<span data-ttu-id="1987c-111">`SetCLRSyncManager`успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="1987c-111">`SetCLRSyncManager` returned successfully.</span></span>|  
|<span data-ttu-id="1987c-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1987c-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1987c-113">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="1987c-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1987c-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1987c-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1987c-115">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="1987c-115">The call timed out.</span></span>|  
|<span data-ttu-id="1987c-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1987c-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1987c-117">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="1987c-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1987c-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1987c-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1987c-119">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="1987c-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1987c-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1987c-120">E_FAIL</span></span>|<span data-ttu-id="1987c-121">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="1987c-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1987c-122">Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="1987c-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1987c-123">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="1987c-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1987c-124">Замечания</span><span class="sxs-lookup"><span data-stu-id="1987c-124">Remarks</span></span>  
 <span data-ttu-id="1987c-125">Для упрощения обмена данными между узлом и средой CLR интерфейсы размещения обычно бывают парными.</span><span class="sxs-lookup"><span data-stu-id="1987c-125">To facilitate communication between the host and the CLR, hosting interfaces generally come in pairs.</span></span> <span data-ttu-id="1987c-126">Один член пары реализуется узлом, а другой — средой CLR.</span><span class="sxs-lookup"><span data-stu-id="1987c-126">One member of the pair is implemented by the host, and the other member is implemented by the CLR.</span></span> <span data-ttu-id="1987c-127">В качестве реализации на стороне узла `IHostSyncManager` интерфейс соответствует `ICLRSyncManager` интерфейсу, РЕАЛИЗОВАНному средой CLR.</span><span class="sxs-lookup"><span data-stu-id="1987c-127">As a host-side implementation, the `IHostSyncManager` interface corresponds to the `ICLRSyncManager` interface implemented by the CLR.</span></span> <span data-ttu-id="1987c-128">Среда CLR вызывает метод, `SetCLRSyncManager` чтобы предоставить `ICLRSyncManager` узлу экземпляр, связываемый с текущим `IHostSyncManager` экземпляром.</span><span class="sxs-lookup"><span data-stu-id="1987c-128">The CLR calls `SetCLRSyncManager` to supply an `ICLRSyncManager` instance for the host to associate with the current `IHostSyncManager` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1987c-129">Требования</span><span class="sxs-lookup"><span data-stu-id="1987c-129">Requirements</span></span>  
 <span data-ttu-id="1987c-130">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1987c-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1987c-131">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="1987c-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1987c-132">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="1987c-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1987c-133">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1987c-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1987c-134">См. также статью</span><span class="sxs-lookup"><span data-stu-id="1987c-134">See also</span></span>

- [<span data-ttu-id="1987c-135">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="1987c-135">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="1987c-136">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="1987c-136">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
