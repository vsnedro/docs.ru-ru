---
title: 4209 - TimeoutOpeningSqlConnection
ms.date: 03/30/2017
ms.assetid: f0e56518-9758-41dc-a760-50d1a10fba6e
ms.openlocfilehash: 9aa8cdffebb0cdf8b1e8225a394edf78ecf032b9
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96238682"
---
# <a name="4209---timeoutopeningsqlconnection"></a><span data-ttu-id="5fda3-102">4209 - TimeoutOpeningSqlConnection</span><span class="sxs-lookup"><span data-stu-id="5fda3-102">4209 - TimeoutOpeningSqlConnection</span></span>

## <a name="properties"></a><span data-ttu-id="5fda3-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="5fda3-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5fda3-104">ID</span><span class="sxs-lookup"><span data-stu-id="5fda3-104">ID</span></span>|<span data-ttu-id="5fda3-105">4209</span><span class="sxs-lookup"><span data-stu-id="5fda3-105">4209</span></span>|  
|<span data-ttu-id="5fda3-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="5fda3-106">Keywords</span></span>|<span data-ttu-id="5fda3-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="5fda3-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="5fda3-108">Level</span><span class="sxs-lookup"><span data-stu-id="5fda3-108">Level</span></span>|<span data-ttu-id="5fda3-109">Ошибка</span><span class="sxs-lookup"><span data-stu-id="5fda3-109">Error</span></span>|  
|<span data-ttu-id="5fda3-110">Канал</span><span class="sxs-lookup"><span data-stu-id="5fda3-110">Channel</span></span>|<span data-ttu-id="5fda3-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="5fda3-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="5fda3-112">Описание</span><span class="sxs-lookup"><span data-stu-id="5fda3-112">Description</span></span>  

 <span data-ttu-id="5fda3-113">Указывает, что при попытке открыть соединение SQL превышено время ожидания.</span><span class="sxs-lookup"><span data-stu-id="5fda3-113">Indicates a timeout was encountered when trying to open a SQL connection.</span></span>  
  
## <a name="message"></a><span data-ttu-id="5fda3-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="5fda3-114">Message</span></span>  

 <span data-ttu-id="5fda3-115">Истекло время ожидания при открытии соединения SQL.</span><span class="sxs-lookup"><span data-stu-id="5fda3-115">Timeout trying to open a SQL connection.</span></span> <span data-ttu-id="5fda3-116">Не удалось выполнить операцию за выделенное время ожидания %1.</span><span class="sxs-lookup"><span data-stu-id="5fda3-116">The operation did not complete within the allotted timeout of %1.</span></span> <span data-ttu-id="5fda3-117">Возможно, выделенное для этой операции время было частью более длительного времени ожидания.</span><span class="sxs-lookup"><span data-stu-id="5fda3-117">The time allotted to this operation may have been a portion of a longer timeout.</span></span>  
  
## <a name="details"></a><span data-ttu-id="5fda3-118">Сведения</span><span class="sxs-lookup"><span data-stu-id="5fda3-118">Details</span></span>  
  
|<span data-ttu-id="5fda3-119">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="5fda3-119">Data Item Name</span></span>|<span data-ttu-id="5fda3-120">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="5fda3-120">Data Item Type</span></span>|<span data-ttu-id="5fda3-121">Описание</span><span class="sxs-lookup"><span data-stu-id="5fda3-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="5fda3-122">Время ожидания</span><span class="sxs-lookup"><span data-stu-id="5fda3-122">Timeout</span></span>|<span data-ttu-id="5fda3-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="5fda3-123">xs:string</span></span>|<span data-ttu-id="5fda3-124">Значение времени ожидания для открытия соединения SQL.</span><span class="sxs-lookup"><span data-stu-id="5fda3-124">The timeout value for opening the SQL connection.</span></span>|  
|<span data-ttu-id="5fda3-125">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="5fda3-125">AppDomain</span></span>|<span data-ttu-id="5fda3-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="5fda3-126">xs:string</span></span>|<span data-ttu-id="5fda3-127">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="5fda3-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
