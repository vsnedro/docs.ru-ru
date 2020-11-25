---
title: Метод ICorRuntimeHost::CreateDomainSetup
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.CreateDomainSetup
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CreateDomainSetup
helpviewer_keywords:
- CreateDomainSetup method [.NET Framework hosting]
- ICorRuntimeHost::CreateDomainSetup method [.NET Framework hosting]
ms.assetid: c21dab60-fb65-47d9-8a94-7fd47ca53b48
topic_type:
- apiref
ms.openlocfilehash: 1be7eee5c2591f26c33572446080a4fa4b3b929d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723900"
---
# <a name="icorruntimehostcreatedomainsetup-method"></a><span data-ttu-id="3cb2e-102">Метод ICorRuntimeHost::CreateDomainSetup</span><span class="sxs-lookup"><span data-stu-id="3cb2e-102">ICorRuntimeHost::CreateDomainSetup Method</span></span>

<span data-ttu-id="3cb2e-103">Возвращает указатель интерфейса типа IAppDomainSetup на <xref:System.AppDomainSetup?displayProperty=nameWithType> экземпляр.</span><span class="sxs-lookup"><span data-stu-id="3cb2e-103">Gets an interface pointer of type IAppDomainSetup to an <xref:System.AppDomainSetup?displayProperty=nameWithType> instance.</span></span> <span data-ttu-id="3cb2e-104">`IAppDomainSetup` предоставляет методы для настройки аспектов домена приложения перед его созданием.</span><span class="sxs-lookup"><span data-stu-id="3cb2e-104">`IAppDomainSetup` provides methods to configure aspects of an application domain before it is created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3cb2e-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3cb2e-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateDomainSetup (  
    [out] IUnknown** pAppDomainSetup  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3cb2e-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="3cb2e-106">Parameters</span></span>  

 `pAppDomainSetup`  
 <span data-ttu-id="3cb2e-107">заполняет Указатель интерфейса на <xref:System.AppDomainSetup?displayProperty=nameWithType> экземпляр.</span><span class="sxs-lookup"><span data-stu-id="3cb2e-107">[out] An interface pointer to an <xref:System.AppDomainSetup?displayProperty=nameWithType> instance.</span></span> <span data-ttu-id="3cb2e-108">Этот параметр типизирован как `IUnknown` , поэтому вызывающие объекты должны обычно вызывать `QueryInterface` этот указатель для получения указателя интерфейса типа `IAppDomainSetup` .</span><span class="sxs-lookup"><span data-stu-id="3cb2e-108">This parameter is typed as `IUnknown`, so callers should generally call `QueryInterface` on this pointer to obtain an interface pointer of type `IAppDomainSetup`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3cb2e-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3cb2e-109">Return Value</span></span>  
  
|<span data-ttu-id="3cb2e-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3cb2e-110">HRESULT</span></span>|<span data-ttu-id="3cb2e-111">Описание:</span><span class="sxs-lookup"><span data-stu-id="3cb2e-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3cb2e-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="3cb2e-112">S_OK</span></span>|<span data-ttu-id="3cb2e-113">Операция выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="3cb2e-113">The operation was successful.</span></span>|  
|<span data-ttu-id="3cb2e-114">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="3cb2e-114">S_FALSE</span></span>|<span data-ttu-id="3cb2e-115">Не удалось завершить операцию.</span><span class="sxs-lookup"><span data-stu-id="3cb2e-115">The operation failed to complete.</span></span>|  
|<span data-ttu-id="3cb2e-116">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3cb2e-116">E_FAIL</span></span>|<span data-ttu-id="3cb2e-117">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="3cb2e-117">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="3cb2e-118">Если метод возвращает E_FAIL, общеязыковая среда выполнения (CLR) больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="3cb2e-118">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="3cb2e-119">Последующие вызовы любых API размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="3cb2e-119">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="3cb2e-120">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3cb2e-120">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3cb2e-121">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="3cb2e-121">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3cb2e-122">Комментарии</span><span class="sxs-lookup"><span data-stu-id="3cb2e-122">Remarks</span></span>  

 <span data-ttu-id="3cb2e-123">Указатель, возвращаемый из этого метода, обычно передается в качестве параметра в метод [CreateDomainEx](icorruntimehost-createdomainex-method.md) .</span><span class="sxs-lookup"><span data-stu-id="3cb2e-123">The pointer returned from this method is typically passed as a parameter to the [CreateDomainEx](icorruntimehost-createdomainex-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3cb2e-124">Требования</span><span class="sxs-lookup"><span data-stu-id="3cb2e-124">Requirements</span></span>  

 <span data-ttu-id="3cb2e-125">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3cb2e-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3cb2e-126">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="3cb2e-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3cb2e-127">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3cb2e-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3cb2e-128">**Версия .NET Framework:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="3cb2e-128">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3cb2e-129">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="3cb2e-129">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- <xref:System.AppDomainSetup>
- <xref:System.IAppDomainSetup?displayProperty=nameWithType>
- [<span data-ttu-id="3cb2e-130">Интерфейс ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="3cb2e-130">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
