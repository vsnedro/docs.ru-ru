---
title: <variable>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 46cc8cbc-10ec-4625-8813-3f5cd6c6afde
ms.openlocfilehash: 5878720f51f4b5cfe3163abf316a867ccda31342
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70397767"
---
# \<variable>
<span data-ttu-id="16da2-101">Представляет коллекцию переменных, связанных с этим запросом действия.</span><span class="sxs-lookup"><span data-stu-id="16da2-101">Represents a collection of variables associated with this activity query.</span></span>  
  
 <span data-ttu-id="16da2-102">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="16da2-102">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQueries>**](activitystatequeries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQuery>**](activitystatequery.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<variables>**](variables.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<variable>**  
  
## <a name="syntax"></a><span data-ttu-id="16da2-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="16da2-103">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <variables>
          <variable name="String" />
        </variables>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="16da2-104">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="16da2-104">Attributes and Elements</span></span>  
 <span data-ttu-id="16da2-105">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="16da2-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="16da2-106">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="16da2-106">Attributes</span></span>  
  
|<span data-ttu-id="16da2-107">Атрибут</span><span class="sxs-lookup"><span data-stu-id="16da2-107">Attribute</span></span>|<span data-ttu-id="16da2-108">Описание</span><span class="sxs-lookup"><span data-stu-id="16da2-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="16da2-109">name</span><span class="sxs-lookup"><span data-stu-id="16da2-109">name</span></span>|<span data-ttu-id="16da2-110">Строка, задающая имя переменной.</span><span class="sxs-lookup"><span data-stu-id="16da2-110">A string that specifies the name of the variable.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="16da2-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="16da2-111">Child Elements</span></span>  
 <span data-ttu-id="16da2-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="16da2-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="16da2-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="16da2-113">Parent Elements</span></span>  
  
|<span data-ttu-id="16da2-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="16da2-114">Element</span></span>|<span data-ttu-id="16da2-115">Описание</span><span class="sxs-lookup"><span data-stu-id="16da2-115">Description</span></span>|  
|-------------|-----------------|  
|[\<variable>](variable.md)|<span data-ttu-id="16da2-116">Переменная, связанная с запросом состояния действия.</span><span class="sxs-lookup"><span data-stu-id="16da2-116">A variable associated with an activity state query.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="16da2-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="16da2-117">Remarks</span></span>  
 <span data-ttu-id="16da2-118">Уникальной возможностью ActivityStateQuery является возможность извлекать данные во время отслеживания выполнения рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="16da2-118">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="16da2-119">Это обеспечивает дополнительный контекст при доступе к записям отслеживания после выполнения.</span><span class="sxs-lookup"><span data-stu-id="16da2-119">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="16da2-120">Можно использовать [\<arguments>](arguments.md) [\<states>](states.md) элементы, и [\<states>](states.md) для извлечения любой переменной или аргумента из любого действия в рабочем процессе.</span><span class="sxs-lookup"><span data-stu-id="16da2-120">You can use the [\<arguments>](arguments.md), [\<states>](states.md) and [\<states>](states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="16da2-121">В следующем примере показан запрос состояния действия, который извлекает переменные и аргументы при создании записи отслеживания действия `Closed`.</span><span class="sxs-lookup"><span data-stu-id="16da2-121">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="16da2-122">Переменные и аргументы могут извлекаться только с помощью Активитистатерекорд, поэтому они подписываются в профиле отслеживания с помощью [\<activityStateQuery>](activitystatequery.md) .</span><span class="sxs-lookup"><span data-stu-id="16da2-122">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="16da2-123">См. также</span><span class="sxs-lookup"><span data-stu-id="16da2-123">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.VariableElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="16da2-124">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="16da2-124">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="16da2-125">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="16da2-125">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
