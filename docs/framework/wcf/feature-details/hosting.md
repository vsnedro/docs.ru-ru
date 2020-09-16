---
title: Hosting2
ms.date: 03/30/2017
ms.assetid: 0820c7e5-0b50-4cde-80e7-74e346513002
ms.openlocfilehash: 0a502093ff40f1a702f5d4d9046d4627eae39e01
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90555787"
---
# <a name="hosting"></a><span data-ttu-id="fe2d1-102">Hosting</span><span class="sxs-lookup"><span data-stu-id="fe2d1-102">Hosting</span></span>
<span data-ttu-id="fe2d1-103">В подразделах этого раздела описано размещение служб.</span><span class="sxs-lookup"><span data-stu-id="fe2d1-103">The topics in the section describe service hosting.</span></span> <span data-ttu-id="fe2d1-104">Служба может размещаться в службы IIS (IIS), службе активации Windows (WAS), Windows Server AppFabric, службе Windows или управляемом приложении — этот вариант часто называется *размещением в собственном расположении*.</span><span class="sxs-lookup"><span data-stu-id="fe2d1-104">A service can be hosted by Internet Information Services (IIS), Windows Process Activation Service (WAS), Windows Server AppFabric, a Windows service, or by a managed application—this option is often referred to as *self hosting*.</span></span>  
  
 <span data-ttu-id="fe2d1-105">Важно отметить, что при запуске службы или любого расширения от недоверенного узла нарушается безопасность.</span><span class="sxs-lookup"><span data-stu-id="fe2d1-105">It is important to note that running a service or any extension from an untrusted host compromises security.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fe2d1-106">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="fe2d1-106">In This Section</span></span>  
 [<span data-ttu-id="fe2d1-107">Размещение в службах IIS</span><span class="sxs-lookup"><span data-stu-id="fe2d1-107">Hosting in Internet Information Services</span></span>](hosting-in-internet-information-services.md)  
 <span data-ttu-id="fe2d1-108">Описывает, как служба Windows Communication Foundation (WCF) размещается в службы IIS или [Windows Server AppFabric](/previous-versions/appfabric/ff384253(v=azure.10)).</span><span class="sxs-lookup"><span data-stu-id="fe2d1-108">Describes how a Windows Communication Foundation (WCF) service is hosted in Internet Information Services or [Windows Server AppFabric](/previous-versions/appfabric/ff384253(v=azure.10)).</span></span>  
  
 [<span data-ttu-id="fe2d1-109">Размещение в службе активации процессов Windows</span><span class="sxs-lookup"><span data-stu-id="fe2d1-109">Hosting in Windows Process Activation Service</span></span>](hosting-in-windows-process-activation-service.md)  
 <span data-ttu-id="fe2d1-110">Описывает, как служба WCF размещается службой активации процессов Windows.</span><span class="sxs-lookup"><span data-stu-id="fe2d1-110">Describes how a WCF service is hosted by Windows Process Activation Service.</span></span>  
  
 [<span data-ttu-id="fe2d1-111">Размещение в приложении службы Windows</span><span class="sxs-lookup"><span data-stu-id="fe2d1-111">Hosting in a Windows Service Application</span></span>](hosting-in-a-windows-service-application.md)  
 <span data-ttu-id="fe2d1-112">Описывает, как служба WCF размещается в службе Windows.</span><span class="sxs-lookup"><span data-stu-id="fe2d1-112">Describes how a WCF service is hosted by a Windows service.</span></span>  
  
 [<span data-ttu-id="fe2d1-113">Размещение в управляемом приложении</span><span class="sxs-lookup"><span data-stu-id="fe2d1-113">Hosting in a Managed Application</span></span>](hosting-in-a-managed-application.md)  
 <span data-ttu-id="fe2d1-114">Описывает, как служба WCF размещается в управляемом приложении.</span><span class="sxs-lookup"><span data-stu-id="fe2d1-114">Describes how a WCF service is hosted in a managed application.</span></span>  
  
 [<span data-ttu-id="fe2d1-115">Активация на основе конфигурации в IIS и WAS</span><span class="sxs-lookup"><span data-stu-id="fe2d1-115">Configuration-Based Activation in IIS and WAS</span></span>](configuration-based-activation-in-iis-and-was.md)  
 <span data-ttu-id="fe2d1-116">Описывает размещение службы WCF в IIS или WAS без использования SVC-файла.</span><span class="sxs-lookup"><span data-stu-id="fe2d1-116">Describes how a WCF service is hosted under IIS or WAS without using a .svc file.</span></span>  
  
 [<span data-ttu-id="fe2d1-117">Поддержка нескольких привязок узла IIS</span><span class="sxs-lookup"><span data-stu-id="fe2d1-117">Supporting Multiple IIS Site Bindings</span></span>](supporting-multiple-iis-site-bindings.md)  
 <span data-ttu-id="fe2d1-118">Описывает, как задать несколько базовых адресов службы с помощью одной схемы URI для одного веб-узла.</span><span class="sxs-lookup"><span data-stu-id="fe2d1-118">Describes how to specify multiple base addresses for a service using the same URI scheme on a single Web site.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe2d1-119">См. также</span><span class="sxs-lookup"><span data-stu-id="fe2d1-119">See also</span></span>

- [<span data-ttu-id="fe2d1-120">Размещение служб</span><span class="sxs-lookup"><span data-stu-id="fe2d1-120">Hosting Services</span></span>](../hosting-services.md)
- <span data-ttu-id="fe2d1-121">[Функции размещения Windows Server App Fabric](/previous-versions/appfabric/ee677189(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="fe2d1-121">[Windows Server App Fabric Hosting Features](/previous-versions/appfabric/ee677189(v=azure.10))</span></span>
