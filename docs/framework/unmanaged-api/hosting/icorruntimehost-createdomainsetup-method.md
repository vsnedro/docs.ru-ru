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
ms.openlocfilehash: aa1ce70311cd4ef0204c1c31efee8bd7b313c81d
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762335"
---
# <a name="icorruntimehostcreatedomainsetup-method"></a><span data-ttu-id="918bc-102">Метод ICorRuntimeHost::CreateDomainSetup</span><span class="sxs-lookup"><span data-stu-id="918bc-102">ICorRuntimeHost::CreateDomainSetup Method</span></span>
<span data-ttu-id="918bc-103">Возвращает указатель интерфейса типа IAppDomainSetup на <xref:System.AppDomainSetup?displayProperty=nameWithType> экземпляр.</span><span class="sxs-lookup"><span data-stu-id="918bc-103">Gets an interface pointer of type IAppDomainSetup to an <xref:System.AppDomainSetup?displayProperty=nameWithType> instance.</span></span> <span data-ttu-id="918bc-104">`IAppDomainSetup`предоставляет методы для настройки аспектов домена приложения перед его созданием.</span><span class="sxs-lookup"><span data-stu-id="918bc-104">`IAppDomainSetup` provides methods to configure aspects of an application domain before it is created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="918bc-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="918bc-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateDomainSetup (  
    [out] IUnknown** pAppDomainSetup  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="918bc-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="918bc-106">Parameters</span></span>  
 `pAppDomainSetup`  
 <span data-ttu-id="918bc-107">заполняет Указатель интерфейса на <xref:System.AppDomainSetup?displayProperty=nameWithType> экземпляр.</span><span class="sxs-lookup"><span data-stu-id="918bc-107">[out] An interface pointer to an <xref:System.AppDomainSetup?displayProperty=nameWithType> instance.</span></span> <span data-ttu-id="918bc-108">Этот параметр типизирован как `IUnknown` , поэтому вызывающие объекты должны обычно вызывать `QueryInterface` этот указатель для получения указателя интерфейса типа `IAppDomainSetup` .</span><span class="sxs-lookup"><span data-stu-id="918bc-108">This parameter is typed as `IUnknown`, so callers should generally call `QueryInterface` on this pointer to obtain an interface pointer of type `IAppDomainSetup`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="918bc-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="918bc-109">Return Value</span></span>  
  
|<span data-ttu-id="918bc-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="918bc-110">HRESULT</span></span>|<span data-ttu-id="918bc-111">Описание</span><span class="sxs-lookup"><span data-stu-id="918bc-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="918bc-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="918bc-112">S_OK</span></span>|<span data-ttu-id="918bc-113">Операция выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="918bc-113">The operation was successful.</span></span>|  
|<span data-ttu-id="918bc-114">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="918bc-114">S_FALSE</span></span>|<span data-ttu-id="918bc-115">Не удалось завершить операцию.</span><span class="sxs-lookup"><span data-stu-id="918bc-115">The operation failed to complete.</span></span>|  
|<span data-ttu-id="918bc-116">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="918bc-116">E_FAIL</span></span>|<span data-ttu-id="918bc-117">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="918bc-117">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="918bc-118">Если метод возвращает E_FAIL, общеязыковая среда выполнения (CLR) больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="918bc-118">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="918bc-119">Последующие вызовы любых API размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="918bc-119">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="918bc-120">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="918bc-120">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="918bc-121">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="918bc-121">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="918bc-122">Комментарии</span><span class="sxs-lookup"><span data-stu-id="918bc-122">Remarks</span></span>  
 <span data-ttu-id="918bc-123">Указатель, возвращаемый из этого метода, обычно передается в качестве параметра в метод [CreateDomainEx](icorruntimehost-createdomainex-method.md) .</span><span class="sxs-lookup"><span data-stu-id="918bc-123">The pointer returned from this method is typically passed as a parameter to the [CreateDomainEx](icorruntimehost-createdomainex-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="918bc-124">Требования</span><span class="sxs-lookup"><span data-stu-id="918bc-124">Requirements</span></span>  
 <span data-ttu-id="918bc-125">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="918bc-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="918bc-126">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="918bc-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="918bc-127">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="918bc-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="918bc-128">**Версия .NET Framework:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="918bc-128">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="918bc-129">См. также</span><span class="sxs-lookup"><span data-stu-id="918bc-129">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- <xref:System.AppDomainSetup>
- <xref:System.IAppDomainSetup?displayProperty=nameWithType>
- [<span data-ttu-id="918bc-130">Интерфейс ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="918bc-130">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
