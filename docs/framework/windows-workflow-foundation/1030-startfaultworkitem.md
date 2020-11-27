---
title: 1030 - StartFaultWorkItem
ms.date: 03/30/2017
ms.assetid: e1601fb9-0bc6-4dbe-816f-f24914063d34
ms.openlocfilehash: 52034f7cc7c6f6749fbbbf06db9267ecb6279ee1
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96281863"
---
# <a name="1030---startfaultworkitem"></a><span data-ttu-id="2f4a0-102">1030 - StartFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="2f4a0-102">1030 - StartFaultWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="2f4a0-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="2f4a0-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2f4a0-104">ID</span><span class="sxs-lookup"><span data-stu-id="2f4a0-104">ID</span></span>|<span data-ttu-id="2f4a0-105">1030</span><span class="sxs-lookup"><span data-stu-id="2f4a0-105">1030</span></span>|  
|<span data-ttu-id="2f4a0-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="2f4a0-106">Keywords</span></span>|<span data-ttu-id="2f4a0-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="2f4a0-107">WFRuntime</span></span>|  
|<span data-ttu-id="2f4a0-108">Level</span><span class="sxs-lookup"><span data-stu-id="2f4a0-108">Level</span></span>|<span data-ttu-id="2f4a0-109">Подробный</span><span class="sxs-lookup"><span data-stu-id="2f4a0-109">Verbose</span></span>|  
|<span data-ttu-id="2f4a0-110">Канал</span><span class="sxs-lookup"><span data-stu-id="2f4a0-110">Channel</span></span>|<span data-ttu-id="2f4a0-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="2f4a0-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="2f4a0-112">Описание</span><span class="sxs-lookup"><span data-stu-id="2f4a0-112">Description</span></span>  

 <span data-ttu-id="2f4a0-113">Указывает на начало выполнения FaultWorkItem.</span><span class="sxs-lookup"><span data-stu-id="2f4a0-113">Indicates a FaultWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="2f4a0-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="2f4a0-114">Message</span></span>  

 <span data-ttu-id="2f4a0-115">Запуск выполнения Фаултворкитем для действия "%1", DisplayName: "%2", InstanceId: "%3".</span><span class="sxs-lookup"><span data-stu-id="2f4a0-115">Starting execution of a FaultWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="2f4a0-116">Исключение распространено из действия «%4», DisplayName «%5», InstanceId «%6».</span><span class="sxs-lookup"><span data-stu-id="2f4a0-116">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="2f4a0-117">Сведения</span><span class="sxs-lookup"><span data-stu-id="2f4a0-117">Details</span></span>  
  
|<span data-ttu-id="2f4a0-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="2f4a0-118">Data Item Name</span></span>|<span data-ttu-id="2f4a0-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="2f4a0-119">Data Item Type</span></span>|<span data-ttu-id="2f4a0-120">Описание</span><span class="sxs-lookup"><span data-stu-id="2f4a0-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="2f4a0-121">FaultActivity</span><span class="sxs-lookup"><span data-stu-id="2f4a0-121">FaultActivity</span></span>|<span data-ttu-id="2f4a0-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="2f4a0-122">xs:string</span></span>|<span data-ttu-id="2f4a0-123">Имя типа действия с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="2f4a0-123">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="2f4a0-124">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="2f4a0-124">FaultActivityDisplayName</span></span>|<span data-ttu-id="2f4a0-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="2f4a0-125">xs:string</span></span>|<span data-ttu-id="2f4a0-126">Отображаемое имя действия с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="2f4a0-126">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="2f4a0-127">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="2f4a0-127">FaultActivityInstanceId</span></span>|<span data-ttu-id="2f4a0-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="2f4a0-128">xs:string</span></span>|<span data-ttu-id="2f4a0-129">Идентификатор экземпляра действия с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="2f4a0-129">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="2f4a0-130">ExceptionActivity</span><span class="sxs-lookup"><span data-stu-id="2f4a0-130">ExceptionActivity</span></span>|<span data-ttu-id="2f4a0-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="2f4a0-131">xs:string</span></span>|<span data-ttu-id="2f4a0-132">Имя типа действия, вызвавшего исключение.</span><span class="sxs-lookup"><span data-stu-id="2f4a0-132">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="2f4a0-133">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="2f4a0-133">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="2f4a0-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="2f4a0-134">xs:string</span></span>|<span data-ttu-id="2f4a0-135">Отображаемое имя действия, вызвавшего исключение.</span><span class="sxs-lookup"><span data-stu-id="2f4a0-135">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="2f4a0-136">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="2f4a0-136">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="2f4a0-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="2f4a0-137">xs:string</span></span>|<span data-ttu-id="2f4a0-138">Идентификатор экземпляра действия, вызвавшего исключение.</span><span class="sxs-lookup"><span data-stu-id="2f4a0-138">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="2f4a0-139">Исключение</span><span class="sxs-lookup"><span data-stu-id="2f4a0-139">Exception</span></span>|<span data-ttu-id="2f4a0-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="2f4a0-140">xs:string</span></span>|<span data-ttu-id="2f4a0-141">Сведения об исключении</span><span class="sxs-lookup"><span data-stu-id="2f4a0-141">The exception details for the exception</span></span>|  
|<span data-ttu-id="2f4a0-142">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="2f4a0-142">AppDomain</span></span>|<span data-ttu-id="2f4a0-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="2f4a0-143">xs:string</span></span>|<span data-ttu-id="2f4a0-144">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="2f4a0-144">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
