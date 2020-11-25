---
title: Метод ICLROnEventManager::RegisterActionOnEvent
ms.date: 03/30/2017
api_name:
- ICLROnEventManager.RegisterActionOnEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLROnEventManager::RegisterActionOnEvent
helpviewer_keywords:
- ICLROnEventManager::RegisterActionOnEvent method [.NET Framework hosting]
- RegisterActionOnEvent method [.NET Framework hosting]
ms.assetid: b944cf49-918d-4c4e-993b-77d097a52550
topic_type:
- apiref
ms.openlocfilehash: 7f0770585e977f5299a40517c28dfb776b2ab898
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725616"
---
# <a name="iclroneventmanagerregisteractiononevent-method"></a><span data-ttu-id="1d1e2-102">Метод ICLROnEventManager::RegisterActionOnEvent</span><span class="sxs-lookup"><span data-stu-id="1d1e2-102">ICLROnEventManager::RegisterActionOnEvent Method</span></span>

<span data-ttu-id="1d1e2-103">Регистрирует указатель обратного вызова для указанного события.</span><span class="sxs-lookup"><span data-stu-id="1d1e2-103">Registers a callback pointer for the specified event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d1e2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1d1e2-104">Syntax</span></span>  
  
```cpp  
HRESULT RegisterActionOnEvent (  
    [in] EClrEvent event,  
    [in] IActionOnCLREvent *pAction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1d1e2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1d1e2-105">Parameters</span></span>  

 `event`  
 <span data-ttu-id="1d1e2-106">окне Одно из значений [еклревент](eclrevent-enumeration.md) , указывающее событие, для которого регистрируется указатель обратного вызова, описанный в `pAction` .</span><span class="sxs-lookup"><span data-stu-id="1d1e2-106">[in] One of the [EClrEvent](eclrevent-enumeration.md) values, indicating the event for which to register the callback pointer described by `pAction`.</span></span>  
  
 `pAction`  
 <span data-ttu-id="1d1e2-107">окне Указатель на объект [иактиононклревент](iactiononclrevent-interface.md) , вызываемый при срабатывании зарегистрированного события.</span><span class="sxs-lookup"><span data-stu-id="1d1e2-107">[in] A pointer to an [IActionOnCLREvent](iactiononclrevent-interface.md) object that is called when the registered event fires.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1d1e2-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="1d1e2-108">Return Value</span></span>  
  
|<span data-ttu-id="1d1e2-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1d1e2-109">HRESULT</span></span>|<span data-ttu-id="1d1e2-110">Описание:</span><span class="sxs-lookup"><span data-stu-id="1d1e2-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1d1e2-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="1d1e2-111">S_OK</span></span>|<span data-ttu-id="1d1e2-112">`RegisterActionOnEvent` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="1d1e2-112">`RegisterActionOnEvent` returned successfully.</span></span>|  
|<span data-ttu-id="1d1e2-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1d1e2-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1d1e2-114">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="1d1e2-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1d1e2-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1d1e2-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1d1e2-116">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="1d1e2-116">The call timed out.</span></span>|  
|<span data-ttu-id="1d1e2-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1d1e2-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1d1e2-118">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="1d1e2-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1d1e2-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1d1e2-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1d1e2-120">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="1d1e2-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1d1e2-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1d1e2-121">E_FAIL</span></span>|<span data-ttu-id="1d1e2-122">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="1d1e2-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1d1e2-123">После того как метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="1d1e2-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1d1e2-124">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="1d1e2-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1d1e2-125">Комментарии</span><span class="sxs-lookup"><span data-stu-id="1d1e2-125">Remarks</span></span>  

 <span data-ttu-id="1d1e2-126">Узел может регистрировать обратные вызовы для одного или обоих типов событий, описанных в `EClrEvent` .</span><span class="sxs-lookup"><span data-stu-id="1d1e2-126">The host can register callbacks for either or both of the two event types described by `EClrEvent`.</span></span> <span data-ttu-id="1d1e2-127">Узел получает `ICLROnEventManager` интерфейс путем вызова метода [ICLRControl:: GetCLRManager](iclrcontrol-getclrmanager-method.md) .</span><span class="sxs-lookup"><span data-stu-id="1d1e2-127">The host gets the `ICLROnEventManager` interface by calling the [ICLRControl::GetCLRManager](iclrcontrol-getclrmanager-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1d1e2-128">События, которые `RegisterActionOnEvent` регистрируются, могут быть запущены более одного раза и из разных потоков, чтобы сообщить о выгрузке или отключении среды CLR.</span><span class="sxs-lookup"><span data-stu-id="1d1e2-128">The events that `RegisterActionOnEvent` registers can be fired more than once and from different threads to signal an unload or the disabling of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d1e2-129">Требования</span><span class="sxs-lookup"><span data-stu-id="1d1e2-129">Requirements</span></span>  

 <span data-ttu-id="1d1e2-130">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1d1e2-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d1e2-131">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="1d1e2-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1d1e2-132">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1d1e2-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1d1e2-133">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d1e2-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d1e2-134">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="1d1e2-134">See also</span></span>

- [<span data-ttu-id="1d1e2-135">Перечисление EClrEvent</span><span class="sxs-lookup"><span data-stu-id="1d1e2-135">EClrEvent Enumeration</span></span>](eclrevent-enumeration.md)
- [<span data-ttu-id="1d1e2-136">Интерфейс IActionOnCLREvent</span><span class="sxs-lookup"><span data-stu-id="1d1e2-136">IActionOnCLREvent Interface</span></span>](iactiononclrevent-interface.md)
- [<span data-ttu-id="1d1e2-137">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="1d1e2-137">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="1d1e2-138">Интерфейс ICLROnEventManager</span><span class="sxs-lookup"><span data-stu-id="1d1e2-138">ICLROnEventManager Interface</span></span>](iclroneventmanager-interface.md)
