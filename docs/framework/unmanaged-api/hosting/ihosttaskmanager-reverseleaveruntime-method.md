---
title: Метод IHostTaskManager::ReverseLeaveRuntime
ms.date: 03/30/2017
api_name:
- IHostTaskManager.ReverseLeaveRuntime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::ReverseLeaveRuntime
helpviewer_keywords:
- IHostTaskManager::ReverseLeaveRuntime method [.NET Framework hosting]
- ReverseLeaveRuntime method [.NET Framework hosting]
ms.assetid: 4837d398-16a1-4e32-902c-022cd1aad3ca
topic_type:
- apiref
ms.openlocfilehash: d328afcba9761f686dd38bdb2dd651994faaac2a
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/26/2020
ms.locfileid: "83841871"
---
# <a name="ihosttaskmanagerreverseleaveruntime-method"></a><span data-ttu-id="81e0c-102">Метод IHostTaskManager::ReverseLeaveRuntime</span><span class="sxs-lookup"><span data-stu-id="81e0c-102">IHostTaskManager::ReverseLeaveRuntime Method</span></span>
<span data-ttu-id="81e0c-103">Уведомляет узел, что элемент управления выходит из среды CLR и вводит неуправляемую функцию, которая, в свою очередь, вызывается из управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="81e0c-103">Notifies the host that control is leaving the common language runtime (CLR) and entering an unmanaged function that was, in turn, called from managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81e0c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="81e0c-104">Syntax</span></span>  
  
```cpp  
HRESULT ReverseLeaveRuntime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="81e0c-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="81e0c-105">Return Value</span></span>  
  
|<span data-ttu-id="81e0c-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="81e0c-106">HRESULT</span></span>|<span data-ttu-id="81e0c-107">Описание</span><span class="sxs-lookup"><span data-stu-id="81e0c-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="81e0c-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="81e0c-108">S_OK</span></span>|<span data-ttu-id="81e0c-109">`ReverseLeaveRuntime`успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="81e0c-109">`ReverseLeaveRuntime` returned successfully.</span></span>|  
|<span data-ttu-id="81e0c-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="81e0c-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="81e0c-111">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="81e0c-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="81e0c-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="81e0c-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="81e0c-113">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="81e0c-113">The call timed out.</span></span>|  
|<span data-ttu-id="81e0c-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="81e0c-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="81e0c-115">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="81e0c-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="81e0c-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="81e0c-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="81e0c-117">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="81e0c-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="81e0c-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="81e0c-118">E_FAIL</span></span>|<span data-ttu-id="81e0c-119">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="81e0c-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="81e0c-120">Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="81e0c-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="81e0c-121">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="81e0c-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="81e0c-122">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="81e0c-122">E_OUTOFMEMORY</span></span>|<span data-ttu-id="81e0c-123">Недостаточно памяти для завершения запрошенного выделения ресурсов.</span><span class="sxs-lookup"><span data-stu-id="81e0c-123">Not enough memory is available to complete the requested resource allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="81e0c-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="81e0c-124">Remarks</span></span>  
 <span data-ttu-id="81e0c-125">Вызовы CLR `ReverseLeaveRuntime` для информирования основного приложения о том, что выполняемая в данный момент задача возвращает управление неуправляемой функции, которая, в свою очередь, вызывается из управляемого кода через вызов платформы.</span><span class="sxs-lookup"><span data-stu-id="81e0c-125">The CLR calls `ReverseLeaveRuntime` to inform the host that the currently executing task is returning control to an unmanaged function that was, in turn, called from managed code through platform invoke.</span></span> <span data-ttu-id="81e0c-126">Каждый вызов `ReverseLeaveRuntime` соответствует соответствующему вызову [реверсинтеррунтиме](ihosttaskmanager-reverseenterruntime-method.md).</span><span class="sxs-lookup"><span data-stu-id="81e0c-126">Each call to `ReverseLeaveRuntime` matches a corresponding call to [ReverseEnterRuntime](ihosttaskmanager-reverseenterruntime-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="81e0c-127">Требования</span><span class="sxs-lookup"><span data-stu-id="81e0c-127">Requirements</span></span>  
 <span data-ttu-id="81e0c-128">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="81e0c-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81e0c-129">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="81e0c-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="81e0c-130">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="81e0c-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="81e0c-131">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81e0c-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81e0c-132">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="81e0c-132">See also</span></span>

- [<span data-ttu-id="81e0c-133">Метод CallNeedsHostHook</span><span class="sxs-lookup"><span data-stu-id="81e0c-133">CallNeedsHostHook Method</span></span>](ihosttaskmanager-callneedshosthook-method.md)
- [<span data-ttu-id="81e0c-134">Метод EnterRuntime</span><span class="sxs-lookup"><span data-stu-id="81e0c-134">EnterRuntime Method</span></span>](ihosttaskmanager-enterruntime-method.md)
- [<span data-ttu-id="81e0c-135">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="81e0c-135">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="81e0c-136">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="81e0c-136">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="81e0c-137">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="81e0c-137">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="81e0c-138">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="81e0c-138">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="81e0c-139">Метод LeaveRuntime</span><span class="sxs-lookup"><span data-stu-id="81e0c-139">LeaveRuntime Method</span></span>](ihosttaskmanager-leaveruntime-method.md)
- <span data-ttu-id="81e0c-140">[Более подробное рассмотрение вызова неуправляемого кода](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/0h9e9t7d(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="81e0c-140">[A Closer Look at Platform Invoke](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/0h9e9t7d(v=vs.100))</span></span>
