---
title: <faultPropagationQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 00ff90ae-ebe0-4c85-a93f-61557288d0a3
ms.openlocfilehash: 24e9136729df1352ebb1e665d1ebaf0ce9dc28a5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91175841"
---
# \<faultPropagationQueries>

<span data-ttu-id="7e306-101">Представляет коллекцию запросов, которые используются для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="7e306-101">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="7e306-102">Это событие возникает каждый раз, когда FaultHandler обрабатывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="7e306-102">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="7e306-103">Такой запрос следует использовать для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="7e306-103">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="7e306-104">Этот запрос необходим, чтобы участник отслеживания подписался на записи распространения ошибок.</span><span class="sxs-lookup"><span data-stu-id="7e306-104">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
 <span data-ttu-id="7e306-105">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="7e306-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<faultPropagationQueries>**
  
## <a name="syntax"></a><span data-ttu-id="7e306-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7e306-106">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <faultPropagationQueries>
        <faultPropagationQuery activityName="String"
                               faultHandlerActivityName="String" />
      </faultPropagationQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7e306-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="7e306-107">Attributes and Elements</span></span>  

 <span data-ttu-id="7e306-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="7e306-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7e306-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="7e306-109">Attributes</span></span>  

 <span data-ttu-id="7e306-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="7e306-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7e306-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="7e306-111">Child Elements</span></span>  
  
|<span data-ttu-id="7e306-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="7e306-112">Element</span></span>|<span data-ttu-id="7e306-113">Описание</span><span class="sxs-lookup"><span data-stu-id="7e306-113">Description</span></span>|  
|-------------|-----------------|  
|[\<faultPropagationQuery>](faultpropagationquery.md)|<span data-ttu-id="7e306-114">Запрос, который используется для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="7e306-114">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="7e306-115">Это событие возникает каждый раз, когда FaultHandler обрабатывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="7e306-115">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7e306-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="7e306-116">Parent Elements</span></span>  
  
|<span data-ttu-id="7e306-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="7e306-117">Element</span></span>|<span data-ttu-id="7e306-118">Описание</span><span class="sxs-lookup"><span data-stu-id="7e306-118">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](workflow.md)|<span data-ttu-id="7e306-119">Элемент конфигурации, содержащий все запросы для определенного рабочего процесса, определяемого свойством **ActivityDefinitionId** .</span><span class="sxs-lookup"><span data-stu-id="7e306-119">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7e306-120">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="7e306-120">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="7e306-121">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="7e306-121">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="7e306-122">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="7e306-122">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
