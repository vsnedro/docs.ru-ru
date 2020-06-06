---
title: <cancelRequestedQueries>WCF
ms.date: 03/30/2017
ms.assetid: a7cc7125-9ea3-4d3f-99c0-878cdeb1258a
ms.openlocfilehash: 63cfc835ac7ce88bde56fd9243a2cf6652cbce6e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850092"
---
# <a name="cancelrequestedqueries-of-wcf"></a><span data-ttu-id="81f57-102">\<cancelRequestedQueries>WCF</span><span class="sxs-lookup"><span data-stu-id="81f57-102">\<cancelRequestedQueries> of WCF</span></span>
<span data-ttu-id="81f57-103">Представляет коллекцию запросов, используемых для отслеживания запросов по отмене дочернего действия родительским действием.</span><span class="sxs-lookup"><span data-stu-id="81f57-103">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="81f57-104">Этот запрос необходим, чтобы участник отслеживания подписался на объекты записей запросов на отмену.</span><span class="sxs-lookup"><span data-stu-id="81f57-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
<span data-ttu-id="81f57-105">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="81f57-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cancelRequestedQueries>**  
  
## <a name="syntax"></a><span data-ttu-id="81f57-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="81f57-106">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <cancelRequestQueries>
          <cancelRequestQuery activityName="String"
                              childActivityName="String" />
        </cancelRequestQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="81f57-107">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="81f57-107">Attributes and elements</span></span>  

<span data-ttu-id="81f57-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="81f57-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="81f57-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="81f57-109">Attributes</span></span>

<span data-ttu-id="81f57-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="81f57-110">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="81f57-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="81f57-111">Child elements</span></span>
  
|<span data-ttu-id="81f57-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="81f57-112">Element</span></span>|<span data-ttu-id="81f57-113">Описание</span><span class="sxs-lookup"><span data-stu-id="81f57-113">Description</span></span>|  
|-------------|-----------------|  
|[\<cancelRequestedQuery>](cancelrequestedquery-of-wcf.md)|<span data-ttu-id="81f57-114">Запрос, используемый для отслеживания запросов по отмене дочернего действия родительским.</span><span class="sxs-lookup"><span data-stu-id="81f57-114">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="81f57-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="81f57-115">Parent elements</span></span>  
  
|<span data-ttu-id="81f57-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="81f57-116">Element</span></span>|<span data-ttu-id="81f57-117">Описание</span><span class="sxs-lookup"><span data-stu-id="81f57-117">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="81f57-118">Элемент конфигурации, содержащий все запросы для определенного рабочего процесса, обозначенного свойством <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId>.</span><span class="sxs-lookup"><span data-stu-id="81f57-118">A configuration element that contains all queries for a specific workflow identified by the <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId> property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="81f57-119">См. также</span><span class="sxs-lookup"><span data-stu-id="81f57-119">See also</span></span>

- <xref:System.Activities.Tracking.CancelRequestedQuery>
- [<span data-ttu-id="81f57-120">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="81f57-120">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="81f57-121">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="81f57-121">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
