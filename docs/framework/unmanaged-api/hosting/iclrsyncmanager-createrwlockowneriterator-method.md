---
title: Метод ICLRSyncManager::CreateRWLockOwnerIterator
ms.date: 03/30/2017
api_name:
- ICLRSyncManager.CreateRWLockOwnerIterator
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRSyncManager::CreateRWLockOwnerIterator
helpviewer_keywords:
- ICLRSyncManager::CreateRWLockOwnerIterator method [.NET Framework hosting]
- CreateRWLockOwnerIterator method [.NET Framework hosting]
ms.assetid: b5535b87-9439-424e-b9b3-7d6fafb9819e
topic_type:
- apiref
ms.openlocfilehash: f8fde4905c41dffde90c6361b5a8cdffa15deb4a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503969"
---
# <a name="iclrsyncmanagercreaterwlockowneriterator-method"></a><span data-ttu-id="1d7e2-102">Метод ICLRSyncManager::CreateRWLockOwnerIterator</span><span class="sxs-lookup"><span data-stu-id="1d7e2-102">ICLRSyncManager::CreateRWLockOwnerIterator Method</span></span>
<span data-ttu-id="1d7e2-103">Запрашивает, что среда CLR создает итератор для узла, который будет использоваться для определения набора задач, ожидающих блокировки чтения и записи.</span><span class="sxs-lookup"><span data-stu-id="1d7e2-103">Requests that the common language runtime (CLR) create an iterator for the host to use to determine the set of tasks waiting on a reader-writer lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d7e2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1d7e2-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateRWLockOwnerIterator (  
    [in]  SIZE_T    cookie,  
    [out] SIZE_T   *pIterator  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1d7e2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1d7e2-105">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="1d7e2-106">окне Файл cookie, связанный с требуемой блокировкой чтения и записи.</span><span class="sxs-lookup"><span data-stu-id="1d7e2-106">[in] The cookie associated with the desired reader-writer lock.</span></span>  
  
 `pIterator`  
 <span data-ttu-id="1d7e2-107">заполняет Указатель на итератор, который может быть передан методам [жетрвлокковнернекст](iclrsyncmanager-getrwlockownernext-method.md) и [DeleteRWLockOwnerIterator](iclrsyncmanager-deleterwlockowneriterator-method.md) .</span><span class="sxs-lookup"><span data-stu-id="1d7e2-107">[out] A pointer to an iterator that can be passed to the [GetRWLockOwnerNext](iclrsyncmanager-getrwlockownernext-method.md) and [DeleteRWLockOwnerIterator](iclrsyncmanager-deleterwlockowneriterator-method.md) methods.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1d7e2-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="1d7e2-108">Return Value</span></span>  
  
|<span data-ttu-id="1d7e2-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1d7e2-109">HRESULT</span></span>|<span data-ttu-id="1d7e2-110">Описание</span><span class="sxs-lookup"><span data-stu-id="1d7e2-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1d7e2-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="1d7e2-111">S_OK</span></span>|<span data-ttu-id="1d7e2-112">`CreateRWLockOwnerIterator`успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="1d7e2-112">`CreateRWLockOwnerIterator` returned successfully.</span></span>|  
|<span data-ttu-id="1d7e2-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1d7e2-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1d7e2-114">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="1d7e2-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1d7e2-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1d7e2-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1d7e2-116">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="1d7e2-116">The call timed out.</span></span>|  
|<span data-ttu-id="1d7e2-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1d7e2-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1d7e2-118">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="1d7e2-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1d7e2-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1d7e2-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1d7e2-120">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="1d7e2-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1d7e2-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1d7e2-121">E_FAIL</span></span>|<span data-ttu-id="1d7e2-122">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="1d7e2-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1d7e2-123">Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="1d7e2-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1d7e2-124">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="1d7e2-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="1d7e2-125">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="1d7e2-125">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="1d7e2-126">`CreateRWLockOwnerIterator`был вызван в потоке, который в настоящий момент выполняет управляемый код.</span><span class="sxs-lookup"><span data-stu-id="1d7e2-126">`CreateRWLockOwnerIterator` was called on a thread that is currently running managed code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1d7e2-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="1d7e2-127">Remarks</span></span>  
 <span data-ttu-id="1d7e2-128">Узлы обычно вызывают `CreateRWLockOwnerIterator` методы, `DeleteRWLockOwnerIterator` и `GetRWLockOwnerNext` во время обнаружения взаимоблокировки.</span><span class="sxs-lookup"><span data-stu-id="1d7e2-128">Hosts typically call the `CreateRWLockOwnerIterator`, `DeleteRWLockOwnerIterator`, and `GetRWLockOwnerNext` methods during deadlock detection.</span></span> <span data-ttu-id="1d7e2-129">Узел отвечает за обеспечение допустимости блокировки чтения и записи, так как среда CLR не пытается сохранить блокировку чтения-записи в активном состоянии.</span><span class="sxs-lookup"><span data-stu-id="1d7e2-129">The host is responsible for ensuring that the reader-writer lock is still valid, because the CLR makes no attempt to keep the reader-writer lock alive.</span></span> <span data-ttu-id="1d7e2-130">Для обеспечения допустимости блокировки на узле доступны несколько стратегий.</span><span class="sxs-lookup"><span data-stu-id="1d7e2-130">Several strategies are available for the host to ensure the validity of the lock:</span></span>  
  
- <span data-ttu-id="1d7e2-131">Узел может блокировать вызовы освобождения для блокировки чтения-записи (например, [IHostSemaphore:: ReleaseSemaphore](ihostsemaphore-releasesemaphore-method.md)), гарантируя, что этот блок не вызывает взаимоблокировку.</span><span class="sxs-lookup"><span data-stu-id="1d7e2-131">The host can block release calls on the reader-writer lock (for example, [IHostSemaphore::ReleaseSemaphore](ihostsemaphore-releasesemaphore-method.md)) while ensuring that this block does not cause deadlock.</span></span>  
  
- <span data-ttu-id="1d7e2-132">Узел может блокировать выход из режима ожидания объекта события, связанного с блокировкой чтения и записи, еще раз гарантируя, что этот блок не вызывает взаимоблокировку.</span><span class="sxs-lookup"><span data-stu-id="1d7e2-132">The host can block the exit from waiting on the event object associated with the reader-writer lock, again ensuring that this block does not cause deadlock.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1d7e2-133">`CreateRWLockOwnerIterator`метод должен вызываться только для потоков, выполняющих в данный момент неуправляемый код.</span><span class="sxs-lookup"><span data-stu-id="1d7e2-133">`CreateRWLockOwnerIterator` must be called only on threads that are currently executing unmanaged code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d7e2-134">Требования</span><span class="sxs-lookup"><span data-stu-id="1d7e2-134">Requirements</span></span>  
 <span data-ttu-id="1d7e2-135">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1d7e2-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d7e2-136">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="1d7e2-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1d7e2-137">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="1d7e2-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1d7e2-138">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d7e2-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d7e2-139">См. также</span><span class="sxs-lookup"><span data-stu-id="1d7e2-139">See also</span></span>

- [<span data-ttu-id="1d7e2-140">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="1d7e2-140">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="1d7e2-141">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="1d7e2-141">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
