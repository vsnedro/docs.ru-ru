---
title: 224 - MessageThrottleAtSeventyPercent
ms.date: 03/30/2017
ms.assetid: 82bbbfd7-10d2-41fd-805d-2443b0c1b96b
ms.openlocfilehash: 26b860b88313a971960a65b599562ef1ccb4e7da
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96243525"
---
# <a name="224---messagethrottleatseventypercent"></a><span data-ttu-id="a6729-102">224 - MessageThrottleAtSeventyPercent</span><span class="sxs-lookup"><span data-stu-id="a6729-102">224 - MessageThrottleAtSeventyPercent</span></span>

## <a name="properties"></a><span data-ttu-id="a6729-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="a6729-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a6729-104">ID</span><span class="sxs-lookup"><span data-stu-id="a6729-104">ID</span></span>|<span data-ttu-id="a6729-105">224</span><span class="sxs-lookup"><span data-stu-id="a6729-105">224</span></span>|  
|<span data-ttu-id="a6729-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="a6729-106">Keywords</span></span>|<span data-ttu-id="a6729-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="a6729-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="a6729-108">Level</span><span class="sxs-lookup"><span data-stu-id="a6729-108">Level</span></span>|<span data-ttu-id="a6729-109">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="a6729-109">Warning</span></span>|  
|<span data-ttu-id="a6729-110">Канал</span><span class="sxs-lookup"><span data-stu-id="a6729-110">Channel</span></span>|<span data-ttu-id="a6729-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="a6729-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="a6729-112">Описание</span><span class="sxs-lookup"><span data-stu-id="a6729-112">Description</span></span>  

 <span data-ttu-id="a6729-113">При превышении одного из основных ограничителей службы создается событие `MessageThrottleExceeded`.</span><span class="sxs-lookup"><span data-stu-id="a6729-113">When one of the main service throttles has been exceeded, the `MessageThrottleExceeded` event is emitted.</span></span> <span data-ttu-id="a6729-114">Если всплеск активности уменьшился и текущее значение ограничителя составляет 70 процентов от текущего предела, то создается это событие.</span><span class="sxs-lookup"><span data-stu-id="a6729-114">When the spike of activity slows and the current value of the throttle is at 70 percent of the current limit then this event is emitted.</span></span> <span data-ttu-id="a6729-115">Обратите внимание, что это событие создается только один раз при замедлении активности.</span><span class="sxs-lookup"><span data-stu-id="a6729-115">Note that this event is only emitted once as the activity is slowing.</span></span> <span data-ttu-id="a6729-116">Если текущее значение находится вблизи отметки 70 процентов (например, 70, 69, 70, 71, 69), то только первое значение 70 процентов приводит к созданию события.</span><span class="sxs-lookup"><span data-stu-id="a6729-116">If the current value hovers at the 70 percent mark, (for example, 70,69,70,71,70,69), only the first occurrence of 70 percent results in an event.</span></span> <span data-ttu-id="a6729-117">После возникновения события все последующие превышения предела регулирования приводят к возникновению события `MessageThrottleExceeded`.</span><span class="sxs-lookup"><span data-stu-id="a6729-117">After this event is emitted, future occurrences of exceeding the throttle's limit result in a `MessageThrottleExceeded` event.</span></span>  
  
## <a name="message"></a><span data-ttu-id="a6729-118">Сообщение</span><span class="sxs-lookup"><span data-stu-id="a6729-118">Message</span></span>  

 <span data-ttu-id="a6729-119">Предел ограничителя %1 из %2 находится на отметке 70%%.</span><span class="sxs-lookup"><span data-stu-id="a6729-119">The '%1' throttle limit of '%2' is at 70%%.</span></span>  
  
## <a name="details"></a><span data-ttu-id="a6729-120">Сведения</span><span class="sxs-lookup"><span data-stu-id="a6729-120">Details</span></span>  
  
|<span data-ttu-id="a6729-121">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="a6729-121">Data Item Name</span></span>|<span data-ttu-id="a6729-122">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="a6729-122">Data Item Type</span></span>|<span data-ttu-id="a6729-123">Описание</span><span class="sxs-lookup"><span data-stu-id="a6729-123">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="a6729-124">Throttle Name</span><span class="sxs-lookup"><span data-stu-id="a6729-124">Throttle Name</span></span>|`xs:string`|<span data-ttu-id="a6729-125">Имя превышенного ограничителя.</span><span class="sxs-lookup"><span data-stu-id="a6729-125">The name of the throttle that has been exceeded.</span></span> <span data-ttu-id="a6729-126">`MaxConcurrentCalls`, `MaxConcurrentInstances` либо `MaxConcurrentSessions`,</span><span class="sxs-lookup"><span data-stu-id="a6729-126">Either `MaxConcurrentCalls`, `MaxConcurrentInstances`, or `MaxConcurrentSessions`,</span></span>|  
|<span data-ttu-id="a6729-127">Ограничение</span><span class="sxs-lookup"><span data-stu-id="a6729-127">Limit</span></span>|`xs:long`|<span data-ttu-id="a6729-128">Заданный в данный момент предел ограничителя.</span><span class="sxs-lookup"><span data-stu-id="a6729-128">The currently configured limit of the throttle.</span></span>|  
|<span data-ttu-id="a6729-129">HostReference</span><span class="sxs-lookup"><span data-stu-id="a6729-129">HostReference</span></span>|`xs:string`|<span data-ttu-id="a6729-130">Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии.</span><span class="sxs-lookup"><span data-stu-id="a6729-130">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="a6729-131">Его формат определяется как "имя веб-сайта виртуальный путь к приложению&#124;виртуальный путь службы&#124;ServiceName".</span><span class="sxs-lookup"><span data-stu-id="a6729-131">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="a6729-132">Пример: "Default Web site/Калкулатораппликатион&#124;/Калкулаторсервице.СВК&#124;CalculatorService".</span><span class="sxs-lookup"><span data-stu-id="a6729-132">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="a6729-133">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="a6729-133">AppDomain</span></span>|`xs:string`|<span data-ttu-id="a6729-134">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="a6729-134">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
