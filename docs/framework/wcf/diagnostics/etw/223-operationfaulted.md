---
title: 223 - OperationFaulted
ms.date: 03/30/2017
ms.assetid: 2f7d89d7-3a6a-40fe-9610-5424eb6bbf61
ms.openlocfilehash: 310e91320d27dd9817302fc14ef088d180152b73
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96263078"
---
# <a name="223---operationfaulted"></a><span data-ttu-id="9bbe6-102">223 - OperationFaulted</span><span class="sxs-lookup"><span data-stu-id="9bbe6-102">223 - OperationFaulted</span></span>

## <a name="properties"></a><span data-ttu-id="9bbe6-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="9bbe6-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9bbe6-104">ID</span><span class="sxs-lookup"><span data-stu-id="9bbe6-104">ID</span></span>|<span data-ttu-id="9bbe6-105">223</span><span class="sxs-lookup"><span data-stu-id="9bbe6-105">223</span></span>|  
|<span data-ttu-id="9bbe6-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="9bbe6-106">Keywords</span></span>|<span data-ttu-id="9bbe6-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="9bbe6-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="9bbe6-108">Level</span><span class="sxs-lookup"><span data-stu-id="9bbe6-108">Level</span></span>|<span data-ttu-id="9bbe6-109">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="9bbe6-109">Warning</span></span>|  
|<span data-ttu-id="9bbe6-110">Канал</span><span class="sxs-lookup"><span data-stu-id="9bbe6-110">Channel</span></span>|<span data-ttu-id="9bbe6-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="9bbe6-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="9bbe6-112">Описание</span><span class="sxs-lookup"><span data-stu-id="9bbe6-112">Description</span></span>  

 <span data-ttu-id="9bbe6-113">Это событие вызывается в том случае, если при вызове `OperationInvoker` модели службы по умолчанию обнаружено исключение, производное от `FaultException`.</span><span class="sxs-lookup"><span data-stu-id="9bbe6-113">This event is emitted when the Service Model's default `OperationInvoker` has encountered an exception deriving from `FaultException` while invoking its method.</span></span>  
  
## <a name="message"></a><span data-ttu-id="9bbe6-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="9bbe6-114">Message</span></span>  

 <span data-ttu-id="9bbe6-115">Метод «%1» вызывал исключение FaultException после того, как был вызван OperationInvoker.</span><span class="sxs-lookup"><span data-stu-id="9bbe6-115">The '%1' method threw a FaultException when invoked by the OperationInvoker.</span></span> <span data-ttu-id="9bbe6-116">Длительность вызова метода составила «%2» мс.</span><span class="sxs-lookup"><span data-stu-id="9bbe6-116">The method call duration was '%2' ms.</span></span>  
  
## <a name="details"></a><span data-ttu-id="9bbe6-117">Сведения</span><span class="sxs-lookup"><span data-stu-id="9bbe6-117">Details</span></span>  
  
|<span data-ttu-id="9bbe6-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="9bbe6-118">Data Item Name</span></span>|<span data-ttu-id="9bbe6-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="9bbe6-119">Data Item Type</span></span>|<span data-ttu-id="9bbe6-120">Описание</span><span class="sxs-lookup"><span data-stu-id="9bbe6-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="9bbe6-121">MethodName</span><span class="sxs-lookup"><span data-stu-id="9bbe6-121">MethodName</span></span>|`xs:string`|<span data-ttu-id="9bbe6-122">Имя CLR метода, который был вызван `OperationInvoker`.</span><span class="sxs-lookup"><span data-stu-id="9bbe6-122">The CLR name of the method that was invoked by the `OperationInvoker`.</span></span>|  
|<span data-ttu-id="9bbe6-123">Длительность</span><span class="sxs-lookup"><span data-stu-id="9bbe6-123">Duration</span></span>|`xs:long`|<span data-ttu-id="9bbe6-124">Время в миллисекундах, которое потребовалось `OperationInvoker`, чтобы вызвать метод.</span><span class="sxs-lookup"><span data-stu-id="9bbe6-124">The time, in milliseconds, that it took the `OperationInvoker` to invoke the method.</span></span>|  
|<span data-ttu-id="9bbe6-125">HostReference</span><span class="sxs-lookup"><span data-stu-id="9bbe6-125">HostReference</span></span>|`xs:string`|<span data-ttu-id="9bbe6-126">Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии.</span><span class="sxs-lookup"><span data-stu-id="9bbe6-126">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="9bbe6-127">Его формат определяется как "имя веб-сайта виртуальный путь к приложению&#124;виртуальный путь службы&#124;ServiceName".</span><span class="sxs-lookup"><span data-stu-id="9bbe6-127">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="9bbe6-128">Пример: "Default Web site/Калкулатораппликатион&#124;/Калкулаторсервице.СВК&#124;CalculatorService".</span><span class="sxs-lookup"><span data-stu-id="9bbe6-128">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="9bbe6-129">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="9bbe6-129">AppDomain</span></span>|`xs:string`|<span data-ttu-id="9bbe6-130">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="9bbe6-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
