---
title: <add> из <knownCertificates>
ms.date: 03/30/2017
ms.assetid: 128aaabe-3f1a-4c3b-b59f-898d0f02910f
ms.openlocfilehash: 453593918de15613edb801cca8a16c9dbf71aa90
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91176088"
---
# <a name="add-of-knowncertificates"></a><span data-ttu-id="8e93e-102">\<add> из \<knownCertificates></span><span class="sxs-lookup"><span data-stu-id="8e93e-102">\<add> of \<knownCertificates></span></span>

<span data-ttu-id="8e93e-103">Добавляет сертификат X.509 в коллекцию известных сертификатов.</span><span class="sxs-lookup"><span data-stu-id="8e93e-103">Adds an X.509 certificate to the collection of known certificates.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedTokenAuthentication>**](issuedtokenauthentication-of-servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<knownCertificates>**](knowncertificates.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="8e93e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8e93e-104">Syntax</span></span>  
  
```xml  
<knownCertificates>
   <add findValue="String"
      storeLocation="CurrentUser/LocalMachine"
      storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
      x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"/>
</knownCertificates>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8e93e-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="8e93e-105">Attributes and Elements</span></span>  

 <span data-ttu-id="8e93e-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="8e93e-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8e93e-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="8e93e-107">Attributes</span></span>  
  
|<span data-ttu-id="8e93e-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="8e93e-108">Attribute</span></span>|<span data-ttu-id="8e93e-109">Описание</span><span class="sxs-lookup"><span data-stu-id="8e93e-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8e93e-110">findValue</span><span class="sxs-lookup"><span data-stu-id="8e93e-110">findValue</span></span>|<span data-ttu-id="8e93e-111">Строка.</span><span class="sxs-lookup"><span data-stu-id="8e93e-111">String.</span></span> <span data-ttu-id="8e93e-112">Значение, которое нужно найти.</span><span class="sxs-lookup"><span data-stu-id="8e93e-112">The value to search for.</span></span>|  
|<span data-ttu-id="8e93e-113">storeLocation</span><span class="sxs-lookup"><span data-stu-id="8e93e-113">storeLocation</span></span>|<span data-ttu-id="8e93e-114">Перечисление.</span><span class="sxs-lookup"><span data-stu-id="8e93e-114">Enumeration.</span></span> <span data-ttu-id="8e93e-115">Одно из двух местоположений хранилища, где следует проводить поиск.</span><span class="sxs-lookup"><span data-stu-id="8e93e-115">One of the two store locations to search.</span></span>|  
|<span data-ttu-id="8e93e-116">storeName</span><span class="sxs-lookup"><span data-stu-id="8e93e-116">storeName</span></span>|<span data-ttu-id="8e93e-117">Перечисление.</span><span class="sxs-lookup"><span data-stu-id="8e93e-117">Enumeration.</span></span> <span data-ttu-id="8e93e-118">Одно из системных хранилищ, где следует проводить поиск.</span><span class="sxs-lookup"><span data-stu-id="8e93e-118">One of the system stores to search.</span></span>|  
|<span data-ttu-id="8e93e-119">x509FindType</span><span class="sxs-lookup"><span data-stu-id="8e93e-119">x509FindType</span></span>|<span data-ttu-id="8e93e-120">Перечисление.</span><span class="sxs-lookup"><span data-stu-id="8e93e-120">Enumeration.</span></span> <span data-ttu-id="8e93e-121">Одно из полей сертификата, где следует проводить поиск.</span><span class="sxs-lookup"><span data-stu-id="8e93e-121">One of the certificate fields to search.</span></span>|  
  
## <a name="findvalue-attribute"></a><span data-ttu-id="8e93e-122">Атрибут findValue</span><span class="sxs-lookup"><span data-stu-id="8e93e-122">findValue Attribute</span></span>  
  
|<span data-ttu-id="8e93e-123">Значение</span><span class="sxs-lookup"><span data-stu-id="8e93e-123">Value</span></span>|<span data-ttu-id="8e93e-124">Описание</span><span class="sxs-lookup"><span data-stu-id="8e93e-124">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8e93e-125">Строка</span><span class="sxs-lookup"><span data-stu-id="8e93e-125">String</span></span>|<span data-ttu-id="8e93e-126">Значение зависит от поля (заданного атрибутом x509FindType), поиск которого выполняется.</span><span class="sxs-lookup"><span data-stu-id="8e93e-126">The value depends on the field (specified by the X509FindType attribute) being searched.</span></span> <span data-ttu-id="8e93e-127">Например, при поиске отпечатка значение должно быть строкой шестнадцатеричных чисел.</span><span class="sxs-lookup"><span data-stu-id="8e93e-127">For example, if searching for a thumbprint, the value must be a string of hexadecimal numbers.</span></span>|  
  
## <a name="x509findtype-attribute"></a><span data-ttu-id="8e93e-128">Атрибут x509FindType</span><span class="sxs-lookup"><span data-stu-id="8e93e-128">x509FindType Attribute</span></span>  
  
|<span data-ttu-id="8e93e-129">Значение</span><span class="sxs-lookup"><span data-stu-id="8e93e-129">Value</span></span>|<span data-ttu-id="8e93e-130">Описание</span><span class="sxs-lookup"><span data-stu-id="8e93e-130">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8e93e-131">Перечисление</span><span class="sxs-lookup"><span data-stu-id="8e93e-131">Enumeration</span></span>|<span data-ttu-id="8e93e-132">К числу значений относятся следующие: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span><span class="sxs-lookup"><span data-stu-id="8e93e-132">Values include: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span></span>|  
  
## <a name="storelocation-attribute"></a><span data-ttu-id="8e93e-133">Атрибут storeLocation</span><span class="sxs-lookup"><span data-stu-id="8e93e-133">storeLocation Attribute</span></span>  
  
|<span data-ttu-id="8e93e-134">Значение</span><span class="sxs-lookup"><span data-stu-id="8e93e-134">Value</span></span>|<span data-ttu-id="8e93e-135">Описание</span><span class="sxs-lookup"><span data-stu-id="8e93e-135">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8e93e-136">Перечисление</span><span class="sxs-lookup"><span data-stu-id="8e93e-136">Enumeration</span></span>|<span data-ttu-id="8e93e-137">CurrentUser или LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="8e93e-137">CurrentUser or LocalMachine.</span></span>|  
  
## <a name="storename-attribute"></a><span data-ttu-id="8e93e-138">Атрибут storeName</span><span class="sxs-lookup"><span data-stu-id="8e93e-138">storeName Attribute</span></span>  
  
|<span data-ttu-id="8e93e-139">Значение</span><span class="sxs-lookup"><span data-stu-id="8e93e-139">Value</span></span>|<span data-ttu-id="8e93e-140">Описание</span><span class="sxs-lookup"><span data-stu-id="8e93e-140">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8e93e-141">Перечисление</span><span class="sxs-lookup"><span data-stu-id="8e93e-141">Enumeration</span></span>|<span data-ttu-id="8e93e-142">К числу значений относятся следующие: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople и TrustedPublisher.</span><span class="sxs-lookup"><span data-stu-id="8e93e-142">Values include: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, and TrustedPublisher.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8e93e-143">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8e93e-143">Child Elements</span></span>  

 <span data-ttu-id="8e93e-144">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="8e93e-144">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8e93e-145">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="8e93e-145">Parent Elements</span></span>  
  
|<span data-ttu-id="8e93e-146">Элемент</span><span class="sxs-lookup"><span data-stu-id="8e93e-146">Element</span></span>|<span data-ttu-id="8e93e-147">Описание</span><span class="sxs-lookup"><span data-stu-id="8e93e-147">Description</span></span>|  
|-------------|-----------------|  
|[\<knownCertificates>](knowncertificates.md)|<span data-ttu-id="8e93e-148">Представляет коллекцию сертификатов X.509, предоставленную службой STS для проверки маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="8e93e-148">Represents a collection of X.509 certificates that are provided by a Security Token Service (STS) for validation of security tokens.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8e93e-149">Remarks</span><span class="sxs-lookup"><span data-stu-id="8e93e-149">Remarks</span></span>  

 <span data-ttu-id="8e93e-150">В сценарии с выданным маркером имеется три этапа.</span><span class="sxs-lookup"><span data-stu-id="8e93e-150">The issued token scenario has three stages.</span></span> <span data-ttu-id="8e93e-151">На первом этапе клиент, пытающийся получить доступ к службе, ссылается на *службу маркеров безопасности*.</span><span class="sxs-lookup"><span data-stu-id="8e93e-151">In the first stage, a client trying to access a service is referred to a *secure token service*.</span></span> <span data-ttu-id="8e93e-152">Затем служба маркеров безопасности проводит проверку подлинности клиента и выдает клиенту маркер, обычно на языке Security Assertions Markup Language (SAML).</span><span class="sxs-lookup"><span data-stu-id="8e93e-152">The secure token service then authenticates the client and subsequently issues the client a token, typically a Security Assertions Markup Language (SAML) token.</span></span> <span data-ttu-id="8e93e-153">После этого клиент возвращается к службе с этим маркером.</span><span class="sxs-lookup"><span data-stu-id="8e93e-153">The client then returns to the service with the token.</span></span> <span data-ttu-id="8e93e-154">Служба проверяет наличие в маркере данных, позволяющих проверить подлинность маркера и, соответственно, самого клиента.</span><span class="sxs-lookup"><span data-stu-id="8e93e-154">The service examines the token for data that allows the service to authenticate the token and therefore the client.</span></span> <span data-ttu-id="8e93e-155">Для проверки подлинности маркера сертификат, используемый службой маркеров безопасности, должен быть известен службе.</span><span class="sxs-lookup"><span data-stu-id="8e93e-155">To authenticate the token, the certificate the secure token service uses must be known to the service.</span></span>  
  
 <span data-ttu-id="8e93e-156">[\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md)Элемент является репозиторием для всех таких сертификатов службы безопасных маркеров.</span><span class="sxs-lookup"><span data-stu-id="8e93e-156">The [\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md) element is the repository for any such secure token service certificates.</span></span> <span data-ttu-id="8e93e-157">Чтобы добавить сертификаты, используйте [\<knownCertificates>](knowncertificates.md) .</span><span class="sxs-lookup"><span data-stu-id="8e93e-157">To add certificates, use the [\<knownCertificates>](knowncertificates.md).</span></span> <span data-ttu-id="8e93e-158">Вставьте [ \<add> \<knownCertificates> элемент element](add-of-knowncertificates.md) для каждого сертификата, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="8e93e-158">Insert an [\<add> element \<knownCertificates> Element](add-of-knowncertificates.md) for each certificate, as shown in the following example.</span></span>  
  
```xml  
<issuedTokenAuthentication>
  <knownCertificates>
    <add findValue="www.contoso.com"
         storeLocation="LocalMachine"
         storeName="My"
         X509FindType="FindBySubjectName" />
  </knownCertificates>
</issuedTokenAuthentication>
```  
  
 <span data-ttu-id="8e93e-159">По умолчанию сертификаты должны быть получены от службы маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="8e93e-159">By default, the certificates must be obtained from a secure token service.</span></span> <span data-ttu-id="8e93e-160">Эти "известные" сертификаты гарантируют, что доступ к службе могут получить только допустимые клиенты.</span><span class="sxs-lookup"><span data-stu-id="8e93e-160">These "known" certificates ensure that only legitimate clients can access a service.</span></span>  
  
 <span data-ttu-id="8e93e-161">Чтобы просмотреть условия, необходимые для проверки подлинности клиента в Федеративной службе, а также дополнительные сведения об использовании этого элемента конфигурации, см. раздел [как настроить учетные данные на служба федерации](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span><span class="sxs-lookup"><span data-stu-id="8e93e-161">To review conditions required for a client to be authenticated by a federated service, as well as more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span> <span data-ttu-id="8e93e-162">Дополнительные сведения о федеративных сценариях см. в разделе [Федерация и выданные токены](../../../wcf/feature-details/federation-and-issued-tokens.md).</span><span class="sxs-lookup"><span data-stu-id="8e93e-162">For more information about federated scenarios, see [Federation and Issued Tokens](../../../wcf/feature-details/federation-and-issued-tokens.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8e93e-163">Пример</span><span class="sxs-lookup"><span data-stu-id="8e93e-163">Example</span></span>  

 <span data-ttu-id="8e93e-164">В следующем примере демонстрируется добавление сертификата в хранилище сертификатов службы STS.</span><span class="sxs-lookup"><span data-stu-id="8e93e-164">The following example adds certificate to the repository for any STS certificates.</span></span>  
  
```xml  
<serviceBehaviors>
  <behavior name="myServiceBehavior">
    <serviceCredentials>
      <issuedTokenAuthentication>
        <knownCertificates>
          <add findValue="www.contoso.com"
               storeLocation="LocalMachine"
               storeName="CertificateAuthority"
               x509FindType="FindByIssuerName" />
        </knownCertificates>
      </issuedTokenAuthentication>
    </serviceCredentials>
  </behavior>
</serviceBehaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="8e93e-165">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="8e93e-165">See also</span></span>

- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.KnownCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElementCollection>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement>
- <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A>
- [\<knownCertificates>](knowncertificates.md)
- [<span data-ttu-id="8e93e-166">Работа с сертификатами</span><span class="sxs-lookup"><span data-stu-id="8e93e-166">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="8e93e-167">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="8e93e-167">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="8e93e-168">Практическое руководство. Настройка учетных данных службы федерации</span><span class="sxs-lookup"><span data-stu-id="8e93e-168">How to: Configure Credentials on a Federation Service</span></span>](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
- [<span data-ttu-id="8e93e-169">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="8e93e-169">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
