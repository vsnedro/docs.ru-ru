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
ms.openlocfilehash: 5d6e19fe307373c2920fd60b04bff482b238c5c4
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762959"
---
# <a name="iclrtaskrudeabort-method"></a><span data-ttu-id="81db6-102">Метод ICLRTask::RudeAbort</span><span class="sxs-lookup"><span data-stu-id="81db6-102">ICLRTask::RudeAbort Method</span></span>
<span data-ttu-id="81db6-103">Инструктирует среду CLR, чтобы немедленно и безусловно прерывать выполнение задачи, представленной текущим экземпляром [интерфейса ICLRTask](iclrtask-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="81db6-103">Instructs the common language runtime (CLR) to abort the task represented by the current [ICLRTask Interface](iclrtask-interface.md) instance immediately and unconditionally.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81db6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="81db6-104">Syntax</span></span>  
  
```cpp  
HRESULT RudeAbort ();
```  
  
## <a name="return-value"></a><span data-ttu-id="81db6-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="81db6-105">Return Value</span></span>  
  
|<span data-ttu-id="81db6-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="81db6-106">HRESULT</span></span>|<span data-ttu-id="81db6-107">Описание</span><span class="sxs-lookup"><span data-stu-id="81db6-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="81db6-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="81db6-108">S_OK</span></span>|<span data-ttu-id="81db6-109">`RudeAbort`успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="81db6-109">`RudeAbort` returned successfully.</span></span>|  
|<span data-ttu-id="81db6-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="81db6-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="81db6-111">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="81db6-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="81db6-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="81db6-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="81db6-113">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="81db6-113">The call timed out.</span></span>|  
|<span data-ttu-id="81db6-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="81db6-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="81db6-115">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="81db6-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="81db6-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="81db6-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="81db6-117">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="81db6-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="81db6-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="81db6-118">E_FAIL</span></span>|<span data-ttu-id="81db6-119">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="81db6-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="81db6-120">Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="81db6-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="81db6-121">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="81db6-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="81db6-122">Комментарии</span><span class="sxs-lookup"><span data-stu-id="81db6-122">Remarks</span></span>  
 <span data-ttu-id="81db6-123">Вызовы узла `RudeAbort` для немедленного прерывания задачи.</span><span class="sxs-lookup"><span data-stu-id="81db6-123">A host calls `RudeAbort` to abort a task immediately.</span></span> <span data-ttu-id="81db6-124">Выполнение методов завершения и подпрограмм обработки исключений не гарантируется.</span><span class="sxs-lookup"><span data-stu-id="81db6-124">Finalizers and exception handling routines are not guaranteed to be executed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="81db6-125">Требования</span><span class="sxs-lookup"><span data-stu-id="81db6-125">Requirements</span></span>  
 <span data-ttu-id="81db6-126">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="81db6-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81db6-127">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="81db6-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="81db6-128">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="81db6-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="81db6-129">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81db6-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81db6-130">См. также</span><span class="sxs-lookup"><span data-stu-id="81db6-130">See also</span></span>

- [<span data-ttu-id="81db6-131">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="81db6-131">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="81db6-132">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="81db6-132">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="81db6-133">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="81db6-133">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="81db6-134">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="81db6-134">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
