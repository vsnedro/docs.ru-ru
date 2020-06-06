---
title: <workflowInstanceQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4fe7ce85-cf9a-4dbf-a8f7-bc9b1fc2fe35
ms.openlocfilehash: 11e301de1ab3dbd4c97f236bfd07c5de4a632272
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398578"
---
# \<workflowInstanceQueries>
<span data-ttu-id="dc8d0-101">Представляет коллекцию элементов конфигурации, которые отслеживают изменения жизненного цикла экземпляра рабочего процесса, например события «запущен» или «завершен».</span><span class="sxs-lookup"><span data-stu-id="dc8d0-101">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>  
  
<span data-ttu-id="dc8d0-102">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="dc8d0-102">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowInstanceQueries>**  
  
## <a name="syntax"></a><span data-ttu-id="dc8d0-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dc8d0-103">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <workflowInstanceQueries>
        <workflowInstanceQuery>
          <states>
            <state name="Name"/>
          </states>
        </workflowInstanceQuery>
      </workflowInstanceQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dc8d0-104">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="dc8d0-104">Attributes and Elements</span></span>  

<span data-ttu-id="dc8d0-105">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="dc8d0-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dc8d0-106">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="dc8d0-106">Attributes</span></span>  

<span data-ttu-id="dc8d0-107">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="dc8d0-107">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="dc8d0-108">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="dc8d0-108">Child Elements</span></span>  
  
|<span data-ttu-id="dc8d0-109">Элемент</span><span class="sxs-lookup"><span data-stu-id="dc8d0-109">Element</span></span>|<span data-ttu-id="dc8d0-110">Описание</span><span class="sxs-lookup"><span data-stu-id="dc8d0-110">Description</span></span>|  
|-------------|-----------------|  
|[\<workflowInstanceQuery>](workflowinstancequery.md)|<span data-ttu-id="dc8d0-111">Запрос, используемый для отслеживания изменений жизненного цикла экземпляра рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="dc8d0-111">A query that is used to track workflow instance life cycle changes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="dc8d0-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="dc8d0-112">Parent Elements</span></span>  
  
|<span data-ttu-id="dc8d0-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="dc8d0-113">Element</span></span>|<span data-ttu-id="dc8d0-114">Описание</span><span class="sxs-lookup"><span data-stu-id="dc8d0-114">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](workflow.md)|<span data-ttu-id="dc8d0-115">Элемент конфигурации, содержащий все запросы для определенного рабочего процесса, определяемого свойством **ActivityDefinitionId** .</span><span class="sxs-lookup"><span data-stu-id="dc8d0-115">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dc8d0-116">Примечания</span><span class="sxs-lookup"><span data-stu-id="dc8d0-116">Remarks</span></span>  

<span data-ttu-id="dc8d0-117">Запрос <xref:System.Activities.Tracking.WorkflowInstanceQuery> используется для подписки на следующие объекты <xref:System.Activities.Tracking.TrackingRecord>.</span><span class="sxs-lookup"><span data-stu-id="dc8d0-117">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="dc8d0-118">Пример</span><span class="sxs-lookup"><span data-stu-id="dc8d0-118">Example</span></span>  

<span data-ttu-id="dc8d0-119">При использовании следующей конфигурации устанавливается подписка на записи отслеживания рабочего процесса на уровне экземпляра для состояния экземпляра `Started` при помощи данного запроса.</span><span class="sxs-lookup"><span data-stu-id="dc8d0-119">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="dc8d0-120">См. также</span><span class="sxs-lookup"><span data-stu-id="dc8d0-120">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="dc8d0-121">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="dc8d0-121">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="dc8d0-122">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="dc8d0-122">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
