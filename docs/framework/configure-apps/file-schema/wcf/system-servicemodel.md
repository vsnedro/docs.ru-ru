---
title: <system.serviceModel>
description: Сведения об элементах конфигурации WCF ServiceModel, которые позволяют настроить службу WCF и клиентские приложения.
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.ServiceModel
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.ServiceModel
helpviewer_keywords:
- <system.serviceModel> element
- system.serviceModel element
ms.assetid: 78519531-ad7a-40d3-b3e7-42f1103d8854
ms.openlocfilehash: 567cbd2cc07ee82e795daa067b9034b2b8dc1974
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85243962"
---
# \<system.serviceModel>
Этот раздел конфигурации содержит все элементы конфигурации Windows Communication Foundation (WCF) ServiceModel.  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;**\<system.serviceModel>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<system.serviceModel>
  <behaviors>
  </behaviors>
  <bindings>
  </bindings>
  <client>
  </client>
  <comContracts>
  </comContracts>
  <commonBehaviors>
  </commonBehaviors>
  <diagnostics>
  </diagnostics>
  <extensions>
  </extensions>
  <protocolMapping>
  </protocolMapping>
  <routing>
  </routing>
  <serviceHostingEnvironment>
  </serviceHostingEnvironment>
  <services>
  </services>
  <standardEndpoints>
  </standardEndpoints>
  <tracking>
  </tracking>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
 Отсутствуют  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<behaviors>](behaviors.md)|Данный раздел определяет две дочерние коллекции с именами `endpointBehaviors` и `serviceBehaviors`.  Каждая коллекция определяет элементы поведений, используемые конечными точками и службами соответственно. Каждый элемент поведения идентифицируется по уникальному атрибуту `name`.|  
|[\<bindings>](bindings.md)|В этом разделе содержится коллекция стандартных и пользовательских привязок. Каждая запись идентифицируется по уникальному свойству `name`. Службы используют привязки, связывая их с помощью параметра `name`.|  
|[\<client>](client.md)|Данный раздел содержит список конечных точек, которые клиент использует для подключения к службе.|  
|[\<comContracts>](comcontracts.md)|В данном разделе определяются контракты COM, которые разрешены для обеспечения взаимодействия WCF и COM.|  
|[\<commonBehaviors>](commonbehaviors.md)|Этот раздел может быть определен только в файле machine.config. В нем определяются две дочерние коллекции с именами `endpointBehaviors` и `serviceBehaviors`.  Каждая коллекция определяет элементы поведения, используемые всеми конечными точками и службами WCF на компьютере соответственно.  Если поведение определяется как в разделе `<commonBehaviors>`, так и в разделе `<behaviors>`, преимущество имеет поведение в разделе \<behaviors>.|  
|[\<diagnostics>](diagnostics.md)|В этом разделе содержатся параметры возможностей диагностики WCF. Пользователь может включить или отключить трассировку, счетчики производительности и провайдер инструментария WMI, а также может добавлять специальные фильтры сообщений.|  
|[\<extensions>](extensions-section.md)|Данный раздел содержит коллекцию расширений, которые позволяют пользователю создавать определяемые пользователем привязки, поведения и другие виды расширений.|  
|[\<protocolMapping>](protocolmapping.md)|Это раздел определяет набор сопоставления протоколов по умолчанию между схемами транспортных протоколов (например, http, net.tcp, net.pipe и т. д.) и привязками WCF.|  
|[\<routing>](routing.md)|В этом разделе определяется набор фильтров маршрутизации, которые определяют тип Windows Communication Foundation (WCF), <xref:System.ServiceModel.Dispatcher.MessageFilter> используемый при оценке входящих сообщений, а также таблицы маршрутизации, определяющие целевые конечные точки для отправки сообщений при совпадении фильтра.|  
|[\<serviceHostingEnvironment>](servicehostingenvironment.md)|Этот раздел определяет тип, который среда размещения служб создает для определенного транспорта. Если данный раздел пуст, то используется тип, заданный по умолчанию.|  
|[\<services>](services.md)|Раздел содержит коллекцию служб. Для каждой службы, определенной в сборке, данный элемент содержит элемент `service`, который задает параметры для данной службы.|  
|[\<standardEndpoints>](standardendpoints.md)|В этом разделе определяется коллекция конечных точек, которые являются пригодными для многократного использования стандартными конечными точками. Значение одного или нескольких атрибутов стандартной конечной точки, обозначающих адрес, привязку или контракт, является фиксированным. Например, в конечной точке обнаружения фиксированным является контракт. По аналогии с определением пользовательских привязок можно также использовать стандартные конечные точки для расширения конечной точки службы за счет новых свойств.|
|[\<tracking>](tracking-of-wcf.md)|В этом разделе определяются параметры отслеживания для службы рабочего процесса.|

### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|\<configuration>|Корневой элемент для всех элементов конфигурации в файле конфигурации .NET.|  
  
## <a name="remarks"></a>Комментарии  
 WCF не добавляет элементы в разделы конфигурации других продуктов.  
  
 Службы WCF определяются в `services` разделе файла конфигурации. Сборка может содержать любое число служб. Для каждой службы используется собственный раздел конфигурации `service`. Этот раздел и его содержимое определяют контракт, поведение и конечные точки конкретной службы.  
  
 Обязательным является только атрибут `name`.  По умолчанию имя службы описывает базовый тип CLR, который используется для реализации службы, однако можно изменить свойство ConfigurationName в классе <xref:System.ServiceModel.ServiceContractAttribute>, чтобы изменить требования к типу CLR.  
  
 Атрибут `behaviorConfiguration` является необязательным. Он указывает поведение, используемое службой. Поведение, которое определяется данным атрибутом, должно быть связано с поведением службы, которое определяется в области того же файла конфигурации (то есть в том же файле или в родительском файле).  
  
 Каждая служба предоставляет одну или несколько конечных точек, которые определяются в элементе `endpoint`. Каждая конечная точка имеет свой адрес и привязку. Все привязки в файле конфигурации должны быть определены в области файла.  
  
 Привязки связаны с конечными точками через сочетание атрибутов `name` и `bindingConfiguration`. Атрибут `binding` указывает, в каком разделе определяется привязка. Атрибут `bindingConfiguration` указывает, какая из настроенных привязок используется в разделе привязки. В разделе привязки может определяться несколько настроенных привязок.  
  
## <a name="example"></a>Пример  
 Ниже приведен пример файла конфигурации WCF.  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <system.serviceModel>
    <behaviors>
      <!-- List of Behaviors -->
    </behaviors>
    <client>
      <!-- List of Endpoints -->
    </client>
    <diagnostics wmiProviderEnabled="false"
                 performanceCountersEnabled="false"
                 tracingEnabled="false">
    </diagnostics>
    <serviceHostingEnvironment>
      <!-- List of entries -->
    </serviceHostingEnvironment>
    <comContracts>
      <!-- List of COM+ Contracts -->
    </comContracts>
    <services>
      <!-- List of Services -->
    </services>
    <bindings>
      <!-- List of Bindings -->
    </bindings>
  </system.serviceModel>
</configuration>
```  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Configuration.ServiceModelSectionGroup>
