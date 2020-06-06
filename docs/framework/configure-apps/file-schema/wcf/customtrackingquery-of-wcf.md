---
title: <customTrackingQuery>WCF
ms.date: 03/30/2017
ms.assetid: 164446ae-8440-4b67-b217-6786cfae1e01
ms.openlocfilehash: 204bbb6cf5ebcb30bf92b697885ecbbbd94385e0
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855418"
---
# <a name="customtrackingquery-of-wcf"></a><span data-ttu-id="383bc-102">\<customTrackingQuery>WCF</span><span class="sxs-lookup"><span data-stu-id="383bc-102">\<customTrackingQuery> of WCF</span></span>

<span data-ttu-id="383bc-103">Представляет запрос, который используется для трассировки событий, определенных в действиях кода.</span><span class="sxs-lookup"><span data-stu-id="383bc-103">Represents a query that is used to track events that you define in your code activities.</span></span> <span data-ttu-id="383bc-104">Запрос необходим, чтобы участник отслеживания подписался на пользовательские записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="383bc-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>

<span data-ttu-id="383bc-105">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="383bc-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customTrackingQueries>**](customtrackingqueries-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customTrackingQuery>**  
  
## <a name="syntax"></a><span data-ttu-id="383bc-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="383bc-106">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <customTrackingQueries>
          <customTrackingQuery activityName="String"
                               name="String"/>
        </customTrackingQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="383bc-107">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="383bc-107">Attributes and elements</span></span>  

<span data-ttu-id="383bc-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="383bc-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="383bc-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="383bc-109">Attributes</span></span>  
  
|<span data-ttu-id="383bc-110">Атрибут</span><span class="sxs-lookup"><span data-stu-id="383bc-110">Attribute</span></span>|<span data-ttu-id="383bc-111">Описание:</span><span class="sxs-lookup"><span data-stu-id="383bc-111">Description</span></span>|  
|---------------|-----------------|  
|`activityName`|<span data-ttu-id="383bc-112">Строка, задающая имя действия, сформировавшего запись отслеживания.</span><span class="sxs-lookup"><span data-stu-id="383bc-112">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|`name`|<span data-ttu-id="383bc-113">Строка, задающая имя выдаваемой пользовательской записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="383bc-113">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="383bc-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="383bc-114">Child elements</span></span>

<span data-ttu-id="383bc-115">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="383bc-115">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="383bc-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="383bc-116">Parent elements</span></span>

|<span data-ttu-id="383bc-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="383bc-117">Element</span></span>|<span data-ttu-id="383bc-118">Описание</span><span class="sxs-lookup"><span data-stu-id="383bc-118">Description</span></span>|  
|-------------|-----------------|  
|[\<customTrackingQueries>](customtrackingqueries-of-wcf.md)|<span data-ttu-id="383bc-119">Представляет коллекцию запросов, используемых для отслеживания событий, определенных в действиях кода.</span><span class="sxs-lookup"><span data-stu-id="383bc-119">Represents a collection of queries that are used to track events that you define in your code activities.</span></span>|
  
## <a name="see-also"></a><span data-ttu-id="383bc-120">См. также</span><span class="sxs-lookup"><span data-stu-id="383bc-120">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="383bc-121">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="383bc-121">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="383bc-122">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="383bc-122">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
