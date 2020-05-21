---
title: Метод ICLRTask::Reset
ms.date: 03/30/2017
api_name:
- ICLRTask.Reset
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::Reset
helpviewer_keywords:
- ICLRTask::Reset method [.NET Framework hosting]
- Reset method, ICLRTask interface [.NET Framework hosting]
ms.assetid: 1bfb5d3a-0ffd-4bb4-9bf6-aec00cb675b7
topic_type:
- apiref
ms.openlocfilehash: 15004238ee296e44ae77cd8739b7f62ea2a7a100
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762973"
---
# <a name="iclrtaskreset-method"></a><span data-ttu-id="016d0-102">Метод ICLRTask::Reset</span><span class="sxs-lookup"><span data-stu-id="016d0-102">ICLRTask::Reset Method</span></span>
<span data-ttu-id="016d0-103">Информирует среду CLR о том, что узел завершил задачу, и позволяет среде CLR повторно использовать текущий экземпляр [ICLRTask](iclrtask-interface.md) для представления другой задачи.</span><span class="sxs-lookup"><span data-stu-id="016d0-103">Informs the common language runtime (CLR) that the host has completed a task, and enables the CLR to reuse the current [ICLRTask](iclrtask-interface.md) instance to represent another task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="016d0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="016d0-104">Syntax</span></span>  
  
```cpp  
HRESULT Reset (  
    [in] BOOL fFull  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="016d0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="016d0-105">Parameters</span></span>  
 `fFull`  
 <span data-ttu-id="016d0-106">[in] `true` , если среда выполнения должна сбрасывать все статические значения, связанные с потоками, в дополнение к сведениям о безопасности и национальной настройке, связанным с текущим `ICLRTask` экземпляром; в противном случае — значение `false` .</span><span class="sxs-lookup"><span data-stu-id="016d0-106">[in] `true`, if the runtime should reset all thread-related static values in addition to the security and locale information related to the current `ICLRTask` instance; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="016d0-107">Если значение равно `true` , среда выполнения сбрасывает данные, сохраненные с помощью <xref:System.Threading.Thread.AllocateDataSlot%2A> или <xref:System.Threading.Thread.AllocateNamedDataSlot%2A> .</span><span class="sxs-lookup"><span data-stu-id="016d0-107">If the value is `true`, the runtime resets data that was stored using <xref:System.Threading.Thread.AllocateDataSlot%2A> or <xref:System.Threading.Thread.AllocateNamedDataSlot%2A>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="016d0-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="016d0-108">Return Value</span></span>  
  
|<span data-ttu-id="016d0-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="016d0-109">HRESULT</span></span>|<span data-ttu-id="016d0-110">Описание</span><span class="sxs-lookup"><span data-stu-id="016d0-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="016d0-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="016d0-111">S_OK</span></span>|<span data-ttu-id="016d0-112">`Reset`успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="016d0-112">`Reset` returned successfully.</span></span>|  
|<span data-ttu-id="016d0-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="016d0-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="016d0-114">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="016d0-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call.</span></span> <span data-ttu-id="016d0-115">успешность</span><span class="sxs-lookup"><span data-stu-id="016d0-115">successfully</span></span>|  
|<span data-ttu-id="016d0-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="016d0-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="016d0-117">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="016d0-117">The call timed out.</span></span>|  
|<span data-ttu-id="016d0-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="016d0-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="016d0-119">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="016d0-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="016d0-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="016d0-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="016d0-121">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="016d0-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="016d0-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="016d0-122">E_FAIL</span></span>|<span data-ttu-id="016d0-123">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="016d0-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="016d0-124">Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="016d0-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="016d0-125">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="016d0-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="016d0-126">Комментарии</span><span class="sxs-lookup"><span data-stu-id="016d0-126">Remarks</span></span>  
 <span data-ttu-id="016d0-127">Среда CLR может перезапустить ранее созданные `ICLRTask` экземпляры, чтобы избежать лишних затрат на создание новых экземпляров каждый раз, когда требуется новая задача.</span><span class="sxs-lookup"><span data-stu-id="016d0-127">The CLR can recycle previously created `ICLRTask` instances to avoid the overhead of repeatedly creating new instances every time it needs a fresh task.</span></span> <span data-ttu-id="016d0-128">Узел включает эту функцию, вызывая `ICLRTask::Reset` вместо [ICLRTask:: ExitTask](iclrtask-exittask-method.md) после завершения задачи.</span><span class="sxs-lookup"><span data-stu-id="016d0-128">The host enables this feature by calling `ICLRTask::Reset` instead of [ICLRTask::ExitTask](iclrtask-exittask-method.md) when it has completed a task.</span></span> <span data-ttu-id="016d0-129">В следующем списке приведено краткое описание обычного жизненного цикла `ICLRTask` экземпляра.</span><span class="sxs-lookup"><span data-stu-id="016d0-129">The following list summarizes the normal life cycle of an `ICLRTask` instance:</span></span>  
  
1. <span data-ttu-id="016d0-130">Среда выполнения создает новый `ICLRTask` экземпляр.</span><span class="sxs-lookup"><span data-stu-id="016d0-130">The runtime creates a new `ICLRTask` instance.</span></span>  
  
2. <span data-ttu-id="016d0-131">Среда выполнения вызывает [IHostTaskManager:: GetCurrentTask](ihosttaskmanager-getcurrenttask-method.md) , чтобы получить ссылку на текущую задачу узла.</span><span class="sxs-lookup"><span data-stu-id="016d0-131">The runtime calls [IHostTaskManager::GetCurrentTask](ihosttaskmanager-getcurrenttask-method.md) to get a reference to the current host task.</span></span>  
  
3. <span data-ttu-id="016d0-132">Среда выполнения вызывает метод [IHostTask:: SetCLRTask](ihosttask-setclrtask-method.md) , чтобы связать новый экземпляр с задачей хоста.</span><span class="sxs-lookup"><span data-stu-id="016d0-132">The runtime calls [IHostTask::SetCLRTask](ihosttask-setclrtask-method.md) to associate the new instance with the host task.</span></span>  
  
4. <span data-ttu-id="016d0-133">Задача выполняется и завершается.</span><span class="sxs-lookup"><span data-stu-id="016d0-133">The task executes and completes.</span></span>  
  
5. <span data-ttu-id="016d0-134">Узел уничтожает задачу путем вызова `ICLRTask::ExitTask` .</span><span class="sxs-lookup"><span data-stu-id="016d0-134">The host destroys the task by calling `ICLRTask::ExitTask`.</span></span>  
  
 <span data-ttu-id="016d0-135">`Reset`изменяет этот сценарий двумя способами.</span><span class="sxs-lookup"><span data-stu-id="016d0-135">`Reset` alters this scenario in two ways.</span></span> <span data-ttu-id="016d0-136">На шаге 5, приведенном выше, вызывается вызов узла `Reset` для сброса задачи до чистого состояния, а затем отделяет `ICLRTask` экземпляр от связанного экземпляра [IHostTask](ihosttask-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="016d0-136">In step 5 above, the host calls `Reset` to reset the task to a clean state, and then decouples the `ICLRTask` instance from its associated [IHostTask](ihosttask-interface.md) instance.</span></span> <span data-ttu-id="016d0-137">При необходимости узел также может кэшировать `IHostTask` экземпляр для повторного использования.</span><span class="sxs-lookup"><span data-stu-id="016d0-137">If desired, the host can also cache the `IHostTask` instance for reuse.</span></span> <span data-ttu-id="016d0-138">На шаге 1 выше среда выполнения извлекает `ICLRTask` из кэша, а не создает новый экземпляр.</span><span class="sxs-lookup"><span data-stu-id="016d0-138">In step 1 above, the runtime pulls a recycled `ICLRTask` from the cache instead of creating a new instance.</span></span>  
  
 <span data-ttu-id="016d0-139">Этот подход хорошо работает, когда узел также имеет пул рабочих задач с многократным использованием.</span><span class="sxs-lookup"><span data-stu-id="016d0-139">This approach works well when the host also has a pool of reusable worker tasks.</span></span> <span data-ttu-id="016d0-140">Когда узел уничтожает один из его `IHostTask` экземпляров, он уничтожает соответствующий `ICLRTask` вызовом `ExitTask` .</span><span class="sxs-lookup"><span data-stu-id="016d0-140">When the host destroys one of its `IHostTask` instances, it destroys the corresponding `ICLRTask` by calling `ExitTask`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="016d0-141">Требования</span><span class="sxs-lookup"><span data-stu-id="016d0-141">Requirements</span></span>  
 <span data-ttu-id="016d0-142">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="016d0-142">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="016d0-143">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="016d0-143">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="016d0-144">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="016d0-144">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="016d0-145">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="016d0-145">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="016d0-146">См. также</span><span class="sxs-lookup"><span data-stu-id="016d0-146">See also</span></span>

- [<span data-ttu-id="016d0-147">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="016d0-147">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="016d0-148">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="016d0-148">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="016d0-149">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="016d0-149">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="016d0-150">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="016d0-150">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
