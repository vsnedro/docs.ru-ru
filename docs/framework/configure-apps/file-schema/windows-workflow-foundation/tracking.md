---
title: <tracking>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: fd9b50ed-98a1-4518-836d-e4e02c670822
ms.openlocfilehash: 968cfa8e5402458afd6f13545ed999a472adf2e0
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "79151914"
---
# \<tracking>
<span data-ttu-id="e91b3-101">Представляет раздел конфигурации для определения настроек отслеживания для службы рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="e91b3-101">Represents a configuration section for defining tracking settings for a workflow service.</span></span>  
  
 <span data-ttu-id="e91b3-102">Дополнительные сведения об отслеживании рабочих процессов и его конфигурации см. в разделе Отслеживание рабочего процесса [и трассировка](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) и [Настройка отслеживания рабочего процесса](../../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="e91b3-102">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Configuring Tracking for a Workflow](../../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<tracking>**  
  
## <a name="syntax"></a><span data-ttu-id="e91b3-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e91b3-103">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <tracking>
    <profiles>
      <participants>
        <add name="String"
             profileName="String"
             type="String" />
      </participants>
      <trackingProfile name="String">
        <workflow activityDefinitionId="String">
          <activityScheduledQueries>
            <activityScheduledQuery activityName="String"
                                    childActivityName="String"/>
          </activityScheduledQueries>
          <activityStateQueries>
            <activityStateQuery activityName="String" />
            <arguments>
              <argument name="String" />
            </arguments>
            <states>
              <state name="String"  />
            </states>
            <variables>
              <variable name="String" />
            </variables>
          </activityStateQueries>
          <bookmarkResumptionQueries>
            <bookmarkResumptionQuery name="String" />
          </bookmarkResumptionQueries>
          <cancelRequestQueries>
            <cancelRequestQuery activityName="String"
                                childActivityName="String"/>
          </cancelRequestQueries>
          <customTrackingQueries>
            <customTrackingQuery activityName="String"
                                 name="String"/>
          </customTrackingQueries>
          <faultPropagationQueries>
            <faultPropagationQuery activityName="String"
                                   faultHandlerActivityName="String" />
          </faultPropagationQueries>
          <workflowInstanceQueries>
            <workflowInstanceQuery>
              <states>
                <state name="String" />
              </states>
            </workflowInstanceQuery>
          </workflowInstanceQueries>
        </workflow>
      </trackingProfile>
    </profiles>
  </tracking>
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e91b3-104">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e91b3-104">Attributes and Elements</span></span>  
 <span data-ttu-id="e91b3-105">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e91b3-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e91b3-106">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e91b3-106">Attributes</span></span>  
 <span data-ttu-id="e91b3-107">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="e91b3-107">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e91b3-108">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e91b3-108">Child Elements</span></span>  
  
|<span data-ttu-id="e91b3-109">Элемент</span><span class="sxs-lookup"><span data-stu-id="e91b3-109">Element</span></span>|<span data-ttu-id="e91b3-110">Описание</span><span class="sxs-lookup"><span data-stu-id="e91b3-110">Description</span></span>|  
|-------------|-----------------|  
|[\<participants>](participants.md)|<span data-ttu-id="e91b3-111">Коллекция элементов конфигурации, которые определяют участников, подписанных на записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="e91b3-111">A collection of configuration elements defining participants that subscribe to tracking records.</span></span> <span data-ttu-id="e91b3-112">Участники содержат логику обработки полезных данных из записей отслеживания (например, они могут записать данные в файл).</span><span class="sxs-lookup"><span data-stu-id="e91b3-112">The tracking participants contain the logic to process the payload from the tracking records (for example, they could choose to write to a file).</span></span>|  
|[\<trackingProfile>](trackingprofile.md)|<span data-ttu-id="e91b3-113">Профиль отслеживания для фильтрации записей отслеживания, выдаваемых экземпляром рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="e91b3-113">A tracking profile to filter tracking records emitted from a workflow instance.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e91b3-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e91b3-114">Parent Elements</span></span>  
  
|<span data-ttu-id="e91b3-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="e91b3-115">Element</span></span>|<span data-ttu-id="e91b3-116">Описание</span><span class="sxs-lookup"><span data-stu-id="e91b3-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e91b3-117">system.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="e91b3-117">system.ServiceModel</span></span>|<span data-ttu-id="e91b3-118">Корневой элемент всех элементов конфигурации рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="e91b3-118">The root element of all workflow configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e91b3-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="e91b3-119">Remarks</span></span>  
 <span data-ttu-id="e91b3-120">Отслеживание позволяет исследовать выполнение рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="e91b3-120">Tracking provides you with the ability to examine the execution of a workflow.</span></span> <span data-ttu-id="e91b3-121">Инфраструктура отслеживания рабочего процесса инструментирует процесс таким образом, что выдаются записи, отражающие ключевые события выполнения.</span><span class="sxs-lookup"><span data-stu-id="e91b3-121">The workflow tracking infrastructure instruments a workflow to emit records reflecting key events during the execution.</span></span> <span data-ttu-id="e91b3-122">Например, записи отслеживания создаются при запуске и завершении экземпляра рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="e91b3-122">For example, when a workflow instance starts or completes tracking records are emitted.</span></span> <span data-ttu-id="e91b3-123">Отслеживание также позволяет извлекать важные бизнес-данные, связанные с переменными рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="e91b3-123">Tracking can also extract business relevant data associated with the workflow variables.</span></span> <span data-ttu-id="e91b3-124">Например, если рабочий процесс представляет собой систему обработки заказов, то вместе с записью отслеживания можно извлечь идентификатор заказа.</span><span class="sxs-lookup"><span data-stu-id="e91b3-124">For example, if the workflow represents an order processing system the order id can be extracted along with the tracking record.</span></span> <span data-ttu-id="e91b3-125">В общем, функции отслеживания WF обеспечивают диагностику и анализ исполнения рабочих задач.</span><span class="sxs-lookup"><span data-stu-id="e91b3-125">In general, enabling WF tracking facilitates diagnostics or business analytics over a workflow execution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e91b3-126">См. также</span><span class="sxs-lookup"><span data-stu-id="e91b3-126">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection?displayProperty=nameWithType>
- [<span data-ttu-id="e91b3-127">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="e91b3-127">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
