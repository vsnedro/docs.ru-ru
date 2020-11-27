---
title: 208 - MessageInspectorAfterReceiveInvoked
ms.date: 03/30/2017
ms.assetid: dfb5f7b0-4346-4949-8104-351726b1f502
ms.openlocfilehash: 4aa0f41b0b772551d9257920e5c15051961b7332
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96267823"
---
# <a name="208---messageinspectorafterreceiveinvoked"></a><span data-ttu-id="2f91a-102">208 - MessageInspectorAfterReceiveInvoked</span><span class="sxs-lookup"><span data-stu-id="2f91a-102">208 - MessageInspectorAfterReceiveInvoked</span></span>

## <a name="properties"></a><span data-ttu-id="2f91a-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="2f91a-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2f91a-104">ID</span><span class="sxs-lookup"><span data-stu-id="2f91a-104">ID</span></span>|<span data-ttu-id="2f91a-105">208</span><span class="sxs-lookup"><span data-stu-id="2f91a-105">208</span></span>|  
|<span data-ttu-id="2f91a-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="2f91a-106">Keywords</span></span>|<span data-ttu-id="2f91a-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="2f91a-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="2f91a-108">Level</span><span class="sxs-lookup"><span data-stu-id="2f91a-108">Level</span></span>|<span data-ttu-id="2f91a-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="2f91a-109">Information</span></span>|  
|<span data-ttu-id="2f91a-110">Канал</span><span class="sxs-lookup"><span data-stu-id="2f91a-110">Channel</span></span>|<span data-ttu-id="2f91a-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="2f91a-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="2f91a-112">Описание</span><span class="sxs-lookup"><span data-stu-id="2f91a-112">Description</span></span>  

 <span data-ttu-id="2f91a-113">Это событие создается после того, как модель службы вызвала метод `AfterReceive` для инспектора сообщений.</span><span class="sxs-lookup"><span data-stu-id="2f91a-113">This event is emitted after the Service Model has invoked the `AfterReceive` method on a message inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="2f91a-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="2f91a-114">Message</span></span>  

 <span data-ttu-id="2f91a-115">Диспетчер вызвал AfterReceiveReply относительно MessageInspector типа «%1».</span><span class="sxs-lookup"><span data-stu-id="2f91a-115">The Dispatcher invoked 'AfterReceiveReply' on a MessageInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="2f91a-116">Сведения</span><span class="sxs-lookup"><span data-stu-id="2f91a-116">Details</span></span>  
  
|<span data-ttu-id="2f91a-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="2f91a-117">Data Item Name</span></span>|<span data-ttu-id="2f91a-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="2f91a-118">Data Item Type</span></span>|<span data-ttu-id="2f91a-119">Описание</span><span class="sxs-lookup"><span data-stu-id="2f91a-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="2f91a-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="2f91a-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="2f91a-121">Имя CLR FullName типа вызванного инспектора `MessageInspector`.</span><span class="sxs-lookup"><span data-stu-id="2f91a-121">The CLR FullName of the type of the invoked `MessageInspector`.</span></span>|  
|<span data-ttu-id="2f91a-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="2f91a-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="2f91a-123">Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии.</span><span class="sxs-lookup"><span data-stu-id="2f91a-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="2f91a-124">Его формат определяется как "имя веб-сайта виртуальный путь к приложению&#124;виртуальный путь службы&#124;ServiceName".</span><span class="sxs-lookup"><span data-stu-id="2f91a-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="2f91a-125">Пример: "Default Web site/Калкулатораппликатион&#124;/Калкулаторсервице.СВК&#124;CalculatorService".</span><span class="sxs-lookup"><span data-stu-id="2f91a-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="2f91a-126">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="2f91a-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="2f91a-127">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="2f91a-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
