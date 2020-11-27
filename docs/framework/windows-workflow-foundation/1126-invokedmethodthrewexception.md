---
title: 1126 - InvokedMethodThrewException
ms.date: 03/30/2017
ms.assetid: 0d3cff1a-97e6-4b6c-be18-108c6881bfc0
ms.openlocfilehash: 7caaebe42f49a62fec61ba17a4d3fe3a538e2ab4
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96262844"
---
# <a name="1126---invokedmethodthrewexception"></a><span data-ttu-id="83b35-102">1126 - InvokedMethodThrewException</span><span class="sxs-lookup"><span data-stu-id="83b35-102">1126 - InvokedMethodThrewException</span></span>

## <a name="properties"></a><span data-ttu-id="83b35-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="83b35-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="83b35-104">ID</span><span class="sxs-lookup"><span data-stu-id="83b35-104">ID</span></span>|<span data-ttu-id="83b35-105">1126</span><span class="sxs-lookup"><span data-stu-id="83b35-105">1126</span></span>|  
|<span data-ttu-id="83b35-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="83b35-106">Keywords</span></span>|<span data-ttu-id="83b35-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="83b35-107">WFRuntime</span></span>|  
|<span data-ttu-id="83b35-108">Level</span><span class="sxs-lookup"><span data-stu-id="83b35-108">Level</span></span>|<span data-ttu-id="83b35-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="83b35-109">Information</span></span>|  
|<span data-ttu-id="83b35-110">Канал</span><span class="sxs-lookup"><span data-stu-id="83b35-110">Channel</span></span>|<span data-ttu-id="83b35-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="83b35-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="83b35-112">Описание</span><span class="sxs-lookup"><span data-stu-id="83b35-112">Description</span></span>  

 <span data-ttu-id="83b35-113">Означает, что метод, вызванный действием InvokeMethod, привел к созданию исключения.</span><span class="sxs-lookup"><span data-stu-id="83b35-113">Indicates an exception was thrown by the method called by the InvokeMethod activity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="83b35-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="83b35-114">Message</span></span>  

 <span data-ttu-id="83b35-115">Возникло исключение в методе, вызванном операцией «%1».</span><span class="sxs-lookup"><span data-stu-id="83b35-115">An exception was thrown in the method called by the activity '%1'.</span></span> <span data-ttu-id="83b35-116">%2</span><span class="sxs-lookup"><span data-stu-id="83b35-116">%2</span></span>  
  
## <a name="details"></a><span data-ttu-id="83b35-117">Сведения</span><span class="sxs-lookup"><span data-stu-id="83b35-117">Details</span></span>  
  
|<span data-ttu-id="83b35-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="83b35-118">Data Item Name</span></span>|<span data-ttu-id="83b35-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="83b35-119">Data Item Type</span></span>|<span data-ttu-id="83b35-120">Описание</span><span class="sxs-lookup"><span data-stu-id="83b35-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="83b35-121">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="83b35-121">InvokeMethod</span></span>|<span data-ttu-id="83b35-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="83b35-122">xs:string</span></span>|<span data-ttu-id="83b35-123">Отображаемое имя действия InvokeMethod.</span><span class="sxs-lookup"><span data-stu-id="83b35-123">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="83b35-124">Исключение</span><span class="sxs-lookup"><span data-stu-id="83b35-124">Exception</span></span>|<span data-ttu-id="83b35-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="83b35-125">xs:string</span></span>|<span data-ttu-id="83b35-126">Сведения об исключении</span><span class="sxs-lookup"><span data-stu-id="83b35-126">The exception details for the exception</span></span>|  
|<span data-ttu-id="83b35-127">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="83b35-127">AppDomain</span></span>|<span data-ttu-id="83b35-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="83b35-128">xs:string</span></span>|<span data-ttu-id="83b35-129">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="83b35-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
