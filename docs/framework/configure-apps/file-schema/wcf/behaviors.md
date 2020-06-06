---
title: <behaviors>
ms.date: 03/30/2017
ms.assetid: 0e5da4e6-1aa5-466c-924e-f10efee57f0b
ms.openlocfilehash: bcdd26f038b343040d81b0add83bf166a5e3151f
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "74139688"
---
# \<behaviors>
Данный элемент определяет две дочерние коллекции с именами `endpointBehaviors` и `serviceBehaviors`.  Каждая коллекция определяет элементы поведений, используемые конечными точками и службами соответственно. Каждый элемент поведения идентифицируется по уникальному атрибуту `name`. Начиная с .NET Framework 4, привязки и поведения не обязательно должны иметь имя. Дополнительные сведения о конфигурации по умолчанию и привязках и поведении, которые не имеют имен, см. в разделе [упрощенная конфигурация](../../../wcf/simplified-configuration.md) и [упрощенная конфигурация для служб WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<behaviors>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<behaviors>
  <serviceBehaviors>
  </serviceBehaviors>
  <endpointBehaviors>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
 Нет  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<endpointBehaviors>](endpointbehaviors.md)|Данный раздел конфигурации представляет все типы поведения, определенные для конкретной конечной точки.|  
|[\<serviceBehaviors>](servicebehaviors.md)|В данном разделе конфигурации представлены все поведения, определенные для конкретной службы.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<system.serviceModel>](system-servicemodel.md)|Корневой элемент всех элементов конфигурации Windows Communication Foundation (WCF).|  
  
## <a name="remarks"></a>Примечания  
 Элемент `<remove>` можно использовать для удаления определенного поведения из коллекции. Для этого нужно просто указать имя удаляемого поведения в атрибуте `name` элемента `<remove>`.  Также можно использовать элемент `<clear>`, очищающий все содержимое коллекции, чтобы обеспечить запуск пустой коллекции.  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Configuration.BehaviorsSection>
- <xref:System.ServiceModel.Configuration.EndpointBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.EndpointBehaviorElement>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>
- [Настройка и расширение среды выполнения с помощью поведений](../../../wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
- [Настройка поведений клиентов](../../../wcf/configuring-client-behaviors.md)
- [Задание поведения клиента во время выполнения](../../../wcf/specifying-client-run-time-behavior.md)
- [Указание поведения службы во время выполнения](../../../wcf/specifying-service-run-time-behavior.md)
- [Поведение безопасности](../../../wcf/feature-details/security-behaviors-in-wcf.md)
