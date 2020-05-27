---
title: Метод IHostSemaphore::ReleaseSemaphore
ms.date: 03/30/2017
api_name:
- IHostSemaphore.ReleaseSemaphore
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSemaphore::ReleaseSemaphore
helpviewer_keywords:
- ReleaseSemaphore method [.NET Framework hosting]
- IHostSemaphore::ReleaseSemaphore method [.NET Framework hosting]
ms.assetid: a343d197-979a-4ac6-ab8c-cb8a05f3120e
topic_type:
- apiref
ms.openlocfilehash: aa67aabbe8a7a47a9b3036f508e2f8bb6082c3e0
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/22/2020
ms.locfileid: "83803558"
---
# <a name="ihostsemaphorereleasesemaphore-method"></a><span data-ttu-id="d9792-102">Метод IHostSemaphore::ReleaseSemaphore</span><span class="sxs-lookup"><span data-stu-id="d9792-102">IHostSemaphore::ReleaseSemaphore Method</span></span>
<span data-ttu-id="d9792-103">Увеличивает количество текущего экземпляра [IHostSemaphore](ihostsemaphore-interface.md) на указанный объем.</span><span class="sxs-lookup"><span data-stu-id="d9792-103">Increases the count of the current [IHostSemaphore](ihostsemaphore-interface.md) instance by the specified amount.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9792-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d9792-104">Syntax</span></span>  
  
```cpp  
HRESULT ReleaseSemaphore (  
    [in]  LONG  lReleaseCount,  
    [out] LONG  *lpPreviousCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d9792-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d9792-105">Parameters</span></span>  
 `lReleaseCount`  
 <span data-ttu-id="d9792-106">окне Величина, на которую увеличивается количество текущего `IHostSemaphore` экземпляра.</span><span class="sxs-lookup"><span data-stu-id="d9792-106">[in] The amount by which to increase the count of the current `IHostSemaphore` instance.</span></span> <span data-ttu-id="d9792-107">Это значение должно быть больше нуля.</span><span class="sxs-lookup"><span data-stu-id="d9792-107">This amount must be greater than zero.</span></span>  
  
 `lpPreviousCount`  
 <span data-ttu-id="d9792-108">заполняет Указатель на предыдущее число или значение null, если для вызывающего объекта не требуется предыдущее число.</span><span class="sxs-lookup"><span data-stu-id="d9792-108">[out] A pointer to the previous count, or null if the caller does not require the previous count.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d9792-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d9792-109">Return Value</span></span>  
  
|<span data-ttu-id="d9792-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d9792-110">HRESULT</span></span>|<span data-ttu-id="d9792-111">Описание</span><span class="sxs-lookup"><span data-stu-id="d9792-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d9792-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="d9792-112">S_OK</span></span>|<span data-ttu-id="d9792-113">`ReleaseSemaphore`успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="d9792-113">`ReleaseSemaphore` returned successfully.</span></span>|  
|<span data-ttu-id="d9792-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d9792-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d9792-115">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="d9792-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d9792-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d9792-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d9792-117">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="d9792-117">The call timed out.</span></span>|  
|<span data-ttu-id="d9792-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d9792-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d9792-119">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="d9792-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d9792-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d9792-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d9792-121">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="d9792-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d9792-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d9792-122">E_FAIL</span></span>|<span data-ttu-id="d9792-123">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="d9792-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d9792-124">Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="d9792-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d9792-125">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="d9792-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d9792-126">Замечания</span><span class="sxs-lookup"><span data-stu-id="d9792-126">Remarks</span></span>  
 <span data-ttu-id="d9792-127">Среда CLR обычно вызывает `ReleaseSemaphore` для уведомления узла о завершении работы с ресурсом, передавая значение 1 для `lReleaseCount` параметра.</span><span class="sxs-lookup"><span data-stu-id="d9792-127">The CLR typically calls `ReleaseSemaphore` to notify the host that it has finished using a resource, passing a value of 1 for the `lReleaseCount` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9792-128">Требования</span><span class="sxs-lookup"><span data-stu-id="d9792-128">Requirements</span></span>  
 <span data-ttu-id="d9792-129">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d9792-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9792-130">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="d9792-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d9792-131">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="d9792-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d9792-132">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d9792-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9792-133">См. также статью</span><span class="sxs-lookup"><span data-stu-id="d9792-133">See also</span></span>

- [<span data-ttu-id="d9792-134">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="d9792-134">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="d9792-135">Интерфейс IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="d9792-135">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="d9792-136">Интерфейс IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="d9792-136">IHostManualEvent Interface</span></span>](ihostmanualevent-interface.md)
- [<span data-ttu-id="d9792-137">Интерфейс IHostSemaphore</span><span class="sxs-lookup"><span data-stu-id="d9792-137">IHostSemaphore Interface</span></span>](ihostsemaphore-interface.md)
- [<span data-ttu-id="d9792-138">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="d9792-138">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
