---
title: Метод IHostTask::Join
ms.date: 03/30/2017
api_name:
- IHostTask.Join
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::Join
helpviewer_keywords:
- IHostTask::Join method [.NET Framework hosting]
- Join method, IHostTask interface [.NET Framework hosting]
ms.assetid: 2cffcc52-19e0-4ced-a440-fc7375078ac9
topic_type:
- apiref
ms.openlocfilehash: 20919bd9889408821cf57817082e3c7d5cebc240
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503930"
---
# <a name="ihosttaskjoin-method"></a><span data-ttu-id="33e37-102">Метод IHostTask::Join</span><span class="sxs-lookup"><span data-stu-id="33e37-102">IHostTask::Join Method</span></span>
<span data-ttu-id="33e37-103">Блокирует вызывающую задачу до тех пор, пока не завершится задача, представленная текущим экземпляром [IHostTask](ihosttask-interface.md) , истечет указанный интервал времени, или будет вызван метод [IHostTask:: Alert](ihosttask-alert-method.md) .</span><span class="sxs-lookup"><span data-stu-id="33e37-103">Blocks the calling task until the task represented by the current [IHostTask](ihosttask-interface.md) instance completes, the specified time interval elapses, or [IHostTask::Alert](ihosttask-alert-method.md) is called.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33e37-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="33e37-104">Syntax</span></span>  
  
```cpp  
HRESULT Join (  
    [in] DWORD milliseconds,  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="33e37-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="33e37-105">Parameters</span></span>  
 `milliseconds`  
 <span data-ttu-id="33e37-106">окне Интервал времени в миллисекундах, в течение которого ожидается завершение задачи.</span><span class="sxs-lookup"><span data-stu-id="33e37-106">[in] The time interval, in milliseconds, to wait for the task to terminate.</span></span> <span data-ttu-id="33e37-107">Если этот интервал истекает до завершения задачи, вызывающая задача разблокируется.</span><span class="sxs-lookup"><span data-stu-id="33e37-107">If this interval elapses before the task terminates, the calling task unblocks.</span></span>  
  
 `option`  
 <span data-ttu-id="33e37-108">окне Одно из значений [WAIT_OPTION](wait-option-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="33e37-108">[in] One of the [WAIT_OPTION](wait-option-enumeration.md) values.</span></span> <span data-ttu-id="33e37-109">Значение WAIT_ALERTABLE указывает узлу вывести задачу из спящего режима, если `Alert` вызывается до `milliseconds` истечения времени.</span><span class="sxs-lookup"><span data-stu-id="33e37-109">A value of WAIT_ALERTABLE instructs the host to wake the task if `Alert` is called before `milliseconds` elapses.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="33e37-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="33e37-110">Return Value</span></span>  
  
|<span data-ttu-id="33e37-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="33e37-111">HRESULT</span></span>|<span data-ttu-id="33e37-112">Описание</span><span class="sxs-lookup"><span data-stu-id="33e37-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="33e37-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="33e37-113">S_OK</span></span>|<span data-ttu-id="33e37-114">`Join`успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="33e37-114">`Join` returned successfully.</span></span>|  
|<span data-ttu-id="33e37-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="33e37-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="33e37-116">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="33e37-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="33e37-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="33e37-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="33e37-118">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="33e37-118">The call timed out.</span></span>|  
|<span data-ttu-id="33e37-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="33e37-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="33e37-120">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="33e37-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="33e37-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="33e37-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="33e37-122">Событие было отменено, пока заблокированный поток или волокно ожидают его, или текущий `IHostTask` экземпляр не связан с задачей.</span><span class="sxs-lookup"><span data-stu-id="33e37-122">An event was canceled while a blocked thread or fiber was waiting on it, or the current `IHostTask` instance is not associated with a task.</span></span>|  
|<span data-ttu-id="33e37-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="33e37-123">E_FAIL</span></span>|<span data-ttu-id="33e37-124">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="33e37-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="33e37-125">Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="33e37-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="33e37-126">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="33e37-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="33e37-127">Требования</span><span class="sxs-lookup"><span data-stu-id="33e37-127">Requirements</span></span>  
 <span data-ttu-id="33e37-128">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="33e37-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33e37-129">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="33e37-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="33e37-130">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="33e37-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="33e37-131">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33e37-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33e37-132">См. также</span><span class="sxs-lookup"><span data-stu-id="33e37-132">See also</span></span>

- [<span data-ttu-id="33e37-133">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="33e37-133">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="33e37-134">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="33e37-134">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="33e37-135">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="33e37-135">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="33e37-136">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="33e37-136">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="33e37-137">Перечисление WAIT_OPTION</span><span class="sxs-lookup"><span data-stu-id="33e37-137">WAIT_OPTION Enumeration</span></span>](wait-option-enumeration.md)
