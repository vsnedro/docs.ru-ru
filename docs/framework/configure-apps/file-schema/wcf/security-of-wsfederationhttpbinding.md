---
title: <security> из <wsFederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: a8e5e854-b8dc-4921-843d-34b6a4a6a8ba
ms.openlocfilehash: 650483099c7d70450cfc56a9a28efac076d64675
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91162244"
---
# <a name="security-of-wsfederationhttpbinding"></a><span data-ttu-id="21c6e-102">\<security> из \<wsFederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="21c6e-102">\<security> of \<wsFederationHttpBinding></span></span>

<span data-ttu-id="21c6e-103">Определяет параметры безопасности для [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="21c6e-103">Defines the security settings of the [\<wsFederationHttpBinding>](wsfederationhttpbinding.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="21c6e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="21c6e-104">Syntax</span></span>  
  
```xml  
<wsFederationBinding>
  <binding>
    <security mode="None/Message/TransportWithMessageCredential">
      <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
               issuedTokenType="string"
               issuedKeyType="SymmetricKey/PublicKey"
               negotiateServiceCredential="Boolean">
        <claimTypeRequirements>
          <add claimType="URI"
               isOptional="Boolean" />
        </claimTypeRequirements>
        <issuer address="Uri" >
          <headers>
            <add name="String"
                 namespace="String" />
          </headers>
          <identity>
            <certificate encodedValue="String" />
            <certificateReference findValue="String"
                                  isChainIncluded="Boolean"
                                  storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                                  storeLocation="LocalMachine/CurrentUser"
                                  X509FindType="System.Security.Cryptography.X509certificates.X509findtype" />
            <dns value="String" />
            <rsa value="String" />
            <servicePrincipalName value="String" />
            <usePrincipalName value="String" />
          </identity>
        </issuer>
        <issuerMetadata address="String">
          <headers>
            <add name="String"
                 namespace="String" />
          </headers>
          <identity>
            <certificate encodedValue="String" />
            <certificateReference findValue="String"
                                  isChainIncluded="Boolean"
                                  storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                                  storeLocation="LocalMachine/CurrentUser"
                                  X509FindType="System.Security.Cryptography.X509certificates.X509findtype" />
            <dns value="String" />
            <rsa value="String" />
            <servicePrincipalName value="String" />
            <usePrincipalName value="String" />
          </identity>
        </issuerMetadata>
        <tokenRequestParameters>
          <xmlElement>
          </xmlElement>
        </tokenRequestParameters>
      </message>
    </security>
  </binding>
</wsFederationBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="21c6e-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="21c6e-105">Attributes and Elements</span></span>  

 <span data-ttu-id="21c6e-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="21c6e-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="21c6e-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="21c6e-107">Attributes</span></span>  
  
|<span data-ttu-id="21c6e-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="21c6e-108">Attribute</span></span>|<span data-ttu-id="21c6e-109">Описание</span><span class="sxs-lookup"><span data-stu-id="21c6e-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="21c6e-110">Режим</span><span class="sxs-lookup"><span data-stu-id="21c6e-110">Mode</span></span>|<span data-ttu-id="21c6e-111">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="21c6e-111">Optional.</span></span> <span data-ttu-id="21c6e-112">Задает тип применяемого механизма обеспечения безопасности.</span><span class="sxs-lookup"><span data-stu-id="21c6e-112">Specifies the type of security that is applied.</span></span> <span data-ttu-id="21c6e-113">Значение по умолчанию — `Message`.</span><span class="sxs-lookup"><span data-stu-id="21c6e-113">The default value is `Message`.</span></span> <span data-ttu-id="21c6e-114">Это атрибут типа <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="21c6e-114">This attribute is of type <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="21c6e-115">Атрибут Mode</span><span class="sxs-lookup"><span data-stu-id="21c6e-115">Mode Attribute</span></span>  
  
|<span data-ttu-id="21c6e-116">Значение</span><span class="sxs-lookup"><span data-stu-id="21c6e-116">Value</span></span>|<span data-ttu-id="21c6e-117">Описание</span><span class="sxs-lookup"><span data-stu-id="21c6e-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="21c6e-118">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="21c6e-118">None</span></span>|<span data-ttu-id="21c6e-119">Во время передачи сообщение SOAP не защищено.</span><span class="sxs-lookup"><span data-stu-id="21c6e-119">The SOAP message is not secure during transfer.</span></span>|  
|<span data-ttu-id="21c6e-120">Сообщение</span><span class="sxs-lookup"><span data-stu-id="21c6e-120">Message</span></span>|<span data-ttu-id="21c6e-121">Целостность, конфиденциальность, проверка подлинности сервера и проверка подлинности клиента обеспечиваются с помощью средств безопасности сообщений SOAP.</span><span class="sxs-lookup"><span data-stu-id="21c6e-121">Integrity, confidentiality, server authentication and client authentication are provided using SOAP message security.</span></span> <span data-ttu-id="21c6e-122">По умолчанию текст сообщений шифруется и подписывается.</span><span class="sxs-lookup"><span data-stu-id="21c6e-122">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="21c6e-123">Служба должна быть настроена с использованием сертификата.</span><span class="sxs-lookup"><span data-stu-id="21c6e-123">The service needs to be configured with a certificate.</span></span> <span data-ttu-id="21c6e-124">Проверка подлинности клиента осуществляется с использованием маркера, выданного клиенту службой маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="21c6e-124">Client authentication is based on the token issued to the client by a security token service</span></span>|  
|<span data-ttu-id="21c6e-125">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="21c6e-125">TransportWithMessageCredential</span></span>|<span data-ttu-id="21c6e-126">Целостность, конфиденциальность и проверка подлинности сервера обеспечиваются с помощью HTTPS.</span><span class="sxs-lookup"><span data-stu-id="21c6e-126">Integrity, confidentiality and server authentication are provided by HTTPS.</span></span> <span data-ttu-id="21c6e-127">Служба должна быть настроена с использованием сертификата.</span><span class="sxs-lookup"><span data-stu-id="21c6e-127">The service needs to be configured with a certificate.</span></span> <span data-ttu-id="21c6e-128">Проверка подлинности клиента выполняется с помощью средств безопасности сообщений SOAP и основана на маркере, выданном клиенту службой маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="21c6e-128">Client authentication is provided by means of SOAP message security and is based on the token issued to the client by a security token service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="21c6e-129">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="21c6e-129">Child Elements</span></span>  
  
|<span data-ttu-id="21c6e-130">Элемент</span><span class="sxs-lookup"><span data-stu-id="21c6e-130">Element</span></span>|<span data-ttu-id="21c6e-131">Описание</span><span class="sxs-lookup"><span data-stu-id="21c6e-131">Description</span></span>|  
|-------------|-----------------|  
|[\<message>](message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="21c6e-132">Определяет параметры безопасности уровня сообщений.</span><span class="sxs-lookup"><span data-stu-id="21c6e-132">Defines the settings for the message-level security.</span></span> <span data-ttu-id="21c6e-133">Это элемент типа <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span><span class="sxs-lookup"><span data-stu-id="21c6e-133">This element is of type <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="21c6e-134">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="21c6e-134">Parent Elements</span></span>  
  
|<span data-ttu-id="21c6e-135">Элемент</span><span class="sxs-lookup"><span data-stu-id="21c6e-135">Element</span></span>|<span data-ttu-id="21c6e-136">Описание</span><span class="sxs-lookup"><span data-stu-id="21c6e-136">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="21c6e-137">Определяет все возможности привязки [\<wsDualHttpBinding>](wsdualhttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="21c6e-137">Defines all binding capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="21c6e-138">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="21c6e-138">See also</span></span>

- <xref:System.ServiceModel.WSFederationHttpSecurity>
- <xref:System.ServiceModel.WSFederationHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>
- [<span data-ttu-id="21c6e-139">Практическое руководство. Создание WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="21c6e-139">How to: Create a WSFederationHttpBinding</span></span>](../../../wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)
- [<span data-ttu-id="21c6e-140">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="21c6e-140">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="21c6e-141">Выбор типа учетных данных</span><span class="sxs-lookup"><span data-stu-id="21c6e-141">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="21c6e-142">Привязки</span><span class="sxs-lookup"><span data-stu-id="21c6e-142">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="21c6e-143">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="21c6e-143">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="21c6e-144">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="21c6e-144">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
