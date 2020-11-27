---
title: 202 - ClientMessageInspectorBeforeSendInvoked
ms.date: 03/30/2017
ms.assetid: 0b02ca82-8a55-45e3-b2e2-ddfe28a7269c
ms.openlocfilehash: f05a0f817b8cb4857a4fa50eada15d3ff9e06855
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96266627"
---
# <a name="202---clientmessageinspectorbeforesendinvoked"></a><span data-ttu-id="66e49-102">202 - ClientMessageInspectorBeforeSendInvoked</span><span class="sxs-lookup"><span data-stu-id="66e49-102">202 - ClientMessageInspectorBeforeSendInvoked</span></span>

## <a name="properties"></a><span data-ttu-id="66e49-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="66e49-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="66e49-104">ID</span><span class="sxs-lookup"><span data-stu-id="66e49-104">ID</span></span>|<span data-ttu-id="66e49-105">202</span><span class="sxs-lookup"><span data-stu-id="66e49-105">202</span></span>|  
|<span data-ttu-id="66e49-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="66e49-106">Keywords</span></span>|<span data-ttu-id="66e49-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="66e49-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="66e49-108">Level</span><span class="sxs-lookup"><span data-stu-id="66e49-108">Level</span></span>|<span data-ttu-id="66e49-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="66e49-109">Information</span></span>|  
|<span data-ttu-id="66e49-110">Канал</span><span class="sxs-lookup"><span data-stu-id="66e49-110">Channel</span></span>|<span data-ttu-id="66e49-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="66e49-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="66e49-112">Описание</span><span class="sxs-lookup"><span data-stu-id="66e49-112">Description</span></span>  

 <span data-ttu-id="66e49-113">Это событие создается после того, как модель службы вызывает метод `BeforeSendRequest` для инспектора сообщений клиента.</span><span class="sxs-lookup"><span data-stu-id="66e49-113">This event is emitted after the Service Model has invoked the `BeforeSendRequest` method on a client message inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="66e49-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="66e49-114">Message</span></span>  

 <span data-ttu-id="66e49-115">Диспетчер вызвал BeforeSendRequest для ClientMessageInspector типа «%1».</span><span class="sxs-lookup"><span data-stu-id="66e49-115">The Dispatcher invoked 'BeforeSendRequest' on a ClientMessageInspector of type  '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="66e49-116">Сведения</span><span class="sxs-lookup"><span data-stu-id="66e49-116">Details</span></span>  
  
|<span data-ttu-id="66e49-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="66e49-117">Data Item Name</span></span>|<span data-ttu-id="66e49-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="66e49-118">Data Item Type</span></span>|<span data-ttu-id="66e49-119">Описание</span><span class="sxs-lookup"><span data-stu-id="66e49-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="66e49-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="66e49-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="66e49-121">Имя CLR FullName типа вызванного инспектора.</span><span class="sxs-lookup"><span data-stu-id="66e49-121">The CLR FullName of the invoked inspector's type.</span></span>|  
|<span data-ttu-id="66e49-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="66e49-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="66e49-123">Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии.</span><span class="sxs-lookup"><span data-stu-id="66e49-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="66e49-124">Его формат определяется как "имя веб-сайта виртуальный путь к приложению&#124;виртуальный путь службы&#124;ServiceName".</span><span class="sxs-lookup"><span data-stu-id="66e49-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="66e49-125">Пример: "Default Web site/Калкулатораппликатион&#124;/Калкулаторсервице.СВК&#124;CalculatorService".</span><span class="sxs-lookup"><span data-stu-id="66e49-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="66e49-126">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="66e49-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="66e49-127">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="66e49-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
