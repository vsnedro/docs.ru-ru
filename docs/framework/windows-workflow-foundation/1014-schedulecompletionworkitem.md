---
title: 1014 - ScheduleCompletionWorkItem
ms.date: 03/30/2017
ms.assetid: 84203735-478d-42d8-a320-c175dbddcb38
ms.openlocfilehash: 7fd93683851c5a8c4ab253272c3f2129b3f0bb49
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275561"
---
# <a name="1014---schedulecompletionworkitem"></a><span data-ttu-id="5fec3-102">1014 - ScheduleCompletionWorkItem</span><span class="sxs-lookup"><span data-stu-id="5fec3-102">1014 - ScheduleCompletionWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="5fec3-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="5fec3-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5fec3-104">ID</span><span class="sxs-lookup"><span data-stu-id="5fec3-104">ID</span></span>|<span data-ttu-id="5fec3-105">1014</span><span class="sxs-lookup"><span data-stu-id="5fec3-105">1014</span></span>|  
|<span data-ttu-id="5fec3-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="5fec3-106">Keywords</span></span>|<span data-ttu-id="5fec3-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="5fec3-107">WFRuntime</span></span>|  
|<span data-ttu-id="5fec3-108">Level</span><span class="sxs-lookup"><span data-stu-id="5fec3-108">Level</span></span>|<span data-ttu-id="5fec3-109">Подробный</span><span class="sxs-lookup"><span data-stu-id="5fec3-109">Verbose</span></span>|  
|<span data-ttu-id="5fec3-110">Канал</span><span class="sxs-lookup"><span data-stu-id="5fec3-110">Channel</span></span>|<span data-ttu-id="5fec3-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="5fec3-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="5fec3-112">Описание</span><span class="sxs-lookup"><span data-stu-id="5fec3-112">Description</span></span>  

 <span data-ttu-id="5fec3-113">Указывает, что элемент CompletionWorkItem был запланирован.</span><span class="sxs-lookup"><span data-stu-id="5fec3-113">Indicates a CompletionWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="5fec3-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="5fec3-114">Message</span></span>  

 <span data-ttu-id="5fec3-115">Комплетионворкитем был запланирован для родительского действия "%1", DisplayName: "%2", InstanceId: "%3".</span><span class="sxs-lookup"><span data-stu-id="5fec3-115">A CompletionWorkItem has been scheduled for parent Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="5fec3-116">Завершено действие «%4», DisplayName «%5», InstanceId «%6».</span><span class="sxs-lookup"><span data-stu-id="5fec3-116">Completed Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="5fec3-117">Сведения</span><span class="sxs-lookup"><span data-stu-id="5fec3-117">Details</span></span>  
  
|<span data-ttu-id="5fec3-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="5fec3-118">Data Item Name</span></span>|<span data-ttu-id="5fec3-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="5fec3-119">Data Item Type</span></span>|<span data-ttu-id="5fec3-120">Описание</span><span class="sxs-lookup"><span data-stu-id="5fec3-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="5fec3-121">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="5fec3-121">ParentActivity</span></span>|<span data-ttu-id="5fec3-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="5fec3-122">xs:string</span></span>|<span data-ttu-id="5fec3-123">Имя типа родительского действия.</span><span class="sxs-lookup"><span data-stu-id="5fec3-123">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="5fec3-124">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="5fec3-124">ParentDisplayName</span></span>|<span data-ttu-id="5fec3-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="5fec3-125">xs:string</span></span>|<span data-ttu-id="5fec3-126">Отображаемое имя родительского действия.</span><span class="sxs-lookup"><span data-stu-id="5fec3-126">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="5fec3-127">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="5fec3-127">ParentInstanceId</span></span>|<span data-ttu-id="5fec3-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="5fec3-128">xs:string</span></span>|<span data-ttu-id="5fec3-129">Идентификатор экземпляра родительского действия.</span><span class="sxs-lookup"><span data-stu-id="5fec3-129">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="5fec3-130">CompletedActivity</span><span class="sxs-lookup"><span data-stu-id="5fec3-130">CompletedActivity</span></span>|<span data-ttu-id="5fec3-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="5fec3-131">xs:string</span></span>|<span data-ttu-id="5fec3-132">Имя типа завершенного действия.</span><span class="sxs-lookup"><span data-stu-id="5fec3-132">The type name of the completed activity.</span></span>|  
|<span data-ttu-id="5fec3-133">CompletedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="5fec3-133">CompletedActivityDisplayName</span></span>|<span data-ttu-id="5fec3-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="5fec3-134">xs:string</span></span>|<span data-ttu-id="5fec3-135">Отображаемое имя завершенного действия.</span><span class="sxs-lookup"><span data-stu-id="5fec3-135">The display name of the completed activity.</span></span>|  
|<span data-ttu-id="5fec3-136">CompletedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="5fec3-136">CompletedActivityInstanceId</span></span>|<span data-ttu-id="5fec3-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="5fec3-137">xs:string</span></span>|<span data-ttu-id="5fec3-138">Идентификатор экземпляра завершенного действия.</span><span class="sxs-lookup"><span data-stu-id="5fec3-138">The instance id of the completed activity.</span></span>|  
|<span data-ttu-id="5fec3-139">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="5fec3-139">AppDomain</span></span>|<span data-ttu-id="5fec3-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="5fec3-140">xs:string</span></span>|<span data-ttu-id="5fec3-141">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="5fec3-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
