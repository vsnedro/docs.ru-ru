---
description: 'Дополнительные сведения о <socket> элементе: Element (параметры сети)'
title: Элемент <socket> (параметры сети)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/socket
- http://schemas.microsoft.com/.NetConfiguration/v2.0#socket
helpviewer_keywords:
- <socket> element
- socket element
ms.assetid: 366c634c-7d16-478f-aedf-053eda94a1a0
ms.openlocfilehash: 564d6566bf6f6b1997b986cb6c0d85f841195e55
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99740136"
---
# <a name="socket-element-network-settings"></a>Элемент \<socket> (параметры сети)

Указывает, используют ли операции сокета порты завершения.  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<socket>**

## <a name="syntax"></a>Синтаксис  
  
```xml  
<socket  
  alwaysUseCompletionPortsForConnect="true|false"  
  alwaysUseCompletionPortsForAccept="true|false"  
  ipProtectionLevel="EdgeRestricted|Restricted|Unrestricted|Unspecified"  
/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  

 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|**Attribute**|**Описание**|  
|-------------------|---------------------|  
|`alwaysUseCompletionPortsForAccept`|Указывает, должен ли сокет всегда использовать порты завершения для вызовов метода Accept. Значение по умолчанию — `false`.|  
|`alwaysUseCompletionPortsForConnect`|Указывает, должен ли сокет всегда использовать порты завершения для вызовов метода Connect. Значение по умолчанию — `false`.|  
|`ipProtectionLevel`|Указывает значение по умолчанию, <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> используемое для сокета. Значение по умолчанию зависит от версии Windows.|  
  
### <a name="child-elements"></a>Дочерние элементы  

 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|**Элемент**|**Описание**|  
|-----------------|---------------------|  
|[параметры](settings-element-network-settings.md)|Настраивает основные параметры сети для пространства имен <xref:System.Net>.|  
  
## <a name="remarks"></a>Remarks  

 Атрибуты `alwaysUseCompletionPortsForAccept` и `alwaysUseCompletionPortsForConnect` используются для задания поведения по умолчанию в отношении использования портов завершения классами в пространстве имен <xref:System.Net.Sockets?displayProperty=nameWithType>. Порты завершения рекомендуются для высокопроизводительных серверных приложений.  
  
 По умолчанию для `alwaysUseCompletionPortsForAccept` атрибутов и `alwaysUseCompletionPortsForConnect` задано значение **false**.  
  
 <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForAccept%2A>Можно использовать для получения текущего значения `alwaysUseCompletionPortsForAccept` атрибута из применимых файлов конфигурации. <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForConnect%2A>Можно использовать для получения текущего значения `alwaysUseCompletionPortsForConnect` атрибута из применимых файлов конфигурации.  
  
 `ipProtectionLevel`Атрибут указывает значение по умолчанию, <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> используемое для сокета. <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A>Свойство позволяет настроить ограничение сокета IPv6 на указанную область, например адреса с одинаковой локальной ссылкой или локальным префиксом сайта. Этот параметр позволяет приложениям размещать ограничения доступа к сокетам IPv6. Такие ограничения позволяют приложению, работающему в частной локальной сети, просто и надежно защититься от внешних атак. Этот параметр расширяет или ограничивает область действия прослушивающего сокета, обеспечивая неограниченный доступ от общедоступных и частных пользователей при необходимости или ограничивающий доступ только для того же сайта, если это необходимо.  
  
 Этот `ipProtectionLevel` параметр атрибута влияет только на первоначальный входящий трафик.  
  
- TCP-сервер, прослушивающий входящие подключения на сокете.  
  
- Приложение UDP, получающее пакет на сокете.  
  
 Этот параметр конфигурации не влияет на уже установленные TCP-подключения (трафик в обоих направлениях не ограничен) и не влияет на приложение, отправляющее пакеты UDP.  
  
 Возможные значения для `ipProtectionLevel` параметра атрибута соответствуют определенным уровням защиты, указанным в <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> перечислении, следующим образом:  
  
|**Значение атрибута**|**Описание**|  
|-|-|  
|еджерестриктед|Уровень защиты IP — предельно ограничено. Это значение используется приложениями, разработанными для работы в Интернете. Этот параметр не позволяет обойти механизм преобразования сетевых адресов (NAT) с помощью реализации Windows Teredo. Эти приложения могут обходить брандмауэры протокола IPv4, поэтому они должны быть защищены от атак из Интернета, направленных на открытый порт. В Windows Server 2003 и Windows XP значение по умолчанию для уровня защиты IP сокета — предельно ограничено.|  
|С ограниченным доступом|Уровень защиты IP — ограничено. Это значение используется приложениями интрасети, не работающих в Интернете. Эти приложения обычно не тестируются и не защищаются против атак из Интернета. Этот параметр ограничивает получаемый трафик локальным.|  
|С неограниченным доступом|Уровень защиты IP — неограниченно. Это значение используется приложениями, разработанными для работы в Интернете, включая приложения, использующие возможности обхода IPv6 NAT, включенные в Windows (например, Teredo). Эти приложения могут обходить брандмауэры протокола IPv4, поэтому они должны быть защищены от атак из Интернета, направленных на открытый порт. В Windows Server 2008 R2 и Windows Vista значение по умолчанию для уровня защиты IP сокета — неограниченно.|  
|Не указан|Уровень защиты IP — не указано. В Windows 7 и Windows Server 2008 R2 и значение по умолчанию для уровня защиты IP сокета — не указано.|  
  
 Значение по умолчанию для `ipProtectionLevel` атрибута не **указано**.  
  
 <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A>Свойство можно использовать для получения текущего значения `ipProtectionLevel` атрибута из применимых файлов конфигурации.  
  
## <a name="configuration-files"></a>Файлы конфигурации  

 Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).  
  
## <a name="example"></a>Пример  

 В следующем примере показано, как указать, что порты завершения должны использоваться и что значение по умолчанию <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> должно быть неограниченным.  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <socket  
        alwaysUseCompletionPortsForAccept="true"  
        alwaysUseCompletionPortsForConnect="true"  
        ipProtectionLevel="Unrestricted"  
       />  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также

- <xref:System.Net?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SocketElement?displayProperty=nameWithType>
- <xref:System.Net.Sockets?displayProperty=nameWithType>
- <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType>
- <xref:System.Net.Sockets.SocketOptionName.IPProtectionLevel?displayProperty=nameWithType>
- [Схема параметров сети](index.md)
