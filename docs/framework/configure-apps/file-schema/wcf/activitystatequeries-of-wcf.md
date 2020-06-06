---
title: <activityStateQueries>WCF
ms.date: 10/08/2018
ms.assetid: 9e45db49-ed85-4fdf-bd65-0d5477e31823
ms.openlocfilehash: 249ac3d91f6251a943dd856e4122b8b54f691702
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850570"
---
# <a name="activitystatequeries-of-wcf"></a><span data-ttu-id="20ddf-102">\<activityStateQueries>WCF</span><span class="sxs-lookup"><span data-stu-id="20ddf-102">\<activityStateQueries> of WCF</span></span>

<span data-ttu-id="20ddf-103">Представляет коллекцию запросов, которые используются для отслеживания изменений жизненного цикла действий, составляющих экземпляр рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="20ddf-103">Represents a collection of queries that are used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="20ddf-104">Например, вы можете захотеть отследить каждый раз, когда действие "отправить электронное письмо" завершается в рамках экземпляра рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="20ddf-104">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="20ddf-105">Этот запрос необходим, чтобы участник отслеживания мог подписываться на объекты записей состояния действия.</span><span class="sxs-lookup"><span data-stu-id="20ddf-105">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="20ddf-106">Состояния, доступные для подписки, указаны в ActivtyStates.</span><span class="sxs-lookup"><span data-stu-id="20ddf-106">The available states to subscribe to are specified in ActivityStates.</span></span>

<span data-ttu-id="20ddf-107">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="20ddf-107">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityStateQueries>**  
  
## <a name="syntax"></a><span data-ttu-id="20ddf-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="20ddf-108">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <activityStateQueries>
          <activityStateQuery activityName="String">
            <arguments>
              <argument name="String" />
            </arguments>
            <states>
              <state name="String" />
            </states>
            <variables>
              <variable name="String" />
            </variables>
          </activityStateQuery>
        </activityStateQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  

## <a name="attributes-and-elements"></a><span data-ttu-id="20ddf-109">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="20ddf-109">Attributes and elements</span></span>

<span data-ttu-id="20ddf-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="20ddf-110">The following sections describe attributes, child elements, and parent elements.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="20ddf-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="20ddf-111">Attributes</span></span>  

<span data-ttu-id="20ddf-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="20ddf-112">None.</span></span>  

### <a name="child-elements"></a><span data-ttu-id="20ddf-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="20ddf-113">Child elements</span></span>

|<span data-ttu-id="20ddf-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="20ddf-114">Element</span></span>|<span data-ttu-id="20ddf-115">Описание</span><span class="sxs-lookup"><span data-stu-id="20ddf-115">Description</span></span>|
|-------------|-----------------|
|[\<activityStateQuery>](activitystatequery-of-wcf.md)|<span data-ttu-id="20ddf-116">Запрос, который используется для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="20ddf-116">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="20ddf-117">Это событие возникает каждый раз, когда FaultHandler обрабатывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="20ddf-117">This event occurs each time a FaultHandler processes a fault.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="20ddf-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="20ddf-118">Parent elements</span></span>

|<span data-ttu-id="20ddf-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="20ddf-119">Element</span></span>|<span data-ttu-id="20ddf-120">Описание</span><span class="sxs-lookup"><span data-stu-id="20ddf-120">Description</span></span>|
|-------------|-----------------|
|[\<workflow>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="20ddf-121">Элемент конфигурации, содержащий все запросы для определенного рабочего процесса, обозначенного свойством `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="20ddf-121">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|

## <a name="see-also"></a><span data-ttu-id="20ddf-122">См. также</span><span class="sxs-lookup"><span data-stu-id="20ddf-122">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElementCollection>
- <xref:System.Activities.Tracking.ActivityStateQuery>
- [<span data-ttu-id="20ddf-123">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="20ddf-123">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="20ddf-124">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="20ddf-124">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
