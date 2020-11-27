---
title: 217 - ClientOperationPrepared
ms.date: 03/30/2017
ms.assetid: ad207f04-b038-4f33-95e9-27a361df8ecd
ms.openlocfilehash: e8aaf65bdff0718e932d07937e052541b7134f11
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96278886"
---
# <a name="217---clientoperationprepared"></a><span data-ttu-id="7d7e4-102">217 - ClientOperationPrepared</span><span class="sxs-lookup"><span data-stu-id="7d7e4-102">217 - ClientOperationPrepared</span></span>

## <a name="properties"></a><span data-ttu-id="7d7e4-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="7d7e4-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7d7e4-104">ID</span><span class="sxs-lookup"><span data-stu-id="7d7e4-104">ID</span></span>|<span data-ttu-id="7d7e4-105">217</span><span class="sxs-lookup"><span data-stu-id="7d7e4-105">217</span></span>|  
|<span data-ttu-id="7d7e4-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="7d7e4-106">Keywords</span></span>|<span data-ttu-id="7d7e4-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="7d7e4-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="7d7e4-108">Level</span><span class="sxs-lookup"><span data-stu-id="7d7e4-108">Level</span></span>|<span data-ttu-id="7d7e4-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="7d7e4-109">Information</span></span>|  
|<span data-ttu-id="7d7e4-110">Канал</span><span class="sxs-lookup"><span data-stu-id="7d7e4-110">Channel</span></span>|<span data-ttu-id="7d7e4-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="7d7e4-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="7d7e4-112">Описание</span><span class="sxs-lookup"><span data-stu-id="7d7e4-112">Description</span></span>  

 <span data-ttu-id="7d7e4-113">Это событие создается клиентом непосредственно перед отправкой операции службе.</span><span class="sxs-lookup"><span data-stu-id="7d7e4-113">This event is emitted by clients just before an operation is sent to the service.</span></span>  
  
## <a name="message"></a><span data-ttu-id="7d7e4-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="7d7e4-114">Message</span></span>  

 <span data-ttu-id="7d7e4-115">Клиент выполняет действие «%1», связанное с контрактом «%2».</span><span class="sxs-lookup"><span data-stu-id="7d7e4-115">The Client is executing Action '%1' associated with the '%2' contract.</span></span> <span data-ttu-id="7d7e4-116">Сообщение будет отправлено «%3».</span><span class="sxs-lookup"><span data-stu-id="7d7e4-116">The message will be sent to '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="7d7e4-117">Сведения</span><span class="sxs-lookup"><span data-stu-id="7d7e4-117">Details</span></span>  
  
|<span data-ttu-id="7d7e4-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="7d7e4-118">Data Item Name</span></span>|<span data-ttu-id="7d7e4-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="7d7e4-119">Data Item Type</span></span>|<span data-ttu-id="7d7e4-120">Описание</span><span class="sxs-lookup"><span data-stu-id="7d7e4-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="7d7e4-121">Действие</span><span class="sxs-lookup"><span data-stu-id="7d7e4-121">Action</span></span>|`xs:string`|<span data-ttu-id="7d7e4-122">Заголовок действия SOAP исходящего сообщения.</span><span class="sxs-lookup"><span data-stu-id="7d7e4-122">The SOAP action header of the outgoing message.</span></span>|  
|<span data-ttu-id="7d7e4-123">Contract Name</span><span class="sxs-lookup"><span data-stu-id="7d7e4-123">Contract Name</span></span>|`xs:string`|<span data-ttu-id="7d7e4-124">Имя контракта.</span><span class="sxs-lookup"><span data-stu-id="7d7e4-124">The name of the contract.</span></span> <span data-ttu-id="7d7e4-125">Пример: ICalculator.</span><span class="sxs-lookup"><span data-stu-id="7d7e4-125">Example: ICalculator.</span></span>|  
|<span data-ttu-id="7d7e4-126">Назначение</span><span class="sxs-lookup"><span data-stu-id="7d7e4-126">Destination</span></span>|`xs:string`|<span data-ttu-id="7d7e4-127">Адрес конечной точки службы, которой отправляется сообщение.</span><span class="sxs-lookup"><span data-stu-id="7d7e4-127">The address of the service endpoint that the message is sent to.</span></span>|  
|<span data-ttu-id="7d7e4-128">HostReference</span><span class="sxs-lookup"><span data-stu-id="7d7e4-128">HostReference</span></span>|`xs:string`|<span data-ttu-id="7d7e4-129">Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии.</span><span class="sxs-lookup"><span data-stu-id="7d7e4-129">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="7d7e4-130">Его формат определяется как "имя веб-сайта виртуальный путь к приложению&#124;виртуальный путь службы&#124;ServiceName".</span><span class="sxs-lookup"><span data-stu-id="7d7e4-130">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="7d7e4-131">Пример: "Default Web site/Калкулатораппликатион&#124;/Калкулаторсервице.СВК&#124;CalculatorService".</span><span class="sxs-lookup"><span data-stu-id="7d7e4-131">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="7d7e4-132">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="7d7e4-132">AppDomain</span></span>|`xs:string`|<span data-ttu-id="7d7e4-133">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="7d7e4-133">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
