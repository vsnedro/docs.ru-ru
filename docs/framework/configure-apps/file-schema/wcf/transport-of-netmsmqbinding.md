---
title: <transport> из <netMsmqBinding>
ms.date: 03/30/2017
ms.assetid: 72e1b338-39f0-4af1-a5d9-7a2fb79f6a0b
ms.openlocfilehash: 84a5437de851ecdb96d0463ec574186ba5f91d9e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203882"
---
# <a name="transport-of-netmsmqbinding"></a>\<transport> из \<netMsmqBinding>

Определяет параметры безопасности транспорта.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netMsmqBinding>**](netmsmqbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-netmsmqbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<netMsmqBinding>
  <binding>
    <security>
      <transport msmqAuthenticationMode="None/WindowsDomain/Certificate"
                 msmqEncryptionAlgorithm="RC4Stream/AES"
                 msmqProtectionLevel="None/Sign/EncryptAndSign"
                 msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />
    </security>
  </binding>
</netMsmqBinding>
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  

 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|msmqAuthenticationMode|Задает способ проверки подлинности сообщения транспортом MSMQ. Допустимые значения.<br /><br /> -None — без проверки подлинности.<br />-WindowsDomain. механизм проверки подлинности использует Active Directory для получения сертификата X. 509 для идентификатора безопасности, связанного с сообщением. Затем он используется для проверки списка управления доступом для очереди с целью удостовериться, что пользователь имеет разрешение на запись в очередь.<br />-Certificate: канал получает сертификат из хранилища сертификатов.<br /><br /> Значение по умолчанию — `WindowsDomain`.<br /><br /> Если данный атрибут имеет значение `None`, то атрибут `msmqProtectionLevel` также должен иметь значение `None`. Это атрибут типа <xref:System.ServiceModel.MsmqAuthenticationMode>.|  
|msmqEncryptionAlgorithm|Задает алгоритм, который будет использоваться для шифрования сообщений при их передаче между диспетчерами очередей сообщений. Допустимые значения.<br /><br /> - RC4Stream<br />— AES<br />— Значение по умолчанию — `RC4Stream` . Это атрибут типа <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.|  
|msmqprotectionLevel|Задает способ обеспечения безопасности сообщений на уровне транспорта MSMQ. Шифрование обеспечивает целостность сообщения, тогда как подпись и шифрование обеспечивают как целостность сообщения, так и неподдельность. То есть сообщение действительно поступило от отправителя, а отправитель — от того, кто говорят. Допустимые значения.<br /><br /> -None: защита отсутствует.<br />-Sign: сообщения подписываются.<br />-EncryptAndSign: сообщения шифруются и подписываются.<br />— Значение по умолчанию — `Sign` .|  
|msmqSecureHashAlgorithm|Указывает алгоритм хэширования, который будет использоваться при вычислении хэш-кода сообщения. Допустимые значения.<br /><br /> -MD5<br />-SHA1<br />-SHA256<br />-SHA512<br /><br /> Значение по умолчанию — `SHA1`. Это атрибут типа <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.<br>Из-за проблем с MD5 и SHA1 Корпорация Майкрософт рекомендует использовать SHA256 или более высокий уровень.|  
  
### <a name="child-elements"></a>Дочерние элементы  

 Нет  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<security>](security-of-netmsmqbinding.md)|Определяет параметры безопасности для поставленного в очередь транспорта.|  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>
- <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement.Transport%2A>
- <xref:System.ServiceModel.NetMsmqSecurity.Transport%2A>
- <xref:System.ServiceModel.MsmqTransportSecurity>
- [Очереди в WCF](../../../wcf/feature-details/queues-in-wcf.md)
- [Защита служб и клиентов](../../../wcf/feature-details/securing-services-and-clients.md)
- [Привязки](../../../wcf/bindings.md)
- [Настройка привязок, предоставляемых системой](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [Использование привязок для настройки служб и клиентов](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
