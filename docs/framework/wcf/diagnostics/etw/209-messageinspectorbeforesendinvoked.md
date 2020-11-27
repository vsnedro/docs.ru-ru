---
title: 209 - MessageInspectorBeforeSendInvoked
ms.date: 03/30/2017
ms.assetid: 7d710875-fb77-4463-978b-bc86d59d84cd
ms.openlocfilehash: 50a9424f445781cac70d7d7fde58beea10231cfa
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96267758"
---
# <a name="209---messageinspectorbeforesendinvoked"></a><span data-ttu-id="ab3ec-102">209 - MessageInspectorBeforeSendInvoked</span><span class="sxs-lookup"><span data-stu-id="ab3ec-102">209 - MessageInspectorBeforeSendInvoked</span></span>

## <a name="properties"></a><span data-ttu-id="ab3ec-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="ab3ec-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ab3ec-104">ID</span><span class="sxs-lookup"><span data-stu-id="ab3ec-104">ID</span></span>|<span data-ttu-id="ab3ec-105">209</span><span class="sxs-lookup"><span data-stu-id="ab3ec-105">209</span></span>|  
|<span data-ttu-id="ab3ec-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="ab3ec-106">Keywords</span></span>|<span data-ttu-id="ab3ec-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="ab3ec-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="ab3ec-108">Level</span><span class="sxs-lookup"><span data-stu-id="ab3ec-108">Level</span></span>|<span data-ttu-id="ab3ec-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="ab3ec-109">Information</span></span>|  
|<span data-ttu-id="ab3ec-110">Канал</span><span class="sxs-lookup"><span data-stu-id="ab3ec-110">Channel</span></span>|<span data-ttu-id="ab3ec-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="ab3ec-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="ab3ec-112">Описание</span><span class="sxs-lookup"><span data-stu-id="ab3ec-112">Description</span></span>  

 <span data-ttu-id="ab3ec-113">Это событие создается после того, как модель службы вызвала метод `BeforeSend` для инспектора сообщений.</span><span class="sxs-lookup"><span data-stu-id="ab3ec-113">This event is emitted after the Service Model has invoked the `BeforeSend` method on a message inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="ab3ec-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="ab3ec-114">Message</span></span>  

 <span data-ttu-id="ab3ec-115">Диспетчер вызвал BeforeSendRequest для MessageInspector типа «%1».</span><span class="sxs-lookup"><span data-stu-id="ab3ec-115">The Dispatcher invoked 'BeforeSendRequest' on a MessageInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="ab3ec-116">Сведения</span><span class="sxs-lookup"><span data-stu-id="ab3ec-116">Details</span></span>  
  
|<span data-ttu-id="ab3ec-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="ab3ec-117">Data Item Name</span></span>|<span data-ttu-id="ab3ec-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="ab3ec-118">Data Item Type</span></span>|<span data-ttu-id="ab3ec-119">Описание</span><span class="sxs-lookup"><span data-stu-id="ab3ec-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="ab3ec-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="ab3ec-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="ab3ec-121">Имя CLR FullName типа вызванного инспектора `MessageInspector`.</span><span class="sxs-lookup"><span data-stu-id="ab3ec-121">The CLR FullName of the type of the invoked `MessageInspector`.</span></span>|  
|<span data-ttu-id="ab3ec-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="ab3ec-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="ab3ec-123">Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии.</span><span class="sxs-lookup"><span data-stu-id="ab3ec-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="ab3ec-124">Его формат определяется как "имя веб-сайта виртуальный путь к приложению&#124;виртуальный путь службы&#124;ServiceName".</span><span class="sxs-lookup"><span data-stu-id="ab3ec-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="ab3ec-125">Пример: "Default Web site/Калкулатораппликатион&#124;/Калкулаторсервице.СВК&#124;CalculatorService".</span><span class="sxs-lookup"><span data-stu-id="ab3ec-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="ab3ec-126">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="ab3ec-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="ab3ec-127">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="ab3ec-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
