---
title: <tracking>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: fd9b50ed-98a1-4518-836d-e4e02c670822
ms.openlocfilehash: 0b00780dedc15fe90163145f23c57f62369c401f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91198747"
---
# \<tracking>

<span data-ttu-id="1e5d2-101">Представляет раздел конфигурации для определения настроек отслеживания для службы рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="1e5d2-101">Represents a configuration section for defining tracking settings for a workflow service.</span></span>  
  
 <span data-ttu-id="1e5d2-102">Дополнительные сведения об отслеживании рабочих процессов и его конфигурации см. в разделе Отслеживание рабочего процесса [и трассировка](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) и [Настройка отслеживания рабочего процесса](../../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="1e5d2-102">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Configuring Tracking for a Workflow](../../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<tracking>**  
  
## <a name="syntax"></a><span data-ttu-id="1e5d2-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1e5d2-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1e5d2-104">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="1e5d2-104">Attributes and Elements</span></span>  

 <span data-ttu-id="1e5d2-105">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="1e5d2-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1e5d2-106">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="1e5d2-106">Attributes</span></span>  

 <span data-ttu-id="1e5d2-107">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="1e5d2-107">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1e5d2-108">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="1e5d2-108">Child Elements</span></span>  
  
|<span data-ttu-id="1e5d2-109">Элемент</span><span class="sxs-lookup"><span data-stu-id="1e5d2-109">Element</span></span>|<span data-ttu-id="1e5d2-110">Описание</span><span class="sxs-lookup"><span data-stu-id="1e5d2-110">Description</span></span>|  
|-------------|-----------------|  
|[\<participants>](participants.md)|<span data-ttu-id="1e5d2-111">Коллекция элементов конфигурации, которые определяют участников, подписанных на записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="1e5d2-111">A collection of configuration elements defining participants that subscribe to tracking records.</span></span> <span data-ttu-id="1e5d2-112">Участники содержат логику обработки полезных данных из записей отслеживания (например, они могут записать данные в файл).</span><span class="sxs-lookup"><span data-stu-id="1e5d2-112">The tracking participants contain the logic to process the payload from the tracking records (for example, they could choose to write to a file).</span></span>|  
|[\<trackingProfile>](trackingprofile.md)|<span data-ttu-id="1e5d2-113">Профиль отслеживания для фильтрации записей отслеживания, выдаваемых экземпляром рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="1e5d2-113">A tracking profile to filter tracking records emitted from a workflow instance.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1e5d2-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="1e5d2-114">Parent Elements</span></span>  
  
|<span data-ttu-id="1e5d2-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="1e5d2-115">Element</span></span>|<span data-ttu-id="1e5d2-116">Описание</span><span class="sxs-lookup"><span data-stu-id="1e5d2-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1e5d2-117">system.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="1e5d2-117">system.ServiceModel</span></span>|<span data-ttu-id="1e5d2-118">Корневой элемент всех элементов конфигурации рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="1e5d2-118">The root element of all workflow configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1e5d2-119">Remarks</span><span class="sxs-lookup"><span data-stu-id="1e5d2-119">Remarks</span></span>  

 <span data-ttu-id="1e5d2-120">Отслеживание позволяет исследовать выполнение рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="1e5d2-120">Tracking provides you with the ability to examine the execution of a workflow.</span></span> <span data-ttu-id="1e5d2-121">Инфраструктура отслеживания рабочего процесса инструментирует процесс таким образом, что выдаются записи, отражающие ключевые события выполнения.</span><span class="sxs-lookup"><span data-stu-id="1e5d2-121">The workflow tracking infrastructure instruments a workflow to emit records reflecting key events during the execution.</span></span> <span data-ttu-id="1e5d2-122">Например, записи отслеживания создаются при запуске и завершении экземпляра рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="1e5d2-122">For example, when a workflow instance starts or completes tracking records are emitted.</span></span> <span data-ttu-id="1e5d2-123">Отслеживание также позволяет извлекать важные бизнес-данные, связанные с переменными рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="1e5d2-123">Tracking can also extract business relevant data associated with the workflow variables.</span></span> <span data-ttu-id="1e5d2-124">Например, если рабочий процесс представляет собой систему обработки заказов, то вместе с записью отслеживания можно извлечь идентификатор заказа.</span><span class="sxs-lookup"><span data-stu-id="1e5d2-124">For example, if the workflow represents an order processing system the order id can be extracted along with the tracking record.</span></span> <span data-ttu-id="1e5d2-125">В общем, функции отслеживания WF обеспечивают диагностику и анализ исполнения рабочих задач.</span><span class="sxs-lookup"><span data-stu-id="1e5d2-125">In general, enabling WF tracking facilitates diagnostics or business analytics over a workflow execution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e5d2-126">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="1e5d2-126">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection?displayProperty=nameWithType>
- [<span data-ttu-id="1e5d2-127">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="1e5d2-127">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
