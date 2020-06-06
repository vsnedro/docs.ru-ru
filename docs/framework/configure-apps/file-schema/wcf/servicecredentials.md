---
title: <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: 96db336c-4f7a-4193-81a5-910b8ffd804f
ms.openlocfilehash: 90a34a4a52b4c7a2e67d733fecba132818cac4fc
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399661"
---
# \<serviceCredentials>
<span data-ttu-id="51bdf-101">Задает учетные данные, используемые при проверке подлинности службы, а также параметры, относящиеся к проверке учетных данных клиента.</span><span class="sxs-lookup"><span data-stu-id="51bdf-101">Specifies the credential to be used in authenticating the service and the client credential validation-related settings.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceCredentials>**  
  
## <a name="syntax"></a><span data-ttu-id="51bdf-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="51bdf-102">Syntax</span></span>  
  
```xml  
<serviceCredentials type="String">
  <clientCertificate>
  </clientCertificate>
  <issuedTokenAuthentication>
  </issuedTokenAuthentication>
  <peer>
  </peer>
  <secureConversationAuthentication>
  </secureConversationAuthentication>
  <serviceCertificate>
  </serviceCertificate>
  <userNameAuthentication>
  </userNameAuthentication>
  <windowsAuthentication>
  </windowsAuthentication>
</serviceCredentials>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="51bdf-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="51bdf-103">Attributes and Elements</span></span>  
 <span data-ttu-id="51bdf-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="51bdf-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="51bdf-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="51bdf-105">Attributes</span></span>  
  
|<span data-ttu-id="51bdf-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="51bdf-106">Attribute</span></span>|<span data-ttu-id="51bdf-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="51bdf-107">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="51bdf-108">Строка, задающая тип данного элемента конфигурации.</span><span class="sxs-lookup"><span data-stu-id="51bdf-108">A string that specifies the type of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="51bdf-109">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="51bdf-109">Child Elements</span></span>  
  
|<span data-ttu-id="51bdf-110">Элемент</span><span class="sxs-lookup"><span data-stu-id="51bdf-110">Element</span></span>|<span data-ttu-id="51bdf-111">Описание</span><span class="sxs-lookup"><span data-stu-id="51bdf-111">Description</span></span>|  
|-------------|-----------------|  
|[\<clientCertificate>](clientcertificate-of-servicecredentials.md)|<span data-ttu-id="51bdf-112">Задает сертификат для использования, когда сертификат клиента доступен внештатно.</span><span class="sxs-lookup"><span data-stu-id="51bdf-112">Specifies the certificate to be used when the client certificate is available out-of-band.</span></span> <span data-ttu-id="51bdf-113">Этот элемент также задает параметры проверки сертификата клиента.</span><span class="sxs-lookup"><span data-stu-id="51bdf-113">This element also specifies client certificate validation settings.</span></span> <span data-ttu-id="51bdf-114">Это элемент типа <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="51bdf-114">This element is of type <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>.</span></span>|  
|[\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="51bdf-115">Задает для этой службы текущий выданный маркер.</span><span class="sxs-lookup"><span data-stu-id="51bdf-115">Specifies the current issued token for this service.</span></span> <span data-ttu-id="51bdf-116">Это элемент типа <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="51bdf-116">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>.</span></span>|  
|[\<peer>](peer-of-servicecredentials.md)|<span data-ttu-id="51bdf-117">Задает текущие учетные данные для однорангового узла.</span><span class="sxs-lookup"><span data-stu-id="51bdf-117">Specifies the current credentials for a peer node.</span></span> <span data-ttu-id="51bdf-118">Это элемент типа <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span><span class="sxs-lookup"><span data-stu-id="51bdf-118">This element is of type <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span></span>|  
|[\<secureConversationAuthentication>](secureconversationauthentication-of-servicecredential.md)|<span data-ttu-id="51bdf-119">Задает текущие учетные данные для безопасного сеанса.</span><span class="sxs-lookup"><span data-stu-id="51bdf-119">Specifies the current credentials for a secure conversation.</span></span> <span data-ttu-id="51bdf-120">Это элемент типа <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="51bdf-120">This element is of type <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>.</span></span>|  
|[\<serviceCertificate>](servicecertificate-of-servicecredentials.md)|<span data-ttu-id="51bdf-121">Задает сертификат, используемый службой для своей идентификации.</span><span class="sxs-lookup"><span data-stu-id="51bdf-121">Specifies a certificate used by a service to identify itself.</span></span> <span data-ttu-id="51bdf-122">Это элемент типа <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="51bdf-122">This element is of type <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>.</span></span>|  
|[\<userNameAuthentication>](usernameauthentication.md)|<span data-ttu-id="51bdf-123">Задает параметры для проверки имени пользователя и пароля.</span><span class="sxs-lookup"><span data-stu-id="51bdf-123">Specifies the settings for username password validation.</span></span> <span data-ttu-id="51bdf-124">Это элемент типа <xref:System.ServiceModel.Configuration.UserNameServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="51bdf-124">This element is of type <xref:System.ServiceModel.Configuration.UserNameServiceElement>.</span></span>|  
|[\<windowsAuthentication>](windowsauthentication-of-servicecredentials.md)|<span data-ttu-id="51bdf-125">Задает параметры для проверки учетных данных ОС Windows.</span><span class="sxs-lookup"><span data-stu-id="51bdf-125">Specifies the settings for Windows credential validation.</span></span> <span data-ttu-id="51bdf-126">Это элемент типа <xref:System.ServiceModel.Configuration.WindowsServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="51bdf-126">This element is of type <xref:System.ServiceModel.Configuration.WindowsServiceElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="51bdf-127">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="51bdf-127">Parent Elements</span></span>  
  
|<span data-ttu-id="51bdf-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="51bdf-128">Element</span></span>|<span data-ttu-id="51bdf-129">Описание</span><span class="sxs-lookup"><span data-stu-id="51bdf-129">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="51bdf-130">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="51bdf-130">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="51bdf-131">См. также</span><span class="sxs-lookup"><span data-stu-id="51bdf-131">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement>
- <xref:System.ServiceModel.Description.ServiceCredentials>
- [<span data-ttu-id="51bdf-132">Поведение безопасности</span><span class="sxs-lookup"><span data-stu-id="51bdf-132">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
