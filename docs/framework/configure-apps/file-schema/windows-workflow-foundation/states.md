---
title: <states>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ebea5e7c-ad58-43c5-8f2d-cca25ae1b721
ms.openlocfilehash: e759f86e7746eaf3fdd72ed923612b24ef9b0c23
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91150821"
---
# \<states>

<span data-ttu-id="95475-101">Представляет коллекцию состояний, на которые установлена подписка, из отслеживаемого экземпляра рабочего процесса в момент создания записей отслеживания.</span><span class="sxs-lookup"><span data-stu-id="95475-101">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="95475-102">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="95475-102">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQueries>**](workflowinstancequeries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQuery>**](workflowinstancequery.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<states>**  
  
## <a name="syntax"></a><span data-ttu-id="95475-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="95475-103">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <workflowInstanceQueries>
        <workflowInstanceQuery>
          <states>
            <state name="Name"/>
          </states>
        </workflowInstanceQuery>
      </workflowInstanceQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="95475-104">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="95475-104">Attributes and Elements</span></span>  

 <span data-ttu-id="95475-105">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="95475-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="95475-106">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="95475-106">Attributes</span></span>  

 <span data-ttu-id="95475-107">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="95475-107">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="95475-108">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="95475-108">Child Elements</span></span>  
  
|<span data-ttu-id="95475-109">Элемент</span><span class="sxs-lookup"><span data-stu-id="95475-109">Element</span></span>|<span data-ttu-id="95475-110">Описание</span><span class="sxs-lookup"><span data-stu-id="95475-110">Description</span></span>|  
|-------------|-----------------|  
|[\<state>](states.md)|<span data-ttu-id="95475-111">Подписанное состояние от экземпляра рабочего процесса, который отслеживается в момент создания записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="95475-111">A subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="95475-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="95475-112">Parent Elements</span></span>  
  
|<span data-ttu-id="95475-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="95475-113">Element</span></span>|<span data-ttu-id="95475-114">Описание</span><span class="sxs-lookup"><span data-stu-id="95475-114">Description</span></span>|  
|-------------|-----------------|  
|[\<workflowInstanceQuery>](workflowinstancequery.md)|<span data-ttu-id="95475-115">Запрос, отслеживающий изменения жизненного цикла экземпляра рабочего процесса, например начавшиеся и завершенные события.</span><span class="sxs-lookup"><span data-stu-id="95475-115">A query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="95475-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="95475-116">Remarks</span></span>  

 <span data-ttu-id="95475-117">Возвращаемые записи фильтруются по состояниям в этой коллекции.</span><span class="sxs-lookup"><span data-stu-id="95475-117">The returned records are filtered by the states in this collection.</span></span>  
  
 <span data-ttu-id="95475-118">Допустимые значения состояния описаны в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="95475-118">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="95475-119">Состояние</span><span class="sxs-lookup"><span data-stu-id="95475-119">State</span></span>|<span data-ttu-id="95475-120">Описание</span><span class="sxs-lookup"><span data-stu-id="95475-120">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="95475-121">Прерывание</span><span class="sxs-lookup"><span data-stu-id="95475-121">Aborted</span></span>|<span data-ttu-id="95475-122">Экземпляр рабочего процесса прерван.</span><span class="sxs-lookup"><span data-stu-id="95475-122">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="95475-123">Завершено</span><span class="sxs-lookup"><span data-stu-id="95475-123">Completed</span></span>|<span data-ttu-id="95475-124">Выполнение экземпляра рабочего процесса завершено.</span><span class="sxs-lookup"><span data-stu-id="95475-124">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="95475-125">Удаленная</span><span class="sxs-lookup"><span data-stu-id="95475-125">Deleted</span></span>|<span data-ttu-id="95475-126">Экземпляр рабочего процесса удален.</span><span class="sxs-lookup"><span data-stu-id="95475-126">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="95475-127">Бездействие</span><span class="sxs-lookup"><span data-stu-id="95475-127">Idle</span></span>|<span data-ttu-id="95475-128">Экземпляр рабочего процесса простаивает.</span><span class="sxs-lookup"><span data-stu-id="95475-128">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="95475-129">Persisted</span><span class="sxs-lookup"><span data-stu-id="95475-129">Persisted</span></span>|<span data-ttu-id="95475-130">Экземпляр рабочего процесса сохранен.</span><span class="sxs-lookup"><span data-stu-id="95475-130">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="95475-131">Возобновление</span><span class="sxs-lookup"><span data-stu-id="95475-131">Resumed</span></span>|<span data-ttu-id="95475-132">Экземпляр рабочего процесса возобновлен.</span><span class="sxs-lookup"><span data-stu-id="95475-132">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="95475-133">Запуск</span><span class="sxs-lookup"><span data-stu-id="95475-133">Started</span></span>|<span data-ttu-id="95475-134">Экземпляр рабочего процесса запущен.</span><span class="sxs-lookup"><span data-stu-id="95475-134">The workflow instance is started.</span></span>|  
|<span data-ttu-id="95475-135">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="95475-135">UnhandledException</span></span>|<span data-ttu-id="95475-136">Экземпляр рабочего процесса встретил необработанное исключение.</span><span class="sxs-lookup"><span data-stu-id="95475-136">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="95475-137">Выгружен</span><span class="sxs-lookup"><span data-stu-id="95475-137">Unloaded</span></span>|<span data-ttu-id="95475-138">Экземпляр рабочего процесса выгружен.</span><span class="sxs-lookup"><span data-stu-id="95475-138">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="95475-139">Отменено</span><span class="sxs-lookup"><span data-stu-id="95475-139">Canceled</span></span>|<span data-ttu-id="95475-140">Выполнение экземпляра рабочего процесса отменено.</span><span class="sxs-lookup"><span data-stu-id="95475-140">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="95475-141">Приостановлена</span><span class="sxs-lookup"><span data-stu-id="95475-141">Suspended</span></span>|<span data-ttu-id="95475-142">Выполнение экземпляра рабочего процесса приостановлено.</span><span class="sxs-lookup"><span data-stu-id="95475-142">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="95475-143">Завершен</span><span class="sxs-lookup"><span data-stu-id="95475-143">Terminated</span></span>|<span data-ttu-id="95475-144">Выполнение экземпляра рабочего процесса завершено.</span><span class="sxs-lookup"><span data-stu-id="95475-144">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="95475-145">Возобновлено</span><span class="sxs-lookup"><span data-stu-id="95475-145">Unsuspended</span></span>|<span data-ttu-id="95475-146">Выполнение экземпляра рабочего процесса возобновлено.</span><span class="sxs-lookup"><span data-stu-id="95475-146">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="95475-147">Пример</span><span class="sxs-lookup"><span data-stu-id="95475-147">Example</span></span>  

 <span data-ttu-id="95475-148">При использовании следующей конфигурации устанавливается подписка на записи отслеживания рабочего процесса на уровне экземпляра для состояния экземпляра `Started` при помощи данного запроса.</span><span class="sxs-lookup"><span data-stu-id="95475-148">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="95475-149">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="95475-149">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="95475-150">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="95475-150">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="95475-151">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="95475-151">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
