---
title: 1013 - CompleteExecuteActivityWorkItem
ms.date: 03/30/2017
ms.assetid: 31fc57b3-ef2f-48f0-a5de-b4e2c5c9ded7
ms.openlocfilehash: 654f961088c371ab53e4a81f40e3c63335efb1a8
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239592"
---
# <a name="1013---completeexecuteactivityworkitem"></a><span data-ttu-id="63a89-102">1013 - CompleteExecuteActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="63a89-102">1013 - CompleteExecuteActivityWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="63a89-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="63a89-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="63a89-104">ID</span><span class="sxs-lookup"><span data-stu-id="63a89-104">ID</span></span>|<span data-ttu-id="63a89-105">1013</span><span class="sxs-lookup"><span data-stu-id="63a89-105">1013</span></span>|  
|<span data-ttu-id="63a89-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="63a89-106">Keywords</span></span>|<span data-ttu-id="63a89-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="63a89-107">WFRuntime</span></span>|  
|<span data-ttu-id="63a89-108">Level</span><span class="sxs-lookup"><span data-stu-id="63a89-108">Level</span></span>|<span data-ttu-id="63a89-109">Подробный</span><span class="sxs-lookup"><span data-stu-id="63a89-109">Verbose</span></span>|  
|<span data-ttu-id="63a89-110">Канал</span><span class="sxs-lookup"><span data-stu-id="63a89-110">Channel</span></span>|<span data-ttu-id="63a89-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="63a89-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="63a89-112">Описание</span><span class="sxs-lookup"><span data-stu-id="63a89-112">Description</span></span>  

 <span data-ttu-id="63a89-113">Указывает, что ExecuteActivityWorkItem завершено</span><span class="sxs-lookup"><span data-stu-id="63a89-113">Indicates an ExecuteActivityWorkItem has completed</span></span>  
  
## <a name="message"></a><span data-ttu-id="63a89-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="63a89-114">Message</span></span>  

 <span data-ttu-id="63a89-115">Завершено выполнение ExecuteActivityWorkItem для действия «%1», DisplayName «%2», InstanceId «%3».</span><span class="sxs-lookup"><span data-stu-id="63a89-115">An ExecuteActivityWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="63a89-116">Сведения</span><span class="sxs-lookup"><span data-stu-id="63a89-116">Details</span></span>  
  
|<span data-ttu-id="63a89-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="63a89-117">Data Item Name</span></span>|<span data-ttu-id="63a89-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="63a89-118">Data Item Type</span></span>|<span data-ttu-id="63a89-119">Описание</span><span class="sxs-lookup"><span data-stu-id="63a89-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="63a89-120">Действие</span><span class="sxs-lookup"><span data-stu-id="63a89-120">Activity</span></span>|<span data-ttu-id="63a89-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="63a89-121">xs:string</span></span>|<span data-ttu-id="63a89-122">Имя типа действия.</span><span class="sxs-lookup"><span data-stu-id="63a89-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="63a89-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="63a89-123">DisplayName</span></span>|<span data-ttu-id="63a89-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="63a89-124">xs:string</span></span>|<span data-ttu-id="63a89-125">Отображаемое имя действия.</span><span class="sxs-lookup"><span data-stu-id="63a89-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="63a89-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="63a89-126">InstanceId</span></span>|<span data-ttu-id="63a89-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="63a89-127">xs:string</span></span>|<span data-ttu-id="63a89-128">Идентификатор экземпляра действия.</span><span class="sxs-lookup"><span data-stu-id="63a89-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="63a89-129">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="63a89-129">AppDomain</span></span>|<span data-ttu-id="63a89-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="63a89-130">xs:string</span></span>|<span data-ttu-id="63a89-131">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="63a89-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
