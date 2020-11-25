---
title: Метод IHostTaskManager::SwitchToTask
ms.date: 03/30/2017
api_name:
- IHostTaskManager.SwitchToTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::SwitchToTask
helpviewer_keywords:
- IHostTaskManager::SwitchToTask method [.NET Framework hosting]
- SwitchToTask method [.NET Framework hosting]
ms.assetid: 35d0c27e-4b14-49ce-810d-7ab2120177e8
topic_type:
- apiref
ms.openlocfilehash: bf3ddd91a58669540ef310e268162ec78408494f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702033"
---
# <a name="ihosttaskmanagerswitchtotask-method"></a><span data-ttu-id="275b3-102">Метод IHostTaskManager::SwitchToTask</span><span class="sxs-lookup"><span data-stu-id="275b3-102">IHostTaskManager::SwitchToTask Method</span></span>

<span data-ttu-id="275b3-103">Уведомляет узел о том, что необходимо отключить текущую задачу.</span><span class="sxs-lookup"><span data-stu-id="275b3-103">Notifies the host that it should switch out the current task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="275b3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="275b3-104">Syntax</span></span>  
  
```cpp  
HRESULT SwitchToTask (  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="275b3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="275b3-105">Parameters</span></span>  

 `option`  
 <span data-ttu-id="275b3-106">окне Одно из значений перечисления [WAIT_OPTION](wait-option-enumeration.md) , указывающее действие, которое должен выполнить узел, если запрошенная операция блокируется.</span><span class="sxs-lookup"><span data-stu-id="275b3-106">[in] One of the [WAIT_OPTION](wait-option-enumeration.md) enumeration values, indicating the action the host should take if the requested operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="275b3-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="275b3-107">Return Value</span></span>  
  
|<span data-ttu-id="275b3-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="275b3-108">HRESULT</span></span>|<span data-ttu-id="275b3-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="275b3-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="275b3-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="275b3-110">S_OK</span></span>|<span data-ttu-id="275b3-111">`SwitchToTask` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="275b3-111">`SwitchToTask` returned successfully.</span></span>|  
|<span data-ttu-id="275b3-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="275b3-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="275b3-113">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="275b3-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="275b3-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="275b3-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="275b3-115">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="275b3-115">The call timed out.</span></span>|  
|<span data-ttu-id="275b3-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="275b3-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="275b3-117">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="275b3-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="275b3-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="275b3-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="275b3-119">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="275b3-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="275b3-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="275b3-120">E_FAIL</span></span>|<span data-ttu-id="275b3-121">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="275b3-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="275b3-122">Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="275b3-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="275b3-123">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="275b3-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="275b3-124">Комментарии</span><span class="sxs-lookup"><span data-stu-id="275b3-124">Remarks</span></span>  

 <span data-ttu-id="275b3-125">Узел может переключиться на другую задачу по мере необходимости или необходимости.</span><span class="sxs-lookup"><span data-stu-id="275b3-125">The host can switch in another task as desired or needed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="275b3-126">`SwitchToTask` не указывает, к какой задаче узел должен переключиться; Он указывает только задачу, с которой она должна переключаться.</span><span class="sxs-lookup"><span data-stu-id="275b3-126">`SwitchToTask` does not specify which task the host should switch to; it specifies only the task that it should switch from.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="275b3-127">Требования</span><span class="sxs-lookup"><span data-stu-id="275b3-127">Requirements</span></span>  

 <span data-ttu-id="275b3-128">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="275b3-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="275b3-129">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="275b3-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="275b3-130">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="275b3-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="275b3-131">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="275b3-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="275b3-132">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="275b3-132">See also</span></span>

- [<span data-ttu-id="275b3-133">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="275b3-133">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="275b3-134">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="275b3-134">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="275b3-135">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="275b3-135">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="275b3-136">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="275b3-136">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
