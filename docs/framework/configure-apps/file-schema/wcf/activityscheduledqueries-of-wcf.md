---
title: <activityScheduledQueries>WCF
ms.date: 03/30/2017
ms.assetid: e351329f-9676-4f11-9b19-f4bac82f36fc
ms.openlocfilehash: c2281a9027aabfc5255ef7b09176f60d1725b522
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850492"
---
# <a name="activityscheduledqueries-of-wcf"></a><span data-ttu-id="d1f42-102">\<activityScheduledQueries>WCF</span><span class="sxs-lookup"><span data-stu-id="d1f42-102">\<activityScheduledQueries> of WCF</span></span>
<span data-ttu-id="d1f42-103">Представляет коллекцию запросов, которые используются для отслеживания действия, выполнение которого запланировано родительским действием.</span><span class="sxs-lookup"><span data-stu-id="d1f42-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="d1f42-104">Этот запрос необходим, чтобы участник отслеживания подписался на записи запланированных действий.</span><span class="sxs-lookup"><span data-stu-id="d1f42-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
<span data-ttu-id="d1f42-105">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="d1f42-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityScheduledQueries>**  
  
## <a name="syntax"></a><span data-ttu-id="d1f42-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d1f42-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d1f42-107">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="d1f42-107">Attributes and elements</span></span>  

<span data-ttu-id="d1f42-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="d1f42-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d1f42-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d1f42-109">Attributes</span></span>  

<span data-ttu-id="d1f42-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="d1f42-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d1f42-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d1f42-111">Child elements</span></span>  
  
|<span data-ttu-id="d1f42-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="d1f42-112">Element</span></span>|<span data-ttu-id="d1f42-113">Описание</span><span class="sxs-lookup"><span data-stu-id="d1f42-113">Description</span></span>|  
|-------------|-----------------|  
|[\<activityScheduledQuery>](activityscheduledquery-of-wcf.md)|<span data-ttu-id="d1f42-114">Запрос, который используется для отслеживания действия, запланированного к исполнению родительским действием.</span><span class="sxs-lookup"><span data-stu-id="d1f42-114">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d1f42-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d1f42-115">Parent elements</span></span>  
  
|<span data-ttu-id="d1f42-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="d1f42-116">Element</span></span>|<span data-ttu-id="d1f42-117">Описание</span><span class="sxs-lookup"><span data-stu-id="d1f42-117">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="d1f42-118">Элемент конфигурации, содержащий все запросы для определенного рабочего процесса, обозначенного свойством `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="d1f42-118">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d1f42-119">См. также</span><span class="sxs-lookup"><span data-stu-id="d1f42-119">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection>
- <xref:System.Activities.Tracking.ActivityScheduledQuery>
- [<span data-ttu-id="d1f42-120">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="d1f42-120">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="d1f42-121">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="d1f42-121">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
