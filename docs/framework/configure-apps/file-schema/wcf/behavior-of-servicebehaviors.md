---
title: <behavior> из <serviceBehaviors>
ms.date: 03/30/2017
ms.assetid: 78fc0a08-55de-416a-ac12-a5e6ffc9a987
ms.openlocfilehash: 115f94fc3f17dc5b4dd1ee3a090f2c9d121f810b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "74139730"
---
# <a name="behavior-of-servicebehaviors"></a>\<behavior> из \<serviceBehaviors>
Элемент `behavior` содержит коллекцию параметров для поведения службы. Каждое поведение индексируется по атрибуту `name`. Службы могут ссылаться на каждое поведение с помощью этого имени, используя `behaviorConfiguration` атрибут [\<endpoint>](endpoint-element.md) элемента. Это позволяет конечным точкам иметь общие конфигурации поведений без переопределения параметров. Начиная с .NET Framework 4, привязки и поведения не обязательно должны иметь имя. Дополнительные сведения о конфигурации по умолчанию и привязках и поведении, которые не имеют имен, см. в разделе [упрощенная конфигурация](../../../wcf/simplified-configuration.md) и [упрощенная конфигурация для служб WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).  
  
> [!NOTE]
> Элементы поведения, относящиеся к действиям рабочего процесса Windows, таким как [\<sendMessageChannelCache>](../windows-workflow-foundation/sendmessagechannelcache.md) элемент, описаны на [ \<behavior> \<serviceBehaviors> ](../windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md) странице.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<behavior>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<system.ServiceModel>
  <behaviors>
    <serviceBehaviors>
       <behavior name="String" />
    </serviceBehaviors>
  </behaviors>
</system.ServiceModel>
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|name|Уникальная строка, содержащая имя конфигурации поведения. Это значение является заданной пользователем строкой, которая должна быть уникальной, поскольку она действует как строка идентификации для элемента. Начиная с .NET Framework 4, привязки и поведения не обязательно должны иметь имя. Дополнительные сведения о конфигурации по умолчанию и привязках и поведении, которые не имеют имен, см. в разделе [упрощенная конфигурация](../../../wcf/simplified-configuration.md) и [упрощенная конфигурация для служб WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<dataContractSerializer>](datacontractserializer-element.md)|Содержит данные конфигурации для DataContractSerializer.|  
|[\<persistenceProvider>](persistenceprovider.md)|Задает тип используемой реализации поставщика сохраняемости, а также время ожидания операций сохраняемости.|  
|[\<routing>](routing-of-servicebehavior.md)|Обеспечивает доступ к службе маршрутизации во время выполнения, чтобы вносить динамические изменения в конфигурацию маршрутизации.|  
|[\<serviceAuthenticationManager>](serviceauthenticationmanager.md)|Обеспечивает элемент конфигурации рабочего процесса, который устанавливает на уровне службы действительность передачи, сообщения или инициатора.|  
|[\<serviceAuthorization>](serviceauthorization-element.md)|Задает параметры авторизации доступа к операциям службы.|  
|[\<serviceCredentials>](servicecredentials.md)|Задает учетные данные, используемые при проверке подлинности службы, а также параметры, относящиеся к проверке учетных данных клиента.|  
|[\<serviceDebug>](servicedebug.md)|Указывает функции отладки и справочной информации для службы Windows Communication Foundation (WCF).|  
|[\<serviceDiscovery>](servicediscovery.md)|Указывает возможность обнаружения конечных точек службы.|  
|[\<serviceMetadata>](servicemetadata.md)|Задает публикацию метаданных службы и связанных сведений.|  
|[\<serviceSecurityAudit>](servicesecurityaudit.md)|Задает параметры, позволяющие проводить аудит событий безопасности во время обслуживания.|  
|[\<serviceThrottling>](servicethrottling.md)|Указывает механизм регулирования службы WCF.|  
|[\<serviceTimeouts>](servicetimeouts.md)|Задает время ожидания для службы.|  
|[\<workflowRuntime>](workflowruntime.md)|Задает параметры для экземпляра WorkflowRuntime для размещения служб WCF на основе рабочих процессов.|  
|[\<useRequestHeadersForMetadataAddress>](userequestheadersformetadataaddress.md)|Включает получение сведений об адресе метаданных из заголовков сообщений запросов.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<serviceBehaviors>](servicebehaviors.md)|Коллекция элементов поведений службы.|
