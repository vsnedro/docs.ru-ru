---
title: 2577 - TryCatchExceptionDuringCancelation
ms.date: 03/30/2017
ms.assetid: 35ee9f55-227f-4566-bcb4-4c7c75dea85b
ms.openlocfilehash: 33c68984e88eaa5e3028899a7c3066c94a65e8eb
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96271243"
---
# <a name="2577---trycatchexceptionduringcancelation"></a><span data-ttu-id="051d6-102">2577 - TryCatchExceptionDuringCancelation</span><span class="sxs-lookup"><span data-stu-id="051d6-102">2577 - TryCatchExceptionDuringCancelation</span></span>

## <a name="properties"></a><span data-ttu-id="051d6-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="051d6-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="051d6-104">ID</span><span class="sxs-lookup"><span data-stu-id="051d6-104">ID</span></span>|<span data-ttu-id="051d6-105">2577</span><span class="sxs-lookup"><span data-stu-id="051d6-105">2577</span></span>|  
|<span data-ttu-id="051d6-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="051d6-106">Keywords</span></span>|<span data-ttu-id="051d6-107">WFActivities</span><span class="sxs-lookup"><span data-stu-id="051d6-107">WFActivities</span></span>|  
|<span data-ttu-id="051d6-108">Level</span><span class="sxs-lookup"><span data-stu-id="051d6-108">Level</span></span>|<span data-ttu-id="051d6-109">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="051d6-109">Warning</span></span>|  
|<span data-ttu-id="051d6-110">Канал</span><span class="sxs-lookup"><span data-stu-id="051d6-110">Channel</span></span>|<span data-ttu-id="051d6-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="051d6-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="051d6-112">Описание</span><span class="sxs-lookup"><span data-stu-id="051d6-112">Description</span></span>  

 <span data-ttu-id="051d6-113">Указывает, что дочернее действие для действия TryCatch вызвало исключение во время отмены.</span><span class="sxs-lookup"><span data-stu-id="051d6-113">Indicates a child activity of the TryCatch activity has thrown an exception during cancelation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="051d6-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="051d6-114">Message</span></span>  

 <span data-ttu-id="051d6-115">При отмене дочернего действия для действия TryCatch «%1» произошло исключение.</span><span class="sxs-lookup"><span data-stu-id="051d6-115">A child activity of the TryCatch activity '%1' has thrown an exception during cancelation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="051d6-116">Сведения</span><span class="sxs-lookup"><span data-stu-id="051d6-116">Details</span></span>  
  
|<span data-ttu-id="051d6-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="051d6-117">Data Item Name</span></span>|<span data-ttu-id="051d6-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="051d6-118">Data Item Type</span></span>|<span data-ttu-id="051d6-119">Описание</span><span class="sxs-lookup"><span data-stu-id="051d6-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="051d6-120">DisplayName</span><span class="sxs-lookup"><span data-stu-id="051d6-120">DisplayName</span></span>|<span data-ttu-id="051d6-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="051d6-121">xs:string</span></span>|<span data-ttu-id="051d6-122">Отображаемое имя действия.</span><span class="sxs-lookup"><span data-stu-id="051d6-122">The display name of the activity.</span></span>|  
|<span data-ttu-id="051d6-123">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="051d6-123">AppDomain</span></span>|<span data-ttu-id="051d6-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="051d6-124">xs:string</span></span>|<span data-ttu-id="051d6-125">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="051d6-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
