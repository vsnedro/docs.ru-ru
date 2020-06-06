---
title: <bookmarkResumptionQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8ed61a7f-4254-439c-bdd8-b474971533f7
ms.openlocfilehash: 563e0cbd3f50887e1c9e3d47a3c9502acc13b2c9
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398863"
---
# \<bookmarkResumptionQueries>
<span data-ttu-id="aeed5-101">Представляет коллекцию запросов, используемых для отслеживания возобновления чтения с закладок в экземпляре рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="aeed5-101">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="aeed5-102">Этот запрос необходим, чтобы участник отслеживания мог подписываться на записи о возобновлении чтения с закладок.</span><span class="sxs-lookup"><span data-stu-id="aeed5-102">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="aeed5-103">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="aeed5-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bookmarkResumptionQueries>**  

## <a name="syntax"></a><span data-ttu-id="aeed5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="aeed5-104">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <bookmarkResumptionQueries>
        <bookmarkResumptionQuery name="String" />
      </bookmarkResumptionQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="aeed5-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="aeed5-105">Attributes and Elements</span></span>  
 <span data-ttu-id="aeed5-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="aeed5-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="aeed5-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="aeed5-107">Attributes</span></span>  
 <span data-ttu-id="aeed5-108">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="aeed5-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="aeed5-109">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="aeed5-109">Child Elements</span></span>  
  
|<span data-ttu-id="aeed5-110">Элемент</span><span class="sxs-lookup"><span data-stu-id="aeed5-110">Element</span></span>|<span data-ttu-id="aeed5-111">Описание</span><span class="sxs-lookup"><span data-stu-id="aeed5-111">Description</span></span>|  
|-------------|-----------------|  
|[\<bookmarkResumptionQuery>](bookmarkresumptionquery.md)|<span data-ttu-id="aeed5-112">Запрос, используемый для отслеживания возобновления закладки в экземпляре рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="aeed5-112">A query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="aeed5-113">Этот запрос необходим, чтобы участник отслеживания мог подписываться на записи о возобновлении чтения с закладок.</span><span class="sxs-lookup"><span data-stu-id="aeed5-113">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="aeed5-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="aeed5-114">Parent Elements</span></span>  
  
|<span data-ttu-id="aeed5-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="aeed5-115">Element</span></span>|<span data-ttu-id="aeed5-116">Описание</span><span class="sxs-lookup"><span data-stu-id="aeed5-116">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](workflow.md)|<span data-ttu-id="aeed5-117">Элемент конфигурации, содержащий все запросы для определенного рабочего процесса, определяемого свойством **ActivityDefinitionId** .</span><span class="sxs-lookup"><span data-stu-id="aeed5-117">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="aeed5-118">См. также</span><span class="sxs-lookup"><span data-stu-id="aeed5-118">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="aeed5-119">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="aeed5-119">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="aeed5-120">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="aeed5-120">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
