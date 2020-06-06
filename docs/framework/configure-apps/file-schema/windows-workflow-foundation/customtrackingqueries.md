---
title: <customTrackingQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4e9e732d-911d-45a3-a569-4b5e9cd1ffbe
ms.openlocfilehash: 6901244009956a499458858bf73f8fd83ec52e13
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152265"
---
# \<customTrackingQueries>
<span data-ttu-id="2deee-101">Представляет коллекцию запросов, используемых для отслеживания событий, определенных в действиях кода.</span><span class="sxs-lookup"><span data-stu-id="2deee-101">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="2deee-102">Запрос необходим, чтобы участник отслеживания подписался на пользовательские записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="2deee-102">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="2deee-103">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="2deee-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customTrackingQueries>**  
  
## <a name="syntax"></a><span data-ttu-id="2deee-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2deee-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2deee-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="2deee-105">Attributes and Elements</span></span>  
 <span data-ttu-id="2deee-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="2deee-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2deee-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="2deee-107">Attributes</span></span>  
 <span data-ttu-id="2deee-108">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="2deee-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2deee-109">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="2deee-109">Child Elements</span></span>  
  
|<span data-ttu-id="2deee-110">Элемент</span><span class="sxs-lookup"><span data-stu-id="2deee-110">Element</span></span>|<span data-ttu-id="2deee-111">Описание</span><span class="sxs-lookup"><span data-stu-id="2deee-111">Description</span></span>|  
|-------------|-----------------|  
|[\<customTrackingQuery>](customtrackingquery.md)|<span data-ttu-id="2deee-112">Запрос, который используется для отслеживания событий, определенных в действиях кода.</span><span class="sxs-lookup"><span data-stu-id="2deee-112">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2deee-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="2deee-113">Parent Elements</span></span>  
  
|<span data-ttu-id="2deee-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="2deee-114">Element</span></span>|<span data-ttu-id="2deee-115">Описание</span><span class="sxs-lookup"><span data-stu-id="2deee-115">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](workflow.md)|<span data-ttu-id="2deee-116">Элемент конфигурации, содержащий все запросы для определенного рабочего процесса, определяемого свойством **ActivityDefinitionId** .</span><span class="sxs-lookup"><span data-stu-id="2deee-116">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2deee-117">См. также</span><span class="sxs-lookup"><span data-stu-id="2deee-117">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="2deee-118">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="2deee-118">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="2deee-119">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="2deee-119">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
