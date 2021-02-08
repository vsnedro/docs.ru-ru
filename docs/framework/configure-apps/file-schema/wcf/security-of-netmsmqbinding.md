---
description: 'Дополнительные сведения <security> о: <netMsmqBinding>'
title: <security> из <netMsmqBinding>
ms.date: 03/30/2017
ms.assetid: 001d11a9-7439-498c-b09d-fca20eaf8cd3
ms.openlocfilehash: 1b60d9e390e371555f4c3abf4988e79bb0f04fe8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786854"
---
# <a name="security-of-netmsmqbinding"></a>\<security> из \<netMsmqBinding>

Определяет параметры безопасности для привязки MSMQ. Он указывает, включена ли поддержка транспорта или безопасности SOAP и, если поддержка включена, указывает используемые уровни защиты и режим проверки подлинности.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netMsmqBinding>**](netmsmqbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<security mode="None/Transport/Message/Both">
  <transport msmqAuthenticationMode="None/WindowsDomain/Certificate"
             msmqEncryptionAlgorithm="RC4Stream/AES"
             msmqProtectionLevel="None/Sign/EncryptAndSign"
             msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />
    <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
             clientCredentialType="None/Windows/UserName/Certificate/CardSpace" />
</security>
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  

 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|mode|Задает тип безопасности, который контролирует целостность, конфиденциальность и проверку подлинности. Допустимые значения.<br /><br /> -None: отключает безопасность.<br />-Transport: защита и проверка подлинности предоставляются транспортом. Это значение связано с безопасностью сообщений между двумя диспетчерами очереди. Между приложением и диспетчером очереди безопасность сообщений не обеспечивается. Существующие Msmq-приложения функционально равноценны такому режиму безопасности.<br />-Message: определяет безопасность конечного приложения. Безопасность на транспортном уровне не предоставляется. Такие параметры аналогичны параметрам безопасности, предоставляемой другими стандартными привязками.<br />Оба: обеспечивают безопасность на уровне транспорта и сообщений протокола SOAP. На обоих уровнях требуются одни и те же учетные данные.<br /><br /> Значение по умолчанию - Transport. Это атрибут типа <xref:System.ServiceModel.NetMsmqSecurityMode>.|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<message>](message-of-netmsmqbinding.md)|Определяет параметры безопасности сообщений SOAP. Это элемент типа <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>.|  
|[\<transport>](transport-of-netmsmqbinding.md)|Определяет параметры безопасности для транспорта MSMQ. Это элемент типа <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|binding|Элемент binding элемента [\<netMsmqBinding>](netmsmqbinding.md)|  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement>
- <xref:System.ServiceModel.NetMsmqBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetMsmqBindingElement.Security%2A>
- <xref:System.ServiceModel.NetMsmqSecurity>
- [Защита служб и клиентов](../../../wcf/feature-details/securing-services-and-clients.md)
- [Привязки](../../../wcf/bindings.md)
- [Настройка привязок, предоставляемых системой](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [Использование привязок для настройки служб и клиентов](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
- [Очереди в WCF](../../../wcf/feature-details/queues-in-wcf.md)
