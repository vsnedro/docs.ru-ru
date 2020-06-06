---
title: <customTrackingQueries>WCF
ms.date: 03/30/2017
ms.assetid: 14cfe47e-9935-4120-84f1-8f38de8ca4c1
ms.openlocfilehash: 2c4bd74ae346c536e8bc0ae454e638b7c76a40fc
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855433"
---
# <a name="customtrackingqueries-of-wcf"></a><span data-ttu-id="0acf4-102">\<customTrackingQueries>WCF</span><span class="sxs-lookup"><span data-stu-id="0acf4-102">\<customTrackingQueries> of WCF</span></span>

<span data-ttu-id="0acf4-103">Представляет коллекцию запросов, используемых для отслеживания событий, определенных в действиях кода.</span><span class="sxs-lookup"><span data-stu-id="0acf4-103">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="0acf4-104">Запрос необходим, чтобы участник отслеживания подписался на пользовательские записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="0acf4-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
<span data-ttu-id="0acf4-105">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="0acf4-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customTrackingQueries>**  

## <a name="syntax"></a><span data-ttu-id="0acf4-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0acf4-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0acf4-107">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="0acf4-107">Attributes and elements</span></span>

<span data-ttu-id="0acf4-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="0acf4-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0acf4-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="0acf4-109">Attributes</span></span>

<span data-ttu-id="0acf4-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="0acf4-110">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="0acf4-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="0acf4-111">Child elements</span></span>
  
|<span data-ttu-id="0acf4-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="0acf4-112">Element</span></span>|<span data-ttu-id="0acf4-113">Описание</span><span class="sxs-lookup"><span data-stu-id="0acf4-113">Description</span></span>|  
|-------------|-----------------|  
|[\<customTrackingQuery>](customtrackingquery-of-wcf.md)|<span data-ttu-id="0acf4-114">Запрос, который используется для отслеживания событий, определенных в действиях кода.</span><span class="sxs-lookup"><span data-stu-id="0acf4-114">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0acf4-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="0acf4-115">Parent elements</span></span>  
  
|<span data-ttu-id="0acf4-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="0acf4-116">Element</span></span>|<span data-ttu-id="0acf4-117">Описание</span><span class="sxs-lookup"><span data-stu-id="0acf4-117">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="0acf4-118">Элемент конфигурации, содержащий все запросы для определенного рабочего процесса, обозначенного свойством `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="0acf4-118">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0acf4-119">См. также</span><span class="sxs-lookup"><span data-stu-id="0acf4-119">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="0acf4-120">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="0acf4-120">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="0acf4-121">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="0acf4-121">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
