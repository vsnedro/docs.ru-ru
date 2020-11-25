---
title: Интерфейс IHostSyncManager
ms.date: 03/30/2017
api_name:
- IHostSyncManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager
helpviewer_keywords:
- IHostSyncManager interface [.NET Framework hosting]
ms.assetid: 2e081a37-6a28-4c93-b7ab-1c96a464637c
topic_type:
- apiref
ms.openlocfilehash: 8a5fc42191634a2e5a441baecc4b78212ffad687
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720501"
---
# <a name="ihostsyncmanager-interface"></a><span data-ttu-id="11732-102">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="11732-102">IHostSyncManager Interface</span></span>

<span data-ttu-id="11732-103">Предоставляет методы, позволяющие среде CLR создавать примитивы синхронизации путем вызова узла вместо использования функций синхронизации Win32.</span><span class="sxs-lookup"><span data-stu-id="11732-103">Provides methods that allow the common language runtime (CLR) to create synchronization primitives by calling the host instead of using the Win32 synchronization functions.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="11732-104">Методы</span><span class="sxs-lookup"><span data-stu-id="11732-104">Methods</span></span>  
  
|<span data-ttu-id="11732-105">Метод</span><span class="sxs-lookup"><span data-stu-id="11732-105">Method</span></span>|<span data-ttu-id="11732-106">Описание</span><span class="sxs-lookup"><span data-stu-id="11732-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="11732-107">Метод CreateAutoEvent</span><span class="sxs-lookup"><span data-stu-id="11732-107">CreateAutoEvent Method</span></span>](ihostsyncmanager-createautoevent-method.md)|<span data-ttu-id="11732-108">Создает объект события автоматического сброса.</span><span class="sxs-lookup"><span data-stu-id="11732-108">Creates an auto-reset event object.</span></span>|  
|[<span data-ttu-id="11732-109">Метод CreateCrst</span><span class="sxs-lookup"><span data-stu-id="11732-109">CreateCrst Method</span></span>](ihostsyncmanager-createcrst-method.md)|<span data-ttu-id="11732-110">Создает объект критической секции для синхронизации.</span><span class="sxs-lookup"><span data-stu-id="11732-110">Creates a critical section object for synchronization.</span></span>|  
|[<span data-ttu-id="11732-111">Метод CreateCrstWithSpinCount</span><span class="sxs-lookup"><span data-stu-id="11732-111">CreateCrstWithSpinCount Method</span></span>](ihostsyncmanager-createcrstwithspincount-method.md)|<span data-ttu-id="11732-112">Создает объект критической секции с количеством счетчиков для синхронизации.</span><span class="sxs-lookup"><span data-stu-id="11732-112">Creates a critical section object with spin count for synchronization.</span></span>|  
|[<span data-ttu-id="11732-113">Метод CreateManualEvent</span><span class="sxs-lookup"><span data-stu-id="11732-113">CreateManualEvent Method</span></span>](ihostsyncmanager-createmanualevent-method.md)|<span data-ttu-id="11732-114">Создает объект события ручного сброса.</span><span class="sxs-lookup"><span data-stu-id="11732-114">Creates a manual-reset event object.</span></span>|  
|[<span data-ttu-id="11732-115">Метод CreateMonitorEvent</span><span class="sxs-lookup"><span data-stu-id="11732-115">CreateMonitorEvent Method</span></span>](ihostsyncmanager-createmonitorevent-method.md)|<span data-ttu-id="11732-116">Создает Отслеживаемый объект события автоматического сброса.</span><span class="sxs-lookup"><span data-stu-id="11732-116">Creates a monitored auto-reset event object.</span></span>|  
|[<span data-ttu-id="11732-117">Метод CreateRWLockReaderEvent</span><span class="sxs-lookup"><span data-stu-id="11732-117">CreateRWLockReaderEvent Method</span></span>](ihostsyncmanager-createrwlockreaderevent-method.md)|<span data-ttu-id="11732-118">Создает объект события ручного сброса для реализации блокировки чтения.</span><span class="sxs-lookup"><span data-stu-id="11732-118">Creates a manual-reset event object for the implementation of a reader lock.</span></span>|  
|[<span data-ttu-id="11732-119">Метод CreateRWLockWriterEvent</span><span class="sxs-lookup"><span data-stu-id="11732-119">CreateRWLockWriterEvent Method</span></span>](ihostsyncmanager-createrwlockwriterevent-method.md)|<span data-ttu-id="11732-120">Создает объект события автоматического сброса для реализации блокировки модуля записи.</span><span class="sxs-lookup"><span data-stu-id="11732-120">Creates an auto-reset event object for the implementation of a writer lock.</span></span>|  
|[<span data-ttu-id="11732-121">Метод CreateSemaphore</span><span class="sxs-lookup"><span data-stu-id="11732-121">CreateSemaphore Method</span></span>](ihostsyncmanager-createsemaphore-method.md)|<span data-ttu-id="11732-122">Создает объект [IHostSemaphore](ihostsemaphore-interface.md) для среды CLR, который будет использоваться в качестве семафора для событий ожидания.</span><span class="sxs-lookup"><span data-stu-id="11732-122">Creates an [IHostSemaphore](ihostsemaphore-interface.md) object for the CLR to use as a semaphore for wait events.</span></span>|  
|[<span data-ttu-id="11732-123">Метод SetCLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="11732-123">SetCLRSyncManager Method</span></span>](ihostsyncmanager-setclrsyncmanager-method.md)|<span data-ttu-id="11732-124">Задает экземпляр [ICLRSyncManager](iclrsyncmanager-interface.md) , связываемый с текущим `IHostSyncManager` экземпляром.</span><span class="sxs-lookup"><span data-stu-id="11732-124">Sets the [ICLRSyncManager](iclrsyncmanager-interface.md) instance to associate with the current `IHostSyncManager` instance.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="11732-125">Комментарии</span><span class="sxs-lookup"><span data-stu-id="11732-125">Remarks</span></span>  

 <span data-ttu-id="11732-126">Среда CLR обнаруживает реализацию узла `IHostSyncManager` , вызывая метод [IHostControl:: жесостманажер](ihostcontrol-gethostmanager-method.md) с `IID` IID_IHostSyncManager.</span><span class="sxs-lookup"><span data-stu-id="11732-126">The CLR discovers the host's implementation of `IHostSyncManager` by calling the [IHostControl::GetHostManager](ihostcontrol-gethostmanager-method.md) method with an `IID` of IID_IHostSyncManager.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11732-127">Требования</span><span class="sxs-lookup"><span data-stu-id="11732-127">Requirements</span></span>  

 <span data-ttu-id="11732-128">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="11732-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11732-129">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="11732-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="11732-130">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="11732-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="11732-131">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11732-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11732-132">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="11732-132">See also</span></span>

- [<span data-ttu-id="11732-133">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="11732-133">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="11732-134">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="11732-134">Hosting Interfaces</span></span>](hosting-interfaces.md)
