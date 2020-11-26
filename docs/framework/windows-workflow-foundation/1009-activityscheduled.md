---
title: 1009 - ActivityScheduled
ms.date: 03/30/2017
ms.assetid: 307e38b6-d47e-47a4-9708-e74d8314b1a1
ms.openlocfilehash: 812531d4206dfee20f183b9461330e71263b0bf8
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239774"
---
# <a name="1009---activityscheduled"></a><span data-ttu-id="02a64-102">1009 - ActivityScheduled</span><span class="sxs-lookup"><span data-stu-id="02a64-102">1009 - ActivityScheduled</span></span>

## <a name="properties"></a><span data-ttu-id="02a64-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="02a64-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="02a64-104">ID</span><span class="sxs-lookup"><span data-stu-id="02a64-104">ID</span></span>|<span data-ttu-id="02a64-105">1009</span><span class="sxs-lookup"><span data-stu-id="02a64-105">1009</span></span>|  
|<span data-ttu-id="02a64-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="02a64-106">Keywords</span></span>|<span data-ttu-id="02a64-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="02a64-107">WFRuntime</span></span>|  
|<span data-ttu-id="02a64-108">Level</span><span class="sxs-lookup"><span data-stu-id="02a64-108">Level</span></span>|<span data-ttu-id="02a64-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="02a64-109">Information</span></span>|  
|<span data-ttu-id="02a64-110">Канал</span><span class="sxs-lookup"><span data-stu-id="02a64-110">Channel</span></span>|<span data-ttu-id="02a64-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="02a64-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="02a64-112">Описание</span><span class="sxs-lookup"><span data-stu-id="02a64-112">Description</span></span>  

 <span data-ttu-id="02a64-113">Указывает, что действие запланировано для выполнения.</span><span class="sxs-lookup"><span data-stu-id="02a64-113">Indicates an activity is being scheduled for execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="02a64-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="02a64-114">Message</span></span>  

 <span data-ttu-id="02a64-115">Родительское действие «%1» (отображаемое имя «%2», ИД экземпляра «%3») запланировало дочернее действие «%4» (отображаемое имя «%5», ИД экземпляра «%6»).</span><span class="sxs-lookup"><span data-stu-id="02a64-115">Parent Activity '%1', DisplayName: '%2', InstanceId: '%3' scheduled child Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="02a64-116">Сведения</span><span class="sxs-lookup"><span data-stu-id="02a64-116">Details</span></span>  
  
|<span data-ttu-id="02a64-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="02a64-117">Data Item Name</span></span>|<span data-ttu-id="02a64-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="02a64-118">Data Item Type</span></span>|<span data-ttu-id="02a64-119">Описание</span><span class="sxs-lookup"><span data-stu-id="02a64-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="02a64-120">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="02a64-120">ParentActivity</span></span>|<span data-ttu-id="02a64-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="02a64-121">xs:string</span></span>|<span data-ttu-id="02a64-122">Имя типа родительского действия.</span><span class="sxs-lookup"><span data-stu-id="02a64-122">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="02a64-123">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="02a64-123">ParentDisplayName</span></span>|<span data-ttu-id="02a64-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="02a64-124">xs:string</span></span>|<span data-ttu-id="02a64-125">Отображаемое имя родительского действия.</span><span class="sxs-lookup"><span data-stu-id="02a64-125">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="02a64-126">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="02a64-126">ParentInstanceId</span></span>|<span data-ttu-id="02a64-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="02a64-127">xs:string</span></span>|<span data-ttu-id="02a64-128">Идентификатор экземпляра родительского действия.</span><span class="sxs-lookup"><span data-stu-id="02a64-128">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="02a64-129">ChildActivity</span><span class="sxs-lookup"><span data-stu-id="02a64-129">ChildActivity</span></span>|<span data-ttu-id="02a64-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="02a64-130">xs:string</span></span>|<span data-ttu-id="02a64-131">Имя типа запланированного дочернего действия.</span><span class="sxs-lookup"><span data-stu-id="02a64-131">The type name of the scheduled child activity.</span></span>|  
|<span data-ttu-id="02a64-132">ChildDisplayName</span><span class="sxs-lookup"><span data-stu-id="02a64-132">ChildDisplayName</span></span>|<span data-ttu-id="02a64-133">xs:string</span><span class="sxs-lookup"><span data-stu-id="02a64-133">xs:string</span></span>|<span data-ttu-id="02a64-134">Отображаемое имя запланированного дочернего действия.</span><span class="sxs-lookup"><span data-stu-id="02a64-134">The display name of the scheduled child activity.</span></span>|  
|<span data-ttu-id="02a64-135">ChildInstanceId</span><span class="sxs-lookup"><span data-stu-id="02a64-135">ChildInstanceId</span></span>|<span data-ttu-id="02a64-136">xs:string</span><span class="sxs-lookup"><span data-stu-id="02a64-136">xs:string</span></span>|<span data-ttu-id="02a64-137">Идентификатор экземпляра запланированного дочернего действия.</span><span class="sxs-lookup"><span data-stu-id="02a64-137">The instance id of the scheduled child activity.</span></span>|  
|<span data-ttu-id="02a64-138">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="02a64-138">AppDomain</span></span>|<span data-ttu-id="02a64-139">xs:string</span><span class="sxs-lookup"><span data-stu-id="02a64-139">xs:string</span></span>|<span data-ttu-id="02a64-140">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="02a64-140">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
