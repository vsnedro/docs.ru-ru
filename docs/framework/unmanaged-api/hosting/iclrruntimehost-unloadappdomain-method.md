---
title: Метод ICLRRuntimeHost::UnloadAppDomain
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.UnloadAppDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::UnloadAppDomain
helpviewer_keywords:
- ICLRRuntimeHost::UnloadAppDomain method [.NET Framework hosting]
- UnloadAppDomain method [.NET Framework hosting]
ms.assetid: 571912bc-3429-4ff8-8eb2-ea993ffbd901
topic_type:
- apiref
ms.openlocfilehash: cc5d0d65d213d952c0897a72d8ec38ea6b8b22db
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95700669"
---
# <a name="iclrruntimehostunloadappdomain-method"></a><span data-ttu-id="13e39-102">Метод ICLRRuntimeHost::UnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="13e39-102">ICLRRuntimeHost::UnloadAppDomain Method</span></span>

<span data-ttu-id="13e39-103">Выгружает управляемый объект <xref:System.AppDomain> , соответствующий указанному числовому идентификатору.</span><span class="sxs-lookup"><span data-stu-id="13e39-103">Unloads the managed <xref:System.AppDomain> that corresponds to the specified numeric identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13e39-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="13e39-104">Syntax</span></span>  
  
```cpp  
HRESULT UnloadAppDomain(  
    [in] DWORD dwAppDomainId  
    [in] BOOL  fWaitUntilDone  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="13e39-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="13e39-105">Parameters</span></span>  

 `dwAppDomainId`  
 <span data-ttu-id="13e39-106">окне Числовой идентификатор домена приложения для выгрузки.</span><span class="sxs-lookup"><span data-stu-id="13e39-106">[in] The numeric identifier of the application domain to unload.</span></span>  
  
 `fWaitUntilDone`  
 <span data-ttu-id="13e39-107">[входные] `true` чтобы указать, что общеязыковая среда выполнения (CLR) должна ожидать завершения выполнения текущего потока приложения перед попыткой выгрузить домен приложения.</span><span class="sxs-lookup"><span data-stu-id="13e39-107">[in] `true` to indicate that the common language runtime( CLR) must wait until it has finished executing the application's current thread before attempting to unload the application domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="13e39-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="13e39-108">Return Value</span></span>  
  
|<span data-ttu-id="13e39-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="13e39-109">HRESULT</span></span>|<span data-ttu-id="13e39-110">Описание:</span><span class="sxs-lookup"><span data-stu-id="13e39-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="13e39-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="13e39-111">S_OK</span></span>|<span data-ttu-id="13e39-112">`UnloadAppDomain` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="13e39-112">`UnloadAppDomain` returned successfully.</span></span>|  
|<span data-ttu-id="13e39-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="13e39-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="13e39-114">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="13e39-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="13e39-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="13e39-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="13e39-116">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="13e39-116">The call timed out.</span></span>|  
|<span data-ttu-id="13e39-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="13e39-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="13e39-118">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="13e39-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="13e39-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="13e39-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="13e39-120">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="13e39-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="13e39-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="13e39-121">E_FAIL</span></span>|<span data-ttu-id="13e39-122">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="13e39-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="13e39-123">Если метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="13e39-123">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="13e39-124">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="13e39-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="13e39-125">Комментарии</span><span class="sxs-lookup"><span data-stu-id="13e39-125">Remarks</span></span>  

 <span data-ttu-id="13e39-126">Вы можете получить числовой идентификатор домена приложения, в котором выполняется текущий поток, вызвав [жеткуррентаппдомаинид](iclrruntimehost-getcurrentappdomainid-method.md).</span><span class="sxs-lookup"><span data-stu-id="13e39-126">You can get the numeric identifier of the application domain in which the current thread is executing by calling [GetCurrentAppDomainId](iclrruntimehost-getcurrentappdomainid-method.md).</span></span> <span data-ttu-id="13e39-127">Этот идентификатор соответствует <xref:System.AppDomain.Id%2A> свойству управляемого <xref:System.AppDomain> типа.</span><span class="sxs-lookup"><span data-stu-id="13e39-127">This identifier corresponds to the <xref:System.AppDomain.Id%2A> property of the managed <xref:System.AppDomain> type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13e39-128">Требования</span><span class="sxs-lookup"><span data-stu-id="13e39-128">Requirements</span></span>  

 <span data-ttu-id="13e39-129">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="13e39-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13e39-130">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="13e39-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="13e39-131">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="13e39-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="13e39-132">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13e39-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13e39-133">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="13e39-133">See also</span></span>

- [<span data-ttu-id="13e39-134">Интерфейс ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="13e39-134">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)
