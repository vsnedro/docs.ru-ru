---
title: Элемент <message> для <wsFederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: 9d710389-d9d8-4454-9bf2-da4ccda31cec
ms.openlocfilehash: ea320b1d97e742d4f90ec55502f3bd429803283d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204896"
---
# <a name="message-element-of-wsfederationhttpbinding"></a><span data-ttu-id="879ac-102">Элемент \<message> для \<wsFederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="879ac-102">\<message> element of \<wsFederationHttpBinding></span></span>

<span data-ttu-id="879ac-103">Определяет параметры безопасности на уровне сообщений для [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="879ac-103">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](wsfederationhttpbinding.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<message>**  
  
## <a name="syntax"></a><span data-ttu-id="879ac-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="879ac-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="879ac-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="879ac-105">Attributes and Elements</span></span>  

 <span data-ttu-id="879ac-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="879ac-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="879ac-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="879ac-107">Attributes</span></span>  
  
|<span data-ttu-id="879ac-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="879ac-108">Attribute</span></span>|<span data-ttu-id="879ac-109">Описание</span><span class="sxs-lookup"><span data-stu-id="879ac-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="879ac-110">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="879ac-110">algorithmSuite</span></span>|<span data-ttu-id="879ac-111">Задает алгоритмы шифрования сообщений и ключей.</span><span class="sxs-lookup"><span data-stu-id="879ac-111">Sets the message encryption and key-wrap algorithms.</span></span> <span data-ttu-id="879ac-112">Допустимые значения этого атрибута см. в таблице «Атрибут algorithmSuite».</span><span class="sxs-lookup"><span data-stu-id="879ac-112">See the "algorithmSuite attribute" table for valid values of this attribute.</span></span> <span data-ttu-id="879ac-113">Значение по умолчанию — `Basic256`.</span><span class="sxs-lookup"><span data-stu-id="879ac-113">The default value is `Basic256`.</span></span><br /><br /> <span data-ttu-id="879ac-114">Это атрибут типа <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span><span class="sxs-lookup"><span data-stu-id="879ac-114">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span></span> <span data-ttu-id="879ac-115">Эти алгоритмы соответствуют алгоритмам, заданным в спецификации языка политики безопасности (WS-SecurityPolicy).</span><span class="sxs-lookup"><span data-stu-id="879ac-115">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span>|  
|<span data-ttu-id="879ac-116">issuedKeyType</span><span class="sxs-lookup"><span data-stu-id="879ac-116">issuedKeyType</span></span>|<span data-ttu-id="879ac-117">Задает тип выдаваемого ключа.</span><span class="sxs-lookup"><span data-stu-id="879ac-117">Specifies the type of key to be issued.</span></span> <span data-ttu-id="879ac-118">Допустимые значения.</span><span class="sxs-lookup"><span data-stu-id="879ac-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="879ac-119">-SymmetricKey</span><span class="sxs-lookup"><span data-stu-id="879ac-119">-   SymmetricKey</span></span><br /><span data-ttu-id="879ac-120">-PublicKey</span><span class="sxs-lookup"><span data-stu-id="879ac-120">-   PublicKey</span></span><br /><br /> <span data-ttu-id="879ac-121">Значение по умолчанию — `SymmetricKey`.</span><span class="sxs-lookup"><span data-stu-id="879ac-121">The default is `SymmetricKey`.</span></span> <span data-ttu-id="879ac-122">Это атрибут типа <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span><span class="sxs-lookup"><span data-stu-id="879ac-122">This attribute is of type <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span></span>|  
|<span data-ttu-id="879ac-123">issuedTokenType</span><span class="sxs-lookup"><span data-stu-id="879ac-123">issuedTokenType</span></span>|<span data-ttu-id="879ac-124">Строка, содержащая универсальный код ресурса (URI), который задает тип выдаваемых маркеров.</span><span class="sxs-lookup"><span data-stu-id="879ac-124">A string that contains a URI that specifies the type of token to be issued.</span></span> <span data-ttu-id="879ac-125">Значение по умолчанию — `null`.</span><span class="sxs-lookup"><span data-stu-id="879ac-125">The default is `null`.</span></span>|  
|<span data-ttu-id="879ac-126">negotiateServiceCredential</span><span class="sxs-lookup"><span data-stu-id="879ac-126">negotiateServiceCredential</span></span>|<span data-ttu-id="879ac-127">Логическое значение, которое определяет, должен ли проводиться обмен учетными данными службы в рамках процесса согласования, или допустимо использование внештатного канала.</span><span class="sxs-lookup"><span data-stu-id="879ac-127">A Boolean value that specifies whether the service credential should be exchanged as part of negotiation or is available out of band.</span></span> <span data-ttu-id="879ac-128">Значением по умолчанию является `true`, означающее, что учетные данные службы согласуются.</span><span class="sxs-lookup"><span data-stu-id="879ac-128">The default is `true`, which means that the service credential is negotiated.</span></span>|  
  
## <a name="algorithmsuite-attribute"></a><span data-ttu-id="879ac-129">Атрибут algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="879ac-129">algorithmSuite Attribute</span></span>  
  
|<span data-ttu-id="879ac-130">Значение</span><span class="sxs-lookup"><span data-stu-id="879ac-130">Value</span></span>|<span data-ttu-id="879ac-131">Описание</span><span class="sxs-lookup"><span data-stu-id="879ac-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="879ac-132">Basic128</span><span class="sxs-lookup"><span data-stu-id="879ac-132">Basic128</span></span>|<span data-ttu-id="879ac-133">Используется шифрование Basic128, Sha1 для хэш-кода и Rsa-oaep-mgf1p для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="879ac-133">Use Basic128 encryption, Sha1 for message digest, and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="879ac-134">Basic192</span><span class="sxs-lookup"><span data-stu-id="879ac-134">Basic192</span></span>|<span data-ttu-id="879ac-135">Используется шифрование Basic192, Sha1 для хэш-кода и Rsa-oaep-mgf1p для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="879ac-135">Use Basic192 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="879ac-136">Basic256</span><span class="sxs-lookup"><span data-stu-id="879ac-136">Basic256</span></span>|<span data-ttu-id="879ac-137">Используется шифрование Basic256, Sha1 для хэш-кода и Rsa-oaep-mgf1p для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="879ac-137">Use Basic256 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="879ac-138">Basic256Rsa15</span><span class="sxs-lookup"><span data-stu-id="879ac-138">Basic256Rsa15</span></span>|<span data-ttu-id="879ac-139">Используется Basic256 для шифрования сообщения, Sha1 для хэш-кода и Rsa15 для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="879ac-139">Use Basic256 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="879ac-140">Basic192Rsa15</span><span class="sxs-lookup"><span data-stu-id="879ac-140">Basic192Rsa15</span></span>|<span data-ttu-id="879ac-141">Используется Basic192 для шифрования сообщения, Sha1 для хэш-кода и Rsa15 для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="879ac-141">Use Basic192 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="879ac-142">TripleDes</span><span class="sxs-lookup"><span data-stu-id="879ac-142">TripleDes</span></span>|<span data-ttu-id="879ac-143">Используется шифрование TripleDes, Sha1 для хэш-кода и Rsa-oaep-mgf1p для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="879ac-143">Use TripleDes encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="879ac-144">Basic128Rsa15</span><span class="sxs-lookup"><span data-stu-id="879ac-144">Basic128Rsa15</span></span>|<span data-ttu-id="879ac-145">Используется Basic128 для шифрования сообщения, Sha1 для хэш-кода и Rsa15 для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="879ac-145">Use Basic128 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="879ac-146">TripleDesRsa15</span><span class="sxs-lookup"><span data-stu-id="879ac-146">TripleDesRsa15</span></span>|<span data-ttu-id="879ac-147">Используется TripleDes для шифрования сообщения, Sha1 для хэш-кода и Rsa15 для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="879ac-147">Use TripleDes encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="879ac-148">Basic128Sha256</span><span class="sxs-lookup"><span data-stu-id="879ac-148">Basic128Sha256</span></span>|<span data-ttu-id="879ac-149">Используется Basic128 для шифрования сообщения, Sha256 для хэш-кода и Rsa-oaep-mgf1p для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="879ac-149">Use Basic128 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="879ac-150">Basic192Sha256</span><span class="sxs-lookup"><span data-stu-id="879ac-150">Basic192Sha256</span></span>|<span data-ttu-id="879ac-151">Используется Basic192 для шифрования сообщения, Sha256 для хэш-кода и Rsa-oaep-mgf1p для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="879ac-151">Use Basic192 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="879ac-152">Basic256Sha256</span><span class="sxs-lookup"><span data-stu-id="879ac-152">Basic256Sha256</span></span>|<span data-ttu-id="879ac-153">Используется Basic256 для шифрования сообщения, Sha256 для хэш-кода и Rsa-oaep-mgf1p для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="879ac-153">Use Basic256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="879ac-154">TripleDesSha256</span><span class="sxs-lookup"><span data-stu-id="879ac-154">TripleDesSha256</span></span>|<span data-ttu-id="879ac-155">Используется TripleDes для шифрования сообщения, Sha256 для хэш-кода и Rsa-oaep-mgf1p для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="879ac-155">Use TripleDes for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="879ac-156">Basic128Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="879ac-156">Basic128Sha256Rsa15</span></span>|<span data-ttu-id="879ac-157">Используется Basic128 для шифрования сообщения, Sha256 для хэш-кода и Rsa15 для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="879ac-157">Use Basic128 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="879ac-158">Basic192Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="879ac-158">Basic192Sha256Rsa15</span></span>|<span data-ttu-id="879ac-159">Используется Aes192 для шифрования сообщения, Sha256 для хэш-кода и Rsa15 для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="879ac-159">Use Aes192 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="879ac-160">Basic256Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="879ac-160">Basic256Sha256Rsa15</span></span>|<span data-ttu-id="879ac-161">Используется Basic256 для шифрования сообщения, Sha256 для хэш-кода и Rsa15 для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="879ac-161">Use Basic256 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="879ac-162">TripleDesSha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="879ac-162">TripleDesSha256Rsa15</span></span>|<span data-ttu-id="879ac-163">Используется TripleDes для шифрования сообщения, Sha256 для хэш-кода и Rsa15 для шифрования ключа.</span><span class="sxs-lookup"><span data-stu-id="879ac-163">Use TripleDes for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="879ac-164">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="879ac-164">Child Elements</span></span>  
  
|<span data-ttu-id="879ac-165">Элемент</span><span class="sxs-lookup"><span data-stu-id="879ac-165">Element</span></span>|<span data-ttu-id="879ac-166">Описание</span><span class="sxs-lookup"><span data-stu-id="879ac-166">Description</span></span>|  
|-------------|-----------------|  
|[\<claimTypeRequirements>](claimtyperequirements-element.md)|<span data-ttu-id="879ac-167">Задает коллекцию типов утверждений для этой привязки.</span><span class="sxs-lookup"><span data-stu-id="879ac-167">Specifies a collection of claim types for this binding.</span></span> <span data-ttu-id="879ac-168">Каждый элемент имеет тип <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="879ac-168">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span>|  
|<span data-ttu-id="879ac-169">issuer</span><span class="sxs-lookup"><span data-stu-id="879ac-169">issuer</span></span>|<span data-ttu-id="879ac-170">Задает конечную точку, которая выдает маркер безопасности.</span><span class="sxs-lookup"><span data-stu-id="879ac-170">Specifies an endpoint that issues a security token.</span></span> <span data-ttu-id="879ac-171">Это элемент типа <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span><span class="sxs-lookup"><span data-stu-id="879ac-171">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span></span>|  
|<span data-ttu-id="879ac-172">issuerMetadata</span><span class="sxs-lookup"><span data-stu-id="879ac-172">issuerMetadata</span></span>|<span data-ttu-id="879ac-173">Задает адрес конечной точки издателя.</span><span class="sxs-lookup"><span data-stu-id="879ac-173">Specifies the endpoint address of the issuer.</span></span>|  
|[\<tokenRequestParameters>](tokenrequestparameters.md)|<span data-ttu-id="879ac-174">Коллекция параметров запроса маркера.</span><span class="sxs-lookup"><span data-stu-id="879ac-174">A collection of token request parameters.</span></span> <span data-ttu-id="879ac-175">Каждый параметр представляет собой элемент XML.</span><span class="sxs-lookup"><span data-stu-id="879ac-175">Each parameter is an XML element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="879ac-176">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="879ac-176">Parent Elements</span></span>  
  
|<span data-ttu-id="879ac-177">Элемент</span><span class="sxs-lookup"><span data-stu-id="879ac-177">Element</span></span>|<span data-ttu-id="879ac-178">Описание</span><span class="sxs-lookup"><span data-stu-id="879ac-178">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-wsfederationhttpbinding.md)|<span data-ttu-id="879ac-179">Определяет параметры безопасности для привязки.</span><span class="sxs-lookup"><span data-stu-id="879ac-179">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="879ac-180">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="879ac-180">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement.Message%2A>
- <xref:System.ServiceModel.WSFederationHttpSecurity.Message%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>
- [<span data-ttu-id="879ac-181">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="879ac-181">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="879ac-182">Привязки</span><span class="sxs-lookup"><span data-stu-id="879ac-182">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="879ac-183">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="879ac-183">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="879ac-184">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="879ac-184">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
