---
title: <tracking>WCF
ms.date: 03/30/2017
ms.assetid: 70cfaf24-a91c-4e56-ac47-d2ed87a963b3
ms.openlocfilehash: e8f74d635299a965b754536234e6be28e4e7a104
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399422"
---
# <a name="tracking-of-wcf"></a><span data-ttu-id="05bd8-102">\<tracking>WCF</span><span class="sxs-lookup"><span data-stu-id="05bd8-102">\<tracking> of WCF</span></span>
<span data-ttu-id="05bd8-103">Представляет раздел конфигурации для определения настроек отслеживания для службы рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="05bd8-103">Represents a configuration section for defining tracking settings for a workflow service.</span></span>  
  
 <span data-ttu-id="05bd8-104">Дополнительные сведения об отслеживании рабочих процессов и его конфигурации см. в разделе Отслеживание рабочего процесса [и трассировка](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) и [Настройка отслеживания рабочего процесса](../../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="05bd8-104">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Configuring Tracking for a Workflow](../../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<tracking>**  
  
## <a name="syntax"></a><span data-ttu-id="05bd8-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="05bd8-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="05bd8-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="05bd8-106">Attributes and Elements</span></span>  
 <span data-ttu-id="05bd8-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="05bd8-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="05bd8-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="05bd8-108">Attributes</span></span>  
 <span data-ttu-id="05bd8-109">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="05bd8-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="05bd8-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="05bd8-110">Child Elements</span></span>  
  
|<span data-ttu-id="05bd8-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="05bd8-111">Element</span></span>|<span data-ttu-id="05bd8-112">Описание</span><span class="sxs-lookup"><span data-stu-id="05bd8-112">Description</span></span>|  
|-------------|-----------------|  
|[\<participants>](../windows-workflow-foundation/participants.md)|<span data-ttu-id="05bd8-113">Коллекция элементов конфигурации, которые определяют участников, подписанных на записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="05bd8-113">A collection of configuration elements defining participants that subscribe to tracking records.</span></span> <span data-ttu-id="05bd8-114">Участники содержат логику обработки полезных данных из записей отслеживания (например, они могут записать данные в файл).</span><span class="sxs-lookup"><span data-stu-id="05bd8-114">The tracking participants contain the logic to process the payload from the tracking records (for example, they could choose to write to a file).</span></span>|  
|[\<trackingProfile>](../windows-workflow-foundation/trackingprofile.md)|<span data-ttu-id="05bd8-115">Профиль отслеживания для фильтрации записей отслеживания, выдаваемых экземпляром рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="05bd8-115">A tracking profile to filter tracking records emitted from a workflow instance.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="05bd8-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="05bd8-116">Parent Elements</span></span>  
  
|<span data-ttu-id="05bd8-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="05bd8-117">Element</span></span>|<span data-ttu-id="05bd8-118">Описание</span><span class="sxs-lookup"><span data-stu-id="05bd8-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="05bd8-119">system.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="05bd8-119">system.ServiceModel</span></span>|<span data-ttu-id="05bd8-120">Корневой элемент всех элементов конфигурации рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="05bd8-120">The root element of all workflow configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="05bd8-121">Примечания</span><span class="sxs-lookup"><span data-stu-id="05bd8-121">Remarks</span></span>  
 <span data-ttu-id="05bd8-122">Отслеживание позволяет исследовать выполнение рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="05bd8-122">Tracking provides you with the ability to examine the execution of a workflow.</span></span> <span data-ttu-id="05bd8-123">Инфраструктура отслеживания рабочего процесса инструментирует процесс таким образом, что выдаются записи, отражающие ключевые события выполнения.</span><span class="sxs-lookup"><span data-stu-id="05bd8-123">The workflow tracking infrastructure instruments a workflow to emit records reflecting key events during the execution.</span></span> <span data-ttu-id="05bd8-124">Например, записи отслеживания создаются при запуске и завершении экземпляра рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="05bd8-124">For example, when a workflow instance starts or completes tracking records are emitted.</span></span> <span data-ttu-id="05bd8-125">Отслеживание также позволяет извлекать важные бизнес-данные, связанные с переменными рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="05bd8-125">Tracking can also extract business relevant data associated with the workflow variables.</span></span> <span data-ttu-id="05bd8-126">Например, если рабочий процесс представляет собой систему обработки заказов, то вместе с записью отслеживания можно извлечь идентификатор заказа.</span><span class="sxs-lookup"><span data-stu-id="05bd8-126">For example, if the workflow represents an order processing system the order id can be extracted along with the tracking record.</span></span> <span data-ttu-id="05bd8-127">В общем, функции отслеживания WF обеспечивают диагностику и анализ исполнения рабочих задач.</span><span class="sxs-lookup"><span data-stu-id="05bd8-127">In general, enabling WF tracking facilitates diagnostics or business analytics over a workflow execution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05bd8-128">См. также</span><span class="sxs-lookup"><span data-stu-id="05bd8-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection?displayProperty=nameWithType>
- [<span data-ttu-id="05bd8-129">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="05bd8-129">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
