---
title: 211 - ParameterInspectorAfterCallInvoked
ms.date: 03/30/2017
ms.assetid: c0e21297-10b8-4456-a0e1-e019145cd5ac
ms.openlocfilehash: 7027b6557520a9ccb587f8d383d3598571da5838
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96279068"
---
# <a name="211---parameterinspectoraftercallinvoked"></a><span data-ttu-id="7a59a-102">211 - ParameterInspectorAfterCallInvoked</span><span class="sxs-lookup"><span data-stu-id="7a59a-102">211 - ParameterInspectorAfterCallInvoked</span></span>

## <a name="properties"></a><span data-ttu-id="7a59a-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="7a59a-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7a59a-104">ID</span><span class="sxs-lookup"><span data-stu-id="7a59a-104">ID</span></span>|<span data-ttu-id="7a59a-105">211</span><span class="sxs-lookup"><span data-stu-id="7a59a-105">211</span></span>|  
|<span data-ttu-id="7a59a-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="7a59a-106">Keywords</span></span>|<span data-ttu-id="7a59a-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="7a59a-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="7a59a-108">Level</span><span class="sxs-lookup"><span data-stu-id="7a59a-108">Level</span></span>|<span data-ttu-id="7a59a-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="7a59a-109">Information</span></span>|  
|<span data-ttu-id="7a59a-110">Канал</span><span class="sxs-lookup"><span data-stu-id="7a59a-110">Channel</span></span>|<span data-ttu-id="7a59a-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="7a59a-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="7a59a-112">Описание</span><span class="sxs-lookup"><span data-stu-id="7a59a-112">Description</span></span>  

 <span data-ttu-id="7a59a-113">Это событие создается после того, как модель службы вызывает метод `AfterCall` для `ParameterInspector`.</span><span class="sxs-lookup"><span data-stu-id="7a59a-113">This event is emitted after the Service Model has invoked the `AfterCall` method on a `ParameterInspector`.</span></span>  
  
## <a name="message"></a><span data-ttu-id="7a59a-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="7a59a-114">Message</span></span>  

 <span data-ttu-id="7a59a-115">Диспетчер вызвал AfterCall относительно ParameterInspector типа «%1».</span><span class="sxs-lookup"><span data-stu-id="7a59a-115">The Dispatcher invoked 'AfterCall' on a ParameterInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="7a59a-116">Сведения</span><span class="sxs-lookup"><span data-stu-id="7a59a-116">Details</span></span>  
  
|<span data-ttu-id="7a59a-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="7a59a-117">Data Item Name</span></span>|<span data-ttu-id="7a59a-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="7a59a-118">Data Item Type</span></span>|<span data-ttu-id="7a59a-119">Описание</span><span class="sxs-lookup"><span data-stu-id="7a59a-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="7a59a-120">Имя типа</span><span class="sxs-lookup"><span data-stu-id="7a59a-120">Type Name</span></span>|`xs:string`|<span data-ttu-id="7a59a-121">Имя CLR FullName типа вызванного инспектора `ParameterInspector`.</span><span class="sxs-lookup"><span data-stu-id="7a59a-121">The CLR FullName of the type of the invoked `ParameterInspector`.</span></span>|  
|<span data-ttu-id="7a59a-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="7a59a-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="7a59a-123">Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии.</span><span class="sxs-lookup"><span data-stu-id="7a59a-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="7a59a-124">Его формат определяется как "имя веб-сайта виртуальный путь к приложению&#124;виртуальный путь службы&#124;ServiceName".</span><span class="sxs-lookup"><span data-stu-id="7a59a-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="7a59a-125">Пример: "Default Web site/Калкулатораппликатион&#124;/Калкулаторсервице.СВК&#124;CalculatorService".</span><span class="sxs-lookup"><span data-stu-id="7a59a-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="7a59a-126">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="7a59a-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="7a59a-127">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="7a59a-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
