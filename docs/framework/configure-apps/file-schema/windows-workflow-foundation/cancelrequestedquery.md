---
title: <cancelRequestedQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8da9b1c4-338a-4f23-9830-6d257772d340
ms.openlocfilehash: 3e6840ce647625c36356cccd4651f17de32777e2
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152291"
---
# \<cancelRequestedQuery>
<span data-ttu-id="b1015-101">Представляет запрос, используемый для отслеживания запросов по отмене дочернего действия родительским.</span><span class="sxs-lookup"><span data-stu-id="b1015-101">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="b1015-102">Этот запрос необходим, чтобы участник отслеживания подписался на объекты записей запросов на отмену.</span><span class="sxs-lookup"><span data-stu-id="b1015-102">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="b1015-103">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="b1015-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cancelRequestedQueries>**](cancelrequestedqueries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cancelRequestedQuery>**  
  
## <a name="syntax"></a><span data-ttu-id="b1015-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b1015-104">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <cancelRequestQueries>
        <cancelRequestQuery activityName="String"
                            childActivityName="String"/>
      </cancelRequestQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b1015-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b1015-105">Attributes and Elements</span></span>  
 <span data-ttu-id="b1015-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="b1015-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b1015-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b1015-107">Attributes</span></span>  
  
|<span data-ttu-id="b1015-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="b1015-108">Attribute</span></span>|<span data-ttu-id="b1015-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="b1015-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b1015-110">activityName</span><span class="sxs-lookup"><span data-stu-id="b1015-110">activityName</span></span>|<span data-ttu-id="b1015-111">Строка, задающая имя действия, которое запрашивает отмену.</span><span class="sxs-lookup"><span data-stu-id="b1015-111">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="b1015-112">childActivityName</span><span class="sxs-lookup"><span data-stu-id="b1015-112">childActivityName</span></span>|<span data-ttu-id="b1015-113">Строка, указывающая имя дочернего действия, для которого была запрошена отмена.</span><span class="sxs-lookup"><span data-stu-id="b1015-113">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b1015-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b1015-114">Child Elements</span></span>  
 <span data-ttu-id="b1015-115">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="b1015-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b1015-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b1015-116">Parent Elements</span></span>  
  
|<span data-ttu-id="b1015-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="b1015-117">Element</span></span>|<span data-ttu-id="b1015-118">Описание</span><span class="sxs-lookup"><span data-stu-id="b1015-118">Description</span></span>|  
|-------------|-----------------|  
|[\<faultPropagationQuery>](faultpropagationquery.md)|<span data-ttu-id="b1015-119">Представляет список элементов конфигурации, которые используются для отслеживания запросов на отмену дочернего действия родительским действием.</span><span class="sxs-lookup"><span data-stu-id="b1015-119">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="b1015-120">Этот запрос необходим, чтобы участник отслеживания подписался на объекты записей запросов на отмену.</span><span class="sxs-lookup"><span data-stu-id="b1015-120">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b1015-121">См. также</span><span class="sxs-lookup"><span data-stu-id="b1015-121">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType>
- [<span data-ttu-id="b1015-122">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="b1015-122">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="b1015-123">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="b1015-123">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
