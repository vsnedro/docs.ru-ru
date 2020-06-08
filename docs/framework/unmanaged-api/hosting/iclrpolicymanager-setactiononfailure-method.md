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
ms.openlocfilehash: 727cd82226b9a59c4879ffea5e87f93dd5fe38c9
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504112"
---
# <a name="iclrpolicymanagersetactiononfailure-method"></a><span data-ttu-id="579d7-102">Метод ICLRPolicyManager::SetActionOnFailure</span><span class="sxs-lookup"><span data-stu-id="579d7-102">ICLRPolicyManager::SetActionOnFailure Method</span></span>
<span data-ttu-id="579d7-103">Указывает действие политики, которое должна выполнять среда CLR при возникновении указанного сбоя.</span><span class="sxs-lookup"><span data-stu-id="579d7-103">Specifies the policy action the common language runtime (CLR) should take when the specified failure occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="579d7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="579d7-104">Syntax</span></span>  
  
```cpp  
HRESULT SetActionOnFailure (  
    [in] EClrFailure   failure,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="579d7-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="579d7-105">Parameters</span></span>  
 `failure`  
 <span data-ttu-id="579d7-106">окне Одно из значений [еклрфаилуре](eclrfailure-enumeration.md) , указывающее тип сбоя, для которого необходимо выполнить действие.</span><span class="sxs-lookup"><span data-stu-id="579d7-106">[in] One of the [EClrFailure](eclrfailure-enumeration.md) values, indicating the type of failure for which to take action.</span></span>  
  
 `action`  
 <span data-ttu-id="579d7-107">окне Одно из значений [еполициактион](epolicyaction-enumeration.md) , указывающее действие, выполняемое в случае сбоя.</span><span class="sxs-lookup"><span data-stu-id="579d7-107">[in] One of the [EPolicyAction](epolicyaction-enumeration.md) values, indicating the action to be taken when a failure occurs.</span></span> <span data-ttu-id="579d7-108">Список поддерживаемых значений см. в разделе "Примечания".</span><span class="sxs-lookup"><span data-stu-id="579d7-108">For a list of supported values, see the Remarks section.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="579d7-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="579d7-109">Return Value</span></span>  
  
|<span data-ttu-id="579d7-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="579d7-110">HRESULT</span></span>|<span data-ttu-id="579d7-111">Описание</span><span class="sxs-lookup"><span data-stu-id="579d7-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="579d7-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="579d7-112">S_OK</span></span>|<span data-ttu-id="579d7-113">`SetActionOnFailure`успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="579d7-113">`SetActionOnFailure` returned successfully.</span></span>|  
|<span data-ttu-id="579d7-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="579d7-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="579d7-115">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="579d7-115">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="579d7-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="579d7-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="579d7-117">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="579d7-117">The call timed out.</span></span>|  
|<span data-ttu-id="579d7-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="579d7-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="579d7-119">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="579d7-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="579d7-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="579d7-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="579d7-121">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="579d7-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="579d7-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="579d7-122">E_FAIL</span></span>|<span data-ttu-id="579d7-123">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="579d7-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="579d7-124">После того как метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="579d7-124">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="579d7-125">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="579d7-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="579d7-126">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="579d7-126">E_INVALIDARG</span></span>|<span data-ttu-id="579d7-127">Действие политики не может быть задано для указанной операции, или для операции указано недопустимое действие политики.</span><span class="sxs-lookup"><span data-stu-id="579d7-127">A policy action cannot be set for the specified operation, or an invalid policy action was specified for the operation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="579d7-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="579d7-128">Remarks</span></span>  
 <span data-ttu-id="579d7-129">По умолчанию среда CLR создает исключение, когда не удается выделить ресурс, например память.</span><span class="sxs-lookup"><span data-stu-id="579d7-129">By default, the CLR throws an exception when it fails to allocate a resource such as memory.</span></span> <span data-ttu-id="579d7-130">`SetActionOnFailure`позволяет узлу переопределить это поведение, указав действие политики для выполнения при сбое.</span><span class="sxs-lookup"><span data-stu-id="579d7-130">`SetActionOnFailure` allows the host to override this behavior by specifying the policy action to take upon failure.</span></span> <span data-ttu-id="579d7-131">В следующей таблице показаны поддерживаемые сочетания значений [еклрфаилуре](eclrfailure-enumeration.md) и [еполициактион](epolicyaction-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="579d7-131">The following table shows the combinations of [EClrFailure](eclrfailure-enumeration.md) and [EPolicyAction](epolicyaction-enumeration.md) values that are supported.</span></span> <span data-ttu-id="579d7-132">(Префикс FAIL_ опущен из значений [еклрфаилуре](eclrfailure-enumeration.md) .)</span><span class="sxs-lookup"><span data-stu-id="579d7-132">(The FAIL_ prefix is omitted from [EClrFailure](eclrfailure-enumeration.md) values.)</span></span>  
  
||<span data-ttu-id="579d7-133">нонкритикалресаурце</span><span class="sxs-lookup"><span data-stu-id="579d7-133">NonCriticalResource</span></span>|<span data-ttu-id="579d7-134">критикалресаурце</span><span class="sxs-lookup"><span data-stu-id="579d7-134">CriticalResource</span></span>|<span data-ttu-id="579d7-135">фаталрунтиме</span><span class="sxs-lookup"><span data-stu-id="579d7-135">FatalRuntime</span></span>|<span data-ttu-id="579d7-136">орфанедлокк</span><span class="sxs-lookup"><span data-stu-id="579d7-136">OrphanedLock</span></span>|<span data-ttu-id="579d7-137">StackOverflow</span><span class="sxs-lookup"><span data-stu-id="579d7-137">StackOverflow</span></span>|<span data-ttu-id="579d7-138">AccessViolationException</span><span class="sxs-lookup"><span data-stu-id="579d7-138">AccessViolation</span></span>|<span data-ttu-id="579d7-139">кодеконтракт</span><span class="sxs-lookup"><span data-stu-id="579d7-139">CodeContract</span></span>|  
|-|-------------------------|----------------------|------------------|------------------|-------------------|---------------------|------------------|  
|`eNoAction`|<span data-ttu-id="579d7-140">X</span><span class="sxs-lookup"><span data-stu-id="579d7-140">X</span></span>|<span data-ttu-id="579d7-141">X</span><span class="sxs-lookup"><span data-stu-id="579d7-141">X</span></span>||||<span data-ttu-id="579d7-142">Н/Д</span><span class="sxs-lookup"><span data-stu-id="579d7-142">N/A</span></span>||  
|<span data-ttu-id="579d7-143">есровексцептион</span><span class="sxs-lookup"><span data-stu-id="579d7-143">eThrowException</span></span>|<span data-ttu-id="579d7-144">X</span><span class="sxs-lookup"><span data-stu-id="579d7-144">X</span></span>|<span data-ttu-id="579d7-145">X</span><span class="sxs-lookup"><span data-stu-id="579d7-145">X</span></span>||||<span data-ttu-id="579d7-146">Н/Д</span><span class="sxs-lookup"><span data-stu-id="579d7-146">N/A</span></span>||  
|`eAbortThread`|<span data-ttu-id="579d7-147">X</span><span class="sxs-lookup"><span data-stu-id="579d7-147">X</span></span>|<span data-ttu-id="579d7-148">X</span><span class="sxs-lookup"><span data-stu-id="579d7-148">X</span></span>||||<span data-ttu-id="579d7-149">Н/Д</span><span class="sxs-lookup"><span data-stu-id="579d7-149">N/A</span></span>|<span data-ttu-id="579d7-150">X</span><span class="sxs-lookup"><span data-stu-id="579d7-150">X</span></span>|  
|`eRudeAbortThread`|<span data-ttu-id="579d7-151">X</span><span class="sxs-lookup"><span data-stu-id="579d7-151">X</span></span>|<span data-ttu-id="579d7-152">X</span><span class="sxs-lookup"><span data-stu-id="579d7-152">X</span></span>||||<span data-ttu-id="579d7-153">Н/Д</span><span class="sxs-lookup"><span data-stu-id="579d7-153">N/A</span></span>|<span data-ttu-id="579d7-154">X</span><span class="sxs-lookup"><span data-stu-id="579d7-154">X</span></span>|  
|`eUnloadAppDomain`|<span data-ttu-id="579d7-155">X</span><span class="sxs-lookup"><span data-stu-id="579d7-155">X</span></span>|<span data-ttu-id="579d7-156">X</span><span class="sxs-lookup"><span data-stu-id="579d7-156">X</span></span>||<span data-ttu-id="579d7-157">X</span><span class="sxs-lookup"><span data-stu-id="579d7-157">X</span></span>||<span data-ttu-id="579d7-158">Н/Д</span><span class="sxs-lookup"><span data-stu-id="579d7-158">N/A</span></span>|<span data-ttu-id="579d7-159">X</span><span class="sxs-lookup"><span data-stu-id="579d7-159">X</span></span>|  
|`eRudeUnloadAppDomain`|<span data-ttu-id="579d7-160">X</span><span class="sxs-lookup"><span data-stu-id="579d7-160">X</span></span>|<span data-ttu-id="579d7-161">X</span><span class="sxs-lookup"><span data-stu-id="579d7-161">X</span></span>||<span data-ttu-id="579d7-162">X</span><span class="sxs-lookup"><span data-stu-id="579d7-162">X</span></span>|<span data-ttu-id="579d7-163">X</span><span class="sxs-lookup"><span data-stu-id="579d7-163">X</span></span>|<span data-ttu-id="579d7-164">Н/Д</span><span class="sxs-lookup"><span data-stu-id="579d7-164">N/A</span></span>|<span data-ttu-id="579d7-165">X</span><span class="sxs-lookup"><span data-stu-id="579d7-165">X</span></span>|  
|`eExitProcess`|<span data-ttu-id="579d7-166">X</span><span class="sxs-lookup"><span data-stu-id="579d7-166">X</span></span>|<span data-ttu-id="579d7-167">X</span><span class="sxs-lookup"><span data-stu-id="579d7-167">X</span></span>||<span data-ttu-id="579d7-168">X</span><span class="sxs-lookup"><span data-stu-id="579d7-168">X</span></span>|<span data-ttu-id="579d7-169">X</span><span class="sxs-lookup"><span data-stu-id="579d7-169">X</span></span>|<span data-ttu-id="579d7-170">Н/Д</span><span class="sxs-lookup"><span data-stu-id="579d7-170">N/A</span></span>|<span data-ttu-id="579d7-171">X</span><span class="sxs-lookup"><span data-stu-id="579d7-171">X</span></span>|  
|<span data-ttu-id="579d7-172">ефастекситпроцесс</span><span class="sxs-lookup"><span data-stu-id="579d7-172">eFastExitProcess</span></span>|<span data-ttu-id="579d7-173">X</span><span class="sxs-lookup"><span data-stu-id="579d7-173">X</span></span>|<span data-ttu-id="579d7-174">X</span><span class="sxs-lookup"><span data-stu-id="579d7-174">X</span></span>||<span data-ttu-id="579d7-175">X</span><span class="sxs-lookup"><span data-stu-id="579d7-175">X</span></span>|<span data-ttu-id="579d7-176">X</span><span class="sxs-lookup"><span data-stu-id="579d7-176">X</span></span>|<span data-ttu-id="579d7-177">Н/Д</span><span class="sxs-lookup"><span data-stu-id="579d7-177">N/A</span></span>||  
|`eRudeExitProcess`|<span data-ttu-id="579d7-178">X</span><span class="sxs-lookup"><span data-stu-id="579d7-178">X</span></span>|<span data-ttu-id="579d7-179">X</span><span class="sxs-lookup"><span data-stu-id="579d7-179">X</span></span>|<span data-ttu-id="579d7-180">X</span><span class="sxs-lookup"><span data-stu-id="579d7-180">X</span></span>|<span data-ttu-id="579d7-181">X</span><span class="sxs-lookup"><span data-stu-id="579d7-181">X</span></span>|<span data-ttu-id="579d7-182">X</span><span class="sxs-lookup"><span data-stu-id="579d7-182">X</span></span>|<span data-ttu-id="579d7-183">Н/Д</span><span class="sxs-lookup"><span data-stu-id="579d7-183">N/A</span></span>||  
|`eDisableRuntime`|<span data-ttu-id="579d7-184">X</span><span class="sxs-lookup"><span data-stu-id="579d7-184">X</span></span>|<span data-ttu-id="579d7-185">X</span><span class="sxs-lookup"><span data-stu-id="579d7-185">X</span></span>|<span data-ttu-id="579d7-186">X</span><span class="sxs-lookup"><span data-stu-id="579d7-186">X</span></span>|<span data-ttu-id="579d7-187">X</span><span class="sxs-lookup"><span data-stu-id="579d7-187">X</span></span>|<span data-ttu-id="579d7-188">X</span><span class="sxs-lookup"><span data-stu-id="579d7-188">X</span></span>|<span data-ttu-id="579d7-189">Н/Д</span><span class="sxs-lookup"><span data-stu-id="579d7-189">N/A</span></span>||  
  
## <a name="requirements"></a><span data-ttu-id="579d7-190">Требования</span><span class="sxs-lookup"><span data-stu-id="579d7-190">Requirements</span></span>  
 <span data-ttu-id="579d7-191">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="579d7-191">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="579d7-192">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="579d7-192">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="579d7-193">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="579d7-193">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="579d7-194">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="579d7-194">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="579d7-195">См. также</span><span class="sxs-lookup"><span data-stu-id="579d7-195">See also</span></span>

- [<span data-ttu-id="579d7-196">Перечисление EClrFailure</span><span class="sxs-lookup"><span data-stu-id="579d7-196">EClrFailure Enumeration</span></span>](eclrfailure-enumeration.md)
- [<span data-ttu-id="579d7-197">Перечисление EPolicyAction</span><span class="sxs-lookup"><span data-stu-id="579d7-197">EPolicyAction Enumeration</span></span>](epolicyaction-enumeration.md)
- [<span data-ttu-id="579d7-198">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="579d7-198">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="579d7-199">Интерфейс ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="579d7-199">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
