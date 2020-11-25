---
title: Метод ICorRuntimeHost::CreateDomainEx
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.CreateDomainEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CreateDomainEx
helpviewer_keywords:
- ICorRuntimeHost::CreateDomainEx method [.NET Framework hosting]
- CreateDomainEx method [.NET Framework hosting]
ms.assetid: 1bdde382-f8ba-4cc8-94b2-d1ac919c585e
topic_type:
- apiref
ms.openlocfilehash: d6d9e06b6ed40bb0e5a65fd64f8bca7abe3afa84
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95715684"
---
# <a name="icorruntimehostcreatedomainex-method"></a><span data-ttu-id="46a5a-102">Метод ICorRuntimeHost::CreateDomainEx</span><span class="sxs-lookup"><span data-stu-id="46a5a-102">ICorRuntimeHost::CreateDomainEx Method</span></span>

<span data-ttu-id="46a5a-103">Создает домен приложения.</span><span class="sxs-lookup"><span data-stu-id="46a5a-103">Creates an application domain.</span></span> <span data-ttu-id="46a5a-104">Вызывающий объект получает указатель интерфейса типа <xref:System._AppDomain> в экземпляр типа <xref:System.AppDomain?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="46a5a-104">The caller receives an interface pointer, of type <xref:System._AppDomain>, to an instance of type <xref:System.AppDomain?displayProperty=nameWithType>.</span></span> <span data-ttu-id="46a5a-105">Этот метод позволяет вызывающему объекту передать экземпляр IAppDomainSetup для настройки дополнительных функций возвращаемого <xref:System._AppDomain> экземпляра.</span><span class="sxs-lookup"><span data-stu-id="46a5a-105">This method allows the caller to pass an IAppDomainSetup instance to configure additional features of the returned <xref:System._AppDomain> instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46a5a-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="46a5a-106">Syntax</span></span>  
  
```cpp  
HRESULT CreateDomainEx (  
    [in] LPCWSTR     pwzFriendlyName,  
    [in] IUnknown*   pSetup,  
    [in] IUnknown*   pIdentityArray,  
    [out] IUnknown** pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="46a5a-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="46a5a-107">Parameters</span></span>  

 `pwzFriendlyName`  
 <span data-ttu-id="46a5a-108">окне Необязательный параметр, используемый для присвоения понятного имени домену.</span><span class="sxs-lookup"><span data-stu-id="46a5a-108">[in] An optional parameter used to give a friendly name to the domain.</span></span> <span data-ttu-id="46a5a-109">Это понятное имя может отображаться в пользовательских интерфейсах, таких как отладчики, для обнаружения домена.</span><span class="sxs-lookup"><span data-stu-id="46a5a-109">This friendly name can be displayed in user interfaces such as debuggers to identify the domain.</span></span>  
  
 `pSetup`  
 <span data-ttu-id="46a5a-110">окне Необязательный указатель интерфейса типа `IAppDomainSetup` , полученный при вызове метода [ICorRuntimeHost:: креатедомаинсетуп](icorruntimehost-createdomainsetup-method.md) .</span><span class="sxs-lookup"><span data-stu-id="46a5a-110">[in] An optional interface pointer of type `IAppDomainSetup`, obtained by a call to the [ICorRuntimeHost::CreateDomainSetup](icorruntimehost-createdomainsetup-method.md) method.</span></span>  
  
 `pIdentityArray`  
 <span data-ttu-id="46a5a-111">окне Необязательный массив указателей на `IIdentity` экземпляры, представляющие свидетельство, сопоставленное через политику безопасности для создания набора разрешений.</span><span class="sxs-lookup"><span data-stu-id="46a5a-111">[in] An optional array of pointers to `IIdentity` instances that represent evidence mapped through security policy to establish a permission set.</span></span> <span data-ttu-id="46a5a-112">`IIdentity`Объект можно получить, вызвав метод [креативиденце](icorruntimehost-createevidence-method.md) .</span><span class="sxs-lookup"><span data-stu-id="46a5a-112">An `IIdentity` object can be obtained by calling the [CreateEvidence](icorruntimehost-createevidence-method.md) method.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="46a5a-113">заполняет Указатель интерфейса типа <xref:System._AppDomain> на экземпляр <xref:System.AppDomain?displayProperty=nameWithType> , который может использоваться для дальнейшего управления доменом.</span><span class="sxs-lookup"><span data-stu-id="46a5a-113">[out] An interface pointer of type <xref:System._AppDomain> to an instance of <xref:System.AppDomain?displayProperty=nameWithType> that can be used to further control the domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="46a5a-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="46a5a-114">Return Value</span></span>  
  
|<span data-ttu-id="46a5a-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="46a5a-115">HRESULT</span></span>|<span data-ttu-id="46a5a-116">Описание:</span><span class="sxs-lookup"><span data-stu-id="46a5a-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="46a5a-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="46a5a-117">S_OK</span></span>|<span data-ttu-id="46a5a-118">Операция выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="46a5a-118">The operation was successful.</span></span>|  
|<span data-ttu-id="46a5a-119">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="46a5a-119">S_FALSE</span></span>|<span data-ttu-id="46a5a-120">Не удалось завершить операцию.</span><span class="sxs-lookup"><span data-stu-id="46a5a-120">The operation failed to complete.</span></span>|  
|<span data-ttu-id="46a5a-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="46a5a-121">E_FAIL</span></span>|<span data-ttu-id="46a5a-122">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="46a5a-122">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="46a5a-123">Если метод возвращает E_FAIL, общеязыковая среда выполнения (CLR) больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="46a5a-123">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="46a5a-124">Последующие вызовы любых API размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="46a5a-124">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="46a5a-125">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="46a5a-125">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="46a5a-126">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="46a5a-126">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="46a5a-127">Комментарии</span><span class="sxs-lookup"><span data-stu-id="46a5a-127">Remarks</span></span>  

 <span data-ttu-id="46a5a-128">`CreateDomainEx` расширяет возможности [CreateDomain](icorruntimehost-createdomain-method.md) , позволяя вызывающей стороне передавать `IAppDomainSetup` экземпляр со значениями свойств для настройки домена приложения.</span><span class="sxs-lookup"><span data-stu-id="46a5a-128">`CreateDomainEx` extends the capabilities of [CreateDomain](icorruntimehost-createdomain-method.md) by allowing the caller to pass in an `IAppDomainSetup` instance with property values for configuring the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46a5a-129">Требования</span><span class="sxs-lookup"><span data-stu-id="46a5a-129">Requirements</span></span>  

 <span data-ttu-id="46a5a-130">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="46a5a-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46a5a-131">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="46a5a-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="46a5a-132">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="46a5a-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="46a5a-133">**Версия .NET Framework:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="46a5a-133">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46a5a-134">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="46a5a-134">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- <xref:System.IAppDomainSetup?displayProperty=nameWithType>
- [<span data-ttu-id="46a5a-135">Метод CreateDomain</span><span class="sxs-lookup"><span data-stu-id="46a5a-135">CreateDomain Method</span></span>](icorruntimehost-createdomain-method.md)
- [<span data-ttu-id="46a5a-136">Интерфейс ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="46a5a-136">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
