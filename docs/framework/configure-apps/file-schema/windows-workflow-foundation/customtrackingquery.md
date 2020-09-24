---
title: <customTrackingQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4e108e89-1132-46b7-868a-c7f5c69dc89f
ms.openlocfilehash: 59a76ea772dc8d06c390e3bca9d531df5f11e5f0
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148728"
---
# \<customTrackingQuery>

<span data-ttu-id="36f00-101">Представляет коллекцию запросов, используемых для отслеживания событий, определенных в действиях кода.</span><span class="sxs-lookup"><span data-stu-id="36f00-101">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="36f00-102">Запрос необходим, чтобы участник отслеживания подписался на пользовательские записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="36f00-102">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="36f00-103">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="36f00-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customTrackingQueries>**](customtrackingqueries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customTrackingQuery>**  
  
## <a name="syntax"></a><span data-ttu-id="36f00-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="36f00-104">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <customTrackingQueries>
        <customTrackingQuery activityName="String"
                             name="String" />
      </customTrackingQueries>
    </workflow>
 </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="36f00-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="36f00-105">Attributes and Elements</span></span>  

 <span data-ttu-id="36f00-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="36f00-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="36f00-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="36f00-107">Attributes</span></span>  
  
|<span data-ttu-id="36f00-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="36f00-108">Attribute</span></span>|<span data-ttu-id="36f00-109">Описание</span><span class="sxs-lookup"><span data-stu-id="36f00-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="36f00-110">activityName</span><span class="sxs-lookup"><span data-stu-id="36f00-110">activityName</span></span>|<span data-ttu-id="36f00-111">Строка, задающая имя действия, сформировавшего запись отслеживания.</span><span class="sxs-lookup"><span data-stu-id="36f00-111">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|<span data-ttu-id="36f00-112">name</span><span class="sxs-lookup"><span data-stu-id="36f00-112">name</span></span>|<span data-ttu-id="36f00-113">Строка, задающая имя выдаваемой пользовательской записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="36f00-113">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="36f00-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="36f00-114">Child Elements</span></span>  

 <span data-ttu-id="36f00-115">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="36f00-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="36f00-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="36f00-116">Parent Elements</span></span>  
  
|<span data-ttu-id="36f00-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="36f00-117">Element</span></span>|<span data-ttu-id="36f00-118">Описание</span><span class="sxs-lookup"><span data-stu-id="36f00-118">Description</span></span>|  
|-------------|-----------------|  
|[\<customTrackingQuery>](customtrackingquery.md)|<span data-ttu-id="36f00-119">Запрос, который используется для отслеживания событий, определенных в действиях кода.</span><span class="sxs-lookup"><span data-stu-id="36f00-119">A query that is used to track events that you define in your code activities.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="36f00-120">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="36f00-120">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="36f00-121">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="36f00-121">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="36f00-122">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="36f00-122">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
