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
ms.openlocfilehash: db651e3fe51f90b84449874f2c60a12050b0350e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95687116"
---
# <a name="iclrsyncmanagerdeleterwlockowneriterator-method"></a><span data-ttu-id="3905a-102">Метод ICLRSyncManager::DeleteRWLockOwnerIterator</span><span class="sxs-lookup"><span data-stu-id="3905a-102">ICLRSyncManager::DeleteRWLockOwnerIterator Method</span></span>

<span data-ttu-id="3905a-103">Запрашивает уничтожение итератора, созданного с помощью вызова метода [ICLRSyncManager:: CreateRWLockOwnerIterator](iclrsyncmanager-createrwlockowneriterator-method.md), в среде CLR.</span><span class="sxs-lookup"><span data-stu-id="3905a-103">Requests that the common language runtime (CLR) destroy an iterator that was created by a call to [ICLRSyncManager::CreateRWLockOwnerIterator](iclrsyncmanager-createrwlockowneriterator-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3905a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3905a-104">Syntax</span></span>  
  
```cpp  
HRESULT DeleteRWLockOwnerIterator (  
    [in] SIZE_T  Iterator  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3905a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3905a-105">Parameters</span></span>  

 `Iterator`  
 <span data-ttu-id="3905a-106">окне Итератор, который был создан с помощью вызова `CreateRWLockOwnerIterator` .</span><span class="sxs-lookup"><span data-stu-id="3905a-106">[in] The iterator that was created by using a call to `CreateRWLockOwnerIterator`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3905a-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3905a-107">Return Value</span></span>  
  
|<span data-ttu-id="3905a-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3905a-108">HRESULT</span></span>|<span data-ttu-id="3905a-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="3905a-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3905a-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="3905a-110">S_OK</span></span>|<span data-ttu-id="3905a-111">`DeleteRWLockOwnerIterator` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="3905a-111">`DeleteRWLockOwnerIterator` returned successfully.</span></span>|  
|<span data-ttu-id="3905a-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3905a-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3905a-113">Среда CLR не была загружена в процесс или находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="3905a-113">The CLR has not been loaded into a process, or is in a state in which it cannot run managed code or successfully process the call.</span></span>|  
|<span data-ttu-id="3905a-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3905a-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3905a-115">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="3905a-115">The call timed out.</span></span>|  
|<span data-ttu-id="3905a-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3905a-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3905a-117">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="3905a-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3905a-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3905a-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3905a-119">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="3905a-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3905a-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3905a-120">E_FAIL</span></span>|<span data-ttu-id="3905a-121">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="3905a-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3905a-122">Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="3905a-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3905a-123">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="3905a-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3905a-124">Комментарии</span><span class="sxs-lookup"><span data-stu-id="3905a-124">Remarks</span></span>  

 <span data-ttu-id="3905a-125">Узел может вызвать этот метод и `CreateRWLockOwnerIterator` убедиться, что его реализация потоков остается синхронизированной.</span><span class="sxs-lookup"><span data-stu-id="3905a-125">The host can call this method and `CreateRWLockOwnerIterator` to ensure that its threading implementation remains synchronized.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3905a-126">Требования</span><span class="sxs-lookup"><span data-stu-id="3905a-126">Requirements</span></span>  

 <span data-ttu-id="3905a-127">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3905a-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3905a-128">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="3905a-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3905a-129">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3905a-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3905a-130">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3905a-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3905a-131">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="3905a-131">See also</span></span>

- [<span data-ttu-id="3905a-132">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="3905a-132">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="3905a-133">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="3905a-133">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
