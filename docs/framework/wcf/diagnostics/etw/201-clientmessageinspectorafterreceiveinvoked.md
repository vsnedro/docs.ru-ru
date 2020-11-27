---
title: 201 - ClientMessageInspectorAfterReceiveInvoked
ms.date: 03/30/2017
ms.assetid: 9ff637f1-cc26-4400-ab9b-546f70e5057d
ms.openlocfilehash: d84f6c6f38868f7915caaaf87e15885099b65456
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96266679"
---
# <a name="201---clientmessageinspectorafterreceiveinvoked"></a><span data-ttu-id="1a65c-102">201 - ClientMessageInspectorAfterReceiveInvoked</span><span class="sxs-lookup"><span data-stu-id="1a65c-102">201 - ClientMessageInspectorAfterReceiveInvoked</span></span>

## <a name="properties"></a><span data-ttu-id="1a65c-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="1a65c-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1a65c-104">ID</span><span class="sxs-lookup"><span data-stu-id="1a65c-104">ID</span></span>|<span data-ttu-id="1a65c-105">201</span><span class="sxs-lookup"><span data-stu-id="1a65c-105">201</span></span>|  
|<span data-ttu-id="1a65c-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="1a65c-106">Keywords</span></span>|<span data-ttu-id="1a65c-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="1a65c-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="1a65c-108">Level</span><span class="sxs-lookup"><span data-stu-id="1a65c-108">Level</span></span>|<span data-ttu-id="1a65c-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="1a65c-109">Information</span></span>|  
|<span data-ttu-id="1a65c-110">Канал</span><span class="sxs-lookup"><span data-stu-id="1a65c-110">Channel</span></span>|<span data-ttu-id="1a65c-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="1a65c-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="1a65c-112">Описание</span><span class="sxs-lookup"><span data-stu-id="1a65c-112">Description</span></span>  

 <span data-ttu-id="1a65c-113">Это событие создается после того, как модель службы вызывает метод `AfterReceiveReply` для инспектора сообщений клиента.</span><span class="sxs-lookup"><span data-stu-id="1a65c-113">This event is emitted after the Service Model has invoked the `AfterReceiveReply` method on a client message inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="1a65c-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="1a65c-114">Message</span></span>  

 <span data-ttu-id="1a65c-115">Диспетчер вызвал AfterReceiveReply относительно ClientMessageInspector типа «%1».</span><span class="sxs-lookup"><span data-stu-id="1a65c-115">The Dispatcher invoked 'AfterReceiveReply' on a ClientMessageInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="1a65c-116">Сведения</span><span class="sxs-lookup"><span data-stu-id="1a65c-116">Details</span></span>  
  
|<span data-ttu-id="1a65c-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="1a65c-117">Data Item Name</span></span>|<span data-ttu-id="1a65c-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="1a65c-118">Data Item Type</span></span>|<span data-ttu-id="1a65c-119">Описание</span><span class="sxs-lookup"><span data-stu-id="1a65c-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="1a65c-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="1a65c-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="1a65c-121">Имя CLR FullName типа вызванного инспектора.</span><span class="sxs-lookup"><span data-stu-id="1a65c-121">The CLR FullName of the invoked inspector's type.</span></span>|  
|<span data-ttu-id="1a65c-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="1a65c-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="1a65c-123">Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии.</span><span class="sxs-lookup"><span data-stu-id="1a65c-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="1a65c-124">Его формат определяется как "имя веб-сайта виртуальный путь к приложению&#124;виртуальный путь службы&#124;ServiceName".</span><span class="sxs-lookup"><span data-stu-id="1a65c-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="1a65c-125">Пример: "Default Web site/Калкулатораппликатион&#124;/Калкулаторсервице.СВК&#124;CalculatorService".</span><span class="sxs-lookup"><span data-stu-id="1a65c-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="1a65c-126">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="1a65c-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="1a65c-127">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="1a65c-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
