---
title: <knownCertificates>
ms.date: 03/30/2017
ms.assetid: 678e21b4-6493-47c3-8359-fcf0d37e2138
ms.openlocfilehash: 7ddb292b8f0ffe38133c7f142be751a87d2be11c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91150912"
---
# \<knownCertificates>

<span data-ttu-id="ab7c4-101">Представляет коллекцию сертификатов X.509, которые предоставляются для проверки подлинности учетных данных безопасности, выданных службой маркеров безопасности (STS).</span><span class="sxs-lookup"><span data-stu-id="ab7c4-101">Represents a collection of X.509 certificates that are provided to authenticate security credentials issued from a Security Token Service (STS).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedTokenAuthentication>**](issuedtokenauthentication-of-servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<knownCertificates>**  
  
## <a name="syntax"></a><span data-ttu-id="ab7c4-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ab7c4-102">Syntax</span></span>  
  
```xml  
<knownCertificates>
  <add findValue="String"
       storeLocation="CurrentUser/LocalMachine"
       storeName=" CurrentUser/LocalMachine"
       x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
</knownCertificates>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ab7c4-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ab7c4-103">Attributes and Elements</span></span>  

 <span data-ttu-id="ab7c4-104">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ab7c4-104">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ab7c4-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ab7c4-105">Attributes</span></span>  

 <span data-ttu-id="ab7c4-106">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="ab7c4-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ab7c4-107">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ab7c4-107">Child Elements</span></span>  
  
|<span data-ttu-id="ab7c4-108">Элемент</span><span class="sxs-lookup"><span data-stu-id="ab7c4-108">Element</span></span>|<span data-ttu-id="ab7c4-109">Описание</span><span class="sxs-lookup"><span data-stu-id="ab7c4-109">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-of-knowncertificates.md)|<span data-ttu-id="ab7c4-110">Добавляет сертификат X.509 в коллекцию.</span><span class="sxs-lookup"><span data-stu-id="ab7c4-110">Adds an X.509 certificate to the collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ab7c4-111">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ab7c4-111">Parent Elements</span></span>  
  
|<span data-ttu-id="ab7c4-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="ab7c4-112">Element</span></span>|<span data-ttu-id="ab7c4-113">Описание</span><span class="sxs-lookup"><span data-stu-id="ab7c4-113">Description</span></span>|  
|-------------|-----------------|  
|[\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="ab7c4-114">Задает маркер, выданный в качестве учетных данных службы.</span><span class="sxs-lookup"><span data-stu-id="ab7c4-114">Specifies a token issued as a service credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ab7c4-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="ab7c4-115">Remarks</span></span>  

 <span data-ttu-id="ab7c4-116">В сценарии с выданным маркером имеется три этапа.</span><span class="sxs-lookup"><span data-stu-id="ab7c4-116">The issued token scenario has three stages.</span></span> <span data-ttu-id="ab7c4-117">На первом этапе клиент, пытающийся получить доступ к службе, ссылается на *службу маркеров безопасности*.</span><span class="sxs-lookup"><span data-stu-id="ab7c4-117">In the first stage, a client trying to access a service is referred to a *secure token service*.</span></span> <span data-ttu-id="ab7c4-118">Затем служба маркеров безопасности проводит проверку подлинности клиента и выдает клиенту маркер, обычно на языке Security Assertions Markup Language (SAML).</span><span class="sxs-lookup"><span data-stu-id="ab7c4-118">The secure token service then authenticates the client and subsequently issues the client a token, typically a Security Assertions Markup Language (SAML) token.</span></span> <span data-ttu-id="ab7c4-119">После этого клиент возвращается к службе с этим маркером.</span><span class="sxs-lookup"><span data-stu-id="ab7c4-119">The client then returns to the service with the token.</span></span> <span data-ttu-id="ab7c4-120">Служба проверяет наличие в маркере данных, позволяющих проверить подлинность маркера и, соответственно, самого клиента.</span><span class="sxs-lookup"><span data-stu-id="ab7c4-120">The service examines the token for data that allows the service to authenticate the token and therefore the client.</span></span> <span data-ttu-id="ab7c4-121">Для проверки подлинности маркера сертификат, используемый службой маркеров безопасности, должен быть известен службе.</span><span class="sxs-lookup"><span data-stu-id="ab7c4-121">To authenticate the token, the certificate the secure token service uses must be known to the service.</span></span>  
  
 <span data-ttu-id="ab7c4-122">[\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md)Элемент является репозиторием для всех таких сертификатов службы безопасных маркеров.</span><span class="sxs-lookup"><span data-stu-id="ab7c4-122">The [\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md) element is the repository for any such secure token service certificates.</span></span> <span data-ttu-id="ab7c4-123">Чтобы добавить сертификаты, используйте [ \<knownCertificates> элемент](knowncertificates.md).</span><span class="sxs-lookup"><span data-stu-id="ab7c4-123">To add certificates, use the [\<knownCertificates> element](knowncertificates.md).</span></span> <span data-ttu-id="ab7c4-124">Вставьте [\<add>](add-of-knowncertificates.md) для каждого сертификата, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="ab7c4-124">Insert an [\<add>](add-of-knowncertificates.md) for each certificate, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="ab7c4-125">По умолчанию сертификаты должны быть получены от службы маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="ab7c4-125">By default, the certificates must be obtained from a secure token service.</span></span> <span data-ttu-id="ab7c4-126">Эти "известные" сертификаты гарантируют, что доступ к службе могут получить только допустимые клиенты.</span><span class="sxs-lookup"><span data-stu-id="ab7c4-126">These "known" certificates ensure that only legitimate clients can access a service.</span></span>  
  
 <span data-ttu-id="ab7c4-127">Чтобы просмотреть условия, необходимые для проверки подлинности клиента в Федеративной службе, а также дополнительные сведения об использовании этого элемента конфигурации, см. раздел [как настроить учетные данные на служба федерации](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span><span class="sxs-lookup"><span data-stu-id="ab7c4-127">To review conditions required for a client to be authenticated by a federated service, as well as more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span> <span data-ttu-id="ab7c4-128">Дополнительные сведения о федеративных сценариях см. в разделе [Федерация и выданные токены](../../../wcf/feature-details/federation-and-issued-tokens.md).</span><span class="sxs-lookup"><span data-stu-id="ab7c4-128">For more information about federated scenarios, see [Federation and Issued Tokens](../../../wcf/feature-details/federation-and-issued-tokens.md).</span></span>  
  
 <span data-ttu-id="ab7c4-129">Пример, демонстрирующий заполнение коллекции в конфигурации, см. в разделе [\<add>](add-of-knowncertificates.md) .</span><span class="sxs-lookup"><span data-stu-id="ab7c4-129">For an example that shows how to populate the collection in configuration, see [\<add>](add-of-knowncertificates.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab7c4-130">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ab7c4-130">See also</span></span>

- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.KnownCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElementCollection>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement>
- <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A>
- [\<add>](add-of-knowncertificates.md)
- [\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md)
- [<span data-ttu-id="ab7c4-131">Поведение безопасности</span><span class="sxs-lookup"><span data-stu-id="ab7c4-131">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="ab7c4-132">Практическое руководство. Настройка учетных данных службы федерации</span><span class="sxs-lookup"><span data-stu-id="ab7c4-132">How to: Configure Credentials on a Federation Service</span></span>](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
- [<span data-ttu-id="ab7c4-133">Работа с сертификатами</span><span class="sxs-lookup"><span data-stu-id="ab7c4-133">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="ab7c4-134">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="ab7c4-134">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [\<add>](add-of-knowncertificates.md)
- [<span data-ttu-id="ab7c4-135">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="ab7c4-135">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
