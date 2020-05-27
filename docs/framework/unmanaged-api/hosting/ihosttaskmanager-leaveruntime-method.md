---
title: Метод IHostTaskManager::LeaveRuntime
ms.date: 03/30/2017
api_name:
- IHostTaskManager.LeaveRuntime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::LeaveRuntime
helpviewer_keywords:
- IHostTaskManager::LeaveRuntime method [.NET Framework hosting]
- LeaveRuntime method [.NET Framework hosting]
ms.assetid: 43689cc4-e48e-46e5-a22d-bafd768b8759
topic_type:
- apiref
ms.openlocfilehash: 2939f13933c4681e7e2220e5290e019e10c2844e
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/26/2020
ms.locfileid: "83841923"
---
# <a name="ihosttaskmanagerleaveruntime-method"></a><span data-ttu-id="b3149-102">Метод IHostTaskManager::LeaveRuntime</span><span class="sxs-lookup"><span data-stu-id="b3149-102">IHostTaskManager::LeaveRuntime Method</span></span>
<span data-ttu-id="b3149-103">Уведомляет основное приложение о том, что Текущая выполняемая задача собирается покинуть среду CLR, и введите неуправляемый код.</span><span class="sxs-lookup"><span data-stu-id="b3149-103">Notifies the host that the currently executing task is about to leave the common language runtime (CLR) and enter unmanaged code.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="b3149-104">Соответствующий вызов [IHostTaskManager:: EnterRuntime](ihosttaskmanager-enterruntime-method.md) уведомляет основное приложение о том, что выполняемая в данный момент задача повторно вводит управляемый код.</span><span class="sxs-lookup"><span data-stu-id="b3149-104">A corresponding call to [IHostTaskManager::EnterRuntime](ihosttaskmanager-enterruntime-method.md) notifies the host that the currently executing task is reentering managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3149-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b3149-105">Syntax</span></span>  
  
```cpp  
HRESULT LeaveRuntime (  
    [in] SIZE_T target  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b3149-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="b3149-106">Parameters</span></span>  
 `target`  
 <span data-ttu-id="b3149-107">окне Адрес в сопоставленном переносимом исполняемом файле неуправляемой функции для вызова.</span><span class="sxs-lookup"><span data-stu-id="b3149-107">[in] The address within the mapped portable executable file of the unmanaged function to be called.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b3149-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b3149-108">Return Value</span></span>  
  
|<span data-ttu-id="b3149-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b3149-109">HRESULT</span></span>|<span data-ttu-id="b3149-110">Описание</span><span class="sxs-lookup"><span data-stu-id="b3149-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b3149-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="b3149-111">S_OK</span></span>|<span data-ttu-id="b3149-112">`LeaveRuntime`успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="b3149-112">`LeaveRuntime` returned successfully.</span></span>|  
|<span data-ttu-id="b3149-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b3149-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b3149-114">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="b3149-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b3149-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b3149-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b3149-116">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="b3149-116">The call timed out.</span></span>|  
|<span data-ttu-id="b3149-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b3149-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b3149-118">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="b3149-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b3149-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b3149-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b3149-120">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="b3149-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b3149-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b3149-121">E_FAIL</span></span>|<span data-ttu-id="b3149-122">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="b3149-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b3149-123">Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="b3149-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b3149-124">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="b3149-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="b3149-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="b3149-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="b3149-126">Недостаточно памяти для завершения запрошенного выделения.</span><span class="sxs-lookup"><span data-stu-id="b3149-126">Not enough memory is available to complete the requested allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b3149-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="b3149-127">Remarks</span></span>  
 <span data-ttu-id="b3149-128">Последовательности вызовов для и из неуправляемого кода могут быть вложенными.</span><span class="sxs-lookup"><span data-stu-id="b3149-128">Call sequences to and from unmanaged code can be nested.</span></span> <span data-ttu-id="b3149-129">Например, приведенный ниже список описывает гипотетическую ситуацию, в которой последовательность вызовов `LeaveRuntime` , [IHostTaskManager:: реверсинтеррунтиме](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md), [IHostTaskManager:: ReverseLeaveRuntime](ihosttaskmanager-reverseleaveruntime-method.md), и узел, `IHostTaskManager::EnterRuntime` позволяющий находить вложенные слои.</span><span class="sxs-lookup"><span data-stu-id="b3149-129">For example, the list below describes a hypothetical situation in which the sequence of calls to `LeaveRuntime`, [IHostTaskManager::ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md), [IHostTaskManager::ReverseLeaveRuntime](ihosttaskmanager-reverseleaveruntime-method.md), and `IHostTaskManager::EnterRuntime` allows the host to identify the nested layers.</span></span>  
  
|<span data-ttu-id="b3149-130">Действие</span><span class="sxs-lookup"><span data-stu-id="b3149-130">Action</span></span>|<span data-ttu-id="b3149-131">Вызов соответствующего метода</span><span class="sxs-lookup"><span data-stu-id="b3149-131">Corresponding Method Call</span></span>|  
|------------|-------------------------------|  
|<span data-ttu-id="b3149-132">Управляемый исполняемый файл Visual Basic вызывает неуправляемую функцию, написанную на языке C, с помощью вызова неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="b3149-132">A managed Visual Basic executable calls an unmanaged function written in C by using platform invoke.</span></span>|`IHostTaskManager::LeaveRuntime`|  
|<span data-ttu-id="b3149-133">Неуправляемая функция C вызывает метод в управляемой библиотеке DLL, написанной на языке C#.</span><span class="sxs-lookup"><span data-stu-id="b3149-133">The unmanaged C function calls a method in a managed DLL written in C#.</span></span>|`IHostTaskManager::ReverseEnterRuntime`|  
|<span data-ttu-id="b3149-134">Управляемая функция C# вызывает другую неуправляемую функцию, написанную на языке C, также используя вызов неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="b3149-134">The managed C# function calls another unmanaged function written in C, also using platform invoke.</span></span>|`IHostTaskManager::LeaveRuntime`|  
|<span data-ttu-id="b3149-135">Вторая неуправляемая функция возвращает выполнение функции C#.</span><span class="sxs-lookup"><span data-stu-id="b3149-135">The second unmanaged function returns execution to the C# function.</span></span>|`IHostTaskManager::EnterRuntime`|  
|<span data-ttu-id="b3149-136">Функция C# возвращает выполнение в первую неуправляемую функцию.</span><span class="sxs-lookup"><span data-stu-id="b3149-136">The C# function returns execution to the first unmanaged function.</span></span>|`IHostTaskManager::ReverseLeaveRuntime`|  
|<span data-ttu-id="b3149-137">Первая неуправляемая функция возвращает выполнение в программу Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="b3149-137">The first unmanaged function returns execution to the Visual Basic program.</span></span>|`IHostTaskManager::EnterRuntime`|  
  
## <a name="requirements"></a><span data-ttu-id="b3149-138">Требования</span><span class="sxs-lookup"><span data-stu-id="b3149-138">Requirements</span></span>  
 <span data-ttu-id="b3149-139">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b3149-139">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b3149-140">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="b3149-140">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b3149-141">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="b3149-141">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b3149-142">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b3149-142">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3149-143">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="b3149-143">See also</span></span>

- [<span data-ttu-id="b3149-144">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="b3149-144">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="b3149-145">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="b3149-145">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="b3149-146">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="b3149-146">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="b3149-147">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="b3149-147">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
