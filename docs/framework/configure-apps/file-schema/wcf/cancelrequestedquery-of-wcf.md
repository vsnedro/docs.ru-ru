---
title: <cancelRequestedQuery>WCF
ms.date: 03/30/2017
ms.assetid: b690d870-02eb-4c56-8bc3-e5ca99d7097b
ms.openlocfilehash: 0ac8b87afc44927ab6653dd6fcdc09cd61436a9b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850048"
---
# <a name="cancelrequestedquery-of-wcf"></a><span data-ttu-id="b8b05-102">\<cancelRequestedQuery>WCF</span><span class="sxs-lookup"><span data-stu-id="b8b05-102">\<cancelRequestedQuery> of WCF</span></span>

<span data-ttu-id="b8b05-103">Представляет запрос, используемый для отслеживания запросов по отмене дочернего действия родительским.</span><span class="sxs-lookup"><span data-stu-id="b8b05-103">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="b8b05-104">Этот запрос необходим, чтобы участник отслеживания подписался на объекты записей запросов на отмену.</span><span class="sxs-lookup"><span data-stu-id="b8b05-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
<span data-ttu-id="b8b05-105">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="b8b05-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cancelRequestedQueries>**](cancelrequestedqueries-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cancelRequestedQuery>**  

## <a name="syntax"></a><span data-ttu-id="b8b05-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b8b05-106">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <cancelRequestedQueries>
          <cancelRequestedQuery activityName="String"
                                childActivityName="String" />
        </cancelRequestedQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b8b05-107">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="b8b05-107">Attributes and elements</span></span>

<span data-ttu-id="b8b05-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="b8b05-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="b8b05-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b8b05-109">Attributes</span></span>  
  
|<span data-ttu-id="b8b05-110">Атрибут</span><span class="sxs-lookup"><span data-stu-id="b8b05-110">Attribute</span></span>|<span data-ttu-id="b8b05-111">Описание:</span><span class="sxs-lookup"><span data-stu-id="b8b05-111">Description</span></span>|  
|---------------|-----------------|  
|`activityName`|<span data-ttu-id="b8b05-112">Строка, задающая имя действия, которое запрашивает отмену.</span><span class="sxs-lookup"><span data-stu-id="b8b05-112">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|`childActivityName`|<span data-ttu-id="b8b05-113">Строка, указывающая имя дочернего действия, для которого была запрошена отмена.</span><span class="sxs-lookup"><span data-stu-id="b8b05-113">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b8b05-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b8b05-114">Child elements</span></span>

<span data-ttu-id="b8b05-115">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="b8b05-115">None.</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="b8b05-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b8b05-116">Parent elements</span></span>
  
|<span data-ttu-id="b8b05-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="b8b05-117">Element</span></span>|<span data-ttu-id="b8b05-118">Описание</span><span class="sxs-lookup"><span data-stu-id="b8b05-118">Description</span></span>|  
|-------------|-----------------|  
|[\<cancelRequestedQueries>](cancelrequestedqueries-of-wcf.md)|<span data-ttu-id="b8b05-119">Представляет коллекцию запросов, используемых для отслеживания запросов по отмене дочернего действия родительским действием.</span><span class="sxs-lookup"><span data-stu-id="b8b05-119">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b8b05-120">См. также</span><span class="sxs-lookup"><span data-stu-id="b8b05-120">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType>
- [<span data-ttu-id="b8b05-121">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="b8b05-121">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="b8b05-122">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="b8b05-122">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
