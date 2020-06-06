---
title: <state> из <states>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ab483c7f-a091-4933-ba6b-708d96846d38
ms.openlocfilehash: 391e552bce34d637a324c78702cb0e7121f2c999
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398655"
---
# <a name="state-of-states"></a><span data-ttu-id="7d8a9-102">\<state> из \<states></span><span class="sxs-lookup"><span data-stu-id="7d8a9-102">\<state> of \<states></span></span>
<span data-ttu-id="7d8a9-103">Элемент конфигурации, содержащий состояние подписанного действия, для которого необходимо создать запись отслеживания.</span><span class="sxs-lookup"><span data-stu-id="7d8a9-103">A configuration element that contains the state of the subscribed activity for which a tracking record should be emitted.</span></span>  
  
 <span data-ttu-id="7d8a9-104">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="7d8a9-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQueries>**](activitystatequeries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQuery>**](activitystatequery.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<states>**](states-of-activitystatequery.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<state>**  
  
## <a name="syntax"></a><span data-ttu-id="7d8a9-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7d8a9-105">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <states>
          <state name="String" />
        </states>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7d8a9-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="7d8a9-106">Attributes and Elements</span></span>  
 <span data-ttu-id="7d8a9-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="7d8a9-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7d8a9-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="7d8a9-108">Attributes</span></span>  
  
|<span data-ttu-id="7d8a9-109">Атрибут</span><span class="sxs-lookup"><span data-stu-id="7d8a9-109">Attribute</span></span>|<span data-ttu-id="7d8a9-110">Описание</span><span class="sxs-lookup"><span data-stu-id="7d8a9-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7d8a9-111">name</span><span class="sxs-lookup"><span data-stu-id="7d8a9-111">name</span></span>|<span data-ttu-id="7d8a9-112">Строка, содержащая состояние подписанного действия, для которого необходимо создать запись отслеживания.</span><span class="sxs-lookup"><span data-stu-id="7d8a9-112">A string that specifies the state of the subscribed activity for which a tracking record should be emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7d8a9-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="7d8a9-113">Child Elements</span></span>  
 <span data-ttu-id="7d8a9-114">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="7d8a9-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7d8a9-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="7d8a9-115">Parent Elements</span></span>  
  
|<span data-ttu-id="7d8a9-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="7d8a9-116">Element</span></span>|<span data-ttu-id="7d8a9-117">Описание</span><span class="sxs-lookup"><span data-stu-id="7d8a9-117">Description</span></span>|  
|-------------|-----------------|  
|[\<states>](states-of-activitystatequery.md)|<span data-ttu-id="7d8a9-118">Коллекция элементов конфигурации, содержащих состояния действия, на которое установлена подписка и для которого необходимо создать запись отслеживания.</span><span class="sxs-lookup"><span data-stu-id="7d8a9-118">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7d8a9-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="7d8a9-119">Remarks</span></span>  
 <span data-ttu-id="7d8a9-120">Уникальной возможностью ActivityStateQuery является возможность извлекать данные во время отслеживания выполнения рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="7d8a9-120">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="7d8a9-121">Это обеспечивает дополнительный контекст при доступе к записям отслеживания после выполнения.</span><span class="sxs-lookup"><span data-stu-id="7d8a9-121">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="7d8a9-122">Можно использовать [\<arguments>](arguments.md) [\<states>](states.md) элементы, и [\<states>](states.md) для извлечения любой переменной или аргумента из любого действия в рабочем процессе.</span><span class="sxs-lookup"><span data-stu-id="7d8a9-122">You can use the [\<arguments>](arguments.md), [\<states>](states.md) and [\<states>](states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="7d8a9-123">В следующем примере показан запрос состояния действия, который извлекает переменные и аргументы при создании записи отслеживания действия `Closed`.</span><span class="sxs-lookup"><span data-stu-id="7d8a9-123">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="7d8a9-124">Переменные и аргументы могут извлекаться только с помощью Активитистатерекорд, поэтому они подписываются в профиле отслеживания с помощью [\<activityStateQuery>](activitystatequery.md) .</span><span class="sxs-lookup"><span data-stu-id="7d8a9-124">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](activitystatequery.md).</span></span>  
  
```xml  
<activityStateQuery activityName="SendEmailActivity">  
  <states>  
    <state name="Closed"/>  
  </states>  
  <variables>  
    <variable name="FromAddress"/>  
  </variables>  
  <arguments>  
    <argument name="Result"/>  
  </arguments>  
</activityStateQuery>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7d8a9-125">См. также</span><span class="sxs-lookup"><span data-stu-id="7d8a9-125">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="7d8a9-126">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="7d8a9-126">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="7d8a9-127">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="7d8a9-127">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
