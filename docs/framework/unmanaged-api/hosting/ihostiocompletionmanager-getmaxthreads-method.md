---
title: Метод IHostIoCompletionManager::GetMaxThreads
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.GetMaxThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::GetMaxThreads
helpviewer_keywords:
- IHostIoCompletionManager::GetMaxThreads method [.NET Framework hosting]
- GetMaxThreads method, IHostIoCompletionManager interface [.NET Framework hosting]
ms.assetid: e7a6cadc-2433-4472-a701-58891abcde45
topic_type:
- apiref
ms.openlocfilehash: a97a7abf4f561a5aba41d8019f2ba5bd8e879acd
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804740"
---
# <a name="ihostiocompletionmanagergetmaxthreads-method"></a><span data-ttu-id="8df7f-102">Метод IHostIoCompletionManager::GetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="8df7f-102">IHostIoCompletionManager::GetMaxThreads Method</span></span>
<span data-ttu-id="8df7f-103">Возвращает максимальное число потоков, которое узел может выделить для обслуживания запросов ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="8df7f-103">Gets the maximum number of threads that the host can allot to service I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8df7f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8df7f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMaxThreads (  
    [out] DWORD *pdwMaxIoCompletionThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8df7f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8df7f-105">Parameters</span></span>  
 `pdwMaxIoCompletionThreads`  
 <span data-ttu-id="8df7f-106">заполняет Указатель на максимальное количество потоков в пуле потоков, которое узел может выделить для обслуживания запросов ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="8df7f-106">[out] A pointer to the maximum number of threads in the thread pool that the host can allot to service I/O requests.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8df7f-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="8df7f-107">Return Value</span></span>  
  
|<span data-ttu-id="8df7f-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8df7f-108">HRESULT</span></span>|<span data-ttu-id="8df7f-109">Описание</span><span class="sxs-lookup"><span data-stu-id="8df7f-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8df7f-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="8df7f-110">S_OK</span></span>|<span data-ttu-id="8df7f-111">`GetMaxThreads`успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="8df7f-111">`GetMaxThreads` returned successfully.</span></span>|  
|<span data-ttu-id="8df7f-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8df7f-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8df7f-113">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="8df7f-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8df7f-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8df7f-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8df7f-115">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="8df7f-115">The call timed out.</span></span>|  
|<span data-ttu-id="8df7f-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8df7f-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8df7f-117">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="8df7f-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8df7f-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8df7f-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8df7f-119">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="8df7f-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8df7f-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8df7f-120">E_FAIL</span></span>|<span data-ttu-id="8df7f-121">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="8df7f-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8df7f-122">Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="8df7f-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8df7f-123">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="8df7f-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="8df7f-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="8df7f-124">E_NOTIMPL</span></span>|<span data-ttu-id="8df7f-125">Узел не предоставляет реализацию `GetMaxThreads` .</span><span class="sxs-lookup"><span data-stu-id="8df7f-125">The host does not provide an implementation of `GetMaxThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8df7f-126">Замечания</span><span class="sxs-lookup"><span data-stu-id="8df7f-126">Remarks</span></span>  
 <span data-ttu-id="8df7f-127">Узлу может потребоваться эксклюзивный контроль над количеством потоков, которые могут быть выделены для обработки запросов ввода-вывода, по таким причинам, как реализация, производительность или масштабируемость.</span><span class="sxs-lookup"><span data-stu-id="8df7f-127">A host might want exclusive control over the number of threads that can be allotted to process I/O requests, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="8df7f-128">По этой причине узел не является обязательным для реализации `GetMaxThreads` .</span><span class="sxs-lookup"><span data-stu-id="8df7f-128">For this reason, the host is not required to implement `GetMaxThreads`.</span></span> <span data-ttu-id="8df7f-129">В этом случае узел должен вернуть E_NOTIMPL из этого метода.</span><span class="sxs-lookup"><span data-stu-id="8df7f-129">In this case, the host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8df7f-130">Требования</span><span class="sxs-lookup"><span data-stu-id="8df7f-130">Requirements</span></span>  
 <span data-ttu-id="8df7f-131">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8df7f-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8df7f-132">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="8df7f-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8df7f-133">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="8df7f-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8df7f-134">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8df7f-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8df7f-135">См. также статью</span><span class="sxs-lookup"><span data-stu-id="8df7f-135">See also</span></span>

- [<span data-ttu-id="8df7f-136">Интерфейс ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="8df7f-136">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)
- [<span data-ttu-id="8df7f-137">Интерфейс IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="8df7f-137">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)
