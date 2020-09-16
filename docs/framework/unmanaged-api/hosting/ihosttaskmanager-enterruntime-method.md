---
title: Метод IHostTaskManager::EnterRuntime
ms.date: 03/30/2017
api_name:
- IHostTaskManager.EnterRuntime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::EnterRuntime
helpviewer_keywords:
- IHostTaskManager::EnterRuntime method [.NET Framework hosting]
- EnterRuntime method [.NET Framework hosting]
ms.assetid: 1aa7a4b1-636a-4f5e-b834-b406d72f7120
topic_type:
- apiref
ms.openlocfilehash: 1591a055200618f3e4951b5f6cf860dd3e71b44b
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90554362"
---
# <a name="ihosttaskmanagerenterruntime-method"></a><span data-ttu-id="1e761-102">Метод IHostTaskManager::EnterRuntime</span><span class="sxs-lookup"><span data-stu-id="1e761-102">IHostTaskManager::EnterRuntime Method</span></span>
<span data-ttu-id="1e761-103">Уведомляет узел о том, что вызов неуправляемого метода, например метода вызова платформы, возвращает управление выполнением среде CLR.</span><span class="sxs-lookup"><span data-stu-id="1e761-103">Notifies the host that a call to an unmanaged method, such as a platform invoke method, is returning execution control to the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e761-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1e761-104">Syntax</span></span>  
  
```cpp  
HRESULT EnterRuntime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="1e761-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="1e761-105">Return Value</span></span>  
  
|<span data-ttu-id="1e761-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1e761-106">HRESULT</span></span>|<span data-ttu-id="1e761-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="1e761-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1e761-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="1e761-108">S_OK</span></span>|<span data-ttu-id="1e761-109">`EnterRuntime` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="1e761-109">`EnterRuntime` returned successfully.</span></span>|  
|<span data-ttu-id="1e761-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1e761-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1e761-111">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="1e761-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1e761-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1e761-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1e761-113">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="1e761-113">The call timed out.</span></span>|  
|<span data-ttu-id="1e761-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1e761-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1e761-115">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="1e761-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1e761-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1e761-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1e761-117">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="1e761-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1e761-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1e761-118">E_FAIL</span></span>|<span data-ttu-id="1e761-119">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="1e761-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1e761-120">Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="1e761-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1e761-121">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="1e761-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="1e761-122">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="1e761-122">E_OUTOFMEMORY</span></span>|<span data-ttu-id="1e761-123">Недостаточно памяти для завершения запрошенного выделения.</span><span class="sxs-lookup"><span data-stu-id="1e761-123">Not enough memory was available to complete the requested allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1e761-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="1e761-124">Remarks</span></span>  
 <span data-ttu-id="1e761-125">`EnterRuntime` вызывается для уведомления узла о том, что неуправляемая функция, для которой был выполнен предыдущий вызов метода [леаверунтиме](ihosttaskmanager-leaveruntime-method.md) , завершила выполнение, и возвращает управление выполнением среде выполнения.</span><span class="sxs-lookup"><span data-stu-id="1e761-125">`EnterRuntime` is called to notify the host that an unmanaged function, for which an earlier call to the [LeaveRuntime](ihosttaskmanager-leaveruntime-method.md) method was made, has finished executing, and is returning execution control to the runtime.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1e761-126">[Реверсинтеррунтиме](ihosttaskmanager-reverseenterruntime-method.md) вызывается для уведомления узла о том, что неуправляемая функция, для которой `LeaveRuntime` был выполнен предыдущий вызов, делает вызов управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="1e761-126">[ReverseEnterRuntime](ihosttaskmanager-reverseenterruntime-method.md) is called to notify the host that an unmanaged function, for which an earlier call to `LeaveRuntime` was made, is making a call into managed code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1e761-127">Требования</span><span class="sxs-lookup"><span data-stu-id="1e761-127">Requirements</span></span>  
 <span data-ttu-id="1e761-128">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1e761-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1e761-129">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="1e761-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1e761-130">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1e761-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1e761-131">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1e761-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e761-132">См. также</span><span class="sxs-lookup"><span data-stu-id="1e761-132">See also</span></span>

- <span data-ttu-id="1e761-133">[Расширенное COM-взаимодействие](/previous-versions/dotnet/netframework-4.0/bd9cdfyx(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="1e761-133">[Advanced COM Interoperability](/previous-versions/dotnet/netframework-4.0/bd9cdfyx(v=vs.100))</span></span>
- [<span data-ttu-id="1e761-134">Инструкции. вызов собственных библиотек DLL из управляемого кода с помощью PInvoke</span><span class="sxs-lookup"><span data-stu-id="1e761-134">How to: Call Native DLLs from Managed Code Using PInvoke</span></span>](/cpp/dotnet/how-to-call-native-dlls-from-managed-code-using-pinvoke)
- [<span data-ttu-id="1e761-135">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="1e761-135">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="1e761-136">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="1e761-136">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="1e761-137">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="1e761-137">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="1e761-138">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="1e761-138">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="1e761-139">Метод LeaveRuntime</span><span class="sxs-lookup"><span data-stu-id="1e761-139">LeaveRuntime Method</span></span>](ihosttaskmanager-leaveruntime-method.md)
