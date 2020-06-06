---
title: <transport> из <msmqIntegrationBinding>
ms.date: 03/30/2017
ms.assetid: 054579e3-7fdd-47df-99ca-952706ba5c8e
ms.openlocfilehash: 1cb165fed9266307335482166116c4c1d62efe7e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152961"
---
# <a name="transport-of-msmqintegrationbinding"></a>\<transport> из \<msmqIntegrationBinding>
Определяет параметры безопасности для транспорта интеграции очереди сообщений.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<msmqIntegrationBinding>**](msmqintegrationbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-msmqintegrationbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<security>
  <transport msmqAuthenticationMode="None/WindowsDomain/Certificate"
             msmqEncryptionAlgorithm="RC4Stream/AES"
             msmqProtectionLevel="None/Sign/EncryptAndSign"
             msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />
</security>
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описываются атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание:|  
|---------------|-----------------|  
|`msmqAuthenticationMode`|Задает способ проверки подлинности сообщения транспортом MSMQ. Если задано значение `None`, атрибуту `msmqProtectionLevel` также должно быть присвоено значение `None`.<br /><br /> Допустимые значения.<br /><br /> -None — без проверки подлинности.<br />-WindowsDomain. механизм проверки подлинности использует Active Directory для получения сертификата X. 509 для идентификатора безопасности, связанного с сообщением. Затем это используется для проверки ACL очереди, чтобы убедиться в наличии у пользователя разрешений для записи в очередь.<br />-Certificate: канал получает сертификат из хранилища сертификатов.<br /><br /> Значение по умолчанию - WindowsDomain. Это атрибут типа <xref:System.ServiceModel.MsmqAuthenticationMode>.|  
|`msmqEncryptionAlgorithm`|Задает алгоритм, который будет использоваться для шифрования сообщений при их передаче между диспетчерами очередей сообщений. Допустимые значения.<br /><br /> - RC4Stream<br />— AES<br /><br /> Значение по умолчанию - RC4Stream. Это атрибут типа <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.|  
|`msmqProtectionLevel`|Задает способ обеспечения безопасности сообщения на уровне транспорта MSMQ. Шифрование гарантирует целостность сообщений, а EncryptAndSign обеспечивает как целостность сообщений, так и неподдельность. то есть сообщение действительно поступает от отправителя, а отправитель — от того, кто говорят.<br /><br /> Допустимые значения включают следующие:<br />-None: защита отсутствует.<br />-Sign: сообщения подписываются.<br />-EncryptAndSign: сообщения шифруются и подписываются.<br /><br /> Значение по умолчанию - Sign. Это атрибут типа ProtectionLevel.|  
|`msmqSecureHashAlgorithm`|— Указывает алгоритм, используемый при вычислении дайджеста как части сигнатур. Допустимые значения.<br />-MD5<br />-SHA1<br />-SHA256<br />-SHA512<br /><br /> Значение по умолчанию - SHA1. Это атрибут типа <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.<br>Из-за проблем с MD5 и SHA1 Корпорация Майкрософт рекомендует использовать SHA256 или более высокий уровень.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<security>](security-of-basichttpbinding.md)|Определяет параметры безопасности для привязки MSMQ.|  
  
## <a name="remarks"></a>Примечания  
 Данный элемент инкапсулирует параметры безопасности для транспорта интеграции очереди сообщений. Данные параметры одинаковы для интеграции очереди сообщений и использующих очереди транспортов. Это позволяет задать режим проверки подлинности, алгоритм шифрования, алгоритм SHA и уровень защиты.  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>
- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.MsmqIntegrationSecurityElement.Transport%2A>
- <xref:System.ServiceModel.MsmqTransportSecurity>
- [Защита служб и клиентов](../../../wcf/feature-details/securing-services-and-clients.md)
- [Привязки](../../../wcf/bindings.md)
- [Настройка привязок, предоставляемых системой](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [Использование привязок для настройки служб и клиентов](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
