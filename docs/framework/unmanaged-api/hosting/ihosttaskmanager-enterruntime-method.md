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
ms.openlocfilehash: b255a1d35aa32975c879aac00f7d4edb8ea88d3b
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/26/2020
ms.locfileid: "83842040"
---
# <a name="ihosttaskmanagerenterruntime-method"></a><span data-ttu-id="d9c40-102">Метод IHostTaskManager::EnterRuntime</span><span class="sxs-lookup"><span data-stu-id="d9c40-102">IHostTaskManager::EnterRuntime Method</span></span>
<span data-ttu-id="d9c40-103">Уведомляет узел о том, что вызов неуправляемого метода, например метода вызова платформы, возвращает управление выполнением среде CLR.</span><span class="sxs-lookup"><span data-stu-id="d9c40-103">Notifies the host that a call to an unmanaged method, such as a platform invoke method, is returning execution control to the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9c40-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d9c40-104">Syntax</span></span>  
  
```cpp  
HRESULT EnterRuntime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="d9c40-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d9c40-105">Return Value</span></span>  
  
|<span data-ttu-id="d9c40-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d9c40-106">HRESULT</span></span>|<span data-ttu-id="d9c40-107">Описание</span><span class="sxs-lookup"><span data-stu-id="d9c40-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d9c40-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="d9c40-108">S_OK</span></span>|<span data-ttu-id="d9c40-109">`EnterRuntime`успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="d9c40-109">`EnterRuntime` returned successfully.</span></span>|  
|<span data-ttu-id="d9c40-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d9c40-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d9c40-111">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="d9c40-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d9c40-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d9c40-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d9c40-113">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="d9c40-113">The call timed out.</span></span>|  
|<span data-ttu-id="d9c40-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d9c40-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d9c40-115">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="d9c40-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d9c40-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d9c40-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d9c40-117">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="d9c40-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d9c40-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d9c40-118">E_FAIL</span></span>|<span data-ttu-id="d9c40-119">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="d9c40-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d9c40-120">Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="d9c40-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d9c40-121">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="d9c40-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="d9c40-122">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="d9c40-122">E_OUTOFMEMORY</span></span>|<span data-ttu-id="d9c40-123">Недостаточно памяти для завершения запрошенного выделения.</span><span class="sxs-lookup"><span data-stu-id="d9c40-123">Not enough memory was available to complete the requested allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d9c40-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="d9c40-124">Remarks</span></span>  
 <span data-ttu-id="d9c40-125">`EnterRuntime`вызывается для уведомления узла о том, что неуправляемая функция, для которой был выполнен предыдущий вызов метода [леаверунтиме](ihosttaskmanager-leaveruntime-method.md) , завершила выполнение, и возвращает управление выполнением среде выполнения.</span><span class="sxs-lookup"><span data-stu-id="d9c40-125">`EnterRuntime` is called to notify the host that an unmanaged function, for which an earlier call to the [LeaveRuntime](ihosttaskmanager-leaveruntime-method.md) method was made, has finished executing, and is returning execution control to the runtime.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d9c40-126">[Реверсинтеррунтиме](ihosttaskmanager-reverseenterruntime-method.md) вызывается для уведомления узла о том, что неуправляемая функция, для которой `LeaveRuntime` был выполнен предыдущий вызов, делает вызов управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="d9c40-126">[ReverseEnterRuntime](ihosttaskmanager-reverseenterruntime-method.md) is called to notify the host that an unmanaged function, for which an earlier call to `LeaveRuntime` was made, is making a call into managed code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9c40-127">Требования</span><span class="sxs-lookup"><span data-stu-id="d9c40-127">Requirements</span></span>  
 <span data-ttu-id="d9c40-128">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d9c40-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9c40-129">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="d9c40-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d9c40-130">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="d9c40-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d9c40-131">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d9c40-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9c40-132">См. также</span><span class="sxs-lookup"><span data-stu-id="d9c40-132">See also</span></span>

- <span data-ttu-id="d9c40-133">[Расширенное COM-взаимодействие](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bd9cdfyx(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="d9c40-133">[Advanced COM Interoperability](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bd9cdfyx(v=vs.100))</span></span>
- [<span data-ttu-id="d9c40-134">Инструкции. вызов собственных библиотек DLL из управляемого кода с помощью PInvoke</span><span class="sxs-lookup"><span data-stu-id="d9c40-134">How to: Call Native DLLs from Managed Code Using PInvoke</span></span>](/cpp/dotnet/how-to-call-native-dlls-from-managed-code-using-pinvoke)
- [<span data-ttu-id="d9c40-135">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="d9c40-135">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="d9c40-136">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="d9c40-136">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="d9c40-137">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="d9c40-137">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="d9c40-138">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="d9c40-138">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="d9c40-139">Метод LeaveRuntime</span><span class="sxs-lookup"><span data-stu-id="d9c40-139">LeaveRuntime Method</span></span>](ihosttaskmanager-leaveruntime-method.md)
