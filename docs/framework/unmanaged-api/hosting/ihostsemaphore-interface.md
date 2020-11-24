---
title: Интерфейс IHostSemaphore
ms.date: 03/30/2017
api_name:
- IHostSemaphore
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSemaphore
helpviewer_keywords:
- IHostSemaphore interface [.NET Framework hosting]
ms.assetid: c0765321-656c-441e-bab5-58176292be1e
topic_type:
- apiref
ms.openlocfilehash: cccbf9a28b16ffee14b3fd3ec43c376109d6ccec
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683060"
---
# <a name="ihostsemaphore-interface"></a><span data-ttu-id="c4f77-102">Интерфейс IHostSemaphore</span><span class="sxs-lookup"><span data-stu-id="c4f77-102">IHostSemaphore Interface</span></span>

<span data-ttu-id="c4f77-103">Представляет реализацию семафора для потоков в ведущем приложении.</span><span class="sxs-lookup"><span data-stu-id="c4f77-103">Represents the host's implementation of a semaphore for threading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c4f77-104">Методы</span><span class="sxs-lookup"><span data-stu-id="c4f77-104">Methods</span></span>  
  
|<span data-ttu-id="c4f77-105">Метод</span><span class="sxs-lookup"><span data-stu-id="c4f77-105">Method</span></span>|<span data-ttu-id="c4f77-106">Описание</span><span class="sxs-lookup"><span data-stu-id="c4f77-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c4f77-107">Метод ReleaseSemaphore</span><span class="sxs-lookup"><span data-stu-id="c4f77-107">ReleaseSemaphore Method</span></span>](ihostsemaphore-releasesemaphore-method.md)|<span data-ttu-id="c4f77-108">Увеличивает количество текущего `IHostSemaphore` экземпляра на указанный объем.</span><span class="sxs-lookup"><span data-stu-id="c4f77-108">Increases the count of the current `IHostSemaphore` instance by the specified amount.</span></span>|  
|[<span data-ttu-id="c4f77-109">Метод Wait</span><span class="sxs-lookup"><span data-stu-id="c4f77-109">Wait Method</span></span>](ihostsemaphore-wait-method.md)|<span data-ttu-id="c4f77-110">Вызывает `IHostSemaphore` Ожидание текущего экземпляра до его признания или указанного периода времени.</span><span class="sxs-lookup"><span data-stu-id="c4f77-110">Causes the current `IHostSemaphore` instance to wait until it is owned or the specified amount of time elapses.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c4f77-111">Требования</span><span class="sxs-lookup"><span data-stu-id="c4f77-111">Requirements</span></span>  

 <span data-ttu-id="c4f77-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c4f77-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4f77-113">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="c4f77-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c4f77-114">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c4f77-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c4f77-115">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4f77-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4f77-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="c4f77-116">See also</span></span>

- [<span data-ttu-id="c4f77-117">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="c4f77-117">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="c4f77-118">Интерфейс IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="c4f77-118">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="c4f77-119">Интерфейс IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="c4f77-119">IHostManualEvent Interface</span></span>](ihostmanualevent-interface.md)
- [<span data-ttu-id="c4f77-120">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="c4f77-120">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
- [<span data-ttu-id="c4f77-121">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="c4f77-121">Hosting Interfaces</span></span>](hosting-interfaces.md)
