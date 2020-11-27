---
title: 39458 - TrackingRecordTruncated
ms.date: 03/30/2017
ms.assetid: 5352f0eb-d571-454a-bab5-e2162888b218
ms.openlocfilehash: f02a34673c51be6e0b127a64e4622131575d836f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275896"
---
# <a name="39458---trackingrecordtruncated"></a><span data-ttu-id="3c6f9-102">39458 - TrackingRecordTruncated</span><span class="sxs-lookup"><span data-stu-id="3c6f9-102">39458 - TrackingRecordTruncated</span></span>

## <a name="properties"></a><span data-ttu-id="3c6f9-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="3c6f9-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3c6f9-104">ID</span><span class="sxs-lookup"><span data-stu-id="3c6f9-104">ID</span></span>|<span data-ttu-id="3c6f9-105">39458</span><span class="sxs-lookup"><span data-stu-id="3c6f9-105">39458</span></span>|  
|<span data-ttu-id="3c6f9-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="3c6f9-106">Keywords</span></span>|<span data-ttu-id="3c6f9-107">WFTracking</span><span class="sxs-lookup"><span data-stu-id="3c6f9-107">WFTracking</span></span>|  
|<span data-ttu-id="3c6f9-108">Level</span><span class="sxs-lookup"><span data-stu-id="3c6f9-108">Level</span></span>|<span data-ttu-id="3c6f9-109">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="3c6f9-109">Warning</span></span>|  
|<span data-ttu-id="3c6f9-110">Канал</span><span class="sxs-lookup"><span data-stu-id="3c6f9-110">Channel</span></span>|<span data-ttu-id="3c6f9-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="3c6f9-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="3c6f9-112">Описание</span><span class="sxs-lookup"><span data-stu-id="3c6f9-112">Description</span></span>  

 <span data-ttu-id="3c6f9-113">Указывает, что запись отслеживания была усечена.</span><span class="sxs-lookup"><span data-stu-id="3c6f9-113">Indicates a tracking record has been truncated.</span></span> <span data-ttu-id="3c6f9-114">Данные переменных, заметок, пользователей удалены.</span><span class="sxs-lookup"><span data-stu-id="3c6f9-114">Variables/annotations/user data have been removed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="3c6f9-115">Сообщение</span><span class="sxs-lookup"><span data-stu-id="3c6f9-115">Message</span></span>  

 <span data-ttu-id="3c6f9-116">Усеченная запись отслеживания %1 записана в сеанс трассировки событий Windows с использованием поставщика %2.</span><span class="sxs-lookup"><span data-stu-id="3c6f9-116">Truncated tracking record %1 written to ETW session with provider %2.</span></span> <span data-ttu-id="3c6f9-117">Данные переменных, заметок, пользователей удалены</span><span class="sxs-lookup"><span data-stu-id="3c6f9-117">Variables/annotations/user data have been removed</span></span>  
  
## <a name="details"></a><span data-ttu-id="3c6f9-118">Сведения</span><span class="sxs-lookup"><span data-stu-id="3c6f9-118">Details</span></span>  
  
|<span data-ttu-id="3c6f9-119">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="3c6f9-119">Data Item Name</span></span>|<span data-ttu-id="3c6f9-120">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="3c6f9-120">Data Item Type</span></span>|<span data-ttu-id="3c6f9-121">Описание</span><span class="sxs-lookup"><span data-stu-id="3c6f9-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="3c6f9-122">RecordNumber</span><span class="sxs-lookup"><span data-stu-id="3c6f9-122">RecordNumber</span></span>|<span data-ttu-id="3c6f9-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="3c6f9-123">xs:string</span></span>|<span data-ttu-id="3c6f9-124">Номер записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="3c6f9-124">The tracking record number.</span></span>|  
|<span data-ttu-id="3c6f9-125">ProviderId</span><span class="sxs-lookup"><span data-stu-id="3c6f9-125">ProviderId</span></span>|<span data-ttu-id="3c6f9-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="3c6f9-126">xs:string</span></span>|<span data-ttu-id="3c6f9-127">Идентификатор поставщика трассировки событий Windows.</span><span class="sxs-lookup"><span data-stu-id="3c6f9-127">The ETW provider id.</span></span>|  
|<span data-ttu-id="3c6f9-128">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="3c6f9-128">AppDomain</span></span>|<span data-ttu-id="3c6f9-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="3c6f9-129">xs:string</span></span>|<span data-ttu-id="3c6f9-130">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="3c6f9-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
