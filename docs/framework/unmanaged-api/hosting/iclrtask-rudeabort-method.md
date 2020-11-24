---
title: Метод ICLRTask::RudeAbort
ms.date: 03/30/2017
api_name:
- ICLRTask.RudeAbort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::RudeAbort
helpviewer_keywords:
- RudeAbort method, ICLRTask interface [.NET Framework hosting]
- ICLRTask::RudeAbort method [.NET Framework hosting]
ms.assetid: b5785468-fcd7-4cc3-8a5d-8796337b53fc
topic_type:
- apiref
ms.openlocfilehash: 5b0e2265810b00fe0760d4e25c0f9904a96d9f2a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95691053"
---
# <a name="iclrtaskrudeabort-method"></a><span data-ttu-id="5db8d-102">Метод ICLRTask::RudeAbort</span><span class="sxs-lookup"><span data-stu-id="5db8d-102">ICLRTask::RudeAbort Method</span></span>

<span data-ttu-id="5db8d-103">Инструктирует среду CLR, чтобы немедленно и безусловно прерывать выполнение задачи, представленной текущим экземпляром [интерфейса ICLRTask](iclrtask-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="5db8d-103">Instructs the common language runtime (CLR) to abort the task represented by the current [ICLRTask Interface](iclrtask-interface.md) instance immediately and unconditionally.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5db8d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5db8d-104">Syntax</span></span>  
  
```cpp  
HRESULT RudeAbort ();
```  
  
## <a name="return-value"></a><span data-ttu-id="5db8d-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="5db8d-105">Return Value</span></span>  
  
|<span data-ttu-id="5db8d-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5db8d-106">HRESULT</span></span>|<span data-ttu-id="5db8d-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="5db8d-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5db8d-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="5db8d-108">S_OK</span></span>|<span data-ttu-id="5db8d-109">`RudeAbort` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="5db8d-109">`RudeAbort` returned successfully.</span></span>|  
|<span data-ttu-id="5db8d-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5db8d-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5db8d-111">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="5db8d-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5db8d-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5db8d-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5db8d-113">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="5db8d-113">The call timed out.</span></span>|  
|<span data-ttu-id="5db8d-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5db8d-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5db8d-115">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="5db8d-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5db8d-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5db8d-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5db8d-117">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="5db8d-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5db8d-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5db8d-118">E_FAIL</span></span>|<span data-ttu-id="5db8d-119">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="5db8d-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5db8d-120">Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="5db8d-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5db8d-121">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="5db8d-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5db8d-122">Комментарии</span><span class="sxs-lookup"><span data-stu-id="5db8d-122">Remarks</span></span>  

 <span data-ttu-id="5db8d-123">Вызовы узла `RudeAbort` для немедленного прерывания задачи.</span><span class="sxs-lookup"><span data-stu-id="5db8d-123">A host calls `RudeAbort` to abort a task immediately.</span></span> <span data-ttu-id="5db8d-124">Выполнение методов завершения и подпрограмм обработки исключений не гарантируется.</span><span class="sxs-lookup"><span data-stu-id="5db8d-124">Finalizers and exception handling routines are not guaranteed to be executed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5db8d-125">Требования</span><span class="sxs-lookup"><span data-stu-id="5db8d-125">Requirements</span></span>  

 <span data-ttu-id="5db8d-126">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5db8d-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5db8d-127">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="5db8d-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5db8d-128">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5db8d-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5db8d-129">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5db8d-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5db8d-130">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="5db8d-130">See also</span></span>

- [<span data-ttu-id="5db8d-131">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="5db8d-131">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="5db8d-132">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="5db8d-132">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="5db8d-133">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="5db8d-133">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="5db8d-134">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="5db8d-134">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
