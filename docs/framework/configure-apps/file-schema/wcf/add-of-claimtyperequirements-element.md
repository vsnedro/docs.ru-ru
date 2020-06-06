---
title: <add> элемента <claimTypeRequirements>
ms.date: 03/30/2017
ms.assetid: 3234cd45-1478-468e-8b19-5c50815c4786
ms.openlocfilehash: f6948052c62684faa734b592f5bdfc2e7827a07a
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153104"
---
# <a name="add-of-claimtyperequirements-element"></a><span data-ttu-id="14f3e-102">\<add> элемента \<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="14f3e-102">\<add> of \<claimTypeRequirements> element</span></span>
<span data-ttu-id="14f3e-103">Задает типы обязательных и необязательных утверждений, которые могут появляться в федеративных учетных данных.</span><span class="sxs-lookup"><span data-stu-id="14f3e-103">Specifies the types of required and optional claims expected to appear in the federated credential.</span></span> <span data-ttu-id="14f3e-104">Например, службы предъявляют требования к входящим учетным данным, которые должны обладать определенным набором типов утверждений.</span><span class="sxs-lookup"><span data-stu-id="14f3e-104">For example, services state the requirements on incoming credentials, which must possess a certain set of claim types.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<claimTypeRequirements>**](claimtyperequirements-for-message.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**
  
## <a name="syntax"></a><span data-ttu-id="14f3e-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="14f3e-105">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <add claimType="URI"
       isOptional="Boolean" />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="14f3e-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="14f3e-106">Attributes and Elements</span></span>  
 <span data-ttu-id="14f3e-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="14f3e-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="14f3e-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="14f3e-108">Attributes</span></span>  
  
|<span data-ttu-id="14f3e-109">Атрибут</span><span class="sxs-lookup"><span data-stu-id="14f3e-109">Attribute</span></span>|<span data-ttu-id="14f3e-110">Описание:</span><span class="sxs-lookup"><span data-stu-id="14f3e-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="14f3e-111">claimType</span><span class="sxs-lookup"><span data-stu-id="14f3e-111">claimType</span></span>|<span data-ttu-id="14f3e-112">Универсальный код ресурса (URI), определяющий тип утверждения.</span><span class="sxs-lookup"><span data-stu-id="14f3e-112">A URI that defines the type of a claim.</span></span> <span data-ttu-id="14f3e-113">Например, для приобретения товара с веб-узла пользователь должен представить действительную кредитную карту с достаточным кредитным лимитом.</span><span class="sxs-lookup"><span data-stu-id="14f3e-113">For example, to purchase a product from a Web site, the user must present a valid credit card with sufficient credit limit.</span></span> <span data-ttu-id="14f3e-114">Типом утверждения будет универсальный код ресурса (URI) кредитной карты.</span><span class="sxs-lookup"><span data-stu-id="14f3e-114">The claim type would be the credit card URI.</span></span>|  
|<span data-ttu-id="14f3e-115">isOptional</span><span class="sxs-lookup"><span data-stu-id="14f3e-115">isOptional</span></span>|<span data-ttu-id="14f3e-116">Логическое значение, указывающее, является ли утверждение необязательным.</span><span class="sxs-lookup"><span data-stu-id="14f3e-116">A Boolean value that specifies if this is for an optional claim.</span></span> <span data-ttu-id="14f3e-117">Если утверждение является обязательным, установите для этого атрибута значение `false`.</span><span class="sxs-lookup"><span data-stu-id="14f3e-117">Set this attribute to `false` if this is a required claim.</span></span><br /><br /> <span data-ttu-id="14f3e-118">Этот атрибут можно использовать, если служба запрашивает определенные данные, но они не являются необходимыми.</span><span class="sxs-lookup"><span data-stu-id="14f3e-118">You can use this attribute when the service asks for some information but does not require it.</span></span> <span data-ttu-id="14f3e-119">Например, если требуется, чтобы пользователь вводил имя, фамилию и адрес, но решите, что номер телефона является необязательным.</span><span class="sxs-lookup"><span data-stu-id="14f3e-119">For example, if you require the user to enter their first name, last name, and address, but decide that phone number is optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="14f3e-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="14f3e-120">Child Elements</span></span>  
 <span data-ttu-id="14f3e-121">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="14f3e-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="14f3e-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="14f3e-122">Parent Elements</span></span>  
  
|<span data-ttu-id="14f3e-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="14f3e-123">Element</span></span>|<span data-ttu-id="14f3e-124">Описание</span><span class="sxs-lookup"><span data-stu-id="14f3e-124">Description</span></span>|  
|-------------|-----------------|  
|[\<claimTypeRequirements>](claimtyperequirements-for-message.md)|<span data-ttu-id="14f3e-125">Задает коллекцию обязательных типов утверждений.</span><span class="sxs-lookup"><span data-stu-id="14f3e-125">Specifies a collection of required claim types.</span></span> <span data-ttu-id="14f3e-126">Каждый элемент имеет тип <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="14f3e-126">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span><br /><br /> <span data-ttu-id="14f3e-127">В федеративном сценарии службы предъявляют требования к входящим учетным данным.</span><span class="sxs-lookup"><span data-stu-id="14f3e-127">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="14f3e-128">Например, входящие учетные данные должны обладать определенным набором типов утверждений.</span><span class="sxs-lookup"><span data-stu-id="14f3e-128">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="14f3e-129">Каждый элемент в этой коллекции задает типы обязательных и необязательных утверждений, которые могут появляться в федеративных учетных данных.</span><span class="sxs-lookup"><span data-stu-id="14f3e-129">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="14f3e-130">Примечания</span><span class="sxs-lookup"><span data-stu-id="14f3e-130">Remarks</span></span>  
 <span data-ttu-id="14f3e-131">В федеративном сценарии службы предъявляют требования к входящим учетным данным.</span><span class="sxs-lookup"><span data-stu-id="14f3e-131">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="14f3e-132">Например, входящие учетные данные должны обладать определенным набором типов утверждений.</span><span class="sxs-lookup"><span data-stu-id="14f3e-132">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="14f3e-133">Это требование представлено в политике безопасности.</span><span class="sxs-lookup"><span data-stu-id="14f3e-133">This requirement is manifested in a security policy.</span></span> <span data-ttu-id="14f3e-134">Когда клиент запрашивает учетные данные в федеративной службе (например, CardSpace), требования помещаются в запрос маркера (RequestSecurityToken), что позволяет федеративной службе выдать учетные данные, полностью отвечающие требованиям.</span><span class="sxs-lookup"><span data-stu-id="14f3e-134">When a client requests credentials from a federated service (for example, CardSpace), it puts the requirements into a token request (RequestSecurityToken) so that the federated service can issue the credentials that satisfy the requirements accordingly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="14f3e-135">Пример</span><span class="sxs-lookup"><span data-stu-id="14f3e-135">Example</span></span>  
 <span data-ttu-id="14f3e-136">Следующая конфигурация добавляет два требования типа утверждения к привязке безопасности.</span><span class="sxs-lookup"><span data-stu-id="14f3e-136">The following configuration adds two claim type requirements to a security binding.</span></span>  
  
```xml  
<bindings>
  <wsFederationHttpBinding>
    <binding name="myFederatedBinding">
      <security mode="Message">
        <message issuedTokenType="urn:oasis:names:tc:SAML:1.0:assertion">
          <claimTypeRequirements>
            <add claimType="http://schemas.microsoft.com/ws/2005/05/identity/claims/EmailAddress" />
            <add claimType="http://schemas.microsoft.com/ws/2005/05/identity/claims/UserName"
                 optional="true" />
          </claimTypeRequirements>
        </message>
      </security>
    </binding>
  </wsFederationHttpBinding>
</bindings>
```  
  
## <a name="see-also"></a><span data-ttu-id="14f3e-137">См. также</span><span class="sxs-lookup"><span data-stu-id="14f3e-137">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
