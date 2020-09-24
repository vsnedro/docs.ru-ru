---
title: <workflowInstanceQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4fe7ce85-cf9a-4dbf-a8f7-bc9b1fc2fe35
ms.openlocfilehash: 1b1315aa176f26c356726c5edf1c851bb4c63a47
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148612"
---
# \<workflowInstanceQueries>

<span data-ttu-id="a4c2d-101">Представляет коллекцию элементов конфигурации, которые отслеживают изменения жизненного цикла экземпляра рабочего процесса, например события «запущен» или «завершен».</span><span class="sxs-lookup"><span data-stu-id="a4c2d-101">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>  
  
<span data-ttu-id="a4c2d-102">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="a4c2d-102">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowInstanceQueries>**  
  
## <a name="syntax"></a><span data-ttu-id="a4c2d-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a4c2d-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a4c2d-104">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a4c2d-104">Attributes and Elements</span></span>  

<span data-ttu-id="a4c2d-105">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="a4c2d-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a4c2d-106">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a4c2d-106">Attributes</span></span>  

<span data-ttu-id="a4c2d-107">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="a4c2d-107">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a4c2d-108">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a4c2d-108">Child Elements</span></span>  
  
|<span data-ttu-id="a4c2d-109">Элемент</span><span class="sxs-lookup"><span data-stu-id="a4c2d-109">Element</span></span>|<span data-ttu-id="a4c2d-110">Описание</span><span class="sxs-lookup"><span data-stu-id="a4c2d-110">Description</span></span>|  
|-------------|-----------------|  
|[\<workflowInstanceQuery>](workflowinstancequery.md)|<span data-ttu-id="a4c2d-111">Запрос, используемый для отслеживания изменений жизненного цикла экземпляра рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="a4c2d-111">A query that is used to track workflow instance life cycle changes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a4c2d-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a4c2d-112">Parent Elements</span></span>  
  
|<span data-ttu-id="a4c2d-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="a4c2d-113">Element</span></span>|<span data-ttu-id="a4c2d-114">Описание</span><span class="sxs-lookup"><span data-stu-id="a4c2d-114">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](workflow.md)|<span data-ttu-id="a4c2d-115">Элемент конфигурации, содержащий все запросы для определенного рабочего процесса, определяемого свойством **ActivityDefinitionId** .</span><span class="sxs-lookup"><span data-stu-id="a4c2d-115">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a4c2d-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="a4c2d-116">Remarks</span></span>  

<span data-ttu-id="a4c2d-117">Запрос <xref:System.Activities.Tracking.WorkflowInstanceQuery> используется для подписки на следующие объекты <xref:System.Activities.Tracking.TrackingRecord>.</span><span class="sxs-lookup"><span data-stu-id="a4c2d-117">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="a4c2d-118">Пример</span><span class="sxs-lookup"><span data-stu-id="a4c2d-118">Example</span></span>  

<span data-ttu-id="a4c2d-119">При использовании следующей конфигурации устанавливается подписка на записи отслеживания рабочего процесса на уровне экземпляра для состояния экземпляра `Started` при помощи данного запроса.</span><span class="sxs-lookup"><span data-stu-id="a4c2d-119">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a4c2d-120">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="a4c2d-120">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="a4c2d-121">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="a4c2d-121">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="a4c2d-122">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="a4c2d-122">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
