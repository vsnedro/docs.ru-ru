---
title: <faultPropagationQueries>WCF
ms.date: 03/30/2017
ms.assetid: d85f66a7-e7b0-4dbb-83cc-89fa06fc9161
ms.openlocfilehash: 709c2c6907b4d0d28118f9de12edb047aa16d741
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855265"
---
# <a name="faultpropagationqueries-of-wcf"></a><span data-ttu-id="2989b-102">\<faultPropagationQueries>WCF</span><span class="sxs-lookup"><span data-stu-id="2989b-102">\<faultPropagationQueries> of WCF</span></span>

<span data-ttu-id="2989b-103">Представляет коллекцию запросов, которые используются для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="2989b-103">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="2989b-104">Это событие возникает каждый раз, когда FaultHandler обрабатывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="2989b-104">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="2989b-105">Такой запрос следует использовать для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="2989b-105">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="2989b-106">Этот запрос необходим, чтобы участник отслеживания подписался на записи распространения ошибок.</span><span class="sxs-lookup"><span data-stu-id="2989b-106">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
<span data-ttu-id="2989b-107">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="2989b-107">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<faultPropagationQueries>**  
  
## <a name="syntax"></a><span data-ttu-id="2989b-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2989b-108">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <faultPropagationQueries>
          <faultPropagationQuery faultSourceActivityName="String"
                                 faultHandlerActivityName="String"/>
        </faultPropagationQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2989b-109">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="2989b-109">Attributes and elements</span></span>

<span data-ttu-id="2989b-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="2989b-110">The following sections describe attributes, child elements, and parent elements.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="2989b-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="2989b-111">Attributes</span></span>

<span data-ttu-id="2989b-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="2989b-112">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="2989b-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="2989b-113">Child elements</span></span>

|<span data-ttu-id="2989b-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="2989b-114">Element</span></span>|<span data-ttu-id="2989b-115">Описание</span><span class="sxs-lookup"><span data-stu-id="2989b-115">Description</span></span>|  
|-------------|-----------------|  
|[\<faultPropagationQuery>](faultpropagationquery-of-wcf.md)|<span data-ttu-id="2989b-116">Запрос, который используется для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="2989b-116">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="2989b-117">Это событие возникает каждый раз, когда FaultHandler обрабатывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="2989b-117">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2989b-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="2989b-118">Parent elements</span></span>  
  
|<span data-ttu-id="2989b-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="2989b-119">Element</span></span>|<span data-ttu-id="2989b-120">Описание</span><span class="sxs-lookup"><span data-stu-id="2989b-120">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="2989b-121">Элемент конфигурации, содержащий все запросы для определенного рабочего процесса, обозначенного свойством `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="2989b-121">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2989b-122">См. также</span><span class="sxs-lookup"><span data-stu-id="2989b-122">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="2989b-123">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="2989b-123">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="2989b-124">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="2989b-124">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
