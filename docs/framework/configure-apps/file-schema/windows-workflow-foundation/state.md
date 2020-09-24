---
title: <state>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 619414f2-61c2-4427-9977-d05009e343db
ms.openlocfilehash: 169fa900b5be9a9577818b68b540184afd4a6681
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91169730"
---
# \<state>

<span data-ttu-id="e2059-101">Представляет коллекцию состояний, на которые установлена подписка, из отслеживаемого экземпляра рабочего процесса в момент создания записей отслеживания.</span><span class="sxs-lookup"><span data-stu-id="e2059-101">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="e2059-102">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="e2059-102">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQueries>**](workflowinstancequeries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQuery>**](workflowinstancequery.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<states>**](states.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<state>**  
  
## <a name="syntax"></a><span data-ttu-id="e2059-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e2059-103">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <workflowInstanceQueries>
        <workflowInstanceQuery>
          <states>
            <state name="Name" />
          </states>
        </workflowInstanceQuery>
      </workflowInstanceQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e2059-104">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e2059-104">Attributes and Elements</span></span>  

 <span data-ttu-id="e2059-105">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e2059-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e2059-106">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e2059-106">Attributes</span></span>  
  
|<span data-ttu-id="e2059-107">Атрибут</span><span class="sxs-lookup"><span data-stu-id="e2059-107">Attribute</span></span>|<span data-ttu-id="e2059-108">Описание</span><span class="sxs-lookup"><span data-stu-id="e2059-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e2059-109">name</span><span class="sxs-lookup"><span data-stu-id="e2059-109">name</span></span>|<span data-ttu-id="e2059-110">Строка, указывающая состояние подписки отслеживаемого экземпляра рабочего потока в момент создания записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="e2059-110">A string that specifies a subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e2059-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e2059-111">Child Elements</span></span>  

 <span data-ttu-id="e2059-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="e2059-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e2059-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e2059-113">Parent Elements</span></span>  
  
|<span data-ttu-id="e2059-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="e2059-114">Element</span></span>|<span data-ttu-id="e2059-115">Описание</span><span class="sxs-lookup"><span data-stu-id="e2059-115">Description</span></span>|  
|-------------|-----------------|  
|[\<states>](states.md)|<span data-ttu-id="e2059-116">Коллекция состояний, на которые установлена подписка, из отслеживаемого экземпляра рабочего процесса в момент создания записей отслеживания.</span><span class="sxs-lookup"><span data-stu-id="e2059-116">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e2059-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="e2059-117">Remarks</span></span>  

 <span data-ttu-id="e2059-118">Возвращаемые записи фильтруются по состояниям в этой коллекции.</span><span class="sxs-lookup"><span data-stu-id="e2059-118">The returned records are filtered by the states in this collection.</span></span>  
  
 <span data-ttu-id="e2059-119">Допустимые значения состояния описаны в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="e2059-119">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="e2059-120">Состояние</span><span class="sxs-lookup"><span data-stu-id="e2059-120">State</span></span>|<span data-ttu-id="e2059-121">Описание</span><span class="sxs-lookup"><span data-stu-id="e2059-121">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e2059-122">Прерывание</span><span class="sxs-lookup"><span data-stu-id="e2059-122">Aborted</span></span>|<span data-ttu-id="e2059-123">Экземпляр рабочего процесса прерван.</span><span class="sxs-lookup"><span data-stu-id="e2059-123">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="e2059-124">Завершено</span><span class="sxs-lookup"><span data-stu-id="e2059-124">Completed</span></span>|<span data-ttu-id="e2059-125">Выполнение экземпляра рабочего процесса завершено.</span><span class="sxs-lookup"><span data-stu-id="e2059-125">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="e2059-126">Удаленная</span><span class="sxs-lookup"><span data-stu-id="e2059-126">Deleted</span></span>|<span data-ttu-id="e2059-127">Экземпляр рабочего процесса удален.</span><span class="sxs-lookup"><span data-stu-id="e2059-127">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="e2059-128">Бездействие</span><span class="sxs-lookup"><span data-stu-id="e2059-128">Idle</span></span>|<span data-ttu-id="e2059-129">Экземпляр рабочего процесса простаивает.</span><span class="sxs-lookup"><span data-stu-id="e2059-129">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="e2059-130">Persisted</span><span class="sxs-lookup"><span data-stu-id="e2059-130">Persisted</span></span>|<span data-ttu-id="e2059-131">Экземпляр рабочего процесса сохранен.</span><span class="sxs-lookup"><span data-stu-id="e2059-131">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="e2059-132">Возобновление</span><span class="sxs-lookup"><span data-stu-id="e2059-132">Resumed</span></span>|<span data-ttu-id="e2059-133">Экземпляр рабочего процесса возобновлен.</span><span class="sxs-lookup"><span data-stu-id="e2059-133">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="e2059-134">Запуск</span><span class="sxs-lookup"><span data-stu-id="e2059-134">Started</span></span>|<span data-ttu-id="e2059-135">Экземпляр рабочего процесса запущен.</span><span class="sxs-lookup"><span data-stu-id="e2059-135">The workflow instance is started.</span></span>|  
|<span data-ttu-id="e2059-136">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="e2059-136">UnhandledException</span></span>|<span data-ttu-id="e2059-137">Экземпляр рабочего процесса встретил необработанное исключение.</span><span class="sxs-lookup"><span data-stu-id="e2059-137">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="e2059-138">Выгружен</span><span class="sxs-lookup"><span data-stu-id="e2059-138">Unloaded</span></span>|<span data-ttu-id="e2059-139">Экземпляр рабочего процесса выгружен.</span><span class="sxs-lookup"><span data-stu-id="e2059-139">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="e2059-140">Отменено</span><span class="sxs-lookup"><span data-stu-id="e2059-140">Canceled</span></span>|<span data-ttu-id="e2059-141">Выполнение экземпляра рабочего процесса отменено.</span><span class="sxs-lookup"><span data-stu-id="e2059-141">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="e2059-142">Приостановлена</span><span class="sxs-lookup"><span data-stu-id="e2059-142">Suspended</span></span>|<span data-ttu-id="e2059-143">Выполнение экземпляра рабочего процесса приостановлено.</span><span class="sxs-lookup"><span data-stu-id="e2059-143">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="e2059-144">Завершен</span><span class="sxs-lookup"><span data-stu-id="e2059-144">Terminated</span></span>|<span data-ttu-id="e2059-145">Выполнение экземпляра рабочего процесса завершено.</span><span class="sxs-lookup"><span data-stu-id="e2059-145">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="e2059-146">Возобновлено</span><span class="sxs-lookup"><span data-stu-id="e2059-146">Unsuspended</span></span>|<span data-ttu-id="e2059-147">Выполнение экземпляра рабочего процесса возобновлено.</span><span class="sxs-lookup"><span data-stu-id="e2059-147">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e2059-148">Пример</span><span class="sxs-lookup"><span data-stu-id="e2059-148">Example</span></span>  

 <span data-ttu-id="e2059-149">При использовании следующей конфигурации устанавливается подписка на записи отслеживания рабочего процесса на уровне экземпляра для состояния экземпляра `Started` при помощи данного запроса.</span><span class="sxs-lookup"><span data-stu-id="e2059-149">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e2059-150">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e2059-150">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="e2059-151">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="e2059-151">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="e2059-152">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="e2059-152">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
