---
title: 1016 - CompleteCompletionWorkItem
ms.date: 03/30/2017
ms.assetid: 246929fb-6f14-440a-814b-cd8349350644
ms.openlocfilehash: a192ffe19777ca3e2e9784f6506a0c2929ced000
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275535"
---
# <a name="1016---completecompletionworkitem"></a><span data-ttu-id="2bd5e-102">1016 - CompleteCompletionWorkItem</span><span class="sxs-lookup"><span data-stu-id="2bd5e-102">1016 - CompleteCompletionWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="2bd5e-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="2bd5e-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2bd5e-104">ID</span><span class="sxs-lookup"><span data-stu-id="2bd5e-104">ID</span></span>|<span data-ttu-id="2bd5e-105">1016</span><span class="sxs-lookup"><span data-stu-id="2bd5e-105">1016</span></span>|  
|<span data-ttu-id="2bd5e-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="2bd5e-106">Keywords</span></span>|<span data-ttu-id="2bd5e-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="2bd5e-107">WFRuntime</span></span>|  
|<span data-ttu-id="2bd5e-108">Level</span><span class="sxs-lookup"><span data-stu-id="2bd5e-108">Level</span></span>|<span data-ttu-id="2bd5e-109">Подробный</span><span class="sxs-lookup"><span data-stu-id="2bd5e-109">Verbose</span></span>|  
|<span data-ttu-id="2bd5e-110">Канал</span><span class="sxs-lookup"><span data-stu-id="2bd5e-110">Channel</span></span>|<span data-ttu-id="2bd5e-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="2bd5e-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="2bd5e-112">Описание</span><span class="sxs-lookup"><span data-stu-id="2bd5e-112">Description</span></span>  

 <span data-ttu-id="2bd5e-113">Указывает на завершение CompletionWorkItem.</span><span class="sxs-lookup"><span data-stu-id="2bd5e-113">Indicates a CompletionWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="2bd5e-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="2bd5e-114">Message</span></span>  

 <span data-ttu-id="2bd5e-115">CompletionWorkItem завершен для родительского действия «%1», DisplayName «%2», InstanceId «%3».</span><span class="sxs-lookup"><span data-stu-id="2bd5e-115">A CompletionWorkItem has completed for parent Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="2bd5e-116">Завершено действие «%4», DisplayName «%5», InstanceId «%6».</span><span class="sxs-lookup"><span data-stu-id="2bd5e-116">Completed Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="2bd5e-117">Сведения</span><span class="sxs-lookup"><span data-stu-id="2bd5e-117">Details</span></span>  
  
|<span data-ttu-id="2bd5e-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="2bd5e-118">Data Item Name</span></span>|<span data-ttu-id="2bd5e-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="2bd5e-119">Data Item Type</span></span>|<span data-ttu-id="2bd5e-120">Описание</span><span class="sxs-lookup"><span data-stu-id="2bd5e-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="2bd5e-121">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="2bd5e-121">ParentActivity</span></span>|<span data-ttu-id="2bd5e-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="2bd5e-122">xs:string</span></span>|<span data-ttu-id="2bd5e-123">Имя типа родительского действия.</span><span class="sxs-lookup"><span data-stu-id="2bd5e-123">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="2bd5e-124">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="2bd5e-124">ParentDisplayName</span></span>|<span data-ttu-id="2bd5e-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="2bd5e-125">xs:string</span></span>|<span data-ttu-id="2bd5e-126">Отображаемое имя родительского действия.</span><span class="sxs-lookup"><span data-stu-id="2bd5e-126">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="2bd5e-127">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="2bd5e-127">ParentInstanceId</span></span>|<span data-ttu-id="2bd5e-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="2bd5e-128">xs:string</span></span>|<span data-ttu-id="2bd5e-129">Идентификатор экземпляра родительского действия.</span><span class="sxs-lookup"><span data-stu-id="2bd5e-129">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="2bd5e-130">CompletedActivity</span><span class="sxs-lookup"><span data-stu-id="2bd5e-130">CompletedActivity</span></span>|<span data-ttu-id="2bd5e-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="2bd5e-131">xs:string</span></span>|<span data-ttu-id="2bd5e-132">Имя типа завершенного действия.</span><span class="sxs-lookup"><span data-stu-id="2bd5e-132">The type name of the completed activity.</span></span>|  
|<span data-ttu-id="2bd5e-133">CompletedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="2bd5e-133">CompletedActivityDisplayName</span></span>|<span data-ttu-id="2bd5e-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="2bd5e-134">xs:string</span></span>|<span data-ttu-id="2bd5e-135">Отображаемое имя завершенного действия.</span><span class="sxs-lookup"><span data-stu-id="2bd5e-135">The display name of the completed activity.</span></span>|  
|<span data-ttu-id="2bd5e-136">CompletedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="2bd5e-136">CompletedActivityInstanceId</span></span>|<span data-ttu-id="2bd5e-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="2bd5e-137">xs:string</span></span>|<span data-ttu-id="2bd5e-138">Идентификатор экземпляра завершенного действия.</span><span class="sxs-lookup"><span data-stu-id="2bd5e-138">The instance id of the completed activity.</span></span>|  
|<span data-ttu-id="2bd5e-139">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="2bd5e-139">AppDomain</span></span>|<span data-ttu-id="2bd5e-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="2bd5e-140">xs:string</span></span>|<span data-ttu-id="2bd5e-141">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="2bd5e-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
