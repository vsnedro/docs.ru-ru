---
title: <findCriteria>
ms.date: 03/30/2017
ms.assetid: 5454cd19-6bf5-4ba8-94d1-f58d10dc1917
ms.openlocfilehash: ce2b1fdd85e0454f901bac393e2f44ae0c6da43f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91178151"
---
# \<findCriteria>

Элемент конфигурации, который предоставляет набор критериев, используемых клиентским приложением для поиска службы обнаружения. Критерии могут быть сгруппированы в критерии поиска (с указанием искомых служб) и критерии прекращения поиска (как долго должен длиться поиск).  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dynamicEndpoint>**](dynamicendpoint.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<standardEndpoint>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<discoveryClientSettings>**](discoveryclientsettings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<findCriteria>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <dynamicEndpoint>
      <standardEndpoint>
        <discoveryClientSettings discoveryEndpoint="String">
          <findCriteria duration="TimeSpan"
                        maxResults="Integer"
                        scopeMatchBy="Uri">
            <contractTypeNames>
              <add name="String"
                   namespace="String" />
            </contractTypeNames>
            <extensions />
            <scopes>
              <add scope="URI" />
            </scopes>
          </findCriteria>
        </discoveryClientSettings>
      </standardEndpoint>
    </dynamicEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  

 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|длительность|Значение Timespan, указывающее максимальное время ожидания ответа от служб в сети. Значение времени ожидания по умолчанию - 20 секунд.|  
|maxResults|Целочисленное значение, указывающее максимальное количество ответов, ожидаемых от служб по сети или через Интернет. Операция поиска завершается, если максимальное число ответов достигнуто до истечения срока, указанного в атрибуте `duration`.|  
|scopeMatchBy|URI, указывающий алгоритм сопоставления, который используется для сопоставления областей из сообщения зонда с областями из конечной точки.<br /><br /> Поддерживаются пять правил сопоставления областей. Если правило сопоставления областей не указано, используется `ScopeMatchByPrefix`. Дополнительные сведения см. в разделе <xref:System.ServiceModel.Discovery.FindCriteria>.|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<contractTypeNames>](contracttypenames.md)|Коллекция элементов конфигурации, содержащих имена типов контрактов службы рабочего процесса.|  
|\<extensions> из \<findCriteria>|Коллекция объектов элементов XML, предоставляющих расширения.|  
|[\<scopes>](scopes.md)|Коллекция объектов, содержащих абсолютные URI, по которым определяется расположение отдельных служб в ходе операции поиска.<br /><br /> Если найдена определенная служба, URI службы и URI области были успешно сопоставлены, иногда с помощью правил области, предназначенных для преодоления сложностей совпадения.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|Содержит параметры, необходимые приложению для участия в процессе обнаружения служб в качестве клиента.|  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.ServiceModel.Discovery.FindCriteria>
- <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>
