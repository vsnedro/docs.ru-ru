---
title: 206 - ErrorHandlerInvoked
ms.date: 03/30/2017
ms.assetid: 97340f4d-4e09-4e42-a17a-982b3868dbcf
ms.openlocfilehash: 99415733624752217d32f6f026a419b2b32bfa7b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96244617"
---
# <a name="206---errorhandlerinvoked"></a><span data-ttu-id="ff72f-102">206 - ErrorHandlerInvoked</span><span class="sxs-lookup"><span data-stu-id="ff72f-102">206 - ErrorHandlerInvoked</span></span>

## <a name="properties"></a><span data-ttu-id="ff72f-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="ff72f-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ff72f-104">ID</span><span class="sxs-lookup"><span data-stu-id="ff72f-104">ID</span></span>|<span data-ttu-id="ff72f-105">206</span><span class="sxs-lookup"><span data-stu-id="ff72f-105">206</span></span>|  
|<span data-ttu-id="ff72f-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="ff72f-106">Keywords</span></span>|<span data-ttu-id="ff72f-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="ff72f-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="ff72f-108">Level</span><span class="sxs-lookup"><span data-stu-id="ff72f-108">Level</span></span>|<span data-ttu-id="ff72f-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="ff72f-109">Information</span></span>|  
|<span data-ttu-id="ff72f-110">Канал</span><span class="sxs-lookup"><span data-stu-id="ff72f-110">Channel</span></span>|<span data-ttu-id="ff72f-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="ff72f-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="ff72f-112">Описание</span><span class="sxs-lookup"><span data-stu-id="ff72f-112">Description</span></span>  

 <span data-ttu-id="ff72f-113">Это событие создается после того, как обработчик `ErrorHandler` начинает обрабатывать исключение, возникшее в операции службы.</span><span class="sxs-lookup"><span data-stu-id="ff72f-113">This event is emitted after an `ErrorHandler` has had an opportunity to handle an exception that occurred in a service operation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="ff72f-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="ff72f-114">Message</span></span>  

 <span data-ttu-id="ff72f-115">Диспетчер вызвал ErrorHandler типа "%1" с исключением типа "%3".</span><span class="sxs-lookup"><span data-stu-id="ff72f-115">The Dispatcher invoked an ErrorHandler of type '%1' with an exception of type '%3'.</span></span> <span data-ttu-id="ff72f-116">ErrorHandled == '%2'.</span><span class="sxs-lookup"><span data-stu-id="ff72f-116">ErrorHandled == '%2'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="ff72f-117">Сведения</span><span class="sxs-lookup"><span data-stu-id="ff72f-117">Details</span></span>  
  
|<span data-ttu-id="ff72f-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="ff72f-118">Data Item Name</span></span>|<span data-ttu-id="ff72f-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="ff72f-119">Data Item Type</span></span>|<span data-ttu-id="ff72f-120">Описание</span><span class="sxs-lookup"><span data-stu-id="ff72f-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="ff72f-121">TypeName</span><span class="sxs-lookup"><span data-stu-id="ff72f-121">TypeName</span></span>|`xs:string`|<span data-ttu-id="ff72f-122">Имя CLR FullName типа вызванного инспектора `ErrorHandler`.</span><span class="sxs-lookup"><span data-stu-id="ff72f-122">The CLR FullName of the type of the invoked `ErrorHandler`.</span></span>|  
|<span data-ttu-id="ff72f-123">Обработанные</span><span class="sxs-lookup"><span data-stu-id="ff72f-123">Handled</span></span>|`xs:unsignedByte`|<span data-ttu-id="ff72f-124">Значение `true`, если обработчик ошибок обработал ошибку, в противном случае значение `false`.</span><span class="sxs-lookup"><span data-stu-id="ff72f-124">`true` if the error handler handled the error, otherwise `false`.</span></span>|  
|<span data-ttu-id="ff72f-125">ExceptionTypeName</span><span class="sxs-lookup"><span data-stu-id="ff72f-125">ExceptionTypeName</span></span>|`xs:string`|<span data-ttu-id="ff72f-126">Имя CLR FullName обрабатываемого исключения.</span><span class="sxs-lookup"><span data-stu-id="ff72f-126">The CLR FullName of the exception that was being handled.</span></span>|  
|<span data-ttu-id="ff72f-127">HostReference</span><span class="sxs-lookup"><span data-stu-id="ff72f-127">HostReference</span></span>|`xs:string`|<span data-ttu-id="ff72f-128">Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии.</span><span class="sxs-lookup"><span data-stu-id="ff72f-128">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="ff72f-129">Его формат определяется как "имя веб-сайта виртуальный путь к приложению&#124;виртуальный путь службы&#124;ServiceName".</span><span class="sxs-lookup"><span data-stu-id="ff72f-129">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="ff72f-130">Пример: "Default Web site/Калкулатораппликатион&#124;/Калкулаторсервице.СВК&#124;CalculatorService".</span><span class="sxs-lookup"><span data-stu-id="ff72f-130">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="ff72f-131">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="ff72f-131">AppDomain</span></span>|`xs:string`|<span data-ttu-id="ff72f-132">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="ff72f-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
