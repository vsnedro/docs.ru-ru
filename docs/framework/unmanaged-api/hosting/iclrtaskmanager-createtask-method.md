---
title: Метод ICLRTaskManager::CreateTask
ms.date: 03/30/2017
api_name:
- ICLRTaskManager.CreateTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTaskManager::CreateTask
helpviewer_keywords:
- ICLRTaskManager::CreateTask method [.NET Framework hosting]
- CreateTask method, ICLRTaskManager interface [.NET Framework hosting]
ms.assetid: eea570d9-2e53-4320-9ea0-eb777bf9dcf3
topic_type:
- apiref
ms.openlocfilehash: c8d18b78cf0185271eae763892610d13f76e42ab
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95734001"
---
# <a name="iclrtaskmanagercreatetask-method"></a><span data-ttu-id="98d81-102">Метод ICLRTaskManager::CreateTask</span><span class="sxs-lookup"><span data-stu-id="98d81-102">ICLRTaskManager::CreateTask Method</span></span>

<span data-ttu-id="98d81-103">Явно запрашивает создание новой задачи средой CLR.</span><span class="sxs-lookup"><span data-stu-id="98d81-103">Requests explicitly that the common language runtime (CLR) create a new task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98d81-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="98d81-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateTask (  
    [out] ICLRTask **pTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="98d81-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="98d81-105">Parameters</span></span>  

 `pTask`  
 <span data-ttu-id="98d81-106">заполняет Указатель на адрес только что созданного файла [ICLRTask](iclrtask-interface.md)или значение null, если задачу не удалось создать.</span><span class="sxs-lookup"><span data-stu-id="98d81-106">[out] A pointer to the address of a newly created [ICLRTask](iclrtask-interface.md), or null, if the task could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="98d81-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="98d81-107">Return Value</span></span>  
  
|<span data-ttu-id="98d81-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="98d81-108">HRESULT</span></span>|<span data-ttu-id="98d81-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="98d81-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="98d81-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="98d81-110">S_OK</span></span>|<span data-ttu-id="98d81-111">Метод возвратился успешно.</span><span class="sxs-lookup"><span data-stu-id="98d81-111">The method returned successfully.</span></span>|  
|<span data-ttu-id="98d81-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="98d81-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="98d81-113">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="98d81-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="98d81-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="98d81-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="98d81-115">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="98d81-115">The call timed out.</span></span>|  
|<span data-ttu-id="98d81-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="98d81-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="98d81-117">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="98d81-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="98d81-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="98d81-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="98d81-119">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="98d81-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="98d81-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="98d81-120">E_FAIL</span></span>|<span data-ttu-id="98d81-121">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="98d81-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="98d81-122">Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="98d81-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="98d81-123">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="98d81-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="98d81-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="98d81-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="98d81-125">Недостаточно памяти для выделения запрошенного ресурса.</span><span class="sxs-lookup"><span data-stu-id="98d81-125">Not enough memory is available to allocate the requested resource.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="98d81-126">Комментарии</span><span class="sxs-lookup"><span data-stu-id="98d81-126">Remarks</span></span>  

 <span data-ttu-id="98d81-127">Среда CLR автоматически создает новую задачу при инициализации, когда пользовательский код создает поток с помощью типов в <xref:System.Threading> пространстве имен или увеличивается размер пула потоков.</span><span class="sxs-lookup"><span data-stu-id="98d81-127">The CLR creates a new task automatically upon initialization, when user code creates a thread by using types in the <xref:System.Threading> namespace, or when the size of the thread pool is increased.</span></span> <span data-ttu-id="98d81-128">Он также создает задачи, когда неуправляемый код вызывает управляемую функцию.</span><span class="sxs-lookup"><span data-stu-id="98d81-128">It also creates tasks when unmanaged code makes a call to a managed function.</span></span>  
  
 <span data-ttu-id="98d81-129">`CreateTask` позволяет узлу выполнить явный запрос о том, что среда CLR создает новую задачу.</span><span class="sxs-lookup"><span data-stu-id="98d81-129">`CreateTask` allows the host to make an explicit request that the CLR create a new task.</span></span> <span data-ttu-id="98d81-130">Например, узел может вызвать этот метод для прединициализации структур данных.</span><span class="sxs-lookup"><span data-stu-id="98d81-130">For example, the host can invoke this method to preinitialize data structures.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="98d81-131">Новая задача возвращается в приостановленном состоянии и остается приостановленной до тех пор, пока узел явно не вызывает метод [IHostTask:: Start](ihosttask-start-method.md).</span><span class="sxs-lookup"><span data-stu-id="98d81-131">The new task is returned in a suspended state and remains suspended until the host explicitly calls [IHostTask::Start](ihosttask-start-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="98d81-132">Требования</span><span class="sxs-lookup"><span data-stu-id="98d81-132">Requirements</span></span>  

 <span data-ttu-id="98d81-133">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="98d81-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98d81-134">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="98d81-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="98d81-135">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="98d81-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="98d81-136">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98d81-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98d81-137">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="98d81-137">See also</span></span>

- [<span data-ttu-id="98d81-138">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="98d81-138">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="98d81-139">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="98d81-139">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="98d81-140">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="98d81-140">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="98d81-141">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="98d81-141">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
