---
title: <customTrackingQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4e9e732d-911d-45a3-a569-4b5e9cd1ffbe
ms.openlocfilehash: 3a666b7c7affda06fbf03515b045eddf2a1f6af5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91175893"
---
# \<customTrackingQueries>

<span data-ttu-id="cd583-101">Представляет коллекцию запросов, используемых для отслеживания событий, определенных в действиях кода.</span><span class="sxs-lookup"><span data-stu-id="cd583-101">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="cd583-102">Запрос необходим, чтобы участник отслеживания подписался на пользовательские записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="cd583-102">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="cd583-103">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="cd583-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customTrackingQueries>**  
  
## <a name="syntax"></a><span data-ttu-id="cd583-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cd583-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cd583-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="cd583-105">Attributes and Elements</span></span>  

 <span data-ttu-id="cd583-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="cd583-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cd583-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="cd583-107">Attributes</span></span>  

 <span data-ttu-id="cd583-108">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="cd583-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="cd583-109">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="cd583-109">Child Elements</span></span>  
  
|<span data-ttu-id="cd583-110">Элемент</span><span class="sxs-lookup"><span data-stu-id="cd583-110">Element</span></span>|<span data-ttu-id="cd583-111">Описание</span><span class="sxs-lookup"><span data-stu-id="cd583-111">Description</span></span>|  
|-------------|-----------------|  
|[\<customTrackingQuery>](customtrackingquery.md)|<span data-ttu-id="cd583-112">Запрос, который используется для отслеживания событий, определенных в действиях кода.</span><span class="sxs-lookup"><span data-stu-id="cd583-112">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cd583-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="cd583-113">Parent Elements</span></span>  
  
|<span data-ttu-id="cd583-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="cd583-114">Element</span></span>|<span data-ttu-id="cd583-115">Описание</span><span class="sxs-lookup"><span data-stu-id="cd583-115">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](workflow.md)|<span data-ttu-id="cd583-116">Элемент конфигурации, содержащий все запросы для определенного рабочего процесса, определяемого свойством **ActivityDefinitionId** .</span><span class="sxs-lookup"><span data-stu-id="cd583-116">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cd583-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="cd583-117">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="cd583-118">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="cd583-118">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="cd583-119">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="cd583-119">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
