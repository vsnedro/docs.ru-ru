---
title: Метод ICLRPolicyManager::SetActionOnFailure
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager.SetActionOnFailure
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetActionOnFailure
helpviewer_keywords:
- SetActionOnFailure method [.NET Framework hosting]
- ICLRPolicyManager::SetActionOnFailure method [.NET Framework hosting]
ms.assetid: 4664033f-db97-4388-b988-2ec470796e58
topic_type:
- apiref
ms.openlocfilehash: fb2ecc80f272a3fc9b63b20c5956e7a28f117784
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703470"
---
# <a name="iclrpolicymanagersetactiononfailure-method"></a><span data-ttu-id="9e120-102">Метод ICLRPolicyManager::SetActionOnFailure</span><span class="sxs-lookup"><span data-stu-id="9e120-102">ICLRPolicyManager::SetActionOnFailure Method</span></span>
<span data-ttu-id="9e120-103">Указывает действие политики, которое должна выполнять среда CLR при возникновении указанного сбоя.</span><span class="sxs-lookup"><span data-stu-id="9e120-103">Specifies the policy action the common language runtime (CLR) should take when the specified failure occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e120-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9e120-104">Syntax</span></span>  
  
```cpp  
HRESULT SetActionOnFailure (  
    [in] EClrFailure   failure,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9e120-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9e120-105">Parameters</span></span>  
 `failure`  
 <span data-ttu-id="9e120-106">окне Одно из значений [еклрфаилуре](eclrfailure-enumeration.md) , указывающее тип сбоя, для которого необходимо выполнить действие.</span><span class="sxs-lookup"><span data-stu-id="9e120-106">[in] One of the [EClrFailure](eclrfailure-enumeration.md) values, indicating the type of failure for which to take action.</span></span>  
  
 `action`  
 <span data-ttu-id="9e120-107">окне Одно из значений [еполициактион](epolicyaction-enumeration.md) , указывающее действие, выполняемое в случае сбоя.</span><span class="sxs-lookup"><span data-stu-id="9e120-107">[in] One of the [EPolicyAction](epolicyaction-enumeration.md) values, indicating the action to be taken when a failure occurs.</span></span> <span data-ttu-id="9e120-108">Список поддерживаемых значений см. в разделе "Примечания".</span><span class="sxs-lookup"><span data-stu-id="9e120-108">For a list of supported values, see the Remarks section.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9e120-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="9e120-109">Return Value</span></span>  
  
|<span data-ttu-id="9e120-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9e120-110">HRESULT</span></span>|<span data-ttu-id="9e120-111">Описание</span><span class="sxs-lookup"><span data-stu-id="9e120-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9e120-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="9e120-112">S_OK</span></span>|<span data-ttu-id="9e120-113">`SetActionOnFailure`успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="9e120-113">`SetActionOnFailure` returned successfully.</span></span>|  
|<span data-ttu-id="9e120-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9e120-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9e120-115">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="9e120-115">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9e120-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9e120-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9e120-117">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="9e120-117">The call timed out.</span></span>|  
|<span data-ttu-id="9e120-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9e120-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9e120-119">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="9e120-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9e120-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9e120-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9e120-121">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="9e120-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9e120-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9e120-122">E_FAIL</span></span>|<span data-ttu-id="9e120-123">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="9e120-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9e120-124">После того как метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="9e120-124">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9e120-125">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="9e120-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="9e120-126">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="9e120-126">E_INVALIDARG</span></span>|<span data-ttu-id="9e120-127">Действие политики не может быть задано для указанной операции, или для операции указано недопустимое действие политики.</span><span class="sxs-lookup"><span data-stu-id="9e120-127">A policy action cannot be set for the specified operation, or an invalid policy action was specified for the operation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9e120-128">Комментарии</span><span class="sxs-lookup"><span data-stu-id="9e120-128">Remarks</span></span>  
 <span data-ttu-id="9e120-129">По умолчанию среда CLR создает исключение, когда не удается выделить ресурс, например память.</span><span class="sxs-lookup"><span data-stu-id="9e120-129">By default, the CLR throws an exception when it fails to allocate a resource such as memory.</span></span> <span data-ttu-id="9e120-130">`SetActionOnFailure`позволяет узлу переопределить это поведение, указав действие политики для выполнения при сбое.</span><span class="sxs-lookup"><span data-stu-id="9e120-130">`SetActionOnFailure` allows the host to override this behavior by specifying the policy action to take upon failure.</span></span> <span data-ttu-id="9e120-131">В следующей таблице показаны поддерживаемые сочетания значений [еклрфаилуре](eclrfailure-enumeration.md) и [еполициактион](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="9e120-131">The following table shows the combinations of [EClrFailure](eclrfailure-enumeration.md) and [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values that are supported.</span></span> <span data-ttu-id="9e120-132">(Префикс FAIL_ опущен из значений [еклрфаилуре](eclrfailure-enumeration.md) .)</span><span class="sxs-lookup"><span data-stu-id="9e120-132">(The FAIL_ prefix is omitted from [EClrFailure](eclrfailure-enumeration.md) values.)</span></span>  
  
||<span data-ttu-id="9e120-133">нонкритикалресаурце</span><span class="sxs-lookup"><span data-stu-id="9e120-133">NonCriticalResource</span></span>|<span data-ttu-id="9e120-134">критикалресаурце</span><span class="sxs-lookup"><span data-stu-id="9e120-134">CriticalResource</span></span>|<span data-ttu-id="9e120-135">фаталрунтиме</span><span class="sxs-lookup"><span data-stu-id="9e120-135">FatalRuntime</span></span>|<span data-ttu-id="9e120-136">орфанедлокк</span><span class="sxs-lookup"><span data-stu-id="9e120-136">OrphanedLock</span></span>|<span data-ttu-id="9e120-137">StackOverflow</span><span class="sxs-lookup"><span data-stu-id="9e120-137">StackOverflow</span></span>|<span data-ttu-id="9e120-138">AccessViolationException</span><span class="sxs-lookup"><span data-stu-id="9e120-138">AccessViolation</span></span>|<span data-ttu-id="9e120-139">кодеконтракт</span><span class="sxs-lookup"><span data-stu-id="9e120-139">CodeContract</span></span>|  
|-|-------------------------|----------------------|------------------|------------------|-------------------|---------------------|------------------|  
|`eNoAction`|<span data-ttu-id="9e120-140">X</span><span class="sxs-lookup"><span data-stu-id="9e120-140">X</span></span>|<span data-ttu-id="9e120-141">X</span><span class="sxs-lookup"><span data-stu-id="9e120-141">X</span></span>||||<span data-ttu-id="9e120-142">Недоступно</span><span class="sxs-lookup"><span data-stu-id="9e120-142">N/A</span></span>||  
|<span data-ttu-id="9e120-143">есровексцептион</span><span class="sxs-lookup"><span data-stu-id="9e120-143">eThrowException</span></span>|<span data-ttu-id="9e120-144">X</span><span class="sxs-lookup"><span data-stu-id="9e120-144">X</span></span>|<span data-ttu-id="9e120-145">X</span><span class="sxs-lookup"><span data-stu-id="9e120-145">X</span></span>||||<span data-ttu-id="9e120-146">Недоступно</span><span class="sxs-lookup"><span data-stu-id="9e120-146">N/A</span></span>||  
|`eAbortThread`|<span data-ttu-id="9e120-147">X</span><span class="sxs-lookup"><span data-stu-id="9e120-147">X</span></span>|<span data-ttu-id="9e120-148">X</span><span class="sxs-lookup"><span data-stu-id="9e120-148">X</span></span>||||<span data-ttu-id="9e120-149">Недоступно</span><span class="sxs-lookup"><span data-stu-id="9e120-149">N/A</span></span>|<span data-ttu-id="9e120-150">X</span><span class="sxs-lookup"><span data-stu-id="9e120-150">X</span></span>|  
|`eRudeAbortThread`|<span data-ttu-id="9e120-151">X</span><span class="sxs-lookup"><span data-stu-id="9e120-151">X</span></span>|<span data-ttu-id="9e120-152">X</span><span class="sxs-lookup"><span data-stu-id="9e120-152">X</span></span>||||<span data-ttu-id="9e120-153">Недоступно</span><span class="sxs-lookup"><span data-stu-id="9e120-153">N/A</span></span>|<span data-ttu-id="9e120-154">X</span><span class="sxs-lookup"><span data-stu-id="9e120-154">X</span></span>|  
|`eUnloadAppDomain`|<span data-ttu-id="9e120-155">X</span><span class="sxs-lookup"><span data-stu-id="9e120-155">X</span></span>|<span data-ttu-id="9e120-156">X</span><span class="sxs-lookup"><span data-stu-id="9e120-156">X</span></span>||<span data-ttu-id="9e120-157">X</span><span class="sxs-lookup"><span data-stu-id="9e120-157">X</span></span>||<span data-ttu-id="9e120-158">Недоступно</span><span class="sxs-lookup"><span data-stu-id="9e120-158">N/A</span></span>|<span data-ttu-id="9e120-159">X</span><span class="sxs-lookup"><span data-stu-id="9e120-159">X</span></span>|  
|`eRudeUnloadAppDomain`|<span data-ttu-id="9e120-160">X</span><span class="sxs-lookup"><span data-stu-id="9e120-160">X</span></span>|<span data-ttu-id="9e120-161">X</span><span class="sxs-lookup"><span data-stu-id="9e120-161">X</span></span>||<span data-ttu-id="9e120-162">X</span><span class="sxs-lookup"><span data-stu-id="9e120-162">X</span></span>|<span data-ttu-id="9e120-163">X</span><span class="sxs-lookup"><span data-stu-id="9e120-163">X</span></span>|<span data-ttu-id="9e120-164">Недоступно</span><span class="sxs-lookup"><span data-stu-id="9e120-164">N/A</span></span>|<span data-ttu-id="9e120-165">X</span><span class="sxs-lookup"><span data-stu-id="9e120-165">X</span></span>|  
|`eExitProcess`|<span data-ttu-id="9e120-166">X</span><span class="sxs-lookup"><span data-stu-id="9e120-166">X</span></span>|<span data-ttu-id="9e120-167">X</span><span class="sxs-lookup"><span data-stu-id="9e120-167">X</span></span>||<span data-ttu-id="9e120-168">X</span><span class="sxs-lookup"><span data-stu-id="9e120-168">X</span></span>|<span data-ttu-id="9e120-169">X</span><span class="sxs-lookup"><span data-stu-id="9e120-169">X</span></span>|<span data-ttu-id="9e120-170">Недоступно</span><span class="sxs-lookup"><span data-stu-id="9e120-170">N/A</span></span>|<span data-ttu-id="9e120-171">X</span><span class="sxs-lookup"><span data-stu-id="9e120-171">X</span></span>|  
|<span data-ttu-id="9e120-172">ефастекситпроцесс</span><span class="sxs-lookup"><span data-stu-id="9e120-172">eFastExitProcess</span></span>|<span data-ttu-id="9e120-173">X</span><span class="sxs-lookup"><span data-stu-id="9e120-173">X</span></span>|<span data-ttu-id="9e120-174">X</span><span class="sxs-lookup"><span data-stu-id="9e120-174">X</span></span>||<span data-ttu-id="9e120-175">X</span><span class="sxs-lookup"><span data-stu-id="9e120-175">X</span></span>|<span data-ttu-id="9e120-176">X</span><span class="sxs-lookup"><span data-stu-id="9e120-176">X</span></span>|<span data-ttu-id="9e120-177">Недоступно</span><span class="sxs-lookup"><span data-stu-id="9e120-177">N/A</span></span>||  
|`eRudeExitProcess`|<span data-ttu-id="9e120-178">X</span><span class="sxs-lookup"><span data-stu-id="9e120-178">X</span></span>|<span data-ttu-id="9e120-179">X</span><span class="sxs-lookup"><span data-stu-id="9e120-179">X</span></span>|<span data-ttu-id="9e120-180">X</span><span class="sxs-lookup"><span data-stu-id="9e120-180">X</span></span>|<span data-ttu-id="9e120-181">X</span><span class="sxs-lookup"><span data-stu-id="9e120-181">X</span></span>|<span data-ttu-id="9e120-182">X</span><span class="sxs-lookup"><span data-stu-id="9e120-182">X</span></span>|<span data-ttu-id="9e120-183">Недоступно</span><span class="sxs-lookup"><span data-stu-id="9e120-183">N/A</span></span>||  
|`eDisableRuntime`|<span data-ttu-id="9e120-184">X</span><span class="sxs-lookup"><span data-stu-id="9e120-184">X</span></span>|<span data-ttu-id="9e120-185">X</span><span class="sxs-lookup"><span data-stu-id="9e120-185">X</span></span>|<span data-ttu-id="9e120-186">X</span><span class="sxs-lookup"><span data-stu-id="9e120-186">X</span></span>|<span data-ttu-id="9e120-187">X</span><span class="sxs-lookup"><span data-stu-id="9e120-187">X</span></span>|<span data-ttu-id="9e120-188">X</span><span class="sxs-lookup"><span data-stu-id="9e120-188">X</span></span>|<span data-ttu-id="9e120-189">Недоступно</span><span class="sxs-lookup"><span data-stu-id="9e120-189">N/A</span></span>||  
  
## <a name="requirements"></a><span data-ttu-id="9e120-190">Требования</span><span class="sxs-lookup"><span data-stu-id="9e120-190">Requirements</span></span>  
 <span data-ttu-id="9e120-191">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9e120-191">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e120-192">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="9e120-192">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9e120-193">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="9e120-193">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9e120-194">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e120-194">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e120-195">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="9e120-195">See also</span></span>

- [<span data-ttu-id="9e120-196">Перечисление EClrFailure</span><span class="sxs-lookup"><span data-stu-id="9e120-196">EClrFailure Enumeration</span></span>](eclrfailure-enumeration.md)
- [<span data-ttu-id="9e120-197">Перечисление EPolicyAction</span><span class="sxs-lookup"><span data-stu-id="9e120-197">EPolicyAction Enumeration</span></span>](epolicyaction-enumeration.md)
- [<span data-ttu-id="9e120-198">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="9e120-198">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="9e120-199">Интерфейс ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="9e120-199">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
