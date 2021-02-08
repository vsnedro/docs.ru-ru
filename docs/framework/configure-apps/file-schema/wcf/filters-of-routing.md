---
description: 'Дополнительные сведения <filters> о: <routing>'
title: <filters> из <routing>
ms.date: 03/30/2017
ms.assetid: 7993cf90-9afd-4c3c-9608-184d5da1105c
ms.openlocfilehash: 41b51453f53fca042f53ca1ee8372413b8478ecd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99782056"
---
# <a name="filters-of-routing"></a>\<filters> из \<routing>

Представляет раздел конфигурации для определения набора фильтров маршрутизации, которые определяют тип Windows Communication Foundation (WCF), <xref:System.ServiceModel.Dispatcher.MessageFilter> используемый при оценке входящих сообщений.

[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<filters>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<system.serviceModel>
  <routing>
    <filters>
      <filter customType="String"
              filterData="String"
              filterType="Action/Address/AddressPrefix/And/Custom/Endpoint/MatchAll/XPath"
              name="String" />
    </filters>
  </routing>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a>Элементы и атрибуты

В следующих разделах описаны атрибуты, дочерние и родительские элементы.

### <a name="attributes"></a>Атрибуты

None

### <a name="child-elements"></a>Дочерние элементы

|     | Описание |
| --- | ----------- |
| [**\<filter>**](filter.md) | Содержит фильтр маршрутизации, определяющий тип Windows Communication Foundation (WCF), который <xref:System.ServiceModel.Dispatcher.MessageFilter> будет использоваться при оценке входящих сообщений. |

### <a name="parent-elements"></a>Родительские элементы

|     | Описание |
| --- | ----------- |
| [**\<routing>**](routing.md) | Представляет раздел конфигурации для определения набора фильтров маршрутизации, которые определяют тип Windows Communication Foundation (WCF), <xref:System.ServiceModel.Dispatcher.MessageFilter> используемый при оценке входящих сообщений, а также таблицы маршрутизации, определяющие целевые конечные точки для отправки сообщений при совпадении фильтра. |

## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>
