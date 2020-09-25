---
title: Элемент <smtp> (параметры сети)
description: <smtp>Элемент Параметры сети настраивает формат доставки, метод доставки и адрес отправителя для отправки параметров электронной почты в .NET Framework.
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp
- http://schemas.microsoft.com/.NetConfiguration/v2.0#smtp
helpviewer_keywords:
- <smtp> element
- smtp element
ms.assetid: 220b0329-e384-4e0c-86b4-0945ad17efd9
ms.openlocfilehash: 58f496b4a07f7d5531df897dd54bb6176111f1c4
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91178324"
---
# <a name="smtp-element-network-settings"></a>Элемент \<smtp> (параметры сети)

Настраивает формат доставки, метод доставки и адрес отправителя для отправки сообщений электронной почты.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<mailSettings>**](mailsettings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<smtp>**
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<smtp  
  deliveryFormat="format"  
  deliveryMethod="method"  
  from="from address">
    <specifiedPickupDirectory>...</specifiedPickupDirectory>  
    <network>...</network>  
</smtp>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  

 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`deliveryFormat`|Указывает формат доставки исходящих сообщений электронной почты. Допустимые значения: SevenBit и International.|  
|`deliveryMethod`|Указывает метод доставки сообщений электронной почты. Допустимые значения: Network, Пиккупдиректорифромиис и СпеЦифиедпиккупдиректори.|  
|`from`|Указывает адрес отсылаемых сообщений электронной почты.|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|attribute|Описание|  
|---------------|-----------------|  
|`specifiedPickupDirectory`|Настраивает локальный каталог для SMTP-сервера.|  
|`network`|Настраивает параметры сети для внешнего SMTP-сервера.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|**Элемент**|**Описание**|  
|-----------------|---------------------|  
|[Элемент \<mailSettings> (параметры сети)](mailsettings-element-network-settings.md)|Настраивает параметры отправки почты.|  
  
## <a name="example"></a>Пример  

 В следующем примере задаются соответствующие параметры SMTP для отправки электронной почты с использованием сетевых учетных данных по умолчанию.  
  
```xml  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="Network" deliveryFormat="SevenBit"  from="ben@contoso.com">  
        <network  
          host="localhost"  
          port="25"  
          defaultCredentials="true"  
        />  
      </smtp>  
    </mailSettings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpDeliveryFormat>
- <xref:System.Net.Mail.SmtpDeliveryMethod>
- [Схема параметров сети](index.md)
