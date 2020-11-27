---
title: 1015 - StartCompletionWorkItem
ms.date: 03/30/2017
ms.assetid: 96fd1d4e-c5d0-46ad-8a71-4b4b49ac7262
ms.openlocfilehash: c0d8572f192a8faa22327fd671cd9ea49c5054ca
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275548"
---
# <a name="1015---startcompletionworkitem"></a><span data-ttu-id="06cbc-102">1015 - StartCompletionWorkItem</span><span class="sxs-lookup"><span data-stu-id="06cbc-102">1015 - StartCompletionWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="06cbc-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="06cbc-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="06cbc-104">ID</span><span class="sxs-lookup"><span data-stu-id="06cbc-104">ID</span></span>|<span data-ttu-id="06cbc-105">1015</span><span class="sxs-lookup"><span data-stu-id="06cbc-105">1015</span></span>|  
|<span data-ttu-id="06cbc-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="06cbc-106">Keywords</span></span>|<span data-ttu-id="06cbc-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="06cbc-107">WFRuntime</span></span>|  
|<span data-ttu-id="06cbc-108">Level</span><span class="sxs-lookup"><span data-stu-id="06cbc-108">Level</span></span>|<span data-ttu-id="06cbc-109">Подробный</span><span class="sxs-lookup"><span data-stu-id="06cbc-109">Verbose</span></span>|  
|<span data-ttu-id="06cbc-110">Канал</span><span class="sxs-lookup"><span data-stu-id="06cbc-110">Channel</span></span>|<span data-ttu-id="06cbc-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="06cbc-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="06cbc-112">Описание</span><span class="sxs-lookup"><span data-stu-id="06cbc-112">Description</span></span>  

 <span data-ttu-id="06cbc-113">Указывает, что выполнение CompletionWorkItem начинается.</span><span class="sxs-lookup"><span data-stu-id="06cbc-113">Indicates a CompletionWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="06cbc-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="06cbc-114">Message</span></span>  

 <span data-ttu-id="06cbc-115">Начато выполнение CompletionWorkItem для родительского действия «%1», DisplayName «%2», InstanceId «%3».</span><span class="sxs-lookup"><span data-stu-id="06cbc-115">Starting execution of a CompletionWorkItem for parent Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="06cbc-116">Завершено действие «%4», DisplayName «%5», InstanceId «%6».</span><span class="sxs-lookup"><span data-stu-id="06cbc-116">Completed Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="06cbc-117">Сведения</span><span class="sxs-lookup"><span data-stu-id="06cbc-117">Details</span></span>  
  
|<span data-ttu-id="06cbc-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="06cbc-118">Data Item Name</span></span>|<span data-ttu-id="06cbc-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="06cbc-119">Data Item Type</span></span>|<span data-ttu-id="06cbc-120">Описание</span><span class="sxs-lookup"><span data-stu-id="06cbc-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="06cbc-121">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="06cbc-121">ParentActivity</span></span>|<span data-ttu-id="06cbc-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="06cbc-122">xs:string</span></span>|<span data-ttu-id="06cbc-123">Имя типа родительского действия.</span><span class="sxs-lookup"><span data-stu-id="06cbc-123">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="06cbc-124">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="06cbc-124">ParentDisplayName</span></span>|<span data-ttu-id="06cbc-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="06cbc-125">xs:string</span></span>|<span data-ttu-id="06cbc-126">Отображаемое имя родительского действия.</span><span class="sxs-lookup"><span data-stu-id="06cbc-126">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="06cbc-127">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="06cbc-127">ParentInstanceId</span></span>|<span data-ttu-id="06cbc-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="06cbc-128">xs:string</span></span>|<span data-ttu-id="06cbc-129">Идентификатор экземпляра родительского действия.</span><span class="sxs-lookup"><span data-stu-id="06cbc-129">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="06cbc-130">CompletedActivity</span><span class="sxs-lookup"><span data-stu-id="06cbc-130">CompletedActivity</span></span>|<span data-ttu-id="06cbc-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="06cbc-131">xs:string</span></span>|<span data-ttu-id="06cbc-132">Имя типа завершенного действия.</span><span class="sxs-lookup"><span data-stu-id="06cbc-132">The type name of the completed activity.</span></span>|  
|<span data-ttu-id="06cbc-133">CompletedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="06cbc-133">CompletedActivityDisplayName</span></span>|<span data-ttu-id="06cbc-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="06cbc-134">xs:string</span></span>|<span data-ttu-id="06cbc-135">Отображаемое имя завершенного действия.</span><span class="sxs-lookup"><span data-stu-id="06cbc-135">The display name of the completed activity.</span></span>|  
|<span data-ttu-id="06cbc-136">CompletedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="06cbc-136">CompletedActivityInstanceId</span></span>|<span data-ttu-id="06cbc-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="06cbc-137">xs:string</span></span>|<span data-ttu-id="06cbc-138">Идентификатор экземпляра завершенного действия.</span><span class="sxs-lookup"><span data-stu-id="06cbc-138">The instance id of the completed activity.</span></span>|  
|<span data-ttu-id="06cbc-139">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="06cbc-139">AppDomain</span></span>|<span data-ttu-id="06cbc-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="06cbc-140">xs:string</span></span>|<span data-ttu-id="06cbc-141">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="06cbc-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
