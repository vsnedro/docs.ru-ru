---
title: 1019 - CompleteCancelActivityWorkItem
ms.date: 03/30/2017
ms.assetid: 75a4a1ab-e5a3-4f4e-88e4-d19806e671d7
ms.openlocfilehash: 903b497fb3f244fd40c6888829ef71dddd455251
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275483"
---
# <a name="1019---completecancelactivityworkitem"></a><span data-ttu-id="9d9ec-102">1019 - CompleteCancelActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="9d9ec-102">1019 - CompleteCancelActivityWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="9d9ec-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="9d9ec-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9d9ec-104">ID</span><span class="sxs-lookup"><span data-stu-id="9d9ec-104">ID</span></span>|<span data-ttu-id="9d9ec-105">1019</span><span class="sxs-lookup"><span data-stu-id="9d9ec-105">1019</span></span>|  
|<span data-ttu-id="9d9ec-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="9d9ec-106">Keywords</span></span>|<span data-ttu-id="9d9ec-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="9d9ec-107">WFRuntime</span></span>|  
|<span data-ttu-id="9d9ec-108">Level</span><span class="sxs-lookup"><span data-stu-id="9d9ec-108">Level</span></span>|<span data-ttu-id="9d9ec-109">Подробный</span><span class="sxs-lookup"><span data-stu-id="9d9ec-109">Verbose</span></span>|  
|<span data-ttu-id="9d9ec-110">Канал</span><span class="sxs-lookup"><span data-stu-id="9d9ec-110">Channel</span></span>|<span data-ttu-id="9d9ec-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="9d9ec-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="9d9ec-112">Описание</span><span class="sxs-lookup"><span data-stu-id="9d9ec-112">Description</span></span>  

 <span data-ttu-id="9d9ec-113">Указывает, что CancelActivityWorkItem завершено.</span><span class="sxs-lookup"><span data-stu-id="9d9ec-113">Indicates a CancelActivityWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="9d9ec-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="9d9ec-114">Message</span></span>  

 <span data-ttu-id="9d9ec-115">CancelActivityWorkItem завершен для действия «%1», DisplayName «%2», InstanceId «%3».</span><span class="sxs-lookup"><span data-stu-id="9d9ec-115">A CancelActivityWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="9d9ec-116">Сведения</span><span class="sxs-lookup"><span data-stu-id="9d9ec-116">Details</span></span>  
  
|<span data-ttu-id="9d9ec-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="9d9ec-117">Data Item Name</span></span>|<span data-ttu-id="9d9ec-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="9d9ec-118">Data Item Type</span></span>|<span data-ttu-id="9d9ec-119">Описание</span><span class="sxs-lookup"><span data-stu-id="9d9ec-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="9d9ec-120">Действие</span><span class="sxs-lookup"><span data-stu-id="9d9ec-120">Activity</span></span>|<span data-ttu-id="9d9ec-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="9d9ec-121">xs:string</span></span>|<span data-ttu-id="9d9ec-122">Имя типа действия.</span><span class="sxs-lookup"><span data-stu-id="9d9ec-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="9d9ec-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="9d9ec-123">DisplayName</span></span>|<span data-ttu-id="9d9ec-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="9d9ec-124">xs:string</span></span>|<span data-ttu-id="9d9ec-125">Отображаемое имя действия.</span><span class="sxs-lookup"><span data-stu-id="9d9ec-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="9d9ec-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="9d9ec-126">InstanceId</span></span>|<span data-ttu-id="9d9ec-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="9d9ec-127">xs:string</span></span>|<span data-ttu-id="9d9ec-128">Идентификатор экземпляра действия.</span><span class="sxs-lookup"><span data-stu-id="9d9ec-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="9d9ec-129">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="9d9ec-129">AppDomain</span></span>|<span data-ttu-id="9d9ec-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="9d9ec-130">xs:string</span></span>|<span data-ttu-id="9d9ec-131">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="9d9ec-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
