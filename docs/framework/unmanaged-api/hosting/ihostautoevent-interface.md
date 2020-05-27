---
title: Интерфейс IHostAutoEvent
ms.date: 03/30/2017
api_name:
- IHostAutoEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAutoEvent
helpviewer_keywords:
- IHostAutoEvent interface [.NET Framework hosting]
ms.assetid: 6c1d15c1-a80a-4ee9-b1e4-6e859db6575a
topic_type:
- apiref
ms.openlocfilehash: a24939ac0b0808546ef3615fae4909c6c3cf8a2e
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804997"
---
# <a name="ihostautoevent-interface"></a><span data-ttu-id="b97f1-102">Интерфейс IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="b97f1-102">IHostAutoEvent Interface</span></span>
<span data-ttu-id="b97f1-103">Предоставляет представление реализации события автоматического сброса в узле.</span><span class="sxs-lookup"><span data-stu-id="b97f1-103">Provides a representation of the host's implementation of an auto-reset event.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b97f1-104">Методы</span><span class="sxs-lookup"><span data-stu-id="b97f1-104">Methods</span></span>  
  
|<span data-ttu-id="b97f1-105">Метод</span><span class="sxs-lookup"><span data-stu-id="b97f1-105">Method</span></span>|<span data-ttu-id="b97f1-106">Описание</span><span class="sxs-lookup"><span data-stu-id="b97f1-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b97f1-107">Метод Set</span><span class="sxs-lookup"><span data-stu-id="b97f1-107">Set Method</span></span>](ihostautoevent-set-method.md)|<span data-ttu-id="b97f1-108">Устанавливает для текущего `IHostAutoEvent` экземпляра сигнальное состояние.</span><span class="sxs-lookup"><span data-stu-id="b97f1-108">Sets the current `IHostAutoEvent` instance to a signaled state.</span></span>|  
|[<span data-ttu-id="b97f1-109">Метод Wait</span><span class="sxs-lookup"><span data-stu-id="b97f1-109">Wait Method</span></span>](ihostautoevent-wait-method.md)|<span data-ttu-id="b97f1-110">Заставляет текущий `IHostAutoEvent` экземпляр ожидать, пока событие не будет присвоено, или истечет указанное время.</span><span class="sxs-lookup"><span data-stu-id="b97f1-110">Causes the current `IHostAutoEvent` instance to wait until the event is owned or a specified amount of time elapses.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b97f1-111">Требования</span><span class="sxs-lookup"><span data-stu-id="b97f1-111">Requirements</span></span>  
 <span data-ttu-id="b97f1-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b97f1-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b97f1-113">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="b97f1-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b97f1-114">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="b97f1-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b97f1-115">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b97f1-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b97f1-116">См. также статью</span><span class="sxs-lookup"><span data-stu-id="b97f1-116">See also</span></span>

- [<span data-ttu-id="b97f1-117">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="b97f1-117">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="b97f1-118">Интерфейс IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="b97f1-118">IHostManualEvent Interface</span></span>](ihostmanualevent-interface.md)
- [<span data-ttu-id="b97f1-119">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="b97f1-119">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
- [<span data-ttu-id="b97f1-120">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="b97f1-120">Hosting Interfaces</span></span>](hosting-interfaces.md)
