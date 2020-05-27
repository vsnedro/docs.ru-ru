---
title: Метод IHostThreadPoolManager::GetMinThreads
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager.GetMinThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager::GetMinThreads
helpviewer_keywords:
- IHostThreadPoolManager::GetMinThreads method [.NET Framework hosting]
- GetMinThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
ms.assetid: dc07232b-b2e4-4dab-87e2-3c955974ab48
topic_type:
- apiref
ms.openlocfilehash: a05cfb43b5b4a328d22c4df04049a7fa156ca080
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/26/2020
ms.locfileid: "83841936"
---
# <a name="ihostthreadpoolmanagergetminthreads-method"></a><span data-ttu-id="9dbeb-102">Метод IHostThreadPoolManager::GetMinThreads</span><span class="sxs-lookup"><span data-stu-id="9dbeb-102">IHostThreadPoolManager::GetMinThreads Method</span></span>
<span data-ttu-id="9dbeb-103">Возвращает минимальное количество бездействующих потоков, которые обслуживающий узел хранит в пуле потоков в ожидаемых запросах.</span><span class="sxs-lookup"><span data-stu-id="9dbeb-103">Gets the minimum number of idle threads that the host maintains in the thread pool in anticipation of requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9dbeb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9dbeb-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMinThreads (  
    [out] DWORD *MinThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9dbeb-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9dbeb-105">Parameters</span></span>  
 `MinThreads`  
 <span data-ttu-id="9dbeb-106">заполняет Указатель на минимальное число бездействующих рабочих потоков, которое в настоящее время поддерживает узел.</span><span class="sxs-lookup"><span data-stu-id="9dbeb-106">[out] A pointer to the minimum number of idle worker threads that the host currently maintains.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9dbeb-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="9dbeb-107">Return Value</span></span>  
  
|<span data-ttu-id="9dbeb-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9dbeb-108">HRESULT</span></span>|<span data-ttu-id="9dbeb-109">Описание</span><span class="sxs-lookup"><span data-stu-id="9dbeb-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9dbeb-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="9dbeb-110">S_OK</span></span>|<span data-ttu-id="9dbeb-111">`GetMinThreads`успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="9dbeb-111">`GetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="9dbeb-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9dbeb-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9dbeb-113">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="9dbeb-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9dbeb-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9dbeb-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9dbeb-115">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="9dbeb-115">The call timed out.</span></span>|  
|<span data-ttu-id="9dbeb-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9dbeb-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9dbeb-117">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="9dbeb-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9dbeb-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9dbeb-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9dbeb-119">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="9dbeb-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9dbeb-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9dbeb-120">E_FAIL</span></span>|<span data-ttu-id="9dbeb-121">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="9dbeb-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9dbeb-122">Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="9dbeb-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9dbeb-123">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="9dbeb-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="9dbeb-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="9dbeb-124">E_NOTIMPL</span></span>|<span data-ttu-id="9dbeb-125">Узел не предоставляет реализацию `GetMinThreads` .</span><span class="sxs-lookup"><span data-stu-id="9dbeb-125">The host does not provide an implementation of `GetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9dbeb-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="9dbeb-126">Remarks</span></span>  
 <span data-ttu-id="9dbeb-127">Узлу не требуется предоставлять реализацию `GetMinThreads` .</span><span class="sxs-lookup"><span data-stu-id="9dbeb-127">The host is not required to provide an implementation of `GetMinThreads`.</span></span> <span data-ttu-id="9dbeb-128">В этом случае он должен возвращать значение HRESULT, равное E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="9dbeb-128">In this case, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9dbeb-129">Требования</span><span class="sxs-lookup"><span data-stu-id="9dbeb-129">Requirements</span></span>  
 <span data-ttu-id="9dbeb-130">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9dbeb-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9dbeb-131">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="9dbeb-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9dbeb-132">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="9dbeb-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9dbeb-133">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9dbeb-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9dbeb-134">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="9dbeb-134">See also</span></span>

- <xref:System.Threading.ThreadPool.GetMinThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="9dbeb-135">Метод GetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="9dbeb-135">GetMaxThreads Method</span></span>](ihostthreadpoolmanager-getmaxthreads-method.md)
- [<span data-ttu-id="9dbeb-136">Метод SetMinThreads</span><span class="sxs-lookup"><span data-stu-id="9dbeb-136">SetMinThreads Method</span></span>](ihostthreadpoolmanager-setminthreads-method.md)
- [<span data-ttu-id="9dbeb-137">Интерфейс IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="9dbeb-137">IHostThreadPoolManager Interface</span></span>](ihostthreadpoolmanager-interface.md)
