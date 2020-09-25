---
title: <add> из <authorizationPolicies>
ms.date: 03/30/2017
ms.assetid: 613a03d8-4384-4556-bce2-8c23286c0bb0
ms.openlocfilehash: 39cb89340907743c727a425bb2f140ac34842e3b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91181678"
---
# <a name="add-of-authorizationpolicies"></a><span data-ttu-id="e43dd-102">\<add> из \<authorizationPolicies></span><span class="sxs-lookup"><span data-stu-id="e43dd-102">\<add> of \<authorizationPolicies></span></span>

<span data-ttu-id="e43dd-103">Задает политику авторизации для преобразования требований.</span><span class="sxs-lookup"><span data-stu-id="e43dd-103">Specifies an authorization policy for claim transformation.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceAuthorization>**](serviceauthorization-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<authorizationPolicies>**](authorizationpolicies.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="e43dd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e43dd-104">Syntax</span></span>  
  
```xml  
<authorizationPolicies>
  <add policyType="String" />
</authorizationPolicies>
```  
  
## <a name="type"></a><span data-ttu-id="e43dd-105">Type</span><span class="sxs-lookup"><span data-stu-id="e43dd-105">Type</span></span>  

 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e43dd-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e43dd-106">Attributes and Elements</span></span>  

 <span data-ttu-id="e43dd-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e43dd-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e43dd-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e43dd-108">Attributes</span></span>  
  
|<span data-ttu-id="e43dd-109">Атрибут</span><span class="sxs-lookup"><span data-stu-id="e43dd-109">Attribute</span></span>|<span data-ttu-id="e43dd-110">Описание</span><span class="sxs-lookup"><span data-stu-id="e43dd-110">Description</span></span>|  
|---------------|-----------------|  
|`policyType`|<span data-ttu-id="e43dd-111">Обязательный строковый атрибут.</span><span class="sxs-lookup"><span data-stu-id="e43dd-111">A required String attribute.</span></span><br /><br /> <span data-ttu-id="e43dd-112">Модель управления доступом Windows Communication Foundation (WCF) поддерживает подготовку набора политик авторизации в качестве типов.</span><span class="sxs-lookup"><span data-stu-id="e43dd-112">The Windows Communication Foundation (WCF) access control model supports provisioning a set of authorization policies as types.</span></span> <span data-ttu-id="e43dd-113">Данный атрибут определяет политику авторизации, которая позволяет преобразовывать один набор входных требований в другой набор требований.</span><span class="sxs-lookup"><span data-stu-id="e43dd-113">This attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="e43dd-114">В зависимости от этого может быть предоставлено управление доступом или отказано в предоставлении управления доступом.</span><span class="sxs-lookup"><span data-stu-id="e43dd-114">Access control can be granted or denied based on that.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e43dd-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e43dd-115">Child Elements</span></span>  

 <span data-ttu-id="e43dd-116">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="e43dd-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e43dd-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e43dd-117">Parent Elements</span></span>  
  
|<span data-ttu-id="e43dd-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="e43dd-118">Element</span></span>|<span data-ttu-id="e43dd-119">Описание</span><span class="sxs-lookup"><span data-stu-id="e43dd-119">Description</span></span>|  
|-------------|-----------------|  
|[\<authorizationPolicies>](authorizationpolicies.md)|<span data-ttu-id="e43dd-120">Задает коллекцию типов политики авторизации.</span><span class="sxs-lookup"><span data-stu-id="e43dd-120">Specifies a collection of authorization policy types.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e43dd-121">Remarks</span><span class="sxs-lookup"><span data-stu-id="e43dd-121">Remarks</span></span>  

 <span data-ttu-id="e43dd-122">Каждая политика авторизации содержит один обязательный атрибут `policyType`, который имеет строковый тип.</span><span class="sxs-lookup"><span data-stu-id="e43dd-122">Each authorization policy contains a single required `policyType` attribute that is a string.</span></span> <span data-ttu-id="e43dd-123">Данный атрибут определяет политику авторизации, которая позволяет преобразовывать один набор входных требований в другой набор требований.</span><span class="sxs-lookup"><span data-stu-id="e43dd-123">The attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="e43dd-124">В зависимости от этого может быть предоставлено управление доступом или отказано в предоставлении управления доступом.</span><span class="sxs-lookup"><span data-stu-id="e43dd-124">Access control can be granted or denied based on that.</span></span> <span data-ttu-id="e43dd-125">Дополнительные сведения о принципах работы политики авторизации см. в разделе <xref:System.IdentityModel.Policy.IAuthorizationPolicy> и [Политика авторизации](../../../wcf/samples/authorization-policy.md).</span><span class="sxs-lookup"><span data-stu-id="e43dd-125">For more information on how an authorization policy works, see <xref:System.IdentityModel.Policy.IAuthorizationPolicy> and [Authorization Policy](../../../wcf/samples/authorization-policy.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e43dd-126">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e43dd-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ExternalAuthorizationPolicies%2A>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
- <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>
- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement.AuthorizationPolicies%2A>
- <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElementCollection>
- <xref:System.IdentityModel.Policy.IAuthorizationPolicy>
- [<span data-ttu-id="e43dd-127">Авторизация доступа к операциям службы</span><span class="sxs-lookup"><span data-stu-id="e43dd-127">Authorizing Access to Service Operations</span></span>](../../../wcf/samples/authorizing-access-to-service-operations.md)
- [<span data-ttu-id="e43dd-128">Практическое руководство. Создание пользовательского диспетчера авторизации для службы</span><span class="sxs-lookup"><span data-stu-id="e43dd-128">How to: Create a Custom Authorization Manager for a Service</span></span>](../../../wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)
- [\<add>](add-of-authorizationpolicies.md)
- [<span data-ttu-id="e43dd-129">Политика авторизации</span><span class="sxs-lookup"><span data-stu-id="e43dd-129">Authorization Policy</span></span>](../../../wcf/samples/authorization-policy.md)
