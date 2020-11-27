---
title: 3503 - DuplicateCorrelationQuery
ms.date: 03/30/2017
ms.assetid: b857f8e6-ce4d-4da4-bc9d-6cd63fa558a4
ms.openlocfilehash: e1e64824ee9a95757ed7c00aa17fa80898219401
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96270332"
---
# <a name="3503---duplicatecorrelationquery"></a><span data-ttu-id="ad445-102">3503 - DuplicateCorrelationQuery</span><span class="sxs-lookup"><span data-stu-id="ad445-102">3503 - DuplicateCorrelationQuery</span></span>

## <a name="properties"></a><span data-ttu-id="ad445-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="ad445-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ad445-104">ID</span><span class="sxs-lookup"><span data-stu-id="ad445-104">ID</span></span>|<span data-ttu-id="ad445-105">3503</span><span class="sxs-lookup"><span data-stu-id="ad445-105">3503</span></span>|  
|<span data-ttu-id="ad445-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="ad445-106">Keywords</span></span>|<span data-ttu-id="ad445-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="ad445-107">WFServices</span></span>|  
|<span data-ttu-id="ad445-108">Level</span><span class="sxs-lookup"><span data-stu-id="ad445-108">Level</span></span>|<span data-ttu-id="ad445-109">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="ad445-109">Warning</span></span>|  
|<span data-ttu-id="ad445-110">Канал</span><span class="sxs-lookup"><span data-stu-id="ad445-110">Channel</span></span>|<span data-ttu-id="ad445-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="ad445-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="ad445-112">Описание</span><span class="sxs-lookup"><span data-stu-id="ad445-112">Description</span></span>  

 <span data-ttu-id="ad445-113">Указывает, что обнаружен повторяющийся запрос CorrelationQuery.</span><span class="sxs-lookup"><span data-stu-id="ad445-113">Indicates a duplicate CorrelationQuery was found.</span></span> <span data-ttu-id="ad445-114">Повторяющийся запрос не будет использоваться при расчете корреляции.</span><span class="sxs-lookup"><span data-stu-id="ad445-114">The duplicate query will not be used when calculating correlation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="ad445-115">Сообщение</span><span class="sxs-lookup"><span data-stu-id="ad445-115">Message</span></span>  

 <span data-ttu-id="ad445-116">Обнаружен повторяющийся запрос CorrelationQuery с параметром Where=«%1».</span><span class="sxs-lookup"><span data-stu-id="ad445-116">A duplicate CorrelationQuery was found with Where='%1'.</span></span> <span data-ttu-id="ad445-117">Это дубликат не будет использоваться при расчете корреляции.</span><span class="sxs-lookup"><span data-stu-id="ad445-117">This duplicate query will not be used when calculating correlation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="ad445-118">Сведения</span><span class="sxs-lookup"><span data-stu-id="ad445-118">Details</span></span>  
  
|<span data-ttu-id="ad445-119">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="ad445-119">Data Item Name</span></span>|<span data-ttu-id="ad445-120">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="ad445-120">Data Item Type</span></span>|<span data-ttu-id="ad445-121">Описание</span><span class="sxs-lookup"><span data-stu-id="ad445-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="ad445-122">Where</span><span class="sxs-lookup"><span data-stu-id="ad445-122">Where</span></span>|<span data-ttu-id="ad445-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="ad445-123">xs:string</span></span>|<span data-ttu-id="ad445-124">Часть Where в запросе корреляции.</span><span class="sxs-lookup"><span data-stu-id="ad445-124">The Where portion of the correlation query.</span></span>|  
|<span data-ttu-id="ad445-125">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="ad445-125">AppDomain</span></span>|<span data-ttu-id="ad445-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="ad445-126">xs:string</span></span>|<span data-ttu-id="ad445-127">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="ad445-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
