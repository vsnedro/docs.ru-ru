---
title: Интерфейс ICLRMemoryNotificationCallback
ms.date: 03/30/2017
api_name:
- ICLRMemoryNotificationCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMemoryNotificationCallback
helpviewer_keywords:
- ICLRMemoryNotificationCallback interface [.NET Framework hosting]
ms.assetid: 873639e2-4837-4568-83b3-4493e67e4174
topic_type:
- apiref
ms.openlocfilehash: 5762a354bec485cb382b5460dfd2a337f79bee1a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95689541"
---
# <a name="iclrmemorynotificationcallback-interface"></a><span data-ttu-id="7017c-102">Интерфейс ICLRMemoryNotificationCallback</span><span class="sxs-lookup"><span data-stu-id="7017c-102">ICLRMemoryNotificationCallback Interface</span></span>

<span data-ttu-id="7017c-103">Позволяет узлу сообщать об условиях нехватки памяти с помощью подхода, аналогичного функции Win32 `CreateMemoryResourceNotification` .</span><span class="sxs-lookup"><span data-stu-id="7017c-103">Allows the host to report memory pressure conditions using an approach similar to that of the Win32 `CreateMemoryResourceNotification` function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7017c-104">Методы</span><span class="sxs-lookup"><span data-stu-id="7017c-104">Methods</span></span>  
  
|<span data-ttu-id="7017c-105">Метод</span><span class="sxs-lookup"><span data-stu-id="7017c-105">Method</span></span>|<span data-ttu-id="7017c-106">Описание</span><span class="sxs-lookup"><span data-stu-id="7017c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7017c-107">Метод OnMemoryNotification</span><span class="sxs-lookup"><span data-stu-id="7017c-107">OnMemoryNotification Method</span></span>](iclrmemorynotificationcallback-onmemorynotification-method.md)|<span data-ttu-id="7017c-108">Уведомляет среду CLR о загрузке памяти на компьютере.</span><span class="sxs-lookup"><span data-stu-id="7017c-108">Notifies the common language runtime (CLR) of the memory load on the computer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7017c-109">Комментарии</span><span class="sxs-lookup"><span data-stu-id="7017c-109">Remarks</span></span>  

 <span data-ttu-id="7017c-110">Узел использует `ICLRMemoryNotificationCallback` интерфейс для запроса освобождения ресурсов памяти CLR.</span><span class="sxs-lookup"><span data-stu-id="7017c-110">The host uses the `ICLRMemoryNotificationCallback` interface to request that the CLR free memory resources.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7017c-111">Требования</span><span class="sxs-lookup"><span data-stu-id="7017c-111">Requirements</span></span>  

 <span data-ttu-id="7017c-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7017c-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7017c-113">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="7017c-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7017c-114">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7017c-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7017c-115">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7017c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7017c-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="7017c-116">See also</span></span>

- [<span data-ttu-id="7017c-117">Интерфейс IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="7017c-117">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
- [<span data-ttu-id="7017c-118">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="7017c-118">Hosting Interfaces</span></span>](hosting-interfaces.md)
