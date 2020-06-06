---
title: Элемент <message> для <wsFederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: 9d710389-d9d8-4454-9bf2-da4ccda31cec
ms.openlocfilehash: 8e0903dd1313e68e2de65730e129079199ebe2f2
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "73738979"
---
# <a name="message-element-of-wsfederationhttpbinding"></a><span data-ttu-id="04285-102">Элемент \<message> для \<wsFederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="04285-102">\<message> element of \<wsFederationHttpBinding></span></span>
<span data-ttu-id="04285-103">Определяет параметры безопасности на уровне сообщений для [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="04285-103">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](wsfederationhttpbinding.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<message>**  
  
## <a name="syntax"></a><span data-ttu-id="04285-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="04285-104">Syntax</span></span>  
  
```xml  
<wsFederationBinding>
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
</wsFederationBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="04285-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="04285-105">Attributes and Elements</span></span>  
 <span data-ttu-id="04285-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="04285-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="04285-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="04285-107">Attributes</span></span>  
  
|<span data-ttu-id="04285-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="04285-108">Attribute</span></span>|<span data-ttu-id="04285-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="04285-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="04285-110">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="04285-110">algorithmSuite</span></span>|<span data-ttu-id="04285-111">Задает алгоритмы шифрования сообщений и ключей.</span><span class="sxs-lookup"><span data-stu-id="04285-111">Sets the message encryption and key-wrap algorithms.</span></span> <span data-ttu-id="04285-112">Допустимые значения этого атрибута см. в таблице «Атрибут algorithmSuite».</span><span class="sxs-lookup"><span data-stu-id="04285-112">See the "algorithmSuite attribute" table for valid values of this attribute.</span></span> <span data-ttu-id="04285-113">Значение по умолчанию — `Basic256`.</span><span class="sxs-lookup"><span data-stu-id="04285-113">The default value is `Basic256`.</span></span><br /><br /> <span data-ttu-id="04285-114">Это атрибут типа <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span><span class="sxs-lookup"><span data-stu-id="04285-114">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span></span> <span data-ttu-id="04285-115">Эти алгоритмы соответствуют алгоритмам, заданным в спецификации языка политики безопасности (WS-SecurityPolicy).</span><span class="sxs-lookup"><span data-stu-id="04285-115">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span>|  
|<span data-ttu-id="04285-116">issuedKeyType</span><span class="sxs-lookup"><span data-stu-id="04285-116">issuedKeyType</span></span>|<span data-ttu-id="04285-117">Задает тип выдаваемого ключа.</span><span class="sxs-lookup"><span data-stu-id="04285-117">Specifies the type of key to be issued.</span></span> <span data-ttu-id="04285-118">Допустимые значения.</span><span class="sxs-lookup"><span data-stu-id="04285-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="04285-119">-SymmetricKey</span><span class="sxs-lookup"><span data-stu-id="04285-119">-   SymmetricKey</span></span><br /><span data-ttu-id="04285-120">-PublicKey</span><span class="sxs-lookup"><span data-stu-id="04285-120">-   PublicKey</span></span><br /><br /> <span data-ttu-id="04285-121">Значение по умолчанию — `SymmetricKey`.</span><span class="sxs-lookup"><span data-stu-id="04285-121">The default is `SymmetricKey`.</span></span> <span data-ttu-id="04285-122">Это атрибут типа <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span><span class="sxs-lookup"><span data-stu-id="04285-122">This attribute is of type <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span></span>|  
|<span data-ttu-id="04285-123">issuedTokenType</span><span class="sxs-lookup"><span data-stu-id="04285-123">issuedTokenType</span></span>|<span data-ttu-id="04285-124">Строка, содержащая универсальный код ресурса (URI), который задает тип выдаваемых маркеров.</span><span class="sxs-lookup"><span data-stu-id="04285-124">A string that contains a URI that specifies the type of token to be issued.</span></span> <span data-ttu-id="04285-125">Значение по умолчанию — `null`.</span><span class="sxs-lookup"><span data-stu-id="04285-125">The default is `null`.</span></span>|  
|<span data-ttu-id="04285-126">negotiateServiceCredential</span><span class="sxs-lookup"><span data-stu-id="04285-126">negotiateServiceCredential</span></span>|<span data-ttu-id="04285-127">Логическое значение, которое определяет, должен ли проводиться обмен учетными данными службы в рамках процесса согласования, или допустимо использование внештатного канала.</span><span class="sxs-lookup"><span data-stu-id="04285-127">A Boolean value that specifies whether the service credential should be exchanged as part of negotiation or is available out of band.</span></span> <span data-ttu-id="04285-128">Значением по умолчанию является `true`, означающее, что учетные данные службы согласуются.</span><span class="sxs-lookup"><span data-stu-id="04285-128">The default is `true`, which means that the service credential is negotiated.</span></span>|  
  
## <a name="algorithmsuite-attribute"></a><span data-ttu-id="04285-129">Атрибут algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="04285-129">algorithmSuite Attribute</span></span>  
  
|<span data-ttu-id="04285-130">Значение</span><span class="sxs-lookup"><span data-stu-id="04285-130">Value</span></span>|<span data-ttu-id="04285-131">Описание</span><span class="sxs-lookup"><span data-stu-id="04285-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="04285-132">Basic128</span><span class="sxs-lookup"><span data-stu-id="04285-132">Basic128</span></span>|<span data-ttu-id="04285-133">Используется шифрование Basic128, Sha1 для хэш-кода и Rsa-oaep-mgf1p для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="04285-133">Use Basic128 encryption, Sha1 for message digest, and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="04285-134">Basic192</span><span class="sxs-lookup"><span data-stu-id="04285-134">Basic192</span></span>|<span data-ttu-id="04285-135">Используется шифрование Basic192, Sha1 для хэш-кода и Rsa-oaep-mgf1p для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="04285-135">Use Basic192 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="04285-136">Basic256</span><span class="sxs-lookup"><span data-stu-id="04285-136">Basic256</span></span>|<span data-ttu-id="04285-137">Используется шифрование Basic256, Sha1 для хэш-кода и Rsa-oaep-mgf1p для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="04285-137">Use Basic256 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="04285-138">Basic256Rsa15</span><span class="sxs-lookup"><span data-stu-id="04285-138">Basic256Rsa15</span></span>|<span data-ttu-id="04285-139">Используется Basic256 для шифрования сообщения, Sha1 для хэш-кода и Rsa15 для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="04285-139">Use Basic256 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="04285-140">Basic192Rsa15</span><span class="sxs-lookup"><span data-stu-id="04285-140">Basic192Rsa15</span></span>|<span data-ttu-id="04285-141">Используется Basic192 для шифрования сообщения, Sha1 для хэш-кода и Rsa15 для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="04285-141">Use Basic192 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="04285-142">TripleDes</span><span class="sxs-lookup"><span data-stu-id="04285-142">TripleDes</span></span>|<span data-ttu-id="04285-143">Используется шифрование TripleDes, Sha1 для хэш-кода и Rsa-oaep-mgf1p для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="04285-143">Use TripleDes encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="04285-144">Basic128Rsa15</span><span class="sxs-lookup"><span data-stu-id="04285-144">Basic128Rsa15</span></span>|<span data-ttu-id="04285-145">Используется Basic128 для шифрования сообщения, Sha1 для хэш-кода и Rsa15 для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="04285-145">Use Basic128 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="04285-146">TripleDesRsa15</span><span class="sxs-lookup"><span data-stu-id="04285-146">TripleDesRsa15</span></span>|<span data-ttu-id="04285-147">Используется TripleDes для шифрования сообщения, Sha1 для хэш-кода и Rsa15 для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="04285-147">Use TripleDes encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="04285-148">Basic128Sha256</span><span class="sxs-lookup"><span data-stu-id="04285-148">Basic128Sha256</span></span>|<span data-ttu-id="04285-149">Используется Basic128 для шифрования сообщения, Sha256 для хэш-кода и Rsa-oaep-mgf1p для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="04285-149">Use Basic128 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="04285-150">Basic192Sha256</span><span class="sxs-lookup"><span data-stu-id="04285-150">Basic192Sha256</span></span>|<span data-ttu-id="04285-151">Используется Basic192 для шифрования сообщения, Sha256 для хэш-кода и Rsa-oaep-mgf1p для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="04285-151">Use Basic192 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="04285-152">Basic256Sha256</span><span class="sxs-lookup"><span data-stu-id="04285-152">Basic256Sha256</span></span>|<span data-ttu-id="04285-153">Используется Basic256 для шифрования сообщения, Sha256 для хэш-кода и Rsa-oaep-mgf1p для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="04285-153">Use Basic256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="04285-154">TripleDesSha256</span><span class="sxs-lookup"><span data-stu-id="04285-154">TripleDesSha256</span></span>|<span data-ttu-id="04285-155">Используется TripleDes для шифрования сообщения, Sha256 для хэш-кода и Rsa-oaep-mgf1p для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="04285-155">Use TripleDes for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="04285-156">Basic128Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="04285-156">Basic128Sha256Rsa15</span></span>|<span data-ttu-id="04285-157">Используется Basic128 для шифрования сообщения, Sha256 для хэш-кода и Rsa15 для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="04285-157">Use Basic128 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="04285-158">Basic192Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="04285-158">Basic192Sha256Rsa15</span></span>|<span data-ttu-id="04285-159">Используется Aes192 для шифрования сообщения, Sha256 для хэш-кода и Rsa15 для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="04285-159">Use Aes192 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="04285-160">Basic256Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="04285-160">Basic256Sha256Rsa15</span></span>|<span data-ttu-id="04285-161">Используется Basic256 для шифрования сообщения, Sha256 для хэш-кода и Rsa15 для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="04285-161">Use Basic256 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="04285-162">TripleDesSha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="04285-162">TripleDesSha256Rsa15</span></span>|<span data-ttu-id="04285-163">Используется TripleDes для шифрования сообщения, Sha256 для хэш-кода и Rsa15 для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="04285-163">Use TripleDes for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="04285-164">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="04285-164">Child Elements</span></span>  
  
|<span data-ttu-id="04285-165">Элемент</span><span class="sxs-lookup"><span data-stu-id="04285-165">Element</span></span>|<span data-ttu-id="04285-166">Описание</span><span class="sxs-lookup"><span data-stu-id="04285-166">Description</span></span>|  
|-------------|-----------------|  
|[\<claimTypeRequirements>](claimtyperequirements-element.md)|<span data-ttu-id="04285-167">Задает коллекцию типов утверждений для этой привязки.</span><span class="sxs-lookup"><span data-stu-id="04285-167">Specifies a collection of claim types for this binding.</span></span> <span data-ttu-id="04285-168">Каждый элемент имеет тип <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="04285-168">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span>|  
|<span data-ttu-id="04285-169">issuer</span><span class="sxs-lookup"><span data-stu-id="04285-169">issuer</span></span>|<span data-ttu-id="04285-170">Задает конечную точку, которая выдает маркер безопасности.</span><span class="sxs-lookup"><span data-stu-id="04285-170">Specifies an endpoint that issues a security token.</span></span> <span data-ttu-id="04285-171">Это элемент типа <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span><span class="sxs-lookup"><span data-stu-id="04285-171">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span></span>|  
|<span data-ttu-id="04285-172">issuerMetadata</span><span class="sxs-lookup"><span data-stu-id="04285-172">issuerMetadata</span></span>|<span data-ttu-id="04285-173">Задает адрес конечной точки издателя.</span><span class="sxs-lookup"><span data-stu-id="04285-173">Specifies the endpoint address of the issuer.</span></span>|  
|[\<tokenRequestParameters>](tokenrequestparameters.md)|<span data-ttu-id="04285-174">Коллекция параметров запроса маркера.</span><span class="sxs-lookup"><span data-stu-id="04285-174">A collection of token request parameters.</span></span> <span data-ttu-id="04285-175">Каждый параметр представляет собой элемент XML.</span><span class="sxs-lookup"><span data-stu-id="04285-175">Each parameter is an XML element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="04285-176">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="04285-176">Parent Elements</span></span>  
  
|<span data-ttu-id="04285-177">Элемент</span><span class="sxs-lookup"><span data-stu-id="04285-177">Element</span></span>|<span data-ttu-id="04285-178">Описание</span><span class="sxs-lookup"><span data-stu-id="04285-178">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-wsfederationhttpbinding.md)|<span data-ttu-id="04285-179">Определяет параметры безопасности для привязки.</span><span class="sxs-lookup"><span data-stu-id="04285-179">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="04285-180">См. также</span><span class="sxs-lookup"><span data-stu-id="04285-180">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement.Message%2A>
- <xref:System.ServiceModel.WSFederationHttpSecurity.Message%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>
- [<span data-ttu-id="04285-181">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="04285-181">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="04285-182">Привязки</span><span class="sxs-lookup"><span data-stu-id="04285-182">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="04285-183">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="04285-183">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="04285-184">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="04285-184">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
