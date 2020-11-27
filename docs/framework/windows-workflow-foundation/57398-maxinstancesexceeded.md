---
title: 57398 - MaxInstancesExceeded
ms.date: 03/30/2017
ms.assetid: f943d209-dfeb-43e5-b572-c9a06217936e
ms.openlocfilehash: bd490aad24fba4550bc778799cd6f836dcfd466c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96289182"
---
# <a name="57398---maxinstancesexceeded"></a><span data-ttu-id="10eb5-102">57398 - MaxInstancesExceeded</span><span class="sxs-lookup"><span data-stu-id="10eb5-102">57398 - MaxInstancesExceeded</span></span>

## <a name="properties"></a><span data-ttu-id="10eb5-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="10eb5-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="10eb5-104">ID</span><span class="sxs-lookup"><span data-stu-id="10eb5-104">ID</span></span>|<span data-ttu-id="10eb5-105">57398</span><span class="sxs-lookup"><span data-stu-id="10eb5-105">57398</span></span>|  
|<span data-ttu-id="10eb5-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="10eb5-106">Keywords</span></span>|<span data-ttu-id="10eb5-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="10eb5-107">WFServices</span></span>|  
|<span data-ttu-id="10eb5-108">Level</span><span class="sxs-lookup"><span data-stu-id="10eb5-108">Level</span></span>|<span data-ttu-id="10eb5-109">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="10eb5-109">Warning</span></span>|  
|<span data-ttu-id="10eb5-110">Канал</span><span class="sxs-lookup"><span data-stu-id="10eb5-110">Channel</span></span>|<span data-ttu-id="10eb5-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="10eb5-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="10eb5-112">Описание</span><span class="sxs-lookup"><span data-stu-id="10eb5-112">Description</span></span>  

 <span data-ttu-id="10eb5-113">Указывает, что система достигла предела, заданного для ограничителя MaxConcurrentInstances.</span><span class="sxs-lookup"><span data-stu-id="10eb5-113">Indicates the system hit the limit set for throttle 'MaxConcurrentInstances'.</span></span>  
  
## <a name="message"></a><span data-ttu-id="10eb5-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="10eb5-114">Message</span></span>  

 <span data-ttu-id="10eb5-115">Система достигла предела, заданного для ограничителя «MaxConcurrentInstances».</span><span class="sxs-lookup"><span data-stu-id="10eb5-115">The system hit the limit set for throttle 'MaxConcurrentInstances'.</span></span> <span data-ttu-id="10eb5-116">Для этого ограничителя был задан предел %1.</span><span class="sxs-lookup"><span data-stu-id="10eb5-116">Limit for this throttle was set to %1.</span></span> <span data-ttu-id="10eb5-117">Значение ограничителя можно изменить, изменив атрибут maxConcurrentInstances в элементе serviceThrottle или свойство MaxConcurrentInstances для поведения ServiceThrottlingBehavior.</span><span class="sxs-lookup"><span data-stu-id="10eb5-117">Throttle value can be changed by modifying attribute 'maxConcurrentInstances' in serviceThrottle element or by modifying 'MaxConcurrentInstances' property on behavior ServiceThrottlingBehavior.</span></span>  
  
## <a name="details"></a><span data-ttu-id="10eb5-118">Сведения</span><span class="sxs-lookup"><span data-stu-id="10eb5-118">Details</span></span>  
  
|<span data-ttu-id="10eb5-119">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="10eb5-119">Data Item Name</span></span>|<span data-ttu-id="10eb5-120">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="10eb5-120">Data Item Type</span></span>|<span data-ttu-id="10eb5-121">Описание</span><span class="sxs-lookup"><span data-stu-id="10eb5-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="10eb5-122">name</span><span class="sxs-lookup"><span data-stu-id="10eb5-122">Name</span></span>|<span data-ttu-id="10eb5-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="10eb5-123">xs:string</span></span>|<span data-ttu-id="10eb5-124">Имя элемента.</span><span class="sxs-lookup"><span data-stu-id="10eb5-124">The name of the item.</span></span>|  
|<span data-ttu-id="10eb5-125">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="10eb5-125">AppDomain</span></span>|<span data-ttu-id="10eb5-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="10eb5-126">xs:string</span></span>|<span data-ttu-id="10eb5-127">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="10eb5-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
