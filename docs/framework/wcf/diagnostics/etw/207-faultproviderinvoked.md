---
title: 207 - FaultProviderInvoked
ms.date: 03/30/2017
ms.assetid: b730d903-01c2-4deb-85a4-da12f8a21fe4
ms.openlocfilehash: 71381c9eee6aed4792500c8558db88e239bf89f7
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96295175"
---
# <a name="207---faultproviderinvoked"></a><span data-ttu-id="84bbe-102">207 - FaultProviderInvoked</span><span class="sxs-lookup"><span data-stu-id="84bbe-102">207 - FaultProviderInvoked</span></span>

## <a name="properties"></a><span data-ttu-id="84bbe-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="84bbe-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="84bbe-104">ID</span><span class="sxs-lookup"><span data-stu-id="84bbe-104">ID</span></span>|<span data-ttu-id="84bbe-105">207</span><span class="sxs-lookup"><span data-stu-id="84bbe-105">207</span></span>|  
|<span data-ttu-id="84bbe-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="84bbe-106">Keywords</span></span>|<span data-ttu-id="84bbe-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="84bbe-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="84bbe-108">Level</span><span class="sxs-lookup"><span data-stu-id="84bbe-108">Level</span></span>|<span data-ttu-id="84bbe-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="84bbe-109">Information</span></span>|  
|<span data-ttu-id="84bbe-110">Канал</span><span class="sxs-lookup"><span data-stu-id="84bbe-110">Channel</span></span>|<span data-ttu-id="84bbe-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="84bbe-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="84bbe-112">Описание</span><span class="sxs-lookup"><span data-stu-id="84bbe-112">Description</span></span>  

 <span data-ttu-id="84bbe-113">Это событие создается после вызова `FaultProvider`.</span><span class="sxs-lookup"><span data-stu-id="84bbe-113">This event is emitted after a `FaultProvider` has been invoked.</span></span>  
  
## <a name="message"></a><span data-ttu-id="84bbe-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="84bbe-114">Message</span></span>  

 <span data-ttu-id="84bbe-115">Диспетчер вызвал FaultProvider типа «%1» с исключением типа «%2».</span><span class="sxs-lookup"><span data-stu-id="84bbe-115">The Dispatcher invoked a FaultProvider of type '%1' with an exception of type '%2'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="84bbe-116">Сведения</span><span class="sxs-lookup"><span data-stu-id="84bbe-116">Details</span></span>  
  
|<span data-ttu-id="84bbe-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="84bbe-117">Data Item Name</span></span>|<span data-ttu-id="84bbe-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="84bbe-118">Data Item Type</span></span>|<span data-ttu-id="84bbe-119">Описание</span><span class="sxs-lookup"><span data-stu-id="84bbe-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="84bbe-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="84bbe-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="84bbe-121">Имя CLR FullName типа вызванного инспектора `FaultProvider`.</span><span class="sxs-lookup"><span data-stu-id="84bbe-121">The CLR FullName of the type of the invoked `FaultProvider`.</span></span>|  
|<span data-ttu-id="84bbe-122">ExceptionTypeName</span><span class="sxs-lookup"><span data-stu-id="84bbe-122">ExceptionTypeName</span></span>|`xs:string`|<span data-ttu-id="84bbe-123">Имя CLR FullName исключения, обработанного `FaultProvider`.</span><span class="sxs-lookup"><span data-stu-id="84bbe-123">The CLR FullName of the exception that the `FaultProvider` has operated on.</span></span>|  
|<span data-ttu-id="84bbe-124">HostReference</span><span class="sxs-lookup"><span data-stu-id="84bbe-124">HostReference</span></span>|`xs:string`|<span data-ttu-id="84bbe-125">Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии.</span><span class="sxs-lookup"><span data-stu-id="84bbe-125">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="84bbe-126">Его формат определяется как "имя веб-сайта виртуальный путь к приложению&#124;виртуальный путь службы&#124;ServiceName".</span><span class="sxs-lookup"><span data-stu-id="84bbe-126">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="84bbe-127">Пример: "Default Web site/Калкулатораппликатион&#124;/Калкулаторсервице.СВК&#124;CalculatorService".</span><span class="sxs-lookup"><span data-stu-id="84bbe-127">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="84bbe-128">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="84bbe-128">AppDomain</span></span>|`xs:string`|<span data-ttu-id="84bbe-129">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="84bbe-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
