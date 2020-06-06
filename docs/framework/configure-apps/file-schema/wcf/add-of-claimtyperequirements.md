---
title: <add> из <claimTypeRequirements>
ms.date: 03/30/2017
ms.assetid: c68e83c9-39e8-4264-b1ce-b6a9eb5b98aa
ms.openlocfilehash: 6ba935f7f6dae0e4d9e6581f53a50c684efcbed3
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153091"
---
# <a name="add-of-claimtyperequirements"></a><span data-ttu-id="53ddf-102">\<add> из \<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="53ddf-102">\<add> of \<claimTypeRequirements></span></span>
<span data-ttu-id="53ddf-103">Задает типы обязательных и необязательных утверждений, которые могут появляться в федеративных учетных данных.</span><span class="sxs-lookup"><span data-stu-id="53ddf-103">Specifies the types of required and optional claims expected to appear in the federated credential.</span></span> <span data-ttu-id="53ddf-104">Например, службы предъявляют требования к входящим учетным данным, которые должны обладать определенным набором типов утверждений.</span><span class="sxs-lookup"><span data-stu-id="53ddf-104">For example, services state the requirements on incoming credentials, which must possess a certain set of claim types.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedTokenParameters>**](issuedtokenparameters.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<claimTypeRequirements>**](claimtyperequirements-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="53ddf-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="53ddf-105">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <add claimType="URI"
       isOptional="Boolean" />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="53ddf-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="53ddf-106">Attributes and Elements</span></span>  
 <span data-ttu-id="53ddf-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="53ddf-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="53ddf-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="53ddf-108">Attributes</span></span>  
  
|<span data-ttu-id="53ddf-109">Атрибут</span><span class="sxs-lookup"><span data-stu-id="53ddf-109">Attribute</span></span>|<span data-ttu-id="53ddf-110">Описание:</span><span class="sxs-lookup"><span data-stu-id="53ddf-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="53ddf-111">claimType</span><span class="sxs-lookup"><span data-stu-id="53ddf-111">claimType</span></span>|<span data-ttu-id="53ddf-112">Универсальный код ресурса (URI), определяющий тип утверждения.</span><span class="sxs-lookup"><span data-stu-id="53ddf-112">A URI that defines the type of a claim.</span></span> <span data-ttu-id="53ddf-113">Например, для приобретения товара с веб-узла пользователь должен представить действительную кредитную карту с достаточным кредитным лимитом.</span><span class="sxs-lookup"><span data-stu-id="53ddf-113">For example, to purchase a product from a Web site, the user must present a valid credit card with sufficient credit limit.</span></span> <span data-ttu-id="53ddf-114">Типом утверждения будет универсальный код ресурса (URI) кредитной карты.</span><span class="sxs-lookup"><span data-stu-id="53ddf-114">The claim type would be the credit card URI.</span></span>|  
|<span data-ttu-id="53ddf-115">isOptional</span><span class="sxs-lookup"><span data-stu-id="53ddf-115">isOptional</span></span>|<span data-ttu-id="53ddf-116">Логическое значение, указывающее, является ли утверждение необязательным.</span><span class="sxs-lookup"><span data-stu-id="53ddf-116">A Boolean value that specifies if this is for an optional claim.</span></span> <span data-ttu-id="53ddf-117">Если утверждение является обязательным, установите для этого атрибута значение `false`.</span><span class="sxs-lookup"><span data-stu-id="53ddf-117">Set this attribute to `false` if this is a required claim.</span></span><br /><br /> <span data-ttu-id="53ddf-118">Этот атрибут можно использовать, если служба запрашивает определенные данные, но они не являются необходимыми.</span><span class="sxs-lookup"><span data-stu-id="53ddf-118">You can use this attribute when the service asks for some information but does not require it.</span></span> <span data-ttu-id="53ddf-119">Например, если требуется, чтобы пользователь вводил имя, фамилию и адрес, но решите, что номер телефона является необязательным.</span><span class="sxs-lookup"><span data-stu-id="53ddf-119">For example, if you require the user to enter their first name, last name, and address, but decide that phone number is optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="53ddf-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="53ddf-120">Child Elements</span></span>  
 <span data-ttu-id="53ddf-121">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="53ddf-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="53ddf-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="53ddf-122">Parent Elements</span></span>  
  
|<span data-ttu-id="53ddf-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="53ddf-123">Element</span></span>|<span data-ttu-id="53ddf-124">Описание</span><span class="sxs-lookup"><span data-stu-id="53ddf-124">Description</span></span>|  
|-------------|-----------------|  
|[\<claimTypeRequirements>](claimtyperequirements-element.md)|<span data-ttu-id="53ddf-125">Задает коллекцию обязательных типов утверждений.</span><span class="sxs-lookup"><span data-stu-id="53ddf-125">Specifies a collection of required claim types.</span></span><br /><br /> <span data-ttu-id="53ddf-126">В федеративном сценарии службы предъявляют требования к входящим учетным данным.</span><span class="sxs-lookup"><span data-stu-id="53ddf-126">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="53ddf-127">Например, входящие учетные данные должны обладать определенным набором типов утверждений.</span><span class="sxs-lookup"><span data-stu-id="53ddf-127">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="53ddf-128">Каждый элемент в этой коллекции задает типы обязательных и необязательных утверждений, которые могут появляться в федеративных учетных данных.</span><span class="sxs-lookup"><span data-stu-id="53ddf-128">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="53ddf-129">Примечания</span><span class="sxs-lookup"><span data-stu-id="53ddf-129">Remarks</span></span>  
 <span data-ttu-id="53ddf-130">В федеративном сценарии службы предъявляют требования к входящим учетным данным.</span><span class="sxs-lookup"><span data-stu-id="53ddf-130">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="53ddf-131">Например, входящие учетные данные должны обладать определенным набором типов утверждений.</span><span class="sxs-lookup"><span data-stu-id="53ddf-131">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="53ddf-132">Это требование представлено в политике безопасности.</span><span class="sxs-lookup"><span data-stu-id="53ddf-132">This requirement is manifested in a security policy.</span></span> <span data-ttu-id="53ddf-133">Когда клиент запрашивает учетные данные в федеративной службе (например, CardSpace), требования помещаются в запрос маркера (RequestSecurityToken), что позволяет федеративной службе выдать учетные данные, полностью отвечающие требованиям.</span><span class="sxs-lookup"><span data-stu-id="53ddf-133">When a client requests credentials from a federated service (for example, CardSpace), it puts the requirements into a token request (RequestSecurityToken) so that the federated service can issue the credentials that satisfy the requirements accordingly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="53ddf-134">Пример</span><span class="sxs-lookup"><span data-stu-id="53ddf-134">Example</span></span>  
 <span data-ttu-id="53ddf-135">Следующая конфигурация добавляет два требования типа утверждения к привязке безопасности.</span><span class="sxs-lookup"><span data-stu-id="53ddf-135">The following configuration adds two claim type requirements to a security binding.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="53ddf-136">См. также</span><span class="sxs-lookup"><span data-stu-id="53ddf-136">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [\<claimTypeRequirements>](claimtyperequirements-element.md)
- [<span data-ttu-id="53ddf-137">Привязки</span><span class="sxs-lookup"><span data-stu-id="53ddf-137">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="53ddf-138">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="53ddf-138">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="53ddf-139">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="53ddf-139">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
- [<span data-ttu-id="53ddf-140">Практическое руководство. Создание пользовательской привязки с использованием элемента SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="53ddf-140">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="53ddf-141">Безопасность пользовательской привязки</span><span class="sxs-lookup"><span data-stu-id="53ddf-141">Custom Binding Security</span></span>](../../../wcf/samples/custom-binding-security.md)
