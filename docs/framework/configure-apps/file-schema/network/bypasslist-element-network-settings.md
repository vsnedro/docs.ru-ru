---
title: Элемент <bypasslist> (параметры сети)
description: <bypasslist>Элемент Network Settings предоставляет набор регулярных выражений, описывающих адреса, которые не используют прокси-сервер в платформа .NET Framework.
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#bypasslist
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist
helpviewer_keywords:
- bypasslist element
- <bypasslist> element
ms.assetid: 124446b7-abb1-4e5e-a492-b64398f268f1
ms.openlocfilehash: 0a03b391c839b7255fdd423a305d474d0e48ad39
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2021
ms.locfileid: "102259360"
---
# <a name="bypasslist-element-network-settings"></a>Элемент \<bypasslist> (параметры сети)

Предоставляет набор регулярных выражений, описывающих адреса, которые не используют прокси-сервер.  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bypasslist>**

## <a name="syntax"></a>Синтаксис  
  
```xml  
<bypasslist>
</bypasslist>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  

 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  

 Отсутствует.  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|**Элемент**|**Описание**|  
|-----------------|---------------------|  
|[add](add-element-for-bypasslist-network-settings.md)|Добавление в список обхода прокси IP-адреса или DNS-имени.|  
|[пусто](clear-element-for-bypasslist-network-settings.md)|Очищает список обхода.|  
|[remove](remove-element-for-bypasslist-network-settings.md)|Удаляет IP-адрес или DNS-имя из списка обхода прокси-сервера.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|**Элемент**|**Описание**|  
|-----------------|---------------------|  
|[defaultProxy](defaultproxy-element-network-settings.md)|Настраивает прокси-сервер протокола передачи гипертекста (HTTP).|  
  
## <a name="remarks"></a>Комментарии  

 Список обхода содержит регулярные выражения, описывающие URI, которые <xref:System.Net.WebRequest> обращаются к экземплярам напрямую, а не через прокси-сервер.  
  
 При указании регулярного выражения для этого элемента следует соблюдать осторожность. Регулярное выражение `[a-z]+\\.contoso\\.com` соответствует любому узлу в домене contoso.com, но оно также соответствует любому узлу в домене contoso.com.cpandl.com. Чтобы сопоставить только узел в домене contoso.com, используйте привязку ( `$` ): `[a-z]+\\.contoso\\.com$` .
  
 Дополнительные сведения о регулярных выражениях см. в разделе. [Платформа .NET Framework регулярных выражений](../../../../standard/base-types/regular-expressions.md).  
  
## <a name="configuration-files"></a>Файлы конфигурации  

 Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).  
  
## <a name="example"></a>Пример  

 В следующем примере в список обхода добавляется два адреса. Первый обход прокси-сервера для всех серверов в домене contoso.com; во втором случае прокси-сервер обходится для всех серверов, IP-адреса которых начинаются с 192,168.  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <bypasslist>  
        <add address="[a-z]+\.contoso\.com$" />  
        <add address="192\.168\.\d{1,3}\.\d{1,3}" />  
      </bypasslist>  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [Схема параметров сети](index.md)
