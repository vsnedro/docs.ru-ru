---
title: 39456 - TrackingRecordDropped
ms.date: 03/30/2017
ms.assetid: da13d5bc-1736-47a4-b3fd-064ca8040326
ms.openlocfilehash: d958b506e057bc0d59f954debdc9da6015bf5f1f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96273104"
---
# <a name="39456---trackingrecorddropped"></a><span data-ttu-id="0c44e-102">39456 - TrackingRecordDropped</span><span class="sxs-lookup"><span data-stu-id="0c44e-102">39456 - TrackingRecordDropped</span></span>

## <a name="properties"></a><span data-ttu-id="0c44e-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="0c44e-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0c44e-104">ID</span><span class="sxs-lookup"><span data-stu-id="0c44e-104">ID</span></span>|<span data-ttu-id="0c44e-105">39456</span><span class="sxs-lookup"><span data-stu-id="0c44e-105">39456</span></span>|  
|<span data-ttu-id="0c44e-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="0c44e-106">Keywords</span></span>|<span data-ttu-id="0c44e-107">WFTracking</span><span class="sxs-lookup"><span data-stu-id="0c44e-107">WFTracking</span></span>|  
|<span data-ttu-id="0c44e-108">Level</span><span class="sxs-lookup"><span data-stu-id="0c44e-108">Level</span></span>|<span data-ttu-id="0c44e-109">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="0c44e-109">Warning</span></span>|  
|<span data-ttu-id="0c44e-110">Канал</span><span class="sxs-lookup"><span data-stu-id="0c44e-110">Channel</span></span>|<span data-ttu-id="0c44e-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="0c44e-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="0c44e-112">Описание</span><span class="sxs-lookup"><span data-stu-id="0c44e-112">Description</span></span>  

 <span data-ttu-id="0c44e-113">Указывает, что запись отслеживания была удалена, поскольку ее размер превышает максимум, поддерживаемый поставщиком сеанса трассировки событий Windows.</span><span class="sxs-lookup"><span data-stu-id="0c44e-113">Indicates a tracking record has been dropped because its size exceeds maximum allowed by the ETW session provider.</span></span>  
  
## <a name="message"></a><span data-ttu-id="0c44e-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="0c44e-114">Message</span></span>  

 <span data-ttu-id="0c44e-115">Размер записи отслеживания %1 превышает максимально допустимое значение, разрешенное в сеансе трассировки событий Windows для поставщика %2</span><span class="sxs-lookup"><span data-stu-id="0c44e-115">Size of tracking record %1 exceeds maximum allowed by the ETW session for provider %2</span></span>  
  
## <a name="details"></a><span data-ttu-id="0c44e-116">Сведения</span><span class="sxs-lookup"><span data-stu-id="0c44e-116">Details</span></span>  
  
|<span data-ttu-id="0c44e-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="0c44e-117">Data Item Name</span></span>|<span data-ttu-id="0c44e-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="0c44e-118">Data Item Type</span></span>|<span data-ttu-id="0c44e-119">Описание</span><span class="sxs-lookup"><span data-stu-id="0c44e-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="0c44e-120">Исключение</span><span class="sxs-lookup"><span data-stu-id="0c44e-120">Exception</span></span>|<span data-ttu-id="0c44e-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="0c44e-121">xs:string</span></span>|<span data-ttu-id="0c44e-122">Сведения об исключении</span><span class="sxs-lookup"><span data-stu-id="0c44e-122">The exception details for the exception</span></span>|  
|<span data-ttu-id="0c44e-123">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="0c44e-123">AppDomain</span></span>|<span data-ttu-id="0c44e-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="0c44e-124">xs:string</span></span>|<span data-ttu-id="0c44e-125">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="0c44e-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
