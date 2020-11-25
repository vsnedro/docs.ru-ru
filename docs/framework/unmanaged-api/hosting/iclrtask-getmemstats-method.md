---
title: Метод ICLRTask::GetMemStats
ms.date: 03/30/2017
api_name:
- ICLRTask.GetMemStats
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::GetMemStats
helpviewer_keywords:
- ICLRTask::GetMemStats method [.NET Framework hosting]
- GetMemStats method [.NET Framework hosting]
ms.assetid: c9e07657-1682-4c30-a336-f8658ff1a125
topic_type:
- apiref
ms.openlocfilehash: 5d57bc742ebcba00f9fbe569a4be27b82a5f8055
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726513"
---
# <a name="iclrtaskgetmemstats-method"></a><span data-ttu-id="b0fa5-102">Метод ICLRTask::GetMemStats</span><span class="sxs-lookup"><span data-stu-id="b0fa5-102">ICLRTask::GetMemStats Method</span></span>

<span data-ttu-id="b0fa5-103">Возвращает статистические сведения об использовании памяти, связанные с задачей, которую представляет текущий экземпляр [ICLRTask](iclrtask-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="b0fa5-103">Gets statistical memory usage information related to the task that the current [ICLRTask](iclrtask-interface.md) instance represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0fa5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b0fa5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMemStats (  
    [out] COR_GC_THREAD_STATS *pMemUsage  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b0fa5-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b0fa5-105">Parameters</span></span>  

 `pMemUsage`  
 <span data-ttu-id="b0fa5-106">заполняет Указатель на экземпляр [COR_GC_THREAD_STATS](cor-gc-thread-stats-structure.md) , содержащий сведения об использовании памяти задачей, включая число выделенных байтов.</span><span class="sxs-lookup"><span data-stu-id="b0fa5-106">[out] A pointer to a [COR_GC_THREAD_STATS](cor-gc-thread-stats-structure.md) instance that contains details about the memory usage of the task, including the number of bytes allocated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b0fa5-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b0fa5-107">Return Value</span></span>  
  
|<span data-ttu-id="b0fa5-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b0fa5-108">HRESULT</span></span>|<span data-ttu-id="b0fa5-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="b0fa5-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b0fa5-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="b0fa5-110">S_OK</span></span>|<span data-ttu-id="b0fa5-111">`GetMemStats` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="b0fa5-111">`GetMemStats` returned successfully.</span></span>|  
|<span data-ttu-id="b0fa5-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b0fa5-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b0fa5-113">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="b0fa5-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b0fa5-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b0fa5-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b0fa5-115">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="b0fa5-115">The call timed out.</span></span>|  
|<span data-ttu-id="b0fa5-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b0fa5-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b0fa5-117">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="b0fa5-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b0fa5-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b0fa5-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b0fa5-119">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="b0fa5-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b0fa5-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b0fa5-120">E_FAIL</span></span>|<span data-ttu-id="b0fa5-121">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="b0fa5-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b0fa5-122">Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="b0fa5-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b0fa5-123">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="b0fa5-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b0fa5-124">Требования</span><span class="sxs-lookup"><span data-stu-id="b0fa5-124">Requirements</span></span>  

 <span data-ttu-id="b0fa5-125">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b0fa5-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0fa5-126">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="b0fa5-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b0fa5-127">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b0fa5-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b0fa5-128">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0fa5-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0fa5-129">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b0fa5-129">See also</span></span>

- [<span data-ttu-id="b0fa5-130">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="b0fa5-130">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="b0fa5-131">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="b0fa5-131">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="b0fa5-132">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="b0fa5-132">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="b0fa5-133">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="b0fa5-133">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
