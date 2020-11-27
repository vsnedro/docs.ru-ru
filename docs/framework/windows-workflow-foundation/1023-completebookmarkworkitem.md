---
title: 1023 - CompleteBookmarkWorkItem
ms.date: 03/30/2017
ms.assetid: fc5dac57-b3eb-4826-b505-c6d269e4774d
ms.openlocfilehash: cb99fd72165182788955021fbedd2aa657b3a098
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275327"
---
# <a name="1023---completebookmarkworkitem"></a><span data-ttu-id="0565e-102">1023 - CompleteBookmarkWorkItem</span><span class="sxs-lookup"><span data-stu-id="0565e-102">1023 - CompleteBookmarkWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="0565e-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="0565e-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0565e-104">ID</span><span class="sxs-lookup"><span data-stu-id="0565e-104">ID</span></span>|<span data-ttu-id="0565e-105">1023</span><span class="sxs-lookup"><span data-stu-id="0565e-105">1023</span></span>|  
|<span data-ttu-id="0565e-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="0565e-106">Keywords</span></span>|<span data-ttu-id="0565e-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="0565e-107">WFRuntime</span></span>|  
|<span data-ttu-id="0565e-108">Level</span><span class="sxs-lookup"><span data-stu-id="0565e-108">Level</span></span>|<span data-ttu-id="0565e-109">Подробный</span><span class="sxs-lookup"><span data-stu-id="0565e-109">Verbose</span></span>|  
|<span data-ttu-id="0565e-110">Канал</span><span class="sxs-lookup"><span data-stu-id="0565e-110">Channel</span></span>|<span data-ttu-id="0565e-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="0565e-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="0565e-112">Описание</span><span class="sxs-lookup"><span data-stu-id="0565e-112">Description</span></span>  

 <span data-ttu-id="0565e-113">Указывает на завершение BookmarkWorkItem.</span><span class="sxs-lookup"><span data-stu-id="0565e-113">Indicates a BookmarkWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="0565e-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="0565e-114">Message</span></span>  

 <span data-ttu-id="0565e-115">BookmarkWorkItem завершен для действия «%1», DisplayName «%2», InstanceId «%3».</span><span class="sxs-lookup"><span data-stu-id="0565e-115">A BookmarkWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="0565e-116">BookmarkName: %4, BookmarkScope: %5.</span><span class="sxs-lookup"><span data-stu-id="0565e-116">BookmarkName: %4, BookmarkScope: %5.</span></span>  
  
## <a name="details"></a><span data-ttu-id="0565e-117">Сведения</span><span class="sxs-lookup"><span data-stu-id="0565e-117">Details</span></span>  
  
|<span data-ttu-id="0565e-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="0565e-118">Data Item Name</span></span>|<span data-ttu-id="0565e-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="0565e-119">Data Item Type</span></span>|<span data-ttu-id="0565e-120">Описание</span><span class="sxs-lookup"><span data-stu-id="0565e-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="0565e-121">Действие</span><span class="sxs-lookup"><span data-stu-id="0565e-121">Activity</span></span>|<span data-ttu-id="0565e-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="0565e-122">xs:string</span></span>|<span data-ttu-id="0565e-123">Имя типа действия.</span><span class="sxs-lookup"><span data-stu-id="0565e-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="0565e-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="0565e-124">DisplayName</span></span>|<span data-ttu-id="0565e-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="0565e-125">xs:string</span></span>|<span data-ttu-id="0565e-126">Отображаемое имя действия.</span><span class="sxs-lookup"><span data-stu-id="0565e-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="0565e-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="0565e-127">InstanceId</span></span>|<span data-ttu-id="0565e-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="0565e-128">xs:string</span></span>|<span data-ttu-id="0565e-129">Идентификатор экземпляра действия.</span><span class="sxs-lookup"><span data-stu-id="0565e-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="0565e-130">BookmarkName</span><span class="sxs-lookup"><span data-stu-id="0565e-130">BookmarkName</span></span>|<span data-ttu-id="0565e-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="0565e-131">xs:string</span></span>|<span data-ttu-id="0565e-132">Имя закладки.</span><span class="sxs-lookup"><span data-stu-id="0565e-132">The name of the bookmark.</span></span>|  
|<span data-ttu-id="0565e-133">BookmarkScope</span><span class="sxs-lookup"><span data-stu-id="0565e-133">BookmarkScope</span></span>|<span data-ttu-id="0565e-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="0565e-134">xs:string</span></span>|<span data-ttu-id="0565e-135">Область закладки.</span><span class="sxs-lookup"><span data-stu-id="0565e-135">The scope of the bookmark.</span></span>|  
|<span data-ttu-id="0565e-136">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="0565e-136">AppDomain</span></span>|<span data-ttu-id="0565e-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="0565e-137">xs:string</span></span>|<span data-ttu-id="0565e-138">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="0565e-138">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
