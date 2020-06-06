---
title: <activityScheduledQuery>WCF
ms.date: 03/30/2017
ms.assetid: 25f6eee1-3d98-4c39-b517-c0813f03f106
ms.openlocfilehash: b173964cf5d691f4b9300bca69ca4a1fe1ea7e11
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850476"
---
# <a name="activityscheduledquery-of-wcf"></a><span data-ttu-id="7e48d-102">\<activityScheduledQuery>WCF</span><span class="sxs-lookup"><span data-stu-id="7e48d-102">\<activityScheduledQuery> of WCF</span></span>

<span data-ttu-id="7e48d-103">Представляет коллекцию запросов, которые используются для отслеживания действия, выполнение которого запланировано родительским действием.</span><span class="sxs-lookup"><span data-stu-id="7e48d-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="7e48d-104">Этот запрос необходим, чтобы участник отслеживания подписался на записи запланированных действий.</span><span class="sxs-lookup"><span data-stu-id="7e48d-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
<span data-ttu-id="7e48d-105">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="7e48d-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityScheduledQueries>**](activityscheduledqueries-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityScheduledQuery>**  
  
## <a name="syntax"></a><span data-ttu-id="7e48d-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7e48d-106">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <activityScheduledQueries>
          <activityScheduledQuery activityName="String"
                                  childActivityName="String" />
        </activityScheduledQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7e48d-107">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="7e48d-107">Attributes and elements</span></span>  

<span data-ttu-id="7e48d-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="7e48d-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7e48d-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="7e48d-109">Attributes</span></span>  
  
|<span data-ttu-id="7e48d-110">Атрибут</span><span class="sxs-lookup"><span data-stu-id="7e48d-110">Attribute</span></span>|<span data-ttu-id="7e48d-111">Описание:</span><span class="sxs-lookup"><span data-stu-id="7e48d-111">Description</span></span>|  
|---------------|-----------------|  
|`activityName`|<span data-ttu-id="7e48d-112">Строка, задающая имя действия, которое запрашивает отмену.</span><span class="sxs-lookup"><span data-stu-id="7e48d-112">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|`childActivityName`|<span data-ttu-id="7e48d-113">Строка, указывающая имя дочернего действия, для которого была запрошена отмена.</span><span class="sxs-lookup"><span data-stu-id="7e48d-113">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7e48d-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="7e48d-114">Child elements</span></span>

<span data-ttu-id="7e48d-115">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="7e48d-115">None.</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="7e48d-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="7e48d-116">Parent elements</span></span>  
  
|<span data-ttu-id="7e48d-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="7e48d-117">Element</span></span>|<span data-ttu-id="7e48d-118">Описание</span><span class="sxs-lookup"><span data-stu-id="7e48d-118">Description</span></span>|  
|-------------|-----------------|  
|[\<activityScheduledQueries>](activityscheduledqueries-of-wcf.md)|<span data-ttu-id="7e48d-119">Коллекция запросов, которая используется для трассировки действия, запланированного на выполнение родительским действием.</span><span class="sxs-lookup"><span data-stu-id="7e48d-119">A collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7e48d-120">См. также</span><span class="sxs-lookup"><span data-stu-id="7e48d-120">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement>
- <xref:System.Activities.Tracking.ActivityScheduledQuery>
- [<span data-ttu-id="7e48d-121">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="7e48d-121">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="7e48d-122">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="7e48d-122">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
