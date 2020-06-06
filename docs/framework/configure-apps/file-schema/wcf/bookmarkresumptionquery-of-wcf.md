---
title: <bookmarkResumptionQuery>WCF
ms.date: 03/30/2017
ms.assetid: 755a34f0-87c9-4a1e-ae4d-0fb8a6fbdc0e
ms.openlocfilehash: 8cb254599a9742305ec958fd77174f4c4b8a57c2
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "71834006"
---
# <a name="bookmarkresumptionquery-of-wcf"></a><span data-ttu-id="76de4-102">\<bookmarkResumptionQuery>WCF</span><span class="sxs-lookup"><span data-stu-id="76de4-102">\<bookmarkResumptionQuery> of WCF</span></span>

<span data-ttu-id="76de4-103">Представляет запрос, используемый для отслеживания возобновления закладки в экземпляре рабочего потока.</span><span class="sxs-lookup"><span data-stu-id="76de4-103">Represents a query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="76de4-104">Этот запрос необходим, чтобы участник отслеживания мог подписываться на записи о возобновлении чтения с закладок.</span><span class="sxs-lookup"><span data-stu-id="76de4-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
<span data-ttu-id="76de4-105">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="76de4-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<bookmarkResumptionQueries>**](bookmarkresumptionqueries-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bookmarkResumptionQuery>**  
  
## <a name="syntax"></a><span data-ttu-id="76de4-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="76de4-106">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <bookmarkResumptionQueries>
          <bookmarkResumptionQuery name="String" />
        </bookmarkResumptionQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="76de4-107">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="76de4-107">Attributes and elements</span></span>

<span data-ttu-id="76de4-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="76de4-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="76de4-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="76de4-109">Attributes</span></span>  
  
|<span data-ttu-id="76de4-110">Атрибут</span><span class="sxs-lookup"><span data-stu-id="76de4-110">Attribute</span></span>|<span data-ttu-id="76de4-111">Описание:</span><span class="sxs-lookup"><span data-stu-id="76de4-111">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="76de4-112">Строка, задающая имя записи закладки, которое используется для подписки.</span><span class="sxs-lookup"><span data-stu-id="76de4-112">A string that specifies the name of the bookmark record to subscribe to.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="76de4-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="76de4-113">Child elements</span></span>

<span data-ttu-id="76de4-114">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="76de4-114">None.</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="76de4-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="76de4-115">Parent elements</span></span>  
  
|<span data-ttu-id="76de4-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="76de4-116">Element</span></span>|<span data-ttu-id="76de4-117">Описание</span><span class="sxs-lookup"><span data-stu-id="76de4-117">Description</span></span>|  
|-------------|-----------------|  
|[\<bookmarkResumptionQueries>](bookmarkresumptionqueries-of-wcf.md)|<span data-ttu-id="76de4-118">Представляет коллекцию запросов, используемых для отслеживания возобновления чтения с закладок в экземпляре рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="76de4-118">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="76de4-119">См. также</span><span class="sxs-lookup"><span data-stu-id="76de4-119">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="76de4-120">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="76de4-120">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="76de4-121">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="76de4-121">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
