---
title: Метод ICLRDomainManager::SetPropertiesForDefaultAppDomain
ms.date: 03/30/2017
api_name:
- ICLRDomainManager.SetPropertiesForDefaultAppDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDomainManager::SetPropertiesForDefaultAppDomain
helpviewer_keywords:
- ICLRDomainManager::SetPropertiesForDefaultAppDomain method [.NET Framework hosting]
- SetPropertiesForDefaultAppDomain method [.NET Framework hosting]
ms.assetid: 43e61c4b-c435-45ec-9ef6-c68403aa4200
ms.openlocfilehash: b5577d0444caf14fb47d9d7e2de60a8399378db7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702138"
---
# <a name="iclrdomainmanagersetpropertiesfordefaultappdomain-method"></a><span data-ttu-id="fd2b9-102">Метод ICLRDomainManager::SetPropertiesForDefaultAppDomain</span><span class="sxs-lookup"><span data-stu-id="fd2b9-102">ICLRDomainManager::SetPropertiesForDefaultAppDomain Method</span></span>

<span data-ttu-id="fd2b9-103">Задает свойства, которые будут использоваться для инициализации домена приложения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="fd2b9-103">Sets properties that will be used to initialize the default application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd2b9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fd2b9-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPropertiesForDefaultAppDomain(  
    [in] DWORD nProperties,  
    [in] LPCWSTR *pwszPropertyNames,  
    [in] LPCWSTR *pwszPropertyValues  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fd2b9-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="fd2b9-105">Parameters</span></span>  

 `nProperties`  
 <span data-ttu-id="fd2b9-106">окне Число записей в `pwszPropertyNames` и `pwszPropertyValues` .</span><span class="sxs-lookup"><span data-stu-id="fd2b9-106">[in] The number of entries in `pwszPropertyNames` and `pwszPropertyValues`.</span></span>  
  
 `pwszPropertyNames`  
 <span data-ttu-id="fd2b9-107">окне Массив имен свойств или значение null, если свойства отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="fd2b9-107">[in] An array of property names, or null if there are no properties.</span></span> <span data-ttu-id="fd2b9-108">В настоящее время единственным именем свойства, распознаваемым этим методом, является "PARTIAL_TRUST_VISIBLE_ASSEMBLIES".</span><span class="sxs-lookup"><span data-stu-id="fd2b9-108">Currently, the only property name that is recognized by this method is "PARTIAL_TRUST_VISIBLE_ASSEMBLIES".</span></span>  
  
 `pwszPropertyValues`  
 <span data-ttu-id="fd2b9-109">окне Массив значений свойств или значение null, если свойства отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="fd2b9-109">[in] An array of property values, or null if there are no properties.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fd2b9-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="fd2b9-110">Return Value</span></span>  

 <span data-ttu-id="fd2b9-111">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="fd2b9-111">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="fd2b9-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fd2b9-112">HRESULT</span></span>|<span data-ttu-id="fd2b9-113">Описание:</span><span class="sxs-lookup"><span data-stu-id="fd2b9-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fd2b9-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="fd2b9-114">S_OK</span></span>|<span data-ttu-id="fd2b9-115">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="fd2b9-115">The method completed successfully.</span></span>|  
|<span data-ttu-id="fd2b9-116">HRESULT_FROM_WIN32 (ERROR_UNKNOWN_PROPERTY)</span><span class="sxs-lookup"><span data-stu-id="fd2b9-116">HRESULT_FROM_WIN32(ERROR_UNKNOWN_PROPERTY)</span></span>|<span data-ttu-id="fd2b9-117">`pwszPropertyNames` содержит имя свойства, которое не распознается этим методом.</span><span class="sxs-lookup"><span data-stu-id="fd2b9-117">`pwszPropertyNames` includes a property name that is not recognized by this method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fd2b9-118">Комментарии</span><span class="sxs-lookup"><span data-stu-id="fd2b9-118">Remarks</span></span>  

 <span data-ttu-id="fd2b9-119">Значение свойства для "PARTIAL_TRUST_VISIBLE_ASSEMBLIES" — это список сборок, имеющих условный <xref:System.Security.AllowPartiallyTrustedCallersAttribute> атрибут (APTCA) с <xref:System.Security.PartialTrustVisibilityLevel.NotVisibleByDefault?displayProperty=nameWithType> флагом, который должен быть видимым для частично доверенных вызывающих объектов в домене приложения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="fd2b9-119">The property value for "PARTIAL_TRUST_VISIBLE_ASSEMBLIES" is a list of assemblies that have the conditional <xref:System.Security.AllowPartiallyTrustedCallersAttribute> (APTCA) attribute with the <xref:System.Security.PartialTrustVisibilityLevel.NotVisibleByDefault?displayProperty=nameWithType> flag, which are to be made visible to partially trusted callers in the default application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd2b9-120">Требования</span><span class="sxs-lookup"><span data-stu-id="fd2b9-120">Requirements</span></span>  

 <span data-ttu-id="fd2b9-121">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fd2b9-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd2b9-122">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="fd2b9-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="fd2b9-123">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fd2b9-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fd2b9-124">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd2b9-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd2b9-125">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="fd2b9-125">See also</span></span>

- [<span data-ttu-id="fd2b9-126">Размещение</span><span class="sxs-lookup"><span data-stu-id="fd2b9-126">Hosting</span></span>](index.md)
- [<span data-ttu-id="fd2b9-127">Интерфейс ICLRDomainManager</span><span class="sxs-lookup"><span data-stu-id="fd2b9-127">ICLRDomainManager Interface</span></span>](iclrdomainmanager-interface.md)
