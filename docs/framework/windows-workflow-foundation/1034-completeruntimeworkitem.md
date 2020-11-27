---
title: 1034 - CompleteRuntimeWorkItem
ms.date: 03/30/2017
ms.assetid: 45620011-8b04-4f87-ab5a-65b24145e17d
ms.openlocfilehash: 837adc9e143060284f2373a049bc9ad9c8cee336
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294291"
---
# <a name="1034---completeruntimeworkitem"></a><span data-ttu-id="d8291-102">1034 - CompleteRuntimeWorkItem</span><span class="sxs-lookup"><span data-stu-id="d8291-102">1034 - CompleteRuntimeWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="d8291-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="d8291-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d8291-104">ID</span><span class="sxs-lookup"><span data-stu-id="d8291-104">ID</span></span>|<span data-ttu-id="d8291-105">1034</span><span class="sxs-lookup"><span data-stu-id="d8291-105">1034</span></span>|  
|<span data-ttu-id="d8291-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="d8291-106">Keywords</span></span>|<span data-ttu-id="d8291-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="d8291-107">WFRuntime</span></span>|  
|<span data-ttu-id="d8291-108">Level</span><span class="sxs-lookup"><span data-stu-id="d8291-108">Level</span></span>|<span data-ttu-id="d8291-109">Подробный</span><span class="sxs-lookup"><span data-stu-id="d8291-109">Verbose</span></span>|  
|<span data-ttu-id="d8291-110">Канал</span><span class="sxs-lookup"><span data-stu-id="d8291-110">Channel</span></span>|<span data-ttu-id="d8291-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="d8291-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="d8291-112">Описание</span><span class="sxs-lookup"><span data-stu-id="d8291-112">Description</span></span>  

 <span data-ttu-id="d8291-113">Указывает на завершение RuntimeWorkItem.</span><span class="sxs-lookup"><span data-stu-id="d8291-113">Indicates a RuntimeWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="d8291-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="d8291-114">Message</span></span>  

 <span data-ttu-id="d8291-115">Рабочий элемент среды выполнения завершен для действия «%1», DisplayName «%2», InstanceId «%3».</span><span class="sxs-lookup"><span data-stu-id="d8291-115">A runtime work item has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="d8291-116">Сведения</span><span class="sxs-lookup"><span data-stu-id="d8291-116">Details</span></span>  
  
|<span data-ttu-id="d8291-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="d8291-117">Data Item Name</span></span>|<span data-ttu-id="d8291-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="d8291-118">Data Item Type</span></span>|<span data-ttu-id="d8291-119">Описание</span><span class="sxs-lookup"><span data-stu-id="d8291-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="d8291-120">Действие</span><span class="sxs-lookup"><span data-stu-id="d8291-120">Activity</span></span>|<span data-ttu-id="d8291-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="d8291-121">xs:string</span></span>|<span data-ttu-id="d8291-122">Имя типа действия.</span><span class="sxs-lookup"><span data-stu-id="d8291-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="d8291-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="d8291-123">DisplayName</span></span>|<span data-ttu-id="d8291-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="d8291-124">xs:string</span></span>|<span data-ttu-id="d8291-125">Отображаемое имя действия.</span><span class="sxs-lookup"><span data-stu-id="d8291-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="d8291-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="d8291-126">InstanceId</span></span>|<span data-ttu-id="d8291-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="d8291-127">xs:string</span></span>|<span data-ttu-id="d8291-128">Идентификатор экземпляра действия.</span><span class="sxs-lookup"><span data-stu-id="d8291-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="d8291-129">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="d8291-129">AppDomain</span></span>|<span data-ttu-id="d8291-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="d8291-130">xs:string</span></span>|<span data-ttu-id="d8291-131">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="d8291-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
