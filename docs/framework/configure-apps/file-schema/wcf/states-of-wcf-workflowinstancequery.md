---
title: <states>WCF,<workflowInstanceQuery>
ms.date: 03/30/2017
ms.assetid: d17f7525-8035-4e9e-85a0-4cddae59f85d
ms.openlocfilehash: 5b779cf1074687dbd648b23d04f7cf3a354a2014
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855037"
---
# <a name="states-of-wcf-workflowinstancequery"></a><span data-ttu-id="7f50f-102">\<states>WCF,\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="7f50f-102">\<states> of WCF, \<workflowInstanceQuery></span></span>

<span data-ttu-id="7f50f-103">Представляет коллекцию состояний, на которые установлена подписка, из отслеживаемого экземпляра рабочего процесса в момент создания записей отслеживания.</span><span class="sxs-lookup"><span data-stu-id="7f50f-103">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
<span data-ttu-id="7f50f-104">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="7f50f-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQueries>**](workflowinstancequeries-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQuery>**](workflowinstancequery-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<states>**  
  
## <a name="syntax"></a><span data-ttu-id="7f50f-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7f50f-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7f50f-106">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="7f50f-106">Attributes and elements</span></span>

<span data-ttu-id="7f50f-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="7f50f-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7f50f-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="7f50f-108">Attributes</span></span>  

<span data-ttu-id="7f50f-109">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="7f50f-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7f50f-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="7f50f-110">Child elements</span></span>
  
|<span data-ttu-id="7f50f-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="7f50f-111">Element</span></span>|<span data-ttu-id="7f50f-112">Описание</span><span class="sxs-lookup"><span data-stu-id="7f50f-112">Description</span></span>|  
|-------------|-----------------|  
|[\<states>](state-of-wcf-workflowinstancequery.md)|<span data-ttu-id="7f50f-113">Подписанное состояние от экземпляра рабочего процесса, который отслеживается в момент создания записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="7f50f-113">A subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7f50f-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="7f50f-114">Parent elements</span></span>  
  
|<span data-ttu-id="7f50f-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="7f50f-115">Element</span></span>|<span data-ttu-id="7f50f-116">Описание</span><span class="sxs-lookup"><span data-stu-id="7f50f-116">Description</span></span>|  
|-------------|-----------------|  
|[\<workflowInstanceQuery>](../windows-workflow-foundation/workflowinstancequery.md)|<span data-ttu-id="7f50f-117">Запрос, отслеживающий изменения жизненного цикла экземпляра рабочего процесса, например начавшиеся и завершенные события.</span><span class="sxs-lookup"><span data-stu-id="7f50f-117">A query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7f50f-118">Примечания</span><span class="sxs-lookup"><span data-stu-id="7f50f-118">Remarks</span></span>

<span data-ttu-id="7f50f-119">Возвращаемые записи фильтруются по состояниям в этой коллекции.</span><span class="sxs-lookup"><span data-stu-id="7f50f-119">The returned records are filtered by the states in this collection.</span></span>  
  
<span data-ttu-id="7f50f-120">Допустимые значения состояния описаны в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="7f50f-120">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="7f50f-121">Состояние</span><span class="sxs-lookup"><span data-stu-id="7f50f-121">State</span></span>|<span data-ttu-id="7f50f-122">Описание</span><span class="sxs-lookup"><span data-stu-id="7f50f-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7f50f-123">Прерывание</span><span class="sxs-lookup"><span data-stu-id="7f50f-123">Aborted</span></span>|<span data-ttu-id="7f50f-124">Экземпляр рабочего процесса прерван.</span><span class="sxs-lookup"><span data-stu-id="7f50f-124">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="7f50f-125">Завершено</span><span class="sxs-lookup"><span data-stu-id="7f50f-125">Completed</span></span>|<span data-ttu-id="7f50f-126">Выполнение экземпляра рабочего процесса завершено.</span><span class="sxs-lookup"><span data-stu-id="7f50f-126">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="7f50f-127">Удаленная</span><span class="sxs-lookup"><span data-stu-id="7f50f-127">Deleted</span></span>|<span data-ttu-id="7f50f-128">Экземпляр рабочего процесса удален.</span><span class="sxs-lookup"><span data-stu-id="7f50f-128">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="7f50f-129">Бездействие</span><span class="sxs-lookup"><span data-stu-id="7f50f-129">Idle</span></span>|<span data-ttu-id="7f50f-130">Экземпляр рабочего процесса простаивает.</span><span class="sxs-lookup"><span data-stu-id="7f50f-130">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="7f50f-131">Сохранение</span><span class="sxs-lookup"><span data-stu-id="7f50f-131">Persisted</span></span>|<span data-ttu-id="7f50f-132">Экземпляр рабочего процесса сохранен.</span><span class="sxs-lookup"><span data-stu-id="7f50f-132">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="7f50f-133">Возобновление</span><span class="sxs-lookup"><span data-stu-id="7f50f-133">Resumed</span></span>|<span data-ttu-id="7f50f-134">Экземпляр рабочего процесса возобновлен.</span><span class="sxs-lookup"><span data-stu-id="7f50f-134">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="7f50f-135">Запуск</span><span class="sxs-lookup"><span data-stu-id="7f50f-135">Started</span></span>|<span data-ttu-id="7f50f-136">Экземпляр рабочего процесса запущен.</span><span class="sxs-lookup"><span data-stu-id="7f50f-136">The workflow instance is started.</span></span>|  
|<span data-ttu-id="7f50f-137">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="7f50f-137">UnhandledException</span></span>|<span data-ttu-id="7f50f-138">Экземпляр рабочего процесса встретил необработанное исключение.</span><span class="sxs-lookup"><span data-stu-id="7f50f-138">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="7f50f-139">Выгружен</span><span class="sxs-lookup"><span data-stu-id="7f50f-139">Unloaded</span></span>|<span data-ttu-id="7f50f-140">Экземпляр рабочего процесса выгружен.</span><span class="sxs-lookup"><span data-stu-id="7f50f-140">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="7f50f-141">Отменено</span><span class="sxs-lookup"><span data-stu-id="7f50f-141">Canceled</span></span>|<span data-ttu-id="7f50f-142">Выполнение экземпляра рабочего процесса отменено.</span><span class="sxs-lookup"><span data-stu-id="7f50f-142">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="7f50f-143">Приостановлена</span><span class="sxs-lookup"><span data-stu-id="7f50f-143">Suspended</span></span>|<span data-ttu-id="7f50f-144">Выполнение экземпляра рабочего процесса приостановлено.</span><span class="sxs-lookup"><span data-stu-id="7f50f-144">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="7f50f-145">Завершение</span><span class="sxs-lookup"><span data-stu-id="7f50f-145">Terminated</span></span>|<span data-ttu-id="7f50f-146">Выполнение экземпляра рабочего процесса завершено.</span><span class="sxs-lookup"><span data-stu-id="7f50f-146">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="7f50f-147">Возобновлено</span><span class="sxs-lookup"><span data-stu-id="7f50f-147">Unsuspended</span></span>|<span data-ttu-id="7f50f-148">Выполнение экземпляра рабочего процесса возобновлено.</span><span class="sxs-lookup"><span data-stu-id="7f50f-148">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="7f50f-149">Пример</span><span class="sxs-lookup"><span data-stu-id="7f50f-149">Example</span></span>

<span data-ttu-id="7f50f-150">При использовании следующей конфигурации устанавливается подписка на записи отслеживания рабочего процесса на уровне экземпляра для состояния экземпляра `Started` при помощи данного запроса.</span><span class="sxs-lookup"><span data-stu-id="7f50f-150">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>
  <workflowInstanceQuery>
    <states>
      <state name="Started" />
    </states>
  </workflowInstanceQuery>
</workflowInstanceQueries>
```  
  
## <a name="see-also"></a><span data-ttu-id="7f50f-151">См. также</span><span class="sxs-lookup"><span data-stu-id="7f50f-151">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="7f50f-152">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="7f50f-152">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="7f50f-153">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="7f50f-153">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
