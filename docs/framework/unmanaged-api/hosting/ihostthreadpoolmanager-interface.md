---
title: Интерфейс IHostThreadPoolManager
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager
helpviewer_keywords:
- IHostThreadPoolManager interface [.NET Framework hosting]
ms.assetid: c3a2cd90-7c4e-4374-bb87-b41befb8344f
topic_type:
- apiref
ms.openlocfilehash: b6625b0ef4dc3de4067514a0b39849c7a958d5c4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730764"
---
# <a name="ihostthreadpoolmanager-interface"></a><span data-ttu-id="80866-102">Интерфейс IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="80866-102">IHostThreadPoolManager Interface</span></span>

<span data-ttu-id="80866-103">Предоставляет методы, позволяющие среде CLR настроить пул потоков и поместить рабочие элементы в очередь в пул потоков.</span><span class="sxs-lookup"><span data-stu-id="80866-103">Provides methods that enable the common language runtime (CLR) to configure the thread pool and to queue work items to the thread pool.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="80866-104">Методы</span><span class="sxs-lookup"><span data-stu-id="80866-104">Methods</span></span>  
  
|<span data-ttu-id="80866-105">Метод</span><span class="sxs-lookup"><span data-stu-id="80866-105">Method</span></span>|<span data-ttu-id="80866-106">Описание</span><span class="sxs-lookup"><span data-stu-id="80866-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="80866-107">Метод GetAvailableThreads</span><span class="sxs-lookup"><span data-stu-id="80866-107">GetAvailableThreads Method</span></span>](ihostthreadpoolmanager-getavailablethreads-method.md)|<span data-ttu-id="80866-108">Возвращает число потоков в пуле потоков, которые в данный момент не обрабатывают рабочие элементы.</span><span class="sxs-lookup"><span data-stu-id="80866-108">Gets the number of threads in the thread pool that are not currently processing work items.</span></span>|  
|[<span data-ttu-id="80866-109">Метод GetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="80866-109">GetMaxThreads Method</span></span>](ihostthreadpoolmanager-getmaxthreads-method.md)|<span data-ttu-id="80866-110">Возвращает максимальное число потоков, которые обслуживается одновременно в пуле потоков.</span><span class="sxs-lookup"><span data-stu-id="80866-110">Gets the maximum number of threads that the host maintains concurrently in the thread pool.</span></span>|  
|[<span data-ttu-id="80866-111">Метод GetMinThreads</span><span class="sxs-lookup"><span data-stu-id="80866-111">GetMinThreads Method</span></span>](ihostthreadpoolmanager-getminthreads-method.md)|<span data-ttu-id="80866-112">Возвращает минимальное число бездействующих потоков, поддерживаемых узлом в ожидаемых запросах.</span><span class="sxs-lookup"><span data-stu-id="80866-112">Gets the minimum number of idle threads that the host maintains in anticipation of requests.</span></span>|  
|[<span data-ttu-id="80866-113">Метод QueueUserWorkItem</span><span class="sxs-lookup"><span data-stu-id="80866-113">QueueUserWorkItem Method</span></span>](ihostthreadpoolmanager-queueuserworkitem-method.md)|<span data-ttu-id="80866-114">Ставит в очередь функцию для выполнения и предоставляет объект, содержащий данные, которые будут использоваться функцией.</span><span class="sxs-lookup"><span data-stu-id="80866-114">Queues a function for execution, and provides an object containing data to be used by the function.</span></span>|  
|[<span data-ttu-id="80866-115">Метод SetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="80866-115">SetMaxThreads Method</span></span>](ihostthreadpoolmanager-setmaxthreads-method.md)|<span data-ttu-id="80866-116">Задает максимальное число потоков, которые узел может поддерживать в пуле потоков.</span><span class="sxs-lookup"><span data-stu-id="80866-116">Sets the maximum number of threads that the host can maintain in the thread pool.</span></span>|  
|[<span data-ttu-id="80866-117">Метод SetMinThreads</span><span class="sxs-lookup"><span data-stu-id="80866-117">SetMinThreads Method</span></span>](ihostthreadpoolmanager-setminthreads-method.md)|<span data-ttu-id="80866-118">Задает минимальное число бездействующих потоков, которые должны поддерживаться узлом в ожидаемых запросах.</span><span class="sxs-lookup"><span data-stu-id="80866-118">Sets the minimum number of idle threads that the host must maintain in anticipation of requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="80866-119">Комментарии</span><span class="sxs-lookup"><span data-stu-id="80866-119">Remarks</span></span>  

 <span data-ttu-id="80866-120">Узел не требуется для настройки пула потоков с использованием значений, указанных в вызовах `SetMaxThreads` `SetMinThreads` методов и.</span><span class="sxs-lookup"><span data-stu-id="80866-120">The host is not required to configure the thread pool by using the values specified in calls to the `SetMaxThreads` and `SetMinThreads` methods.</span></span> <span data-ttu-id="80866-121">В этом случае узел должен вернуть значение HRESULT E_NOTIMPL из этих методов.</span><span class="sxs-lookup"><span data-stu-id="80866-121">In this case, the host should return an HRESULT value of E_NOTIMPL from these methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="80866-122">Требования</span><span class="sxs-lookup"><span data-stu-id="80866-122">Requirements</span></span>  

 <span data-ttu-id="80866-123">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="80866-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80866-124">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="80866-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="80866-125">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="80866-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="80866-126">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="80866-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80866-127">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="80866-127">See also</span></span>

- <xref:System.Threading>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="80866-128">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="80866-128">Hosting Interfaces</span></span>](hosting-interfaces.md)
