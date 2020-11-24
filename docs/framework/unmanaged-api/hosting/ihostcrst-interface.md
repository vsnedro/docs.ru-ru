---
title: Интерфейс IHostCrst
ms.date: 03/30/2017
api_name:
- IHostCrst
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostCrst
helpviewer_keywords:
- IHostCrst interface [.NET Framework hosting]
ms.assetid: ac298ebd-0815-47e4-a823-30b31baab903
topic_type:
- apiref
ms.openlocfilehash: 350af708456914c73929d2b8887173cf784d4294
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95680564"
---
# <a name="ihostcrst-interface"></a><span data-ttu-id="62ec7-102">Интерфейс IHostCrst</span><span class="sxs-lookup"><span data-stu-id="62ec7-102">IHostCrst Interface</span></span>

<span data-ttu-id="62ec7-103">Служит в качестве представления критической секции для потоков в основном приложении.</span><span class="sxs-lookup"><span data-stu-id="62ec7-103">Serves as the host's representation of a critical section for threading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="62ec7-104">Методы</span><span class="sxs-lookup"><span data-stu-id="62ec7-104">Methods</span></span>  
  
|<span data-ttu-id="62ec7-105">Метод</span><span class="sxs-lookup"><span data-stu-id="62ec7-105">Method</span></span>|<span data-ttu-id="62ec7-106">Описание</span><span class="sxs-lookup"><span data-stu-id="62ec7-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="62ec7-107">Метод Enter</span><span class="sxs-lookup"><span data-stu-id="62ec7-107">Enter Method</span></span>](ihostcrst-enter-method.md)|<span data-ttu-id="62ec7-108">Входит в критическую секцию.</span><span class="sxs-lookup"><span data-stu-id="62ec7-108">Enters the critical section.</span></span>|  
|[<span data-ttu-id="62ec7-109">Метод Leave</span><span class="sxs-lookup"><span data-stu-id="62ec7-109">Leave Method</span></span>](ihostcrst-leave-method.md)|<span data-ttu-id="62ec7-110">Оставляет критическую секцию.</span><span class="sxs-lookup"><span data-stu-id="62ec7-110">Leaves the critical section.</span></span>|  
|[<span data-ttu-id="62ec7-111">Метод SetSpinCount</span><span class="sxs-lookup"><span data-stu-id="62ec7-111">SetSpinCount Method</span></span>](ihostcrst-setspincount-method.md)|<span data-ttu-id="62ec7-112">Задает счетчик счетчиков для критической секции.</span><span class="sxs-lookup"><span data-stu-id="62ec7-112">Sets the spin count for the critical section.</span></span>|  
|[<span data-ttu-id="62ec7-113">Метод TryEnter</span><span class="sxs-lookup"><span data-stu-id="62ec7-113">TryEnter Method</span></span>](ihostcrst-tryenter-method.md)|<span data-ttu-id="62ec7-114">Пытается войти в критическую секцию и немедленно сообщает об успешном или неуспешном завершении.</span><span class="sxs-lookup"><span data-stu-id="62ec7-114">Attempts to enter the critical section, and reports success or failure immediately.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="62ec7-115">Комментарии</span><span class="sxs-lookup"><span data-stu-id="62ec7-115">Remarks</span></span>  

 <span data-ttu-id="62ec7-116">`IHostCrst` позволяет среде CLR взаимодействовать непосредственно с представлением критического раздела узла, а не использовать функции Win32, такие как `EnterCriticalSection` или `LeaveCriticalSection` .</span><span class="sxs-lookup"><span data-stu-id="62ec7-116">`IHostCrst` allows the common language runtime (CLR) to communicate directly with the host's representation of a critical section, rather than using Win32 functions such as `EnterCriticalSection` or `LeaveCriticalSection`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62ec7-117">Требования</span><span class="sxs-lookup"><span data-stu-id="62ec7-117">Requirements</span></span>  

 <span data-ttu-id="62ec7-118">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="62ec7-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62ec7-119">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="62ec7-119">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="62ec7-120">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="62ec7-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="62ec7-121">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62ec7-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62ec7-122">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="62ec7-122">See also</span></span>

- [<span data-ttu-id="62ec7-123">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="62ec7-123">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="62ec7-124">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="62ec7-124">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
- [<span data-ttu-id="62ec7-125">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="62ec7-125">Hosting Interfaces</span></span>](hosting-interfaces.md)
