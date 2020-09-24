---
title: Элемент <scopedCertificates>
ms.date: 03/30/2017
ms.assetid: c7b6fc35-d4b2-4c18-98bd-83e09591f1d3
ms.openlocfilehash: 4bee627fe186ed8dd85c118a37f59f575eb4650e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91162261"
---
# <a name="scopedcertificates-element"></a><span data-ttu-id="dc913-102">Элемент \<scopedCertificates></span><span class="sxs-lookup"><span data-stu-id="dc913-102">\<scopedCertificates> Element</span></span>

<span data-ttu-id="dc913-103">Представляет коллекцию сертификатов X.509, предоставленную конкретными службами (в области действия) для проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="dc913-103">Represents a collection of X.509 certificates provided by specific services (scoped) for authentication.</span></span> <span data-ttu-id="dc913-104">Эта коллекция обычно используется, чтобы задать сертификаты служб для служб маркеров безопасности в федеративной инфраструктуре.</span><span class="sxs-lookup"><span data-stu-id="dc913-104">This collection is typically used to specify the service certificates for Security Token Services in a federated scenario.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCertificate>**](servicecertificate-of-clientcredentials-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<scopedCertificates>**  
  
## <a name="syntax"></a><span data-ttu-id="dc913-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dc913-105">Syntax</span></span>  
  
```xml  
<scopedCertificates>
  <add findValue="String"
       storeLocation="CurrentUser/LocalMachine"
       storeName=" CurrentUser/LocalMachine"
       targetUri="string"
       x509Type="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
</scopedCertificates>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dc913-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="dc913-106">Attributes and Elements</span></span>  

 <span data-ttu-id="dc913-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="dc913-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dc913-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="dc913-108">Attributes</span></span>  

 <span data-ttu-id="dc913-109">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="dc913-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="dc913-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="dc913-110">Child Elements</span></span>  
  
|<span data-ttu-id="dc913-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="dc913-111">Element</span></span>|<span data-ttu-id="dc913-112">Описание</span><span class="sxs-lookup"><span data-stu-id="dc913-112">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-of-scopedcertificates-element.md)|<span data-ttu-id="dc913-113">Добавляет сертификат X.509 в коллекцию сертификатов в области действия.</span><span class="sxs-lookup"><span data-stu-id="dc913-113">Adds an X.509 certificate to the collection of scoped certificates.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="dc913-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="dc913-114">Parent Elements</span></span>  
  
|<span data-ttu-id="dc913-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="dc913-115">Element</span></span>|<span data-ttu-id="dc913-116">Описание</span><span class="sxs-lookup"><span data-stu-id="dc913-116">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceCertificate>](servicecertificate-of-servicecredentials.md)|<span data-ttu-id="dc913-117">Задает сертификат для использования при проверке подлинности службы для клиента.</span><span class="sxs-lookup"><span data-stu-id="dc913-117">Specifies a certificate to use when authenticating a service to the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dc913-118">Remarks</span><span class="sxs-lookup"><span data-stu-id="dc913-118">Remarks</span></span>  

 <span data-ttu-id="dc913-119">Эта коллекция позволяет клиенту настроить сертификаты служб для использования на основе URL-адреса службы, с которой он связывается.</span><span class="sxs-lookup"><span data-stu-id="dc913-119">This collection enables the client to configure the service certificates to use based on the URL of the service it communicates with.</span></span> <span data-ttu-id="dc913-120">Это особенно полезно в сценариях с выданным маркером, в которых клиент может связываться с несколькими службами (с конечной службой, а также с промежуточными службами маркеров безопасности).</span><span class="sxs-lookup"><span data-stu-id="dc913-120">This is especially useful in issued token scenarios where a client can be communicating to multiple services (the end service as well as intermediary security token services).</span></span> <span data-ttu-id="dc913-121">Для привязок, в которых используется безопасность сообщений на основе сертификатов, этот сертификат используется для шифрования сообщений службе; предполагается также, что он будет использоваться службой для подписи ответов клиенту.</span><span class="sxs-lookup"><span data-stu-id="dc913-121">For bindings that use certificate-based message security, this certificate is used to encrypt messages to the service, and is expected to be used by the service for signing replies to the client.</span></span>  
  
 <span data-ttu-id="dc913-122">Если для привязки необходим сертификат для службы, а конкретный сертификат для URL-адреса службы в элементе ScopedCertificates отсутствует, то используется сертификат по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="dc913-122">If a binding requires a certificate for the service and no specific certificate for the service URL is found in the ScopedCertificates, the default certificate is used.</span></span>  
  
 <span data-ttu-id="dc913-123">Дополнительные сведения см. в разделе «сертификаты с заданной областью» раздела [о создании федеративного клиента](../../../wcf/feature-details/how-to-create-a-federated-client.md).</span><span class="sxs-lookup"><span data-stu-id="dc913-123">For more information, see the "Scoped Certificates" section of [How to: Create a Federated Client](../../../wcf/feature-details/how-to-create-a-federated-client.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="dc913-124">Пример</span><span class="sxs-lookup"><span data-stu-id="dc913-124">Example</span></span>  

 <span data-ttu-id="dc913-125">В следующем примере задается сертификат службы, используемый клиентом при взаимодействии с конечными точками, доменное имя которых находится `http://www.contoso.com` по протоколу HTTP.</span><span class="sxs-lookup"><span data-stu-id="dc913-125">The following example specifies a service certificate for the client to use when communicating with endpoints whose domain name is `http://www.contoso.com` over the HTTP protocol.</span></span>  
  
```xml  
<serviceCertificate>
  <scopedCertificates>
    <add targetUri="http://www.contoso.com"
         findValue="www.contoso.com"
         storeLocation="LocalMachine"
         storeName="Root"
         x509FindType="FindByIssuerName" />
  </scopedCertificates>
</serviceCertificate>
```  
  
## <a name="see-also"></a><span data-ttu-id="dc913-126">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="dc913-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement.ScopedCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElementCollection>
- <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.ScopedCertificates%2A>
- [<span data-ttu-id="dc913-127">Работа с сертификатами</span><span class="sxs-lookup"><span data-stu-id="dc913-127">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="dc913-128">Практическое руководство. Создание федеративного клиента</span><span class="sxs-lookup"><span data-stu-id="dc913-128">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [\<add>](add-of-scopedcertificates-element.md)
- [<span data-ttu-id="dc913-129">Обеспечение безопасности клиентов</span><span class="sxs-lookup"><span data-stu-id="dc913-129">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="dc913-130">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="dc913-130">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
