---
title: 1032 - ScheduleRuntimeWorkItem
ms.date: 03/30/2017
ms.assetid: 54688101-becf-42f3-80ca-f53a7b527620
ms.openlocfilehash: da35201f2b3e3bc07e0b9139b0584ce37011e168
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294317"
---
# <a name="1032---scheduleruntimeworkitem"></a><span data-ttu-id="47a31-102">1032 - ScheduleRuntimeWorkItem</span><span class="sxs-lookup"><span data-stu-id="47a31-102">1032 - ScheduleRuntimeWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="47a31-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="47a31-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="47a31-104">ID</span><span class="sxs-lookup"><span data-stu-id="47a31-104">ID</span></span>|<span data-ttu-id="47a31-105">1032</span><span class="sxs-lookup"><span data-stu-id="47a31-105">1032</span></span>|  
|<span data-ttu-id="47a31-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="47a31-106">Keywords</span></span>|<span data-ttu-id="47a31-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="47a31-107">WFRuntime</span></span>|  
|<span data-ttu-id="47a31-108">Level</span><span class="sxs-lookup"><span data-stu-id="47a31-108">Level</span></span>|<span data-ttu-id="47a31-109">Подробный</span><span class="sxs-lookup"><span data-stu-id="47a31-109">Verbose</span></span>|  
|<span data-ttu-id="47a31-110">Канал</span><span class="sxs-lookup"><span data-stu-id="47a31-110">Channel</span></span>|<span data-ttu-id="47a31-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="47a31-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="47a31-112">Описание</span><span class="sxs-lookup"><span data-stu-id="47a31-112">Description</span></span>  

 <span data-ttu-id="47a31-113">Указывает, что элемент RuntimeWorkItem был запланирован.</span><span class="sxs-lookup"><span data-stu-id="47a31-113">Indicates a RuntimeWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="47a31-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="47a31-114">Message</span></span>  

 <span data-ttu-id="47a31-115">Рабочий элемент среды выполнения запланирован для действия «%1», DisplayName «%2», InstanceId «%3».</span><span class="sxs-lookup"><span data-stu-id="47a31-115">A runtime work item has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="47a31-116">Сведения</span><span class="sxs-lookup"><span data-stu-id="47a31-116">Details</span></span>  
  
|<span data-ttu-id="47a31-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="47a31-117">Data Item Name</span></span>|<span data-ttu-id="47a31-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="47a31-118">Data Item Type</span></span>|<span data-ttu-id="47a31-119">Описание</span><span class="sxs-lookup"><span data-stu-id="47a31-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="47a31-120">Действие</span><span class="sxs-lookup"><span data-stu-id="47a31-120">Activity</span></span>|<span data-ttu-id="47a31-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="47a31-121">xs:string</span></span>|<span data-ttu-id="47a31-122">Имя типа действия.</span><span class="sxs-lookup"><span data-stu-id="47a31-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="47a31-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="47a31-123">DisplayName</span></span>|<span data-ttu-id="47a31-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="47a31-124">xs:string</span></span>|<span data-ttu-id="47a31-125">Отображаемое имя действия.</span><span class="sxs-lookup"><span data-stu-id="47a31-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="47a31-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="47a31-126">InstanceId</span></span>|<span data-ttu-id="47a31-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="47a31-127">xs:string</span></span>|<span data-ttu-id="47a31-128">Идентификатор экземпляра действия.</span><span class="sxs-lookup"><span data-stu-id="47a31-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="47a31-129">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="47a31-129">AppDomain</span></span>|<span data-ttu-id="47a31-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="47a31-130">xs:string</span></span>|<span data-ttu-id="47a31-131">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="47a31-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
