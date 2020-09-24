---
title: Элемент <security> для <ws2007FederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: 826219b4-3a16-45fc-832d-0cd7cbbd3b84
ms.openlocfilehash: 943ccc241aef15b58661699408b085d98cf86c3b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91183706"
---
# <a name="security-element-of-ws2007federationhttpbinding"></a><span data-ttu-id="0b895-102">Элемент \<security> для \<ws2007FederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="0b895-102">\<security> element of \<ws2007FederationHttpBinding></span></span>

<span data-ttu-id="0b895-103">Определяет параметры безопасности [\<ws2007FederationHttpBinding>](ws2007federationhttpbinding.md) элемента.</span><span class="sxs-lookup"><span data-stu-id="0b895-103">Defines the security settings of the [\<ws2007FederationHttpBinding>](ws2007federationhttpbinding.md) element.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<ws2007FederationHttpBinding>**](ws2007federationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="0b895-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0b895-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0b895-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="0b895-105">Attributes and Elements</span></span>  

 <span data-ttu-id="0b895-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="0b895-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0b895-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="0b895-107">Attributes</span></span>  
  
|<span data-ttu-id="0b895-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="0b895-108">Attribute</span></span>|<span data-ttu-id="0b895-109">Описание</span><span class="sxs-lookup"><span data-stu-id="0b895-109">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="0b895-110">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="0b895-110">Optional.</span></span> <span data-ttu-id="0b895-111">Задает тип применяемого механизма обеспечения безопасности.</span><span class="sxs-lookup"><span data-stu-id="0b895-111">Specifies the type of security that is applied.</span></span> <span data-ttu-id="0b895-112">Значение по умолчанию — `Message`.</span><span class="sxs-lookup"><span data-stu-id="0b895-112">The default value is `Message`.</span></span> <span data-ttu-id="0b895-113">Это атрибут типа <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="0b895-113">This attribute is of type <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="0b895-114">Атрибут mode</span><span class="sxs-lookup"><span data-stu-id="0b895-114">mode Attribute</span></span>  
  
|<span data-ttu-id="0b895-115">Значение</span><span class="sxs-lookup"><span data-stu-id="0b895-115">Value</span></span>|<span data-ttu-id="0b895-116">Описание</span><span class="sxs-lookup"><span data-stu-id="0b895-116">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0b895-117">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="0b895-117">None</span></span>|<span data-ttu-id="0b895-118">Во время передачи сообщение SOAP не защищено.</span><span class="sxs-lookup"><span data-stu-id="0b895-118">The SOAP message is not secure during transfer.</span></span>|  
|<span data-ttu-id="0b895-119">Сообщение</span><span class="sxs-lookup"><span data-stu-id="0b895-119">Message</span></span>|<span data-ttu-id="0b895-120">Целостность, конфиденциальность, проверка подлинности сервера и проверка подлинности клиента обеспечиваются с помощью средств безопасности сообщений SOAP.</span><span class="sxs-lookup"><span data-stu-id="0b895-120">Integrity, confidentiality, server authentication and client authentication are provided using SOAP message security.</span></span> <span data-ttu-id="0b895-121">По умолчанию текст сообщений шифруется и подписывается.</span><span class="sxs-lookup"><span data-stu-id="0b895-121">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="0b895-122">Служба должна быть настроена с использованием сертификата.</span><span class="sxs-lookup"><span data-stu-id="0b895-122">The service must be configured with a certificate.</span></span> <span data-ttu-id="0b895-123">Проверка подлинности клиента основана на маркере, выданного клиенту службой маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="0b895-123">Client authentication is based on the token issued to the client by a security token service.</span></span>|  
|<span data-ttu-id="0b895-124">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="0b895-124">TransportWithMessageCredential</span></span>|<span data-ttu-id="0b895-125">Целостность, конфиденциальность и проверка подлинности сервера обеспечиваются с помощью HTTPS.</span><span class="sxs-lookup"><span data-stu-id="0b895-125">Integrity, confidentiality and server authentication are provided by HTTPS.</span></span> <span data-ttu-id="0b895-126">Служба должна быть настроена с использованием сертификата.</span><span class="sxs-lookup"><span data-stu-id="0b895-126">The service must be configured with a certificate.</span></span> <span data-ttu-id="0b895-127">Проверка подлинности клиента выполняется с помощью средств безопасности сообщений SOAP и основана на маркере, выданном клиенту службой маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="0b895-127">Client authentication is provided by means of SOAP message security and is based on the token issued to the client by a security token service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0b895-128">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="0b895-128">Child Elements</span></span>  
  
|<span data-ttu-id="0b895-129">Элемент</span><span class="sxs-lookup"><span data-stu-id="0b895-129">Element</span></span>|<span data-ttu-id="0b895-130">Описание</span><span class="sxs-lookup"><span data-stu-id="0b895-130">Description</span></span>|  
|-------------|-----------------|  
|[\<message>](message-of-ws2007httpbinding.md)|<span data-ttu-id="0b895-131">Определяет параметры безопасности уровня сообщений.</span><span class="sxs-lookup"><span data-stu-id="0b895-131">Defines the settings for the message-level security.</span></span> <span data-ttu-id="0b895-132">Это элемент типа <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span><span class="sxs-lookup"><span data-stu-id="0b895-132">This element is of type <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0b895-133">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="0b895-133">Parent Elements</span></span>  
  
|<span data-ttu-id="0b895-134">Элемент</span><span class="sxs-lookup"><span data-stu-id="0b895-134">Element</span></span>|<span data-ttu-id="0b895-135">Описание</span><span class="sxs-lookup"><span data-stu-id="0b895-135">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="0b895-136">Определяет все возможности привязки [\<wsDualHttpBinding>](wsdualhttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="0b895-136">Defines all binding capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0b895-137">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="0b895-137">See also</span></span>

- <xref:System.ServiceModel.WSFederationHttpSecurity>
- <xref:System.ServiceModel.WSFederationHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>
- [<span data-ttu-id="0b895-138">Практическое руководство. Создание WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="0b895-138">How to: Create a WSFederationHttpBinding</span></span>](../../../wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)
- [<span data-ttu-id="0b895-139">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="0b895-139">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="0b895-140">Выбор типа учетных данных</span><span class="sxs-lookup"><span data-stu-id="0b895-140">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="0b895-141">Привязки</span><span class="sxs-lookup"><span data-stu-id="0b895-141">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="0b895-142">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="0b895-142">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="0b895-143">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="0b895-143">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
