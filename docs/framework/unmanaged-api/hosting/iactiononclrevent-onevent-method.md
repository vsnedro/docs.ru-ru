---
title: Метод IActionOnCLREvent::OnEvent
ms.date: 03/30/2017
api_name:
- IActionOnCLREvent.OnEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IActionOnCLREvent::OnEvent
helpviewer_keywords:
- OnEvent method [.NET Framework hosting]
- IActionOnCLREvent::OnEvent method [.NET Framework hosting]
ms.assetid: 0970f10c-4304-4c12-91c0-83e51455afb4
topic_type:
- apiref
ms.openlocfilehash: 3bfcb01e30b4cb33ec9276f1d3c6ac2f3bde4b58
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721768"
---
# <a name="iactiononclreventonevent-method"></a><span data-ttu-id="81798-102">Метод IActionOnCLREvent::OnEvent</span><span class="sxs-lookup"><span data-stu-id="81798-102">IActionOnCLREvent::OnEvent Method</span></span>

<span data-ttu-id="81798-103">Выполняет обратные вызовы для событий, зарегистрированных с помощью вызова метода [ICLROnEventManager:: регистерактиононевент](iclroneventmanager-registeractiononevent-method.md) .</span><span class="sxs-lookup"><span data-stu-id="81798-103">Performs callbacks on events that have been registered by using a call to the [ICLROnEventManager::RegisterActionOnEvent](iclroneventmanager-registeractiononevent-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81798-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="81798-104">Syntax</span></span>  
  
```cpp  
HRESULT OnEvent (  
    [in] EClrEvent event,  
    [in] PVOID     data  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="81798-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="81798-105">Parameters</span></span>  

 `event`  
 <span data-ttu-id="81798-106">окне Одно из значений [еклревент](eclrevent-enumeration.md) , указывающее тип события.</span><span class="sxs-lookup"><span data-stu-id="81798-106">[in] One of the [EClrEvent](eclrevent-enumeration.md) values, which indicates the type of event.</span></span>  
  
 `data`  
 <span data-ttu-id="81798-107">окне Указатель на объект, содержащий сведения о `event` .</span><span class="sxs-lookup"><span data-stu-id="81798-107">[in] A pointer to an object that contains details about `event`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="81798-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="81798-108">Return Value</span></span>  
  
|<span data-ttu-id="81798-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="81798-109">HRESULT</span></span>|<span data-ttu-id="81798-110">Описание:</span><span class="sxs-lookup"><span data-stu-id="81798-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="81798-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="81798-111">S_OK</span></span>|<span data-ttu-id="81798-112">`OnEvent` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="81798-112">`OnEvent` returned successfully.</span></span>|  
|<span data-ttu-id="81798-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="81798-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="81798-114">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="81798-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="81798-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="81798-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="81798-116">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="81798-116">The call timed out.</span></span>|  
|<span data-ttu-id="81798-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="81798-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="81798-118">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="81798-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="81798-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="81798-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="81798-120">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="81798-120">An event was cancelled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="81798-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="81798-121">E_FAIL</span></span>|<span data-ttu-id="81798-122">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="81798-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="81798-123">Если метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="81798-123">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="81798-124">Последующие вызовы метода размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="81798-124">Subsequent calls to any hosting method return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="81798-125">Комментарии</span><span class="sxs-lookup"><span data-stu-id="81798-125">Remarks</span></span>  

 <span data-ttu-id="81798-126">`data`Параметр является указателем на объект неопределенного типа.</span><span class="sxs-lookup"><span data-stu-id="81798-126">The `data` parameter is a pointer to an object of unspecified type.</span></span> <span data-ttu-id="81798-127">Если `event` параметр имеет значение `Event_DomainUnload` , то `data` является числовым идентификатором для <xref:System.AppDomain> выгрузки.</span><span class="sxs-lookup"><span data-stu-id="81798-127">If the `event` parameter is `Event_DomainUnload`, `data` is the numeric identifier for the <xref:System.AppDomain> that was unloaded.</span></span> <span data-ttu-id="81798-128">Узел может предпринять соответствующие действия, используя этот идентификатор в качестве ключа.</span><span class="sxs-lookup"><span data-stu-id="81798-128">The host can take appropriate action using this identifier as a key.</span></span>  
  
 <span data-ttu-id="81798-129">Если `event` имеет значение `Event_MDAFired` , `data` то является указателем на экземпляр [мдаинфо](mdainfo-structure.md) , который содержит выходные данные сообщения от помощника по отладке управляемого кода (MDA).</span><span class="sxs-lookup"><span data-stu-id="81798-129">If `event` is `Event_MDAFired`, `data` is a pointer to an [MDAInfo](mdainfo-structure.md) instance that contains the message output from a Managed Debugging Assistant (MDA).</span></span> <span data-ttu-id="81798-130">MDA — это функция среды CLR, которая помогает разработчикам выполнять отладку путем создания сообщений XML о событиях, которые в противном случае сложны для перехвата.</span><span class="sxs-lookup"><span data-stu-id="81798-130">MDAs are a feature of the CLR that help developers with debugging, by generating XML messages about events that are otherwise difficult to trap.</span></span> <span data-ttu-id="81798-131">Такие сообщения могут быть особенно полезны при отладке переходов между управляемым и неуправляемым кодом.</span><span class="sxs-lookup"><span data-stu-id="81798-131">Such messages can be especially useful in debugging transitions between managed and unmanaged code.</span></span> <span data-ttu-id="81798-132">Дополнительные сведения см. в разделе [Диагностика ошибок с помощью помощников по отладке управляемого](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)кода.</span><span class="sxs-lookup"><span data-stu-id="81798-132">For more information, see [Diagnosing Errors with Managed Debugging Assistants](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="81798-133">Требования</span><span class="sxs-lookup"><span data-stu-id="81798-133">Requirements</span></span>  

 <span data-ttu-id="81798-134">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="81798-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81798-135">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="81798-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="81798-136">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="81798-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="81798-137">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81798-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81798-138">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="81798-138">See also</span></span>

- [<span data-ttu-id="81798-139">Диагностика ошибок посредством управляемых помощников по отладке</span><span class="sxs-lookup"><span data-stu-id="81798-139">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="81798-140">Перечисление EClrEvent</span><span class="sxs-lookup"><span data-stu-id="81798-140">EClrEvent Enumeration</span></span>](eclrevent-enumeration.md)
- [<span data-ttu-id="81798-141">Интерфейс IActionOnCLREvent</span><span class="sxs-lookup"><span data-stu-id="81798-141">IActionOnCLREvent Interface</span></span>](iactiononclrevent-interface.md)
- [<span data-ttu-id="81798-142">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="81798-142">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="81798-143">Интерфейс ICLROnEventManager</span><span class="sxs-lookup"><span data-stu-id="81798-143">ICLROnEventManager Interface</span></span>](iclroneventmanager-interface.md)
- [<span data-ttu-id="81798-144">Структура MDAInfo</span><span class="sxs-lookup"><span data-stu-id="81798-144">MDAInfo Structure</span></span>](mdainfo-structure.md)
