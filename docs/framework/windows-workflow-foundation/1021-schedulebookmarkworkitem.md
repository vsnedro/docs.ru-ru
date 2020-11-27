---
title: 1021 - ScheduleBookmarkWorkItem
ms.date: 03/30/2017
ms.assetid: 2e0da311-b219-4637-9460-90cdafcc4ecd
ms.openlocfilehash: 42ed23654622e29df8ffc210c8d5ba572fa69fd4
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275353"
---
# <a name="1021---schedulebookmarkworkitem"></a><span data-ttu-id="f68b0-102">1021 - ScheduleBookmarkWorkItem</span><span class="sxs-lookup"><span data-stu-id="f68b0-102">1021 - ScheduleBookmarkWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="f68b0-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="f68b0-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f68b0-104">ID</span><span class="sxs-lookup"><span data-stu-id="f68b0-104">ID</span></span>|<span data-ttu-id="f68b0-105">1021</span><span class="sxs-lookup"><span data-stu-id="f68b0-105">1021</span></span>|  
|<span data-ttu-id="f68b0-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="f68b0-106">Keywords</span></span>|<span data-ttu-id="f68b0-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="f68b0-107">WFRuntime</span></span>|  
|<span data-ttu-id="f68b0-108">Level</span><span class="sxs-lookup"><span data-stu-id="f68b0-108">Level</span></span>|<span data-ttu-id="f68b0-109">Подробный</span><span class="sxs-lookup"><span data-stu-id="f68b0-109">Verbose</span></span>|  
|<span data-ttu-id="f68b0-110">Канал</span><span class="sxs-lookup"><span data-stu-id="f68b0-110">Channel</span></span>|<span data-ttu-id="f68b0-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="f68b0-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f68b0-112">Описание</span><span class="sxs-lookup"><span data-stu-id="f68b0-112">Description</span></span>  

 <span data-ttu-id="f68b0-113">Указывает, что элемент BookmarkWorkItem был запланирован.</span><span class="sxs-lookup"><span data-stu-id="f68b0-113">Indicates a BookmarkWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f68b0-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="f68b0-114">Message</span></span>  

 <span data-ttu-id="f68b0-115">Букмаркворкитем был запланирован для действия "%1", DisplayName: "%2", InstanceId: "%3".</span><span class="sxs-lookup"><span data-stu-id="f68b0-115">A BookmarkWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="f68b0-116">BookmarkName: %4, BookmarkScope: %5.</span><span class="sxs-lookup"><span data-stu-id="f68b0-116">BookmarkName: %4, BookmarkScope: %5.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f68b0-117">Сведения</span><span class="sxs-lookup"><span data-stu-id="f68b0-117">Details</span></span>  
  
|<span data-ttu-id="f68b0-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="f68b0-118">Data Item Name</span></span>|<span data-ttu-id="f68b0-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="f68b0-119">Data Item Type</span></span>|<span data-ttu-id="f68b0-120">Описание</span><span class="sxs-lookup"><span data-stu-id="f68b0-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f68b0-121">Действие</span><span class="sxs-lookup"><span data-stu-id="f68b0-121">Activity</span></span>|<span data-ttu-id="f68b0-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="f68b0-122">xs:string</span></span>|<span data-ttu-id="f68b0-123">Имя типа действия.</span><span class="sxs-lookup"><span data-stu-id="f68b0-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="f68b0-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="f68b0-124">DisplayName</span></span>|<span data-ttu-id="f68b0-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="f68b0-125">xs:string</span></span>|<span data-ttu-id="f68b0-126">Отображаемое имя действия.</span><span class="sxs-lookup"><span data-stu-id="f68b0-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="f68b0-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="f68b0-127">InstanceId</span></span>|<span data-ttu-id="f68b0-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="f68b0-128">xs:string</span></span>|<span data-ttu-id="f68b0-129">Идентификатор экземпляра действия.</span><span class="sxs-lookup"><span data-stu-id="f68b0-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="f68b0-130">BookmarkName</span><span class="sxs-lookup"><span data-stu-id="f68b0-130">BookmarkName</span></span>|<span data-ttu-id="f68b0-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="f68b0-131">xs:string</span></span>|<span data-ttu-id="f68b0-132">Имя закладки.</span><span class="sxs-lookup"><span data-stu-id="f68b0-132">The name of the bookmark.</span></span>|  
|<span data-ttu-id="f68b0-133">BookmarkScope</span><span class="sxs-lookup"><span data-stu-id="f68b0-133">BookmarkScope</span></span>|<span data-ttu-id="f68b0-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="f68b0-134">xs:string</span></span>|<span data-ttu-id="f68b0-135">Область закладки.</span><span class="sxs-lookup"><span data-stu-id="f68b0-135">The scope of the bookmark.</span></span>|  
|<span data-ttu-id="f68b0-136">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="f68b0-136">AppDomain</span></span>|<span data-ttu-id="f68b0-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="f68b0-137">xs:string</span></span>|<span data-ttu-id="f68b0-138">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="f68b0-138">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
