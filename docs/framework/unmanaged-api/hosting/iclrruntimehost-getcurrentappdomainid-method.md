---
title: Метод ICLRRuntimeHost::GetCurrentAppDomainId
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.GetCurrentAppDomainId
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::GetCurrentAppDomainId
helpviewer_keywords:
- ICLRRuntimeHost::GetCurrentAppDomainId method [.NET Framework hosting]
- GetCurrentAppDomainId method [.NET Framework hosting]
ms.assetid: 33800475-7815-4976-8aca-a1038761a2ef
topic_type:
- apiref
ms.openlocfilehash: 2b1c9e99604664c99960a0741de6eae6b38fe963
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728853"
---
# <a name="iclrruntimehostgetcurrentappdomainid-method"></a><span data-ttu-id="0e0d5-102">Метод ICLRRuntimeHost::GetCurrentAppDomainId</span><span class="sxs-lookup"><span data-stu-id="0e0d5-102">ICLRRuntimeHost::GetCurrentAppDomainId Method</span></span>

<span data-ttu-id="0e0d5-103">Возвращает числовой идентификатор объекта <xref:System.AppDomain> , который выполняется в данный момент.</span><span class="sxs-lookup"><span data-stu-id="0e0d5-103">Gets the numeric identifier of the <xref:System.AppDomain> that is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e0d5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0e0d5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentAppDomainId(  
    [out] DWORD* pdwAppDomainId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0e0d5-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0e0d5-105">Parameters</span></span>  

 `pdwAppDomainId`  
 <span data-ttu-id="0e0d5-106">заполняет Числовой идентификатор объекта <xref:System.AppDomain> , который выполняется в данный момент.</span><span class="sxs-lookup"><span data-stu-id="0e0d5-106">[out] The numeric identifier of the <xref:System.AppDomain> that is currently executing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0e0d5-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="0e0d5-107">Return Value</span></span>  
  
|<span data-ttu-id="0e0d5-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0e0d5-108">HRESULT</span></span>|<span data-ttu-id="0e0d5-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="0e0d5-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0e0d5-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="0e0d5-110">S_OK</span></span>|<span data-ttu-id="0e0d5-111">`GetCurrentAppDomainId` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="0e0d5-111">`GetCurrentAppDomainId` returned successfully.</span></span>|  
|<span data-ttu-id="0e0d5-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0e0d5-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0e0d5-113">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="0e0d5-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0e0d5-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0e0d5-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0e0d5-115">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="0e0d5-115">The call timed out.</span></span>|  
|<span data-ttu-id="0e0d5-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0e0d5-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0e0d5-117">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="0e0d5-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0e0d5-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0e0d5-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0e0d5-119">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="0e0d5-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0e0d5-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0e0d5-120">E_FAIL</span></span>|<span data-ttu-id="0e0d5-121">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="0e0d5-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0e0d5-122">Если метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="0e0d5-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0e0d5-123">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="0e0d5-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0e0d5-124">Комментарии</span><span class="sxs-lookup"><span data-stu-id="0e0d5-124">Remarks</span></span>  

 <span data-ttu-id="0e0d5-125">`pdwAppDomainId`Параметру присваивается значение <xref:System.AppDomain.Id%2A> свойства объекта, <xref:System.AppDomain> в котором выполняется текущий поток.</span><span class="sxs-lookup"><span data-stu-id="0e0d5-125">The `pdwAppDomainId` parameter is set to the value of the <xref:System.AppDomain.Id%2A> property of the <xref:System.AppDomain> in which the current thread is executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e0d5-126">Требования</span><span class="sxs-lookup"><span data-stu-id="0e0d5-126">Requirements</span></span>  

 <span data-ttu-id="0e0d5-127">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0e0d5-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e0d5-128">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="0e0d5-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0e0d5-129">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0e0d5-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0e0d5-130">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0e0d5-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e0d5-131">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="0e0d5-131">See also</span></span>

- <xref:System.AppDomain>
- <xref:System.AppDomainManager>
- [<span data-ttu-id="0e0d5-132">Интерфейс ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="0e0d5-132">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)
