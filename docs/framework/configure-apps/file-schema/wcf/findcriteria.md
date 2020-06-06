---
title: <findCriteria>
ms.date: 03/30/2017
ms.assetid: 5454cd19-6bf5-4ba8-94d1-f58d10dc1917
ms.openlocfilehash: 44e068ee205bc5e04382164e7ab00716b2c07dcf
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855167"
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
  
|Атрибут|Описание:|  
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
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Discovery.FindCriteria>
- <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>
