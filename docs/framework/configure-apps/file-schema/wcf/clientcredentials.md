---
title: <clientCredentials>
ms.date: 03/30/2017
ms.assetid: 1e6eef0d-a34e-4d74-b0f7-f65d2181858d
ms.openlocfilehash: f295fe48e194611c80b78c0c23ab3e66ea1c0b64
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400501"
---
# \<clientCredentials>
<span data-ttu-id="7e740-101">Задает учетные данные, используемые для проверки подлинности клиента при подключении к службе.</span><span class="sxs-lookup"><span data-stu-id="7e740-101">Specifies the credentials used to authenticate the client to a service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clientCredentials>**  
  
## <a name="syntax"></a><span data-ttu-id="7e740-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7e740-102">Syntax</span></span>  
  
```xml  
<clientCredentials type="String"
                   supportInteractive="Boolean" >
  <clientCertificate>
  </clientCertificate>
  <digest>
  </digest>
  <isuedToken>
  </isuedToken>
  <peer>
  </peer>
  <serviceCertificate>
  </serviceCertificate>
  <windowsAuthentication>
  </windowsAuthentication>
</clientCredentials>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7e740-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="7e740-103">Attributes and Elements</span></span>  
 <span data-ttu-id="7e740-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="7e740-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7e740-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="7e740-105">Attributes</span></span>  
  
|<span data-ttu-id="7e740-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="7e740-106">Attribute</span></span>|<span data-ttu-id="7e740-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="7e740-107">Description</span></span>|  
|---------------|-----------------|  
|`supportInteractive`|<span data-ttu-id="7e740-108">Логическое значение, которое указывает, может ли текущий пользователь принимать участие в выборе учетных данных клиента во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="7e740-108">A Boolean value that specifies whether an interactive user can be involved in selecting a client credential at runtime.</span></span> <span data-ttu-id="7e740-109">Значение по умолчанию — `true`.</span><span class="sxs-lookup"><span data-stu-id="7e740-109">The default value is `true`.</span></span>|  
|`type`|<span data-ttu-id="7e740-110">Строка, задающая тип данного элемента конфигурации.</span><span class="sxs-lookup"><span data-stu-id="7e740-110">A string that specifies the type of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7e740-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="7e740-111">Child Elements</span></span>  
  
|<span data-ttu-id="7e740-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="7e740-112">Element</span></span>|<span data-ttu-id="7e740-113">Описание</span><span class="sxs-lookup"><span data-stu-id="7e740-113">Description</span></span>|  
|-------------|-----------------|  
|[\<clientCertificate>](clientcertificate-of-clientcredentials-element.md)|<span data-ttu-id="7e740-114">Задает сертификат, используемый для проверки подлинности клиента при подключении к службе.</span><span class="sxs-lookup"><span data-stu-id="7e740-114">Specifies the certificate used to authenticate the client to the service.</span></span> <span data-ttu-id="7e740-115">Это элемент типа <xref:System.ServiceModel.Configuration.X509InitiatorCertificateClientElement>.</span><span class="sxs-lookup"><span data-stu-id="7e740-115">This element is of type <xref:System.ServiceModel.Configuration.X509InitiatorCertificateClientElement>.</span></span>|  
|[\<httpDigest>](httpdigest-element.md)|<span data-ttu-id="7e740-116">Задает хэш-код, используемый для проверки подлинности клиента при подключении к службе.</span><span class="sxs-lookup"><span data-stu-id="7e740-116">Specifies a digest used to authenticate the client to the service.</span></span> <span data-ttu-id="7e740-117">Это элемент типа <xref:System.ServiceModel.Configuration.HttpDigestClientElement>.</span><span class="sxs-lookup"><span data-stu-id="7e740-117">This element is of type <xref:System.ServiceModel.Configuration.HttpDigestClientElement>.</span></span>|  
|[\<issuedToken>](issuedtoken.md)|<span data-ttu-id="7e740-118">Задает тип пользовательского маркера, используемого для проверки подлинности клиента при подключении к службе маркеров безопасности (STS).</span><span class="sxs-lookup"><span data-stu-id="7e740-118">Specifies a custom token type used to authenticate the client to a Secure Token Service (STS).</span></span> <span data-ttu-id="7e740-119">Это элемент типа <xref:System.ServiceModel.Configuration.IssuedTokenClientElement>.</span><span class="sxs-lookup"><span data-stu-id="7e740-119">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenClientElement>.</span></span>|  
|[\<peer>](peer-of-clientcredentials-element.md)|<span data-ttu-id="7e740-120">Задает учетные данные текущего однорангового узла.</span><span class="sxs-lookup"><span data-stu-id="7e740-120">Specifies a current peer credential.</span></span> <span data-ttu-id="7e740-121">Это элемент типа <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span><span class="sxs-lookup"><span data-stu-id="7e740-121">This element is of type <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span></span>|  
|[\<serviceCertificate>](servicecertificate-of-clientcredentials-element.md)|<span data-ttu-id="7e740-122">Задает сертификат, используемый при проверки подлинности службы для клиента, и предоставляет структуру для настройки параметров сертификата.</span><span class="sxs-lookup"><span data-stu-id="7e740-122">Specifies the certificate used to authenticate the service to the client and provides a structure for setting certificate options.</span></span> <span data-ttu-id="7e740-123">Данный сертификат должен быть предоставлен вне диапазона службой клиенту.</span><span class="sxs-lookup"><span data-stu-id="7e740-123">This certificate must be supplied out-of-band from the service to the client.</span></span> <span data-ttu-id="7e740-124">Это элемент типа <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>.</span><span class="sxs-lookup"><span data-stu-id="7e740-124">This element is of type <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>.</span></span>|  
|[\<windows>](windows-of-clientcredentials-element.md)|<span data-ttu-id="7e740-125">Задает учетные данные Windows.</span><span class="sxs-lookup"><span data-stu-id="7e740-125">Specifies a Windows credential.</span></span> <span data-ttu-id="7e740-126">Значением по умолчанию являются учетные данные текущего потока.</span><span class="sxs-lookup"><span data-stu-id="7e740-126">The default is the credential of the current thread.</span></span> <span data-ttu-id="7e740-127">Это элемент типа <xref:System.ServiceModel.Configuration.WindowsClientElement>.</span><span class="sxs-lookup"><span data-stu-id="7e740-127">This element is of type <xref:System.ServiceModel.Configuration.WindowsClientElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7e740-128">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="7e740-128">Parent Elements</span></span>  
  
|<span data-ttu-id="7e740-129">Элемент</span><span class="sxs-lookup"><span data-stu-id="7e740-129">Element</span></span>|<span data-ttu-id="7e740-130">Описание</span><span class="sxs-lookup"><span data-stu-id="7e740-130">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="7e740-131">Задает поведение конечной точки.</span><span class="sxs-lookup"><span data-stu-id="7e740-131">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7e740-132">Примечания</span><span class="sxs-lookup"><span data-stu-id="7e740-132">Remarks</span></span>  
 <span data-ttu-id="7e740-133">Учетные данные клиента используются для проверки подлинности клиента при подключении к службам в случаях, когда требуется взаимная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="7e740-133">Client credentials are used to authenticate the client to services in cases where mutual authentication is required.</span></span> <span data-ttu-id="7e740-134">Данный раздел конфигурации также можно использовать для задания сертификатов служб для сценариев, где клиент должен обеспечить защиту сообщений, передаваемых службе, с помощью сертификатов службы.</span><span class="sxs-lookup"><span data-stu-id="7e740-134">This configuration section can also be used to specify service certificates for scenarios where the client must secure messages to a service with the service's certificate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e740-135">См. также</span><span class="sxs-lookup"><span data-stu-id="7e740-135">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- [<span data-ttu-id="7e740-136">Поведение безопасности</span><span class="sxs-lookup"><span data-stu-id="7e740-136">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="7e740-137">Обеспечение безопасности клиентов</span><span class="sxs-lookup"><span data-stu-id="7e740-137">Securing Clients</span></span>](../../../wcf/securing-clients.md)
