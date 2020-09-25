---
title: Элемент <applicationPool> (веб-параметры)
ms.date: 03/30/2017
helpviewer_keywords:
- applicationPool element
- <applicationPool> element
ms.assetid: 46d1baaa-e343-4639-b70d-2a43a9f62b2a
ms.openlocfilehash: 963b25e57ae8c2cc59dcc3e50ae2a52cc04f54a8
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91185643"
---
# <a name="applicationpool-element-web-settings"></a><span data-ttu-id="14e91-102">Элемент \<applicationPool> (веб-параметры)</span><span class="sxs-lookup"><span data-stu-id="14e91-102">\<applicationPool> Element (Web Settings)</span></span>

<span data-ttu-id="14e91-103">Указывает параметры конфигурации, используемые ASP.NET для управления поведением на уровне процесса, когда приложение ASP.NET работает в интегрированном режиме в IIS 7,0 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="14e91-103">Specifies configuration settings that are used by ASP.NET to manage process-wide behavior when an ASP.NET application is running in Integrated mode on IIS 7.0 or a later version.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="14e91-104">Этот элемент и функция, которые он поддерживает, работают только в том случае, если приложение ASP.NET размещено в IIS 7,0 или более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="14e91-104">This element and the feature it supports only work if your ASP.NET application is hosted on IIS 7.0 or later versions.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.web>**](system-web-element-web-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<applicationPool>**  
  
## <a name="syntax"></a><span data-ttu-id="14e91-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="14e91-105">Syntax</span></span>  
  
```xml  
<applicationPool
    maxConcurrentRequestsPerCPU="5000"
    maxConcurrentThreadsPerCPU="0"
    requestQueueLimit="5000" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="14e91-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="14e91-106">Attributes and Elements</span></span>  

<span data-ttu-id="14e91-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="14e91-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="14e91-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="14e91-108">Attributes</span></span>  
  
|<span data-ttu-id="14e91-109">Атрибут</span><span class="sxs-lookup"><span data-stu-id="14e91-109">Attribute</span></span>|<span data-ttu-id="14e91-110">Описание</span><span class="sxs-lookup"><span data-stu-id="14e91-110">Description</span></span>|  
|---------------|-----------------|  
|`maxConcurrentRequestsPerCPU`|<span data-ttu-id="14e91-111">Указывает, сколько одновременных запросов ASP.NET позволяет для каждого ЦП.</span><span class="sxs-lookup"><span data-stu-id="14e91-111">Specifies how many simultaneous requests ASP.NET allows per CPU.</span></span>|  
|`maxConcurrentThreadsPerCPU`|<span data-ttu-id="14e91-112">Указывает, сколько одновременных потоков может выполняться для пула приложений для каждого ЦП.</span><span class="sxs-lookup"><span data-stu-id="14e91-112">Specifies how many simultaneous threads can be running for an application pool for each CPU.</span></span> <span data-ttu-id="14e91-113">Это предоставляет альтернативный способ управления параллелизмом ASP.NET, так как можно ограничить количество управляемых потоков, которые могут использоваться на каждый ЦП для обслуживания запросов.</span><span class="sxs-lookup"><span data-stu-id="14e91-113">This provides an alternative way to control ASP.NET concurrency, because you can limit the number of managed threads that can be used per CPU to serve requests.</span></span> <span data-ttu-id="14e91-114">По умолчанию этот параметр равен 0. Это означает, что ASP.NET не ограничивает количество потоков, которые могут быть созданы для каждого ЦП, хотя пул потоков CLR также ограничивает количество потоков, которые могут быть созданы.</span><span class="sxs-lookup"><span data-stu-id="14e91-114">By default this setting is 0, which means that ASP.NET does not limit the number of threads that can be created per CPU, although the CLR thread pool also limits the number of threads that can be created.</span></span>|  
|`requestQueueLimit`|<span data-ttu-id="14e91-115">Указывает максимальное количество запросов, которые могут быть поставлены в очередь для ASP.NET в одном процессе.</span><span class="sxs-lookup"><span data-stu-id="14e91-115">Specifies the maximum number of requests that can be queued for ASP.NET in a single process.</span></span> <span data-ttu-id="14e91-116">Если два или более ASP.NET приложений работают в одном пуле приложений, этот параметр подлежит совокупному набору запросов, выполняемых в любом приложении в пуле приложений.</span><span class="sxs-lookup"><span data-stu-id="14e91-116">When two or more ASP.NET applications run in a single application pool, the cumulative set of requests being made to any application in the application pool is subject to this setting.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="14e91-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="14e91-117">Child Elements</span></span>  

 <span data-ttu-id="14e91-118">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="14e91-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="14e91-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="14e91-119">Parent Elements</span></span>  
  
|<span data-ttu-id="14e91-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="14e91-120">Element</span></span>|<span data-ttu-id="14e91-121">Описание</span><span class="sxs-lookup"><span data-stu-id="14e91-121">Description</span></span>|  
|-------------|-----------------|  
|[\<system.web>](system-web-element-web-settings.md)|<span data-ttu-id="14e91-122">Содержит сведения о взаимодействии ASP.NET с ведущим приложением.</span><span class="sxs-lookup"><span data-stu-id="14e91-122">Contains information about how ASP.NET interacts with a host application.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="14e91-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="14e91-123">Remarks</span></span>  

<span data-ttu-id="14e91-124">При запуске IIS 7,0 или более поздней версии в интегрированном режиме это сочетание элементов позволяет настроить, как ASP.NET управляет потоками и помещает запросы в очередь, когда приложение размещается в пуле приложений IIS.</span><span class="sxs-lookup"><span data-stu-id="14e91-124">When you run IIS 7.0 or a later version in Integrated mode, this element combination lets you configure how ASP.NET manages threads and queues requests when the application is hosted in an IIS application pool.</span></span> <span data-ttu-id="14e91-125">При запуске IIS 6 или IIS 7,0 в классическом режиме или в режиме ISAPI эти параметры игнорируются.</span><span class="sxs-lookup"><span data-stu-id="14e91-125">If you run IIS 6 or you run IIS 7.0 in Classic mode or in ISAPI mode, these settings are ignored.</span></span>  
  
<span data-ttu-id="14e91-126">`applicationPool`Параметры применяются ко всем пулам приложений, которые выполняются в определенной версии .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="14e91-126">The `applicationPool` settings apply to all application pools that run on a particular version of the .NET Framework.</span></span> <span data-ttu-id="14e91-127">Параметры содержатся в файле aspnet.config.</span><span class="sxs-lookup"><span data-stu-id="14e91-127">The settings are contained in an aspnet.config file.</span></span> <span data-ttu-id="14e91-128">Существует версия этого файла для .NET Framework версий 2,0 и 4,0.</span><span class="sxs-lookup"><span data-stu-id="14e91-128">There is a version of this file for versions 2.0 and 4.0 of the .NET Framework.</span></span> <span data-ttu-id="14e91-129">(Версии 3,0 и 3,5 .NET Framework совместно используют файл aspnet.config с версией 2,0.)</span><span class="sxs-lookup"><span data-stu-id="14e91-129">(Versions 3.0 and 3.5 of the .NET Framework share the aspnet.config file with version 2.0.)</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="14e91-130">При запуске IIS 7,0 в Windows 7 можно настроить отдельный файл aspnet.config для каждого пула приложений.</span><span class="sxs-lookup"><span data-stu-id="14e91-130">If you run IIS 7.0 on Windows 7, you can configure a separate aspnet.config file for every application pool.</span></span> <span data-ttu-id="14e91-131">Это позволяет адаптировать производительность потоков для каждого пула приложений.</span><span class="sxs-lookup"><span data-stu-id="14e91-131">This lets you tailor the performance of the threads for each application pool.</span></span>  
  
<span data-ttu-id="14e91-132">Для `maxConcurrentRequestsPerCPU` параметра значение по умолчанию "5000" в .NET Framework 4 эффективно регулирует регулирование запросов, контролируемое ASP.NET, если на самом деле не будет 5000 или больше запросов на ЦП.</span><span class="sxs-lookup"><span data-stu-id="14e91-132">For the `maxConcurrentRequestsPerCPU` setting, the default setting of "5000" in the .NET Framework 4 effectively turns off request throttling that is controlled by ASP.NET, unless you actually have 5000 or more requests per CPU.</span></span> <span data-ttu-id="14e91-133">Значение по умолчанию зависит от того, что в пуле потоков CLR для автоматического управления параллелизмом на каждый ЦП.</span><span class="sxs-lookup"><span data-stu-id="14e91-133">The default setting depends instead on the CLR thread-pool to automatically manage concurrency per CPU.</span></span> <span data-ttu-id="14e91-134">Приложения, которые активно используют асинхронную обработку запросов или которые имеют много долго выполняющихся запросов, заблокированы в операциях ввода-вывода сети, получат преимущество от увеличения предельного значения по умолчанию в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="14e91-134">Applications that make extensive use of asynchronous request processing, or that have many long-running requests blocked on network I/O, will benefit from the increased default limit in the .NET Framework 4.</span></span> <span data-ttu-id="14e91-135">Если задать для параметра значение `maxConcurrentRequestsPerCPU` 0, использование управляемых потоков для обработки запросов ASP.NET отключается.</span><span class="sxs-lookup"><span data-stu-id="14e91-135">Setting `maxConcurrentRequestsPerCPU` to zero turns off the use of managed threads for processing ASP.NET requests.</span></span> <span data-ttu-id="14e91-136">Когда приложение запускается в пуле приложений IIS, запросы остаются в потоке ввода-вывода IIS, поэтому параллелизм регулируется параметрами потока IIS.</span><span class="sxs-lookup"><span data-stu-id="14e91-136">When an application runs in an IIS application pool, requests stay on the IIS I/O thread and therefore concurrency is throttled by IIS thread settings.</span></span>  
  
<span data-ttu-id="14e91-137">Этот `requestQueueLimit` параметр работает так же, как `requestQueueLimit` атрибут элемента [processModel](/previous-versions/dotnet/netframework-4.0/7w2sway1(v=vs.100)) , который задается в файлах Web.config для приложений ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="14e91-137">The `requestQueueLimit` setting works the same way as the `requestQueueLimit` attribute of the [processModel](/previous-versions/dotnet/netframework-4.0/7w2sway1(v=vs.100)) element, which is set in the Web.config files for ASP.NET applications.</span></span> <span data-ttu-id="14e91-138">Однако `requestQueueLimit` параметр в файле aspnet.config переопределяет `requestQueueLimit` параметр в Web.configном файле.</span><span class="sxs-lookup"><span data-stu-id="14e91-138">However, the `requestQueueLimit` setting in an aspnet.config file overrides the `requestQueueLimit` setting in a Web.config file.</span></span> <span data-ttu-id="14e91-139">Иными словами, если заданы оба атрибута (по умолчанию это значение равно true), `requestQueueLimit` приоритет имеет параметр в файле aspnet.config.</span><span class="sxs-lookup"><span data-stu-id="14e91-139">In other words, if both attributes are set (by default, this is true), the `requestQueueLimit` setting in the aspnet.config file takes precedence.</span></span>  
  
## <a name="example"></a><span data-ttu-id="14e91-140">Пример</span><span class="sxs-lookup"><span data-stu-id="14e91-140">Example</span></span>  

<span data-ttu-id="14e91-141">В следующем примере показано, как настроить поведение ASP.NET на уровне процесса в файле aspnet.config в следующих случаях.</span><span class="sxs-lookup"><span data-stu-id="14e91-141">The following example shows how to configure ASP.NET process-wide behavior in the aspnet.config file in the following circumstances:</span></span>  
  
- <span data-ttu-id="14e91-142">Приложение размещается в пуле приложений IIS 7,0.</span><span class="sxs-lookup"><span data-stu-id="14e91-142">The application is hosted in an IIS 7.0 application pool.</span></span>  
  
- <span data-ttu-id="14e91-143">IIS 7,0 работает в интегрированном режиме.</span><span class="sxs-lookup"><span data-stu-id="14e91-143">IIS 7.0 is running in Integrated mode.</span></span>  
  
- <span data-ttu-id="14e91-144">Приложение использует .NET Framework 3,5 с пакетом обновления 1 (SP1) или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="14e91-144">The application is using the .NET Framework 3.5 SP1 or a later version.</span></span>  
  
<span data-ttu-id="14e91-145">Значения в примере являются значениями по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="14e91-145">The values in the example are the default values.</span></span>  
  
```xml  
<configuration>  
  <system.web>  
    <applicationPool
        maxConcurrentRequestsPerCPU="5000"  
        maxConcurrentThreadsPerCPU="0"
        requestQueueLimit="5000" />  
  </system.web>  
</configuration>  
```  
  
## <a name="element-information"></a><span data-ttu-id="14e91-146">Сведения об элементе</span><span class="sxs-lookup"><span data-stu-id="14e91-146">Element Information</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="14e91-147">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="14e91-147">Namespace</span></span>||  
|<span data-ttu-id="14e91-148">Имя схемы</span><span class="sxs-lookup"><span data-stu-id="14e91-148">Schema Name</span></span>||  
|<span data-ttu-id="14e91-149">Файл проверки</span><span class="sxs-lookup"><span data-stu-id="14e91-149">Validation File</span></span>||  
|<span data-ttu-id="14e91-150">Может быть пустым</span><span class="sxs-lookup"><span data-stu-id="14e91-150">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="14e91-151">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="14e91-151">See also</span></span>

- [<span data-ttu-id="14e91-152">\<system.web> Элемент (веб-параметры)</span><span class="sxs-lookup"><span data-stu-id="14e91-152">\<system.web> Element (Web Settings)</span></span>](system-web-element-web-settings.md)
