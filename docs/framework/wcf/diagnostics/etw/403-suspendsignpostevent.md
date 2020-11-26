---
title: 403 - SuspendSignpostEvent
ms.date: 03/30/2017
ms.assetid: fb2e6f29-e556-47b4-b4c1-acd6b8879702
ms.openlocfilehash: 66251141cdf66c18ad0c1334f6f3e6c0629b4b33
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96241061"
---
# <a name="403---suspendsignpostevent"></a><span data-ttu-id="c75a8-102">403 - SuspendSignpostEvent</span><span class="sxs-lookup"><span data-stu-id="c75a8-102">403 - SuspendSignpostEvent</span></span>

## <a name="properties"></a><span data-ttu-id="c75a8-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="c75a8-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c75a8-104">ID</span><span class="sxs-lookup"><span data-stu-id="c75a8-104">ID</span></span>|<span data-ttu-id="c75a8-105">403</span><span class="sxs-lookup"><span data-stu-id="c75a8-105">403</span></span>|  
|<span data-ttu-id="c75a8-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="c75a8-106">Keywords</span></span>|<span data-ttu-id="c75a8-107">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="c75a8-107">Troubleshooting</span></span>|  
|<span data-ttu-id="c75a8-108">Level</span><span class="sxs-lookup"><span data-stu-id="c75a8-108">Level</span></span>|<span data-ttu-id="c75a8-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="c75a8-109">Information</span></span>|  
|<span data-ttu-id="c75a8-110">Канал</span><span class="sxs-lookup"><span data-stu-id="c75a8-110">Channel</span></span>|<span data-ttu-id="c75a8-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="c75a8-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="c75a8-112">Описание</span><span class="sxs-lookup"><span data-stu-id="c75a8-112">Description</span></span>  

 <span data-ttu-id="c75a8-113">Это событие сигнализирует о приостановке сквозного действия.</span><span class="sxs-lookup"><span data-stu-id="c75a8-113">This event marks the suspension of an end-to-end activity.</span></span> <span data-ttu-id="c75a8-114">В ней содержится имя действия.</span><span class="sxs-lookup"><span data-stu-id="c75a8-114">It contains the name of the activity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="c75a8-115">Сообщение</span><span class="sxs-lookup"><span data-stu-id="c75a8-115">Message</span></span>  

 <span data-ttu-id="c75a8-116">Граница действия.</span><span class="sxs-lookup"><span data-stu-id="c75a8-116">Activity boundary.</span></span>  
  
## <a name="details"></a><span data-ttu-id="c75a8-117">Сведения</span><span class="sxs-lookup"><span data-stu-id="c75a8-117">Details</span></span>  
  
|<span data-ttu-id="c75a8-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="c75a8-118">Data Item Name</span></span>|<span data-ttu-id="c75a8-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="c75a8-119">Data Item Type</span></span>|<span data-ttu-id="c75a8-120">Описание</span><span class="sxs-lookup"><span data-stu-id="c75a8-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="c75a8-121">Расширенные данные</span><span class="sxs-lookup"><span data-stu-id="c75a8-121">Extended Data</span></span>|`xs:string`|<span data-ttu-id="c75a8-122">Имя действия.</span><span class="sxs-lookup"><span data-stu-id="c75a8-122">The name of the activity.</span></span>|  
|<span data-ttu-id="c75a8-123">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="c75a8-123">AppDomain</span></span>|`xs:string`|<span data-ttu-id="c75a8-124">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="c75a8-124">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
