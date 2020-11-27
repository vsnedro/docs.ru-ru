---
title: 1125 - InvokeMethodIsNotStatic
ms.date: 03/30/2017
ms.assetid: ea2b3827-63da-497b-b2c3-d5cebefe57a1
ms.openlocfilehash: 0405b4e1207db5c056fbd478b98c408258daf0c3
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294213"
---
# <a name="1125---invokemethodisnotstatic"></a><span data-ttu-id="65e56-102">1125 - InvokeMethodIsNotStatic</span><span class="sxs-lookup"><span data-stu-id="65e56-102">1125 - InvokeMethodIsNotStatic</span></span>

## <a name="properties"></a><span data-ttu-id="65e56-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="65e56-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="65e56-104">ID</span><span class="sxs-lookup"><span data-stu-id="65e56-104">ID</span></span>|<span data-ttu-id="65e56-105">1125</span><span class="sxs-lookup"><span data-stu-id="65e56-105">1125</span></span>|  
|<span data-ttu-id="65e56-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="65e56-106">Keywords</span></span>|<span data-ttu-id="65e56-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="65e56-107">WFRuntime</span></span>|  
|<span data-ttu-id="65e56-108">Level</span><span class="sxs-lookup"><span data-stu-id="65e56-108">Level</span></span>|<span data-ttu-id="65e56-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="65e56-109">Information</span></span>|  
|<span data-ttu-id="65e56-110">Канал</span><span class="sxs-lookup"><span data-stu-id="65e56-110">Channel</span></span>|<span data-ttu-id="65e56-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="65e56-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="65e56-112">Описание</span><span class="sxs-lookup"><span data-stu-id="65e56-112">Description</span></span>  

 <span data-ttu-id="65e56-113">На шаге CacheMetadata действие InvokeMethod означает, что вызываемый метод - не статический.</span><span class="sxs-lookup"><span data-stu-id="65e56-113">During CacheMetadata step, InvokeMethod activity indicates the method to be invoked is not static.</span></span>  
  
## <a name="message"></a><span data-ttu-id="65e56-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="65e56-114">Message</span></span>  

 <span data-ttu-id="65e56-115">Метод InvokeMethod «%1»: метод не является статическим.</span><span class="sxs-lookup"><span data-stu-id="65e56-115">InvokeMethod '%1' - method is not Static.</span></span>  
  
## <a name="details"></a><span data-ttu-id="65e56-116">Сведения</span><span class="sxs-lookup"><span data-stu-id="65e56-116">Details</span></span>  
  
|<span data-ttu-id="65e56-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="65e56-117">Data Item Name</span></span>|<span data-ttu-id="65e56-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="65e56-118">Data Item Type</span></span>|<span data-ttu-id="65e56-119">Описание</span><span class="sxs-lookup"><span data-stu-id="65e56-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="65e56-120">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="65e56-120">InvokeMethod</span></span>|<span data-ttu-id="65e56-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="65e56-121">xs:string</span></span>|<span data-ttu-id="65e56-122">Отображаемое имя действия InvokeMethod.</span><span class="sxs-lookup"><span data-stu-id="65e56-122">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="65e56-123">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="65e56-123">AppDomain</span></span>|<span data-ttu-id="65e56-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="65e56-124">xs:string</span></span>|<span data-ttu-id="65e56-125">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="65e56-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
