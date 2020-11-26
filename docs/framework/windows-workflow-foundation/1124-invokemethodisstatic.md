---
title: 1124 - InvokeMethodIsStatic
ms.date: 03/30/2017
ms.assetid: b9643641-fb52-4fa8-b354-4dd6617d68f6
ms.openlocfilehash: d7ad99131f9813c2102f52784fc33605bed37557
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96242127"
---
# <a name="1124---invokemethodisstatic"></a><span data-ttu-id="8d540-102">1124 - InvokeMethodIsStatic</span><span class="sxs-lookup"><span data-stu-id="8d540-102">1124 - InvokeMethodIsStatic</span></span>

## <a name="properties"></a><span data-ttu-id="8d540-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="8d540-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8d540-104">ID</span><span class="sxs-lookup"><span data-stu-id="8d540-104">ID</span></span>|<span data-ttu-id="8d540-105">1124</span><span class="sxs-lookup"><span data-stu-id="8d540-105">1124</span></span>|  
|<span data-ttu-id="8d540-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="8d540-106">Keywords</span></span>|<span data-ttu-id="8d540-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="8d540-107">WFRuntime</span></span>|  
|<span data-ttu-id="8d540-108">Level</span><span class="sxs-lookup"><span data-stu-id="8d540-108">Level</span></span>|<span data-ttu-id="8d540-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="8d540-109">Information</span></span>|  
|<span data-ttu-id="8d540-110">Канал</span><span class="sxs-lookup"><span data-stu-id="8d540-110">Channel</span></span>|<span data-ttu-id="8d540-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="8d540-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="8d540-112">Описание</span><span class="sxs-lookup"><span data-stu-id="8d540-112">Description</span></span>  

 <span data-ttu-id="8d540-113">На шаге CacheMetadata действие InvokeMethod означает, что вызываемый метод - статический.</span><span class="sxs-lookup"><span data-stu-id="8d540-113">During CacheMetadata step, InvokeMethod activity indicates the method to be invoked is static.</span></span>  
  
## <a name="message"></a><span data-ttu-id="8d540-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="8d540-114">Message</span></span>  

 <span data-ttu-id="8d540-115">Метод InvokeMethod «%1»: метод является статическим.</span><span class="sxs-lookup"><span data-stu-id="8d540-115">InvokeMethod '%1' - method is Static.</span></span>  
  
## <a name="details"></a><span data-ttu-id="8d540-116">Сведения</span><span class="sxs-lookup"><span data-stu-id="8d540-116">Details</span></span>  
  
|<span data-ttu-id="8d540-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="8d540-117">Data Item Name</span></span>|<span data-ttu-id="8d540-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="8d540-118">Data Item Type</span></span>|<span data-ttu-id="8d540-119">Описание</span><span class="sxs-lookup"><span data-stu-id="8d540-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="8d540-120">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="8d540-120">InvokeMethod</span></span>|<span data-ttu-id="8d540-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="8d540-121">xs:string</span></span>|<span data-ttu-id="8d540-122">Отображаемое имя действия InvokeMethod.</span><span class="sxs-lookup"><span data-stu-id="8d540-122">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="8d540-123">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="8d540-123">AppDomain</span></span>|<span data-ttu-id="8d540-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="8d540-124">xs:string</span></span>|<span data-ttu-id="8d540-125">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="8d540-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
