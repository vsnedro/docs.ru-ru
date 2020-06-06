---
title: <workflowInstanceQueries>WCF
ms.date: 03/30/2017
ms.assetid: b0852f77-16e4-4d55-8eb7-a19feb0e8fc4
ms.openlocfilehash: 8a58767745efab67fb7550de8770fec2c6226117
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70854770"
---
# <a name="workflowinstancequeries-of-wcf"></a><span data-ttu-id="9b9a4-102">\<workflowInstanceQueries>WCF</span><span class="sxs-lookup"><span data-stu-id="9b9a4-102">\<workflowInstanceQueries> of WCF</span></span>

<span data-ttu-id="9b9a4-103">Представляет коллекцию элементов конфигурации, которые отслеживают изменения жизненного цикла экземпляра рабочего процесса, например события «запущен» или «завершен».</span><span class="sxs-lookup"><span data-stu-id="9b9a4-103">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>  
  
<span data-ttu-id="9b9a4-104">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="9b9a4-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowInstanceQueries>**  
  
## <a name="syntax"></a><span data-ttu-id="9b9a4-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9b9a4-105">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <workflowInstanceQueries>
          <workflowInstanceQuery>
            <states>
              <state name="Name" />
            </states>
          </workflowInstanceQuery>
        </workflowInstanceQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9b9a4-106">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="9b9a4-106">Attributes and elements</span></span>

<span data-ttu-id="9b9a4-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="9b9a4-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9b9a4-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="9b9a4-108">Attributes</span></span>  

<span data-ttu-id="9b9a4-109">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="9b9a4-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9b9a4-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="9b9a4-110">Child elements</span></span>  
  
|<span data-ttu-id="9b9a4-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="9b9a4-111">Element</span></span>|<span data-ttu-id="9b9a4-112">Описание</span><span class="sxs-lookup"><span data-stu-id="9b9a4-112">Description</span></span>|  
|-------------|-----------------|  
|[\<workflowInstanceQuery>](workflowinstancequery-of-wcf.md)|<span data-ttu-id="9b9a4-113">Запрос, используемый для отслеживания изменений жизненного цикла экземпляра рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="9b9a4-113">A query that is used to track workflow instance life cycle changes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9b9a4-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="9b9a4-114">Parent elements</span></span>  
  
|<span data-ttu-id="9b9a4-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="9b9a4-115">Element</span></span>|<span data-ttu-id="9b9a4-116">Описание</span><span class="sxs-lookup"><span data-stu-id="9b9a4-116">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="9b9a4-117">Элемент конфигурации, содержащий все запросы для определенного рабочего процесса, определяемого свойством [ActivityDefinitionId](xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId) .</span><span class="sxs-lookup"><span data-stu-id="9b9a4-117">A configuration element that contains all queries for a specific workflow identified by the [activityDefinitionId](xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId) property.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9b9a4-118">Примечания</span><span class="sxs-lookup"><span data-stu-id="9b9a4-118">Remarks</span></span>

<span data-ttu-id="9b9a4-119">Запрос <xref:System.Activities.Tracking.WorkflowInstanceQuery> используется для подписки на следующие объекты <xref:System.Activities.Tracking.TrackingRecord>.</span><span class="sxs-lookup"><span data-stu-id="9b9a4-119">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="9b9a4-120">Пример</span><span class="sxs-lookup"><span data-stu-id="9b9a4-120">Example</span></span>  

<span data-ttu-id="9b9a4-121">При использовании следующей конфигурации устанавливается подписка на записи отслеживания рабочего процесса на уровне экземпляра для состояния экземпляра `Started` при помощи данного запроса.</span><span class="sxs-lookup"><span data-stu-id="9b9a4-121">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>
  <workflowInstanceQuery>
    <states>
      <state name="Started" />
    </states>
  </workflowInstanceQuery>
</workflowInstanceQueries>
```  
  
## <a name="see-also"></a><span data-ttu-id="9b9a4-122">См. также</span><span class="sxs-lookup"><span data-stu-id="9b9a4-122">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="9b9a4-123">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="9b9a4-123">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="9b9a4-124">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="9b9a4-124">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
