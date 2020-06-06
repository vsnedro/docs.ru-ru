---
title: Элемент <message> для <ws2007FederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: 52cd941d-e230-4c82-8b29-333a7d20eca8
ms.openlocfilehash: dde763687dbc62d6fb342a21a4c614208f28d7e8
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "73739001"
---
# <a name="message-element-of-ws2007federationhttpbinding"></a><span data-ttu-id="7b89c-102">Элемент \<message> для \<ws2007FederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="7b89c-102">\<message> element of \<ws2007FederationHttpBinding></span></span>
<span data-ttu-id="7b89c-103">Определяет параметры безопасности на уровне сообщений для [\<ws2007FederationHttpBinding>](ws2007federationhttpbinding.md) элемента.</span><span class="sxs-lookup"><span data-stu-id="7b89c-103">Defines settings for the message-level security for the [\<ws2007FederationHttpBinding>](ws2007federationhttpbinding.md) element.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<ws2007FederationHttpBinding>**](ws2007federationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-element-of-ws2007federationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<message>**  
  
## <a name="syntax"></a><span data-ttu-id="7b89c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7b89c-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7b89c-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="7b89c-105">Attributes and Elements</span></span>  
 <span data-ttu-id="7b89c-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="7b89c-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7b89c-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="7b89c-107">Attributes</span></span>  
  
|<span data-ttu-id="7b89c-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="7b89c-108">Attribute</span></span>|<span data-ttu-id="7b89c-109">Описание</span><span class="sxs-lookup"><span data-stu-id="7b89c-109">Description</span></span>|  
|---------------|-----------------|  
|`algorithmSuite`|<span data-ttu-id="7b89c-110">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="7b89c-110">Optional.</span></span> <span data-ttu-id="7b89c-111">Задает алгоритмы шифрования сообщений, сигнатуры и ключей.</span><span class="sxs-lookup"><span data-stu-id="7b89c-111">Sets the message encryption, signature, and key-wrap algorithms.</span></span> <span data-ttu-id="7b89c-112">Алгоритмы и размеры ключей определяются классом <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span><span class="sxs-lookup"><span data-stu-id="7b89c-112">The algorithms and the key sizes are determined by the <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> class.</span></span> <span data-ttu-id="7b89c-113">Эти алгоритмы соответствуют алгоритмам, заданным в спецификации языка политики безопасности (WS-SecurityPolicy).</span><span class="sxs-lookup"><span data-stu-id="7b89c-113">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span><br /><br /> <span data-ttu-id="7b89c-114">В следующей таблице приводятся возможные значения.</span><span class="sxs-lookup"><span data-stu-id="7b89c-114">See the following table for possible values.</span></span> <span data-ttu-id="7b89c-115">Значение по умолчанию - Basic256.</span><span class="sxs-lookup"><span data-stu-id="7b89c-115">The default value is Basic256.</span></span>|  
|`issuedKeyType`|<span data-ttu-id="7b89c-116">Задает тип выдаваемого ключа.</span><span class="sxs-lookup"><span data-stu-id="7b89c-116">Specifies the type of key to be issued.</span></span> <span data-ttu-id="7b89c-117">Допустимые значения.</span><span class="sxs-lookup"><span data-stu-id="7b89c-117">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="7b89c-118">-SymmetricKey</span><span class="sxs-lookup"><span data-stu-id="7b89c-118">-   SymmetricKey</span></span><br /><span data-ttu-id="7b89c-119">-PublicKey</span><span class="sxs-lookup"><span data-stu-id="7b89c-119">-   PublicKey</span></span><br /><span data-ttu-id="7b89c-120">-Беареркэй</span><span class="sxs-lookup"><span data-stu-id="7b89c-120">-   BearerKey</span></span><br /><br /> <span data-ttu-id="7b89c-121">Значение по умолчанию - SymmetricKey.</span><span class="sxs-lookup"><span data-stu-id="7b89c-121">The default is SymmetricKey.</span></span> <span data-ttu-id="7b89c-122">Это атрибут типа <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span><span class="sxs-lookup"><span data-stu-id="7b89c-122">This attribute is of type <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span></span>|  
|`issuedTokenType`|<span data-ttu-id="7b89c-123">Универсальный код ресурса (URI), который задает тип выдаваемых маркеров.</span><span class="sxs-lookup"><span data-stu-id="7b89c-123">A URI that specifies the type of token to be issued.</span></span> <span data-ttu-id="7b89c-124">Значение по умолчанию — `null`.</span><span class="sxs-lookup"><span data-stu-id="7b89c-124">The default is `null`.</span></span>|  
|`negotiateServiceCredential`|<span data-ttu-id="7b89c-125">Значение, которое определяет, должен ли проводиться обмен учетными данными службы в рамках процесса согласования, или эти данные доступны вне диапазона.</span><span class="sxs-lookup"><span data-stu-id="7b89c-125">A value that specifies whether the service credential should be exchanged as part of negotiation or is available out of band.</span></span> <span data-ttu-id="7b89c-126">Значением по умолчанию является `true`, означающее, что учетные данные службы согласуются.</span><span class="sxs-lookup"><span data-stu-id="7b89c-126">The default is `true`, which means that the service credential is negotiated.</span></span>|  
  
## <a name="algorithmsuite-attribute"></a><span data-ttu-id="7b89c-127">Атрибут algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="7b89c-127">algorithmSuite Attribute</span></span>  
  
|<span data-ttu-id="7b89c-128">Значение</span><span class="sxs-lookup"><span data-stu-id="7b89c-128">Value</span></span>|<span data-ttu-id="7b89c-129">Описание</span><span class="sxs-lookup"><span data-stu-id="7b89c-129">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7b89c-130">Basic128</span><span class="sxs-lookup"><span data-stu-id="7b89c-130">Basic128</span></span>|<span data-ttu-id="7b89c-131">Используется шифрование Aes128, Sha1 для хэша и Rsa-oaep-mgf1p для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="7b89c-131">Use Aes128 encryption, Sha1 for message digest, and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="7b89c-132">Basic192</span><span class="sxs-lookup"><span data-stu-id="7b89c-132">Basic192</span></span>|<span data-ttu-id="7b89c-133">Используется шифрование Aes192, Sha1 для хэша и Rsa-oaep-mgf1p для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="7b89c-133">Use Aes192 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="7b89c-134">Basic256</span><span class="sxs-lookup"><span data-stu-id="7b89c-134">Basic256</span></span>|<span data-ttu-id="7b89c-135">Используется шифрование Aes256, Sha1 для хэш-кода и Rsa-oaep-mgf1p для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="7b89c-135">Use Aes256 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="7b89c-136">Basic256Rsa15</span><span class="sxs-lookup"><span data-stu-id="7b89c-136">Basic256Rsa15</span></span>|<span data-ttu-id="7b89c-137">Используется Aes256 для шифрования сообщения, Sha1 для хэш-кода и Rsa15 для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="7b89c-137">Use Aes256 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="7b89c-138">Basic192Rsa15</span><span class="sxs-lookup"><span data-stu-id="7b89c-138">Basic192Rsa15</span></span>|<span data-ttu-id="7b89c-139">Используется Aes192 для шифрования сообщения, Sha1 для хэш-кода и Rsa15 для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="7b89c-139">Use Aes192 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="7b89c-140">TripleDes</span><span class="sxs-lookup"><span data-stu-id="7b89c-140">TripleDes</span></span>|<span data-ttu-id="7b89c-141">Используется шифрование TripleDes, Sha1 для хэш-кода и Rsa-oaep-mgf1p для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="7b89c-141">Use TripleDes encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="7b89c-142">Basic128Rsa15</span><span class="sxs-lookup"><span data-stu-id="7b89c-142">Basic128Rsa15</span></span>|<span data-ttu-id="7b89c-143">Используется Aes128 для шифрования сообщения, Sha1 для хэш-кода и Rsa15 для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="7b89c-143">Use Aes128 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="7b89c-144">TripleDesRsa15</span><span class="sxs-lookup"><span data-stu-id="7b89c-144">TripleDesRsa15</span></span>|<span data-ttu-id="7b89c-145">Используется TripleDes для шифрования сообщения, Sha1 для хэш-кода и Rsa15 для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="7b89c-145">Use TripleDes encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="7b89c-146">Basic128Sha256</span><span class="sxs-lookup"><span data-stu-id="7b89c-146">Basic128Sha256</span></span>|<span data-ttu-id="7b89c-147">Используется Aes256 для шифрования сообщения, Sha256 для хэша и Rsa-oaep-mgf1p для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="7b89c-147">Use Aes256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="7b89c-148">Basic192Sha256</span><span class="sxs-lookup"><span data-stu-id="7b89c-148">Basic192Sha256</span></span>|<span data-ttu-id="7b89c-149">Используется Aes192 для шифрования сообщения, Sha256 для хэш-кода и Rsa-oaep-mgf1p для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="7b89c-149">Use Aes192 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="7b89c-150">Basic256Sha256</span><span class="sxs-lookup"><span data-stu-id="7b89c-150">Basic256Sha256</span></span>|<span data-ttu-id="7b89c-151">Используется Aes256 для шифрования сообщения, Sha256 для хэша и Rsa-oaep-mgf1p для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="7b89c-151">Use Aes256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="7b89c-152">TripleDesSha256</span><span class="sxs-lookup"><span data-stu-id="7b89c-152">TripleDesSha256</span></span>|<span data-ttu-id="7b89c-153">Используется TripleDes для шифрования сообщения, Sha256 для хэш-кода и Rsa-oaep-mgf1p для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="7b89c-153">Use TripleDes for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="7b89c-154">Basic128Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="7b89c-154">Basic128Sha256Rsa15</span></span>|<span data-ttu-id="7b89c-155">Используется Aes128 для шифрования сообщения, Sha256 для хэш-кода и Rsa15 для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="7b89c-155">Use Aes128 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="7b89c-156">Basic192Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="7b89c-156">Basic192Sha256Rsa15</span></span>|<span data-ttu-id="7b89c-157">Используется Aes192 для шифрования сообщения, Sha256 для хэш-кода и Rsa15 для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="7b89c-157">Use Aes192 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="7b89c-158">Basic256Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="7b89c-158">Basic256Sha256Rsa15</span></span>|<span data-ttu-id="7b89c-159">Используется Aes256 для шифрования сообщения, Sha256 для хэша и Rsa15 для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="7b89c-159">Use Aes256 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="7b89c-160">TripleDesSha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="7b89c-160">TripleDesSha256Rsa15</span></span>|<span data-ttu-id="7b89c-161">Используется TripleDes для шифрования сообщения, Sha256 для хэш-кода и Rsa15 для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="7b89c-161">Use TripleDes for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7b89c-162">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="7b89c-162">Child Elements</span></span>  
  
|<span data-ttu-id="7b89c-163">Элемент</span><span class="sxs-lookup"><span data-stu-id="7b89c-163">Element</span></span>|<span data-ttu-id="7b89c-164">Описание</span><span class="sxs-lookup"><span data-stu-id="7b89c-164">Description</span></span>|  
|-------------|-----------------|  
|[\<claimTypeRequirements>](claimtyperequirements-element.md)|<span data-ttu-id="7b89c-165">Задает коллекцию типов утверждений для этой привязки.</span><span class="sxs-lookup"><span data-stu-id="7b89c-165">Specifies a collection of claim types for this binding.</span></span> <span data-ttu-id="7b89c-166">Каждый элемент имеет тип <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="7b89c-166">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span>|  
|[\<issuer>](issuer.md)|<span data-ttu-id="7b89c-167">Задает конечную точку, которая выдает маркер безопасности.</span><span class="sxs-lookup"><span data-stu-id="7b89c-167">Specifies an endpoint that issues a security token.</span></span> <span data-ttu-id="7b89c-168">Это элемент типа <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span><span class="sxs-lookup"><span data-stu-id="7b89c-168">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span></span>|  
|[\<issuerMetadata>](issuermetadata.md)|<span data-ttu-id="7b89c-169">Задает адрес конечной точки издателя.</span><span class="sxs-lookup"><span data-stu-id="7b89c-169">Specifies the endpoint address of the issuer.</span></span>|  
|[\<tokenRequestParameters>](tokenrequestparameters.md)|<span data-ttu-id="7b89c-170">Коллекция параметров запроса маркера.</span><span class="sxs-lookup"><span data-stu-id="7b89c-170">A collection of token request parameters.</span></span> <span data-ttu-id="7b89c-171">Каждый параметр представляет собой элемент XML.</span><span class="sxs-lookup"><span data-stu-id="7b89c-171">Each parameter is an XML element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7b89c-172">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="7b89c-172">Parent Elements</span></span>  
  
|<span data-ttu-id="7b89c-173">Элемент</span><span class="sxs-lookup"><span data-stu-id="7b89c-173">Element</span></span>|<span data-ttu-id="7b89c-174">Описание</span><span class="sxs-lookup"><span data-stu-id="7b89c-174">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-element-of-ws2007federationhttpbinding.md)|<span data-ttu-id="7b89c-175">Определяет параметры безопасности для привязки.</span><span class="sxs-lookup"><span data-stu-id="7b89c-175">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7b89c-176">См. также</span><span class="sxs-lookup"><span data-stu-id="7b89c-176">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement.Message%2A>
- <xref:System.ServiceModel.WSFederationHttpSecurity.Message%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>
- [<span data-ttu-id="7b89c-177">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="7b89c-177">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="7b89c-178">Привязки</span><span class="sxs-lookup"><span data-stu-id="7b89c-178">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="7b89c-179">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="7b89c-179">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="7b89c-180">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="7b89c-180">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
