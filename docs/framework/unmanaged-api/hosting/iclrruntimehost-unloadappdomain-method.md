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
ms.openlocfilehash: 293c1764f4c0d857138726b8ed4855b1e3b03116
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703922"
---
# <a name="iclrruntimehostunloadappdomain-method"></a><span data-ttu-id="64113-102">Метод ICLRRuntimeHost::UnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="64113-102">ICLRRuntimeHost::UnloadAppDomain Method</span></span>
<span data-ttu-id="64113-103">Выгружает управляемый объект <xref:System.AppDomain> , соответствующий указанному числовому идентификатору.</span><span class="sxs-lookup"><span data-stu-id="64113-103">Unloads the managed <xref:System.AppDomain> that corresponds to the specified numeric identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64113-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="64113-104">Syntax</span></span>  
  
```cpp  
HRESULT UnloadAppDomain(  
    [in] DWORD dwAppDomainId  
    [in] BOOL  fWaitUntilDone  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="64113-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="64113-105">Parameters</span></span>  
 `dwAppDomainId`  
 <span data-ttu-id="64113-106">окне Числовой идентификатор домена приложения для выгрузки.</span><span class="sxs-lookup"><span data-stu-id="64113-106">[in] The numeric identifier of the application domain to unload.</span></span>  
  
 `fWaitUntilDone`  
 <span data-ttu-id="64113-107">[входные] `true` чтобы указать, что общеязыковая среда выполнения (CLR) должна ожидать завершения выполнения текущего потока приложения перед попыткой выгрузить домен приложения.</span><span class="sxs-lookup"><span data-stu-id="64113-107">[in] `true` to indicate that the common language runtime( CLR) must wait until it has finished executing the application's current thread before attempting to unload the application domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="64113-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="64113-108">Return Value</span></span>  
  
|<span data-ttu-id="64113-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="64113-109">HRESULT</span></span>|<span data-ttu-id="64113-110">Описание</span><span class="sxs-lookup"><span data-stu-id="64113-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="64113-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="64113-111">S_OK</span></span>|<span data-ttu-id="64113-112">`UnloadAppDomain`успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="64113-112">`UnloadAppDomain` returned successfully.</span></span>|  
|<span data-ttu-id="64113-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="64113-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="64113-114">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="64113-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="64113-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="64113-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="64113-116">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="64113-116">The call timed out.</span></span>|  
|<span data-ttu-id="64113-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="64113-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="64113-118">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="64113-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="64113-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="64113-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="64113-120">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="64113-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="64113-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="64113-121">E_FAIL</span></span>|<span data-ttu-id="64113-122">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="64113-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="64113-123">Если метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="64113-123">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="64113-124">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="64113-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="64113-125">Комментарии</span><span class="sxs-lookup"><span data-stu-id="64113-125">Remarks</span></span>  
 <span data-ttu-id="64113-126">Вы можете получить числовой идентификатор домена приложения, в котором выполняется текущий поток, вызвав [жеткуррентаппдомаинид](iclrruntimehost-getcurrentappdomainid-method.md).</span><span class="sxs-lookup"><span data-stu-id="64113-126">You can get the numeric identifier of the application domain in which the current thread is executing by calling [GetCurrentAppDomainId](iclrruntimehost-getcurrentappdomainid-method.md).</span></span> <span data-ttu-id="64113-127">Этот идентификатор соответствует <xref:System.AppDomain.Id%2A> свойству управляемого <xref:System.AppDomain> типа.</span><span class="sxs-lookup"><span data-stu-id="64113-127">This identifier corresponds to the <xref:System.AppDomain.Id%2A> property of the managed <xref:System.AppDomain> type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64113-128">Требования</span><span class="sxs-lookup"><span data-stu-id="64113-128">Requirements</span></span>  
 <span data-ttu-id="64113-129">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="64113-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64113-130">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="64113-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="64113-131">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="64113-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="64113-132">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64113-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64113-133">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="64113-133">See also</span></span>

- [<span data-ttu-id="64113-134">Интерфейс ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="64113-134">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)
