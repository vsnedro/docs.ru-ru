---
title: <argument>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: a7144d53-8023-4e90-971f-895e016fd58a
ms.openlocfilehash: 72a2d6f8439e720bb7bf236bd942552224e85501
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91189731"
---
# \<argument>

<span data-ttu-id="beff5-101">Элемент конфигурации, который представляет аргумент, связанный с запросом состояния действия.</span><span class="sxs-lookup"><span data-stu-id="beff5-101">A configuration element that represents an argument associated with an activity state query.</span></span>  
  
 <span data-ttu-id="beff5-102">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="beff5-102">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQueries>**](activitystatequeries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQuery>**](activitystatequery.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<arguments>**](arguments.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<argument>**  
  
## <a name="syntax"></a><span data-ttu-id="beff5-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="beff5-103">Syntax</span></span>  
  
```xml
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <arguments>
          <argument name="String"/>
        </arguments>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="beff5-104">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="beff5-104">Attributes and Elements</span></span>  

 <span data-ttu-id="beff5-105">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="beff5-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="beff5-106">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="beff5-106">Attributes</span></span>  
  
|<span data-ttu-id="beff5-107">Атрибут</span><span class="sxs-lookup"><span data-stu-id="beff5-107">Attribute</span></span>|<span data-ttu-id="beff5-108">Описание</span><span class="sxs-lookup"><span data-stu-id="beff5-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="beff5-109">name</span><span class="sxs-lookup"><span data-stu-id="beff5-109">name</span></span>|<span data-ttu-id="beff5-110">Строка, задающая имя аргумента.</span><span class="sxs-lookup"><span data-stu-id="beff5-110">A string that specifies the name of the argument.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="beff5-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="beff5-111">Child Elements</span></span>  

 <span data-ttu-id="beff5-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="beff5-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="beff5-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="beff5-113">Parent Elements</span></span>  
  
|<span data-ttu-id="beff5-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="beff5-114">Element</span></span>|<span data-ttu-id="beff5-115">Описание</span><span class="sxs-lookup"><span data-stu-id="beff5-115">Description</span></span>|  
|-------------|-----------------|  
|[\<arguments>](arguments.md)|<span data-ttu-id="beff5-116">Коллекция аргументов, связанных с этим запросом действия.</span><span class="sxs-lookup"><span data-stu-id="beff5-116">A collection of arguments associated with this activity query.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="beff5-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="beff5-117">Remarks</span></span>  

 <span data-ttu-id="beff5-118">Уникальной возможностью ActivityStateQuery является возможность извлекать данные во время отслеживания выполнения рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="beff5-118">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="beff5-119">Это обеспечивает дополнительный контекст при доступе к записям отслеживания после выполнения.</span><span class="sxs-lookup"><span data-stu-id="beff5-119">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="beff5-120">Можно использовать [\<arguments>](arguments.md) [\<states>](states.md) элементы, и [\<states>](states.md) для извлечения любой переменной или аргумента из любого действия в рабочем процессе.</span><span class="sxs-lookup"><span data-stu-id="beff5-120">You can use the [\<arguments>](arguments.md), [\<states>](states.md) and [\<states>](states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="beff5-121">В следующем примере показан запрос состояния действия, который извлекает переменные и аргументы при создании записи отслеживания действия `Closed`.</span><span class="sxs-lookup"><span data-stu-id="beff5-121">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="beff5-122">Переменные и аргументы могут извлекаться только с помощью Активитистатерекорд, поэтому они подписываются в профиле отслеживания с помощью [\<activityStateQuery>](activitystatequery.md) .</span><span class="sxs-lookup"><span data-stu-id="beff5-122">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="beff5-123">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="beff5-123">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ArgumentElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="beff5-124">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="beff5-124">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="beff5-125">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="beff5-125">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
