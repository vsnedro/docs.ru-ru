---
title: Метод ICLRTask::NeedsPriorityScheduling
ms.date: 03/30/2017
api_name:
- ICLRTask.NeedsPriorityScheduling
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::NeedsPriorityScheduling
helpviewer_keywords:
- ICLRTask::NeedsPriorityScheduling method [.NET Framework hosting]
- NeedsPriorityScheduling method [.NET Framework hosting]
ms.assetid: 9c9db3f3-26bf-4317-88de-5eb926a22a1d
topic_type:
- apiref
ms.openlocfilehash: 86e0899b883f09f2e7b27c0f957e943deb73bb66
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95690802"
---
# <a name="iclrtaskneedspriorityscheduling-method"></a><span data-ttu-id="df88d-102">Метод ICLRTask::NeedsPriorityScheduling</span><span class="sxs-lookup"><span data-stu-id="df88d-102">ICLRTask::NeedsPriorityScheduling Method</span></span>

<span data-ttu-id="df88d-103">Возвращает значение, указывающее, нужно ли пометить текущую задачу, для которой выполняется переключение, в качестве высокого приоритета для повторного планирования.</span><span class="sxs-lookup"><span data-stu-id="df88d-103">Gets a value that indicates whether the current task, which is being switched out, needs to be marked as a high priority for rescheduling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df88d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="df88d-104">Syntax</span></span>  
  
```cpp  
HRESULT NeedsPriorityScheduling (  
    [out] BOOL *pbNeedsPriorityScheduling  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="df88d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="df88d-105">Parameters</span></span>  

 `pbNeedsPriorityRescheduling`  
 <span data-ttu-id="df88d-106">[out] `true` , если узел должен попытаться повторно запланировать текущий экземпляр задачи как можно скорее. в противном случае — значение `false` .</span><span class="sxs-lookup"><span data-stu-id="df88d-106">[out] `true`, if the host should attempt to reschedule the current task instance as soon as possible; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="df88d-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="df88d-107">Return Value</span></span>  
  
|<span data-ttu-id="df88d-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="df88d-108">HRESULT</span></span>|<span data-ttu-id="df88d-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="df88d-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="df88d-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="df88d-110">S_OK</span></span>|<span data-ttu-id="df88d-111">`NeedsPriorityRescheduling` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="df88d-111">`NeedsPriorityRescheduling` returned successfully.</span></span>|  
|<span data-ttu-id="df88d-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="df88d-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="df88d-113">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="df88d-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="df88d-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="df88d-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="df88d-115">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="df88d-115">The call timed out.</span></span>|  
|<span data-ttu-id="df88d-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="df88d-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="df88d-117">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="df88d-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="df88d-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="df88d-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="df88d-119">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="df88d-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="df88d-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="df88d-120">E_FAIL</span></span>|<span data-ttu-id="df88d-121">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="df88d-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="df88d-122">Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="df88d-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="df88d-123">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="df88d-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="df88d-124">Комментарии</span><span class="sxs-lookup"><span data-stu-id="df88d-124">Remarks</span></span>  

 <span data-ttu-id="df88d-125">В ситуациях, когда задача находится в близком к сбору сборщиком мусора, среда CLR устанавливает значение `pbNeedsPriorityScheduling` равным `true` , что указывает на перепланирование с высоким приоритетом.</span><span class="sxs-lookup"><span data-stu-id="df88d-125">In situations where the task is close to being collected by the garbage collector, the CLR sets the value of `pbNeedsPriorityScheduling` to `true`, indicating high-priority rescheduling.</span></span> <span data-ttu-id="df88d-126">Это позволяет основному приложению быстро планировать задачу, уменьшая вероятность задержек при сборке мусора и позволяя основному приложению и среде выполнения взаимодействовать для экономии ресурсов памяти.</span><span class="sxs-lookup"><span data-stu-id="df88d-126">This allows the host to reschedule the task quickly, thereby minimizing the potential for delays in garbage collection, and enabling the host and the runtime to cooperate in conserving memory resources.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df88d-127">Требования</span><span class="sxs-lookup"><span data-stu-id="df88d-127">Requirements</span></span>  

 <span data-ttu-id="df88d-128">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="df88d-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df88d-129">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="df88d-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="df88d-130">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="df88d-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="df88d-131">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df88d-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df88d-132">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="df88d-132">See also</span></span>

- [<span data-ttu-id="df88d-133">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="df88d-133">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="df88d-134">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="df88d-134">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="df88d-135">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="df88d-135">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="df88d-136">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="df88d-136">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
