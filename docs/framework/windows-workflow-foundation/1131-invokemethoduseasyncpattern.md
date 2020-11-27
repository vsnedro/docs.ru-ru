---
title: 1131 - InvokeMethodUseAsyncPattern
ms.date: 03/30/2017
ms.assetid: eca50fa7-5276-4759-ad1c-e490b9bd1f82
ms.openlocfilehash: 2192b63b8a08657b69f6e3984f898bd6baddbc5f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294187"
---
# <a name="1131---invokemethoduseasyncpattern"></a><span data-ttu-id="41b04-102">1131 - InvokeMethodUseAsyncPattern</span><span class="sxs-lookup"><span data-stu-id="41b04-102">1131 - InvokeMethodUseAsyncPattern</span></span>

## <a name="properties"></a><span data-ttu-id="41b04-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="41b04-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="41b04-104">ID</span><span class="sxs-lookup"><span data-stu-id="41b04-104">ID</span></span>|<span data-ttu-id="41b04-105">1131</span><span class="sxs-lookup"><span data-stu-id="41b04-105">1131</span></span>|  
|<span data-ttu-id="41b04-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="41b04-106">Keywords</span></span>|<span data-ttu-id="41b04-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="41b04-107">WFRuntime</span></span>|  
|<span data-ttu-id="41b04-108">Level</span><span class="sxs-lookup"><span data-stu-id="41b04-108">Level</span></span>|<span data-ttu-id="41b04-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="41b04-109">Information</span></span>|  
|<span data-ttu-id="41b04-110">Канал</span><span class="sxs-lookup"><span data-stu-id="41b04-110">Channel</span></span>|<span data-ttu-id="41b04-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="41b04-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="41b04-112">Описание</span><span class="sxs-lookup"><span data-stu-id="41b04-112">Description</span></span>  

 <span data-ttu-id="41b04-113">На шаге CacheMetadata действие InvokeMethod указывает на использование асинхронного шаблона при вызове метода.</span><span class="sxs-lookup"><span data-stu-id="41b04-113">During CacheMetadata step, InvokeMethod activity indicates that it is using the async pattern when invoking the method.</span></span>  
  
## <a name="message"></a><span data-ttu-id="41b04-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="41b04-114">Message</span></span>  

 <span data-ttu-id="41b04-115">Метод InvokeMethod «%1»: в методе используется асинхронная модель «%2» и «%3».</span><span class="sxs-lookup"><span data-stu-id="41b04-115">InvokeMethod '%1' - method uses asynchronous pattern of '%2' and '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="41b04-116">Сведения</span><span class="sxs-lookup"><span data-stu-id="41b04-116">Details</span></span>  
  
|<span data-ttu-id="41b04-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="41b04-117">Data Item Name</span></span>|<span data-ttu-id="41b04-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="41b04-118">Data Item Type</span></span>|<span data-ttu-id="41b04-119">Описание</span><span class="sxs-lookup"><span data-stu-id="41b04-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="41b04-120">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="41b04-120">InvokeMethod</span></span>|<span data-ttu-id="41b04-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="41b04-121">xs:string</span></span>|<span data-ttu-id="41b04-122">Отображаемое имя действия InvokeMethod.</span><span class="sxs-lookup"><span data-stu-id="41b04-122">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="41b04-123">BeginMethod</span><span class="sxs-lookup"><span data-stu-id="41b04-123">BeginMethod</span></span>|<span data-ttu-id="41b04-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="41b04-124">xs:string</span></span>|<span data-ttu-id="41b04-125">Имя метода Begin.</span><span class="sxs-lookup"><span data-stu-id="41b04-125">The name of the begin method.</span></span>|  
|<span data-ttu-id="41b04-126">EndMethod</span><span class="sxs-lookup"><span data-stu-id="41b04-126">EndMethod</span></span>|<span data-ttu-id="41b04-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="41b04-127">xs:string</span></span>|<span data-ttu-id="41b04-128">Имя метода End.</span><span class="sxs-lookup"><span data-stu-id="41b04-128">The name of the end method.</span></span>|  
|<span data-ttu-id="41b04-129">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="41b04-129">AppDomain</span></span>|<span data-ttu-id="41b04-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="41b04-130">xs:string</span></span>|<span data-ttu-id="41b04-131">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="41b04-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
