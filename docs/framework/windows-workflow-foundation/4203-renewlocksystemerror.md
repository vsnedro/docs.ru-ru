---
title: 4203 - RenewLockSystemError
ms.date: 03/30/2017
ms.assetid: 6ec9ec6f-4ae2-45cf-b99b-02cdb9dc9ec9
ms.openlocfilehash: 17617e25c5cf8cecae608438529e9ce1a7d506f7
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96251273"
---
# <a name="4203---renewlocksystemerror"></a><span data-ttu-id="c9751-102">4203 - RenewLockSystemError</span><span class="sxs-lookup"><span data-stu-id="c9751-102">4203 - RenewLockSystemError</span></span>

## <a name="properties"></a><span data-ttu-id="c9751-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="c9751-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c9751-104">ID</span><span class="sxs-lookup"><span data-stu-id="c9751-104">ID</span></span>|<span data-ttu-id="c9751-105">4203</span><span class="sxs-lookup"><span data-stu-id="c9751-105">4203</span></span>|  
|<span data-ttu-id="c9751-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="c9751-106">Keywords</span></span>|<span data-ttu-id="c9751-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="c9751-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="c9751-108">Level</span><span class="sxs-lookup"><span data-stu-id="c9751-108">Level</span></span>|<span data-ttu-id="c9751-109">Ошибка</span><span class="sxs-lookup"><span data-stu-id="c9751-109">Error</span></span>|  
|<span data-ttu-id="c9751-110">Канал</span><span class="sxs-lookup"><span data-stu-id="c9751-110">Channel</span></span>|<span data-ttu-id="c9751-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="c9751-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="c9751-112">Описание</span><span class="sxs-lookup"><span data-stu-id="c9751-112">Description</span></span>  

 <span data-ttu-id="c9751-113">Указывает, что поставщику SQL не удалось продлить срок блокировки либо из-за того, что срок блокировки уже истек, либо из-за того, что владелец блокировки был удален.</span><span class="sxs-lookup"><span data-stu-id="c9751-113">Indicates SQL provider has failed to extend lock expiration due to either lock expiration already passed or the lock owner was deleted.</span></span> <span data-ttu-id="c9751-114">SqlWorkflowInstanceStore будет прервано.</span><span class="sxs-lookup"><span data-stu-id="c9751-114">The SqlWorkflowInstanceStore will be aborted.</span></span>  
  
## <a name="message"></a><span data-ttu-id="c9751-115">Сообщение</span><span class="sxs-lookup"><span data-stu-id="c9751-115">Message</span></span>  

 <span data-ttu-id="c9751-116">Не удалось увеличить срок окончания блокировки, срок окончания блокировки уже истек или владелец блокировки удален.</span><span class="sxs-lookup"><span data-stu-id="c9751-116">Failed to extend lock expiration, lock expiration already passed or the lock owner was deleted.</span></span> <span data-ttu-id="c9751-117">Прерывание блокировки SqlWorkflowInstanceStore.</span><span class="sxs-lookup"><span data-stu-id="c9751-117">Aborting SqlWorkflowInstanceStore.</span></span>  
  
## <a name="details"></a><span data-ttu-id="c9751-118">Сведения</span><span class="sxs-lookup"><span data-stu-id="c9751-118">Details</span></span>  
  
|<span data-ttu-id="c9751-119">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="c9751-119">Data Item Name</span></span>|<span data-ttu-id="c9751-120">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="c9751-120">Data Item Type</span></span>|<span data-ttu-id="c9751-121">Описание</span><span class="sxs-lookup"><span data-stu-id="c9751-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="c9751-122">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="c9751-122">AppDomain</span></span>|<span data-ttu-id="c9751-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="c9751-123">xs:string</span></span>|<span data-ttu-id="c9751-124">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="c9751-124">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
