---
title: Метод IHostSyncManager::CreateRWLockWriterEvent
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateRWLockWriterEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateRWLockWriterEvent
helpviewer_keywords:
- CreateRWLockWriterEvent method [.NET Framework hosting]
- IHostSyncManager::CreateRWLockWriterEvent method [.NET Framework hosting]
ms.assetid: 70e488c2-cf53-4dc0-ba52-74372d215c41
topic_type:
- apiref
ms.openlocfilehash: 5b5faf14337f78d9b176787528ae8947f5810ba6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95704374"
---
# <a name="ihostsyncmanagercreaterwlockwriterevent-method"></a><span data-ttu-id="b27db-102">Метод IHostSyncManager::CreateRWLockWriterEvent</span><span class="sxs-lookup"><span data-stu-id="b27db-102">IHostSyncManager::CreateRWLockWriterEvent Method</span></span>

<span data-ttu-id="b27db-103">Создает объект события автоматического сброса для реализации блокировки модуля записи.</span><span class="sxs-lookup"><span data-stu-id="b27db-103">Creates an auto-reset event object for the implementation of a writer lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b27db-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b27db-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateRWLockWriterEvent (  
    [in]  SIZE_T cookie,  
    [out] IHostAutoEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b27db-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b27db-105">Parameters</span></span>  

 `cookie`  
 <span data-ttu-id="b27db-106">окне Файл cookie, связываемый с событием автоматического сброса.</span><span class="sxs-lookup"><span data-stu-id="b27db-106">[in] A cookie to associate with the auto-reset event.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="b27db-107">заполняет Указатель на адрес экземпляра [ихостаутоевент](ihostautoevent-interface.md) или значение null, если не удалось создать объект события.</span><span class="sxs-lookup"><span data-stu-id="b27db-107">[out] A pointer to the address of an [IHostAutoEvent](ihostautoevent-interface.md) instance, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b27db-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b27db-108">Return Value</span></span>  
  
|<span data-ttu-id="b27db-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b27db-109">HRESULT</span></span>|<span data-ttu-id="b27db-110">Описание:</span><span class="sxs-lookup"><span data-stu-id="b27db-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b27db-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="b27db-111">S_OK</span></span>|<span data-ttu-id="b27db-112">`CreateRWLockWriterEvent` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="b27db-112">`CreateRWLockWriterEvent` returned successfully.</span></span>|  
|<span data-ttu-id="b27db-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b27db-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b27db-114">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="b27db-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b27db-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b27db-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b27db-116">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="b27db-116">The call timed out.</span></span>|  
|<span data-ttu-id="b27db-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b27db-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b27db-118">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="b27db-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b27db-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b27db-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b27db-120">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="b27db-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b27db-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b27db-121">E_FAIL</span></span>|<span data-ttu-id="b27db-122">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="b27db-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b27db-123">Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="b27db-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b27db-124">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="b27db-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="b27db-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="b27db-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="b27db-126">Недостаточно свободной памяти для создания запрошенного объекта события.</span><span class="sxs-lookup"><span data-stu-id="b27db-126">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b27db-127">Комментарии</span><span class="sxs-lookup"><span data-stu-id="b27db-127">Remarks</span></span>  

 <span data-ttu-id="b27db-128">Среда CLR вызывает `CreateRWLockWriterEvent` метод, чтобы получить ссылку на `IHostAutoEvent` экземпляр, используемый в реализации блокировки записи.</span><span class="sxs-lookup"><span data-stu-id="b27db-128">The CLR calls the `CreateRWLockWriterEvent` method to get a reference to an `IHostAutoEvent` instance to use in its implementation of a writer lock.</span></span> <span data-ttu-id="b27db-129">Узел может использовать указанный файл cookie, чтобы определить, какие задачи ожидают блокировки, вызвав методы итерации интерфейса [ICLRSyncManager](iclrsyncmanager-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="b27db-129">The host can use the specified cookie to determine which tasks are waiting on the lock by calling the iteration methods of the [ICLRSyncManager](iclrsyncmanager-interface.md) interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b27db-130">Требования</span><span class="sxs-lookup"><span data-stu-id="b27db-130">Requirements</span></span>  

 <span data-ttu-id="b27db-131">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b27db-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b27db-132">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="b27db-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b27db-133">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b27db-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b27db-134">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b27db-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b27db-135">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b27db-135">See also</span></span>

- [<span data-ttu-id="b27db-136">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="b27db-136">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="b27db-137">Интерфейс IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="b27db-137">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="b27db-138">Интерфейс IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="b27db-138">IHostManualEvent Interface</span></span>](ihostmanualevent-interface.md)
- [<span data-ttu-id="b27db-139">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="b27db-139">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
