---
title: <issuedTokenParameters>
ms.date: 03/30/2017
ms.assetid: 120b3f37-7331-4816-b712-d6aab39655a4
ms.openlocfilehash: 8432463ff62e4b5e54a491b574cc6a5285efe220
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70397956"
---
# \<issuedTokenParameters>
<span data-ttu-id="2ec3b-101">Задает параметры маркера безопасности, выданного в федеративном сценарии безопасности.</span><span class="sxs-lookup"><span data-stu-id="2ec3b-101">Specifies the parameters for a security token issued in a Federated security scenario.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuedTokenParameters>**  
  
## <a name="syntax"></a><span data-ttu-id="2ec3b-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2ec3b-102">Syntax</span></span>  
  
```xml  
<issuedTokenParameters defaultMessageSecurityVersion="System.ServiceModel.MessageSecurityVersion"
                       inclusionMode="AlwaysToInitiator/AlwaysToRecipient/Never/Once"
                       keySize="Integer"
                       keyType="AsymmetricKey/BearerKey/SymmetricKey"
                       tokenType="String">
  <additionalRequestParameters />
  <claimTypeRequirements>
    <add claimType="URI"
         isOptional="Boolean" />
  </claimTypeRequirements>
  <issuer address="String"
          binding="" />
  <issuerMetadata address="String" />
</issuedTokenParameters>
```  
  
## <a name="type"></a><span data-ttu-id="2ec3b-103">Type</span><span class="sxs-lookup"><span data-stu-id="2ec3b-103">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2ec3b-104">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="2ec3b-104">Attributes and Elements</span></span>  
 <span data-ttu-id="2ec3b-105">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="2ec3b-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2ec3b-106">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="2ec3b-106">Attributes</span></span>  
  
|<span data-ttu-id="2ec3b-107">Атрибут</span><span class="sxs-lookup"><span data-stu-id="2ec3b-107">Attribute</span></span>|<span data-ttu-id="2ec3b-108">Описание:</span><span class="sxs-lookup"><span data-stu-id="2ec3b-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2ec3b-109">defaultMessageSecurityVersion</span><span class="sxs-lookup"><span data-stu-id="2ec3b-109">defaultMessageSecurityVersion</span></span>|<span data-ttu-id="2ec3b-110">Задает версии спецификаций безопасности (WS-Security, WS-Trust, WS-Secure Conversation и WS-Security Policy), которые должны поддерживаться привязкой.</span><span class="sxs-lookup"><span data-stu-id="2ec3b-110">Specifies the versions of the security specifications, (WS-Security, WS-Trust, WS-Secure Conversation and WS-Security Policy) that must be supported by the binding.</span></span> <span data-ttu-id="2ec3b-111">Это значение имеет тип <xref:System.ServiceModel.MessageSecurityVersion>.</span><span class="sxs-lookup"><span data-stu-id="2ec3b-111">This value is of type <xref:System.ServiceModel.MessageSecurityVersion>.</span></span>|  
|<span data-ttu-id="2ec3b-112">inclusionMode</span><span class="sxs-lookup"><span data-stu-id="2ec3b-112">inclusionMode</span></span>|<span data-ttu-id="2ec3b-113">Задает требования включения маркера.</span><span class="sxs-lookup"><span data-stu-id="2ec3b-113">Specifies the token inclusion requirements.</span></span> <span data-ttu-id="2ec3b-114">Это атрибут типа <xref:System.ServiceModel.Security.Tokens.SecurityTokenInclusionMode>.</span><span class="sxs-lookup"><span data-stu-id="2ec3b-114">This attribute is of type <xref:System.ServiceModel.Security.Tokens.SecurityTokenInclusionMode>.</span></span>|  
|<span data-ttu-id="2ec3b-115">keySize</span><span class="sxs-lookup"><span data-stu-id="2ec3b-115">keySize</span></span>|<span data-ttu-id="2ec3b-116">Целое число, которое задает размер ключа маркера.</span><span class="sxs-lookup"><span data-stu-id="2ec3b-116">An integer that specifies the token key size.</span></span> <span data-ttu-id="2ec3b-117">Значение по умолчанию — 256.</span><span class="sxs-lookup"><span data-stu-id="2ec3b-117">The default value is 256.</span></span>|  
|<span data-ttu-id="2ec3b-118">keyType</span><span class="sxs-lookup"><span data-stu-id="2ec3b-118">keyType</span></span>|<span data-ttu-id="2ec3b-119">Допустимое значение <xref:System.IdentityModel.Tokens.SecurityKeyType>, которое задает тип ключа.</span><span class="sxs-lookup"><span data-stu-id="2ec3b-119">A valid value of <xref:System.IdentityModel.Tokens.SecurityKeyType> that specifies the key type.</span></span> <span data-ttu-id="2ec3b-120">Значение по умолчанию — `SymmetricKey`.</span><span class="sxs-lookup"><span data-stu-id="2ec3b-120">The default is `SymmetricKey`.</span></span>|  
|<span data-ttu-id="2ec3b-121">tokenType</span><span class="sxs-lookup"><span data-stu-id="2ec3b-121">tokenType</span></span>|<span data-ttu-id="2ec3b-122">Строка, задающая тип маркера.</span><span class="sxs-lookup"><span data-stu-id="2ec3b-122">A string that specifies the token type.</span></span> <span data-ttu-id="2ec3b-123">Значение по умолчанию - «http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAML».</span><span class="sxs-lookup"><span data-stu-id="2ec3b-123">The default is "http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAML".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2ec3b-124">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="2ec3b-124">Child Elements</span></span>  
  
|<span data-ttu-id="2ec3b-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="2ec3b-125">Element</span></span>|<span data-ttu-id="2ec3b-126">Описание</span><span class="sxs-lookup"><span data-stu-id="2ec3b-126">Description</span></span>|  
|-------------|-----------------|  
|[\<additionalRequestParameters>](additionalrequestparameters-element.md)|<span data-ttu-id="2ec3b-127">Коллекция элементов конфигурации, задающих дополнительные параметры запросов.</span><span class="sxs-lookup"><span data-stu-id="2ec3b-127">A collection of configuration elements that specify additional request parameters.</span></span>|  
|[\<claimTypeRequirements>](claimtyperequirements-element.md)|<span data-ttu-id="2ec3b-128">Задает коллекцию обязательных типов утверждений.</span><span class="sxs-lookup"><span data-stu-id="2ec3b-128">Specifies a collection of required claim types.</span></span><br /><br /> <span data-ttu-id="2ec3b-129">В федеративном сценарии службы предъявляют требования к входящим учетным данным.</span><span class="sxs-lookup"><span data-stu-id="2ec3b-129">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="2ec3b-130">Например, входящие учетные данные должны обладать определенным набором типов утверждений.</span><span class="sxs-lookup"><span data-stu-id="2ec3b-130">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="2ec3b-131">Каждый элемент в этой коллекции задает типы обязательных и необязательных утверждений, которые могут появляться в федеративных учетных данных.</span><span class="sxs-lookup"><span data-stu-id="2ec3b-131">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
|[\<issuer>](issuer-of-issuedtokenparameters.md)|<span data-ttu-id="2ec3b-132">Элемент конфигурации, задающий конечную точку, выдавшую текущий маркер.</span><span class="sxs-lookup"><span data-stu-id="2ec3b-132">A configuration element that specifies the endpoint that issues the current token.</span></span>|  
|[\<issuerMetadata>](issuermetadata-of-issuedtokenparameters.md)|<span data-ttu-id="2ec3b-133">Элемент конфигурации, задающий адрес конечной точки метаданных поставщика маркера.</span><span class="sxs-lookup"><span data-stu-id="2ec3b-133">A configuration element that specifies the endpoint address of the token issuer's metadata.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2ec3b-134">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="2ec3b-134">Parent Elements</span></span>  
  
|<span data-ttu-id="2ec3b-135">Элемент</span><span class="sxs-lookup"><span data-stu-id="2ec3b-135">Element</span></span>|<span data-ttu-id="2ec3b-136">Описание</span><span class="sxs-lookup"><span data-stu-id="2ec3b-136">Description</span></span>|  
|-------------|-----------------|  
|[\<secureConversationBootstrap>](secureconversationbootstrap.md)|<span data-ttu-id="2ec3b-137">Задает значения по умолчанию, используемые для инициализации службы безопасного обмена данными.</span><span class="sxs-lookup"><span data-stu-id="2ec3b-137">Specifies the default values used for initiating a secure conversation service.</span></span>|  
|[\<security>](security-of-custombinding.md)|<span data-ttu-id="2ec3b-138">Задает параметры безопасности для пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="2ec3b-138">Specifies the security options for a custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2ec3b-139">См. также</span><span class="sxs-lookup"><span data-stu-id="2ec3b-139">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement>
- <xref:System.ServiceModel.Configuration.SecurityElementBase.IssuedTokenParameters%2A>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="2ec3b-140">Привязки</span><span class="sxs-lookup"><span data-stu-id="2ec3b-140">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="2ec3b-141">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="2ec3b-141">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="2ec3b-142">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="2ec3b-142">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
- [<span data-ttu-id="2ec3b-143">Практическое руководство. Создание пользовательской привязки с использованием элемента SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="2ec3b-143">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="2ec3b-144">Безопасность пользовательской привязки</span><span class="sxs-lookup"><span data-stu-id="2ec3b-144">Custom Binding Security</span></span>](../../../wcf/samples/custom-binding-security.md)
- [<span data-ttu-id="2ec3b-145">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="2ec3b-145">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="2ec3b-146">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="2ec3b-146">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="2ec3b-147">Возможности безопасности при использовании пользовательских привязок</span><span class="sxs-lookup"><span data-stu-id="2ec3b-147">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="2ec3b-148">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="2ec3b-148">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
