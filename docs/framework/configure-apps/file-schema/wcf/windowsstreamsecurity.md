---
title: <windowsStreamSecurity>
ms.date: 03/30/2017
ms.assetid: 926bea29-90c7-4a26-9cf0-fb4aa44f6f70
ms.openlocfilehash: dab8505a9ddb348a6f7fe16ae9acb3a0119a8b06
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "73735893"
---
# \<windowsStreamSecurity>
Задает параметры безопасности потока Windows пользовательской привязки.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<windowsStreamSecurity>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<windowsStreamSecurity protectionLevel="None/Sign/EncryptAndSign" />
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание:|  
|---------------|-----------------|  
|protectionLevel|Определяет систему безопасности уровня сообщений. Подпись сообщений уменьшает риск подделки сообщения сторонними лицами при его передаче. Шифрование обеспечивает конфиденциальность на уровне данных во время транспортировки. Допустимые значения.<br /><br /> -None: защита отсутствует.<br />-Sign: сообщения подписываются.<br />-EncryptAndSign: сообщения подписываются и шифруются.<br /><br /> Значение по умолчанию - EncryptAndSign.<br /><br /> Это атрибут типа <xref:System.Net.Security.ProtectionLevel>.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|Определяет все возможности пользовательской привязки.|  
  
## <a name="remarks"></a>Примечания  
 Транспорты, использующие такой поточно-ориентированный протокол, как TCP и именованные каналы, поддерживают потоковые обновления транспорта. В частности, WCF обеспечивает обновления системы безопасности. Конфигурация этой защиты транспорта инкапсулирована этим элементом конфигурации, а также с [\<sslStreamSecurity>](sslstreamsecurity.md) , который можно настроить и добавить в пользовательскую привязку.  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>
- <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>
- [Привязки](../../../wcf/bindings.md)
- [Расширение привязок](../../../wcf/extending/extending-bindings.md)
- [Пользовательские привязки](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
