---
title: <serviceCertificate> элемента <clientCredentials>
ms.date: 03/30/2017
ms.assetid: e50c0ac5-f0df-4c90-b54b-fc602c1f84ea
ms.openlocfilehash: 4c7489a171bdd5cb4b747ca99f1b7ff6dd65517b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399684"
---
# <a name="servicecertificate-of-clientcredentials-element"></a><span data-ttu-id="82de7-102">\<serviceCertificate> элемента \<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="82de7-102">\<serviceCertificate> of \<clientCredentials> Element</span></span>
<span data-ttu-id="82de7-103">Задает сертификат для использования при проверке подлинности службы для клиента.</span><span class="sxs-lookup"><span data-stu-id="82de7-103">Specifies a certificate to use when authenticating a service to the client.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceCertificate>**  
  
## <a name="syntax"></a><span data-ttu-id="82de7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="82de7-104">Syntax</span></span>  
  
```xml  
<serviceCertificate />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="82de7-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="82de7-105">Attributes and Elements</span></span>  
 <span data-ttu-id="82de7-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="82de7-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="82de7-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="82de7-107">Attributes</span></span>  
 <span data-ttu-id="82de7-108">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="82de7-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="82de7-109">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="82de7-109">Child Elements</span></span>  
  
|<span data-ttu-id="82de7-110">Элемент</span><span class="sxs-lookup"><span data-stu-id="82de7-110">Element</span></span>|<span data-ttu-id="82de7-111">Описание</span><span class="sxs-lookup"><span data-stu-id="82de7-111">Description</span></span>|  
|-------------|-----------------|  
|[\<defaultCertificate>](defaultcertificate-element.md)|<span data-ttu-id="82de7-112">Задает сертификат X.509 для использования, когда служба или служба маркеров безопасности не предоставляет сертификат посредством протокола согласования.</span><span class="sxs-lookup"><span data-stu-id="82de7-112">Specifies an X.509 certificate to be used when a service or STS does not provide one via a negotiation protocol.</span></span>|  
|[\<scopedCertificates>](scopedcertificates-element.md)|<span data-ttu-id="82de7-113">Представляет коллекцию сертификатов X.509, предоставленную конкретными службами (в области действия) для проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="82de7-113">Represents a collection of X.509 certificates provided by specific services (scoped) for authentication.</span></span> <span data-ttu-id="82de7-114">Эта коллекция обычно используется, чтобы задать сертификаты служб для служб маркеров безопасности в федеративной инфраструктуре.</span><span class="sxs-lookup"><span data-stu-id="82de7-114">This collection is typically used to specify the service certificates for Security Token Services in a federated scenario.</span></span>|  
|[\<authentication>](authentication-of-servicecertificate-element.md)|<span data-ttu-id="82de7-115">Задает поведение проверки подлинности для сертификатов служб, используемых клиентом.</span><span class="sxs-lookup"><span data-stu-id="82de7-115">Specifies authentication behaviors for service certificates used by a client.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="82de7-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="82de7-116">Parent Elements</span></span>  
  
|<span data-ttu-id="82de7-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="82de7-117">Element</span></span>|<span data-ttu-id="82de7-118">Описание</span><span class="sxs-lookup"><span data-stu-id="82de7-118">Description</span></span>|  
|-------------|-----------------|  
|[\<clientCredentials>](clientcredentials.md)|<span data-ttu-id="82de7-119">Задает учетные данные, используемые клиентом для подтверждения своей подлинности при подключении к службе.</span><span class="sxs-lookup"><span data-stu-id="82de7-119">Specifies the credentials used by the client to authenticate itself to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="82de7-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="82de7-120">Remarks</span></span>  
 <span data-ttu-id="82de7-121">Этот элемент конфигурации содержит параметры, используемые клиентом для проверки сертификата, представленного службой с помощью проверки подлинности SSL.</span><span class="sxs-lookup"><span data-stu-id="82de7-121">This configuration element specifies the settings used by the client to validate the certificate presented by the service using SSL authentication.</span></span> <span data-ttu-id="82de7-122">Он также содержит сертификат для службы, который явно задан в клиенте для шифрования сообщений для службы с помощью безопасности сообщений.</span><span class="sxs-lookup"><span data-stu-id="82de7-122">It also contains any certificate for the service that is explicitly configured on the client to use for encrypting messages to the service using message security.</span></span>  
  
 <span data-ttu-id="82de7-123">Атрибуты `serviceCertificate` элемента идентичны атрибутам объекта [\<clientCertificate>](clientcertificate-of-clientcredentials-element.md) .</span><span class="sxs-lookup"><span data-stu-id="82de7-123">The attributes of the `serviceCertificate` element are identical to the attributes of the [\<clientCertificate>](clientcertificate-of-clientcredentials-element.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82de7-124">См. также</span><span class="sxs-lookup"><span data-stu-id="82de7-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.ServiceCertificate%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.ServiceCertificate%2A>
- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- [<span data-ttu-id="82de7-125">Поведение безопасности</span><span class="sxs-lookup"><span data-stu-id="82de7-125">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="82de7-126">Обеспечение безопасности клиентов</span><span class="sxs-lookup"><span data-stu-id="82de7-126">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="82de7-127">Работа с сертификатами</span><span class="sxs-lookup"><span data-stu-id="82de7-127">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="82de7-128">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="82de7-128">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
