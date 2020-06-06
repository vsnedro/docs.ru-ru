---
title: <bookmarkResumptionQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 226de75d-d25c-48d5-b069-4b7d80a6852b
ms.openlocfilehash: b2a81a42a17474bdb0124bec6d3c3eeefa514411
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398852"
---
# \<bookmarkResumptionQuery>
<span data-ttu-id="e8c43-101">Представляет запрос, используемый для отслеживания возобновления закладки в экземпляре рабочего потока.</span><span class="sxs-lookup"><span data-stu-id="e8c43-101">Represents a query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="e8c43-102">Этот запрос необходим, чтобы участник отслеживания мог подписываться на записи о возобновлении чтения с закладок.</span><span class="sxs-lookup"><span data-stu-id="e8c43-102">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="e8c43-103">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="e8c43-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<bookmarkResumptionQueries>**](bookmarkresumptionqueries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bookmarkResumptionQuery>**  
  
## <a name="syntax"></a><span data-ttu-id="e8c43-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e8c43-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e8c43-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e8c43-105">Attributes and Elements</span></span>  
 <span data-ttu-id="e8c43-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e8c43-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e8c43-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e8c43-107">Attributes</span></span>  
  
|<span data-ttu-id="e8c43-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="e8c43-108">Attribute</span></span>|<span data-ttu-id="e8c43-109">Описание</span><span class="sxs-lookup"><span data-stu-id="e8c43-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e8c43-110">name</span><span class="sxs-lookup"><span data-stu-id="e8c43-110">name</span></span>|<span data-ttu-id="e8c43-111">Строка, задающая имя записи закладки, которое используется для подписки.</span><span class="sxs-lookup"><span data-stu-id="e8c43-111">A string that specifies the name of the bookmark record to subscribe to.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e8c43-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e8c43-112">Child Elements</span></span>  
 <span data-ttu-id="e8c43-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="e8c43-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e8c43-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e8c43-114">Parent Elements</span></span>  
  
|<span data-ttu-id="e8c43-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="e8c43-115">Element</span></span>|<span data-ttu-id="e8c43-116">Описание</span><span class="sxs-lookup"><span data-stu-id="e8c43-116">Description</span></span>|  
|-------------|-----------------|  
|[\<bookmarkResumptionQueries>](bookmarkresumptionqueries.md)|<span data-ttu-id="e8c43-117">Представляет коллекцию запросов, используемых для отслеживания возобновления чтения с закладок в экземпляре рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="e8c43-117">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e8c43-118">См. также</span><span class="sxs-lookup"><span data-stu-id="e8c43-118">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="e8c43-119">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="e8c43-119">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="e8c43-120">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="e8c43-120">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
