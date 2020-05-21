---
title: Метод ICLRTask::Abort
ms.date: 03/30/2017
api_name:
- ICLRTask.Abort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::Abort
helpviewer_keywords:
- ICLRTask::Abort method [.NET Framework hosting]
- Abort method, ICLRTask interface [.NET Framework hosting]
ms.assetid: b3594b5f-2e41-4e36-9096-3586276a138c
topic_type:
- apiref
ms.openlocfilehash: 76f216b12bccc950a34e2b23404ac305de519f4a
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762478"
---
# <a name="iclrtaskabort-method"></a><span data-ttu-id="053e8-102">Метод ICLRTask::Abort</span><span class="sxs-lookup"><span data-stu-id="053e8-102">ICLRTask::Abort Method</span></span>
<span data-ttu-id="053e8-103">Запрашивает прекращение средой CLR задачи, которую представляет текущий экземпляр [ICLRTask](iclrtask-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="053e8-103">Requests that the common language runtime (CLR) abort the task that the current [ICLRTask](iclrtask-interface.md) instance represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="053e8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="053e8-104">Syntax</span></span>  
  
```cpp  
HRESULT Abort ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="053e8-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="053e8-105">Return Value</span></span>  
  
|<span data-ttu-id="053e8-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="053e8-106">HRESULT</span></span>|<span data-ttu-id="053e8-107">Описание</span><span class="sxs-lookup"><span data-stu-id="053e8-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="053e8-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="053e8-108">S_OK</span></span>|<span data-ttu-id="053e8-109">`Abort`успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="053e8-109">`Abort` returned successfully.</span></span>|  
|<span data-ttu-id="053e8-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="053e8-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="053e8-111">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="053e8-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="053e8-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="053e8-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="053e8-113">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="053e8-113">The call timed out.</span></span>|  
|<span data-ttu-id="053e8-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="053e8-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="053e8-115">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="053e8-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="053e8-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="053e8-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="053e8-117">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="053e8-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="053e8-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="053e8-118">E_FAIL</span></span>|<span data-ttu-id="053e8-119">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="053e8-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="053e8-120">Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="053e8-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="053e8-121">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="053e8-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="053e8-122">Комментарии</span><span class="sxs-lookup"><span data-stu-id="053e8-122">Remarks</span></span>  
 <span data-ttu-id="053e8-123">Среда CLR вызывает исключение <xref:System.Threading.ThreadAbortException> при вызове узла `Abort` .</span><span class="sxs-lookup"><span data-stu-id="053e8-123">The CLR raises a <xref:System.Threading.ThreadAbortException> when the host calls `Abort`.</span></span> <span data-ttu-id="053e8-124">Он возвращает сразу после инициализации сведений об исключении, не дожидаясь выполнения пользовательского кода, например методов завершения или механизмов обработки исключений.</span><span class="sxs-lookup"><span data-stu-id="053e8-124">It returns immediately after the exception information is initialized, without waiting for user code, such as finalizers or exception handling mechanisms, to execute.</span></span> <span data-ttu-id="053e8-125">Вызовы, `Abort` таким путем, быстро возвращают.</span><span class="sxs-lookup"><span data-stu-id="053e8-125">Calls to `Abort` thus return quickly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="053e8-126">Требования</span><span class="sxs-lookup"><span data-stu-id="053e8-126">Requirements</span></span>  
 <span data-ttu-id="053e8-127">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="053e8-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="053e8-128">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="053e8-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="053e8-129">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="053e8-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="053e8-130">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="053e8-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="053e8-131">См. также</span><span class="sxs-lookup"><span data-stu-id="053e8-131">See also</span></span>

- [<span data-ttu-id="053e8-132">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="053e8-132">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="053e8-133">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="053e8-133">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="053e8-134">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="053e8-134">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="053e8-135">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="053e8-135">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
