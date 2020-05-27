---
title: Метод IHostIoCompletionManager::SetMaxThreads
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.SetMaxThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::SetMaxThreads
helpviewer_keywords:
- IHostIoCompletionManager::SetMaxThreads method [.NET Framework hosting]
- SetMaxThreads method, IHostIoCompletionManager interface [.NET Framework hosting]
ms.assetid: ebad4f40-d9f1-4dc6-9b27-a89c9eb3926f
topic_type:
- apiref
ms.openlocfilehash: 55727903a7f3c798e7472de6de5249de98af7ae7
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804673"
---
# <a name="ihostiocompletionmanagersetmaxthreads-method"></a><span data-ttu-id="a53a5-102">Метод IHostIoCompletionManager::SetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="a53a5-102">IHostIoCompletionManager::SetMaxThreads Method</span></span>
<span data-ttu-id="a53a5-103">Задает максимальное число потоков, которое узел запрашивает для обслуживания запросов ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="a53a5-103">Sets the maximum number of threads that the host allots to service I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a53a5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a53a5-104">Syntax</span></span>  
  
```cpp  
HRESULT SetMaxThreads (  
    [in] DWORD dwMaxIoCompletionThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a53a5-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a53a5-105">Parameters</span></span>  
 `dwMaxIoCompletionThreads`  
 <span data-ttu-id="a53a5-106">окне Максимальное число потоков, которое можно выделить для запросов ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="a53a5-106">[in] The maximum number of threads to allot for I/O requests.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a53a5-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a53a5-107">Return Value</span></span>  
  
|<span data-ttu-id="a53a5-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a53a5-108">HRESULT</span></span>|<span data-ttu-id="a53a5-109">Описание</span><span class="sxs-lookup"><span data-stu-id="a53a5-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a53a5-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="a53a5-110">S_OK</span></span>|<span data-ttu-id="a53a5-111">`SetMaxThreads`успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="a53a5-111">`SetMaxThreads` returned successfully.</span></span>|  
|<span data-ttu-id="a53a5-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a53a5-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a53a5-113">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="a53a5-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a53a5-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a53a5-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a53a5-115">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="a53a5-115">The call timed out.</span></span>|  
|<span data-ttu-id="a53a5-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a53a5-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a53a5-117">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="a53a5-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a53a5-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a53a5-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a53a5-119">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="a53a5-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a53a5-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a53a5-120">E_FAIL</span></span>|<span data-ttu-id="a53a5-121">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="a53a5-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a53a5-122">Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="a53a5-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a53a5-123">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="a53a5-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="a53a5-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="a53a5-124">E_NOTIMPL</span></span>|<span data-ttu-id="a53a5-125">Узел не предоставляет реализацию `SetMaxThreads` .</span><span class="sxs-lookup"><span data-stu-id="a53a5-125">The host does not provide an implementation of `SetMaxThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a53a5-126">Замечания</span><span class="sxs-lookup"><span data-stu-id="a53a5-126">Remarks</span></span>  
 <span data-ttu-id="a53a5-127">`SetMaxThreads`предоставляет среде CLR возможность задать максимальное число потоков, доступных для запросов на обслуживание на портах ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="a53a5-127">`SetMaxThreads` provides the CLR with an opportunity to set the maximum number of threads that are available to service requests on I/O ports.</span></span> <span data-ttu-id="a53a5-128">Узлу может потребоваться эксклюзивный контроль над размером пула потоков по таким причинам, как реализация, производительность или масштабируемость.</span><span class="sxs-lookup"><span data-stu-id="a53a5-128">A host might need exclusive control over the size of the thread pool, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="a53a5-129">По этой причине узел не является обязательным для реализации `SetMaxThreads` .</span><span class="sxs-lookup"><span data-stu-id="a53a5-129">For this reason, the host is not required to implement `SetMaxThreads`.</span></span> <span data-ttu-id="a53a5-130">В этом случае узел должен возвращать E_NOTIMPL из этого метода.</span><span class="sxs-lookup"><span data-stu-id="a53a5-130">In this case, a host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a53a5-131">Требования</span><span class="sxs-lookup"><span data-stu-id="a53a5-131">Requirements</span></span>  
 <span data-ttu-id="a53a5-132">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a53a5-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a53a5-133">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="a53a5-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a53a5-134">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="a53a5-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a53a5-135">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a53a5-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a53a5-136">См. также статью</span><span class="sxs-lookup"><span data-stu-id="a53a5-136">See also</span></span>

- [<span data-ttu-id="a53a5-137">Интерфейс ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="a53a5-137">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)
- [<span data-ttu-id="a53a5-138">Интерфейс IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="a53a5-138">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)
