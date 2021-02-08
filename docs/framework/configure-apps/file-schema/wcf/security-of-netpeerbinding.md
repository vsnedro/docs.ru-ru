---
description: 'Дополнительные сведения <security> о: <netPeerBinding>'
title: <security> из <netPeerBinding>
ms.date: 03/30/2017
ms.assetid: 1ef40d8c-f903-4426-9b08-da81462766d8
ms.openlocfilehash: f67cfa445a5a605b99783cfd67dd1bae6e17b51e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786841"
---
# <a name="security-of-netpeerbinding"></a>\<security> из \<netPeerBinding>

Определяет параметры безопасности [\<netPeerTcpBinding>](netpeertcpbinding.md) , включая тип используемой проверки подлинности и безопасность, используемую для транспорта сообщений.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netPeerTcpBinding>**](netpeertcpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<netPeerBinding>
  <binding>
    <security mode="Message/None/Transport//TransportWithMessageCredential">
      <transport credentialType="Certificate/Password" />
    </security>
  </binding>
</netPeerBinding>
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  

 В следующих разделах описываются атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|mode|Необязательный элемент. Указывает тип безопасности, используемый одноранговыми узлами, настроенными с использованием этой привязки. Значение по умолчанию — `Message`. Это атрибут типа <xref:System.ServiceModel.SecurityMode>.|  
  
## <a name="mode-attribute"></a>Атрибут mode  
  
|Значение|Описание|  
|-----------|-----------------|  
|Сообщение|Механизм безопасности SOAP обеспечивает целостность, конфиденциальность и проверку подлинности.|  
|None|Режим безопасности отключен.|  
|Транспорт|Безопасность обеспечивается с помощью протокола HTTPS.|  
|TransportWithMessageCredential|HTTPS обеспечивает конфиденциальность и проверку подлинности. Сообщения SOAP предоставляют различные типы учетных данных.|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<transport>](transport-of-netpeertcpbinding.md)|Определяет тип транспорта для безопасных сообщений, отправленных одноранговыми узлами, настроенными с помощью этой привязки. Это элемент типа <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|Определяет все возможности привязки [\<netPeerTcpBinding>](netpeertcpbinding.md) .|  
  
## <a name="remarks"></a>Remarks  

 Безопасность может определяться как на уровне сообщений, так и на уровне транспорта.  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Configuration.PeerSecurityElement>
- <xref:System.ServiceModel.NetPeerTcpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Security%2A>
- <xref:System.ServiceModel.PeerSecuritySettings>
- [Защита служб и клиентов](../../../wcf/feature-details/securing-services-and-clients.md)
- [Выбор типа учетных данных](../../../wcf/feature-details/selecting-a-credential-type.md)
- [Привязки](../../../wcf/bindings.md)
- [Настройка привязок, предоставляемых системой](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [Использование привязок для настройки служб и клиентов](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
