---
title: Метод ICLRPolicyManager::SetTimeoutAndAction
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager.SetTimeoutAndAction
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetTimeoutAndAction
helpviewer_keywords:
- ICLRPolicyManager::SetTimeoutAndAction method [.NET Framework hosting]
- SetTimeoutAndAction method [.NET Framework hosting]
ms.assetid: 60454f91-d855-4ddf-bb6d-60a02f5eabab
topic_type:
- apiref
ms.openlocfilehash: 41e13e20a1cf5a7000907b1cc7d8d2af5174ceba
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728981"
---
# <a name="iclrpolicymanagersettimeoutandaction-method"></a><span data-ttu-id="3e18b-102">Метод ICLRPolicyManager::SetTimeoutAndAction</span><span class="sxs-lookup"><span data-stu-id="3e18b-102">ICLRPolicyManager::SetTimeoutAndAction Method</span></span>

<span data-ttu-id="3e18b-103">Задает значение времени ожидания для указанной операции и указывает действие политики, которое должна выполнять среда CLR при выполнении операции.</span><span class="sxs-lookup"><span data-stu-id="3e18b-103">Sets a timeout value for the specified operation, and specifies the policy action the common language runtime (CLR) should take when the operation occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e18b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3e18b-104">Syntax</span></span>  
  
```cpp  
HRESULT SetTimeoutAndAction (  
    [in] EClrOperation operation,  
    [in] DWORD dwMilliseconds,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3e18b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3e18b-105">Parameters</span></span>  

 `operation`  
 <span data-ttu-id="3e18b-106">окне Одно из значений [еклроператион](eclroperation-enumeration.md) , указывающее операцию, для которой необходимо задать время ожидания и политику `action` .</span><span class="sxs-lookup"><span data-stu-id="3e18b-106">[in] One of the [EClrOperation](eclroperation-enumeration.md) values, indicating the operation for which to set the timeout and policy `action`.</span></span> <span data-ttu-id="3e18b-107">Поддерживаются следующие значения.</span><span class="sxs-lookup"><span data-stu-id="3e18b-107">The following values are supported:</span></span>  
  
- <span data-ttu-id="3e18b-108">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="3e18b-108">OPR_AppDomainUnload</span></span>  
  
- <span data-ttu-id="3e18b-109">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="3e18b-109">OPR_ProcessExit</span></span>  
  
- <span data-ttu-id="3e18b-110">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="3e18b-110">OPR_ThreadRudeAbortInCriticalRegion</span></span>  
  
- <span data-ttu-id="3e18b-111">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="3e18b-111">OPR_ThreadRudeAbortInNonCriticalRegion</span></span>  
  
 `dwMilliseconds`  
 <span data-ttu-id="3e18b-112">окне Новое значение времени ожидания в миллисекундах.</span><span class="sxs-lookup"><span data-stu-id="3e18b-112">[in] The new timeout value, in milliseconds.</span></span> <span data-ttu-id="3e18b-113">Значение бесконечности приводит к тому, что `operation` время ожидания никогда не истекает.</span><span class="sxs-lookup"><span data-stu-id="3e18b-113">A value of INFINITE causes `operation` never to time out.</span></span>  
  
 `action`  
 <span data-ttu-id="3e18b-114">окне Одно из значений [еполициактион](epolicyaction-enumeration.md) , указывающее действие политики, ВЫПОЛНЯЕМое средой CLR при `operation` возникновении.</span><span class="sxs-lookup"><span data-stu-id="3e18b-114">[in] One of the [EPolicyAction](epolicyaction-enumeration.md) values, indicating the policy action that the CLR should take when `operation` occurs.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3e18b-115">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3e18b-115">Return Value</span></span>  
  
|<span data-ttu-id="3e18b-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3e18b-116">HRESULT</span></span>|<span data-ttu-id="3e18b-117">Описание:</span><span class="sxs-lookup"><span data-stu-id="3e18b-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3e18b-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="3e18b-118">S_OK</span></span>|<span data-ttu-id="3e18b-119">`SetTimeoutAndAction` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="3e18b-119">`SetTimeoutAndAction` returned successfully.</span></span>|  
|<span data-ttu-id="3e18b-120">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3e18b-120">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3e18b-121">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="3e18b-121">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3e18b-122">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3e18b-122">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3e18b-123">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="3e18b-123">The call timed out.</span></span>|  
|<span data-ttu-id="3e18b-124">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3e18b-124">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3e18b-125">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="3e18b-125">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3e18b-126">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3e18b-126">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3e18b-127">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="3e18b-127">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3e18b-128">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3e18b-128">E_FAIL</span></span>|<span data-ttu-id="3e18b-129">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="3e18b-129">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3e18b-130">После того как метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="3e18b-130">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3e18b-131">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="3e18b-131">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="3e18b-132">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="3e18b-132">E_INVALIDARG</span></span>|<span data-ttu-id="3e18b-133">Не удается задать время ожидания для указанного `operation` или указано недопустимое значение для `action` .</span><span class="sxs-lookup"><span data-stu-id="3e18b-133">A timeout cannot be set for the specified `operation`, or an invalid value was supplied for `action`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3e18b-134">Комментарии</span><span class="sxs-lookup"><span data-stu-id="3e18b-134">Remarks</span></span>  

 <span data-ttu-id="3e18b-135">`SetTimeoutAndAction` Инкапсулирует возможности методов [ICLRPolicyManager:: setTimeout](iclrpolicymanager-settimeout-method.md) и [ICLRPolicyManager:: сетактиононтимеаут](iclrpolicymanager-setactionontimeout-method.md) , и их можно вызывать вместо последовательных вызовов этих двух методов.</span><span class="sxs-lookup"><span data-stu-id="3e18b-135">`SetTimeoutAndAction` encapsulates the capabilities of the [ICLRPolicyManager::SetTimeout](iclrpolicymanager-settimeout-method.md) and [ICLRPolicyManager::SetActionOnTimeout](iclrpolicymanager-setactionontimeout-method.md) methods, and can be called in place of sequential calls to these two methods.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="3e18b-136">Не все значения действий политики могут быть указаны в качестве поведения времени ожидания для операций среды CLR.</span><span class="sxs-lookup"><span data-stu-id="3e18b-136">Not all policy action values can be specified as the timeout behavior for CLR operations.</span></span> <span data-ttu-id="3e18b-137">Допустимые значения см. в подразделах "Примечания" для этих двух методов.</span><span class="sxs-lookup"><span data-stu-id="3e18b-137">See the Remarks sections of the topics for these two methods for valid values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e18b-138">Требования</span><span class="sxs-lookup"><span data-stu-id="3e18b-138">Requirements</span></span>  

 <span data-ttu-id="3e18b-139">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3e18b-139">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e18b-140">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="3e18b-140">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3e18b-141">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3e18b-141">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3e18b-142">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3e18b-142">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e18b-143">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="3e18b-143">See also</span></span>

- [<span data-ttu-id="3e18b-144">Перечисление EClrOperation</span><span class="sxs-lookup"><span data-stu-id="3e18b-144">EClrOperation Enumeration</span></span>](eclroperation-enumeration.md)
- [<span data-ttu-id="3e18b-145">Перечисление EPolicyAction</span><span class="sxs-lookup"><span data-stu-id="3e18b-145">EPolicyAction Enumeration</span></span>](epolicyaction-enumeration.md)
- [<span data-ttu-id="3e18b-146">Интерфейс ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="3e18b-146">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
- [<span data-ttu-id="3e18b-147">Метод SetActionOnTimeout</span><span class="sxs-lookup"><span data-stu-id="3e18b-147">SetActionOnTimeout Method</span></span>](iclrpolicymanager-setactionontimeout-method.md)
- [<span data-ttu-id="3e18b-148">ICLRPolicyManager:: SetTimeoutAndAction</span><span class="sxs-lookup"><span data-stu-id="3e18b-148">ICLRPolicyManager::SetTimeoutAndAction</span></span>](iclrpolicymanager-settimeoutandaction-method.md)
