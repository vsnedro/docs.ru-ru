---
title: 1020 - CreateBookmark
ms.date: 03/30/2017
ms.assetid: 4bee948d-816f-4803-85cc-3883b5e23d10
ms.openlocfilehash: 8c9c20fd4fb74f80779c1d2ef8f29ac3d44050d9
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275379"
---
# <a name="1020---createbookmark"></a><span data-ttu-id="2f448-102">1020 - CreateBookmark</span><span class="sxs-lookup"><span data-stu-id="2f448-102">1020 - CreateBookmark</span></span>

## <a name="properties"></a><span data-ttu-id="2f448-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="2f448-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2f448-104">ID</span><span class="sxs-lookup"><span data-stu-id="2f448-104">ID</span></span>|<span data-ttu-id="2f448-105">1020</span><span class="sxs-lookup"><span data-stu-id="2f448-105">1020</span></span>|  
|<span data-ttu-id="2f448-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="2f448-106">Keywords</span></span>|<span data-ttu-id="2f448-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="2f448-107">WFRuntime</span></span>|  
|<span data-ttu-id="2f448-108">Level</span><span class="sxs-lookup"><span data-stu-id="2f448-108">Level</span></span>|<span data-ttu-id="2f448-109">Подробный</span><span class="sxs-lookup"><span data-stu-id="2f448-109">Verbose</span></span>|  
|<span data-ttu-id="2f448-110">Канал</span><span class="sxs-lookup"><span data-stu-id="2f448-110">Channel</span></span>|<span data-ttu-id="2f448-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="2f448-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="2f448-112">Описание</span><span class="sxs-lookup"><span data-stu-id="2f448-112">Description</span></span>  

 <span data-ttu-id="2f448-113">Указывает, что для действия создана закладка.</span><span class="sxs-lookup"><span data-stu-id="2f448-113">Indicates a bookmark has been created for an activity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="2f448-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="2f448-114">Message</span></span>  

 <span data-ttu-id="2f448-115">Создана закладка для действия "%1", DisplayName: "%2", InstanceId: "%3".</span><span class="sxs-lookup"><span data-stu-id="2f448-115">A Bookmark has been created for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="2f448-116">BookmarkName: %4, BookmarkScope: %5.</span><span class="sxs-lookup"><span data-stu-id="2f448-116">BookmarkName: %4, BookmarkScope: %5.</span></span>  
  
## <a name="details"></a><span data-ttu-id="2f448-117">Сведения</span><span class="sxs-lookup"><span data-stu-id="2f448-117">Details</span></span>  
  
|<span data-ttu-id="2f448-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="2f448-118">Data Item Name</span></span>|<span data-ttu-id="2f448-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="2f448-119">Data Item Type</span></span>|<span data-ttu-id="2f448-120">Описание</span><span class="sxs-lookup"><span data-stu-id="2f448-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="2f448-121">Действие</span><span class="sxs-lookup"><span data-stu-id="2f448-121">Activity</span></span>|<span data-ttu-id="2f448-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="2f448-122">xs:string</span></span>|<span data-ttu-id="2f448-123">Имя типа действия.</span><span class="sxs-lookup"><span data-stu-id="2f448-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="2f448-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="2f448-124">DisplayName</span></span>|<span data-ttu-id="2f448-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="2f448-125">xs:string</span></span>|<span data-ttu-id="2f448-126">Отображаемое имя действия.</span><span class="sxs-lookup"><span data-stu-id="2f448-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="2f448-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="2f448-127">InstanceId</span></span>|<span data-ttu-id="2f448-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="2f448-128">xs:string</span></span>|<span data-ttu-id="2f448-129">Идентификатор экземпляра действия.</span><span class="sxs-lookup"><span data-stu-id="2f448-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="2f448-130">BookmarkName</span><span class="sxs-lookup"><span data-stu-id="2f448-130">BookmarkName</span></span>|<span data-ttu-id="2f448-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="2f448-131">xs:string</span></span>|<span data-ttu-id="2f448-132">Имя закладки.</span><span class="sxs-lookup"><span data-stu-id="2f448-132">The name of the bookmark.</span></span>|  
|<span data-ttu-id="2f448-133">BookmarkScope</span><span class="sxs-lookup"><span data-stu-id="2f448-133">BookmarkScope</span></span>|<span data-ttu-id="2f448-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="2f448-134">xs:string</span></span>|<span data-ttu-id="2f448-135">Область закладки.</span><span class="sxs-lookup"><span data-stu-id="2f448-135">The scope of the bookmark.</span></span>|  
|<span data-ttu-id="2f448-136">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="2f448-136">AppDomain</span></span>|<span data-ttu-id="2f448-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="2f448-137">xs:string</span></span>|<span data-ttu-id="2f448-138">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="2f448-138">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
