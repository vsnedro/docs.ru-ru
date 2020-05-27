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
ms.openlocfilehash: 7c46f00063cdf9281a5f1080594e8d6dbc6c101e
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804597"
---
# <a name="ihostmanualevent-interface"></a><span data-ttu-id="0292d-102">Интерфейс IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="0292d-102">IHostManualEvent Interface</span></span>
<span data-ttu-id="0292d-103">Предоставляет реализацию представления события ручного сброса в узле.</span><span class="sxs-lookup"><span data-stu-id="0292d-103">Provides the host's implementation of a representation of a manual reset event.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0292d-104">Методы</span><span class="sxs-lookup"><span data-stu-id="0292d-104">Methods</span></span>  
  
|<span data-ttu-id="0292d-105">Метод</span><span class="sxs-lookup"><span data-stu-id="0292d-105">Method</span></span>|<span data-ttu-id="0292d-106">Описание</span><span class="sxs-lookup"><span data-stu-id="0292d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0292d-107">Метод Reset</span><span class="sxs-lookup"><span data-stu-id="0292d-107">Reset Method</span></span>](ihostmanualevent-reset-method.md)|<span data-ttu-id="0292d-108">Сбрасывает текущий `IHostManualEvent` экземпляр в несигнальное состояние.</span><span class="sxs-lookup"><span data-stu-id="0292d-108">Resets the current `IHostManualEvent` instance to a non-signaled state.</span></span>|  
|[<span data-ttu-id="0292d-109">Метод Set</span><span class="sxs-lookup"><span data-stu-id="0292d-109">Set Method</span></span>](ihostmanualevent-set-method.md)|<span data-ttu-id="0292d-110">Устанавливает для текущего `IHostManualEvent` экземпляра сигнальное состояние.</span><span class="sxs-lookup"><span data-stu-id="0292d-110">Sets the current `IHostManualEvent` instance to a signaled state.</span></span>|  
|[<span data-ttu-id="0292d-111">Метод Wait</span><span class="sxs-lookup"><span data-stu-id="0292d-111">Wait Method</span></span>](ihostmanualevent-wait-method.md)|<span data-ttu-id="0292d-112">Вызывает `IHostManualEvent` Ожидание текущего экземпляра до его признания или истечения указанного периода времени.</span><span class="sxs-lookup"><span data-stu-id="0292d-112">Causes the current `IHostManualEvent` instance to wait until it is owned, or a specified amount of time elapses.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0292d-113">Требования</span><span class="sxs-lookup"><span data-stu-id="0292d-113">Requirements</span></span>  
 <span data-ttu-id="0292d-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0292d-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0292d-115">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="0292d-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0292d-116">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="0292d-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0292d-117">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0292d-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0292d-118">См. также статью</span><span class="sxs-lookup"><span data-stu-id="0292d-118">See also</span></span>

- [<span data-ttu-id="0292d-119">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="0292d-119">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="0292d-120">Интерфейс IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="0292d-120">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="0292d-121">Интерфейс IHostSemaphore</span><span class="sxs-lookup"><span data-stu-id="0292d-121">IHostSemaphore Interface</span></span>](ihostsemaphore-interface.md)
- [<span data-ttu-id="0292d-122">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="0292d-122">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
- [<span data-ttu-id="0292d-123">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="0292d-123">Hosting Interfaces</span></span>](hosting-interfaces.md)
