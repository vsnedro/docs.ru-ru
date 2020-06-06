---
title: <peer> элемента <clientCredentials>
ms.date: 03/30/2017
ms.assetid: 505bd987-0042-4622-b68e-94f439729d53
ms.openlocfilehash: dce7ef64de1e3eb248e3553c97cbce8e9b205b4c
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400100"
---
# <a name="peer-of-clientcredentials-element"></a><span data-ttu-id="86619-102">\<peer> элемента \<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="86619-102">\<peer> of \<clientCredentials> Element</span></span>
<span data-ttu-id="86619-103">Задает учетные данные, используемые при проверке подлинности одноранговых клиентов.</span><span class="sxs-lookup"><span data-stu-id="86619-103">Specifies credentials used when authenticating peer-to-peer clients.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<peer>**  
  
## <a name="syntax"></a><span data-ttu-id="86619-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="86619-104">Syntax</span></span>  
  
```xml  
<peer>
  <certificate />
  <peerAuthentication />
  <messageSenderAuthentication />
</peer>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="86619-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="86619-105">Attributes and Elements</span></span>  
 <span data-ttu-id="86619-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="86619-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="86619-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="86619-107">Attributes</span></span>  
 <span data-ttu-id="86619-108">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="86619-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="86619-109">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="86619-109">Child Elements</span></span>  
  
|<span data-ttu-id="86619-110">Элемент</span><span class="sxs-lookup"><span data-stu-id="86619-110">Element</span></span>|<span data-ttu-id="86619-111">Описание</span><span class="sxs-lookup"><span data-stu-id="86619-111">Description</span></span>|  
|-------------|-----------------|  
|[\<certificate>](certificate-element.md)|<span data-ttu-id="86619-112">Задает сертификат X.509, используемый для подписи и шифрования сообщений для клиентов одноранговых сетей.</span><span class="sxs-lookup"><span data-stu-id="86619-112">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer clients.</span></span> <span data-ttu-id="86619-113">.</span><span class="sxs-lookup"><span data-stu-id="86619-113">.</span></span>|  
|[\<peerAuthentication>](peerauthentication-element.md)|<span data-ttu-id="86619-114">Задает параметры проверки подлинности для одноранговых клиентов.</span><span class="sxs-lookup"><span data-stu-id="86619-114">Specifies authentication options for peer clients.</span></span>|  
|[\<messageSenderAuthentication>](messagesenderauthentication-element.md)|<span data-ttu-id="86619-115">Задает параметры проверки подлинности для отправителей сообщений.</span><span class="sxs-lookup"><span data-stu-id="86619-115">Specifies authentication options for message senders.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="86619-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="86619-116">Parent Elements</span></span>  
  
|<span data-ttu-id="86619-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="86619-117">Element</span></span>|<span data-ttu-id="86619-118">Описание</span><span class="sxs-lookup"><span data-stu-id="86619-118">Description</span></span>|  
|-------------|-----------------|  
|[\<clientCredentials>](clientcredentials.md)|<span data-ttu-id="86619-119">Задает учетные данные, используемые для проверки подлинности клиента при подключении к службе.</span><span class="sxs-lookup"><span data-stu-id="86619-119">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="86619-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="86619-120">Remarks</span></span>  
 <span data-ttu-id="86619-121">Этот элемент конфигурации задает учетные данные, используемые одноранговым узлом для подтверждения своей подлинности для других узлов в сетке, а также параметры, используемые одноранговым узлом для проверки подлинности других одноранговых узлов.</span><span class="sxs-lookup"><span data-stu-id="86619-121">This configuration element specifies the credentials that a peer node uses to authenticate itself to other nodes in the mesh, as well as authentication settings that a peer node uses to authenticate other peer nodes.</span></span> <span data-ttu-id="86619-122">Дополнительные сведения см. в статье [Проверка подлинности сообщений одноранговых каналов](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90)) и [Защита приложений одноранговых каналов](../../../wcf/feature-details/securing-peer-channel-applications.md).</span><span class="sxs-lookup"><span data-stu-id="86619-122">For more information, see [Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90)) and [Securing Peer Channel Applications](../../../wcf/feature-details/securing-peer-channel-applications.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86619-123">См. также</span><span class="sxs-lookup"><span data-stu-id="86619-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.Peer%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.Peer%2A>
- <xref:System.ServiceModel.Security.PeerCredential>
- [<span data-ttu-id="86619-124">Одноранговая сеть</span><span class="sxs-lookup"><span data-stu-id="86619-124">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- [<span data-ttu-id="86619-125">Обеспечение безопасности клиентов</span><span class="sxs-lookup"><span data-stu-id="86619-125">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- <span data-ttu-id="86619-126">[Проверка подлинности сообщений для однорангового канала](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="86619-126">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="86619-127">[Пользовательской проверка подлинности для однорангового канала](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="86619-127">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="86619-128">Защита приложений одноранговых каналов</span><span class="sxs-lookup"><span data-stu-id="86619-128">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
- [<span data-ttu-id="86619-129">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="86619-129">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
