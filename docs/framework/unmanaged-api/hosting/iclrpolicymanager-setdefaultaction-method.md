---
title: Метод ICLRPolicyManager::SetDefaultAction
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager.SetDefaultAction
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetDefaultAction
helpviewer_keywords:
- SetDefaultAction method [.NET Framework hosting]
- ICLRPolicyManager::SetDefaultAction method [.NET Framework hosting]
ms.assetid: f9411e7a-27df-451f-9f6c-d643d6a7a7ce
topic_type:
- apiref
ms.openlocfilehash: 93070690ea6b30b22949953f1ed0b8c5b1e92764
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732487"
---
# <a name="iclrpolicymanagersetdefaultaction-method"></a><span data-ttu-id="87a76-102">Метод ICLRPolicyManager::SetDefaultAction</span><span class="sxs-lookup"><span data-stu-id="87a76-102">ICLRPolicyManager::SetDefaultAction Method</span></span>

<span data-ttu-id="87a76-103">Указывает действие политики, которое должна выполнять среда CLR при выполнении указанной операции.</span><span class="sxs-lookup"><span data-stu-id="87a76-103">Specifies the policy action the common language runtime (CLR) should take when the specified operation occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87a76-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="87a76-104">Syntax</span></span>  
  
```cpp  
HRESULT SetDefaultAction (  
    [in] EClrOperation operation,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="87a76-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="87a76-105">Parameters</span></span>  

 `operation`  
 <span data-ttu-id="87a76-106">окне Одно из значений [еклроператион](eclroperation-enumeration.md) , указывающее действие, для которого необходимо настроить поведение среды CLR.</span><span class="sxs-lookup"><span data-stu-id="87a76-106">[in] One of the [EClrOperation](eclroperation-enumeration.md) values, indicating the action for which CLR behavior should be customized.</span></span>  
  
 `action`  
 <span data-ttu-id="87a76-107">окне Одно из значений [еполициактион](epolicyaction-enumeration.md) , указывающее действие политики, которое должна предпринять среда CLR при `operation` возникновении.</span><span class="sxs-lookup"><span data-stu-id="87a76-107">[in] One of the [EPolicyAction](epolicyaction-enumeration.md) values, indicating the policy action the CLR should take when `operation` occurs.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="87a76-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="87a76-108">Return Value</span></span>  
  
|<span data-ttu-id="87a76-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="87a76-109">HRESULT</span></span>|<span data-ttu-id="87a76-110">Описание:</span><span class="sxs-lookup"><span data-stu-id="87a76-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="87a76-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="87a76-111">S_OK</span></span>|<span data-ttu-id="87a76-112">`SetDefaultAction` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="87a76-112">`SetDefaultAction` returned successfully.</span></span>|  
|<span data-ttu-id="87a76-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="87a76-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="87a76-114">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="87a76-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="87a76-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="87a76-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="87a76-116">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="87a76-116">The call timed out.</span></span>|  
|<span data-ttu-id="87a76-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="87a76-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="87a76-118">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="87a76-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="87a76-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="87a76-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="87a76-120">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="87a76-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="87a76-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="87a76-121">E_FAIL</span></span>|<span data-ttu-id="87a76-122">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="87a76-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="87a76-123">После того как метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="87a76-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="87a76-124">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="87a76-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="87a76-125">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="87a76-125">E_INVALIDARG</span></span>|<span data-ttu-id="87a76-126">Для `action` задано недопустимое `operation` значение, или для параметра было указано недопустимое `operation` .</span><span class="sxs-lookup"><span data-stu-id="87a76-126">An invalid `action` was specified for the `operation`, or an invalid value was supplied for `operation`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="87a76-127">Комментарии</span><span class="sxs-lookup"><span data-stu-id="87a76-127">Remarks</span></span>  

 <span data-ttu-id="87a76-128">Не все значения действий политики могут быть указаны в качестве поведения по умолчанию для операций среды CLR.</span><span class="sxs-lookup"><span data-stu-id="87a76-128">Not all policy action values can be specified as the default behavior for CLR operations.</span></span> <span data-ttu-id="87a76-129">`SetDefaultAction` обычно может использоваться только для эскалации поведения.</span><span class="sxs-lookup"><span data-stu-id="87a76-129">`SetDefaultAction` can typically be used only to escalate behavior.</span></span> <span data-ttu-id="87a76-130">Например, узел может указать, что прерывания потока должны быть преобразованы в грубые прерывания потока, но не могут указывать обратно.</span><span class="sxs-lookup"><span data-stu-id="87a76-130">For example, a host can specify that thread aborts be turned into rude thread aborts, but cannot specify the opposite.</span></span> <span data-ttu-id="87a76-131">В следующей таблице описаны допустимые `action` значения для каждого возможного `operation` значения.</span><span class="sxs-lookup"><span data-stu-id="87a76-131">The table below describes the valid `action` values for each possible `operation` value.</span></span>  
  
|<span data-ttu-id="87a76-132">Значение для `operation`</span><span class="sxs-lookup"><span data-stu-id="87a76-132">Value for `operation`</span></span>|<span data-ttu-id="87a76-133">Допустимые значения для `action`</span><span class="sxs-lookup"><span data-stu-id="87a76-133">Valid values for `action`</span></span>|  
|---------------------------|-------------------------------|  
|<span data-ttu-id="87a76-134">OPR_ThreadAbort</span><span class="sxs-lookup"><span data-stu-id="87a76-134">OPR_ThreadAbort</span></span>|<span data-ttu-id="87a76-135">-Еабортсреад</span><span class="sxs-lookup"><span data-stu-id="87a76-135">-   eAbortThread</span></span><br /><span data-ttu-id="87a76-136">-Ерудеабортсреад</span><span class="sxs-lookup"><span data-stu-id="87a76-136">-   eRudeAbortThread</span></span><br /><span data-ttu-id="87a76-137">-Еунлоадаппдомаин</span><span class="sxs-lookup"><span data-stu-id="87a76-137">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="87a76-138">-Ерудеунлоадаппдомаин</span><span class="sxs-lookup"><span data-stu-id="87a76-138">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="87a76-139">-Икситпроцесс</span><span class="sxs-lookup"><span data-stu-id="87a76-139">-   eExitProcess</span></span><br /><span data-ttu-id="87a76-140">-Ефастекситпроцесс</span><span class="sxs-lookup"><span data-stu-id="87a76-140">-   eFastExitProcess</span></span><br /><span data-ttu-id="87a76-141">-Ерудикситпроцесс</span><span class="sxs-lookup"><span data-stu-id="87a76-141">-   eRudeExitProcess</span></span><br /><span data-ttu-id="87a76-142">-Едисаблерунтиме</span><span class="sxs-lookup"><span data-stu-id="87a76-142">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="87a76-143">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="87a76-143">OPR_ThreadRudeAbortInNonCriticalRegion</span></span><br /><br /> <span data-ttu-id="87a76-144">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="87a76-144">OPR_ThreadRudeAbortInCriticalRegion</span></span>|<span data-ttu-id="87a76-145">-Ерудеабортсреад</span><span class="sxs-lookup"><span data-stu-id="87a76-145">-   eRudeAbortThread</span></span><br /><span data-ttu-id="87a76-146">-Еунлоадаппдомаин</span><span class="sxs-lookup"><span data-stu-id="87a76-146">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="87a76-147">-Ерудеунлоадаппдомаин</span><span class="sxs-lookup"><span data-stu-id="87a76-147">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="87a76-148">-Икситпроцесс</span><span class="sxs-lookup"><span data-stu-id="87a76-148">-   eExitProcess</span></span><br /><span data-ttu-id="87a76-149">-Ефастекситпроцесс</span><span class="sxs-lookup"><span data-stu-id="87a76-149">-   eFastExitProcess</span></span><br /><span data-ttu-id="87a76-150">-Ерудикситпроцесс</span><span class="sxs-lookup"><span data-stu-id="87a76-150">-   eRudeExitProcess</span></span><br /><span data-ttu-id="87a76-151">-Едисаблерунтиме</span><span class="sxs-lookup"><span data-stu-id="87a76-151">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="87a76-152">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="87a76-152">OPR_AppDomainUnload</span></span>|<span data-ttu-id="87a76-153">-Еунлоадаппдомаин</span><span class="sxs-lookup"><span data-stu-id="87a76-153">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="87a76-154">-Ерудеунлоадаппдомаин</span><span class="sxs-lookup"><span data-stu-id="87a76-154">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="87a76-155">-Икситпроцесс</span><span class="sxs-lookup"><span data-stu-id="87a76-155">-   eExitProcess</span></span><br /><span data-ttu-id="87a76-156">-Ефастекситпроцесс</span><span class="sxs-lookup"><span data-stu-id="87a76-156">-   eFastExitProcess</span></span><br /><span data-ttu-id="87a76-157">-Ерудикситпроцесс</span><span class="sxs-lookup"><span data-stu-id="87a76-157">-   eRudeExitProcess</span></span><br /><span data-ttu-id="87a76-158">-Едисаблерунтиме</span><span class="sxs-lookup"><span data-stu-id="87a76-158">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="87a76-159">OPR_AppDomainRudeUnload</span><span class="sxs-lookup"><span data-stu-id="87a76-159">OPR_AppDomainRudeUnload</span></span>|<span data-ttu-id="87a76-160">-Ерудеунлоадаппдомаин</span><span class="sxs-lookup"><span data-stu-id="87a76-160">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="87a76-161">-Икситпроцесс</span><span class="sxs-lookup"><span data-stu-id="87a76-161">-   eExitProcess</span></span><br /><span data-ttu-id="87a76-162">-Ефастекситпроцесс</span><span class="sxs-lookup"><span data-stu-id="87a76-162">-   eFastExitProcess</span></span><br /><span data-ttu-id="87a76-163">-Ерудикситпроцесс</span><span class="sxs-lookup"><span data-stu-id="87a76-163">-   eRudeExitProcess</span></span><br /><span data-ttu-id="87a76-164">-Едисаблерунтиме</span><span class="sxs-lookup"><span data-stu-id="87a76-164">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="87a76-165">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="87a76-165">OPR_ProcessExit</span></span>|<span data-ttu-id="87a76-166">-Икситпроцесс</span><span class="sxs-lookup"><span data-stu-id="87a76-166">-   eExitProcess</span></span><br /><span data-ttu-id="87a76-167">-Ефастекситпроцесс</span><span class="sxs-lookup"><span data-stu-id="87a76-167">-   eFastExitProcess</span></span><br /><span data-ttu-id="87a76-168">-Ерудикситпроцесс</span><span class="sxs-lookup"><span data-stu-id="87a76-168">-   eRudeExitProcess</span></span><br /><span data-ttu-id="87a76-169">-Едисаблерунтиме</span><span class="sxs-lookup"><span data-stu-id="87a76-169">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="87a76-170">OPR_FinalizerRun</span><span class="sxs-lookup"><span data-stu-id="87a76-170">OPR_FinalizerRun</span></span>|<span data-ttu-id="87a76-171">-Еноактион</span><span class="sxs-lookup"><span data-stu-id="87a76-171">-   eNoAction</span></span><br /><span data-ttu-id="87a76-172">-Еабортсреад</span><span class="sxs-lookup"><span data-stu-id="87a76-172">-   eAbortThread</span></span><br /><span data-ttu-id="87a76-173">-Ерудеабортсреад</span><span class="sxs-lookup"><span data-stu-id="87a76-173">-   eRudeAbortThread</span></span><br /><span data-ttu-id="87a76-174">-Еунлоадаппдомаин</span><span class="sxs-lookup"><span data-stu-id="87a76-174">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="87a76-175">-Ерудеунлоадаппдомаин</span><span class="sxs-lookup"><span data-stu-id="87a76-175">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="87a76-176">-Икситпроцесс</span><span class="sxs-lookup"><span data-stu-id="87a76-176">-   eExitProcess</span></span><br /><span data-ttu-id="87a76-177">-Ефастекситпроцесс</span><span class="sxs-lookup"><span data-stu-id="87a76-177">-   eFastExitProcess</span></span><br /><span data-ttu-id="87a76-178">-Ерудикситпроцесс</span><span class="sxs-lookup"><span data-stu-id="87a76-178">-   eRudeExitProcess</span></span><br /><span data-ttu-id="87a76-179">-Едисаблерунтиме</span><span class="sxs-lookup"><span data-stu-id="87a76-179">-   eDisableRuntime</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="87a76-180">Требования</span><span class="sxs-lookup"><span data-stu-id="87a76-180">Requirements</span></span>  

 <span data-ttu-id="87a76-181">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="87a76-181">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87a76-182">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="87a76-182">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="87a76-183">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="87a76-183">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="87a76-184">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87a76-184">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87a76-185">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="87a76-185">See also</span></span>

- [<span data-ttu-id="87a76-186">Перечисление EClrOperation</span><span class="sxs-lookup"><span data-stu-id="87a76-186">EClrOperation Enumeration</span></span>](eclroperation-enumeration.md)
- [<span data-ttu-id="87a76-187">Перечисление EPolicyAction</span><span class="sxs-lookup"><span data-stu-id="87a76-187">EPolicyAction Enumeration</span></span>](epolicyaction-enumeration.md)
- [<span data-ttu-id="87a76-188">Интерфейс ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="87a76-188">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
