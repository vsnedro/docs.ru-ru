---
title: Метод ICLRTask::SetTaskIdentifier
ms.date: 03/30/2017
api_name:
- ICLRTask.SetTaskIdentifier
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::SetTaskIdentifier
helpviewer_keywords:
- SetTaskIdentifier method [.NET Framework hosting]
- ICLRTask::SetTaskIdentifier method [.NET Framework hosting]
ms.assetid: bdb7f047-1e90-40fc-9e3b-d44a16509073
topic_type:
- apiref
ms.openlocfilehash: d1f731e00d4917b997dfba392cb9b6ce2afc082e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95690750"
---
# <a name="iclrtasksettaskidentifier-method"></a><span data-ttu-id="3f30d-102">Метод ICLRTask::SetTaskIdentifier</span><span class="sxs-lookup"><span data-stu-id="3f30d-102">ICLRTask::SetTaskIdentifier Method</span></span>

<span data-ttu-id="3f30d-103">Инструктирует среду CLR, чтобы связать указанное значение идентификатора с задачей, представленной текущим экземпляром [ICLRTask](iclrtask-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="3f30d-103">Instructs the common language runtime (CLR) to associate the specified identifier value with the task represented by the current [ICLRTask](iclrtask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f30d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3f30d-104">Syntax</span></span>  
  
```cpp  
HRESULT SetTaskIdentifier (  
    [in] DWORD Asked  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3f30d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3f30d-105">Parameters</span></span>  

 `Asked`  
 <span data-ttu-id="3f30d-106">окне Уникальный идентификатор среды CLR, связываемый с задачей, представленной текущим `ICLRTask` экземпляром.</span><span class="sxs-lookup"><span data-stu-id="3f30d-106">[in] The unique identifier for the common language runtime to associate with the task represented by the current `ICLRTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3f30d-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3f30d-107">Return Value</span></span>  
  
|<span data-ttu-id="3f30d-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3f30d-108">HRESULT</span></span>|<span data-ttu-id="3f30d-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="3f30d-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3f30d-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="3f30d-110">S_OK</span></span>|<span data-ttu-id="3f30d-111">`SetTaskIdentifier` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="3f30d-111">`SetTaskIdentifier` returned successfully.</span></span>|  
|<span data-ttu-id="3f30d-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3f30d-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3f30d-113">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="3f30d-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3f30d-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3f30d-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3f30d-115">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="3f30d-115">The call timed out.</span></span>|  
|<span data-ttu-id="3f30d-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3f30d-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3f30d-117">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="3f30d-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3f30d-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3f30d-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3f30d-119">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="3f30d-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3f30d-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3f30d-120">E_FAIL</span></span>|<span data-ttu-id="3f30d-121">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="3f30d-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3f30d-122">Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="3f30d-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3f30d-123">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="3f30d-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3f30d-124">Комментарии</span><span class="sxs-lookup"><span data-stu-id="3f30d-124">Remarks</span></span>  

 <span data-ttu-id="3f30d-125">Узел может связать идентификатор с задачей, чтобы упростить интеграцию среды CLR и узла в среде отладки.</span><span class="sxs-lookup"><span data-stu-id="3f30d-125">The host can associate an identifier with a task to help integrate the CLR and the host in a debugging environment.</span></span> <span data-ttu-id="3f30d-126">Идентификатор не имеет смысла для CLR.</span><span class="sxs-lookup"><span data-stu-id="3f30d-126">The identifier has no meaning for the CLR.</span></span> <span data-ttu-id="3f30d-127">Среда CLR передает ее в приложение отладчика.</span><span class="sxs-lookup"><span data-stu-id="3f30d-127">The CLR passes it along to a debugger application.</span></span> <span data-ttu-id="3f30d-128">Отладчик может использовать этот идентификатор для связывания стека вызовов CLR с стеком вызовов узла и включения соответствующей информации трассировки при просмотре в пользовательском интерфейсе отладчика.</span><span class="sxs-lookup"><span data-stu-id="3f30d-128">The debugger can use this identifier to associate a CLR call stack with a host call stack, and enable their respective trace information to be unified when viewed in the debugger's user interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f30d-129">Требования</span><span class="sxs-lookup"><span data-stu-id="3f30d-129">Requirements</span></span>  

 <span data-ttu-id="3f30d-130">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3f30d-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f30d-131">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="3f30d-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3f30d-132">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3f30d-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3f30d-133">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f30d-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f30d-134">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="3f30d-134">See also</span></span>

- [<span data-ttu-id="3f30d-135">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="3f30d-135">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="3f30d-136">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="3f30d-136">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="3f30d-137">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="3f30d-137">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="3f30d-138">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="3f30d-138">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
