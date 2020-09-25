---
title: Элемент <message> для <ws2007FederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: 52cd941d-e230-4c82-8b29-333a7d20eca8
ms.openlocfilehash: d71bce5e94568bdad3c52226fa1029a1dd87bfd9
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204922"
---
# <a name="message-element-of-ws2007federationhttpbinding"></a><span data-ttu-id="b84c3-102">Элемент \<message> для \<ws2007FederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="b84c3-102">\<message> element of \<ws2007FederationHttpBinding></span></span>

<span data-ttu-id="b84c3-103">Определяет параметры безопасности на уровне сообщений для [\<ws2007FederationHttpBinding>](ws2007federationhttpbinding.md) элемента.</span><span class="sxs-lookup"><span data-stu-id="b84c3-103">Defines settings for the message-level security for the [\<ws2007FederationHttpBinding>](ws2007federationhttpbinding.md) element.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<ws2007FederationHttpBinding>**](ws2007federationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-element-of-ws2007federationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<message>**  
  
## <a name="syntax"></a><span data-ttu-id="b84c3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b84c3-104">Syntax</span></span>  
  
```xml  
<ws2007FederationBinding>
  <binding>
    <security>
      <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
               issuedTokenType="string"
               issuedKeyType="SymmetricKey/PublicKey"
               negotiateServiceCredential="Boolean">
        <claimTypeRequirements>
          <add claimType="URI"
               isOptional="Boolean" />
        </claimTypeRequirements>
        <issuer address="Uri">
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
                                  x509FindType="System.Security.Cryptography.X509certificates.X509findtype" />
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
</ws2007FederationBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b84c3-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b84c3-105">Attributes and Elements</span></span>  

 <span data-ttu-id="b84c3-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="b84c3-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b84c3-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b84c3-107">Attributes</span></span>  
  
|<span data-ttu-id="b84c3-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="b84c3-108">Attribute</span></span>|<span data-ttu-id="b84c3-109">Описание</span><span class="sxs-lookup"><span data-stu-id="b84c3-109">Description</span></span>|  
|---------------|-----------------|  
|`algorithmSuite`|<span data-ttu-id="b84c3-110">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="b84c3-110">Optional.</span></span> <span data-ttu-id="b84c3-111">Задает алгоритмы шифрования сообщений, сигнатуры и ключей.</span><span class="sxs-lookup"><span data-stu-id="b84c3-111">Sets the message encryption, signature, and key-wrap algorithms.</span></span> <span data-ttu-id="b84c3-112">Алгоритмы и размеры ключей определяются классом <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span><span class="sxs-lookup"><span data-stu-id="b84c3-112">The algorithms and the key sizes are determined by the <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> class.</span></span> <span data-ttu-id="b84c3-113">Эти алгоритмы соответствуют алгоритмам, заданным в спецификации языка политики безопасности (WS-SecurityPolicy).</span><span class="sxs-lookup"><span data-stu-id="b84c3-113">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span><br /><br /> <span data-ttu-id="b84c3-114">В следующей таблице приводятся возможные значения.</span><span class="sxs-lookup"><span data-stu-id="b84c3-114">See the following table for possible values.</span></span> <span data-ttu-id="b84c3-115">Значение по умолчанию - Basic256.</span><span class="sxs-lookup"><span data-stu-id="b84c3-115">The default value is Basic256.</span></span>|  
|`issuedKeyType`|<span data-ttu-id="b84c3-116">Задает тип выдаваемого ключа.</span><span class="sxs-lookup"><span data-stu-id="b84c3-116">Specifies the type of key to be issued.</span></span> <span data-ttu-id="b84c3-117">Допустимые значения.</span><span class="sxs-lookup"><span data-stu-id="b84c3-117">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="b84c3-118">-SymmetricKey</span><span class="sxs-lookup"><span data-stu-id="b84c3-118">-   SymmetricKey</span></span><br /><span data-ttu-id="b84c3-119">-PublicKey</span><span class="sxs-lookup"><span data-stu-id="b84c3-119">-   PublicKey</span></span><br /><span data-ttu-id="b84c3-120">-Беареркэй</span><span class="sxs-lookup"><span data-stu-id="b84c3-120">-   BearerKey</span></span><br /><br /> <span data-ttu-id="b84c3-121">Значение по умолчанию - SymmetricKey.</span><span class="sxs-lookup"><span data-stu-id="b84c3-121">The default is SymmetricKey.</span></span> <span data-ttu-id="b84c3-122">Это атрибут типа <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span><span class="sxs-lookup"><span data-stu-id="b84c3-122">This attribute is of type <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span></span>|  
|`issuedTokenType`|<span data-ttu-id="b84c3-123">Универсальный код ресурса (URI), который задает тип выдаваемых маркеров.</span><span class="sxs-lookup"><span data-stu-id="b84c3-123">A URI that specifies the type of token to be issued.</span></span> <span data-ttu-id="b84c3-124">Значение по умолчанию — `null`.</span><span class="sxs-lookup"><span data-stu-id="b84c3-124">The default is `null`.</span></span>|  
|`negotiateServiceCredential`|<span data-ttu-id="b84c3-125">Значение, которое определяет, должен ли проводиться обмен учетными данными службы в рамках процесса согласования, или эти данные доступны вне диапазона.</span><span class="sxs-lookup"><span data-stu-id="b84c3-125">A value that specifies whether the service credential should be exchanged as part of negotiation or is available out of band.</span></span> <span data-ttu-id="b84c3-126">Значением по умолчанию является `true`, означающее, что учетные данные службы согласуются.</span><span class="sxs-lookup"><span data-stu-id="b84c3-126">The default is `true`, which means that the service credential is negotiated.</span></span>|  
  
## <a name="algorithmsuite-attribute"></a><span data-ttu-id="b84c3-127">Атрибут algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="b84c3-127">algorithmSuite Attribute</span></span>  
  
|<span data-ttu-id="b84c3-128">Значение</span><span class="sxs-lookup"><span data-stu-id="b84c3-128">Value</span></span>|<span data-ttu-id="b84c3-129">Описание</span><span class="sxs-lookup"><span data-stu-id="b84c3-129">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b84c3-130">Basic128</span><span class="sxs-lookup"><span data-stu-id="b84c3-130">Basic128</span></span>|<span data-ttu-id="b84c3-131">Используется шифрование Aes128, Sha1 для хэша и Rsa-oaep-mgf1p для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="b84c3-131">Use Aes128 encryption, Sha1 for message digest, and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="b84c3-132">Basic192</span><span class="sxs-lookup"><span data-stu-id="b84c3-132">Basic192</span></span>|<span data-ttu-id="b84c3-133">Используется шифрование Aes192, Sha1 для хэша и Rsa-oaep-mgf1p для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="b84c3-133">Use Aes192 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="b84c3-134">Basic256</span><span class="sxs-lookup"><span data-stu-id="b84c3-134">Basic256</span></span>|<span data-ttu-id="b84c3-135">Используется шифрование Aes256, Sha1 для хэш-кода и Rsa-oaep-mgf1p для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="b84c3-135">Use Aes256 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="b84c3-136">Basic256Rsa15</span><span class="sxs-lookup"><span data-stu-id="b84c3-136">Basic256Rsa15</span></span>|<span data-ttu-id="b84c3-137">Используется Aes256 для шифрования сообщения, Sha1 для хэш-кода и Rsa15 для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="b84c3-137">Use Aes256 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="b84c3-138">Basic192Rsa15</span><span class="sxs-lookup"><span data-stu-id="b84c3-138">Basic192Rsa15</span></span>|<span data-ttu-id="b84c3-139">Используется Aes192 для шифрования сообщения, Sha1 для хэш-кода и Rsa15 для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="b84c3-139">Use Aes192 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="b84c3-140">TripleDes</span><span class="sxs-lookup"><span data-stu-id="b84c3-140">TripleDes</span></span>|<span data-ttu-id="b84c3-141">Используется шифрование TripleDes, Sha1 для хэш-кода и Rsa-oaep-mgf1p для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="b84c3-141">Use TripleDes encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="b84c3-142">Basic128Rsa15</span><span class="sxs-lookup"><span data-stu-id="b84c3-142">Basic128Rsa15</span></span>|<span data-ttu-id="b84c3-143">Используется Aes128 для шифрования сообщения, Sha1 для хэш-кода и Rsa15 для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="b84c3-143">Use Aes128 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="b84c3-144">TripleDesRsa15</span><span class="sxs-lookup"><span data-stu-id="b84c3-144">TripleDesRsa15</span></span>|<span data-ttu-id="b84c3-145">Используется TripleDes для шифрования сообщения, Sha1 для хэш-кода и Rsa15 для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="b84c3-145">Use TripleDes encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="b84c3-146">Basic128Sha256</span><span class="sxs-lookup"><span data-stu-id="b84c3-146">Basic128Sha256</span></span>|<span data-ttu-id="b84c3-147">Используется Aes256 для шифрования сообщения, Sha256 для хэша и Rsa-oaep-mgf1p для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="b84c3-147">Use Aes256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="b84c3-148">Basic192Sha256</span><span class="sxs-lookup"><span data-stu-id="b84c3-148">Basic192Sha256</span></span>|<span data-ttu-id="b84c3-149">Используется Aes192 для шифрования сообщения, Sha256 для хэш-кода и Rsa-oaep-mgf1p для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="b84c3-149">Use Aes192 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="b84c3-150">Basic256Sha256</span><span class="sxs-lookup"><span data-stu-id="b84c3-150">Basic256Sha256</span></span>|<span data-ttu-id="b84c3-151">Используется Aes256 для шифрования сообщения, Sha256 для хэша и Rsa-oaep-mgf1p для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="b84c3-151">Use Aes256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="b84c3-152">TripleDesSha256</span><span class="sxs-lookup"><span data-stu-id="b84c3-152">TripleDesSha256</span></span>|<span data-ttu-id="b84c3-153">Используется TripleDes для шифрования сообщения, Sha256 для хэш-кода и Rsa-oaep-mgf1p для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="b84c3-153">Use TripleDes for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="b84c3-154">Basic128Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="b84c3-154">Basic128Sha256Rsa15</span></span>|<span data-ttu-id="b84c3-155">Используется Aes128 для шифрования сообщения, Sha256 для хэш-кода и Rsa15 для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="b84c3-155">Use Aes128 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="b84c3-156">Basic192Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="b84c3-156">Basic192Sha256Rsa15</span></span>|<span data-ttu-id="b84c3-157">Используется Aes192 для шифрования сообщения, Sha256 для хэш-кода и Rsa15 для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="b84c3-157">Use Aes192 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="b84c3-158">Basic256Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="b84c3-158">Basic256Sha256Rsa15</span></span>|<span data-ttu-id="b84c3-159">Используется Aes256 для шифрования сообщения, Sha256 для хэша и Rsa15 для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="b84c3-159">Use Aes256 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="b84c3-160">TripleDesSha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="b84c3-160">TripleDesSha256Rsa15</span></span>|<span data-ttu-id="b84c3-161">Используется TripleDes для шифрования сообщения, Sha256 для хэш-кода и Rsa15 для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="b84c3-161">Use TripleDes for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b84c3-162">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b84c3-162">Child Elements</span></span>  
  
|<span data-ttu-id="b84c3-163">Элемент</span><span class="sxs-lookup"><span data-stu-id="b84c3-163">Element</span></span>|<span data-ttu-id="b84c3-164">Описание</span><span class="sxs-lookup"><span data-stu-id="b84c3-164">Description</span></span>|  
|-------------|-----------------|  
|[\<claimTypeRequirements>](claimtyperequirements-element.md)|<span data-ttu-id="b84c3-165">Задает коллекцию типов утверждений для этой привязки.</span><span class="sxs-lookup"><span data-stu-id="b84c3-165">Specifies a collection of claim types for this binding.</span></span> <span data-ttu-id="b84c3-166">Каждый элемент имеет тип <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="b84c3-166">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span>|  
|[\<issuer>](issuer.md)|<span data-ttu-id="b84c3-167">Задает конечную точку, которая выдает маркер безопасности.</span><span class="sxs-lookup"><span data-stu-id="b84c3-167">Specifies an endpoint that issues a security token.</span></span> <span data-ttu-id="b84c3-168">Это элемент типа <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span><span class="sxs-lookup"><span data-stu-id="b84c3-168">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span></span>|  
|[\<issuerMetadata>](issuermetadata.md)|<span data-ttu-id="b84c3-169">Задает адрес конечной точки издателя.</span><span class="sxs-lookup"><span data-stu-id="b84c3-169">Specifies the endpoint address of the issuer.</span></span>|  
|[\<tokenRequestParameters>](tokenrequestparameters.md)|<span data-ttu-id="b84c3-170">Коллекция параметров запроса маркера.</span><span class="sxs-lookup"><span data-stu-id="b84c3-170">A collection of token request parameters.</span></span> <span data-ttu-id="b84c3-171">Каждый параметр представляет собой элемент XML.</span><span class="sxs-lookup"><span data-stu-id="b84c3-171">Each parameter is an XML element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b84c3-172">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b84c3-172">Parent Elements</span></span>  
  
|<span data-ttu-id="b84c3-173">Элемент</span><span class="sxs-lookup"><span data-stu-id="b84c3-173">Element</span></span>|<span data-ttu-id="b84c3-174">Описание</span><span class="sxs-lookup"><span data-stu-id="b84c3-174">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-element-of-ws2007federationhttpbinding.md)|<span data-ttu-id="b84c3-175">Определяет параметры безопасности для привязки.</span><span class="sxs-lookup"><span data-stu-id="b84c3-175">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b84c3-176">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b84c3-176">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement.Message%2A>
- <xref:System.ServiceModel.WSFederationHttpSecurity.Message%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>
- [<span data-ttu-id="b84c3-177">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="b84c3-177">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="b84c3-178">Привязки</span><span class="sxs-lookup"><span data-stu-id="b84c3-178">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="b84c3-179">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="b84c3-179">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="b84c3-180">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="b84c3-180">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
