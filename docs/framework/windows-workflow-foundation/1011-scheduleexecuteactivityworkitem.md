---
title: 1011 - ScheduleExecuteActivityWorkItem
ms.date: 03/30/2017
ms.assetid: e503ae46-ad6b-4fcb-8c0e-146d59a8eff1
ms.openlocfilehash: dc209fc41dc6b076dfb897880f753be51f7fb0ce
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239696"
---
# <a name="1011---scheduleexecuteactivityworkitem"></a><span data-ttu-id="8b6bd-102">1011 - ScheduleExecuteActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="8b6bd-102">1011 - ScheduleExecuteActivityWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="8b6bd-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="8b6bd-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8b6bd-104">ID</span><span class="sxs-lookup"><span data-stu-id="8b6bd-104">ID</span></span>|<span data-ttu-id="8b6bd-105">1011</span><span class="sxs-lookup"><span data-stu-id="8b6bd-105">1011</span></span>|  
|<span data-ttu-id="8b6bd-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="8b6bd-106">Keywords</span></span>|<span data-ttu-id="8b6bd-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="8b6bd-107">WFRuntime</span></span>|  
|<span data-ttu-id="8b6bd-108">Level</span><span class="sxs-lookup"><span data-stu-id="8b6bd-108">Level</span></span>|<span data-ttu-id="8b6bd-109">Подробный</span><span class="sxs-lookup"><span data-stu-id="8b6bd-109">Verbose</span></span>|  
|<span data-ttu-id="8b6bd-110">Канал</span><span class="sxs-lookup"><span data-stu-id="8b6bd-110">Channel</span></span>|<span data-ttu-id="8b6bd-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="8b6bd-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="8b6bd-112">Описание</span><span class="sxs-lookup"><span data-stu-id="8b6bd-112">Description</span></span>  

 <span data-ttu-id="8b6bd-113">Указывает, что элемент ExecuteActivityWorkItem запланирован.</span><span class="sxs-lookup"><span data-stu-id="8b6bd-113">Indicates an ExecuteActivityWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="8b6bd-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="8b6bd-114">Message</span></span>  

 <span data-ttu-id="8b6bd-115">ExecuteActivityWorkItem запланирован для действия «%1», DisplayName «%2», InstanceId «%3».</span><span class="sxs-lookup"><span data-stu-id="8b6bd-115">An ExecuteActivityWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="8b6bd-116">Сведения</span><span class="sxs-lookup"><span data-stu-id="8b6bd-116">Details</span></span>  
  
|<span data-ttu-id="8b6bd-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="8b6bd-117">Data Item Name</span></span>|<span data-ttu-id="8b6bd-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="8b6bd-118">Data Item Type</span></span>|<span data-ttu-id="8b6bd-119">Описание</span><span class="sxs-lookup"><span data-stu-id="8b6bd-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="8b6bd-120">Действие</span><span class="sxs-lookup"><span data-stu-id="8b6bd-120">Activity</span></span>|<span data-ttu-id="8b6bd-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="8b6bd-121">xs:string</span></span>|<span data-ttu-id="8b6bd-122">Имя типа действия.</span><span class="sxs-lookup"><span data-stu-id="8b6bd-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="8b6bd-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="8b6bd-123">DisplayName</span></span>|<span data-ttu-id="8b6bd-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="8b6bd-124">xs:string</span></span>|<span data-ttu-id="8b6bd-125">Отображаемое имя действия.</span><span class="sxs-lookup"><span data-stu-id="8b6bd-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="8b6bd-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="8b6bd-126">InstanceId</span></span>|<span data-ttu-id="8b6bd-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="8b6bd-127">xs:string</span></span>|<span data-ttu-id="8b6bd-128">Идентификатор экземпляра действия.</span><span class="sxs-lookup"><span data-stu-id="8b6bd-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="8b6bd-129">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="8b6bd-129">AppDomain</span></span>|<span data-ttu-id="8b6bd-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="8b6bd-130">xs:string</span></span>|<span data-ttu-id="8b6bd-131">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="8b6bd-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
