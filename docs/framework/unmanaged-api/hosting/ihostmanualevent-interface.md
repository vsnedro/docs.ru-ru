---
title: Интерфейс IHostManualEvent
ms.date: 03/30/2017
api_name:
- IHostManualEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostManualEvent
helpviewer_keywords:
- IHostManualEvent interface [.NET Framework hosting]
ms.assetid: 300c2661-b7d1-4c39-b080-9ebdef0fd523
topic_type:
- apiref
ms.openlocfilehash: 50e37b770e3ee6e0a5cdfca61fc5b09749e5735f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673208"
---
# <a name="ihostmanualevent-interface"></a><span data-ttu-id="a4acf-102">Интерфейс IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="a4acf-102">IHostManualEvent Interface</span></span>

<span data-ttu-id="a4acf-103">Предоставляет реализацию представления события ручного сброса в узле.</span><span class="sxs-lookup"><span data-stu-id="a4acf-103">Provides the host's implementation of a representation of a manual reset event.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a4acf-104">Методы</span><span class="sxs-lookup"><span data-stu-id="a4acf-104">Methods</span></span>  
  
|<span data-ttu-id="a4acf-105">Метод</span><span class="sxs-lookup"><span data-stu-id="a4acf-105">Method</span></span>|<span data-ttu-id="a4acf-106">Описание</span><span class="sxs-lookup"><span data-stu-id="a4acf-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a4acf-107">Метод Reset</span><span class="sxs-lookup"><span data-stu-id="a4acf-107">Reset Method</span></span>](ihostmanualevent-reset-method.md)|<span data-ttu-id="a4acf-108">Сбрасывает текущий `IHostManualEvent` экземпляр в несигнальное состояние.</span><span class="sxs-lookup"><span data-stu-id="a4acf-108">Resets the current `IHostManualEvent` instance to a non-signaled state.</span></span>|  
|[<span data-ttu-id="a4acf-109">Метод Set</span><span class="sxs-lookup"><span data-stu-id="a4acf-109">Set Method</span></span>](ihostmanualevent-set-method.md)|<span data-ttu-id="a4acf-110">Устанавливает для текущего `IHostManualEvent` экземпляра сигнальное состояние.</span><span class="sxs-lookup"><span data-stu-id="a4acf-110">Sets the current `IHostManualEvent` instance to a signaled state.</span></span>|  
|[<span data-ttu-id="a4acf-111">Метод Wait</span><span class="sxs-lookup"><span data-stu-id="a4acf-111">Wait Method</span></span>](ihostmanualevent-wait-method.md)|<span data-ttu-id="a4acf-112">Вызывает `IHostManualEvent` Ожидание текущего экземпляра до его признания или истечения указанного периода времени.</span><span class="sxs-lookup"><span data-stu-id="a4acf-112">Causes the current `IHostManualEvent` instance to wait until it is owned, or a specified amount of time elapses.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a4acf-113">Требования</span><span class="sxs-lookup"><span data-stu-id="a4acf-113">Requirements</span></span>  

 <span data-ttu-id="a4acf-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a4acf-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4acf-115">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="a4acf-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a4acf-116">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a4acf-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a4acf-117">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a4acf-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4acf-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="a4acf-118">See also</span></span>

- [<span data-ttu-id="a4acf-119">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="a4acf-119">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="a4acf-120">Интерфейс IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="a4acf-120">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="a4acf-121">Интерфейс IHostSemaphore</span><span class="sxs-lookup"><span data-stu-id="a4acf-121">IHostSemaphore Interface</span></span>](ihostsemaphore-interface.md)
- [<span data-ttu-id="a4acf-122">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="a4acf-122">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
- [<span data-ttu-id="a4acf-123">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="a4acf-123">Hosting Interfaces</span></span>](hosting-interfaces.md)
