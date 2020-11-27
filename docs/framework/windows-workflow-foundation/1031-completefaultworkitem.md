---
title: 1031 - CompleteFaultWorkItem
ms.date: 03/30/2017
ms.assetid: 95f4ccb0-6be4-41f3-9330-fae43165828f
ms.openlocfilehash: 557155fab35a37bdbaa45efb26d6bc025ad825c4
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96281837"
---
# <a name="1031---completefaultworkitem"></a><span data-ttu-id="3c8f8-102">1031 - CompleteFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="3c8f8-102">1031 - CompleteFaultWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="3c8f8-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="3c8f8-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3c8f8-104">ID</span><span class="sxs-lookup"><span data-stu-id="3c8f8-104">ID</span></span>|<span data-ttu-id="3c8f8-105">1031</span><span class="sxs-lookup"><span data-stu-id="3c8f8-105">1031</span></span>|  
|<span data-ttu-id="3c8f8-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="3c8f8-106">Keywords</span></span>|<span data-ttu-id="3c8f8-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="3c8f8-107">WFRuntime</span></span>|  
|<span data-ttu-id="3c8f8-108">Level</span><span class="sxs-lookup"><span data-stu-id="3c8f8-108">Level</span></span>|<span data-ttu-id="3c8f8-109">Подробный</span><span class="sxs-lookup"><span data-stu-id="3c8f8-109">Verbose</span></span>|  
|<span data-ttu-id="3c8f8-110">Канал</span><span class="sxs-lookup"><span data-stu-id="3c8f8-110">Channel</span></span>|<span data-ttu-id="3c8f8-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="3c8f8-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="3c8f8-112">Описание</span><span class="sxs-lookup"><span data-stu-id="3c8f8-112">Description</span></span>  

 <span data-ttu-id="3c8f8-113">Указывает, что FaultWorkItem завершено.</span><span class="sxs-lookup"><span data-stu-id="3c8f8-113">Indicates a FaultWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="3c8f8-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="3c8f8-114">Message</span></span>  

 <span data-ttu-id="3c8f8-115">FaultWorkItem завершено для действия «%1», DisplayName «%2», InstanceId «%3».</span><span class="sxs-lookup"><span data-stu-id="3c8f8-115">A FaultWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="3c8f8-116">Исключение распространено из действия «%4», DisplayName «%5», InstanceId «%6».</span><span class="sxs-lookup"><span data-stu-id="3c8f8-116">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="3c8f8-117">Сведения</span><span class="sxs-lookup"><span data-stu-id="3c8f8-117">Details</span></span>  
  
|<span data-ttu-id="3c8f8-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="3c8f8-118">Data Item Name</span></span>|<span data-ttu-id="3c8f8-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="3c8f8-119">Data Item Type</span></span>|<span data-ttu-id="3c8f8-120">Описание</span><span class="sxs-lookup"><span data-stu-id="3c8f8-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="3c8f8-121">FaultActivity</span><span class="sxs-lookup"><span data-stu-id="3c8f8-121">FaultActivity</span></span>|<span data-ttu-id="3c8f8-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="3c8f8-122">xs:string</span></span>|<span data-ttu-id="3c8f8-123">Имя типа действия с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="3c8f8-123">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="3c8f8-124">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="3c8f8-124">FaultActivityDisplayName</span></span>|<span data-ttu-id="3c8f8-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="3c8f8-125">xs:string</span></span>|<span data-ttu-id="3c8f8-126">Отображаемое имя действия с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="3c8f8-126">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="3c8f8-127">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="3c8f8-127">FaultActivityInstanceId</span></span>|<span data-ttu-id="3c8f8-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="3c8f8-128">xs:string</span></span>|<span data-ttu-id="3c8f8-129">Идентификатор экземпляра действия с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="3c8f8-129">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="3c8f8-130">ExceptionActivity</span><span class="sxs-lookup"><span data-stu-id="3c8f8-130">ExceptionActivity</span></span>|<span data-ttu-id="3c8f8-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="3c8f8-131">xs:string</span></span>|<span data-ttu-id="3c8f8-132">Имя типа действия, вызвавшего исключение.</span><span class="sxs-lookup"><span data-stu-id="3c8f8-132">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="3c8f8-133">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="3c8f8-133">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="3c8f8-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="3c8f8-134">xs:string</span></span>|<span data-ttu-id="3c8f8-135">Отображаемое имя действия, вызвавшего исключение.</span><span class="sxs-lookup"><span data-stu-id="3c8f8-135">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="3c8f8-136">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="3c8f8-136">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="3c8f8-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="3c8f8-137">xs:string</span></span>|<span data-ttu-id="3c8f8-138">Идентификатор экземпляра действия, вызвавшего исключение.</span><span class="sxs-lookup"><span data-stu-id="3c8f8-138">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="3c8f8-139">Исключение</span><span class="sxs-lookup"><span data-stu-id="3c8f8-139">Exception</span></span>|<span data-ttu-id="3c8f8-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="3c8f8-140">xs:string</span></span>|<span data-ttu-id="3c8f8-141">Сведения об исключении</span><span class="sxs-lookup"><span data-stu-id="3c8f8-141">The exception details for the exception</span></span>|  
|<span data-ttu-id="3c8f8-142">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="3c8f8-142">AppDomain</span></span>|<span data-ttu-id="3c8f8-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="3c8f8-143">xs:string</span></span>|<span data-ttu-id="3c8f8-144">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="3c8f8-144">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
