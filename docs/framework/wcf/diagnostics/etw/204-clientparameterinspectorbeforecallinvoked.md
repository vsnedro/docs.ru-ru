---
title: 204 - ClientParameterInspectorBeforeCallInvoked
ms.date: 03/30/2017
ms.assetid: 8253555a-9002-4565-8ede-33d7a33a895f
ms.openlocfilehash: a7db8c9fa87518c59969f3089ff033fa8c912577
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275792"
---
# <a name="204---clientparameterinspectorbeforecallinvoked"></a><span data-ttu-id="dd2d1-102">204 - ClientParameterInspectorBeforeCallInvoked</span><span class="sxs-lookup"><span data-stu-id="dd2d1-102">204 - ClientParameterInspectorBeforeCallInvoked</span></span>

## <a name="properties"></a><span data-ttu-id="dd2d1-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="dd2d1-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="dd2d1-104">ID</span><span class="sxs-lookup"><span data-stu-id="dd2d1-104">ID</span></span>|<span data-ttu-id="dd2d1-105">204</span><span class="sxs-lookup"><span data-stu-id="dd2d1-105">204</span></span>|  
|<span data-ttu-id="dd2d1-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="dd2d1-106">Keywords</span></span>|<span data-ttu-id="dd2d1-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="dd2d1-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="dd2d1-108">Level</span><span class="sxs-lookup"><span data-stu-id="dd2d1-108">Level</span></span>|<span data-ttu-id="dd2d1-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="dd2d1-109">Information</span></span>|  
|<span data-ttu-id="dd2d1-110">Канал</span><span class="sxs-lookup"><span data-stu-id="dd2d1-110">Channel</span></span>|<span data-ttu-id="dd2d1-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="dd2d1-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="dd2d1-112">Описание</span><span class="sxs-lookup"><span data-stu-id="dd2d1-112">Description</span></span>  

 <span data-ttu-id="dd2d1-113">Это событие создается после того, как модель службы вызывает метод `BeforeCall` для инспектора параметров клиента.</span><span class="sxs-lookup"><span data-stu-id="dd2d1-113">This event is emitted after the Service Model has invoked the `BeforeCall` method on a client parameter inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="dd2d1-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="dd2d1-114">Message</span></span>  

 <span data-ttu-id="dd2d1-115">Диспетчер вызвал BeforeCall для ClientParameterInspector типа «%1».</span><span class="sxs-lookup"><span data-stu-id="dd2d1-115">The Dispatcher invoked 'BeforeCall' on a ClientParameterInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="dd2d1-116">Сведения</span><span class="sxs-lookup"><span data-stu-id="dd2d1-116">Details</span></span>  
  
|<span data-ttu-id="dd2d1-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="dd2d1-117">Data Item Name</span></span>|<span data-ttu-id="dd2d1-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="dd2d1-118">Data Item Type</span></span>|<span data-ttu-id="dd2d1-119">Описание</span><span class="sxs-lookup"><span data-stu-id="dd2d1-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="dd2d1-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="dd2d1-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="dd2d1-121">Имя CLR FullName типа вызванного инспектора.</span><span class="sxs-lookup"><span data-stu-id="dd2d1-121">The CLR FullName of the invoked inspector's type.</span></span>|  
|<span data-ttu-id="dd2d1-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="dd2d1-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="dd2d1-123">Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии.</span><span class="sxs-lookup"><span data-stu-id="dd2d1-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="dd2d1-124">Его формат определяется как "имя веб-сайта виртуальный путь к приложению&#124;виртуальный путь службы&#124;ServiceName".</span><span class="sxs-lookup"><span data-stu-id="dd2d1-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="dd2d1-125">Пример: "Default Web site/Калкулатораппликатион&#124;/Калкулаторсервице.СВК&#124;CalculatorService".</span><span class="sxs-lookup"><span data-stu-id="dd2d1-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="dd2d1-126">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="dd2d1-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="dd2d1-127">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="dd2d1-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
