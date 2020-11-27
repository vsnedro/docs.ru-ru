---
title: 216 - MessageSentByTransport
ms.date: 03/30/2017
ms.assetid: 150c3167-4154-4225-8d94-57cc94341233
ms.openlocfilehash: b3e9e1a48951ad5a2e5e7820dc1828c20e310635
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96278912"
---
# <a name="216---messagesentbytransport"></a><span data-ttu-id="ce256-102">216 - MessageSentByTransport</span><span class="sxs-lookup"><span data-stu-id="ce256-102">216 - MessageSentByTransport</span></span>

## <a name="properties"></a><span data-ttu-id="ce256-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="ce256-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ce256-104">ID</span><span class="sxs-lookup"><span data-stu-id="ce256-104">ID</span></span>|<span data-ttu-id="ce256-105">216</span><span class="sxs-lookup"><span data-stu-id="ce256-105">216</span></span>|  
|<span data-ttu-id="ce256-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="ce256-106">Keywords</span></span>|<span data-ttu-id="ce256-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="ce256-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="ce256-108">Level</span><span class="sxs-lookup"><span data-stu-id="ce256-108">Level</span></span>|<span data-ttu-id="ce256-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="ce256-109">Information</span></span>|  
|<span data-ttu-id="ce256-110">Канал</span><span class="sxs-lookup"><span data-stu-id="ce256-110">Channel</span></span>|<span data-ttu-id="ce256-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="ce256-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="ce256-112">Описание</span><span class="sxs-lookup"><span data-stu-id="ce256-112">Description</span></span>  

 <span data-ttu-id="ce256-113">Это событие возникает при отправке сообщения транспортом на основе TCP.</span><span class="sxs-lookup"><span data-stu-id="ce256-113">This event occurs when a TCP-based transport sends a message.</span></span> <span data-ttu-id="ce256-114">Обратите внимание, что в рамках одной операции между клиентом и службой может быть передано несколько сообщений уровня транспорта.</span><span class="sxs-lookup"><span data-stu-id="ce256-114">Note that at the transport level multiple messages can be exchanged between clients and services for a single operation.</span></span> <span data-ttu-id="ce256-115">Это может быть вызвано особенностями инфраструктуры (и требования безопасности - хороший пример).</span><span class="sxs-lookup"><span data-stu-id="ce256-115">This may be due to infrastructure behavior, security being a good example.</span></span> <span data-ttu-id="ce256-116">Таким образом, количество выдаваемых событий **мессажесентбитранспорт** зависит от привязки службы и ее конфигурации.</span><span class="sxs-lookup"><span data-stu-id="ce256-116">Therefore, the number of **MessageSentByTransport** events that are emitted vary based on your service's binding and its configuration.</span></span>  
  
## <a name="message"></a><span data-ttu-id="ce256-117">Сообщение</span><span class="sxs-lookup"><span data-stu-id="ce256-117">Message</span></span>  

 <span data-ttu-id="ce256-118">Транспорт отправил сообщение «%1».</span><span class="sxs-lookup"><span data-stu-id="ce256-118">The transport sent a message to '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="ce256-119">Сведения</span><span class="sxs-lookup"><span data-stu-id="ce256-119">Details</span></span>  
  
|<span data-ttu-id="ce256-120">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="ce256-120">Data Item Name</span></span>|<span data-ttu-id="ce256-121">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="ce256-121">Data Item Type</span></span>|<span data-ttu-id="ce256-122">Описание</span><span class="sxs-lookup"><span data-stu-id="ce256-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="ce256-123">DestinationAddress</span><span class="sxs-lookup"><span data-stu-id="ce256-123">DestinationAddress</span></span>|`xs:string`|<span data-ttu-id="ce256-124">Адрес, на который было отправлено сообщение запроса.</span><span class="sxs-lookup"><span data-stu-id="ce256-124">The address that the request message was sent to.</span></span>|  
|<span data-ttu-id="ce256-125">HostReference</span><span class="sxs-lookup"><span data-stu-id="ce256-125">HostReference</span></span>|<span data-ttu-id="ce256-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="ce256-126">xs:string</span></span>|<span data-ttu-id="ce256-127">Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии.</span><span class="sxs-lookup"><span data-stu-id="ce256-127">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="ce256-128">Его формат определяется как "имя веб-сайта виртуальный путь к приложению&#124;виртуальный путь службы&#124;ServiceName".</span><span class="sxs-lookup"><span data-stu-id="ce256-128">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="ce256-129">Пример: "Default Web site/Калкулатораппликатион&#124;/Калкулаторсервице.СВК&#124;CalculatorService".</span><span class="sxs-lookup"><span data-stu-id="ce256-129">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="ce256-130">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="ce256-130">AppDomain</span></span>|`xs:string`|<span data-ttu-id="ce256-131">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="ce256-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
