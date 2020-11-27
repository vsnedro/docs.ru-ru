---
title: 4211 - QueuingSqlRetry
ms.date: 03/30/2017
ms.assetid: df569f88-c86b-4503-840d-1399b67f4df7
ms.openlocfilehash: ff8a1e099934f5bf71fef0afbb7e54c0d1851fae
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96267186"
---
# <a name="4211---queuingsqlretry"></a><span data-ttu-id="333cb-102">4211 - QueuingSqlRetry</span><span class="sxs-lookup"><span data-stu-id="333cb-102">4211 - QueuingSqlRetry</span></span>

## <a name="properties"></a><span data-ttu-id="333cb-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="333cb-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="333cb-104">ID</span><span class="sxs-lookup"><span data-stu-id="333cb-104">ID</span></span>|<span data-ttu-id="333cb-105">4211</span><span class="sxs-lookup"><span data-stu-id="333cb-105">4211</span></span>|  
|<span data-ttu-id="333cb-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="333cb-106">Keywords</span></span>|<span data-ttu-id="333cb-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="333cb-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="333cb-108">Level</span><span class="sxs-lookup"><span data-stu-id="333cb-108">Level</span></span>|<span data-ttu-id="333cb-109">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="333cb-109">Warning</span></span>|  
|<span data-ttu-id="333cb-110">Канал</span><span class="sxs-lookup"><span data-stu-id="333cb-110">Channel</span></span>|<span data-ttu-id="333cb-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="333cb-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="333cb-112">Описание</span><span class="sxs-lookup"><span data-stu-id="333cb-112">Description</span></span>  

 <span data-ttu-id="333cb-113">Указывает на повтор SQL с задержкой.</span><span class="sxs-lookup"><span data-stu-id="333cb-113">Indicates queuing SQL retry.</span></span>  
  
## <a name="message"></a><span data-ttu-id="333cb-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="333cb-114">Message</span></span>  

 <span data-ttu-id="333cb-115">Повторная попытка поместить SQL в очередь с задержкой %1 мс.</span><span class="sxs-lookup"><span data-stu-id="333cb-115">Queuing SQL retry with delay %1 milliseconds.</span></span>  
  
## <a name="details"></a><span data-ttu-id="333cb-116">Сведения</span><span class="sxs-lookup"><span data-stu-id="333cb-116">Details</span></span>  
  
|<span data-ttu-id="333cb-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="333cb-117">Data Item Name</span></span>|<span data-ttu-id="333cb-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="333cb-118">Data Item Type</span></span>|<span data-ttu-id="333cb-119">Описание</span><span class="sxs-lookup"><span data-stu-id="333cb-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="333cb-120">Задержка</span><span class="sxs-lookup"><span data-stu-id="333cb-120">Delay</span></span>|<span data-ttu-id="333cb-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="333cb-121">xs:string</span></span>|<span data-ttu-id="333cb-122">Задержка между повторными попытками.</span><span class="sxs-lookup"><span data-stu-id="333cb-122">The delay between retries.</span></span>|  
|<span data-ttu-id="333cb-123">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="333cb-123">AppDomain</span></span>|<span data-ttu-id="333cb-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="333cb-124">xs:string</span></span>|<span data-ttu-id="333cb-125">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="333cb-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
