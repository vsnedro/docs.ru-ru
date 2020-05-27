---
title: Метод IHostSyncManager::CreateSemaphore
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateSemaphore
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateSemaphore
helpviewer_keywords:
- CreateSemaphore method [.NET Framework hosting]
- IHostSyncManager::CreateSemaphore method [.NET Framework hosting]
ms.assetid: 37679e94-5ff9-4173-8fa5-457febeb89bf
topic_type:
- apiref
ms.openlocfilehash: 680280e959d523356b95a5a4d9390c80720c0330
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/22/2020
ms.locfileid: "83803138"
---
# <a name="ihostsyncmanagercreatesemaphore-method"></a><span data-ttu-id="a6ddb-102">Метод IHostSyncManager::CreateSemaphore</span><span class="sxs-lookup"><span data-stu-id="a6ddb-102">IHostSyncManager::CreateSemaphore Method</span></span>
<span data-ttu-id="a6ddb-103">Создает объект [IHostSemaphore](ihostsemaphore-interface.md) для общеязыковой среды выполнения (CLR) для использования в качестве семафора для событий ожидания.</span><span class="sxs-lookup"><span data-stu-id="a6ddb-103">Creates an [IHostSemaphore](ihostsemaphore-interface.md) object for the common language runtime (CLR) to use as a semaphore for wait events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6ddb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a6ddb-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateSemaphore (  
    [in]  DWORD dwInitial,  
    [in]  DWORD dwMax,  
    [out] IHostSemaphore **ppSemaphore  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a6ddb-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a6ddb-105">Parameters</span></span>  
 `dwInitial`  
 <span data-ttu-id="a6ddb-106">окне Начальное число для `ppSemaphore` .</span><span class="sxs-lookup"><span data-stu-id="a6ddb-106">[in] The initial count for `ppSemaphore`.</span></span>  
  
 `dwMax`  
 <span data-ttu-id="a6ddb-107">окне Максимальное число для `ppSemaphore` .</span><span class="sxs-lookup"><span data-stu-id="a6ddb-107">[in] The maximum count for `ppSemaphore`.</span></span>  
  
 `ppSemaphore`  
 <span data-ttu-id="a6ddb-108">заполняет Указатель на адрес `IHostSemaphore` экземпляра или значение null, если не удалось создать семафор.</span><span class="sxs-lookup"><span data-stu-id="a6ddb-108">[out] A pointer to the address of an `IHostSemaphore` instance, or null if the semaphore could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a6ddb-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a6ddb-109">Return Value</span></span>  
  
|<span data-ttu-id="a6ddb-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a6ddb-110">HRESULT</span></span>|<span data-ttu-id="a6ddb-111">Описание</span><span class="sxs-lookup"><span data-stu-id="a6ddb-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a6ddb-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="a6ddb-112">S_OK</span></span>|<span data-ttu-id="a6ddb-113">`CreateSemaphore`успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="a6ddb-113">`CreateSemaphore` returned successfully.</span></span>|  
|<span data-ttu-id="a6ddb-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a6ddb-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a6ddb-115">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="a6ddb-115">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a6ddb-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a6ddb-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a6ddb-117">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="a6ddb-117">The call timed out.</span></span>|  
|<span data-ttu-id="a6ddb-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a6ddb-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a6ddb-119">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="a6ddb-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a6ddb-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a6ddb-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a6ddb-121">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="a6ddb-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a6ddb-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a6ddb-122">E_FAIL</span></span>|<span data-ttu-id="a6ddb-123">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="a6ddb-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a6ddb-124">Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="a6ddb-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a6ddb-125">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="a6ddb-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="a6ddb-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="a6ddb-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="a6ddb-127">Недостаточно свободной памяти для создания запрошенного объекта события.</span><span class="sxs-lookup"><span data-stu-id="a6ddb-127">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a6ddb-128">Замечания</span><span class="sxs-lookup"><span data-stu-id="a6ddb-128">Remarks</span></span>  
 <span data-ttu-id="a6ddb-129">`CreateSemaphore`отражает функцию Win32 с тем же именем.</span><span class="sxs-lookup"><span data-stu-id="a6ddb-129">`CreateSemaphore` mirrors the Win32 function that has the same name.</span></span> <span data-ttu-id="a6ddb-130">`dwInitial`Параметры и `dwMax` используют ту же семантику для счетчика семафора `lInitialCount` , что и Win32 и `lMaximumCount` параметры соответственно.</span><span class="sxs-lookup"><span data-stu-id="a6ddb-130">The `dwInitial` and `dwMax` parameters use the same semantics for the semaphore count as the Win32 `lInitialCount` and `lMaximumCount` parameters, respectively.</span></span> <span data-ttu-id="a6ddb-131">`dwInitial`значение должно находиться в диапазоне от 0 до `dwMax` включительно.</span><span class="sxs-lookup"><span data-stu-id="a6ddb-131">`dwInitial` must be between zero and `dwMax`, inclusive.</span></span> <span data-ttu-id="a6ddb-132">`dwMax`должно быть больше нуля.</span><span class="sxs-lookup"><span data-stu-id="a6ddb-132">`dwMax` must be greater than zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a6ddb-133">Требования</span><span class="sxs-lookup"><span data-stu-id="a6ddb-133">Requirements</span></span>  
 <span data-ttu-id="a6ddb-134">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a6ddb-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6ddb-135">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="a6ddb-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a6ddb-136">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="a6ddb-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a6ddb-137">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6ddb-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6ddb-138">См. также статью</span><span class="sxs-lookup"><span data-stu-id="a6ddb-138">See also</span></span>

- [<span data-ttu-id="a6ddb-139">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="a6ddb-139">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="a6ddb-140">Интерфейс IHostSemaphore</span><span class="sxs-lookup"><span data-stu-id="a6ddb-140">IHostSemaphore Interface</span></span>](ihostsemaphore-interface.md)
- [<span data-ttu-id="a6ddb-141">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="a6ddb-141">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
