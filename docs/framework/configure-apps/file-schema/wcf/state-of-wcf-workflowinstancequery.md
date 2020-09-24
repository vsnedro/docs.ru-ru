---
title: <state> WCF, <workflowInstanceQuery>
ms.date: 03/30/2017
ms.assetid: 40f21055-766c-4be9-86c4-d1d899007098
ms.openlocfilehash: c323f7dba265e7fbcb09482115694088e761af0e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148897"
---
# <a name="state-of-wcf-workflowinstancequery"></a><span data-ttu-id="93291-102">\<state> WCF, \<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="93291-102">\<state> of WCF, \<workflowInstanceQuery></span></span>

<span data-ttu-id="93291-103">Представляет коллекцию состояний, на которые установлена подписка, из отслеживаемого экземпляра рабочего процесса в момент создания записей отслеживания.</span><span class="sxs-lookup"><span data-stu-id="93291-103">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="93291-104">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="93291-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQueries>**](workflowinstancequeries-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQuery>**](workflowinstancequery-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<states>**](states-of-wcf-workflowinstancequery.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<state>**  
  
## <a name="syntax"></a><span data-ttu-id="93291-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="93291-105">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
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
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="93291-106">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="93291-106">Attributes and elements</span></span>

<span data-ttu-id="93291-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="93291-107">The following sections describe attributes, child elements, and parent elements.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="93291-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="93291-108">Attributes</span></span>

|<span data-ttu-id="93291-109">Атрибут</span><span class="sxs-lookup"><span data-stu-id="93291-109">Attribute</span></span>|<span data-ttu-id="93291-110">Описание</span><span class="sxs-lookup"><span data-stu-id="93291-110">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="93291-111">Строка, указывающая состояние подписки отслеживаемого экземпляра рабочего потока в момент создания записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="93291-111">A string that specifies a subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="93291-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="93291-112">Child elements</span></span>

<span data-ttu-id="93291-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="93291-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="93291-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="93291-114">Parent elements</span></span>

|<span data-ttu-id="93291-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="93291-115">Element</span></span>|<span data-ttu-id="93291-116">Описание</span><span class="sxs-lookup"><span data-stu-id="93291-116">Description</span></span>|  
|-------------|-----------------|  
|[\<states>](states-of-wcf-workflowinstancequery.md)|<span data-ttu-id="93291-117">Коллекция состояний, на которые установлена подписка, из отслеживаемого экземпляра рабочего процесса в момент создания записей отслеживания.</span><span class="sxs-lookup"><span data-stu-id="93291-117">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="93291-118">Remarks</span><span class="sxs-lookup"><span data-stu-id="93291-118">Remarks</span></span>  

<span data-ttu-id="93291-119">Возвращаемые записи фильтруются по состояниям в этой коллекции.</span><span class="sxs-lookup"><span data-stu-id="93291-119">The returned records are filtered by the states in this collection.</span></span>  
  
<span data-ttu-id="93291-120">Возможные значения состояния описаны в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="93291-120">Possible state values are described in the following table:</span></span>
  
|<span data-ttu-id="93291-121">Состояние</span><span class="sxs-lookup"><span data-stu-id="93291-121">State</span></span>|<span data-ttu-id="93291-122">Описание</span><span class="sxs-lookup"><span data-stu-id="93291-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="93291-123">Прерывание</span><span class="sxs-lookup"><span data-stu-id="93291-123">Aborted</span></span>|<span data-ttu-id="93291-124">Экземпляр рабочего процесса прерван.</span><span class="sxs-lookup"><span data-stu-id="93291-124">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="93291-125">Завершено</span><span class="sxs-lookup"><span data-stu-id="93291-125">Completed</span></span>|<span data-ttu-id="93291-126">Выполнение экземпляра рабочего процесса завершено.</span><span class="sxs-lookup"><span data-stu-id="93291-126">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="93291-127">Удаленная</span><span class="sxs-lookup"><span data-stu-id="93291-127">Deleted</span></span>|<span data-ttu-id="93291-128">Экземпляр рабочего процесса удален.</span><span class="sxs-lookup"><span data-stu-id="93291-128">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="93291-129">Бездействие</span><span class="sxs-lookup"><span data-stu-id="93291-129">Idle</span></span>|<span data-ttu-id="93291-130">Экземпляр рабочего процесса простаивает.</span><span class="sxs-lookup"><span data-stu-id="93291-130">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="93291-131">Persisted</span><span class="sxs-lookup"><span data-stu-id="93291-131">Persisted</span></span>|<span data-ttu-id="93291-132">Экземпляр рабочего процесса сохранен.</span><span class="sxs-lookup"><span data-stu-id="93291-132">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="93291-133">Возобновление</span><span class="sxs-lookup"><span data-stu-id="93291-133">Resumed</span></span>|<span data-ttu-id="93291-134">Экземпляр рабочего процесса возобновлен.</span><span class="sxs-lookup"><span data-stu-id="93291-134">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="93291-135">Запуск</span><span class="sxs-lookup"><span data-stu-id="93291-135">Started</span></span>|<span data-ttu-id="93291-136">Экземпляр рабочего процесса запущен.</span><span class="sxs-lookup"><span data-stu-id="93291-136">The workflow instance is started.</span></span>|  
|<span data-ttu-id="93291-137">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="93291-137">UnhandledException</span></span>|<span data-ttu-id="93291-138">Экземпляр рабочего процесса встретил необработанное исключение.</span><span class="sxs-lookup"><span data-stu-id="93291-138">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="93291-139">Выгружен</span><span class="sxs-lookup"><span data-stu-id="93291-139">Unloaded</span></span>|<span data-ttu-id="93291-140">Экземпляр рабочего процесса выгружен.</span><span class="sxs-lookup"><span data-stu-id="93291-140">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="93291-141">Отменено</span><span class="sxs-lookup"><span data-stu-id="93291-141">Canceled</span></span>|<span data-ttu-id="93291-142">Выполнение экземпляра рабочего процесса отменено.</span><span class="sxs-lookup"><span data-stu-id="93291-142">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="93291-143">Приостановлена</span><span class="sxs-lookup"><span data-stu-id="93291-143">Suspended</span></span>|<span data-ttu-id="93291-144">Выполнение экземпляра рабочего процесса приостановлено.</span><span class="sxs-lookup"><span data-stu-id="93291-144">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="93291-145">Завершен</span><span class="sxs-lookup"><span data-stu-id="93291-145">Terminated</span></span>|<span data-ttu-id="93291-146">Выполнение экземпляра рабочего процесса завершено.</span><span class="sxs-lookup"><span data-stu-id="93291-146">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="93291-147">Возобновлено</span><span class="sxs-lookup"><span data-stu-id="93291-147">Unsuspended</span></span>|<span data-ttu-id="93291-148">Выполнение экземпляра рабочего процесса возобновлено.</span><span class="sxs-lookup"><span data-stu-id="93291-148">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="93291-149">Пример</span><span class="sxs-lookup"><span data-stu-id="93291-149">Example</span></span>

<span data-ttu-id="93291-150">При использовании следующей конфигурации устанавливается подписка на записи отслеживания рабочего процесса на уровне экземпляра для состояния экземпляра `Started` при помощи данного запроса.</span><span class="sxs-lookup"><span data-stu-id="93291-150">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>
  <workflowInstanceQuery>
    <states>
      <state name="Started" />
    </states>
  </workflowInstanceQuery>
</workflowInstanceQueries>
```  
  
## <a name="see-also"></a><span data-ttu-id="93291-151">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="93291-151">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="93291-152">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="93291-152">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="93291-153">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="93291-153">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
