---
title: Метод ICLROnEventManager::UnregisterActionOnEvent
ms.date: 03/30/2017
api_name:
- ICLROnEventManager.UnregisterActionOnEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLROnEventManager::UnregisterActionOnEvent
helpviewer_keywords:
- UnRegisterActionOnEvent method [.NET Framework hosting]
- ICLROnEventManager::UnRegisterActionOnEvent method [.NET Framework hosting]
ms.assetid: 4c02ec37-cdf0-46b2-890e-235092741236
topic_type:
- apiref
ms.openlocfilehash: a3018d8477d5abd7d03ad8675503624d2e44e8f4
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504138"
---
# <a name="iclroneventmanagerunregisteractiononevent-method"></a><span data-ttu-id="ec119-102">Метод ICLROnEventManager::UnregisterActionOnEvent</span><span class="sxs-lookup"><span data-stu-id="ec119-102">ICLROnEventManager::UnregisterActionOnEvent Method</span></span>
<span data-ttu-id="ec119-103">Отменяет регистрацию ранее зарегистрированного указателя обратного вызова для указанного события.</span><span class="sxs-lookup"><span data-stu-id="ec119-103">Unregisters a previously registered callback pointer for the specified event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec119-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ec119-104">Syntax</span></span>  
  
```cpp  
HRESULT UnregisterActionOnEvent (  
    [in] EClrEvent event,  
    [in] IActionOnCLREvent *pAction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ec119-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ec119-105">Parameters</span></span>  
 `event`  
 <span data-ttu-id="ec119-106">окне Одно из значений [еклревент](eclrevent-enumeration.md) , указывающее событие, для которого отменяется регистрация указателя обратного вызова, описанного в `pAction` .</span><span class="sxs-lookup"><span data-stu-id="ec119-106">[in] One of the [EClrEvent](eclrevent-enumeration.md) values, indicating the event for which to unregister the callback pointer described by `pAction`.</span></span>  
  
 `pAction`  
 <span data-ttu-id="ec119-107">окне Указатель на объект [иактиононклревент](iactiononclrevent-interface.md) , переданный в качестве параметра в метод [регистерактиононевент](iclroneventmanager-registeractiononevent-method.md) .</span><span class="sxs-lookup"><span data-stu-id="ec119-107">[in] A pointer to an [IActionOnCLREvent](iactiononclrevent-interface.md) object that was passed as a parameter to the [RegisterActionOnEvent](iclroneventmanager-registeractiononevent-method.md) method.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ec119-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ec119-108">Return Value</span></span>  
  
|<span data-ttu-id="ec119-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ec119-109">HRESULT</span></span>|<span data-ttu-id="ec119-110">Описание</span><span class="sxs-lookup"><span data-stu-id="ec119-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ec119-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="ec119-111">S_OK</span></span>|<span data-ttu-id="ec119-112">`UnregisterActionOnEvent`успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="ec119-112">`UnregisterActionOnEvent` returned successfully.</span></span>|  
|<span data-ttu-id="ec119-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ec119-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ec119-114">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="ec119-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ec119-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ec119-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ec119-116">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="ec119-116">The call timed out.</span></span>|  
|<span data-ttu-id="ec119-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ec119-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ec119-118">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="ec119-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ec119-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ec119-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ec119-120">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="ec119-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ec119-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ec119-121">E_FAIL</span></span>|<span data-ttu-id="ec119-122">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="ec119-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ec119-123">После того как метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="ec119-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ec119-124">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="ec119-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ec119-125">Требования</span><span class="sxs-lookup"><span data-stu-id="ec119-125">Requirements</span></span>  
 <span data-ttu-id="ec119-126">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ec119-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec119-127">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="ec119-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ec119-128">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ec119-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ec119-129">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec119-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec119-130">См. также</span><span class="sxs-lookup"><span data-stu-id="ec119-130">See also</span></span>

- [<span data-ttu-id="ec119-131">Перечисление EClrEvent</span><span class="sxs-lookup"><span data-stu-id="ec119-131">EClrEvent Enumeration</span></span>](eclrevent-enumeration.md)
- [<span data-ttu-id="ec119-132">Интерфейс IActionOnCLREvent</span><span class="sxs-lookup"><span data-stu-id="ec119-132">IActionOnCLREvent Interface</span></span>](iactiononclrevent-interface.md)
- [<span data-ttu-id="ec119-133">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="ec119-133">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="ec119-134">Интерфейс ICLROnEventManager</span><span class="sxs-lookup"><span data-stu-id="ec119-134">ICLROnEventManager Interface</span></span>](iclroneventmanager-interface.md)
