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
ms.openlocfilehash: 4e5856fbcda83c1dd30559c6f59f63495faea78d
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762348"
---
# <a name="icorruntimehostcreatedomainex-method"></a><span data-ttu-id="7949e-102">Метод ICorRuntimeHost::CreateDomainEx</span><span class="sxs-lookup"><span data-stu-id="7949e-102">ICorRuntimeHost::CreateDomainEx Method</span></span>
<span data-ttu-id="7949e-103">Создает домен приложения.</span><span class="sxs-lookup"><span data-stu-id="7949e-103">Creates an application domain.</span></span> <span data-ttu-id="7949e-104">Вызывающий объект получает указатель интерфейса типа <xref:System._AppDomain> в экземпляр типа <xref:System.AppDomain?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="7949e-104">The caller receives an interface pointer, of type <xref:System._AppDomain>, to an instance of type <xref:System.AppDomain?displayProperty=nameWithType>.</span></span> <span data-ttu-id="7949e-105">Этот метод позволяет вызывающему объекту передать экземпляр IAppDomainSetup для настройки дополнительных функций возвращаемого <xref:System._AppDomain> экземпляра.</span><span class="sxs-lookup"><span data-stu-id="7949e-105">This method allows the caller to pass an IAppDomainSetup instance to configure additional features of the returned <xref:System._AppDomain> instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7949e-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7949e-106">Syntax</span></span>  
  
```cpp  
HRESULT CreateDomainEx (  
    [in] LPCWSTR     pwzFriendlyName,  
    [in] IUnknown*   pSetup,  
    [in] IUnknown*   pIdentityArray,  
    [out] IUnknown** pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7949e-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="7949e-107">Parameters</span></span>  
 `pwzFriendlyName`  
 <span data-ttu-id="7949e-108">окне Необязательный параметр, используемый для присвоения понятного имени домену.</span><span class="sxs-lookup"><span data-stu-id="7949e-108">[in] An optional parameter used to give a friendly name to the domain.</span></span> <span data-ttu-id="7949e-109">Это понятное имя может отображаться в пользовательских интерфейсах, таких как отладчики, для обнаружения домена.</span><span class="sxs-lookup"><span data-stu-id="7949e-109">This friendly name can be displayed in user interfaces such as debuggers to identify the domain.</span></span>  
  
 `pSetup`  
 <span data-ttu-id="7949e-110">окне Необязательный указатель интерфейса типа `IAppDomainSetup` , полученный при вызове метода [ICorRuntimeHost:: креатедомаинсетуп](icorruntimehost-createdomainsetup-method.md) .</span><span class="sxs-lookup"><span data-stu-id="7949e-110">[in] An optional interface pointer of type `IAppDomainSetup`, obtained by a call to the [ICorRuntimeHost::CreateDomainSetup](icorruntimehost-createdomainsetup-method.md) method.</span></span>  
  
 `pIdentityArray`  
 <span data-ttu-id="7949e-111">окне Необязательный массив указателей на `IIdentity` экземпляры, представляющие свидетельство, сопоставленное через политику безопасности для создания набора разрешений.</span><span class="sxs-lookup"><span data-stu-id="7949e-111">[in] An optional array of pointers to `IIdentity` instances that represent evidence mapped through security policy to establish a permission set.</span></span> <span data-ttu-id="7949e-112">`IIdentity`Объект можно получить, вызвав метод [креативиденце](icorruntimehost-createevidence-method.md) .</span><span class="sxs-lookup"><span data-stu-id="7949e-112">An `IIdentity` object can be obtained by calling the [CreateEvidence](icorruntimehost-createevidence-method.md) method.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="7949e-113">заполняет Указатель интерфейса типа <xref:System._AppDomain> на экземпляр <xref:System.AppDomain?displayProperty=nameWithType> , который может использоваться для дальнейшего управления доменом.</span><span class="sxs-lookup"><span data-stu-id="7949e-113">[out] An interface pointer of type <xref:System._AppDomain> to an instance of <xref:System.AppDomain?displayProperty=nameWithType> that can be used to further control the domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7949e-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="7949e-114">Return Value</span></span>  
  
|<span data-ttu-id="7949e-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7949e-115">HRESULT</span></span>|<span data-ttu-id="7949e-116">Описание</span><span class="sxs-lookup"><span data-stu-id="7949e-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7949e-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="7949e-117">S_OK</span></span>|<span data-ttu-id="7949e-118">Операция выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="7949e-118">The operation was successful.</span></span>|  
|<span data-ttu-id="7949e-119">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="7949e-119">S_FALSE</span></span>|<span data-ttu-id="7949e-120">Не удалось завершить операцию.</span><span class="sxs-lookup"><span data-stu-id="7949e-120">The operation failed to complete.</span></span>|  
|<span data-ttu-id="7949e-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7949e-121">E_FAIL</span></span>|<span data-ttu-id="7949e-122">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="7949e-122">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="7949e-123">Если метод возвращает E_FAIL, общеязыковая среда выполнения (CLR) больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="7949e-123">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="7949e-124">Последующие вызовы любых API размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="7949e-124">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="7949e-125">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7949e-125">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7949e-126">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="7949e-126">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7949e-127">Комментарии</span><span class="sxs-lookup"><span data-stu-id="7949e-127">Remarks</span></span>  
 <span data-ttu-id="7949e-128">`CreateDomainEx`расширяет возможности [CreateDomain](icorruntimehost-createdomain-method.md) , позволяя вызывающей стороне передавать `IAppDomainSetup` экземпляр со значениями свойств для настройки домена приложения.</span><span class="sxs-lookup"><span data-stu-id="7949e-128">`CreateDomainEx` extends the capabilities of [CreateDomain](icorruntimehost-createdomain-method.md) by allowing the caller to pass in an `IAppDomainSetup` instance with property values for configuring the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7949e-129">Требования</span><span class="sxs-lookup"><span data-stu-id="7949e-129">Requirements</span></span>  
 <span data-ttu-id="7949e-130">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7949e-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7949e-131">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="7949e-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7949e-132">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="7949e-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7949e-133">**Версия .NET Framework:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="7949e-133">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7949e-134">См. также</span><span class="sxs-lookup"><span data-stu-id="7949e-134">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- <xref:System.IAppDomainSetup?displayProperty=nameWithType>
- [<span data-ttu-id="7949e-135">Метод CreateDomain</span><span class="sxs-lookup"><span data-stu-id="7949e-135">CreateDomain Method</span></span>](icorruntimehost-createdomain-method.md)
- [<span data-ttu-id="7949e-136">Интерфейс ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="7949e-136">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
