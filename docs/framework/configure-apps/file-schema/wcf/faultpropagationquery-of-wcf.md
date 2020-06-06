---
title: <faultPropagationQuery>WCF
ms.date: 03/30/2017
ms.assetid: fabafbc8-3e45-4feb-8321-0725e9f4079c
ms.openlocfilehash: a6ef4e198caec4a1f21cedf2ff46d390aeaa2d3b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855328"
---
# <a name="faultpropagationquery-of-wcf"></a><span data-ttu-id="b3f23-102">\<faultPropagationQuery>WCF</span><span class="sxs-lookup"><span data-stu-id="b3f23-102">\<faultPropagationQuery> of WCF</span></span>

<span data-ttu-id="b3f23-103">Представляет запрос, который используется для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="b3f23-103">Represents a query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="b3f23-104">Это событие возникает каждый раз, когда FaultHandler обрабатывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="b3f23-104">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="b3f23-105">Такой запрос следует использовать для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="b3f23-105">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="b3f23-106">Этот запрос необходим, чтобы участник отслеживания подписался на записи распространения ошибок.</span><span class="sxs-lookup"><span data-stu-id="b3f23-106">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>

<span data-ttu-id="b3f23-107">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="b3f23-107">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<faultPropagationQueries>**](faultpropagationqueries-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<faultPropagationQuery>**  

## <a name="syntax"></a><span data-ttu-id="b3f23-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b3f23-108">Syntax</span></span>

```xml
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <faultPropagationQueries>
          <faultPropagationQuery faultSourceActivityName="String"
                                 faultHandlerActivityName="String" />
        </faultPropagationQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b3f23-109">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="b3f23-109">Attributes and elements</span></span>

<span data-ttu-id="b3f23-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="b3f23-110">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="b3f23-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b3f23-111">Attributes</span></span>

|<span data-ttu-id="b3f23-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="b3f23-112">Attribute</span></span>|<span data-ttu-id="b3f23-113">Описание:</span><span class="sxs-lookup"><span data-stu-id="b3f23-113">Description</span></span>|
|---------------|-----------------|
|`faultSourceActivityName`|<span data-ttu-id="b3f23-114">Строка, указывающая имя действия обработчика сбоев, которое распространило ошибку.</span><span class="sxs-lookup"><span data-stu-id="b3f23-114">A string that specifies the name of the fault handler activity that propagated the fault.</span></span> <span data-ttu-id="b3f23-115">Значение по умолчанию — \* , что означает, что для всех действий возвращаются записи распространения ошибок.</span><span class="sxs-lookup"><span data-stu-id="b3f23-115">The default is \*, which indicates that fault propagation records are returned for all activities.</span></span>|
|`faultHandlerActivityName`|<span data-ttu-id="b3f23-116">Строка, указывающая имя действия, ставшего источником ошибки.</span><span class="sxs-lookup"><span data-stu-id="b3f23-116">A string that specifies the name of the activity that was the source of the fault.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="b3f23-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b3f23-117">Child elements</span></span>

<span data-ttu-id="b3f23-118">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="b3f23-118">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="b3f23-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b3f23-119">Parent elements</span></span>

|<span data-ttu-id="b3f23-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="b3f23-120">Element</span></span>|<span data-ttu-id="b3f23-121">Описание</span><span class="sxs-lookup"><span data-stu-id="b3f23-121">Description</span></span>|
|-------------|-----------------|
|[\<faultPropagationQueries>](faultpropagationqueries-of-wcf.md)|<span data-ttu-id="b3f23-122">Представляет список элементов конфигурации, которые используются для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="b3f23-122">Represents a list of configuration elements that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="b3f23-123">Это событие возникает каждый раз, когда FaultHandler обрабатывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="b3f23-123">This event occurs each time a FaultHandler processes a fault.</span></span>|

## <a name="see-also"></a><span data-ttu-id="b3f23-124">См. также</span><span class="sxs-lookup"><span data-stu-id="b3f23-124">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="b3f23-125">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="b3f23-125">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="b3f23-126">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="b3f23-126">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
