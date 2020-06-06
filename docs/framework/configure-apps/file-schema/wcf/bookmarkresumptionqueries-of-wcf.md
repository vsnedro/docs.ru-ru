---
title: <bookmarkResumptionQueries>WCF
ms.date: 03/30/2017
ms.assetid: ed086712-1dc7-4932-a592-d1116a0155f3
ms.openlocfilehash: 94ff9f44f295b45c03e1bd8f52a85d6b7b0c6e3b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850137"
---
# <a name="bookmarkresumptionqueries-of-wcf"></a><span data-ttu-id="88dbf-102">\<bookmarkResumptionQueries>WCF</span><span class="sxs-lookup"><span data-stu-id="88dbf-102">\<bookmarkResumptionQueries> of WCF</span></span>
  
<span data-ttu-id="88dbf-103">Представляет коллекцию запросов, используемых для отслеживания возобновления чтения с закладок в экземпляре рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="88dbf-103">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="88dbf-104">Этот запрос необходим, чтобы участник отслеживания мог подписываться на записи о возобновлении чтения с закладок.</span><span class="sxs-lookup"><span data-stu-id="88dbf-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
<span data-ttu-id="88dbf-105">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="88dbf-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bookmarkResumptionQueries>**  

## <a name="syntax"></a><span data-ttu-id="88dbf-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="88dbf-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="88dbf-107">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="88dbf-107">Attributes and elements</span></span>  
  
<span data-ttu-id="88dbf-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="88dbf-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="88dbf-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="88dbf-109">Attributes</span></span>  
  
<span data-ttu-id="88dbf-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="88dbf-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="88dbf-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="88dbf-111">Child elements</span></span>  
  
|<span data-ttu-id="88dbf-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="88dbf-112">Element</span></span>|<span data-ttu-id="88dbf-113">Описание</span><span class="sxs-lookup"><span data-stu-id="88dbf-113">Description</span></span>|  
|-------------|-----------------|  
|[\<bookmarkResumptionQuery>](bookmarkresumptionquery-of-wcf.md)|<span data-ttu-id="88dbf-114">Запрос, используемый для отслеживания возобновления закладки в экземпляре рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="88dbf-114">A query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="88dbf-115">Этот запрос необходим, чтобы участник отслеживания мог подписываться на записи о возобновлении чтения с закладок.</span><span class="sxs-lookup"><span data-stu-id="88dbf-115">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="88dbf-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="88dbf-116">Parent elements</span></span>  
  
|<span data-ttu-id="88dbf-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="88dbf-117">Element</span></span>|<span data-ttu-id="88dbf-118">Описание</span><span class="sxs-lookup"><span data-stu-id="88dbf-118">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="88dbf-119">Элемент конфигурации, содержащий все запросы для определенного рабочего процесса, обозначенного свойством `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="88dbf-119">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="88dbf-120">См. также</span><span class="sxs-lookup"><span data-stu-id="88dbf-120">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="88dbf-121">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="88dbf-121">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="88dbf-122">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="88dbf-122">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
