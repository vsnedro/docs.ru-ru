---
title: 219 - ServiceException
ms.date: 03/30/2017
ms.assetid: 81e2efac-39aa-4ed2-85a9-97eb8793b844
ms.openlocfilehash: 832ced406b6079fad8f4b9bea512a6d390bdcc0f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96241945"
---
# <a name="219---serviceexception"></a><span data-ttu-id="c13f2-102">219 - ServiceException</span><span class="sxs-lookup"><span data-stu-id="c13f2-102">219 - ServiceException</span></span>

## <a name="properties"></a><span data-ttu-id="c13f2-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="c13f2-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c13f2-104">ID</span><span class="sxs-lookup"><span data-stu-id="c13f2-104">ID</span></span>|<span data-ttu-id="c13f2-105">219</span><span class="sxs-lookup"><span data-stu-id="c13f2-105">219</span></span>|  
|<span data-ttu-id="c13f2-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="c13f2-106">Keywords</span></span>|<span data-ttu-id="c13f2-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="c13f2-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="c13f2-108">Level</span><span class="sxs-lookup"><span data-stu-id="c13f2-108">Level</span></span>|<span data-ttu-id="c13f2-109">Ошибка</span><span class="sxs-lookup"><span data-stu-id="c13f2-109">Error</span></span>|  
|<span data-ttu-id="c13f2-110">Канал</span><span class="sxs-lookup"><span data-stu-id="c13f2-110">Channel</span></span>|<span data-ttu-id="c13f2-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="c13f2-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="c13f2-112">Описание</span><span class="sxs-lookup"><span data-stu-id="c13f2-112">Description</span></span>  

 <span data-ttu-id="c13f2-113">Это событие создается при обнаружении службой WCF необработанного исключения.</span><span class="sxs-lookup"><span data-stu-id="c13f2-113">This event is emitted when a WCF service encounters an unhandled exception.</span></span> <span data-ttu-id="c13f2-114">В число необработанных входят исключения, возникшие во время активации, обработки сообщений и выполнения пользовательского кода.</span><span class="sxs-lookup"><span data-stu-id="c13f2-114">This includes unhandled exceptions during activation, during message processing, and in user code.</span></span>  
  
## <a name="message"></a><span data-ttu-id="c13f2-115">Сообщение</span><span class="sxs-lookup"><span data-stu-id="c13f2-115">Message</span></span>  

 <span data-ttu-id="c13f2-116">Во время обработки сообщения возникло необработанное исключение типа «%2».</span><span class="sxs-lookup"><span data-stu-id="c13f2-116">There was an unhandled exception of type '%2' during message processing.</span></span> <span data-ttu-id="c13f2-117">Полное исключение ToString: %1.</span><span class="sxs-lookup"><span data-stu-id="c13f2-117">Full Exception ToString: %1.</span></span>  
  
## <a name="details"></a><span data-ttu-id="c13f2-118">Сведения</span><span class="sxs-lookup"><span data-stu-id="c13f2-118">Details</span></span>  
  
|<span data-ttu-id="c13f2-119">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="c13f2-119">Data Item Name</span></span>|<span data-ttu-id="c13f2-120">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="c13f2-120">Data Item Type</span></span>|<span data-ttu-id="c13f2-121">Описание</span><span class="sxs-lookup"><span data-stu-id="c13f2-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="c13f2-122">ExceptionToString</span><span class="sxs-lookup"><span data-stu-id="c13f2-122">ExceptionToString</span></span>|`xs:string`|<span data-ttu-id="c13f2-123">Результат вызова метода `ToString`() относительно исключения CLR.</span><span class="sxs-lookup"><span data-stu-id="c13f2-123">The result of calling `ToString`() on the CLR exception.</span></span>|  
|<span data-ttu-id="c13f2-124">ExceptionTypeName</span><span class="sxs-lookup"><span data-stu-id="c13f2-124">ExceptionTypeName</span></span>|`xs:string`|<span data-ttu-id="c13f2-125">Имя CLR FullName типа исключения.</span><span class="sxs-lookup"><span data-stu-id="c13f2-125">The CLR FullName of the exception's type.</span></span>|  
|<span data-ttu-id="c13f2-126">HostReference</span><span class="sxs-lookup"><span data-stu-id="c13f2-126">HostReference</span></span>|`xs:string`|<span data-ttu-id="c13f2-127">Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии.</span><span class="sxs-lookup"><span data-stu-id="c13f2-127">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="c13f2-128">Его формат определяется как "имя веб-сайта виртуальный путь к приложению&#124;виртуальный путь службы&#124;ServiceName".</span><span class="sxs-lookup"><span data-stu-id="c13f2-128">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="c13f2-129">Пример: "Default Web site/Калкулатораппликатион&#124;/Калкулаторсервице.СВК&#124;CalculatorService".</span><span class="sxs-lookup"><span data-stu-id="c13f2-129">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="c13f2-130">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="c13f2-130">AppDomain</span></span>|`xs:string`|<span data-ttu-id="c13f2-131">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="c13f2-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
