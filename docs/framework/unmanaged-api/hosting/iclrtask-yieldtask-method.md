---
title: Метод ICLRTask::YieldTask
ms.date: 03/30/2017
api_name:
- ICLRTask.YieldTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::YieldTask
helpviewer_keywords:
- ICLRTask::YieldTask method [.NET Framework hosting]
- YieldTask method [.NET Framework hosting]
ms.assetid: b8eb4095-3a8f-4be3-9446-63e9893dce7d
topic_type:
- apiref
ms.openlocfilehash: 7b9b47daa96ffcb1f66b462ff8e227250c5a81ca
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720286"
---
# <a name="iclrtaskyieldtask-method"></a><span data-ttu-id="982ee-102">Метод ICLRTask::YieldTask</span><span class="sxs-lookup"><span data-stu-id="982ee-102">ICLRTask::YieldTask Method</span></span>

<span data-ttu-id="982ee-103">Запрашивает, что среда CLR должна отложить задачу, представляемую текущим экземпляром [ICLRTask](iclrtask-interface.md) , и сделать процессор доступным для других задач.</span><span class="sxs-lookup"><span data-stu-id="982ee-103">Requests that the common language runtime (CLR) put aside the task that the current [ICLRTask](iclrtask-interface.md) instance represents, and make the processor time available to other tasks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="982ee-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="982ee-104">Syntax</span></span>  
  
```cpp  
HRESULT YieldTask ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="982ee-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="982ee-105">Return Value</span></span>  
  
|<span data-ttu-id="982ee-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="982ee-106">HRESULT</span></span>|<span data-ttu-id="982ee-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="982ee-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="982ee-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="982ee-108">S_OK</span></span>|<span data-ttu-id="982ee-109">`YieldTask` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="982ee-109">`YieldTask` returned successfully.</span></span>|  
|<span data-ttu-id="982ee-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="982ee-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="982ee-111">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="982ee-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="982ee-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="982ee-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="982ee-113">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="982ee-113">The call timed out.</span></span>|  
|<span data-ttu-id="982ee-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="982ee-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="982ee-115">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="982ee-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="982ee-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="982ee-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="982ee-117">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="982ee-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="982ee-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="982ee-118">E_FAIL</span></span>|<span data-ttu-id="982ee-119">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="982ee-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="982ee-120">Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="982ee-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="982ee-121">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="982ee-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="982ee-122">Комментарии</span><span class="sxs-lookup"><span data-stu-id="982ee-122">Remarks</span></span>  

 <span data-ttu-id="982ee-123">Вызовы узла `YieldTask` для запроса ресурсов процессора для других задач или процессов.</span><span class="sxs-lookup"><span data-stu-id="982ee-123">A host calls `YieldTask` to request processor resources for other tasks or processes.</span></span> <span data-ttu-id="982ee-124">Этот метод в основном предназначен для того, чтобы долго выполняемый код выдать время ЦП.</span><span class="sxs-lookup"><span data-stu-id="982ee-124">This method is primarily intended to allow long-running code to give up CPU time.</span></span> <span data-ttu-id="982ee-125">Среда выполнения пытается разместить задачу, которая представляет текущий `ICLRTask` экземпляр, в состоянии, в котором оно может подавать время обработки, но не гарантирует успешного выполнения.</span><span class="sxs-lookup"><span data-stu-id="982ee-125">The runtime attempts to put the task that the current `ICLRTask` instance represents in a state where it can yield processing time, but makes no guarantee of success.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="982ee-126">Требования</span><span class="sxs-lookup"><span data-stu-id="982ee-126">Requirements</span></span>  

 <span data-ttu-id="982ee-127">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="982ee-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="982ee-128">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="982ee-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="982ee-129">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="982ee-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="982ee-130">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="982ee-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="982ee-131">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="982ee-131">See also</span></span>

- [<span data-ttu-id="982ee-132">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="982ee-132">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="982ee-133">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="982ee-133">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="982ee-134">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="982ee-134">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="982ee-135">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="982ee-135">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
