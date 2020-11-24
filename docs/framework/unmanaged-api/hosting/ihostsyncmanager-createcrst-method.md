---
title: Метод IHostSyncManager::CreateCrst
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateCrst
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateCrst
helpviewer_keywords:
- CreateCrst method [.NET Framework hosting]
- IHostSyncManager::CreateCrst method [.NET Framework hosting]
ms.assetid: ac278cc8-2540-4a6c-b5c6-b90c3970b4f4
topic_type:
- apiref
ms.openlocfilehash: 27861a9258916f4c188d981c44833e5be4c507f2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95682888"
---
# <a name="ihostsyncmanagercreatecrst-method"></a><span data-ttu-id="da541-102">Метод IHostSyncManager::CreateCrst</span><span class="sxs-lookup"><span data-stu-id="da541-102">IHostSyncManager::CreateCrst Method</span></span>

<span data-ttu-id="da541-103">Создает объект критической секции для синхронизации.</span><span class="sxs-lookup"><span data-stu-id="da541-103">Creates a critical section object for synchronization.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da541-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="da541-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateCrst (  
    [out] IHostCrst** ppCrst  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="da541-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="da541-105">Parameters</span></span>  

 `ppCrst`  
 <span data-ttu-id="da541-106">заполняет Указатель на адрес экземпляра [IHostCrst](ihostcrst-interface.md) , реализуемого узлом, или значение null, если не удалось создать критический раздел.</span><span class="sxs-lookup"><span data-stu-id="da541-106">[out] A pointer to the address of an [IHostCrst](ihostcrst-interface.md) instance implemented by the host, or null if the critical section could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="da541-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="da541-107">Return Value</span></span>  
  
|<span data-ttu-id="da541-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="da541-108">HRESULT</span></span>|<span data-ttu-id="da541-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="da541-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="da541-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="da541-110">S_OK</span></span>|<span data-ttu-id="da541-111">`CreateCrst` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="da541-111">`CreateCrst` returned successfully.</span></span>|  
|<span data-ttu-id="da541-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="da541-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="da541-113">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="da541-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="da541-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="da541-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="da541-115">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="da541-115">The call timed out.</span></span>|  
|<span data-ttu-id="da541-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="da541-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="da541-117">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="da541-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="da541-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="da541-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="da541-119">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="da541-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="da541-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="da541-120">E_FAIL</span></span>|<span data-ttu-id="da541-121">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="da541-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="da541-122">Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="da541-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="da541-123">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="da541-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="da541-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="da541-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="da541-125">Недостаточно свободной памяти для создания запрошенной критической секции.</span><span class="sxs-lookup"><span data-stu-id="da541-125">Not enough memory was available to create the requested critical section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="da541-126">Комментарии</span><span class="sxs-lookup"><span data-stu-id="da541-126">Remarks</span></span>  

 <span data-ttu-id="da541-127">Объекты критических секций обеспечивают синхронизацию, аналогичную той, которая предоставляется объектом Mutex, за исключением того, что критические разделы могут использоваться только потоками одного процесса.</span><span class="sxs-lookup"><span data-stu-id="da541-127">Critical section objects provide synchronization similar to that provided by a mutex object, except that critical sections can be used only by the threads of a single process.</span></span> <span data-ttu-id="da541-128">`CreateCrst` отражает функцию Win32 `InitializeCriticalSection` .</span><span class="sxs-lookup"><span data-stu-id="da541-128">`CreateCrst` mirrors the Win32 `InitializeCriticalSection` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da541-129">Требования</span><span class="sxs-lookup"><span data-stu-id="da541-129">Requirements</span></span>  

 <span data-ttu-id="da541-130">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="da541-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da541-131">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="da541-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="da541-132">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="da541-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="da541-133">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da541-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da541-134">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="da541-134">See also</span></span>

- [<span data-ttu-id="da541-135">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="da541-135">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="da541-136">Интерфейс IHostCrst</span><span class="sxs-lookup"><span data-stu-id="da541-136">IHostCrst Interface</span></span>](ihostcrst-interface.md)
- [<span data-ttu-id="da541-137">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="da541-137">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
- [<span data-ttu-id="da541-138">Интерфейс IHostSemaphore</span><span class="sxs-lookup"><span data-stu-id="da541-138">IHostSemaphore Interface</span></span>](ihostsemaphore-interface.md)
- [<span data-ttu-id="da541-139">Мьютексы</span><span class="sxs-lookup"><span data-stu-id="da541-139">Mutexes</span></span>](../../../standard/threading/mutexes.md)
- [<span data-ttu-id="da541-140">Классы Semaphore и SemaphoreSlim</span><span class="sxs-lookup"><span data-stu-id="da541-140">Semaphore and SemaphoreSlim</span></span>](../../../standard/threading/semaphore-and-semaphoreslim.md)
