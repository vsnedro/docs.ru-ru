---
title: 212 - ParameterInspectorBeforeCallInvoked
ms.date: 03/30/2017
ms.assetid: 063fc8d2-ceac-4c18-8368-de84f2c78035
ms.openlocfilehash: 28c2aca4555d2e4ff498e450deae55ad6a87743c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96279042"
---
# <a name="212---parameterinspectorbeforecallinvoked"></a><span data-ttu-id="1d108-102">212 - ParameterInspectorBeforeCallInvoked</span><span class="sxs-lookup"><span data-stu-id="1d108-102">212 - ParameterInspectorBeforeCallInvoked</span></span>

## <a name="properties"></a><span data-ttu-id="1d108-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="1d108-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1d108-104">ID</span><span class="sxs-lookup"><span data-stu-id="1d108-104">ID</span></span>|<span data-ttu-id="1d108-105">212</span><span class="sxs-lookup"><span data-stu-id="1d108-105">212</span></span>|  
|<span data-ttu-id="1d108-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="1d108-106">Keywords</span></span>|<span data-ttu-id="1d108-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="1d108-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="1d108-108">Level</span><span class="sxs-lookup"><span data-stu-id="1d108-108">Level</span></span>|<span data-ttu-id="1d108-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="1d108-109">Information</span></span>|  
|<span data-ttu-id="1d108-110">Канал</span><span class="sxs-lookup"><span data-stu-id="1d108-110">Channel</span></span>|<span data-ttu-id="1d108-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="1d108-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="1d108-112">Описание</span><span class="sxs-lookup"><span data-stu-id="1d108-112">Description</span></span>  

 <span data-ttu-id="1d108-113">Это событие создается после того, как модель службы вызывает метод `BeforeCall` для `ParameterInspector`.</span><span class="sxs-lookup"><span data-stu-id="1d108-113">This event is emitted after the Service Model has invoked the `BeforeCall` method on a `ParameterInspector`.</span></span>  
  
## <a name="message"></a><span data-ttu-id="1d108-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="1d108-114">Message</span></span>  

 <span data-ttu-id="1d108-115">Диспетчер вызвал BeforeCall для ParameterInspector типа «%1».</span><span class="sxs-lookup"><span data-stu-id="1d108-115">The Dispatcher invoked 'BeforeCall' on a ParameterInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="1d108-116">Сведения</span><span class="sxs-lookup"><span data-stu-id="1d108-116">Details</span></span>  
  
|<span data-ttu-id="1d108-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="1d108-117">Data Item Name</span></span>|<span data-ttu-id="1d108-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="1d108-118">Data Item Type</span></span>|<span data-ttu-id="1d108-119">Описание</span><span class="sxs-lookup"><span data-stu-id="1d108-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="1d108-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="1d108-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="1d108-121">Имя CLR FullName типа вызванного инспектора.</span><span class="sxs-lookup"><span data-stu-id="1d108-121">The CLR FullName of the invoked inspector's type.</span></span>|  
|<span data-ttu-id="1d108-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="1d108-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="1d108-123">Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии.</span><span class="sxs-lookup"><span data-stu-id="1d108-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="1d108-124">Его формат определяется как "имя веб-сайта виртуальный путь к приложению&#124;виртуальный путь службы&#124;ServiceName".</span><span class="sxs-lookup"><span data-stu-id="1d108-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="1d108-125">Пример: "Default Web site/Калкулатораппликатион&#124;/Калкулаторсервице.СВК&#124;CalculatorService".</span><span class="sxs-lookup"><span data-stu-id="1d108-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="1d108-126">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="1d108-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="1d108-127">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="1d108-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
