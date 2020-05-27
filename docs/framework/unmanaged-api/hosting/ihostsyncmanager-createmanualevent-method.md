---
title: Метод IHostSyncManager::CreateManualEvent
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateManualEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateManualEvent
helpviewer_keywords:
- CreateManualEvent method [.NET Framework hosting]
- IHostSyncManager::CreateManualEvent method [.NET Framework hosting]
ms.assetid: 68661fbd-09cf-46dc-890b-e694f8a3880a
topic_type:
- apiref
ms.openlocfilehash: 334520df749ba428e6480188cd0655bb734725a6
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/22/2020
ms.locfileid: "83803309"
---
# <a name="ihostsyncmanagercreatemanualevent-method"></a><span data-ttu-id="7c37e-102">Метод IHostSyncManager::CreateManualEvent</span><span class="sxs-lookup"><span data-stu-id="7c37e-102">IHostSyncManager::CreateManualEvent Method</span></span>
<span data-ttu-id="7c37e-103">Создает объект события ручного сброса.</span><span class="sxs-lookup"><span data-stu-id="7c37e-103">Creates a manual-reset event object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c37e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7c37e-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateManualEvent (  
    [in]  BOOL bInitialState,  
    [out] IHostManualEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7c37e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7c37e-105">Parameters</span></span>  
 `bInitialState`  
 <span data-ttu-id="7c37e-106">[in] `true` , если объект получает сигнал; в противном случае — значение `false` .</span><span class="sxs-lookup"><span data-stu-id="7c37e-106">[in] `true`, if the object is signaled; otherwise, `false`.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="7c37e-107">заполняет Указатель на адрес экземпляра [ихостмануалевент](ihostmanualevent-interface.md) или значение null, если не удалось создать событие.</span><span class="sxs-lookup"><span data-stu-id="7c37e-107">[out] A pointer to the address of an [IHostManualEvent](ihostmanualevent-interface.md) instance, or null if the event could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7c37e-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="7c37e-108">Return Value</span></span>  
  
|<span data-ttu-id="7c37e-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7c37e-109">HRESULT</span></span>|<span data-ttu-id="7c37e-110">Описание</span><span class="sxs-lookup"><span data-stu-id="7c37e-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7c37e-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="7c37e-111">S_OK</span></span>|<span data-ttu-id="7c37e-112">`CreateManualEvent`успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="7c37e-112">`CreateManualEvent` returned successfully.</span></span>|  
|<span data-ttu-id="7c37e-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7c37e-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7c37e-114">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="7c37e-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7c37e-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7c37e-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7c37e-116">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="7c37e-116">The call timed out.</span></span>|  
|<span data-ttu-id="7c37e-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7c37e-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7c37e-118">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="7c37e-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7c37e-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7c37e-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7c37e-120">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="7c37e-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7c37e-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7c37e-121">E_FAIL</span></span>|<span data-ttu-id="7c37e-122">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="7c37e-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7c37e-123">Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="7c37e-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7c37e-124">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="7c37e-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="7c37e-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="7c37e-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="7c37e-126">Недостаточно свободной памяти для создания запрошенного объекта события.</span><span class="sxs-lookup"><span data-stu-id="7c37e-126">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7c37e-127">Замечания</span><span class="sxs-lookup"><span data-stu-id="7c37e-127">Remarks</span></span>  
 <span data-ttu-id="7c37e-128">`CreateManualEvent`создает `IHostManualEvent` объект события ручного сброса, для которого требуется вызов метода [ихостмануалевент:: Reset](ihostmanualevent-reset-method.md) , чтобы установить несигнальное состояние.</span><span class="sxs-lookup"><span data-stu-id="7c37e-128">`CreateManualEvent` creates an `IHostManualEvent`, a manual-reset event object that requires a call to the [IHostManualEvent::Reset](ihostmanualevent-reset-method.md) method to set it to a non-signaled state.</span></span> <span data-ttu-id="7c37e-129">`CreateManualEvent`отражает функцию Win32 `CreateEvent` со значением, `true` указанным для `bManualReset` параметра.</span><span class="sxs-lookup"><span data-stu-id="7c37e-129">`CreateManualEvent` mirrors the Win32 `CreateEvent` function with a value of `true` specified for the `bManualReset` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c37e-130">Требования</span><span class="sxs-lookup"><span data-stu-id="7c37e-130">Requirements</span></span>  
 <span data-ttu-id="7c37e-131">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7c37e-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c37e-132">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="7c37e-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7c37e-133">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="7c37e-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7c37e-134">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c37e-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c37e-135">См. также статью</span><span class="sxs-lookup"><span data-stu-id="7c37e-135">See also</span></span>

- [<span data-ttu-id="7c37e-136">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="7c37e-136">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="7c37e-137">Интерфейс IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="7c37e-137">IHostManualEvent Interface</span></span>](ihostmanualevent-interface.md)
- [<span data-ttu-id="7c37e-138">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="7c37e-138">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
