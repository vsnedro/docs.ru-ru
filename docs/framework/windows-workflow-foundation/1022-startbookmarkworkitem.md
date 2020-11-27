---
title: 1022 - StartBookmarkWorkItem
ms.date: 03/30/2017
ms.assetid: 4415fbdb-0329-4019-803f-aea66e75f3da
ms.openlocfilehash: ca1f4244fb1a5144cb2d86eaacb9b31137d317c2
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275340"
---
# <a name="1022---startbookmarkworkitem"></a><span data-ttu-id="04bcc-102">1022 - StartBookmarkWorkItem</span><span class="sxs-lookup"><span data-stu-id="04bcc-102">1022 - StartBookmarkWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="04bcc-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="04bcc-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="04bcc-104">ID</span><span class="sxs-lookup"><span data-stu-id="04bcc-104">ID</span></span>|<span data-ttu-id="04bcc-105">1022</span><span class="sxs-lookup"><span data-stu-id="04bcc-105">1022</span></span>|  
|<span data-ttu-id="04bcc-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="04bcc-106">Keywords</span></span>|<span data-ttu-id="04bcc-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="04bcc-107">WFRuntime</span></span>|  
|<span data-ttu-id="04bcc-108">Level</span><span class="sxs-lookup"><span data-stu-id="04bcc-108">Level</span></span>|<span data-ttu-id="04bcc-109">Подробный</span><span class="sxs-lookup"><span data-stu-id="04bcc-109">Verbose</span></span>|  
|<span data-ttu-id="04bcc-110">Канал</span><span class="sxs-lookup"><span data-stu-id="04bcc-110">Channel</span></span>|<span data-ttu-id="04bcc-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="04bcc-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="04bcc-112">Описание</span><span class="sxs-lookup"><span data-stu-id="04bcc-112">Description</span></span>  

 <span data-ttu-id="04bcc-113">Указывает, что начинается выполнение BookmarkWorkItem.</span><span class="sxs-lookup"><span data-stu-id="04bcc-113">Indicates a BookmarkWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="04bcc-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="04bcc-114">Message</span></span>  

 <span data-ttu-id="04bcc-115">Запуск выполнения Букмаркворкитем для действия "%1", DisplayName: "%2", InstanceId: "%3".</span><span class="sxs-lookup"><span data-stu-id="04bcc-115">Starting execution of a BookmarkWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="04bcc-116">BookmarkName: %4, BookmarkScope: %5.</span><span class="sxs-lookup"><span data-stu-id="04bcc-116">BookmarkName: %4, BookmarkScope: %5.</span></span>  
  
## <a name="details"></a><span data-ttu-id="04bcc-117">Сведения</span><span class="sxs-lookup"><span data-stu-id="04bcc-117">Details</span></span>  
  
|<span data-ttu-id="04bcc-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="04bcc-118">Data Item Name</span></span>|<span data-ttu-id="04bcc-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="04bcc-119">Data Item Type</span></span>|<span data-ttu-id="04bcc-120">Описание</span><span class="sxs-lookup"><span data-stu-id="04bcc-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="04bcc-121">Действие</span><span class="sxs-lookup"><span data-stu-id="04bcc-121">Activity</span></span>|<span data-ttu-id="04bcc-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="04bcc-122">xs:string</span></span>|<span data-ttu-id="04bcc-123">Имя типа действия.</span><span class="sxs-lookup"><span data-stu-id="04bcc-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="04bcc-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="04bcc-124">DisplayName</span></span>|<span data-ttu-id="04bcc-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="04bcc-125">xs:string</span></span>|<span data-ttu-id="04bcc-126">Отображаемое имя действия.</span><span class="sxs-lookup"><span data-stu-id="04bcc-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="04bcc-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="04bcc-127">InstanceId</span></span>|<span data-ttu-id="04bcc-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="04bcc-128">xs:string</span></span>|<span data-ttu-id="04bcc-129">Идентификатор экземпляра действия.</span><span class="sxs-lookup"><span data-stu-id="04bcc-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="04bcc-130">BookmarkName</span><span class="sxs-lookup"><span data-stu-id="04bcc-130">BookmarkName</span></span>|<span data-ttu-id="04bcc-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="04bcc-131">xs:string</span></span>|<span data-ttu-id="04bcc-132">Имя закладки.</span><span class="sxs-lookup"><span data-stu-id="04bcc-132">The name of the bookmark.</span></span>|  
|<span data-ttu-id="04bcc-133">BookmarkScope</span><span class="sxs-lookup"><span data-stu-id="04bcc-133">BookmarkScope</span></span>|<span data-ttu-id="04bcc-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="04bcc-134">xs:string</span></span>|<span data-ttu-id="04bcc-135">Область закладки.</span><span class="sxs-lookup"><span data-stu-id="04bcc-135">The scope of the bookmark.</span></span>|  
|<span data-ttu-id="04bcc-136">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="04bcc-136">AppDomain</span></span>|<span data-ttu-id="04bcc-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="04bcc-137">xs:string</span></span>|<span data-ttu-id="04bcc-138">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="04bcc-138">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
