---
title: Сборка мусора .NET
description: Узнайте о сборке мусора в .NET. Сборщик мусора .NET управляет выделением и освобождением памяти для приложения.
ms.date: 04/21/2020
ms.technology: dotnet-standard
helpviewer_keywords:
- memory, garbage collection
- garbage collection, automatic memory management
- GC [.NET]
- memory, allocating
- common language runtime, garbage collection
- garbage collector
- cleanup operations
- garbage collection
- memory, releasing
- common language runtime, automatic memory management
- automatic memory management
- runtime, automatic memory management
- runtime, garbage collection
- garbage collection, about
ms.assetid: 22b6cb97-0c80-4eeb-a2cf-5ed7655e37f9
ms.openlocfilehash: 39b5bf62935054bd4b9be2d228cc42202aa89144
ms.sourcegitcommit: b1442669f1982d3a1cb18ea35b5acfb0fc7d93e4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2020
ms.locfileid: "93063193"
---
# <a name="garbage-collection"></a><span data-ttu-id="04d5d-104">Сборка мусора</span><span class="sxs-lookup"><span data-stu-id="04d5d-104">Garbage collection</span></span>

<span data-ttu-id="04d5d-105">Сборщик мусора .NET управляет выделением и освобождением памяти для приложения.</span><span class="sxs-lookup"><span data-stu-id="04d5d-105">.NET's garbage collector manages the allocation and release of memory for your application.</span></span> <span data-ttu-id="04d5d-106">При каждом создании объекта среда CLR выделяет память для объекта из управляемой кучи.</span><span class="sxs-lookup"><span data-stu-id="04d5d-106">Each time you create a new object, the common language runtime allocates memory for the object from the managed heap.</span></span> <span data-ttu-id="04d5d-107">Пока в управляемой куче есть доступное адресное пространство, среда выполнения продолжает выделять пространство для новых объектов.</span><span class="sxs-lookup"><span data-stu-id="04d5d-107">As long as address space is available in the managed heap, the runtime continues to allocate space for new objects.</span></span> <span data-ttu-id="04d5d-108">Тем не менее ресурсы памяти не безграничны.</span><span class="sxs-lookup"><span data-stu-id="04d5d-108">However, memory is not infinite.</span></span> <span data-ttu-id="04d5d-109">В конечном счете сборщику мусора необходимо выполнить сбор, чтобы освободить память.</span><span class="sxs-lookup"><span data-stu-id="04d5d-109">Eventually the garbage collector must perform a collection in order to free some memory.</span></span> <span data-ttu-id="04d5d-110">Механизм оптимизации сборщика мусора определяет наилучшее время для выполнения сбора, основываясь на выполненных операциях выделения памяти.</span><span class="sxs-lookup"><span data-stu-id="04d5d-110">The garbage collector's optimizing engine determines the best time to perform a collection, based upon the allocations being made.</span></span> <span data-ttu-id="04d5d-111">Когда сборщик мусора выполняет сборку, он проверяет наличие объектов в управляемой куче, которые больше не используются приложением, а затем выполняет необходимые операции, чтобы освободить память.</span><span class="sxs-lookup"><span data-stu-id="04d5d-111">When the garbage collector performs a collection, it checks for objects in the managed heap that are no longer being used by the application and performs the necessary operations to reclaim their memory.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="04d5d-112">Содержание раздела</span><span class="sxs-lookup"><span data-stu-id="04d5d-112">In this section</span></span>
  
|<span data-ttu-id="04d5d-113">Заголовок</span><span class="sxs-lookup"><span data-stu-id="04d5d-113">Title</span></span>|<span data-ttu-id="04d5d-114">Описание</span><span class="sxs-lookup"><span data-stu-id="04d5d-114">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="04d5d-115">Основы сборки мусора</span><span class="sxs-lookup"><span data-stu-id="04d5d-115">Fundamentals of garbage collection</span></span>](fundamentals.md)|<span data-ttu-id="04d5d-116">Описание работы сборки мусора, выделения объектов в управляемой куче и других базовых понятий.</span><span class="sxs-lookup"><span data-stu-id="04d5d-116">Describes how garbage collection works, how objects are allocated on the managed heap, and other core concepts.</span></span>|  
|[<span data-ttu-id="04d5d-117">Сборка мусора рабочей станции и сборка мусора сервера</span><span class="sxs-lookup"><span data-stu-id="04d5d-117">Workstation and server garbage collection</span></span>](workstation-server-gc.md)|<span data-ttu-id="04d5d-118">Описывает различия между сборкой мусора рабочей станции для клиентских приложений и сборкой мусора сервера для серверных приложений.</span><span class="sxs-lookup"><span data-stu-id="04d5d-118">Describes the differences between workstation garbage collection for client apps and server garbage collection for server apps.</span></span>|
|[<span data-ttu-id="04d5d-119">Фоновая сборка мусора</span><span class="sxs-lookup"><span data-stu-id="04d5d-119">Background garbage collection</span></span>](background-gc.md)|<span data-ttu-id="04d5d-120">Описывает фоновую сборку мусора, которая представляет собой сборку объектов поколения 0 и 1 во время сборки объектов поколения 2.</span><span class="sxs-lookup"><span data-stu-id="04d5d-120">Describes background garbage collection, which is the collection of generation 0 and 1 objects while generation 2 collection is in progress.</span></span>|
|[<span data-ttu-id="04d5d-121">Куча больших объектов</span><span class="sxs-lookup"><span data-stu-id="04d5d-121">The large object heap</span></span>](large-object-heap.md)|<span data-ttu-id="04d5d-122">Описывает кучу больших объектов (LOH) и то, как для них выполняется сборка мусора.</span><span class="sxs-lookup"><span data-stu-id="04d5d-122">Describes the large object heap (LOH) and how large objects are garbage-collected.</span></span>|
|[<span data-ttu-id="04d5d-123">Сборка мусора и производительность</span><span class="sxs-lookup"><span data-stu-id="04d5d-123">Garbage collection and performance</span></span>](performance.md)|<span data-ttu-id="04d5d-124">Проверки производительности, которые можно использовать для диагностики проблем со сборкой мусора и производительностью.</span><span class="sxs-lookup"><span data-stu-id="04d5d-124">Describes the performance checks you can use to diagnose garbage collection and performance issues.</span></span>|  
|[<span data-ttu-id="04d5d-125">Индуцированные коллекции</span><span class="sxs-lookup"><span data-stu-id="04d5d-125">Induced collections</span></span>](induced.md)|<span data-ttu-id="04d5d-126">Описание выполнения сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="04d5d-126">Describes how to make a garbage collection occur.</span></span>|  
|[<span data-ttu-id="04d5d-127">Режимы задержки</span><span class="sxs-lookup"><span data-stu-id="04d5d-127">Latency modes</span></span>](latency.md)|<span data-ttu-id="04d5d-128">Описание режимов, которые определяют степень вмешательства сборщика мусора.</span><span class="sxs-lookup"><span data-stu-id="04d5d-128">Describes the modes that determine the intrusiveness of garbage collection.</span></span>|  
|[<span data-ttu-id="04d5d-129">Оптимизация совместного размещения веб-сайтов</span><span class="sxs-lookup"><span data-stu-id="04d5d-129">Optimization for shared web hosting</span></span>](optimization-for-shared-web-hosting.md)|<span data-ttu-id="04d5d-130">Способы оптимизации сборки мусора на серверах, совместно используемыми небольшими веб-узлами.</span><span class="sxs-lookup"><span data-stu-id="04d5d-130">Describes how to optimize garbage collection on servers shared by several small Web sites.</span></span>|  
|[<span data-ttu-id="04d5d-131">Уведомления о сборке мусора</span><span class="sxs-lookup"><span data-stu-id="04d5d-131">Garbage collection notifications</span></span>](notifications.md)|<span data-ttu-id="04d5d-132">Определение необходимости полной сборки мусора и времени завершения этой операции.</span><span class="sxs-lookup"><span data-stu-id="04d5d-132">Describes how to determine when a full garbage collection is approaching and when it has completed.</span></span>|  
|[<span data-ttu-id="04d5d-133">Отслеживание ресурсов домена приложения</span><span class="sxs-lookup"><span data-stu-id="04d5d-133">Application domain resource monitoring</span></span>](app-domain-resource-monitoring.md)|<span data-ttu-id="04d5d-134">Способы наблюдения за использованием ЦП и памяти доменом приложения.</span><span class="sxs-lookup"><span data-stu-id="04d5d-134">Describes how to monitor CPU and memory usage by an application domain.</span></span>|  
|[<span data-ttu-id="04d5d-135">Слабые ссылки</span><span class="sxs-lookup"><span data-stu-id="04d5d-135">Weak references</span></span>](weak-references.md)|<span data-ttu-id="04d5d-136">Описание функциональных возможностей, которые позволяют сборщику мусора обрабатывать объект, разрешая при этом приложению получать доступ к этому объекту.</span><span class="sxs-lookup"><span data-stu-id="04d5d-136">Describes features that permit the garbage collector to collect an object while still allowing the application to access that object.</span></span>|  
  
## <a name="reference"></a><span data-ttu-id="04d5d-137">Справочник</span><span class="sxs-lookup"><span data-stu-id="04d5d-137">Reference</span></span>

- <xref:System.GC?displayProperty=nameWithType>  
- <xref:System.GCCollectionMode?displayProperty=nameWithType>  
- <xref:System.GCNotificationStatus?displayProperty=nameWithType>  
- <xref:System.Runtime.GCLatencyMode?displayProperty=nameWithType>  
- <xref:System.Runtime.GCSettings?displayProperty=nameWithType>  
- <xref:System.Runtime.GCSettings.LargeObjectHeapCompactionMode%2A?displayProperty=nameWithType>  
- <xref:System.Object.Finalize%2A?displayProperty=nameWithType>  
- <xref:System.IDisposable?displayProperty=nameWithType>  
  
## <a name="see-also"></a><span data-ttu-id="04d5d-138">См. также</span><span class="sxs-lookup"><span data-stu-id="04d5d-138">See also</span></span>

- [<span data-ttu-id="04d5d-139">Очистка неуправляемых ресурсов</span><span class="sxs-lookup"><span data-stu-id="04d5d-139">Clean up unmanaged resources</span></span>](unmanaged.md)
