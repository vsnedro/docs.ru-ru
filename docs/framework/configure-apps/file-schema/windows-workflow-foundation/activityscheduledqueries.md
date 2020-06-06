---
title: <activityScheduledQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ca6e82f1-54f2-48d6-899c-9873065b5547
ms.openlocfilehash: 763754b95a7f39c7f35e05df28589b69352168e6
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152428"
---
# \<activityScheduledQueries>
<span data-ttu-id="ec6e8-101">Представляет коллекцию запросов, которые используются для отслеживания действия, выполнение которого запланировано родительским действием.</span><span class="sxs-lookup"><span data-stu-id="ec6e8-101">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="ec6e8-102">Этот запрос необходим, чтобы участник отслеживания подписался на записи запланированных действий.</span><span class="sxs-lookup"><span data-stu-id="ec6e8-102">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="ec6e8-103">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="ec6e8-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityScheduledQueries>**  
  
## <a name="syntax"></a><span data-ttu-id="ec6e8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ec6e8-104">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityScheduledQueries>
        <activityScheduledQuery activityName="String"
                                childActivityName="String" />
      </activityScheduledQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ec6e8-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ec6e8-105">Attributes and Elements</span></span>  
 <span data-ttu-id="ec6e8-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ec6e8-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ec6e8-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ec6e8-107">Attributes</span></span>  
 <span data-ttu-id="ec6e8-108">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="ec6e8-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ec6e8-109">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ec6e8-109">Child Elements</span></span>  
  
|<span data-ttu-id="ec6e8-110">Элемент</span><span class="sxs-lookup"><span data-stu-id="ec6e8-110">Element</span></span>|<span data-ttu-id="ec6e8-111">Описание</span><span class="sxs-lookup"><span data-stu-id="ec6e8-111">Description</span></span>|  
|-------------|-----------------|  
|[\<activityScheduledQuery>](activityscheduledquery.md)|<span data-ttu-id="ec6e8-112">Запрос, который используется для отслеживания действия, запланированного к исполнению родительским действием.</span><span class="sxs-lookup"><span data-stu-id="ec6e8-112">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ec6e8-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ec6e8-113">Parent Elements</span></span>  
  
|<span data-ttu-id="ec6e8-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="ec6e8-114">Element</span></span>|<span data-ttu-id="ec6e8-115">Описание</span><span class="sxs-lookup"><span data-stu-id="ec6e8-115">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](workflow.md)|<span data-ttu-id="ec6e8-116">Элемент конфигурации, содержащий все запросы для определенного рабочего процесса, определяемого свойством **ActivityDefinitionId** .</span><span class="sxs-lookup"><span data-stu-id="ec6e8-116">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ec6e8-117">См. также</span><span class="sxs-lookup"><span data-stu-id="ec6e8-117">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType>
- [<span data-ttu-id="ec6e8-118">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="ec6e8-118">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="ec6e8-119">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="ec6e8-119">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
