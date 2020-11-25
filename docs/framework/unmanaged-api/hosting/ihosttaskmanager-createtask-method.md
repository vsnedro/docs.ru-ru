---
title: Метод IHostTaskManager::CreateTask
ms.date: 03/30/2017
api_name:
- IHostTaskManager.CreateTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::CreateTask
helpviewer_keywords:
- CreateTask method, IHostTaskManager interface [.NET Framework hosting]
- IHostTaskManager::CreateTask method [.NET Framework hosting]
ms.assetid: a6f8ad36-61e1-42b0-9db2-add575646d18
topic_type:
- apiref
ms.openlocfilehash: 7fdf25d44bdf630e306cf0f5dcb3387a3b0f7c76
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731687"
---
# <a name="ihosttaskmanagercreatetask-method"></a><span data-ttu-id="47b4a-102">Метод IHostTaskManager::CreateTask</span><span class="sxs-lookup"><span data-stu-id="47b4a-102">IHostTaskManager::CreateTask Method</span></span>

<span data-ttu-id="47b4a-103">Запрашивает создание новой задачи узлом.</span><span class="sxs-lookup"><span data-stu-id="47b4a-103">Requests that the host create a new task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47b4a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="47b4a-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateTask (  
    [in]  DWORD stacksize,
    [in]  LPTHREAD_START_ROUTINE pStartAddress,  
    [in]  PVOID pParameter,  
    [out] IHostTask **ppTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="47b4a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="47b4a-105">Parameters</span></span>  

 `stacksize`  
 <span data-ttu-id="47b4a-106">окне Запрошенный размер (в байтах) запрошенного стека или 0 (ноль) для размера по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="47b4a-106">[in] The requested size, in bytes, of the requested stack, or 0 (zero) for the default size.</span></span>  
  
 `pStartAddress`  
 <span data-ttu-id="47b4a-107">окне Указатель на функцию, которая должна быть выполнена задачей.</span><span class="sxs-lookup"><span data-stu-id="47b4a-107">[in] A pointer to the function the task is to execute.</span></span>  
  
 `pParameter`  
 <span data-ttu-id="47b4a-108">окне Указатель на пользовательские данные, передаваемые в функцию, или значение null, если функция не принимает параметры.</span><span class="sxs-lookup"><span data-stu-id="47b4a-108">[in] A pointer to the user data to be passed to the function, or null if the function takes no parameters.</span></span>  
  
 `ppTask`  
 <span data-ttu-id="47b4a-109">заполняет Указатель на адрес экземпляра [IHostTask](ihosttask-interface.md) , созданного узлом, или значение null, если задача не может быть создана.</span><span class="sxs-lookup"><span data-stu-id="47b4a-109">[out] A pointer to the address of an [IHostTask](ihosttask-interface.md) instance created by the host, or null if the task cannot be created.</span></span> <span data-ttu-id="47b4a-110">Задача остается в приостановленном состоянии до тех пор, пока она не будет явно запущена вызовом [IHostTask:: Start](ihosttask-start-method.md).</span><span class="sxs-lookup"><span data-stu-id="47b4a-110">The task remains in a suspended state until it is explicitly started by a call to [IHostTask::Start](ihosttask-start-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="47b4a-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="47b4a-111">Return Value</span></span>  
  
|<span data-ttu-id="47b4a-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="47b4a-112">HRESULT</span></span>|<span data-ttu-id="47b4a-113">Описание:</span><span class="sxs-lookup"><span data-stu-id="47b4a-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="47b4a-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="47b4a-114">S_OK</span></span>|<span data-ttu-id="47b4a-115">`CreateTask` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="47b4a-115">`CreateTask` returned successfully.</span></span>|  
|<span data-ttu-id="47b4a-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="47b4a-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="47b4a-117">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="47b4a-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="47b4a-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="47b4a-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="47b4a-119">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="47b4a-119">The call timed out.</span></span>|  
|<span data-ttu-id="47b4a-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="47b4a-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="47b4a-121">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="47b4a-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="47b4a-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="47b4a-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="47b4a-123">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="47b4a-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="47b4a-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="47b4a-124">E_FAIL</span></span>|<span data-ttu-id="47b4a-125">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="47b4a-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="47b4a-126">Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="47b4a-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="47b4a-127">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="47b4a-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="47b4a-128">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="47b4a-128">E_OUTOFMEMORY</span></span>|<span data-ttu-id="47b4a-129">Недостаточно свободной памяти для создания запрошенной задачи.</span><span class="sxs-lookup"><span data-stu-id="47b4a-129">Not enough memory was available to create the requested task.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="47b4a-130">Комментарии</span><span class="sxs-lookup"><span data-stu-id="47b4a-130">Remarks</span></span>  

 <span data-ttu-id="47b4a-131">Вызовы CLR `CreateTask` для запроса создания новой задачи узлом.</span><span class="sxs-lookup"><span data-stu-id="47b4a-131">The CLR calls `CreateTask` to request that the host create a new task.</span></span> <span data-ttu-id="47b4a-132">Узел возвращает указатель интерфейса на `IHostTask` экземпляр.</span><span class="sxs-lookup"><span data-stu-id="47b4a-132">The host returns an interface pointer to an `IHostTask` instance.</span></span> <span data-ttu-id="47b4a-133">Возвращаемая задача должна оставаться приостановленной до тех пор, пока она не будет явно запущена вызовом метода `IHostTask::Start` .</span><span class="sxs-lookup"><span data-stu-id="47b4a-133">The returned task must remain suspended until it is explicitly started by a call to `IHostTask::Start`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="47b4a-134">Требования</span><span class="sxs-lookup"><span data-stu-id="47b4a-134">Requirements</span></span>  

 <span data-ttu-id="47b4a-135">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="47b4a-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47b4a-136">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="47b4a-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="47b4a-137">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="47b4a-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="47b4a-138">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="47b4a-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47b4a-139">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="47b4a-139">See also</span></span>

- [<span data-ttu-id="47b4a-140">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="47b4a-140">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="47b4a-141">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="47b4a-141">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="47b4a-142">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="47b4a-142">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="47b4a-143">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="47b4a-143">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
