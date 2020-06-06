---
title: <activityScheduledQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: a8bcd6d4-b389-4daf-86bf-1ade85fec114
ms.openlocfilehash: 09cbc43ae4db82dc80e6985131f8d6cc0c24b2ac
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152415"
---
# \<activityScheduledQuery>
<span data-ttu-id="eb841-101">Представляет коллекцию запросов, которые используются для отслеживания действия, выполнение которого запланировано родительским действием.</span><span class="sxs-lookup"><span data-stu-id="eb841-101">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="eb841-102">Этот запрос необходим, чтобы участник отслеживания подписался на записи запланированных действий.</span><span class="sxs-lookup"><span data-stu-id="eb841-102">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="eb841-103">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="eb841-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityScheduledQueries>**](activityscheduledqueries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityScheduledQuery>**  
  
## <a name="syntax"></a><span data-ttu-id="eb841-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="eb841-104">Syntax</span></span>  
  
```xml
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityScheduledQueries>
        <activityScheduledQuery activityName="String"
                                childActivityName="String"/>
      </activityScheduledQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eb841-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="eb841-105">Attributes and Elements</span></span>  
 <span data-ttu-id="eb841-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="eb841-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eb841-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="eb841-107">Attributes</span></span>  
  
|<span data-ttu-id="eb841-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="eb841-108">Attribute</span></span>|<span data-ttu-id="eb841-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="eb841-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="eb841-110">activityName</span><span class="sxs-lookup"><span data-stu-id="eb841-110">activityName</span></span>|<span data-ttu-id="eb841-111">Строка, задающая имя действия, которое запрашивает отмену.</span><span class="sxs-lookup"><span data-stu-id="eb841-111">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="eb841-112">childActivityName</span><span class="sxs-lookup"><span data-stu-id="eb841-112">childActivityName</span></span>|<span data-ttu-id="eb841-113">Строка, указывающая имя дочернего действия, для которого была запрошена отмена.</span><span class="sxs-lookup"><span data-stu-id="eb841-113">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="eb841-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="eb841-114">Child Elements</span></span>  
 <span data-ttu-id="eb841-115">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="eb841-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="eb841-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="eb841-116">Parent Elements</span></span>  
  
|<span data-ttu-id="eb841-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="eb841-117">Element</span></span>|<span data-ttu-id="eb841-118">Описание</span><span class="sxs-lookup"><span data-stu-id="eb841-118">Description</span></span>|  
|-------------|-----------------|  
|[\<activityScheduledQuery>](activityscheduledquery.md)|<span data-ttu-id="eb841-119">Запрос, который используется для отслеживания действия, запланированного к исполнению родительским действием.</span><span class="sxs-lookup"><span data-stu-id="eb841-119">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="eb841-120">См. также</span><span class="sxs-lookup"><span data-stu-id="eb841-120">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType>
- [<span data-ttu-id="eb841-121">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="eb841-121">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="eb841-122">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="eb841-122">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
