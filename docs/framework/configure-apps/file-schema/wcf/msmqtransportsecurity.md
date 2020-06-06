---
title: <msmqTransportSecurity>
ms.date: 03/30/2017
ms.assetid: 092e911b-ab1b-4069-a26e-6134c3299e06
ms.openlocfilehash: 5899c609b3cf52c4a275ba6fb10c5826fcf37f1e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153013"
---
# \<msmqTransportSecurity>
Задает параметры безопасности транспорта MSMQ для пользовательской привязки.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<msmqIntegration>**](msmqintegration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<msmqTransportSecurity>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<msmqTransportSecurity msmqAuthenticationMode="None/Windows/Certificate"
                       msmqEncryptionAlgorithm="RC4Stream/AES"
                       msmqProtectionLevel="None/Sign/EncryptAndSign"
                       msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />
</msmqTransportSecurity>
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание:|  
|---------------|-----------------|  
|`msmqAuthenticationMode`|Задает способ проверки подлинности сообщения транспортом MSMQ. Если задано значение `None`, атрибуту `msmqProtectionLevel` также должно быть присвоено значение `None`.<br /><br /> Допустимые значения.<br /><br /> -None — без проверки подлинности.<br />— Windows: механизм проверки подлинности использует Active Directory, чтобы получить сертификат X. 509 для идентификатора безопасности, связанного с сообщением. Затем это используется для проверки ACL очереди, чтобы убедиться в наличии у пользователя разрешений для записи в очередь.<br />-Certificate: канал получает сертификат из хранилища сертификатов.<br /><br /> Значение по умолчанию - Windows. Это атрибут типа <xref:System.ServiceModel.MsmqAuthenticationMode>.|  
|`msmqEncryptionAlgorithm`|Задает алгоритм, который будет использоваться для шифрования сообщений при их передаче между диспетчерами очередей сообщений. Допустимые значения.<br /><br /> - RC4Stream<br />— AES<br /><br /> Значение по умолчанию - RC4Stream. Это атрибут типа <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.|  
|`msmqProtectionLevel`|Задает способ обеспечения безопасности сообщения на уровне транспорта MSMQ. Шифрование гарантирует целостность сообщений, а EncryptAndSign обеспечивает как целостность сообщений, так и неподдельность. то есть сообщение действительно поступает от отправителя, а отправитель — от того, кто говорят. Допустимые значения.<br /><br /> -None: защита отсутствует.<br />-Sign: сообщения подписываются.<br />-EncryptAndSign: сообщения шифруются и подписываются.<br /><br /> Значение по умолчанию - Sign. Это атрибут типа <xref:System.Net.Security.ProtectionLevel>.|  
|`msmqSecureHashAlgorithm`|Задает алгоритм, который должен использоваться при вычислении хэш-кода как части сигнатур. Допустимые значения.<br /><br /> -MD5<br />-SHA1<br />-SHA256<br />-SHA512<br /><br /> Значение по умолчанию - SHA1. Это атрибут типа <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.<br>Из-за проблем с MD5 и SHA1 Корпорация Майкрософт рекомендует использовать SHA256 или более высокий уровень.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<msmqIntegration>](msmqintegration.md)|Задает параметры, необходимые для взаимодействия с отправителем или получателем очереди сообщений (MSMQ).|  
|[\<msmqTransport>](msmqtransport.md)|Задает свойства обмена данными в очереди для службы Windows Communication Foundation (WCF), использующей собственный протокол MSMQ.|  
  
## <a name="remarks"></a>Примечания  
 Дополнительные сведения о безопасности транспорта см. в разделе [Безопасность транспорта](../../../wcf/feature-details/transport-security.md).  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity>
- <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [Очереди в WCF](../../../wcf/feature-details/queues-in-wcf.md)
- [Транспорты](../../../wcf/feature-details/transports.md)
- [Выбор транспортов](../../../wcf/feature-details/choosing-a-transport.md)
- [Привязки](../../../wcf/bindings.md)
- [Расширение привязок](../../../wcf/extending/extending-bindings.md)
- [Пользовательские привязки](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
- [Безопасность транспорта](../../../wcf/feature-details/transport-security.md)
