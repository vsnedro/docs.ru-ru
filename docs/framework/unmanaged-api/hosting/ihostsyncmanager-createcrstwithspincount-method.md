---
title: Метод IHostSyncManager::CreateCrstWithSpinCount
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateCrstWithSpinCount
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateCrstWithSpinCount
helpviewer_keywords:
- CreateCrstWithSpinCount method [.NET Framework hosting]
- IHostSyncManager::CreateCrstWithSpinCount method [.NET Framework hosting]
ms.assetid: 7280fa8c-3639-4abf-91cb-bc343da742d1
topic_type:
- apiref
ms.openlocfilehash: 86bc320c28a5fbf122d234a4a1f15b674628c0b5
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/22/2020
ms.locfileid: "83803398"
---
# <a name="ihostsyncmanagercreatecrstwithspincount-method"></a><span data-ttu-id="f5e67-102">Метод IHostSyncManager::CreateCrstWithSpinCount</span><span class="sxs-lookup"><span data-stu-id="f5e67-102">IHostSyncManager::CreateCrstWithSpinCount Method</span></span>
<span data-ttu-id="f5e67-103">Создает объект критической секции с количеством счетчиков для синхронизации.</span><span class="sxs-lookup"><span data-stu-id="f5e67-103">Creates a critical section object with spin count for synchronization.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5e67-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f5e67-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateCrstWithSpinCount (  
    [in]  DWORD dwSpinCount,  
    [out] IHostCrst** ppCrst  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f5e67-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f5e67-105">Parameters</span></span>  
 `dwSpinCount`  
 <span data-ttu-id="f5e67-106">окне Указывает счетчик счетчиков для объекта критической секции.</span><span class="sxs-lookup"><span data-stu-id="f5e67-106">[in] Specifies the spin count for the critical section object.</span></span>  
  
 `ppCrst`  
 <span data-ttu-id="f5e67-107">заполняет Указатель на адрес экземпляра [IHostCrst](ihostcrst-interface.md) или значение null, если не удалось создать критическую секцию.</span><span class="sxs-lookup"><span data-stu-id="f5e67-107">[out] A pointer to the address of an [IHostCrst](ihostcrst-interface.md) instance, or null if the critical section could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f5e67-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f5e67-108">Return Value</span></span>  
  
|<span data-ttu-id="f5e67-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f5e67-109">HRESULT</span></span>|<span data-ttu-id="f5e67-110">Описание</span><span class="sxs-lookup"><span data-stu-id="f5e67-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f5e67-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="f5e67-111">S_OK</span></span>|<span data-ttu-id="f5e67-112">`CreateCrstWithSpinCount`успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="f5e67-112">`CreateCrstWithSpinCount` returned successfully.</span></span>|  
|<span data-ttu-id="f5e67-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f5e67-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f5e67-114">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="f5e67-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f5e67-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f5e67-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f5e67-116">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="f5e67-116">The call timed out.</span></span>|  
|<span data-ttu-id="f5e67-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f5e67-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f5e67-118">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="f5e67-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f5e67-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f5e67-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f5e67-120">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="f5e67-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f5e67-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f5e67-121">E_FAIL</span></span>|<span data-ttu-id="f5e67-122">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="f5e67-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f5e67-123">Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="f5e67-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f5e67-124">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="f5e67-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="f5e67-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="f5e67-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="f5e67-126">Недостаточно свободной памяти для создания запрошенной критической секции.</span><span class="sxs-lookup"><span data-stu-id="f5e67-126">Not enough memory was available to create the requested critical section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f5e67-127">Замечания</span><span class="sxs-lookup"><span data-stu-id="f5e67-127">Remarks</span></span>  
 <span data-ttu-id="f5e67-128">Счетчик прокрутки используется только в многопроцессорной системе.</span><span class="sxs-lookup"><span data-stu-id="f5e67-128">A spin count is used only on a multi-processor system.</span></span> <span data-ttu-id="f5e67-129">Число счетчиков указывает, сколько раз вызывающий поток должен прокрутить перед выполнением операции ожидания семафора, связанного с недоступным критическим разделом.</span><span class="sxs-lookup"><span data-stu-id="f5e67-129">The spin count specifies the number of times a calling thread must spin before it performs a wait operation on a semaphore that is associated with an unavailable critical section.</span></span> <span data-ttu-id="f5e67-130">Если критическая секция будет свободна во время операции Spin, вызывающий поток не будет выполнять операцию ожидания.</span><span class="sxs-lookup"><span data-stu-id="f5e67-130">If the critical section becomes free during the spin operation, the calling thread avoids the wait operation.</span></span> <span data-ttu-id="f5e67-131">`CreateCrstWithSpinCount`отражает функцию Win32 `InitializeCriticalSectionAndSpinCount` .</span><span class="sxs-lookup"><span data-stu-id="f5e67-131">`CreateCrstWithSpinCount` mirrors the Win32 `InitializeCriticalSectionAndSpinCount` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5e67-132">Требования</span><span class="sxs-lookup"><span data-stu-id="f5e67-132">Requirements</span></span>  
 <span data-ttu-id="f5e67-133">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f5e67-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5e67-134">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="f5e67-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f5e67-135">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f5e67-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f5e67-136">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5e67-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5e67-137">См. также статью</span><span class="sxs-lookup"><span data-stu-id="f5e67-137">See also</span></span>

- [<span data-ttu-id="f5e67-138">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="f5e67-138">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="f5e67-139">Интерфейс IHostSemaphore</span><span class="sxs-lookup"><span data-stu-id="f5e67-139">IHostSemaphore Interface</span></span>](ihostsemaphore-interface.md)
- [<span data-ttu-id="f5e67-140">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="f5e67-140">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
