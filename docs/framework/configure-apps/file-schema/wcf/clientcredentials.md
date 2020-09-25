---
title: <clientCredentials>
ms.date: 03/30/2017
ms.assetid: 1e6eef0d-a34e-4d74-b0f7-f65d2181858d
ms.openlocfilehash: 6094006df24ee824c419a783ab29d7604757577c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201464"
---
# \<clientCredentials>

<span data-ttu-id="064f6-101">Задает учетные данные, используемые для проверки подлинности клиента при подключении к службе.</span><span class="sxs-lookup"><span data-stu-id="064f6-101">Specifies the credentials used to authenticate the client to a service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clientCredentials>**  
  
## <a name="syntax"></a><span data-ttu-id="064f6-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="064f6-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="064f6-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="064f6-103">Attributes and Elements</span></span>  

 <span data-ttu-id="064f6-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="064f6-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="064f6-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="064f6-105">Attributes</span></span>  
  
|<span data-ttu-id="064f6-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="064f6-106">Attribute</span></span>|<span data-ttu-id="064f6-107">Описание</span><span class="sxs-lookup"><span data-stu-id="064f6-107">Description</span></span>|  
|---------------|-----------------|  
|`supportInteractive`|<span data-ttu-id="064f6-108">Логическое значение, которое указывает, может ли текущий пользователь принимать участие в выборе учетных данных клиента во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="064f6-108">A Boolean value that specifies whether an interactive user can be involved in selecting a client credential at runtime.</span></span> <span data-ttu-id="064f6-109">Значение по умолчанию — `true`.</span><span class="sxs-lookup"><span data-stu-id="064f6-109">The default value is `true`.</span></span>|  
|`type`|<span data-ttu-id="064f6-110">Строка, задающая тип данного элемента конфигурации.</span><span class="sxs-lookup"><span data-stu-id="064f6-110">A string that specifies the type of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="064f6-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="064f6-111">Child Elements</span></span>  
  
|<span data-ttu-id="064f6-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="064f6-112">Element</span></span>|<span data-ttu-id="064f6-113">Описание</span><span class="sxs-lookup"><span data-stu-id="064f6-113">Description</span></span>|  
|-------------|-----------------|  
|[\<clientCertificate>](clientcertificate-of-clientcredentials-element.md)|<span data-ttu-id="064f6-114">Задает сертификат, используемый для проверки подлинности клиента при подключении к службе.</span><span class="sxs-lookup"><span data-stu-id="064f6-114">Specifies the certificate used to authenticate the client to the service.</span></span> <span data-ttu-id="064f6-115">Это элемент типа <xref:System.ServiceModel.Configuration.X509InitiatorCertificateClientElement>.</span><span class="sxs-lookup"><span data-stu-id="064f6-115">This element is of type <xref:System.ServiceModel.Configuration.X509InitiatorCertificateClientElement>.</span></span>|  
|[\<httpDigest>](httpdigest-element.md)|<span data-ttu-id="064f6-116">Задает хэш-код, используемый для проверки подлинности клиента при подключении к службе.</span><span class="sxs-lookup"><span data-stu-id="064f6-116">Specifies a digest used to authenticate the client to the service.</span></span> <span data-ttu-id="064f6-117">Это элемент типа <xref:System.ServiceModel.Configuration.HttpDigestClientElement>.</span><span class="sxs-lookup"><span data-stu-id="064f6-117">This element is of type <xref:System.ServiceModel.Configuration.HttpDigestClientElement>.</span></span>|  
|[\<issuedToken>](issuedtoken.md)|<span data-ttu-id="064f6-118">Задает тип пользовательского маркера, используемого для проверки подлинности клиента при подключении к службе маркеров безопасности (STS).</span><span class="sxs-lookup"><span data-stu-id="064f6-118">Specifies a custom token type used to authenticate the client to a Secure Token Service (STS).</span></span> <span data-ttu-id="064f6-119">Это элемент типа <xref:System.ServiceModel.Configuration.IssuedTokenClientElement>.</span><span class="sxs-lookup"><span data-stu-id="064f6-119">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenClientElement>.</span></span>|  
|[\<peer>](peer-of-clientcredentials-element.md)|<span data-ttu-id="064f6-120">Задает учетные данные текущего однорангового узла.</span><span class="sxs-lookup"><span data-stu-id="064f6-120">Specifies a current peer credential.</span></span> <span data-ttu-id="064f6-121">Это элемент типа <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span><span class="sxs-lookup"><span data-stu-id="064f6-121">This element is of type <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span></span>|  
|[\<serviceCertificate>](servicecertificate-of-clientcredentials-element.md)|<span data-ttu-id="064f6-122">Задает сертификат, используемый при проверки подлинности службы для клиента, и предоставляет структуру для настройки параметров сертификата.</span><span class="sxs-lookup"><span data-stu-id="064f6-122">Specifies the certificate used to authenticate the service to the client and provides a structure for setting certificate options.</span></span> <span data-ttu-id="064f6-123">Данный сертификат должен быть предоставлен вне диапазона службой клиенту.</span><span class="sxs-lookup"><span data-stu-id="064f6-123">This certificate must be supplied out-of-band from the service to the client.</span></span> <span data-ttu-id="064f6-124">Это элемент типа <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>.</span><span class="sxs-lookup"><span data-stu-id="064f6-124">This element is of type <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>.</span></span>|  
|[\<windows>](windows-of-clientcredentials-element.md)|<span data-ttu-id="064f6-125">Задает учетные данные Windows.</span><span class="sxs-lookup"><span data-stu-id="064f6-125">Specifies a Windows credential.</span></span> <span data-ttu-id="064f6-126">Значением по умолчанию являются учетные данные текущего потока.</span><span class="sxs-lookup"><span data-stu-id="064f6-126">The default is the credential of the current thread.</span></span> <span data-ttu-id="064f6-127">Это элемент типа <xref:System.ServiceModel.Configuration.WindowsClientElement>.</span><span class="sxs-lookup"><span data-stu-id="064f6-127">This element is of type <xref:System.ServiceModel.Configuration.WindowsClientElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="064f6-128">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="064f6-128">Parent Elements</span></span>  
  
|<span data-ttu-id="064f6-129">Элемент</span><span class="sxs-lookup"><span data-stu-id="064f6-129">Element</span></span>|<span data-ttu-id="064f6-130">Описание</span><span class="sxs-lookup"><span data-stu-id="064f6-130">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="064f6-131">Задает поведение конечной точки.</span><span class="sxs-lookup"><span data-stu-id="064f6-131">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="064f6-132">Remarks</span><span class="sxs-lookup"><span data-stu-id="064f6-132">Remarks</span></span>  

 <span data-ttu-id="064f6-133">Учетные данные клиента используются для проверки подлинности клиента при подключении к службам в случаях, когда требуется взаимная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="064f6-133">Client credentials are used to authenticate the client to services in cases where mutual authentication is required.</span></span> <span data-ttu-id="064f6-134">Данный раздел конфигурации также можно использовать для задания сертификатов служб для сценариев, где клиент должен обеспечить защиту сообщений, передаваемых службе, с помощью сертификатов службы.</span><span class="sxs-lookup"><span data-stu-id="064f6-134">This configuration section can also be used to specify service certificates for scenarios where the client must secure messages to a service with the service's certificate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="064f6-135">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="064f6-135">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- [<span data-ttu-id="064f6-136">Поведение безопасности</span><span class="sxs-lookup"><span data-stu-id="064f6-136">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="064f6-137">Обеспечение безопасности клиентов</span><span class="sxs-lookup"><span data-stu-id="064f6-137">Securing Clients</span></span>](../../../wcf/securing-clients.md)
