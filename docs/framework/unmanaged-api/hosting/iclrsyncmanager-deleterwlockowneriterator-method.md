---
title: Метод ICLRSyncManager::DeleteRWLockOwnerIterator
ms.date: 03/30/2017
api_name:
- ICLRSyncManager.DeleteRWLockOwnerIterator
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRSyncManager::DeleteRWLockOwnerIterator
helpviewer_keywords:
- ICLRSyncManager::DeleteRWLockOwnerIterator method [.NET Framework hosting]
- DeleteRWLockOwnerIterator method [.NET Framework hosting]
ms.assetid: fcfd340a-b7d6-44e4-8167-2c05b789d483
topic_type:
- apiref
ms.openlocfilehash: a4094a64d27072ce257341398bb49419bef9b8bb
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/21/2020
ms.locfileid: "83763154"
---
# <a name="iclrsyncmanagerdeleterwlockowneriterator-method"></a><span data-ttu-id="f0a9d-102">Метод ICLRSyncManager::DeleteRWLockOwnerIterator</span><span class="sxs-lookup"><span data-stu-id="f0a9d-102">ICLRSyncManager::DeleteRWLockOwnerIterator Method</span></span>
<span data-ttu-id="f0a9d-103">Запрашивает уничтожение итератора, созданного с помощью вызова метода [ICLRSyncManager:: CreateRWLockOwnerIterator](iclrsyncmanager-createrwlockowneriterator-method.md), в среде CLR.</span><span class="sxs-lookup"><span data-stu-id="f0a9d-103">Requests that the common language runtime (CLR) destroy an iterator that was created by a call to [ICLRSyncManager::CreateRWLockOwnerIterator](iclrsyncmanager-createrwlockowneriterator-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0a9d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f0a9d-104">Syntax</span></span>  
  
```cpp  
HRESULT DeleteRWLockOwnerIterator (  
    [in] SIZE_T  Iterator  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f0a9d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f0a9d-105">Parameters</span></span>  
 `Iterator`  
 <span data-ttu-id="f0a9d-106">окне Итератор, который был создан с помощью вызова `CreateRWLockOwnerIterator` .</span><span class="sxs-lookup"><span data-stu-id="f0a9d-106">[in] The iterator that was created by using a call to `CreateRWLockOwnerIterator`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f0a9d-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f0a9d-107">Return Value</span></span>  
  
|<span data-ttu-id="f0a9d-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f0a9d-108">HRESULT</span></span>|<span data-ttu-id="f0a9d-109">Описание</span><span class="sxs-lookup"><span data-stu-id="f0a9d-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f0a9d-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="f0a9d-110">S_OK</span></span>|<span data-ttu-id="f0a9d-111">`DeleteRWLockOwnerIterator`успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="f0a9d-111">`DeleteRWLockOwnerIterator` returned successfully.</span></span>|  
|<span data-ttu-id="f0a9d-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f0a9d-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f0a9d-113">Среда CLR не была загружена в процесс или находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="f0a9d-113">The CLR has not been loaded into a process, or is in a state in which it cannot run managed code or successfully process the call.</span></span>|  
|<span data-ttu-id="f0a9d-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f0a9d-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f0a9d-115">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="f0a9d-115">The call timed out.</span></span>|  
|<span data-ttu-id="f0a9d-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f0a9d-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f0a9d-117">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="f0a9d-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f0a9d-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f0a9d-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f0a9d-119">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="f0a9d-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f0a9d-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f0a9d-120">E_FAIL</span></span>|<span data-ttu-id="f0a9d-121">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="f0a9d-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f0a9d-122">Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="f0a9d-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f0a9d-123">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="f0a9d-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f0a9d-124">Комментарии</span><span class="sxs-lookup"><span data-stu-id="f0a9d-124">Remarks</span></span>  
 <span data-ttu-id="f0a9d-125">Узел может вызвать этот метод и `CreateRWLockOwnerIterator` убедиться, что его реализация потоков остается синхронизированной.</span><span class="sxs-lookup"><span data-stu-id="f0a9d-125">The host can call this method and `CreateRWLockOwnerIterator` to ensure that its threading implementation remains synchronized.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0a9d-126">Требования</span><span class="sxs-lookup"><span data-stu-id="f0a9d-126">Requirements</span></span>  
 <span data-ttu-id="f0a9d-127">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f0a9d-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0a9d-128">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="f0a9d-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f0a9d-129">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f0a9d-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f0a9d-130">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0a9d-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0a9d-131">См. также</span><span class="sxs-lookup"><span data-stu-id="f0a9d-131">See also</span></span>

- [<span data-ttu-id="f0a9d-132">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="f0a9d-132">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="f0a9d-133">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="f0a9d-133">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
