---
title: <faultPropagationQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4fb5c2b1-3dad-4eca-9c7f-3efb51899813
ms.openlocfilehash: 6b43a570b4d4534adce1ef5ab394849651e3ac0e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398716"
---
# \<faultPropagationQuery>

<span data-ttu-id="4ddda-101">Представляет запрос, который используется для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="4ddda-101">Represents a query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="4ddda-102">Это событие возникает каждый раз, когда FaultHandler обрабатывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="4ddda-102">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="4ddda-103">Такой запрос следует использовать для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="4ddda-103">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="4ddda-104">Этот запрос необходим, чтобы участник отслеживания подписался на записи распространения ошибок.</span><span class="sxs-lookup"><span data-stu-id="4ddda-104">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>

 <span data-ttu-id="4ddda-105">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="4ddda-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<faultPropagationQueries>**](faultpropagationqueries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<faultPropagationQuery>**

## <a name="syntax"></a><span data-ttu-id="4ddda-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4ddda-106">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="4ddda-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="4ddda-107">Attributes and Elements</span></span>

<span data-ttu-id="4ddda-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="4ddda-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="4ddda-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="4ddda-109">Attributes</span></span>

|<span data-ttu-id="4ddda-110">Атрибут</span><span class="sxs-lookup"><span data-stu-id="4ddda-110">Attribute</span></span>|<span data-ttu-id="4ddda-111">Описание:</span><span class="sxs-lookup"><span data-stu-id="4ddda-111">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="4ddda-112">activityName</span><span class="sxs-lookup"><span data-stu-id="4ddda-112">activityName</span></span>|<span data-ttu-id="4ddda-113">Строка, указывающая имя действия обработчика сбоев, которое распространило ошибку.</span><span class="sxs-lookup"><span data-stu-id="4ddda-113">A string that specifies the name of the fault handler activity that propagated the fault.</span></span> <span data-ttu-id="4ddda-114">Значение по умолчанию - «\*», которое указывает на то, что записи распространения ошибок возвращаются для всех действий.</span><span class="sxs-lookup"><span data-stu-id="4ddda-114">The default is \*, which indicates that fault propagation records are returned for all activities.</span></span>|
|<span data-ttu-id="4ddda-115">faultHandlerActivityName</span><span class="sxs-lookup"><span data-stu-id="4ddda-115">faultHandlerActivityName</span></span>|<span data-ttu-id="4ddda-116">Строка, указывающая имя действия, ставшего источником ошибки.</span><span class="sxs-lookup"><span data-stu-id="4ddda-116">A string that specifies the name of the activity that was the source of the fault.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="4ddda-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="4ddda-117">Child Elements</span></span>

<span data-ttu-id="4ddda-118">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="4ddda-118">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="4ddda-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="4ddda-119">Parent Elements</span></span>

|<span data-ttu-id="4ddda-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="4ddda-120">Element</span></span>|<span data-ttu-id="4ddda-121">Описание</span><span class="sxs-lookup"><span data-stu-id="4ddda-121">Description</span></span>|
|-------------|-----------------|
|[\<faultPropagationQueries>](faultpropagationqueries.md)|<span data-ttu-id="4ddda-122">Представляет список элементов конфигурации, которые используются для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="4ddda-122">Represents a list of configuration elements that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="4ddda-123">Это событие возникает каждый раз, когда FaultHandler обрабатывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="4ddda-123">This event occurs each time a FaultHandler processes a fault.</span></span>|

## <a name="see-also"></a><span data-ttu-id="4ddda-124">См. также</span><span class="sxs-lookup"><span data-stu-id="4ddda-124">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="4ddda-125">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="4ddda-125">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="4ddda-126">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="4ddda-126">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
