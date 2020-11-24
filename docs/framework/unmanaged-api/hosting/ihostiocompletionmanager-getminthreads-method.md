---
title: Метод IHostIoCompletionManager::GetMinThreads
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.GetMinThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::GetMinThreads
helpviewer_keywords:
- GetMinThreads method, IHostIoCompletionManager interface [.NET Framework hosting]
- IHostIoCompletionManager::GetMinThreads method [.NET Framework hosting]
ms.assetid: d7a7f733-677d-481c-b3d5-444fcc502b8e
topic_type:
- apiref
ms.openlocfilehash: d321ce08edf4780fc5f26ac627849b9129c2f283
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673232"
---
# <a name="ihostiocompletionmanagergetminthreads-method"></a><span data-ttu-id="c96c3-102">Метод IHostIoCompletionManager::GetMinThreads</span><span class="sxs-lookup"><span data-stu-id="c96c3-102">IHostIoCompletionManager::GetMinThreads Method</span></span>

<span data-ttu-id="c96c3-103">Возвращает минимальное число потоков, которые предоставляет узел для обработки запросов ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="c96c3-103">Gets the minimum number of threads that the host provides for processing I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c96c3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c96c3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMinThreads (  
    [out] DWORD *pdwMinIOCompletionThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c96c3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c96c3-105">Parameters</span></span>  

 `pdwMinIOCompletionThreads`  
 <span data-ttu-id="c96c3-106">заполняет Указатель на минимальное количество потоков, предоставляемых узлом для обработки запросов ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="c96c3-106">[out] A pointer to the minimum number of threads that the host provides to process I/O requests.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c96c3-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c96c3-107">Return Value</span></span>  
  
|<span data-ttu-id="c96c3-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c96c3-108">HRESULT</span></span>|<span data-ttu-id="c96c3-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="c96c3-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c96c3-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="c96c3-110">S_OK</span></span>|<span data-ttu-id="c96c3-111">`GetMinThreads` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="c96c3-111">`GetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="c96c3-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c96c3-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c96c3-113">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="c96c3-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c96c3-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c96c3-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c96c3-115">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="c96c3-115">The call timed out.</span></span>|  
|<span data-ttu-id="c96c3-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c96c3-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c96c3-117">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="c96c3-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c96c3-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c96c3-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c96c3-119">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="c96c3-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c96c3-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c96c3-120">E_FAIL</span></span>|<span data-ttu-id="c96c3-121">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="c96c3-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c96c3-122">Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="c96c3-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c96c3-123">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="c96c3-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="c96c3-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="c96c3-124">E_NOTIMPL</span></span>|<span data-ttu-id="c96c3-125">Узел не предоставляет реализацию `GetMinThreads` .</span><span class="sxs-lookup"><span data-stu-id="c96c3-125">The host does not provide an implementation of `GetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c96c3-126">Комментарии</span><span class="sxs-lookup"><span data-stu-id="c96c3-126">Remarks</span></span>  

 <span data-ttu-id="c96c3-127">Узлу может потребоваться эксклюзивный контроль над числом потоков, выделенных для запросов на обслуживание операций ввода-вывода, по таким причинам, как реализация, производительность или масштабируемость.</span><span class="sxs-lookup"><span data-stu-id="c96c3-127">A host might want exclusive control over the number of threads allotted to service I/O requests, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="c96c3-128">По этой причине узел не является обязательным для реализации `GetMinThreads` .</span><span class="sxs-lookup"><span data-stu-id="c96c3-128">For this reason, the host is not required to implement `GetMinThreads`.</span></span> <span data-ttu-id="c96c3-129">В этом случае узел должен вернуть E_NOTIMPL из этого метода.</span><span class="sxs-lookup"><span data-stu-id="c96c3-129">In this case, the host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c96c3-130">Требования</span><span class="sxs-lookup"><span data-stu-id="c96c3-130">Requirements</span></span>  

 <span data-ttu-id="c96c3-131">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c96c3-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c96c3-132">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="c96c3-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c96c3-133">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c96c3-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c96c3-134">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c96c3-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c96c3-135">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="c96c3-135">See also</span></span>

- [<span data-ttu-id="c96c3-136">Интерфейс ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="c96c3-136">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)
- [<span data-ttu-id="c96c3-137">Интерфейс IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="c96c3-137">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)
