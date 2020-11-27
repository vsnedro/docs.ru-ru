---
title: 205 - OperationInvoked
ms.date: 03/30/2017
ms.assetid: 9c8d6c90-dfa5-4ae0-a589-96679a8fb3ba
ms.openlocfilehash: c36294a4a430c3e372e8213246e85dba45ce03c8
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96286023"
---
# <a name="205---operationinvoked"></a><span data-ttu-id="88d56-102">205 - OperationInvoked</span><span class="sxs-lookup"><span data-stu-id="88d56-102">205 - OperationInvoked</span></span>

## <a name="properties"></a><span data-ttu-id="88d56-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="88d56-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="88d56-104">ID</span><span class="sxs-lookup"><span data-stu-id="88d56-104">ID</span></span>|<span data-ttu-id="88d56-105">205</span><span class="sxs-lookup"><span data-stu-id="88d56-105">205</span></span>|  
|<span data-ttu-id="88d56-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="88d56-106">Keywords</span></span>|<span data-ttu-id="88d56-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="88d56-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="88d56-108">Level</span><span class="sxs-lookup"><span data-stu-id="88d56-108">Level</span></span>|<span data-ttu-id="88d56-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="88d56-109">Information</span></span>|  
|<span data-ttu-id="88d56-110">Канал</span><span class="sxs-lookup"><span data-stu-id="88d56-110">Channel</span></span>|<span data-ttu-id="88d56-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="88d56-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="88d56-112">Описание</span><span class="sxs-lookup"><span data-stu-id="88d56-112">Description</span></span>  

 <span data-ttu-id="88d56-113">Это событие создается непосредственно перед тем, как `OperationInvoker` по умолчанию модели службы начнет вызов метода.</span><span class="sxs-lookup"><span data-stu-id="88d56-113">This event is emitted just before the Service Model's default `OperationInvoker` begins a call to a method.</span></span>  
  
## <a name="message"></a><span data-ttu-id="88d56-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="88d56-114">Message</span></span>  

 <span data-ttu-id="88d56-115">OperationInvoker вызвал метод «%1».</span><span class="sxs-lookup"><span data-stu-id="88d56-115">An OperationInvoker invoked the '%1' method.</span></span> <span data-ttu-id="88d56-116">Сведения о вызывающем объекте: «%2».</span><span class="sxs-lookup"><span data-stu-id="88d56-116">Caller information: '%2'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="88d56-117">Сведения</span><span class="sxs-lookup"><span data-stu-id="88d56-117">Details</span></span>  
  
|<span data-ttu-id="88d56-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="88d56-118">Data Item Name</span></span>|<span data-ttu-id="88d56-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="88d56-119">Data Item Type</span></span>|<span data-ttu-id="88d56-120">Описание</span><span class="sxs-lookup"><span data-stu-id="88d56-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="88d56-121">Имя метода</span><span class="sxs-lookup"><span data-stu-id="88d56-121">Method Name</span></span>|`xs:string`|<span data-ttu-id="88d56-122">Имя CLR метода, который был вызван `OperationInvoker`.</span><span class="sxs-lookup"><span data-stu-id="88d56-122">The CLR name of the method that was invoked by the `OperationInvoker`.</span></span>|  
|<span data-ttu-id="88d56-123">Сведения о вызывающем</span><span class="sxs-lookup"><span data-stu-id="88d56-123">Caller Information</span></span>|`xs:string`|<span data-ttu-id="88d56-124">IP-адрес и номер порта клиента в формате «IPAddress:PortNumber».</span><span class="sxs-lookup"><span data-stu-id="88d56-124">The IP address and port number of the client in the format 'IPAddress:PortNumber'.</span></span> <span data-ttu-id="88d56-125">Эти два значения извлекаются из свойства сообщения «System.ServiceModel.Channels.RemoteEndpointMessageProperty» в контексте операции.</span><span class="sxs-lookup"><span data-stu-id="88d56-125">The two values are retrieved from the 'System.ServiceModel.Channels.RemoteEndpointMessageProperty' message property within the operation context.</span></span> <span data-ttu-id="88d56-126">Следует отметить, что для привязок, отличных от TCP, это значение `null`.</span><span class="sxs-lookup"><span data-stu-id="88d56-126">Note that for non-TCP bindings this value `null`.</span></span>|  
|<span data-ttu-id="88d56-127">HostReference</span><span class="sxs-lookup"><span data-stu-id="88d56-127">HostReference</span></span>|`xs:string`|<span data-ttu-id="88d56-128">Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии.</span><span class="sxs-lookup"><span data-stu-id="88d56-128">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="88d56-129">Его формат определяется как "имя веб-сайта виртуальный путь к приложению&#124;виртуальный путь службы&#124;ServiceName".</span><span class="sxs-lookup"><span data-stu-id="88d56-129">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="88d56-130">Пример: "Default Web site/Калкулатораппликатион&#124;/Калкулаторсервице.СВК&#124;CalculatorService".</span><span class="sxs-lookup"><span data-stu-id="88d56-130">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="88d56-131">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="88d56-131">AppDomain</span></span>|`xs:string`|<span data-ttu-id="88d56-132">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="88d56-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
