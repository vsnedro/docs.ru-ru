---
title: 1017 - ScheduleCancelActivityWorkItem
ms.date: 03/30/2017
ms.assetid: 864546ab-d65c-4989-8fcb-537ba03a3cdd
ms.openlocfilehash: 6aed9773aa45251075520a0f955e9d71234f1357
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275623"
---
# <a name="1017---schedulecancelactivityworkitem"></a><span data-ttu-id="5dd70-102">1017 - ScheduleCancelActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="5dd70-102">1017 - ScheduleCancelActivityWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="5dd70-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="5dd70-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5dd70-104">ID</span><span class="sxs-lookup"><span data-stu-id="5dd70-104">ID</span></span>|<span data-ttu-id="5dd70-105">1017</span><span class="sxs-lookup"><span data-stu-id="5dd70-105">1017</span></span>|  
|<span data-ttu-id="5dd70-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="5dd70-106">Keywords</span></span>|<span data-ttu-id="5dd70-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="5dd70-107">WFRuntime</span></span>|  
|<span data-ttu-id="5dd70-108">Level</span><span class="sxs-lookup"><span data-stu-id="5dd70-108">Level</span></span>|<span data-ttu-id="5dd70-109">Подробный</span><span class="sxs-lookup"><span data-stu-id="5dd70-109">Verbose</span></span>|  
|<span data-ttu-id="5dd70-110">Канал</span><span class="sxs-lookup"><span data-stu-id="5dd70-110">Channel</span></span>|<span data-ttu-id="5dd70-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="5dd70-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="5dd70-112">Описание</span><span class="sxs-lookup"><span data-stu-id="5dd70-112">Description</span></span>  

 <span data-ttu-id="5dd70-113">Указывает, что элемент CancelActivityWorkItem был запланирован.</span><span class="sxs-lookup"><span data-stu-id="5dd70-113">Indicates a CancelActivityWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="5dd70-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="5dd70-114">Message</span></span>  

 <span data-ttu-id="5dd70-115">CancelActivityWorkItem запланирован для действия «%1», DisplayName «%2», InstanceId «%3».</span><span class="sxs-lookup"><span data-stu-id="5dd70-115">A CancelActivityWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="5dd70-116">Сведения</span><span class="sxs-lookup"><span data-stu-id="5dd70-116">Details</span></span>  
  
|<span data-ttu-id="5dd70-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="5dd70-117">Data Item Name</span></span>|<span data-ttu-id="5dd70-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="5dd70-118">Data Item Type</span></span>|<span data-ttu-id="5dd70-119">Описание</span><span class="sxs-lookup"><span data-stu-id="5dd70-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="5dd70-120">Действие</span><span class="sxs-lookup"><span data-stu-id="5dd70-120">Activity</span></span>|<span data-ttu-id="5dd70-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="5dd70-121">xs:string</span></span>|<span data-ttu-id="5dd70-122">Имя типа действия.</span><span class="sxs-lookup"><span data-stu-id="5dd70-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="5dd70-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="5dd70-123">DisplayName</span></span>|<span data-ttu-id="5dd70-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="5dd70-124">xs:string</span></span>|<span data-ttu-id="5dd70-125">Отображаемое имя действия.</span><span class="sxs-lookup"><span data-stu-id="5dd70-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="5dd70-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="5dd70-126">InstanceId</span></span>|<span data-ttu-id="5dd70-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="5dd70-127">xs:string</span></span>|<span data-ttu-id="5dd70-128">Идентификатор экземпляра действия.</span><span class="sxs-lookup"><span data-stu-id="5dd70-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="5dd70-129">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="5dd70-129">AppDomain</span></span>|<span data-ttu-id="5dd70-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="5dd70-130">xs:string</span></span>|<span data-ttu-id="5dd70-131">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="5dd70-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
