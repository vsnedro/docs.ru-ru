---
title: Метод IHostTask::SetPriority
ms.date: 03/30/2017
api_name:
- IHostTask.SetPriority
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::SetPriority
helpviewer_keywords:
- IHostTask::SetPriority method [.NET Framework hosting]
- SetPriority method [.NET Framework hosting]
ms.assetid: cd8c379b-c7a0-434f-8e23-899bd26be75d
topic_type:
- apiref
ms.openlocfilehash: 80b4bb2f6a547250acbc16a89e7396c60cc50d87
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720455"
---
# <a name="ihosttasksetpriority-method"></a><span data-ttu-id="c7d8d-102">Метод IHostTask::SetPriority</span><span class="sxs-lookup"><span data-stu-id="c7d8d-102">IHostTask::SetPriority Method</span></span>

<span data-ttu-id="c7d8d-103">Запрашивает у узла настройку уровня приоритета потока для задачи, представленной текущим экземпляром [IHostTask](ihosttask-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="c7d8d-103">Requests that the host adjust the thread priority level for the task represented by the current [IHostTask](ihosttask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7d8d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c7d8d-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPriority (  
    [in] int newPriority  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c7d8d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c7d8d-105">Parameters</span></span>  

 `newPriority`  
 <span data-ttu-id="c7d8d-106">окне Целое число, представляющее запрошенное значение приоритета потока для задачи, представленной текущим `IHostTask` экземпляром.</span><span class="sxs-lookup"><span data-stu-id="c7d8d-106">[in] An integer that represents the requested thread priority value for the task represented by the current `IHostTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c7d8d-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c7d8d-107">Return Value</span></span>  
  
|<span data-ttu-id="c7d8d-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c7d8d-108">HRESULT</span></span>|<span data-ttu-id="c7d8d-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="c7d8d-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c7d8d-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="c7d8d-110">S_OK</span></span>|<span data-ttu-id="c7d8d-111">`SetPriority` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="c7d8d-111">`SetPriority` returned successfully.</span></span>|  
|<span data-ttu-id="c7d8d-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c7d8d-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c7d8d-113">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="c7d8d-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c7d8d-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c7d8d-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c7d8d-115">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="c7d8d-115">The call timed out.</span></span>|  
|<span data-ttu-id="c7d8d-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c7d8d-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c7d8d-117">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="c7d8d-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c7d8d-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c7d8d-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c7d8d-119">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="c7d8d-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c7d8d-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c7d8d-120">E_FAIL</span></span>|<span data-ttu-id="c7d8d-121">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="c7d8d-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c7d8d-122">Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="c7d8d-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c7d8d-123">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="c7d8d-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c7d8d-124">Комментарии</span><span class="sxs-lookup"><span data-stu-id="c7d8d-124">Remarks</span></span>  

 <span data-ttu-id="c7d8d-125">Потокам предоставляется время обработки с помощью системы циклического перебора, частично основанной на уровне приоритета потока.</span><span class="sxs-lookup"><span data-stu-id="c7d8d-125">Threads are granted processing time using a round-robin system that is partly based on a thread's priority level.</span></span> <span data-ttu-id="c7d8d-126">`SetPriority` позволяет среде CLR устанавливать этот уровень приоритета потока для текущей задачи.</span><span class="sxs-lookup"><span data-stu-id="c7d8d-126">`SetPriority` allows the CLR to set that thread priority level for the current task.</span></span> <span data-ttu-id="c7d8d-127">`newPriority`Поддерживаются следующие значения.</span><span class="sxs-lookup"><span data-stu-id="c7d8d-127">The following `newPriority` values are supported.</span></span>  
  
- <span data-ttu-id="c7d8d-128">THREAD_PRIORITY_ABOVE_NORMAL</span><span class="sxs-lookup"><span data-stu-id="c7d8d-128">THREAD_PRIORITY_ABOVE_NORMAL</span></span>  
  
- <span data-ttu-id="c7d8d-129">THREAD_PRIORITY_BELOW_NORMAL</span><span class="sxs-lookup"><span data-stu-id="c7d8d-129">THREAD_PRIORITY_BELOW_NORMAL</span></span>  
  
- <span data-ttu-id="c7d8d-130">THREAD_PRIORITY_HIGHEST</span><span class="sxs-lookup"><span data-stu-id="c7d8d-130">THREAD_PRIORITY_HIGHEST</span></span>  
  
- <span data-ttu-id="c7d8d-131">THREAD_PRIORITY_IDLE</span><span class="sxs-lookup"><span data-stu-id="c7d8d-131">THREAD_PRIORITY_IDLE</span></span>  
  
- <span data-ttu-id="c7d8d-132">THREAD_PRIORITY_LOWEST</span><span class="sxs-lookup"><span data-stu-id="c7d8d-132">THREAD_PRIORITY_LOWEST</span></span>  
  
- <span data-ttu-id="c7d8d-133">THREAD_PRIORITY_NORMAL</span><span class="sxs-lookup"><span data-stu-id="c7d8d-133">THREAD_PRIORITY_NORMAL</span></span>  
  
- <span data-ttu-id="c7d8d-134">THREAD_PRIORITY_TIME_CRITICAL</span><span class="sxs-lookup"><span data-stu-id="c7d8d-134">THREAD_PRIORITY_TIME_CRITICAL</span></span>  
  
 <span data-ttu-id="c7d8d-135">Среда CLR вызывает, `SetPriority` когда значение изменяется <xref:System.Threading.Thread.Priority%2A?displayProperty=nameWithType> с помощью пользовательского кода.</span><span class="sxs-lookup"><span data-stu-id="c7d8d-135">The CLR calls `SetPriority` when the value of the <xref:System.Threading.Thread.Priority%2A?displayProperty=nameWithType> is modified by user code.</span></span> <span data-ttu-id="c7d8d-136">Узел может определять собственные алгоритмы для назначения приоритета потоков и может без необходимости пропускать этот запрос.</span><span class="sxs-lookup"><span data-stu-id="c7d8d-136">A host can define its own algorithms for thread priority assignment, and is free to ignore this request.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c7d8d-137">`SetPriority` не сообщает, был ли изменен уровень приоритета потока.</span><span class="sxs-lookup"><span data-stu-id="c7d8d-137">`SetPriority` does not report whether the thread priority level was changed.</span></span> <span data-ttu-id="c7d8d-138">Вызовите метод [IHostTask:: предшествовал](ihosttask-getpriority-method.md) , чтобы определить значение уровня приоритета потока задачи.</span><span class="sxs-lookup"><span data-stu-id="c7d8d-138">Call [IHostTask::GetPriority](ihosttask-getpriority-method.md) to determine the value of the task's thread priority level.</span></span>  
  
 <span data-ttu-id="c7d8d-139">Значения уровня приоритета потока определяются функцией Win32 `SetThreadPriority` .</span><span class="sxs-lookup"><span data-stu-id="c7d8d-139">Thread priority level values are defined by the Win32 `SetThreadPriority` function.</span></span> <span data-ttu-id="c7d8d-140">Дополнительные сведения о приоритете потоков см. в документации по платформе Windows.</span><span class="sxs-lookup"><span data-stu-id="c7d8d-140">For more information about thread priority, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7d8d-141">Требования</span><span class="sxs-lookup"><span data-stu-id="c7d8d-141">Requirements</span></span>  

 <span data-ttu-id="c7d8d-142">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c7d8d-142">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7d8d-143">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="c7d8d-143">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c7d8d-144">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c7d8d-144">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c7d8d-145">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7d8d-145">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7d8d-146">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="c7d8d-146">See also</span></span>

- <xref:System.Threading.Thread>
- [<span data-ttu-id="c7d8d-147">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="c7d8d-147">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="c7d8d-148">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="c7d8d-148">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="c7d8d-149">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="c7d8d-149">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="c7d8d-150">Метод GetPriority</span><span class="sxs-lookup"><span data-stu-id="c7d8d-150">GetPriority Method</span></span>](ihosttask-getpriority-method.md)
- [<span data-ttu-id="c7d8d-151">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="c7d8d-151">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
