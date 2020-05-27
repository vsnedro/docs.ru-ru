---
title: Метод IHostCrst::SetSpinCount
ms.date: 03/30/2017
api_name:
- IHostCrst.SetSpinCount
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostCrst::SetSpinCount
helpviewer_keywords:
- IHostCrst::SetSpinCount method [.NET Framework hosting]
- SetSpinCount method [.NET Framework hosting]
ms.assetid: 863fc8ce-9b8a-477e-8dd8-75c8544bb43a
topic_type:
- apiref
ms.openlocfilehash: 2436809f35d5c46416f48987cc92feb51d291a6a
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804885"
---
# <a name="ihostcrstsetspincount-method"></a><span data-ttu-id="1f565-102">Метод IHostCrst::SetSpinCount</span><span class="sxs-lookup"><span data-stu-id="1f565-102">IHostCrst::SetSpinCount Method</span></span>
<span data-ttu-id="1f565-103">Задает счетчик прокрутки для текущего экземпляра [IHostCrst](ihostcrst-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="1f565-103">Sets the spin count for the current [IHostCrst](ihostcrst-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f565-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1f565-104">Syntax</span></span>  
  
```cpp  
HRESULT SetSpinCount (  
    [in] DWORD dwSpinCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1f565-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1f565-105">Parameters</span></span>  
 `dwSpinCount`  
 <span data-ttu-id="1f565-106">окне Новое количество прокруток для текущего `IHostCrst` экземпляра.</span><span class="sxs-lookup"><span data-stu-id="1f565-106">[in] The new spin count for the current `IHostCrst` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1f565-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="1f565-107">Return Value</span></span>  
  
|<span data-ttu-id="1f565-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1f565-108">HRESULT</span></span>|<span data-ttu-id="1f565-109">Описание</span><span class="sxs-lookup"><span data-stu-id="1f565-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1f565-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="1f565-110">S_OK</span></span>|<span data-ttu-id="1f565-111">`SetSpinCount`успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="1f565-111">`SetSpinCount` returned successfully.</span></span>|  
|<span data-ttu-id="1f565-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1f565-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1f565-113">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="1f565-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1f565-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1f565-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1f565-115">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="1f565-115">The call timed out.</span></span>|  
|<span data-ttu-id="1f565-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1f565-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1f565-117">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="1f565-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1f565-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1f565-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1f565-119">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="1f565-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1f565-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1f565-120">E_FAIL</span></span>|<span data-ttu-id="1f565-121">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="1f565-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1f565-122">Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="1f565-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1f565-123">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="1f565-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1f565-124">Замечания</span><span class="sxs-lookup"><span data-stu-id="1f565-124">Remarks</span></span>  
 <span data-ttu-id="1f565-125">В многопроцессорных системах, если критическая секция, представленная текущим `IHostCrst` экземпляром, недоступна, вызывающий поток вращает `dwSpinCount` время до вызова [IHostSemaphore:: wait](ihostsemaphore-wait-method.md) для семафора, связанного с критическим разделом.</span><span class="sxs-lookup"><span data-stu-id="1f565-125">On multi-processor systems, if the critical section represented by the current `IHostCrst` instance is unavailable, a calling thread spins `dwSpinCount` times before calling [IHostSemaphore::Wait](ihostsemaphore-wait-method.md) on a semaphore associated with the critical section.</span></span> <span data-ttu-id="1f565-126">Если критическая секция будет свободна во время операции Spin, вызывающий поток не будет выполнять операцию ожидания.</span><span class="sxs-lookup"><span data-stu-id="1f565-126">If the critical section becomes free during the spin operation, the calling thread avoids the wait operation.</span></span>  
  
 <span data-ttu-id="1f565-127">Использование аналогично `dwSpinCount` использованию параметра с тем же именем в `InitializeCriticalSectionAndSpinCount` функции Win32.</span><span class="sxs-lookup"><span data-stu-id="1f565-127">The usage of `dwSpinCount` is identical to the usage of the parameter of the same name in the Win32 `InitializeCriticalSectionAndSpinCount` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1f565-128">Требования</span><span class="sxs-lookup"><span data-stu-id="1f565-128">Requirements</span></span>  
 <span data-ttu-id="1f565-129">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1f565-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1f565-130">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="1f565-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1f565-131">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="1f565-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1f565-132">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1f565-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f565-133">См. также статью</span><span class="sxs-lookup"><span data-stu-id="1f565-133">See also</span></span>

- [<span data-ttu-id="1f565-134">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="1f565-134">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="1f565-135">Интерфейс IHostCrst</span><span class="sxs-lookup"><span data-stu-id="1f565-135">IHostCrst Interface</span></span>](ihostcrst-interface.md)
- [<span data-ttu-id="1f565-136">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="1f565-136">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
