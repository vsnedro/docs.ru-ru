---
title: <peer> из <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: b134e21d-e5b5-458e-9309-626dbf8db4ed
ms.openlocfilehash: 7f6669d3f53a6ee0d189786fa9ca3625fdedd127
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91162482"
---
# <a name="peer-of-servicecredentials"></a><span data-ttu-id="b35d6-102">\<peer> из \<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="b35d6-102">\<peer> of \<serviceCredentials></span></span>

<span data-ttu-id="b35d6-103">Задает текущие учетные данные для однорангового узла.</span><span class="sxs-lookup"><span data-stu-id="b35d6-103">Specifies the current credentials for a peer node.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<peer>**  
  
## <a name="syntax"></a><span data-ttu-id="b35d6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b35d6-104">Syntax</span></span>  
  
```xml  
<peer>
  <certificate />
  <peerAuthentication />
  <messageSenderAuthentication />
</peer>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b35d6-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b35d6-105">Attributes and Elements</span></span>  

 <span data-ttu-id="b35d6-106">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="b35d6-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b35d6-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b35d6-107">Attributes</span></span>  

 <span data-ttu-id="b35d6-108">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="b35d6-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b35d6-109">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b35d6-109">Child Elements</span></span>  
  
|<span data-ttu-id="b35d6-110">Элемент</span><span class="sxs-lookup"><span data-stu-id="b35d6-110">Element</span></span>|<span data-ttu-id="b35d6-111">Описание</span><span class="sxs-lookup"><span data-stu-id="b35d6-111">Description</span></span>|  
|-------------|-----------------|  
|[\<certificate>](certificate-of-peer.md)|<span data-ttu-id="b35d6-112">Задает сертификат X.509, используемый для подписи и шифрования сообщений для служб одноранговых сетей.</span><span class="sxs-lookup"><span data-stu-id="b35d6-112">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer services.</span></span> <span data-ttu-id="b35d6-113">.</span><span class="sxs-lookup"><span data-stu-id="b35d6-113">.</span></span>|  
|[\<messageSenderAuthentication>](messagesenderauthentication.md)|<span data-ttu-id="b35d6-114">Задает параметры проверки подлинности для отправителей сообщений.</span><span class="sxs-lookup"><span data-stu-id="b35d6-114">Specifies authentication options for message senders.</span></span>|  
|[\<peerAuthentication>](peerauthentication.md)|<span data-ttu-id="b35d6-115">Задает параметры проверки подлинности для одноранговых служб.</span><span class="sxs-lookup"><span data-stu-id="b35d6-115">Specifies authentication options for peer services.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b35d6-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b35d6-116">Parent Elements</span></span>  
  
|<span data-ttu-id="b35d6-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="b35d6-117">Element</span></span>|<span data-ttu-id="b35d6-118">Описание</span><span class="sxs-lookup"><span data-stu-id="b35d6-118">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceCredentials>](servicecredentials.md)|<span data-ttu-id="b35d6-119">Задает учетные данные, используемые при проверке подлинности службы, а также параметры, относящиеся к проверке учетных данных клиента.</span><span class="sxs-lookup"><span data-stu-id="b35d6-119">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b35d6-120">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b35d6-120">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.Peer%2A>
- <xref:System.ServiceModel.Description.ServiceCredentials.Peer%2A>
- <xref:System.ServiceModel.Security.PeerCredential>
- [<span data-ttu-id="b35d6-121">Одноранговая сеть</span><span class="sxs-lookup"><span data-stu-id="b35d6-121">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="b35d6-122">[Проверка подлинности сообщений для однорангового канала](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="b35d6-122">[Peer Channel Message Authentication](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="b35d6-123">[Пользовательской проверка подлинности для однорангового канала](/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="b35d6-123">[Peer Channel Custom Authentication](/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="b35d6-124">Защита приложений одноранговых каналов</span><span class="sxs-lookup"><span data-stu-id="b35d6-124">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
- [<span data-ttu-id="b35d6-125">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="b35d6-125">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
