---
title: Метод ICLRPolicyManager::SetTimeout
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager.SetTimeout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetTimeout
helpviewer_keywords:
- SetTimeout method [.NET Framework hosting]
- ICLRPolicyManager::SetTimeout method [.NET Framework hosting]
ms.assetid: 954404fd-d52d-4e68-b582-8692f3a5f608
topic_type:
- apiref
ms.openlocfilehash: 459c5bc0699487b62d5dcf76f1044faf53ebab8b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732467"
---
# <a name="iclrpolicymanagersettimeout-method"></a><span data-ttu-id="4ffe3-102">Метод ICLRPolicyManager::SetTimeout</span><span class="sxs-lookup"><span data-stu-id="4ffe3-102">ICLRPolicyManager::SetTimeout Method</span></span>

<span data-ttu-id="4ffe3-103">Задает значение времени ожидания для указанной операции.</span><span class="sxs-lookup"><span data-stu-id="4ffe3-103">Sets a timeout value for the specified operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ffe3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4ffe3-104">Syntax</span></span>  
  
```cpp  
HRESULT SetTimeout (  
    [in] EClrOperation operation,  
    [in] DWORD dsMilliseconds  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4ffe3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4ffe3-105">Parameters</span></span>  

 `operation`  
 <span data-ttu-id="4ffe3-106">окне Одно из значений [еклроператион](eclroperation-enumeration.md) , указывающее на операцию среды CLR, для которой задается время ожидания.</span><span class="sxs-lookup"><span data-stu-id="4ffe3-106">[in] One of the [EClrOperation](eclroperation-enumeration.md) values, indicating the common language runtime (CLR) operation for which to set a timeout.</span></span> <span data-ttu-id="4ffe3-107">Поддерживаются следующие значения.</span><span class="sxs-lookup"><span data-stu-id="4ffe3-107">The following values are supported:</span></span>  
  
- <span data-ttu-id="4ffe3-108">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="4ffe3-108">OPR_AppDomainUnload</span></span>  
  
- <span data-ttu-id="4ffe3-109">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="4ffe3-109">OPR_ProcessExit</span></span>  
  
- <span data-ttu-id="4ffe3-110">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="4ffe3-110">OPR_ThreadRudeAbortInCriticalRegion</span></span>  
  
- <span data-ttu-id="4ffe3-111">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="4ffe3-111">OPR_ThreadRudeAbortInNonCriticalRegion</span></span>  
  
 `dwMilliseconds`  
 <span data-ttu-id="4ffe3-112">окне Новое значение времени ожидания в миллисекундах.</span><span class="sxs-lookup"><span data-stu-id="4ffe3-112">[in] The new timeout value, in milliseconds.</span></span> <span data-ttu-id="4ffe3-113">Значение INFINITE приводит к тому, что время ожидания операции никогда не истекает.</span><span class="sxs-lookup"><span data-stu-id="4ffe3-113">A value of INFINITE causes the operation never to time out.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4ffe3-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="4ffe3-114">Return Value</span></span>  
  
|<span data-ttu-id="4ffe3-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4ffe3-115">HRESULT</span></span>|<span data-ttu-id="4ffe3-116">Описание:</span><span class="sxs-lookup"><span data-stu-id="4ffe3-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4ffe3-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="4ffe3-117">S_OK</span></span>|<span data-ttu-id="4ffe3-118">`SetTimeout` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="4ffe3-118">`SetTimeout` returned successfully.</span></span>|  
|<span data-ttu-id="4ffe3-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4ffe3-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4ffe3-120">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="4ffe3-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4ffe3-121">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4ffe3-121">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4ffe3-122">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="4ffe3-122">The call timed out.</span></span>|  
|<span data-ttu-id="4ffe3-123">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4ffe3-123">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4ffe3-124">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="4ffe3-124">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4ffe3-125">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4ffe3-125">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4ffe3-126">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="4ffe3-126">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4ffe3-127">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4ffe3-127">E_FAIL</span></span>|<span data-ttu-id="4ffe3-128">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="4ffe3-128">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4ffe3-129">После того как метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="4ffe3-129">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4ffe3-130">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="4ffe3-130">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="4ffe3-131">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="4ffe3-131">E_INVALIDARG</span></span>|<span data-ttu-id="4ffe3-132">Не удается задать время ожидания для указанного `operation` или указано недопустимое значение для `operation` .</span><span class="sxs-lookup"><span data-stu-id="4ffe3-132">A timeout cannot be set for the specified `operation`, or an invalid value was supplied for `operation`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4ffe3-133">Требования</span><span class="sxs-lookup"><span data-stu-id="4ffe3-133">Requirements</span></span>  

 <span data-ttu-id="4ffe3-134">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4ffe3-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ffe3-135">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="4ffe3-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4ffe3-136">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4ffe3-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4ffe3-137">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4ffe3-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ffe3-138">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="4ffe3-138">See also</span></span>

- [<span data-ttu-id="4ffe3-139">Перечисление EClrOperation</span><span class="sxs-lookup"><span data-stu-id="4ffe3-139">EClrOperation Enumeration</span></span>](eclroperation-enumeration.md)
- [<span data-ttu-id="4ffe3-140">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="4ffe3-140">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="4ffe3-141">Интерфейс ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="4ffe3-141">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
