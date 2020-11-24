---
title: Метод ICLRTask::ExitTask
ms.date: 03/30/2017
api_name:
- ICLRTask.ExitTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::ExitTask
helpviewer_keywords:
- ExitTask method [.NET Framework hosting]
- ICLRTask::ExitTask method [.NET Framework hosting]
ms.assetid: 746c85a6-4b33-4f72-a2e9-379fdf2e96af
topic_type:
- apiref
ms.openlocfilehash: bcd1cac47e4b59cc47c95145f0ccf60c92ea54fe
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95690844"
---
# <a name="iclrtaskexittask-method"></a><span data-ttu-id="1e323-102">Метод ICLRTask::ExitTask</span><span class="sxs-lookup"><span data-stu-id="1e323-102">ICLRTask::ExitTask Method</span></span>

<span data-ttu-id="1e323-103">Уведомляет среду CLR о том, что задача, представленная текущим экземпляром [ICLRTask](iclrtask-interface.md) , завершается, и пытается корректно завершить задачу.</span><span class="sxs-lookup"><span data-stu-id="1e323-103">Notifies the common language runtime (CLR) that the task represented by the current [ICLRTask](iclrtask-interface.md) instance is ending, and attempts to shut the task down gracefully.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e323-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1e323-104">Syntax</span></span>  
  
```cpp  
HRESULT ExitTask ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="1e323-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="1e323-105">Return Value</span></span>  
  
|<span data-ttu-id="1e323-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1e323-106">HRESULT</span></span>|<span data-ttu-id="1e323-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="1e323-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1e323-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="1e323-108">S_OK</span></span>|<span data-ttu-id="1e323-109">`ExitTask` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="1e323-109">`ExitTask` returned successfully.</span></span>|  
|<span data-ttu-id="1e323-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1e323-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1e323-111">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="1e323-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1e323-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1e323-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1e323-113">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="1e323-113">The call timed out.</span></span>|  
|<span data-ttu-id="1e323-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1e323-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1e323-115">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="1e323-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1e323-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1e323-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1e323-117">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="1e323-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1e323-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1e323-118">E_FAIL</span></span>|<span data-ttu-id="1e323-119">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="1e323-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1e323-120">Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="1e323-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1e323-121">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="1e323-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1e323-122">Комментарии</span><span class="sxs-lookup"><span data-stu-id="1e323-122">Remarks</span></span>  

 <span data-ttu-id="1e323-123">`ExitTask` пытается выполнить чистое завершение задачи, аналогично отсоединению потока из неуправляемой библиотеки типов.</span><span class="sxs-lookup"><span data-stu-id="1e323-123">`ExitTask` attempts a clean shutdown of a task, in a manner analogous to detaching a thread from an unmanaged type library.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1e323-124">Требования</span><span class="sxs-lookup"><span data-stu-id="1e323-124">Requirements</span></span>  

 <span data-ttu-id="1e323-125">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1e323-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1e323-126">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="1e323-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1e323-127">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1e323-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1e323-128">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1e323-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e323-129">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="1e323-129">See also</span></span>

- [<span data-ttu-id="1e323-130">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="1e323-130">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="1e323-131">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="1e323-131">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="1e323-132">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="1e323-132">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="1e323-133">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="1e323-133">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
