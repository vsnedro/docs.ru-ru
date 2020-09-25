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

<span data-ttu-id="83a95-101">Элемент конфигурации, который предоставляет набор критериев, используемых клиентским приложением для поиска службы обнаружения.</span><span class="sxs-lookup"><span data-stu-id="83a95-101">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="83a95-102">Критерии могут быть сгруппированы в критерии поиска (с указанием искомых служб) и критерии прекращения поиска (как долго должен длиться поиск).</span><span class="sxs-lookup"><span data-stu-id="83a95-102">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dynamicEndpoint>**](dynamicendpoint.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<standardEndpoint>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<discoveryClientSettings>**](discoveryclientsettings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<findCriteria>**  
  
## <a name="syntax"></a><span data-ttu-id="83a95-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="83a95-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="83a95-104">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="83a95-104">Attributes and Elements</span></span>  

 <span data-ttu-id="83a95-105">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="83a95-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="83a95-106">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="83a95-106">Attributes</span></span>  
  
|<span data-ttu-id="83a95-107">Атрибут</span><span class="sxs-lookup"><span data-stu-id="83a95-107">Attribute</span></span>|<span data-ttu-id="83a95-108">Описание</span><span class="sxs-lookup"><span data-stu-id="83a95-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="83a95-109">длительность</span><span class="sxs-lookup"><span data-stu-id="83a95-109">duration</span></span>|<span data-ttu-id="83a95-110">Значение Timespan, указывающее максимальное время ожидания ответа от служб в сети.</span><span class="sxs-lookup"><span data-stu-id="83a95-110">A Timespan value that specifies the maximum time to wait for replies from services on the network.</span></span> <span data-ttu-id="83a95-111">Значение времени ожидания по умолчанию - 20 секунд.</span><span class="sxs-lookup"><span data-stu-id="83a95-111">The default duration is 20 seconds.</span></span>|  
|<span data-ttu-id="83a95-112">maxResults</span><span class="sxs-lookup"><span data-stu-id="83a95-112">maxResults</span></span>|<span data-ttu-id="83a95-113">Целочисленное значение, указывающее максимальное количество ответов, ожидаемых от служб по сети или через Интернет.</span><span class="sxs-lookup"><span data-stu-id="83a95-113">An integer that specifies the maximum number of replies to wait for, from services on a network or the Internet.</span></span> <span data-ttu-id="83a95-114">Операция поиска завершается, если максимальное число ответов достигнуто до истечения срока, указанного в атрибуте `duration`.</span><span class="sxs-lookup"><span data-stu-id="83a95-114">If maximum replies are received before the value specified in the `duration` attribute has elapsed, the find operation ends.</span></span>|  
|<span data-ttu-id="83a95-115">scopeMatchBy</span><span class="sxs-lookup"><span data-stu-id="83a95-115">scopeMatchBy</span></span>|<span data-ttu-id="83a95-116">URI, указывающий алгоритм сопоставления, который используется для сопоставления областей из сообщения зонда с областями из конечной точки.</span><span class="sxs-lookup"><span data-stu-id="83a95-116">A URI that specify the matching algorithm to use while matching the scopes in the Probe message with that of the endpoint.</span></span><br /><br /> <span data-ttu-id="83a95-117">Поддерживаются пять правил сопоставления областей.</span><span class="sxs-lookup"><span data-stu-id="83a95-117">There are five supported scope-matching rules.</span></span> <span data-ttu-id="83a95-118">Если правило сопоставления областей не указано, используется `ScopeMatchByPrefix`.</span><span class="sxs-lookup"><span data-stu-id="83a95-118">If you do not specify a scope-matching rule, `ScopeMatchByPrefix` is used.</span></span> <span data-ttu-id="83a95-119">Дополнительные сведения см. в разделе <xref:System.ServiceModel.Discovery.FindCriteria>.</span><span class="sxs-lookup"><span data-stu-id="83a95-119">For more information on this, see <xref:System.ServiceModel.Discovery.FindCriteria>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="83a95-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="83a95-120">Child Elements</span></span>  
  
|<span data-ttu-id="83a95-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="83a95-121">Element</span></span>|<span data-ttu-id="83a95-122">Описание</span><span class="sxs-lookup"><span data-stu-id="83a95-122">Description</span></span>|  
|-------------|-----------------|  
|[\<contractTypeNames>](contracttypenames.md)|<span data-ttu-id="83a95-123">Коллекция элементов конфигурации, содержащих имена типов контрактов службы рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="83a95-123">A collection of configuration elements that contain the names of workflow service contract types.</span></span>|  
|<span data-ttu-id="83a95-124">\<extensions> из \<findCriteria></span><span class="sxs-lookup"><span data-stu-id="83a95-124">\<extensions> of \<findCriteria></span></span>|<span data-ttu-id="83a95-125">Коллекция объектов элементов XML, предоставляющих расширения.</span><span class="sxs-lookup"><span data-stu-id="83a95-125">A collection of XML element objects that provide extensions.</span></span>|  
|[\<scopes>](scopes.md)|<span data-ttu-id="83a95-126">Коллекция объектов, содержащих абсолютные URI, по которым определяется расположение отдельных служб в ходе операции поиска.</span><span class="sxs-lookup"><span data-stu-id="83a95-126">A collection of objects that contain absolute URIs that are used during a find operation to locate a specific service or services.</span></span><br /><br /> <span data-ttu-id="83a95-127">Если найдена определенная служба, URI службы и URI области были успешно сопоставлены, иногда с помощью правил области, предназначенных для преодоления сложностей совпадения.</span><span class="sxs-lookup"><span data-stu-id="83a95-127">If the specific service is found, a successful match has been made between the service URI and the Scope URI, sometimes with the help of scope rules that handle complications of matching.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="83a95-128">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="83a95-128">Parent Elements</span></span>  
  
|<span data-ttu-id="83a95-129">Элемент</span><span class="sxs-lookup"><span data-stu-id="83a95-129">Element</span></span>|<span data-ttu-id="83a95-130">Описание</span><span class="sxs-lookup"><span data-stu-id="83a95-130">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="83a95-131">Содержит параметры, необходимые приложению для участия в процессе обнаружения служб в качестве клиента.</span><span class="sxs-lookup"><span data-stu-id="83a95-131">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="83a95-132">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="83a95-132">See also</span></span>

- <xref:System.ServiceModel.Discovery.FindCriteria>
- <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>
