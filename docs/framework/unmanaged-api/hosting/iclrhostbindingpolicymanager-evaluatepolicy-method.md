---
title: Метод ICLRHostBindingPolicyManager::EvaluatePolicy
ms.date: 03/30/2017
api_name:
- ICLRHostBindingPolicyManager.EvaluatePolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostBindingPolicyManager::EvaluatePolicy
helpviewer_keywords:
- ICLRHostBindingPolicyManager::EvaluatePolicy method [.NET Framework hosting]
- EvaluatePolicy method [.NET Framework hosting]
ms.assetid: 3a3a9446-7a4e-4836-9b27-5c536c15993d
topic_type:
- apiref
ms.openlocfilehash: f72a66354bfc907dab7ebc24de515bdfb20ddfb2
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703596"
---
# <a name="iclrhostbindingpolicymanagerevaluatepolicy-method"></a><span data-ttu-id="3c583-102">Метод ICLRHostBindingPolicyManager::EvaluatePolicy</span><span class="sxs-lookup"><span data-stu-id="3c583-102">ICLRHostBindingPolicyManager::EvaluatePolicy Method</span></span>
<span data-ttu-id="3c583-103">Оценивает политику привязки от имени узла.</span><span class="sxs-lookup"><span data-stu-id="3c583-103">Evaluates binding policy on behalf of the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c583-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3c583-104">Syntax</span></span>  
  
```cpp  
HRESULT EvaluatePolicy (  
    [in] LPCWSTR     pwzReferenceIdentity,  
    [in] BYTE       *pbApplicationPolicy,  
    [in] DWORD       cbAppPolicySize,  
    [out, size_is(*pcchPostPolicyReferenceIdentity)] LPWSTR pwzPostPolicyReferenceIdentity,  
    [in, out] DWORD *pcchPostPolicyReferenceIdentity,  
    [out] DWORD     *pdwPoliciesApplied  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3c583-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3c583-105">Parameters</span></span>  
 `pwzReferenceIdentity`  
 <span data-ttu-id="3c583-106">окне Ссылка на сборку перед вычислением политики.</span><span class="sxs-lookup"><span data-stu-id="3c583-106">[in] A reference to the assembly before the policy evaluation.</span></span>  
  
 `pbApplicationPolicy`  
 <span data-ttu-id="3c583-107">окне Указатель на буфер, содержащий данные политики.</span><span class="sxs-lookup"><span data-stu-id="3c583-107">[in] A pointer to a buffer that contains the policy data.</span></span>  
  
 `cbAppPolicySize`  
 <span data-ttu-id="3c583-108">окне Размер `pbApplicationPolicy` буфера.</span><span class="sxs-lookup"><span data-stu-id="3c583-108">[in] The size of the `pbApplicationPolicy` buffer.</span></span>  
  
 `pwzPostPolicyReferenceIdentity`  
 <span data-ttu-id="3c583-109">заполняет Ссылка на сборку после вычисления новых данных политики.</span><span class="sxs-lookup"><span data-stu-id="3c583-109">[out] A reference to the assembly after the evaluation of the new policy data.</span></span>  
  
 `pcchPostPolicyReferenceIdentity`  
 <span data-ttu-id="3c583-110">[вход, выход] Указатель на размер буфера ссылки идентификации сборки после вычисления новых данных политики.</span><span class="sxs-lookup"><span data-stu-id="3c583-110">[in, out] A pointer to the size of the assembly identity reference buffer after the evaluation of the new policy data.</span></span>  
  
 `pdwPoliciesApplied`  
 <span data-ttu-id="3c583-111">заполняет Указатель на логическое или сочетание значений [EBindPolicyLevels](ebindpolicylevels-enumeration.md) , указывающих, какие политики были применены.</span><span class="sxs-lookup"><span data-stu-id="3c583-111">[out] A pointer to a logical OR combination of [EBindPolicyLevels](ebindpolicylevels-enumeration.md) values, indicating which policies have been applied.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3c583-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3c583-112">Return Value</span></span>  
  
|<span data-ttu-id="3c583-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3c583-113">HRESULT</span></span>|<span data-ttu-id="3c583-114">Описание</span><span class="sxs-lookup"><span data-stu-id="3c583-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3c583-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="3c583-115">S_OK</span></span>|<span data-ttu-id="3c583-116">Оценка успешно завершена.</span><span class="sxs-lookup"><span data-stu-id="3c583-116">The evaluation completed successfully.</span></span>|  
|<span data-ttu-id="3c583-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="3c583-117">E_INVALIDARG</span></span>|<span data-ttu-id="3c583-118">Либо `pwzReferenceIdentity` `pbApplicationPolicy` является пустой ссылкой.</span><span class="sxs-lookup"><span data-stu-id="3c583-118">Either `pwzReferenceIdentity` or `pbApplicationPolicy` is a null reference.</span></span>|  
|<span data-ttu-id="3c583-119">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="3c583-119">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="3c583-120">`cbAppPolicySize` слишком мал.</span><span class="sxs-lookup"><span data-stu-id="3c583-120">`cbAppPolicySize` is too small.</span></span>|  
|<span data-ttu-id="3c583-121">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3c583-121">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3c583-122">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="3c583-122">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3c583-123">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3c583-123">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3c583-124">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="3c583-124">The call timed out.</span></span>|  
|<span data-ttu-id="3c583-125">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3c583-125">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3c583-126">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="3c583-126">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3c583-127">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3c583-127">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3c583-128">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="3c583-128">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3c583-129">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3c583-129">E_FAIL</span></span>|<span data-ttu-id="3c583-130">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="3c583-130">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3c583-131">После того как метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="3c583-131">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3c583-132">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="3c583-132">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3c583-133">Комментарии</span><span class="sxs-lookup"><span data-stu-id="3c583-133">Remarks</span></span>  
 <span data-ttu-id="3c583-134">`EvaluatePolicy`Метод позволяет основному приложению влиять на политику привязки, чтобы обеспечить соответствие требованиям к версии сборки, относящейся к конкретному узлу.</span><span class="sxs-lookup"><span data-stu-id="3c583-134">The `EvaluatePolicy` method allows the host to influence binding policy to maintain host-specific assembly versioning requirements.</span></span> <span data-ttu-id="3c583-135">Сам модуль политики остается внутри среды CLR.</span><span class="sxs-lookup"><span data-stu-id="3c583-135">The policy engine itself remains inside the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c583-136">Требования</span><span class="sxs-lookup"><span data-stu-id="3c583-136">Requirements</span></span>  
 <span data-ttu-id="3c583-137">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3c583-137">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c583-138">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="3c583-138">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3c583-139">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="3c583-139">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3c583-140">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c583-140">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c583-141">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="3c583-141">See also</span></span>

- [<span data-ttu-id="3c583-142">Интерфейс ICLRHostBindingPolicyManager</span><span class="sxs-lookup"><span data-stu-id="3c583-142">ICLRHostBindingPolicyManager Interface</span></span>](iclrhostbindingpolicymanager-interface.md)
