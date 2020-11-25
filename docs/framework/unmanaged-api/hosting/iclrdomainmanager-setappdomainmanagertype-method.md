---
title: Метод ICLRDomainManager::SetAppDomainManagerType
ms.date: 03/30/2017
api_name:
- ICLRDomainManager.SetAppDomainManagerType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDomainManager::SetAppDomainManagerType
helpviewer_keywords:
- SetAppDomainManagerType method, ICLRDomainManager interface [.NET Framework hosting]
- ICLRDomainManager::SetAppDomainManagerType method [.NET Framework hosting]
ms.assetid: ee91abb0-cb74-41dd-927b-e117fb8ffdf4
ms.openlocfilehash: 7c6b328793e6437682ad8d642e611be30e7b0fe6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702152"
---
# <a name="iclrdomainmanagersetappdomainmanagertype-method"></a><span data-ttu-id="9033d-102">Метод ICLRDomainManager::SetAppDomainManagerType</span><span class="sxs-lookup"><span data-stu-id="9033d-102">ICLRDomainManager::SetAppDomainManagerType Method</span></span>

<span data-ttu-id="9033d-103">Задает тип, производный от <xref:System.AppDomainManager?displayProperty=nameWithType> класса диспетчера домена приложения, который будет использоваться для инициализации домена приложения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9033d-103">Specifies the type, derived from the <xref:System.AppDomainManager?displayProperty=nameWithType> class, of the application domain manager that will be used to initialize the default application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9033d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9033d-104">Syntax</span></span>  
  
```cpp  
HRESULT SetAppDomainManagerType(  
    [in] LPCWSTR wszAppDomainManagerAssembly,  
    [in] LPCWSTR wszAppDomainManagerType,  
    [in] EInitializeNewDomainFlags dwInitializeDomainFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9033d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9033d-105">Parameters</span></span>  

 `wszAppDomainManagerAssembly`  
 <span data-ttu-id="9033d-106">окне Отображаемое имя сборки, содержащей тип диспетчера домена приложения; Например: "Адмгрексампле, Version = 1.0.0.0, культура = Neutral, PublicKeyToken = 6856bccf150f00b3".</span><span class="sxs-lookup"><span data-stu-id="9033d-106">[in] The display name of the assembly that contains the application domain manager type; for example: "AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3".</span></span>  
  
 `wszAppDomainManagerType`  
 <span data-ttu-id="9033d-107">окне Имя типа диспетчера домена приложения, включая пространство имен.</span><span class="sxs-lookup"><span data-stu-id="9033d-107">[in] The type name of the application domain manager, including the namespace.</span></span>  
  
 `dwInitializeDomainFlags`  
 <span data-ttu-id="9033d-108">окне Сочетание значений перечисления [EInitializeNewDomainFlags](einitializenewdomainflags-enumeration.md) , которые предоставляют сведения о диспетчере доменов приложений.</span><span class="sxs-lookup"><span data-stu-id="9033d-108">[in] A combination of [EInitializeNewDomainFlags](einitializenewdomainflags-enumeration.md) enumeration values that provide information about the application domain manager.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9033d-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="9033d-109">Return Value</span></span>  

 <span data-ttu-id="9033d-110">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="9033d-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="9033d-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9033d-111">HRESULT</span></span>|<span data-ttu-id="9033d-112">Описание:</span><span class="sxs-lookup"><span data-stu-id="9033d-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9033d-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="9033d-113">S_OK</span></span>|<span data-ttu-id="9033d-114">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="9033d-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="9033d-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9033d-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9033d-116">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="9033d-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9033d-117">Комментарии</span><span class="sxs-lookup"><span data-stu-id="9033d-117">Remarks</span></span>  

 <span data-ttu-id="9033d-118">В настоящее время единственным определенным значением для `dwInitializeDomainFlags` является `eInitializeNewDomainFlags_NoSecurityChanges` , которое указывает среде CLR, что диспетчер домена приложения не изменяет параметры безопасности во время выполнения <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> метода.</span><span class="sxs-lookup"><span data-stu-id="9033d-118">Currently, the only defined value for `dwInitializeDomainFlags` is `eInitializeNewDomainFlags_NoSecurityChanges`, which tells the common language runtime (CLR) that the application domain manager will not modify security settings during the execution of the <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="9033d-119">Это позволяет среде CLR оптимизировать загрузку сборок с условным <xref:System.Security.AllowPartiallyTrustedCallersAttribute> атрибутом (APTCA).</span><span class="sxs-lookup"><span data-stu-id="9033d-119">This allows the CLR to optimize the loading of assemblies that have the conditional <xref:System.Security.AllowPartiallyTrustedCallersAttribute> (APTCA) attribute.</span></span> <span data-ttu-id="9033d-120">Это может привести к значительному улучшению времени запуска, если транзитивное замыкание этого набора сборок велико.</span><span class="sxs-lookup"><span data-stu-id="9033d-120">This can result in a significant improvement in startup time if the transitive closure of this set of assemblies is large.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="9033d-121">Если узел указан `eInitializeNewDomainFlags_NoSecurityChanges` для диспетчера доменов приложений, создается исключение, <xref:System.InvalidOperationException> Если выполняется любая попытка изменить безопасность домена приложения.</span><span class="sxs-lookup"><span data-stu-id="9033d-121">If the host specifies `eInitializeNewDomainFlags_NoSecurityChanges` for the application domain manager, an <xref:System.InvalidOperationException> is thrown if any attempt is made to modify the security of the application domain.</span></span>  
  
 <span data-ttu-id="9033d-122">Вызов метода [ICLRControl:: SetAppDomainManagerType](iclrcontrol-setappdomainmanagertype-method.md)эквивалентен вызову `ICLRDomainManager::SetAppDomainManagerType` с `eInitializeNewDomainFlags_None` .</span><span class="sxs-lookup"><span data-stu-id="9033d-122">Calling the [ICLRControl::SetAppDomainManagerType](iclrcontrol-setappdomainmanagertype-method.md)method is equivalent to calling `ICLRDomainManager::SetAppDomainManagerType` with `eInitializeNewDomainFlags_None`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9033d-123">Требования</span><span class="sxs-lookup"><span data-stu-id="9033d-123">Requirements</span></span>  

 <span data-ttu-id="9033d-124">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9033d-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9033d-125">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="9033d-125">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="9033d-126">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9033d-126">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9033d-127">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9033d-127">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9033d-128">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="9033d-128">See also</span></span>

- [<span data-ttu-id="9033d-129">Размещение</span><span class="sxs-lookup"><span data-stu-id="9033d-129">Hosting</span></span>](index.md)
- [<span data-ttu-id="9033d-130">Интерфейс ICLRDomainManager</span><span class="sxs-lookup"><span data-stu-id="9033d-130">ICLRDomainManager Interface</span></span>](iclrdomainmanager-interface.md)
- [<span data-ttu-id="9033d-131">Перечисление EInitializeNewDomainFlags</span><span class="sxs-lookup"><span data-stu-id="9033d-131">EInitializeNewDomainFlags Enumeration</span></span>](einitializenewdomainflags-enumeration.md)
