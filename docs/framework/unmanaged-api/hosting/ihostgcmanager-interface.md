---
title: Интерфейс IHostGCManager
ms.date: 03/30/2017
api_name:
- IHostGCManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostGCManager
helpviewer_keywords:
- IHostGCManager interface [.NET Framework hosting]
ms.assetid: 820330a4-244c-4f67-ab5e-f24b0b3c2080
topic_type:
- apiref
ms.openlocfilehash: eb7e52b5237d4341c27b8c167249dc2614168679
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729536"
---
# <a name="ihostgcmanager-interface"></a><span data-ttu-id="5c284-102">Интерфейс IHostGCManager</span><span class="sxs-lookup"><span data-stu-id="5c284-102">IHostGCManager Interface</span></span>

<span data-ttu-id="5c284-103">Предоставляет методы, которые уведомляют узел о событиях в механизме сборки мусора, реализованном средой CLR.</span><span class="sxs-lookup"><span data-stu-id="5c284-103">Provides methods that notify the host of events in the garbage collection mechanism implemented by the common language runtime (CLR).</span></span>  
  
## <a name="members"></a><span data-ttu-id="5c284-104">Элементы</span><span class="sxs-lookup"><span data-stu-id="5c284-104">Members</span></span>  
  
|<span data-ttu-id="5c284-105">Член</span><span class="sxs-lookup"><span data-stu-id="5c284-105">Member</span></span>|<span data-ttu-id="5c284-106">Описание</span><span class="sxs-lookup"><span data-stu-id="5c284-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5c284-107">Метод SuspensionEnding</span><span class="sxs-lookup"><span data-stu-id="5c284-107">SuspensionEnding Method</span></span>](ihostgcmanager-suspensionending-method.md)|<span data-ttu-id="5c284-108">Уведомляет узел о том, что среда CLR возобновляет выполнение задач в потоках, которые были приостановлены для сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="5c284-108">Notifies the host that the CLR is resuming execution of tasks on threads that had been suspended for a garbage collection.</span></span>|  
|[<span data-ttu-id="5c284-109">Метод SuspensionStarting</span><span class="sxs-lookup"><span data-stu-id="5c284-109">SuspensionStarting Method</span></span>](ihostgcmanager-suspensionstarting-method.md)|<span data-ttu-id="5c284-110">Уведомляет узел о том, что среда CLR приостанавливает выполнение задач, для выполнения сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="5c284-110">Notifies the host that the CLR is suspending execution of tasks, to perform a garbage collection.</span></span>|  
|[<span data-ttu-id="5c284-111">Метод ThreadIsBlockingForSuspension</span><span class="sxs-lookup"><span data-stu-id="5c284-111">ThreadIsBlockingForSuspension Method</span></span>](ihostgcmanager-threadisblockingforsuspension-method.md)|<span data-ttu-id="5c284-112">Уведомляет узел о том, что поток, из которого был сделан вызов метода, собирается блокироваться для сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="5c284-112">Notifies the host that the thread from which the method call was made is about to block for a garbage collection.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5c284-113">Требования</span><span class="sxs-lookup"><span data-stu-id="5c284-113">Requirements</span></span>  

 <span data-ttu-id="5c284-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5c284-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c284-115">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="5c284-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5c284-116">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5c284-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5c284-117">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c284-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c284-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="5c284-118">See also</span></span>

- [<span data-ttu-id="5c284-119">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="5c284-119">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="5c284-120">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="5c284-120">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="5c284-121">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="5c284-121">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="5c284-122">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="5c284-122">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="5c284-123">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="5c284-123">Hosting Interfaces</span></span>](hosting-interfaces.md)
