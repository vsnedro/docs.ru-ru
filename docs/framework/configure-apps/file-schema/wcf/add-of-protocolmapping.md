---
title: <add> из <protocolMapping>
ms.date: 03/30/2017
ms.assetid: 08e62249-1641-41d1-91b1-66d7b46244e4
ms.openlocfilehash: 46ba21b65f524f88bfce81739f0cd73040a2ad45
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91205013"
---
# <a name="add-of-protocolmapping"></a>\<add> из \<protocolMapping>

Представляет сопоставление протокола по умолчанию между схемой транспортного протокола (например, HTTP, net. TCP, net. pipe и т. д.) и привязкой Windows Communication Foundation (WCF). При создании конечных точек по умолчанию во время выполнения WCF проверяет настроенные сопоставления и решает, какая привязка будет использоваться для конкретного адреса на основе.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<protocolMapping>**](protocolmapping.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<protocolMapping>
  <add binding="String"
       bindingConfiguration="String"
       scheme="http/net.msmq/net.pipe/net.tcp" />
</protocolMapping>
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  

 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Элемент|Описание|  
|-------------|-----------------|  
|binding|Строка, в которой указан тип привязки, используемый для конечной точки во время создания конечной точки по умолчанию.|  
|bindingConfiguration|Строка, содержащая имя раздела конфигурации привязки, на который будет установлена ссылка.|  
|scheme|Схема транспортного протокола, которая будет использоваться для конечной точки по умолчанию.|  
  
### <a name="child-elements"></a>Дочерние элементы  

 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<protocolMapping>](protocolmapping.md)|Представляет раздел конфигурации для определения сопоставлений протоколов по умолчанию между схемами транспортного протокола (например, HTTP, net. TCP, net. pipe и т. д.) и привязками Windows Communication Foundation (WCF).|  
  
## <a name="example"></a>Пример  

 В следующем примере конфигурации показано сопоставление протокола по умолчанию в файле machine.config. Это сопоставление по умолчанию можно переопределить на уровне компьютера путем изменения файла machine.config. Или же, если необходимо переопределить это сопоставление только в области приложения, можно отменить этот раздел в файле конфигурации приложения и изменить сопоставление для отдельных схем протокола.  
  
```xml  
<protocolMapping>
  <add scheme="http"
       binding="basicHttpBinding" />
  <add scheme="net.tcp"
       binding="netTcpBinding" />
  <add scheme="net.pipe"
       binding="netNamedPipeBinding" />
  <add scheme="net.msmq"
       binding="netMsmqBinding" />
</protocolMapping>
```  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.ServiceModel.Configuration.ProtocolMappingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Configuration.ProtocolMappingElement?displayProperty=nameWithType>
