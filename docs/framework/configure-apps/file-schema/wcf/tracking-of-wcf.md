---
title: <tracking> WCF
ms.date: 03/30/2017
ms.assetid: 70cfaf24-a91c-4e56-ac47-d2ed87a963b3
ms.openlocfilehash: 223a30cd79d346d6ae36ca64fa887a683e6bfc8d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201438"
---
# <a name="tracking-of-wcf"></a><span data-ttu-id="ce170-102">\<tracking> WCF</span><span class="sxs-lookup"><span data-stu-id="ce170-102">\<tracking> of WCF</span></span>

<span data-ttu-id="ce170-103">Представляет раздел конфигурации для определения настроек отслеживания для службы рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="ce170-103">Represents a configuration section for defining tracking settings for a workflow service.</span></span>  
  
 <span data-ttu-id="ce170-104">Дополнительные сведения об отслеживании рабочих процессов и его конфигурации см. в разделе Отслеживание рабочего процесса [и трассировка](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) и [Настройка отслеживания рабочего процесса](../../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="ce170-104">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Configuring Tracking for a Workflow](../../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<tracking>**  
  
## <a name="syntax"></a><span data-ttu-id="ce170-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ce170-105">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <tracking>
    <participants>
      <add name="String"
           profileName="String"
           type="String" />
    </participants>
    <profiles>
      <trackingProfile name="String">
        <workflow activityDefinitionId="String">
          <activityScheduledQueries>
            <activityScheduledQuery activityName="String"
                                    childActivityName="String"/>
          </activityScheduledQueries>
          <activityStateQueries>
            <activityStateQuery activityName="String" />
            <arguments>
              <argument name="String"/>
            </arguments>
            <states>
              <state name="String"/>
            </states>
            <variables>
              <variable name="String"/>
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
                                   faultHandlerActivityName="String"/>
          </faultPropagationQueries>
          <workflowInstanceQueries>
            <workflowInstanceQuery>
              <states>
                <state name="String"/>
              </states>
            </workflowInstanceQuery>
          </workflowInstanceQueries>
        </workflow>
      </trackingProfile>
    </profiles>
  </tracking>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ce170-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ce170-106">Attributes and Elements</span></span>  

 <span data-ttu-id="ce170-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ce170-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ce170-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ce170-108">Attributes</span></span>  

 <span data-ttu-id="ce170-109">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="ce170-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ce170-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ce170-110">Child Elements</span></span>  
  
|<span data-ttu-id="ce170-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="ce170-111">Element</span></span>|<span data-ttu-id="ce170-112">Описание</span><span class="sxs-lookup"><span data-stu-id="ce170-112">Description</span></span>|  
|-------------|-----------------|  
|[\<participants>](../windows-workflow-foundation/participants.md)|<span data-ttu-id="ce170-113">Коллекция элементов конфигурации, которые определяют участников, подписанных на записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="ce170-113">A collection of configuration elements defining participants that subscribe to tracking records.</span></span> <span data-ttu-id="ce170-114">Участники содержат логику обработки полезных данных из записей отслеживания (например, они могут записать данные в файл).</span><span class="sxs-lookup"><span data-stu-id="ce170-114">The tracking participants contain the logic to process the payload from the tracking records (for example, they could choose to write to a file).</span></span>|  
|[\<trackingProfile>](../windows-workflow-foundation/trackingprofile.md)|<span data-ttu-id="ce170-115">Профиль отслеживания для фильтрации записей отслеживания, выдаваемых экземпляром рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="ce170-115">A tracking profile to filter tracking records emitted from a workflow instance.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ce170-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ce170-116">Parent Elements</span></span>  
  
|<span data-ttu-id="ce170-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="ce170-117">Element</span></span>|<span data-ttu-id="ce170-118">Описание</span><span class="sxs-lookup"><span data-stu-id="ce170-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ce170-119">system.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="ce170-119">system.ServiceModel</span></span>|<span data-ttu-id="ce170-120">Корневой элемент всех элементов конфигурации рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="ce170-120">The root element of all workflow configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ce170-121">Remarks</span><span class="sxs-lookup"><span data-stu-id="ce170-121">Remarks</span></span>  

 <span data-ttu-id="ce170-122">Отслеживание позволяет исследовать выполнение рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="ce170-122">Tracking provides you with the ability to examine the execution of a workflow.</span></span> <span data-ttu-id="ce170-123">Инфраструктура отслеживания рабочего процесса инструментирует процесс таким образом, что выдаются записи, отражающие ключевые события выполнения.</span><span class="sxs-lookup"><span data-stu-id="ce170-123">The workflow tracking infrastructure instruments a workflow to emit records reflecting key events during the execution.</span></span> <span data-ttu-id="ce170-124">Например, записи отслеживания создаются при запуске и завершении экземпляра рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="ce170-124">For example, when a workflow instance starts or completes tracking records are emitted.</span></span> <span data-ttu-id="ce170-125">Отслеживание также позволяет извлекать важные бизнес-данные, связанные с переменными рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="ce170-125">Tracking can also extract business relevant data associated with the workflow variables.</span></span> <span data-ttu-id="ce170-126">Например, если рабочий процесс представляет собой систему обработки заказов, то вместе с записью отслеживания можно извлечь идентификатор заказа.</span><span class="sxs-lookup"><span data-stu-id="ce170-126">For example, if the workflow represents an order processing system the order id can be extracted along with the tracking record.</span></span> <span data-ttu-id="ce170-127">В общем, функции отслеживания WF обеспечивают диагностику и анализ исполнения рабочих задач.</span><span class="sxs-lookup"><span data-stu-id="ce170-127">In general, enabling WF tracking facilitates diagnostics or business analytics over a workflow execution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce170-128">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ce170-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection?displayProperty=nameWithType>
- [<span data-ttu-id="ce170-129">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="ce170-129">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
