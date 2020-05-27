---
title: Метод IHostTaskManager::BeginThreadAffinity
ms.date: 03/30/2017
api_name:
- IHostTaskManager.BeginThreadAffinity
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::BeginThreadAffinity
helpviewer_keywords:
- IHostTaskManager::BeginThreadAffinity method [.NET Framework hosting]
- BeginThreadAffinity method [.NET Framework hosting]
ms.assetid: fea3ab88-ce41-4c5a-847b-bb78cd748da6
topic_type:
- apiref
ms.openlocfilehash: 90ae790603f0e41a20993ffef88654211a3168d9
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/26/2020
ms.locfileid: "83842365"
---
# <a name="ihosttaskmanagerbeginthreadaffinity-method"></a><span data-ttu-id="ee7b9-102">Метод IHostTaskManager::BeginThreadAffinity</span><span class="sxs-lookup"><span data-stu-id="ee7b9-102">IHostTaskManager::BeginThreadAffinity Method</span></span>
<span data-ttu-id="ee7b9-103">Уведомляет узел о том, что управляемый код вводит точку, в которой текущая задача не должна быть перемещена в другой поток операционной системы.</span><span class="sxs-lookup"><span data-stu-id="ee7b9-103">Notifies the host that managed code is entering a period in which the current task must not be moved to another operating system thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee7b9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ee7b9-104">Syntax</span></span>  
  
```cpp  
HRESULT BeginThreadAffinity ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="ee7b9-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ee7b9-105">Return Value</span></span>  
  
|<span data-ttu-id="ee7b9-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ee7b9-106">HRESULT</span></span>|<span data-ttu-id="ee7b9-107">Описание</span><span class="sxs-lookup"><span data-stu-id="ee7b9-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ee7b9-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="ee7b9-108">S_OK</span></span>|<span data-ttu-id="ee7b9-109">`BeginThreadAffinity`успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="ee7b9-109">`BeginThreadAffinity` returned successfully.</span></span>|  
|<span data-ttu-id="ee7b9-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ee7b9-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ee7b9-111">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="ee7b9-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ee7b9-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ee7b9-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ee7b9-113">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="ee7b9-113">The call timed out.</span></span>|  
|<span data-ttu-id="ee7b9-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ee7b9-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ee7b9-115">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="ee7b9-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ee7b9-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ee7b9-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ee7b9-117">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="ee7b9-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ee7b9-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ee7b9-118">E_FAIL</span></span>|<span data-ttu-id="ee7b9-119">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="ee7b9-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ee7b9-120">Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="ee7b9-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ee7b9-121">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="ee7b9-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ee7b9-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="ee7b9-122">Remarks</span></span>  
 <span data-ttu-id="ee7b9-123">Среда CLR обычно вызывает `IHostTaskManager::BeginThreadAffinity` в контексте вызова <xref:System.Threading.Thread.BeginThreadAffinity%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="ee7b9-123">The CLR typically calls `IHostTaskManager::BeginThreadAffinity` in the context of a call to <xref:System.Threading.Thread.BeginThreadAffinity%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="ee7b9-124">Текущая задача не должна быть перепланирована, пока не будет выполнен соответствующий вызов [IHostTaskManager:: EndThreadAffinity](ihosttaskmanager-endthreadaffinity-method.md).</span><span class="sxs-lookup"><span data-stu-id="ee7b9-124">The current task must not be rescheduled until a corresponding call is made to [IHostTaskManager::EndThreadAffinity](ihosttaskmanager-endthreadaffinity-method.md).</span></span> <span data-ttu-id="ee7b9-125">Задачи можно переключать, но при их переключении обратно они должны быть назначены тому же потоку операционной системы, из которого они были переключены. Вложенные вызовы `BeginThreadAffinity` не оказывают никакого влияния, так как вызов ссылается на текущую задачу.</span><span class="sxs-lookup"><span data-stu-id="ee7b9-125">Tasks can be switched out, but when they are switched back in, they must be assigned to the same operating system thread from which they were switched out. Nested calls to `BeginThreadAffinity` have no effect, because the call refers to the current task.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee7b9-126">Требования</span><span class="sxs-lookup"><span data-stu-id="ee7b9-126">Requirements</span></span>  
 <span data-ttu-id="ee7b9-127">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ee7b9-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee7b9-128">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="ee7b9-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ee7b9-129">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ee7b9-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ee7b9-130">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ee7b9-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee7b9-131">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="ee7b9-131">See also</span></span>

- [<span data-ttu-id="ee7b9-132">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="ee7b9-132">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="ee7b9-133">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="ee7b9-133">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="ee7b9-134">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="ee7b9-134">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="ee7b9-135">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="ee7b9-135">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
