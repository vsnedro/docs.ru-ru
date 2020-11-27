---
title: 213 - ServiceHostStarted
ms.date: 03/30/2017
ms.assetid: a6f7facc-342f-46bb-9d52-a470178ba6bb
ms.openlocfilehash: 87a98d30f5ecde6f81580a95e337df22341c23d4
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96279029"
---
# <a name="213---servicehoststarted"></a><span data-ttu-id="c3a05-102">213 - ServiceHostStarted</span><span class="sxs-lookup"><span data-stu-id="c3a05-102">213 - ServiceHostStarted</span></span>

## <a name="properties"></a><span data-ttu-id="c3a05-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="c3a05-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c3a05-104">ID</span><span class="sxs-lookup"><span data-stu-id="c3a05-104">ID</span></span>|<span data-ttu-id="c3a05-105">213</span><span class="sxs-lookup"><span data-stu-id="c3a05-105">213</span></span>|  
|<span data-ttu-id="c3a05-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="c3a05-106">Keywords</span></span>|<span data-ttu-id="c3a05-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceHost</span><span class="sxs-lookup"><span data-stu-id="c3a05-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceHost</span></span>|  
|<span data-ttu-id="c3a05-108">Level</span><span class="sxs-lookup"><span data-stu-id="c3a05-108">Level</span></span>|<span data-ttu-id="c3a05-109">LogAlways</span><span class="sxs-lookup"><span data-stu-id="c3a05-109">LogAlways</span></span>|  
|<span data-ttu-id="c3a05-110">Канал</span><span class="sxs-lookup"><span data-stu-id="c3a05-110">Channel</span></span>|<span data-ttu-id="c3a05-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="c3a05-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="c3a05-112">Описание</span><span class="sxs-lookup"><span data-stu-id="c3a05-112">Description</span></span>  

 <span data-ttu-id="c3a05-113">Это событие создается при запуске службы, размещенной на веб-сервере.</span><span class="sxs-lookup"><span data-stu-id="c3a05-113">This event is emitted when a Web-hosted service host is started.</span></span> <span data-ttu-id="c3a05-114">Обычно это происходит, когда служба активируется сообщением.</span><span class="sxs-lookup"><span data-stu-id="c3a05-114">This typically happens when the service is activated by a message.</span></span> <span data-ttu-id="c3a05-115">Это также может произойти, если служба настроена для автоматического запуска.</span><span class="sxs-lookup"><span data-stu-id="c3a05-115">It may also happen if the service is configured to be automatically started.</span></span>  
  
## <a name="message"></a><span data-ttu-id="c3a05-116">Сообщение</span><span class="sxs-lookup"><span data-stu-id="c3a05-116">Message</span></span>  

 <span data-ttu-id="c3a05-117">ServiceHost запущена: «%1».</span><span class="sxs-lookup"><span data-stu-id="c3a05-117">ServiceHost started: '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="c3a05-118">Сведения</span><span class="sxs-lookup"><span data-stu-id="c3a05-118">Details</span></span>  
  
|<span data-ttu-id="c3a05-119">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="c3a05-119">Data Item Name</span></span>|<span data-ttu-id="c3a05-120">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="c3a05-120">Data Item Type</span></span>|<span data-ttu-id="c3a05-121">Описание</span><span class="sxs-lookup"><span data-stu-id="c3a05-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="c3a05-122">Имя типа службы</span><span class="sxs-lookup"><span data-stu-id="c3a05-122">Service Type Name</span></span>|`xs:string`|<span data-ttu-id="c3a05-123">Имя CLR FullName типа реализации службы.</span><span class="sxs-lookup"><span data-stu-id="c3a05-123">The CLR FullName of the type of the service implementation.</span></span>|  
|<span data-ttu-id="c3a05-124">HostReference</span><span class="sxs-lookup"><span data-stu-id="c3a05-124">HostReference</span></span>|`xs:string`|<span data-ttu-id="c3a05-125">Для служб, размещенных на веб-узле, это поле служит уникальным идентификатором службы в веб-иерархии.</span><span class="sxs-lookup"><span data-stu-id="c3a05-125">For Web hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="c3a05-126">Его формат определяется как "имя веб-сайта виртуальный путь к приложению&#124;виртуальный путь службы&#124;ServiceName".</span><span class="sxs-lookup"><span data-stu-id="c3a05-126">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="c3a05-127">Пример: "Default Web site/Калкулатораппликатион&#124;/Калкулаторсервице.СВК&#124;CalculatorService".</span><span class="sxs-lookup"><span data-stu-id="c3a05-127">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="c3a05-128">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="c3a05-128">AppDomain</span></span>|`xs:string`|<span data-ttu-id="c3a05-129">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="c3a05-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
