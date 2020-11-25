---
title: Метод IHostThreadPoolManager::GetMaxThreads
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager.GetMaxThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager::GetMaxThreads
helpviewer_keywords:
- IHostThreadPoolManager::GetMaxThreads method [.NET Framework hosting]
- GetMaxThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
ms.assetid: db268876-6178-4a81-aca3-318ee7f96001
topic_type:
- apiref
ms.openlocfilehash: 3aecebe2803d3a795db801491d0f60a5eb7c00ce
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730790"
---
# <a name="ihostthreadpoolmanagergetmaxthreads-method"></a><span data-ttu-id="ebb16-102">Метод IHostThreadPoolManager::GetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="ebb16-102">IHostThreadPoolManager::GetMaxThreads Method</span></span>

<span data-ttu-id="ebb16-103">Возвращает максимальное число потоков, которые обслуживается одновременно в пуле потоков.</span><span class="sxs-lookup"><span data-stu-id="ebb16-103">Gets the maximum number of threads that the host maintains concurrently in the thread pool.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ebb16-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ebb16-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMaxThreads (  
    [out] DWORD *pdwMaxWorkerThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ebb16-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ebb16-105">Parameters</span></span>  

 `pdwMaxWorkerThreads`  
 <span data-ttu-id="ebb16-106">заполняет Указатель на максимальное число потоков, поддерживаемых узлом в пуле потоков.</span><span class="sxs-lookup"><span data-stu-id="ebb16-106">[out] A pointer to the maximum number of threads that the host maintains in the thread pool.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ebb16-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ebb16-107">Return Value</span></span>  
  
|<span data-ttu-id="ebb16-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ebb16-108">HRESULT</span></span>|<span data-ttu-id="ebb16-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="ebb16-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ebb16-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="ebb16-110">S_OK</span></span>|<span data-ttu-id="ebb16-111">`GetMaxThreads` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="ebb16-111">`GetMaxThreads` returned successfully.</span></span>|  
|<span data-ttu-id="ebb16-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ebb16-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ebb16-113">Общеязыковая среда выполнения (CLR не загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="ebb16-113">The common language runtime (CLR( has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ebb16-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ebb16-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ebb16-115">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="ebb16-115">The call timed out.</span></span>|  
|<span data-ttu-id="ebb16-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ebb16-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ebb16-117">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="ebb16-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ebb16-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ebb16-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ebb16-119">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="ebb16-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ebb16-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ebb16-120">E_FAIL</span></span>|<span data-ttu-id="ebb16-121">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="ebb16-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ebb16-122">Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="ebb16-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ebb16-123">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="ebb16-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="ebb16-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="ebb16-124">E_NOTIMPL</span></span>|<span data-ttu-id="ebb16-125">Узел не предоставляет реализацию `GetMaxThreads` .</span><span class="sxs-lookup"><span data-stu-id="ebb16-125">The host does not provide an implementation of `GetMaxThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ebb16-126">Комментарии</span><span class="sxs-lookup"><span data-stu-id="ebb16-126">Remarks</span></span>  

 <span data-ttu-id="ebb16-127">Вызовы CLR `GetMaxThreads` для определения общего числа потоков в пуле потоков.</span><span class="sxs-lookup"><span data-stu-id="ebb16-127">The CLR calls `GetMaxThreads` to determine the total number of threads in the thread pool.</span></span> <span data-ttu-id="ebb16-128">Метод [GetAvailableThreads](ihostthreadpoolmanager-getavailablethreads-method.md) возвращает число потоков, которые в данный момент не обрабатывают рабочие элементы.</span><span class="sxs-lookup"><span data-stu-id="ebb16-128">The [GetAvailableThreads](ihostthreadpoolmanager-getavailablethreads-method.md) method gets the number of threads that are not currently processing work items.</span></span> <span data-ttu-id="ebb16-129">Все запросы выше возвращенного значения `pdwMaxWorkerThreads` параметра остаются в очереди до тех пор, пока потоки не станут доступными.</span><span class="sxs-lookup"><span data-stu-id="ebb16-129">All requests above the returned value of the `pdwMaxWorkerThreads` parameter remain queued until threads become available.</span></span>  
  
 <span data-ttu-id="ebb16-130">Если узел не предоставляет реализацию `GetMaxThreads` , он должен возвращать значение HRESULT, равное E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="ebb16-130">If the host does not provide an implementation of `GetMaxThreads`, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ebb16-131">Требования</span><span class="sxs-lookup"><span data-stu-id="ebb16-131">Requirements</span></span>  

 <span data-ttu-id="ebb16-132">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ebb16-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ebb16-133">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="ebb16-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ebb16-134">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ebb16-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ebb16-135">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ebb16-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebb16-136">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ebb16-136">See also</span></span>

- <xref:System.Threading.ThreadPool.GetMaxThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="ebb16-137">Метод GetMinThreads</span><span class="sxs-lookup"><span data-stu-id="ebb16-137">GetMinThreads Method</span></span>](ihostthreadpoolmanager-getminthreads-method.md)
- [<span data-ttu-id="ebb16-138">Метод SetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="ebb16-138">SetMaxThreads Method</span></span>](ihostthreadpoolmanager-setmaxthreads-method.md)
- [<span data-ttu-id="ebb16-139">Интерфейс IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="ebb16-139">IHostThreadPoolManager Interface</span></span>](ihostthreadpoolmanager-interface.md)
