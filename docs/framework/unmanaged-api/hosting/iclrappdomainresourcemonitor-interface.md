---
title: Интерфейс ICLRAppDomainResourceMonitor
ms.date: 03/30/2017
api_name:
- ICLRAppDomainResourceMonitor
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAppDomainResourceMonitor
helpviewer_keywords:
- ICLRAppDomainResourceMonitor interface [.NET Framework hosting]
ms.assetid: 72fa83a1-8997-41d7-b355-ab177a24a303
topic_type:
- apiref
ms.openlocfilehash: 84c53f0666d0e04b898e28c1d8e146eab566ca1b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95674701"
---
# <a name="iclrappdomainresourcemonitor-interface"></a><span data-ttu-id="0cf93-102">Интерфейс ICLRAppDomainResourceMonitor</span><span class="sxs-lookup"><span data-stu-id="0cf93-102">ICLRAppDomainResourceMonitor Interface</span></span>

<span data-ttu-id="0cf93-103">Предоставляет методы для проверки использования памяти и ЦП домена приложения.</span><span class="sxs-lookup"><span data-stu-id="0cf93-103">Provides methods that inspect an application domain's memory and CPU usage.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0cf93-104">Методы</span><span class="sxs-lookup"><span data-stu-id="0cf93-104">Methods</span></span>  
  
|<span data-ttu-id="0cf93-105">Метод</span><span class="sxs-lookup"><span data-stu-id="0cf93-105">Method</span></span>|<span data-ttu-id="0cf93-106">Описание</span><span class="sxs-lookup"><span data-stu-id="0cf93-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0cf93-107">Метод GetCurrentAllocated</span><span class="sxs-lookup"><span data-stu-id="0cf93-107">GetCurrentAllocated Method</span></span>](iclrappdomainresourcemonitor-getcurrentallocated-method.md)|<span data-ttu-id="0cf93-108">Возвращает общий размер (в байтах) всех выделений памяти, сделанных доменом приложения с момента его создания, без вычитания памяти, которая была собрана сборщиком мусора.</span><span class="sxs-lookup"><span data-stu-id="0cf93-108">Gets the total size, in bytes, of all memory allocations that have been made by the application domain since it was created, without subtracting memory that has been garbage-collected.</span></span>|  
|[<span data-ttu-id="0cf93-109">Метод GetCurrentSurvived</span><span class="sxs-lookup"><span data-stu-id="0cf93-109">GetCurrentSurvived Method</span></span>](iclrappdomainresourcemonitor-getcurrentsurvived-method.md)|<span data-ttu-id="0cf93-110">Возвращает число байтов, сохранившихся последней полной блокирующей сборки мусора, на которые ссылается текущий домен приложения.</span><span class="sxs-lookup"><span data-stu-id="0cf93-110">Gets the number of bytes that survived the last full, blocking garbage collection and that are referenced by the current application domain.</span></span>|  
|[<span data-ttu-id="0cf93-111">Метод GetCurrentCpuTime</span><span class="sxs-lookup"><span data-stu-id="0cf93-111">GetCurrentCpuTime Method</span></span>](iclrappdomainresourcemonitor-getcurrentcputime-method.md)|<span data-ttu-id="0cf93-112">Возвращает общее время процессора, которое использовалось всеми потоками во время выполнения в текущем домене приложения, так как был создан домен приложения.</span><span class="sxs-lookup"><span data-stu-id="0cf93-112">Gets the total processor time that has been used by all threads while executing in the current application domain, since the application domain was created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0cf93-113">Комментарии</span><span class="sxs-lookup"><span data-stu-id="0cf93-113">Remarks</span></span>  

 <span data-ttu-id="0cf93-114">`ICLRAppDomainResourceMonitor`Интерфейс предоставляет функциональные возможности, аналогичные следующим управляемым свойствам:</span><span class="sxs-lookup"><span data-stu-id="0cf93-114">The `ICLRAppDomainResourceMonitor` interface provides functionality that is similar to the following managed properties:</span></span>  
  
- <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType>  
  
- <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType>  
  
- <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType>  
  
- <xref:System.AppDomain.MonitoringSurvivedProcessMemorySize%2A?displayProperty=nameWithType>  
  
- <xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType>  
  
## <a name="requirements"></a><span data-ttu-id="0cf93-115">Требования</span><span class="sxs-lookup"><span data-stu-id="0cf93-115">Requirements</span></span>  

 <span data-ttu-id="0cf93-116">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0cf93-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0cf93-117">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="0cf93-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="0cf93-118">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0cf93-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0cf93-119">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0cf93-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0cf93-120">См. также</span><span class="sxs-lookup"><span data-stu-id="0cf93-120">See also</span></span>

- [<span data-ttu-id="0cf93-121">\<appDomainResourceMonitoring> Элемент</span><span class="sxs-lookup"><span data-stu-id="0cf93-121">\<appDomainResourceMonitoring> Element</span></span>](../../configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md)
- [<span data-ttu-id="0cf93-122">Мониторинг ресурсов домена приложения</span><span class="sxs-lookup"><span data-stu-id="0cf93-122">Application Domain Resource Monitoring</span></span>](../../../standard/garbage-collection/app-domain-resource-monitoring.md)
- [<span data-ttu-id="0cf93-123">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="0cf93-123">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="0cf93-124">Размещение</span><span class="sxs-lookup"><span data-stu-id="0cf93-124">Hosting</span></span>](index.md)
