---
title: Метод ICLRPolicyManager::SetActionOnTimeout
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager.SetActionOnTimeout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetActionOnTimeout
helpviewer_keywords:
- SetActionOnTimeout method [.NET Framework hosting]
- ICLRPolicyManager::SetActionOnTimeout method [.NET Framework hosting]
ms.assetid: 38439fa1-2b99-4fa8-a6ec-08afc0f83b9c
topic_type:
- apiref
ms.openlocfilehash: 0b8e7dfbe377e60b548003af10fb11392b514030
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703454"
---
# <a name="iclrpolicymanagersetactionontimeout-method"></a><span data-ttu-id="08969-102">Метод ICLRPolicyManager::SetActionOnTimeout</span><span class="sxs-lookup"><span data-stu-id="08969-102">ICLRPolicyManager::SetActionOnTimeout Method</span></span>
<span data-ttu-id="08969-103">Указывает действие политики, которое должна выполнять среда CLR при истечении времени ожидания указанной операции.</span><span class="sxs-lookup"><span data-stu-id="08969-103">Specifies the policy action the common language runtime (CLR) should take when the specified operation times out.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08969-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="08969-104">Syntax</span></span>  
  
```cpp  
HRESULT SetActionOnTimeout (  
    [in] EClrOperation operation,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="08969-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="08969-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="08969-106">окне Одно из значений [еклроператион](eclroperation-enumeration.md) , указывающее операцию, для которой необходимо указать действие времени ожидания.</span><span class="sxs-lookup"><span data-stu-id="08969-106">[in] One of the [EClrOperation](eclroperation-enumeration.md) values, indicating the operation for which to specify the timeout action.</span></span> <span data-ttu-id="08969-107">Поддерживаются следующие значения.</span><span class="sxs-lookup"><span data-stu-id="08969-107">The following values are supported:</span></span>  
  
- <span data-ttu-id="08969-108">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="08969-108">OPR_AppDomainUnload</span></span>  
  
- <span data-ttu-id="08969-109">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="08969-109">OPR_ProcessExit</span></span>  
  
- <span data-ttu-id="08969-110">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="08969-110">OPR_ThreadRudeAbortInCriticalRegion</span></span>  
  
- <span data-ttu-id="08969-111">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="08969-111">OPR_ThreadRudeAbortInNonCriticalRegion</span></span>  
  
 `action`  
 <span data-ttu-id="08969-112">окне Одно из значений [еполициактион](epolicyaction-enumeration.md) , указывающее действие политики, выполняемое при истечении времени ожидания операции.</span><span class="sxs-lookup"><span data-stu-id="08969-112">[in] One of the [EPolicyAction](epolicyaction-enumeration.md) values, indicating the policy action to be taken when the operation times out.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="08969-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="08969-113">Return Value</span></span>  
  
|<span data-ttu-id="08969-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="08969-114">HRESULT</span></span>|<span data-ttu-id="08969-115">Описание</span><span class="sxs-lookup"><span data-stu-id="08969-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="08969-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="08969-116">S_OK</span></span>|<span data-ttu-id="08969-117">`SetActionOnTimeout`успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="08969-117">`SetActionOnTimeout` returned successfully.</span></span>|  
|<span data-ttu-id="08969-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="08969-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="08969-119">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="08969-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="08969-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="08969-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="08969-121">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="08969-121">The call timed out.</span></span>|  
|<span data-ttu-id="08969-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="08969-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="08969-123">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="08969-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="08969-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="08969-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="08969-125">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="08969-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="08969-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="08969-126">E_FAIL</span></span>|<span data-ttu-id="08969-127">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="08969-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="08969-128">После того как метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="08969-128">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="08969-129">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="08969-129">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="08969-130">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="08969-130">E_INVALIDARG</span></span>|<span data-ttu-id="08969-131">Не удается задать время ожидания для указанного `operation` или указано недопустимое значение для `operation` .</span><span class="sxs-lookup"><span data-stu-id="08969-131">A timeout cannot be set for the specified `operation`, or an invalid value was supplied for `operation`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="08969-132">Комментарии</span><span class="sxs-lookup"><span data-stu-id="08969-132">Remarks</span></span>  
 <span data-ttu-id="08969-133">Значение времени ожидания может быть либо временем ожидания по умолчанию, установленным средой CLR, либо значением, заданным узлом при вызове метода [ICLRPolicyManager:: setTimeout](iclrpolicymanager-settimeout-method.md) .</span><span class="sxs-lookup"><span data-stu-id="08969-133">The timeout value can be either the default timeout set by the CLR, or a value specified by the host in a call to the [ICLRPolicyManager::SetTimeout](iclrpolicymanager-settimeout-method.md) method.</span></span>  
  
 <span data-ttu-id="08969-134">Не все значения действий политики могут быть указаны в качестве поведения времени ожидания для операций среды CLR.</span><span class="sxs-lookup"><span data-stu-id="08969-134">Not all policy action values can be specified as the timeout behavior for CLR operations.</span></span> <span data-ttu-id="08969-135">`SetActionOnTimeout`обычно используется только для эскалации поведения.</span><span class="sxs-lookup"><span data-stu-id="08969-135">`SetActionOnTimeout` is typically used only to escalate behavior.</span></span> <span data-ttu-id="08969-136">Например, узел может указать, что прерывания потока должны быть преобразованы в грубые прерывания потока, но не могут указывать обратно.</span><span class="sxs-lookup"><span data-stu-id="08969-136">For example, a host can specify that thread aborts be turned into rude thread aborts, but cannot specify the opposite.</span></span> <span data-ttu-id="08969-137">В следующей таблице описаны допустимые `action` значения для допустимых `operation` значений.</span><span class="sxs-lookup"><span data-stu-id="08969-137">The table below describes the valid `action` values for valid `operation` values.</span></span>  
  
|<span data-ttu-id="08969-138">Значение для`operation`</span><span class="sxs-lookup"><span data-stu-id="08969-138">Value for `operation`</span></span>|<span data-ttu-id="08969-139">Допустимые значения для`action`</span><span class="sxs-lookup"><span data-stu-id="08969-139">Valid values for `action`</span></span>|  
|---------------------------|-------------------------------|  
|<span data-ttu-id="08969-140">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="08969-140">OPR_ThreadRudeAbortInNonCriticalRegion</span></span><br /><br /> <span data-ttu-id="08969-141">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="08969-141">OPR_ThreadRudeAbortInCriticalRegion</span></span>|<span data-ttu-id="08969-142">-Ерудеабортсреад</span><span class="sxs-lookup"><span data-stu-id="08969-142">-   eRudeAbortThread</span></span><br /><span data-ttu-id="08969-143">-Еунлоадаппдомаин</span><span class="sxs-lookup"><span data-stu-id="08969-143">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="08969-144">-Ерудеунлоадаппдомаин</span><span class="sxs-lookup"><span data-stu-id="08969-144">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="08969-145">-Икситпроцесс</span><span class="sxs-lookup"><span data-stu-id="08969-145">-   eExitProcess</span></span><br /><span data-ttu-id="08969-146">-Ефастекситпроцесс</span><span class="sxs-lookup"><span data-stu-id="08969-146">-   eFastExitProcess</span></span><br /><span data-ttu-id="08969-147">-Ерудикситпроцесс</span><span class="sxs-lookup"><span data-stu-id="08969-147">-   eRudeExitProcess</span></span><br /><span data-ttu-id="08969-148">-Едисаблерунтиме</span><span class="sxs-lookup"><span data-stu-id="08969-148">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="08969-149">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="08969-149">OPR_AppDomainUnload</span></span>|<span data-ttu-id="08969-150">-Еунлоадаппдомаин</span><span class="sxs-lookup"><span data-stu-id="08969-150">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="08969-151">-Ерудеунлоадаппдомаин</span><span class="sxs-lookup"><span data-stu-id="08969-151">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="08969-152">-Икситпроцесс</span><span class="sxs-lookup"><span data-stu-id="08969-152">-   eExitProcess</span></span><br /><span data-ttu-id="08969-153">-Ефастекситпроцесс</span><span class="sxs-lookup"><span data-stu-id="08969-153">-   eFastExitProcess</span></span><br /><span data-ttu-id="08969-154">-Ерудикситпроцесс</span><span class="sxs-lookup"><span data-stu-id="08969-154">-   eRudeExitProcess</span></span><br /><span data-ttu-id="08969-155">-Едисаблерунтиме</span><span class="sxs-lookup"><span data-stu-id="08969-155">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="08969-156">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="08969-156">OPR_ProcessExit</span></span>|<span data-ttu-id="08969-157">-Икситпроцесс</span><span class="sxs-lookup"><span data-stu-id="08969-157">-   eExitProcess</span></span><br /><span data-ttu-id="08969-158">-Ефастекситпроцесс</span><span class="sxs-lookup"><span data-stu-id="08969-158">-   eFastExitProcess</span></span><br /><span data-ttu-id="08969-159">-Ерудикситпроцесс</span><span class="sxs-lookup"><span data-stu-id="08969-159">-   eRudeExitProcess</span></span><br /><span data-ttu-id="08969-160">-Едисаблерунтиме</span><span class="sxs-lookup"><span data-stu-id="08969-160">-   eDisableRuntime</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="08969-161">Требования</span><span class="sxs-lookup"><span data-stu-id="08969-161">Requirements</span></span>  
 <span data-ttu-id="08969-162">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="08969-162">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08969-163">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="08969-163">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="08969-164">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="08969-164">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="08969-165">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08969-165">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08969-166">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="08969-166">See also</span></span>

- [<span data-ttu-id="08969-167">Перечисление EClrOperation</span><span class="sxs-lookup"><span data-stu-id="08969-167">EClrOperation Enumeration</span></span>](eclroperation-enumeration.md)
- [<span data-ttu-id="08969-168">Перечисление EPolicyAction</span><span class="sxs-lookup"><span data-stu-id="08969-168">EPolicyAction Enumeration</span></span>](epolicyaction-enumeration.md)
- [<span data-ttu-id="08969-169">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="08969-169">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="08969-170">Интерфейс ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="08969-170">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
