---
title: Метод IHostThreadPoolManager::GetAvailableThreads
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager.GetAvailableThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager::GetAvailableThreads
helpviewer_keywords:
- GetAvailableThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
- IHostThreadPoolManager::GetAvailableThreads method [.NET Framework hosting]
ms.assetid: 61d26dfd-7f24-4e7d-a63e-b30a463f08e1
topic_type:
- apiref
ms.openlocfilehash: cc03960c2d45a6cf8aed58eaf048a0531decb08f
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/26/2020
ms.locfileid: "83842339"
---
# <a name="ihostthreadpoolmanagergetavailablethreads-method"></a><span data-ttu-id="a0c18-102">Метод IHostThreadPoolManager::GetAvailableThreads</span><span class="sxs-lookup"><span data-stu-id="a0c18-102">IHostThreadPoolManager::GetAvailableThreads Method</span></span>
<span data-ttu-id="a0c18-103">Возвращает число потоков в пуле потоков, которые в данный момент не обрабатывают рабочие элементы.</span><span class="sxs-lookup"><span data-stu-id="a0c18-103">Gets the number of threads in the thread pool that are not currently processing work items.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0c18-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a0c18-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAvailableThreads (  
    [out] DWORD *pdwAvailableWorkerThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a0c18-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a0c18-105">Parameters</span></span>  
 `pdwAvailableWorkerThreads`  
 <span data-ttu-id="a0c18-106">заполняет Указатель на число потоков в пуле потоков, которые в данный момент не обрабатывают рабочие элементы.</span><span class="sxs-lookup"><span data-stu-id="a0c18-106">[out] Pointer to the number of threads in the thread pool that are not currently processing work items.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a0c18-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a0c18-107">Return Value</span></span>  
  
|<span data-ttu-id="a0c18-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a0c18-108">HRESULT</span></span>|<span data-ttu-id="a0c18-109">Описание</span><span class="sxs-lookup"><span data-stu-id="a0c18-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a0c18-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="a0c18-110">S_OK</span></span>|<span data-ttu-id="a0c18-111">`GetAvailableThreads`успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="a0c18-111">`GetAvailableThreads` returned successfully.</span></span>|  
|<span data-ttu-id="a0c18-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a0c18-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a0c18-113">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="a0c18-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a0c18-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a0c18-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a0c18-115">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="a0c18-115">The call timed out.</span></span>|  
|<span data-ttu-id="a0c18-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a0c18-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a0c18-117">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="a0c18-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a0c18-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a0c18-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a0c18-119">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="a0c18-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a0c18-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a0c18-120">E_FAIL</span></span>|<span data-ttu-id="a0c18-121">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="a0c18-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a0c18-122">Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="a0c18-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a0c18-123">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="a0c18-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="a0c18-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="a0c18-124">E_NOTIMPL</span></span>|<span data-ttu-id="a0c18-125">Узел не предоставляет реализацию `GetAvailableThreads` .</span><span class="sxs-lookup"><span data-stu-id="a0c18-125">The host does not provide an implementation of `GetAvailableThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a0c18-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="a0c18-126">Remarks</span></span>  
 <span data-ttu-id="a0c18-127">Если узел не предоставляет реализацию `GetAvailableThreads` , он должен возвращать значение HRESULT, равное E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="a0c18-127">If the host does not provide an implementation of `GetAvailableThreads`, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0c18-128">Требования</span><span class="sxs-lookup"><span data-stu-id="a0c18-128">Requirements</span></span>  
 <span data-ttu-id="a0c18-129">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a0c18-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0c18-130">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="a0c18-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a0c18-131">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="a0c18-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a0c18-132">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0c18-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0c18-133">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="a0c18-133">See also</span></span>

- <xref:System.Threading.ThreadPool.GetAvailableThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="a0c18-134">Интерфейс IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="a0c18-134">IHostThreadPoolManager Interface</span></span>](ihostthreadpoolmanager-interface.md)
