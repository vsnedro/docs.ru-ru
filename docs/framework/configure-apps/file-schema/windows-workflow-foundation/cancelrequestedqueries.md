---
title: <cancelRequestedQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: eab5af7e-76fa-434d-9d36-873e995cee05
ms.openlocfilehash: 89297b3a7d64f4300a735d8512230d441836c634
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152311"
---
# \<cancelRequestedQueries>
<span data-ttu-id="540be-101">Представляет коллекцию запросов, используемых для отслеживания запросов по отмене дочернего действия родительским действием.</span><span class="sxs-lookup"><span data-stu-id="540be-101">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="540be-102">Этот запрос необходим, чтобы участник отслеживания подписался на объекты записей запросов на отмену.</span><span class="sxs-lookup"><span data-stu-id="540be-102">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="540be-103">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="540be-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cancelRequestedQueries>**  
  
## <a name="syntax"></a><span data-ttu-id="540be-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="540be-104">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <cancelRequestQueries>
        <cancelRequestQuery activityName="String"
                            childActivityName="String"/>
      </cancelRequestQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="540be-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="540be-105">Attributes and Elements</span></span>  
 <span data-ttu-id="540be-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="540be-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="540be-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="540be-107">Attributes</span></span>  
 <span data-ttu-id="540be-108">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="540be-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="540be-109">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="540be-109">Child Elements</span></span>  
  
|<span data-ttu-id="540be-110">Элемент</span><span class="sxs-lookup"><span data-stu-id="540be-110">Element</span></span>|<span data-ttu-id="540be-111">Описание</span><span class="sxs-lookup"><span data-stu-id="540be-111">Description</span></span>|  
|-------------|-----------------|  
|[\<cancelRequestedQuery>](cancelrequestedquery.md)|<span data-ttu-id="540be-112">Запрос, используемый для отслеживания запросов по отмене дочернего действия родительским.</span><span class="sxs-lookup"><span data-stu-id="540be-112">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="540be-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="540be-113">Parent Elements</span></span>  
  
|<span data-ttu-id="540be-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="540be-114">Element</span></span>|<span data-ttu-id="540be-115">Описание</span><span class="sxs-lookup"><span data-stu-id="540be-115">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](workflow.md)|<span data-ttu-id="540be-116">Элемент конфигурации, содержащий все запросы для определенного рабочего процесса, определяемого свойством **ActivityDefinitionId** .</span><span class="sxs-lookup"><span data-stu-id="540be-116">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="540be-117">См. также</span><span class="sxs-lookup"><span data-stu-id="540be-117">See also</span></span>

- [<span data-ttu-id="540be-118">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="540be-118">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="540be-119">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="540be-119">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
