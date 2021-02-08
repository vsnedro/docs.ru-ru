---
description: 'Дополнительные сведения <behavior> о: <endpointBehaviors>'
title: <behavior> из <endpointBehaviors>
ms.date: 03/30/2017
ms.assetid: b90ca3bc-3c22-4174-b903-e3a39898bd27
ms.openlocfilehash: a72bb69cce96d72cdc00d48546244bdcde20271f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802337"
---
# <a name="behavior-of-endpointbehaviors"></a>\<behavior> из \<endpointBehaviors>

Элемент `behavior` содержит коллекцию параметров поведения конечной точки. Каждое поведение индексируется по атрибуту `name`. Конечные точки могут ссылаться на каждое поведение по этому имени. Начиная с платформа .NET Framework 4, привязки и поведения не обязательно должны иметь имя. Дополнительные сведения о конфигурации по умолчанию и привязках и поведении, которые не имеют имен, см. в разделе [упрощенная конфигурация](../../../wcf/simplified-configuration.md) и [упрощенная конфигурация для служб WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<behavior>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<system.ServiceModel>
  <behaviors>
    <endpointBehaviors>
      <behavior name="String" />
    </endpointBehaviors>
  </behaviors>
</system.ServiceModel>
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  

 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|name|Уникальная строка, содержащая имя конфигурации поведения. Это значение является заданной пользователем строкой, которая должна быть уникальной, поскольку она действует как строка идентификации для элемента. Начиная с платформа .NET Framework 4, привязки и поведения не обязательно должны иметь имя. Дополнительные сведения о конфигурации по умолчанию и привязках и поведении, которые не имеют имен, см. в разделе [упрощенная конфигурация](../../../wcf/simplified-configuration.md) и [упрощенная конфигурация для служб WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<clientCredentials>](clientcredentials.md)|Задает учетные данные, используемые для проверки подлинности клиента при подключении к службе.|  
|[\<callbackDebug>](callbackdebug.md)|Указывает отладку службы для объекта обратного вызова Windows Communication Foundation (WCF).|  
|[\<callbackTimeouts>](callbacktimeouts.md)|Задает время ожидания для обратного вызова клиента.|  
|[\<clientVia>](clientvia.md)|Задает маршрут, по которому должно быть передано сообщение.|  
|[\<dataContractSerializer>](datacontractserializer.md)|Содержит данные конфигурации для DataContractSerializer.|  
|[\<dispatcherSynchronization>](dispatchersynchronization.md)|Указывает поведение конечной точки, которое позволяет службе отправлять ответы в асинхронном режиме.|  
|[\<enableWebScript>](enablewebscript.md)|Включает поведение конечной точки, позволяющее использовать службу с веб-страниц ASP.NET с поддержкой технологии AJAX. Поведение следует использовать только в сочетании со \<webHttpBinding> стандартной привязкой или с \<webMessageEncoding> элементом Binding.|  
|[\<endpointDiscovery>](endpointdiscovery.md)|Указывает различные параметры обнаружения для конечной точки, такие как возможность обнаружения, области и любые пользовательские модули для ее метаданных.|  
|[\<soapProcessing>](soapprocessing.md)|Определяет поведение конечной точки клиента, используемое для маршалинга сообщений между различными типами привязок и версиями сообщения.|  
|[\<synchronousReceive>](synchronousreceive-element.md)|Задает поведение времени выполнения для получения сообщений в службе или клиентском приложении. Он не имеет атрибутов или дочерних элементов.|  
|[\<transactedBatching>](transactedbatching.md)|Указывает, поддерживается ли объединение транзакций для операций получения.|  
|[\<webHttp>](webhttp.md)|Задает WebHttpBehavior в конечной точке посредством настройки конфигурации. Такое поведение при использовании в сочетании со \<webHttpBinding> стандартной привязкой включает в себя модель веб-программирования для службы WCF.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<endpointBehaviors>](endpointbehaviors.md)|Коллекция элементов поведения конечной точки.|
