---
title: 1029 - ScheduleFaultWorkItem
ms.date: 03/30/2017
ms.assetid: 3a56b29e-f740-459d-8576-d81e58bf5a03
ms.openlocfilehash: 5c109607b2d353d3d4a5a693f29ab66bb76c8398
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275093"
---
# <a name="1029---schedulefaultworkitem"></a><span data-ttu-id="c51e6-102">1029 - ScheduleFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="c51e6-102">1029 - ScheduleFaultWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="c51e6-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="c51e6-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c51e6-104">ID</span><span class="sxs-lookup"><span data-stu-id="c51e6-104">ID</span></span>|<span data-ttu-id="c51e6-105">1029</span><span class="sxs-lookup"><span data-stu-id="c51e6-105">1029</span></span>|  
|<span data-ttu-id="c51e6-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="c51e6-106">Keywords</span></span>|<span data-ttu-id="c51e6-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="c51e6-107">WFRuntime</span></span>|  
|<span data-ttu-id="c51e6-108">Level</span><span class="sxs-lookup"><span data-stu-id="c51e6-108">Level</span></span>|<span data-ttu-id="c51e6-109">Подробный</span><span class="sxs-lookup"><span data-stu-id="c51e6-109">Verbose</span></span>|  
|<span data-ttu-id="c51e6-110">Канал</span><span class="sxs-lookup"><span data-stu-id="c51e6-110">Channel</span></span>|<span data-ttu-id="c51e6-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="c51e6-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="c51e6-112">Описание</span><span class="sxs-lookup"><span data-stu-id="c51e6-112">Description</span></span>  

 <span data-ttu-id="c51e6-113">Указывает, что FaultWorkItem было предназначено.</span><span class="sxs-lookup"><span data-stu-id="c51e6-113">Indicates a FaultWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="c51e6-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="c51e6-114">Message</span></span>  

 <span data-ttu-id="c51e6-115">Фаултворкитем был запланирован для действия "%1", DisplayName: "%2", InstanceId: "%3".</span><span class="sxs-lookup"><span data-stu-id="c51e6-115">A FaultWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="c51e6-116">Исключение распространено из действия «%4», DisplayName «%5», InstanceId «%6».</span><span class="sxs-lookup"><span data-stu-id="c51e6-116">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="c51e6-117">Сведения</span><span class="sxs-lookup"><span data-stu-id="c51e6-117">Details</span></span>  
  
|<span data-ttu-id="c51e6-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="c51e6-118">Data Item Name</span></span>|<span data-ttu-id="c51e6-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="c51e6-119">Data Item Type</span></span>|<span data-ttu-id="c51e6-120">Описание</span><span class="sxs-lookup"><span data-stu-id="c51e6-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="c51e6-121">FaultActivity</span><span class="sxs-lookup"><span data-stu-id="c51e6-121">FaultActivity</span></span>|<span data-ttu-id="c51e6-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="c51e6-122">xs:string</span></span>|<span data-ttu-id="c51e6-123">Имя типа действия с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="c51e6-123">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="c51e6-124">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="c51e6-124">FaultActivityDisplayName</span></span>|<span data-ttu-id="c51e6-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="c51e6-125">xs:string</span></span>|<span data-ttu-id="c51e6-126">Отображаемое имя действия с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="c51e6-126">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="c51e6-127">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="c51e6-127">FaultActivityInstanceId</span></span>|<span data-ttu-id="c51e6-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="c51e6-128">xs:string</span></span>|<span data-ttu-id="c51e6-129">Идентификатор экземпляра действия с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="c51e6-129">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="c51e6-130">ExceptionActivity</span><span class="sxs-lookup"><span data-stu-id="c51e6-130">ExceptionActivity</span></span>|<span data-ttu-id="c51e6-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="c51e6-131">xs:string</span></span>|<span data-ttu-id="c51e6-132">Имя типа действия, вызвавшего исключение.</span><span class="sxs-lookup"><span data-stu-id="c51e6-132">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="c51e6-133">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="c51e6-133">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="c51e6-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="c51e6-134">xs:string</span></span>|<span data-ttu-id="c51e6-135">Отображаемое имя действия, вызвавшего исключение.</span><span class="sxs-lookup"><span data-stu-id="c51e6-135">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="c51e6-136">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="c51e6-136">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="c51e6-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="c51e6-137">xs:string</span></span>|<span data-ttu-id="c51e6-138">Идентификатор экземпляра действия, вызвавшего исключение.</span><span class="sxs-lookup"><span data-stu-id="c51e6-138">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="c51e6-139">Исключение</span><span class="sxs-lookup"><span data-stu-id="c51e6-139">Exception</span></span>|<span data-ttu-id="c51e6-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="c51e6-140">xs:string</span></span>|<span data-ttu-id="c51e6-141">Сведения об исключении</span><span class="sxs-lookup"><span data-stu-id="c51e6-141">The exception details for the exception</span></span>|  
|<span data-ttu-id="c51e6-142">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="c51e6-142">AppDomain</span></span>|<span data-ttu-id="c51e6-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="c51e6-143">xs:string</span></span>|<span data-ttu-id="c51e6-144">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="c51e6-144">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
