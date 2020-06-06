---
title: Элемент <security> для <ws2007FederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: 826219b4-3a16-45fc-832d-0cd7cbbd3b84
ms.openlocfilehash: b85c54c6507313522286e0c66504cfd0c8afb2b0
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "73738722"
---
# <a name="security-element-of-ws2007federationhttpbinding"></a><span data-ttu-id="5bf6a-102">Элемент \<security> для \<ws2007FederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="5bf6a-102">\<security> element of \<ws2007FederationHttpBinding></span></span>
<span data-ttu-id="5bf6a-103">Определяет параметры безопасности [\<ws2007FederationHttpBinding>](ws2007federationhttpbinding.md) элемента.</span><span class="sxs-lookup"><span data-stu-id="5bf6a-103">Defines the security settings of the [\<ws2007FederationHttpBinding>](ws2007federationhttpbinding.md) element.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<ws2007FederationHttpBinding>**](ws2007federationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="5bf6a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5bf6a-104">Syntax</span></span>  
  
```xml  
<ws2007FederationBinding>
  <binding>
    <security mode="None/Message/TransportWithMessageCredential">
      <message negotiateServiceCredential="Boolean"
               algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/  Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
               defaultProtectionLevel="none/sign/EncryptAndSign"
               issuedTokenType="string"
               issuedKeyType="SymmetricKey/PublicKey">
      </message>
    </security>
  </binding>
</ws2007FederationBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5bf6a-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="5bf6a-105">Attributes and Elements</span></span>  
 <span data-ttu-id="5bf6a-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="5bf6a-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5bf6a-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="5bf6a-107">Attributes</span></span>  
  
|<span data-ttu-id="5bf6a-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="5bf6a-108">Attribute</span></span>|<span data-ttu-id="5bf6a-109">Описание</span><span class="sxs-lookup"><span data-stu-id="5bf6a-109">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="5bf6a-110">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="5bf6a-110">Optional.</span></span> <span data-ttu-id="5bf6a-111">Задает тип применяемого механизма обеспечения безопасности.</span><span class="sxs-lookup"><span data-stu-id="5bf6a-111">Specifies the type of security that is applied.</span></span> <span data-ttu-id="5bf6a-112">Значение по умолчанию — `Message`.</span><span class="sxs-lookup"><span data-stu-id="5bf6a-112">The default value is `Message`.</span></span> <span data-ttu-id="5bf6a-113">Это атрибут типа <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="5bf6a-113">This attribute is of type <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="5bf6a-114">Атрибут mode</span><span class="sxs-lookup"><span data-stu-id="5bf6a-114">mode Attribute</span></span>  
  
|<span data-ttu-id="5bf6a-115">Значение</span><span class="sxs-lookup"><span data-stu-id="5bf6a-115">Value</span></span>|<span data-ttu-id="5bf6a-116">Описание</span><span class="sxs-lookup"><span data-stu-id="5bf6a-116">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5bf6a-117">None</span><span class="sxs-lookup"><span data-stu-id="5bf6a-117">None</span></span>|<span data-ttu-id="5bf6a-118">Во время передачи сообщение SOAP не защищено.</span><span class="sxs-lookup"><span data-stu-id="5bf6a-118">The SOAP message is not secure during transfer.</span></span>|  
|<span data-ttu-id="5bf6a-119">Сообщение</span><span class="sxs-lookup"><span data-stu-id="5bf6a-119">Message</span></span>|<span data-ttu-id="5bf6a-120">Целостность, конфиденциальность, проверка подлинности сервера и проверка подлинности клиента обеспечиваются с помощью средств безопасности сообщений SOAP.</span><span class="sxs-lookup"><span data-stu-id="5bf6a-120">Integrity, confidentiality, server authentication and client authentication are provided using SOAP message security.</span></span> <span data-ttu-id="5bf6a-121">По умолчанию текст сообщений шифруется и подписывается.</span><span class="sxs-lookup"><span data-stu-id="5bf6a-121">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="5bf6a-122">Служба должна быть настроена с использованием сертификата.</span><span class="sxs-lookup"><span data-stu-id="5bf6a-122">The service must be configured with a certificate.</span></span> <span data-ttu-id="5bf6a-123">Проверка подлинности клиента основана на маркере, выданного клиенту службой маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="5bf6a-123">Client authentication is based on the token issued to the client by a security token service.</span></span>|  
|<span data-ttu-id="5bf6a-124">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="5bf6a-124">TransportWithMessageCredential</span></span>|<span data-ttu-id="5bf6a-125">Целостность, конфиденциальность и проверка подлинности сервера обеспечиваются с помощью HTTPS.</span><span class="sxs-lookup"><span data-stu-id="5bf6a-125">Integrity, confidentiality and server authentication are provided by HTTPS.</span></span> <span data-ttu-id="5bf6a-126">Служба должна быть настроена с использованием сертификата.</span><span class="sxs-lookup"><span data-stu-id="5bf6a-126">The service must be configured with a certificate.</span></span> <span data-ttu-id="5bf6a-127">Проверка подлинности клиента выполняется с помощью средств безопасности сообщений SOAP и основана на маркере, выданном клиенту службой маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="5bf6a-127">Client authentication is provided by means of SOAP message security and is based on the token issued to the client by a security token service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5bf6a-128">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="5bf6a-128">Child Elements</span></span>  
  
|<span data-ttu-id="5bf6a-129">Элемент</span><span class="sxs-lookup"><span data-stu-id="5bf6a-129">Element</span></span>|<span data-ttu-id="5bf6a-130">Описание</span><span class="sxs-lookup"><span data-stu-id="5bf6a-130">Description</span></span>|  
|-------------|-----------------|  
|[\<message>](message-of-ws2007httpbinding.md)|<span data-ttu-id="5bf6a-131">Определяет параметры безопасности уровня сообщений.</span><span class="sxs-lookup"><span data-stu-id="5bf6a-131">Defines the settings for the message-level security.</span></span> <span data-ttu-id="5bf6a-132">Это элемент типа <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span><span class="sxs-lookup"><span data-stu-id="5bf6a-132">This element is of type <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5bf6a-133">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="5bf6a-133">Parent Elements</span></span>  
  
|<span data-ttu-id="5bf6a-134">Элемент</span><span class="sxs-lookup"><span data-stu-id="5bf6a-134">Element</span></span>|<span data-ttu-id="5bf6a-135">Описание</span><span class="sxs-lookup"><span data-stu-id="5bf6a-135">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="5bf6a-136">Определяет все возможности привязки [\<wsDualHttpBinding>](wsdualhttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="5bf6a-136">Defines all binding capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5bf6a-137">См. также</span><span class="sxs-lookup"><span data-stu-id="5bf6a-137">See also</span></span>

- <xref:System.ServiceModel.WSFederationHttpSecurity>
- <xref:System.ServiceModel.WSFederationHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>
- [<span data-ttu-id="5bf6a-138">Практическое руководство. Создание WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="5bf6a-138">How to: Create a WSFederationHttpBinding</span></span>](../../../wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)
- [<span data-ttu-id="5bf6a-139">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="5bf6a-139">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="5bf6a-140">Выбор типа учетных данных</span><span class="sxs-lookup"><span data-stu-id="5bf6a-140">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="5bf6a-141">Привязки</span><span class="sxs-lookup"><span data-stu-id="5bf6a-141">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="5bf6a-142">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="5bf6a-142">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="5bf6a-143">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="5bf6a-143">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
