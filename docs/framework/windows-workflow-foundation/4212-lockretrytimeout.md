---
title: 4212 - LockRetryTimeout
ms.date: 03/30/2017
ms.assetid: d4ad415a-9871-49fc-85b8-8ee2ea149b1d
ms.openlocfilehash: 43ec434064f768fc976232c6d3013f17c80fe053
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96267173"
---
# <a name="4212---lockretrytimeout"></a><span data-ttu-id="c6431-102">4212 - LockRetryTimeout</span><span class="sxs-lookup"><span data-stu-id="c6431-102">4212 - LockRetryTimeout</span></span>

## <a name="properties"></a><span data-ttu-id="c6431-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="c6431-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c6431-104">ID</span><span class="sxs-lookup"><span data-stu-id="c6431-104">ID</span></span>|<span data-ttu-id="c6431-105">4212</span><span class="sxs-lookup"><span data-stu-id="c6431-105">4212</span></span>|  
|<span data-ttu-id="c6431-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="c6431-106">Keywords</span></span>|<span data-ttu-id="c6431-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="c6431-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="c6431-108">Level</span><span class="sxs-lookup"><span data-stu-id="c6431-108">Level</span></span>|<span data-ttu-id="c6431-109">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="c6431-109">Warning</span></span>|  
|<span data-ttu-id="c6431-110">Канал</span><span class="sxs-lookup"><span data-stu-id="c6431-110">Channel</span></span>|<span data-ttu-id="c6431-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="c6431-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="c6431-112">Описание</span><span class="sxs-lookup"><span data-stu-id="c6431-112">Description</span></span>  

 <span data-ttu-id="c6431-113">При попытке поставщика SQL получить блокировку для экземпляра истекло время ожидания.</span><span class="sxs-lookup"><span data-stu-id="c6431-113">SQL provider encountered a timeout trying to acquire the instance lock.</span></span>  
  
## <a name="message"></a><span data-ttu-id="c6431-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="c6431-114">Message</span></span>  

 <span data-ttu-id="c6431-115">Истекло время ожидания при попытке получить блокировку экземпляра.</span><span class="sxs-lookup"><span data-stu-id="c6431-115">Timeout trying to acquire the instance lock.</span></span>  <span data-ttu-id="c6431-116">Не удалось выполнить операцию за выделенное время ожидания %1.</span><span class="sxs-lookup"><span data-stu-id="c6431-116">The operation did not complete within the allotted timeout of %1.</span></span> <span data-ttu-id="c6431-117">Возможно, выделенное для этой операции время было частью более длительного времени ожидания.</span><span class="sxs-lookup"><span data-stu-id="c6431-117">The time allotted to this operation may have been a portion of a longer timeout.</span></span>  
  
## <a name="details"></a><span data-ttu-id="c6431-118">Сведения</span><span class="sxs-lookup"><span data-stu-id="c6431-118">Details</span></span>  
  
|<span data-ttu-id="c6431-119">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="c6431-119">Data Item Name</span></span>|<span data-ttu-id="c6431-120">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="c6431-120">Data Item Type</span></span>|<span data-ttu-id="c6431-121">Описание</span><span class="sxs-lookup"><span data-stu-id="c6431-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="c6431-122">Задержка</span><span class="sxs-lookup"><span data-stu-id="c6431-122">Delay</span></span>|<span data-ttu-id="c6431-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="c6431-123">xs:string</span></span>|<span data-ttu-id="c6431-124">Задержка между повторными попытками.</span><span class="sxs-lookup"><span data-stu-id="c6431-124">The delay between retries.</span></span>|  
|<span data-ttu-id="c6431-125">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="c6431-125">AppDomain</span></span>|<span data-ttu-id="c6431-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="c6431-126">xs:string</span></span>|<span data-ttu-id="c6431-127">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="c6431-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
