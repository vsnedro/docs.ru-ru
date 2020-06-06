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
# <a name="peer-of-clientcredentials-element"></a>\<peer> элемента \<clientCredentials>
Задает учетные данные, используемые при проверке подлинности одноранговых клиентов.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<peer>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<peer>
  <certificate />
  <peerAuthentication />
  <messageSenderAuthentication />
</peer>
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
 Отсутствует.  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<certificate>](certificate-element.md)|Задает сертификат X.509, используемый для подписи и шифрования сообщений для клиентов одноранговых сетей. .|  
|[\<peerAuthentication>](peerauthentication-element.md)|Задает параметры проверки подлинности для одноранговых клиентов.|  
|[\<messageSenderAuthentication>](messagesenderauthentication-element.md)|Задает параметры проверки подлинности для отправителей сообщений.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<clientCredentials>](clientcredentials.md)|Задает учетные данные, используемые для проверки подлинности клиента при подключении к службе.|  
  
## <a name="remarks"></a>Примечания  
 Этот элемент конфигурации задает учетные данные, используемые одноранговым узлом для подтверждения своей подлинности для других узлов в сетке, а также параметры, используемые одноранговым узлом для проверки подлинности других одноранговых узлов. Дополнительные сведения см. в статье [Проверка подлинности сообщений одноранговых каналов](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90)) и [Защита приложений одноранговых каналов](../../../wcf/feature-details/securing-peer-channel-applications.md).  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.Peer%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.Peer%2A>
- <xref:System.ServiceModel.Security.PeerCredential>
- [Одноранговая сеть](../../../wcf/feature-details/peer-to-peer-networking.md)
- [Обеспечение безопасности клиентов](../../../wcf/securing-clients.md)
- [Проверка подлинности сообщений для однорангового канала](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))
- [Пользовательской проверка подлинности для однорангового канала](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))
- [Защита приложений одноранговых каналов](../../../wcf/feature-details/securing-peer-channel-applications.md)
- [Защита служб и клиентов](../../../wcf/feature-details/securing-services-and-clients.md)
