---
title: Метода ICLRRuntimeHost::ExecuteInAppDomain
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.ExecuteInAppDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::ExecuteInAppDomain
helpviewer_keywords:
- ICLRRuntimeHost::ExecuteInAppDomain method [.NET Framework hosting]
- ExecuteInAppDomain method [.NET Framework hosting]
ms.assetid: e2b0e2db-3fae-4b56-844e-d30a125a660c
topic_type:
- apiref
ms.openlocfilehash: 4c28c4a5cc64b20c9ac9c57e1aef5e7b90a20e01
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728892"
---
# <a name="iclrruntimehostexecuteinappdomain-method"></a><span data-ttu-id="818cf-102">Метода ICLRRuntimeHost::ExecuteInAppDomain</span><span class="sxs-lookup"><span data-stu-id="818cf-102">ICLRRuntimeHost::ExecuteInAppDomain Method</span></span>

<span data-ttu-id="818cf-103">Указывает, <xref:System.AppDomain> в котором следует выполнить указанный управляемый код.</span><span class="sxs-lookup"><span data-stu-id="818cf-103">Specifies the <xref:System.AppDomain> in which to execute the specified managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="818cf-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="818cf-104">Syntax</span></span>  
  
```cpp  
HRESULT ExecuteInAppDomain(  
    [in] DWORD AppDomainId,
    [in] FExecuteInDomainCallback pCallback,
    [in] void* cookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="818cf-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="818cf-105">Parameters</span></span>  

 `AppDomainId`  
 <span data-ttu-id="818cf-106">окне Числовой идентификатор объекта, <xref:System.AppDomain> в котором выполняется указанный метод.</span><span class="sxs-lookup"><span data-stu-id="818cf-106">[in] The numeric ID of the <xref:System.AppDomain> in which to execute the specified method.</span></span>  
  
 `pCallback`  
 <span data-ttu-id="818cf-107">окне Указатель на функцию, которую необходимо выполнить в указанном объекте <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="818cf-107">[in] A pointer to the function to execute within the specified <xref:System.AppDomain>.</span></span>  
  
 `cookie`  
 <span data-ttu-id="818cf-108">окне Указатель на непрозрачную память, выделенную вызывающим объектом.</span><span class="sxs-lookup"><span data-stu-id="818cf-108">[in] A pointer to opaque caller-allocated memory.</span></span> <span data-ttu-id="818cf-109">Этот параметр передается средой CLR в обратный вызов домена.</span><span class="sxs-lookup"><span data-stu-id="818cf-109">This parameter is passed by the common language runtime (CLR) to the domain callback.</span></span> <span data-ttu-id="818cf-110">Это не управляемая средой выполнения память кучи; как выделение, так и время существования этой памяти контролируются вызывающим объектом.</span><span class="sxs-lookup"><span data-stu-id="818cf-110">It is not runtime-managed heap memory; both the allocation and lifetime of this memory are controlled by the caller.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="818cf-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="818cf-111">Return Value</span></span>  
  
|<span data-ttu-id="818cf-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="818cf-112">HRESULT</span></span>|<span data-ttu-id="818cf-113">Описание:</span><span class="sxs-lookup"><span data-stu-id="818cf-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="818cf-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="818cf-114">S_OK</span></span>|<span data-ttu-id="818cf-115">`ExecuteInAppDomain` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="818cf-115">`ExecuteInAppDomain` returned successfully.</span></span>|  
|<span data-ttu-id="818cf-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="818cf-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="818cf-117">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="818cf-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="818cf-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="818cf-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="818cf-119">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="818cf-119">The call timed out.</span></span>|  
|<span data-ttu-id="818cf-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="818cf-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="818cf-121">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="818cf-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="818cf-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="818cf-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="818cf-123">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="818cf-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="818cf-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="818cf-124">E_FAIL</span></span>|<span data-ttu-id="818cf-125">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="818cf-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="818cf-126">Если метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="818cf-126">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="818cf-127">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="818cf-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="818cf-128">Комментарии</span><span class="sxs-lookup"><span data-stu-id="818cf-128">Remarks</span></span>  

 <span data-ttu-id="818cf-129">`ExecuteInAppDomain` позволяет ведущему приложению осуществлять контроль над тем, какой управляемым <xref:System.AppDomain> указанным управляемым методом следует выполнять в.</span><span class="sxs-lookup"><span data-stu-id="818cf-129">`ExecuteInAppDomain` allows the host to exercise control over which managed <xref:System.AppDomain> the specified managed method should be executed in.</span></span> <span data-ttu-id="818cf-130">Можно получить значение идентификатора домена приложения, которое соответствует значению <xref:System.AppDomain.Id%2A> свойства, вызвав [метод жеткуррентаппдомаинид](iclrruntimehost-getcurrentappdomainid-method.md).</span><span class="sxs-lookup"><span data-stu-id="818cf-130">You can get the value of an application domain's identifier, which corresponds to the value of the <xref:System.AppDomain.Id%2A> property, by calling [GetCurrentAppDomainId Method](iclrruntimehost-getcurrentappdomainid-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="818cf-131">Требования</span><span class="sxs-lookup"><span data-stu-id="818cf-131">Requirements</span></span>  

 <span data-ttu-id="818cf-132">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="818cf-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="818cf-133">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="818cf-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="818cf-134">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="818cf-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="818cf-135">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="818cf-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="818cf-136">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="818cf-136">See also</span></span>

- [<span data-ttu-id="818cf-137">Интерфейс ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="818cf-137">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)
