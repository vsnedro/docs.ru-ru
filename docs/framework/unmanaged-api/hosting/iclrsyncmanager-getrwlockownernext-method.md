---
title: Метод ICLRSyncManager::GetRWLockOwnerNext
ms.date: 03/30/2017
api_name:
- ICLRSyncManager.GetRWLockOwnerNext
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRSyncManager::GetRWLockOwnerNext
helpviewer_keywords:
- ICLRSyncManager::GetRWLockOwnerNext method [.NET Framework hosting]
- GetRWLockOwnerNext method [.NET Framework hosting]
ms.assetid: 0e025b6a-280e-40a2-a2d0-b15f58777b81
topic_type:
- apiref
ms.openlocfilehash: e5a8f69e66bb4b6373aea2c753bff9351bff8128
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762491"
---
# <a name="iclrsyncmanagergetrwlockownernext-method"></a><span data-ttu-id="76ec7-102">Метод ICLRSyncManager::GetRWLockOwnerNext</span><span class="sxs-lookup"><span data-stu-id="76ec7-102">ICLRSyncManager::GetRWLockOwnerNext Method</span></span>
<span data-ttu-id="76ec7-103">Возвращает следующий экземпляр [IHostTask](ihosttask-interface.md) , заблокированный для текущей блокировки чтения и записи.</span><span class="sxs-lookup"><span data-stu-id="76ec7-103">Gets the next [IHostTask](ihosttask-interface.md) instance that is blocked on the current reader-writer lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76ec7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="76ec7-104">Syntax</span></span>  
  
```cpp
HRESULT GetRWLockOwnerNext (  
    [in] SIZE_T       Iterator,  
    [out] IHostTask  *ppOwnerHostTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="76ec7-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="76ec7-105">Parameters</span></span>  
 `Iterator`  
 <span data-ttu-id="76ec7-106">окне Итератор, который был создан с помощью вызова [CreateRWLockOwnerIterator](iclrsyncmanager-createrwlockowneriterator-method.md).</span><span class="sxs-lookup"><span data-stu-id="76ec7-106">[in] The iterator that was created by using a call to [CreateRWLockOwnerIterator](iclrsyncmanager-createrwlockowneriterator-method.md).</span></span>  
  
 `ppOwnerHostTask`  
 <span data-ttu-id="76ec7-107">заполняет Указатель на следующий объект `IHostTask` , ожидающий блокировки, или значение null, если ни одна из задач не ожидает выполнения.</span><span class="sxs-lookup"><span data-stu-id="76ec7-107">[out] A pointer to the next `IHostTask` that is waiting on the lock, or null if no task is waiting.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="76ec7-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="76ec7-108">Return Value</span></span>  
  
|<span data-ttu-id="76ec7-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="76ec7-109">HRESULT</span></span>|<span data-ttu-id="76ec7-110">Описание</span><span class="sxs-lookup"><span data-stu-id="76ec7-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="76ec7-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="76ec7-111">S_OK</span></span>|<span data-ttu-id="76ec7-112">`GetRWLockOwnerNext`успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="76ec7-112">`GetRWLockOwnerNext` returned successfully.</span></span>|  
|<span data-ttu-id="76ec7-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="76ec7-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="76ec7-114">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="76ec7-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="76ec7-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="76ec7-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="76ec7-116">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="76ec7-116">The call timed out.</span></span>|  
|<span data-ttu-id="76ec7-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="76ec7-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="76ec7-118">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="76ec7-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="76ec7-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="76ec7-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="76ec7-120">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="76ec7-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="76ec7-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="76ec7-121">E_FAIL</span></span>|<span data-ttu-id="76ec7-122">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="76ec7-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="76ec7-123">Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="76ec7-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="76ec7-124">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="76ec7-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="76ec7-125">Комментарии</span><span class="sxs-lookup"><span data-stu-id="76ec7-125">Remarks</span></span>  
 <span data-ttu-id="76ec7-126">Если параметр `ppOwnerHostTask` имеет значение null, итерация завершается и узел должен вызвать метод [DeleteRWLockOwnerIterator](iclrsyncmanager-deleterwlockowneriterator-method.md) .</span><span class="sxs-lookup"><span data-stu-id="76ec7-126">If `ppOwnerHostTask` is set to null, the iteration has terminated, and the host should call the [DeleteRWLockOwnerIterator](iclrsyncmanager-deleterwlockowneriterator-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="76ec7-127">Среда CLR вызывает метод в `AddRef` , `IHostTask` который `ppOwnerHostTask` указывает, чтобы предотвратить выход этой задачи, пока узел удерживает указатель.</span><span class="sxs-lookup"><span data-stu-id="76ec7-127">The CLR calls `AddRef` on the `IHostTask` to which `ppOwnerHostTask` points to prevent this task from exiting while the host holds the pointer.</span></span> <span data-ttu-id="76ec7-128">Узел должен вызвать `Release` , чтобы уменьшить число ссылок по завершении.</span><span class="sxs-lookup"><span data-stu-id="76ec7-128">The host must call `Release` to decrement the reference count when it is finished.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76ec7-129">Требования</span><span class="sxs-lookup"><span data-stu-id="76ec7-129">Requirements</span></span>  
 <span data-ttu-id="76ec7-130">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="76ec7-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="76ec7-131">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="76ec7-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="76ec7-132">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="76ec7-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="76ec7-133">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="76ec7-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76ec7-134">См. также</span><span class="sxs-lookup"><span data-stu-id="76ec7-134">See also</span></span>

- [<span data-ttu-id="76ec7-135">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="76ec7-135">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="76ec7-136">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="76ec7-136">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
