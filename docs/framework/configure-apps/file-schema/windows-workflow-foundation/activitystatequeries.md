---
title: <activityStateQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: bdd3c8ae-a13f-4df1-9b3c-a9d6c4bb1b5f
ms.openlocfilehash: 4663ccedcafb6b151de75568afd3743c83c75224
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91189829"
---
# \<activityStateQueries>

<span data-ttu-id="29859-101">Представляет коллекцию запросов, которые используются для отслеживания изменений жизненного цикла действий, составляющих экземпляр рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="29859-101">Represents a collection of queries that are used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="29859-102">Например, вы можете захотеть отследить каждый раз, когда действие "отправить электронное письмо" завершается в рамках экземпляра рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="29859-102">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="29859-103">Этот запрос необходим, чтобы участник отслеживания мог подписываться на объекты записей состояния действия.</span><span class="sxs-lookup"><span data-stu-id="29859-103">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="29859-104">Состояния, доступные для подписки, указаны в ActivtyStates.</span><span class="sxs-lookup"><span data-stu-id="29859-104">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
 <span data-ttu-id="29859-105">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="29859-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityStateQueries>**  
  
## <a name="syntax"></a><span data-ttu-id="29859-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="29859-106">Syntax</span></span>  
  
```xml
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <arguments>
          <argument name="String" />
        </arguments>
        <states>
          <state name="String" />
        </states>
        <variables>
         <variable name="String" />
        </variables>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="29859-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="29859-107">Attributes and Elements</span></span>  

 <span data-ttu-id="29859-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="29859-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="29859-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="29859-109">Attributes</span></span>  

 <span data-ttu-id="29859-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="29859-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="29859-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="29859-111">Child Elements</span></span>  
  
|<span data-ttu-id="29859-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="29859-112">Element</span></span>|<span data-ttu-id="29859-113">Описание</span><span class="sxs-lookup"><span data-stu-id="29859-113">Description</span></span>|  
|-------------|-----------------|  
|[\<activityStateQuery>](activitystatequery.md)|<span data-ttu-id="29859-114">Запрос, который используется для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="29859-114">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="29859-115">Это событие возникает каждый раз, когда FaultHandler обрабатывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="29859-115">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="29859-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="29859-116">Parent Elements</span></span>  
  
|<span data-ttu-id="29859-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="29859-117">Element</span></span>|<span data-ttu-id="29859-118">Описание</span><span class="sxs-lookup"><span data-stu-id="29859-118">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](workflow.md)|<span data-ttu-id="29859-119">Элемент конфигурации, содержащий все запросы для определенного рабочего процесса, определяемого свойством **ActivityDefinitionId** .</span><span class="sxs-lookup"><span data-stu-id="29859-119">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="29859-120">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="29859-120">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="29859-121">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="29859-121">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="29859-122">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="29859-122">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
