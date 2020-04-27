---
title: Сборка мусора .NET
ms.date: 04/21/2020
ms.technology: dotnet-standard
helpviewer_keywords:
- memory, garbage collection
- garbage collection, automatic memory management
- GC [.NET Framework]
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
ms.openlocfilehash: c087deb033a373dd8b3980feb7ec6901c7909569
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102246"
---
# <a name="garbage-collection"></a><span data-ttu-id="17d7e-102">Сборка мусора</span><span class="sxs-lookup"><span data-stu-id="17d7e-102">Garbage collection</span></span>

<span data-ttu-id="17d7e-103">Сборщик мусора .NET управляет выделением и освобождением памяти для приложения.</span><span class="sxs-lookup"><span data-stu-id="17d7e-103">.NET's garbage collector manages the allocation and release of memory for your application.</span></span> <span data-ttu-id="17d7e-104">При каждом создании объекта среда CLR выделяет память для объекта из управляемой кучи.</span><span class="sxs-lookup"><span data-stu-id="17d7e-104">Each time you create a new object, the common language runtime allocates memory for the object from the managed heap.</span></span> <span data-ttu-id="17d7e-105">Пока в управляемой куче есть доступное адресное пространство, среда выполнения продолжает выделять пространство для новых объектов.</span><span class="sxs-lookup"><span data-stu-id="17d7e-105">As long as address space is available in the managed heap, the runtime continues to allocate space for new objects.</span></span> <span data-ttu-id="17d7e-106">Тем не менее ресурсы памяти не безграничны.</span><span class="sxs-lookup"><span data-stu-id="17d7e-106">However, memory is not infinite.</span></span> <span data-ttu-id="17d7e-107">В конечном счете сборщику мусора необходимо выполнить сбор, чтобы освободить память.</span><span class="sxs-lookup"><span data-stu-id="17d7e-107">Eventually the garbage collector must perform a collection in order to free some memory.</span></span> <span data-ttu-id="17d7e-108">Механизм оптимизации сборщика мусора определяет наилучшее время для выполнения сбора, основываясь на выполненных операциях выделения памяти.</span><span class="sxs-lookup"><span data-stu-id="17d7e-108">The garbage collector's optimizing engine determines the best time to perform a collection, based upon the allocations being made.</span></span> <span data-ttu-id="17d7e-109">Когда сборщик мусора выполняет сборку, он проверяет наличие объектов в управляемой куче, которые больше не используются приложением, а затем выполняет необходимые операции, чтобы освободить память.</span><span class="sxs-lookup"><span data-stu-id="17d7e-109">When the garbage collector performs a collection, it checks for objects in the managed heap that are no longer being used by the application and performs the necessary operations to reclaim their memory.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="17d7e-110">Содержание раздела</span><span class="sxs-lookup"><span data-stu-id="17d7e-110">In this section</span></span>
  
|<span data-ttu-id="17d7e-111">Заголовок</span><span class="sxs-lookup"><span data-stu-id="17d7e-111">Title</span></span>|<span data-ttu-id="17d7e-112">Описание</span><span class="sxs-lookup"><span data-stu-id="17d7e-112">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="17d7e-113">Основы сборки мусора</span><span class="sxs-lookup"><span data-stu-id="17d7e-113">Fundamentals of garbage collection</span></span>](../../../docs/standard/garbage-collection/fundamentals.md)|<span data-ttu-id="17d7e-114">Описание работы сборки мусора, выделения объектов в управляемой куче и других базовых понятий.</span><span class="sxs-lookup"><span data-stu-id="17d7e-114">Describes how garbage collection works, how objects are allocated on the managed heap, and other core concepts.</span></span>|  
|[<span data-ttu-id="17d7e-115">Сборка мусора рабочей станции и сборка мусора сервера</span><span class="sxs-lookup"><span data-stu-id="17d7e-115">Workstation and server garbage collection</span></span>](workstation-server-gc.md)|<span data-ttu-id="17d7e-116">Описывает различия между сборкой мусора рабочей станции для клиентских приложений и сборкой мусора сервера для серверных приложений.</span><span class="sxs-lookup"><span data-stu-id="17d7e-116">Describes the differences between workstation garbage collection for client apps and server garbage collection for server apps.</span></span>|
|[<span data-ttu-id="17d7e-117">Фоновая сборка мусора</span><span class="sxs-lookup"><span data-stu-id="17d7e-117">Background garbage collection</span></span>](background-gc.md)|<span data-ttu-id="17d7e-118">Описывает фоновую сборку мусора, которая представляет собой сборку объектов поколения 0 и 1 во время сборки объектов поколения 2.</span><span class="sxs-lookup"><span data-stu-id="17d7e-118">Describes background garbage collection, which is the collection of generation 0 and 1 objects while generation 2 collection is in progress.</span></span>|
|[<span data-ttu-id="17d7e-119">Куча больших объектов</span><span class="sxs-lookup"><span data-stu-id="17d7e-119">The large object heap</span></span>](large-object-heap.md)|<span data-ttu-id="17d7e-120">Описывает кучу больших объектов (LOH) и то, как для них выполняется сборка мусора.</span><span class="sxs-lookup"><span data-stu-id="17d7e-120">Describes the large object heap (LOH) and how large objects are garbage-collected.</span></span>|
|[<span data-ttu-id="17d7e-121">Сборка мусора и производительность</span><span class="sxs-lookup"><span data-stu-id="17d7e-121">Garbage collection and performance</span></span>](../../../docs/standard/garbage-collection/performance.md)|<span data-ttu-id="17d7e-122">Проверки производительности, которые можно использовать для диагностики проблем со сборкой мусора и производительностью.</span><span class="sxs-lookup"><span data-stu-id="17d7e-122">Describes the performance checks you can use to diagnose garbage collection and performance issues.</span></span>|  
|[<span data-ttu-id="17d7e-123">Индуцированные коллекции</span><span class="sxs-lookup"><span data-stu-id="17d7e-123">Induced collections</span></span>](../../../docs/standard/garbage-collection/induced.md)|<span data-ttu-id="17d7e-124">Описание выполнения сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="17d7e-124">Describes how to make a garbage collection occur.</span></span>|  
|[<span data-ttu-id="17d7e-125">Режимы задержки</span><span class="sxs-lookup"><span data-stu-id="17d7e-125">Latency modes</span></span>](../../../docs/standard/garbage-collection/latency.md)|<span data-ttu-id="17d7e-126">Описание режимов, которые определяют степень вмешательства сборщика мусора.</span><span class="sxs-lookup"><span data-stu-id="17d7e-126">Describes the modes that determine the intrusiveness of garbage collection.</span></span>|  
|[<span data-ttu-id="17d7e-127">Оптимизация совместного размещения веб-сайтов</span><span class="sxs-lookup"><span data-stu-id="17d7e-127">Optimization for shared web hosting</span></span>](../../../docs/standard/garbage-collection/optimization-for-shared-web-hosting.md)|<span data-ttu-id="17d7e-128">Способы оптимизации сборки мусора на серверах, совместно используемыми небольшими веб-узлами.</span><span class="sxs-lookup"><span data-stu-id="17d7e-128">Describes how to optimize garbage collection on servers shared by several small Web sites.</span></span>|  
|[<span data-ttu-id="17d7e-129">Уведомления о сборке мусора</span><span class="sxs-lookup"><span data-stu-id="17d7e-129">Garbage collection notifications</span></span>](../../../docs/standard/garbage-collection/notifications.md)|<span data-ttu-id="17d7e-130">Определение необходимости полной сборки мусора и времени завершения этой операции.</span><span class="sxs-lookup"><span data-stu-id="17d7e-130">Describes how to determine when a full garbage collection is approaching and when it has completed.</span></span>|  
|[<span data-ttu-id="17d7e-131">Отслеживание ресурсов домена приложения</span><span class="sxs-lookup"><span data-stu-id="17d7e-131">Application domain resource monitoring</span></span>](../../../docs/standard/garbage-collection/app-domain-resource-monitoring.md)|<span data-ttu-id="17d7e-132">Способы наблюдения за использованием ЦП и памяти доменом приложения.</span><span class="sxs-lookup"><span data-stu-id="17d7e-132">Describes how to monitor CPU and memory usage by an application domain.</span></span>|  
|[<span data-ttu-id="17d7e-133">Слабые ссылки</span><span class="sxs-lookup"><span data-stu-id="17d7e-133">Weak references</span></span>](../../../docs/standard/garbage-collection/weak-references.md)|<span data-ttu-id="17d7e-134">Описание функциональных возможностей, которые позволяют сборщику мусора обрабатывать объект, разрешая при этом приложению получать доступ к этому объекту.</span><span class="sxs-lookup"><span data-stu-id="17d7e-134">Describes features that permit the garbage collector to collect an object while still allowing the application to access that object.</span></span>|  
  
## <a name="reference"></a><span data-ttu-id="17d7e-135">Справочник</span><span class="sxs-lookup"><span data-stu-id="17d7e-135">Reference</span></span>

- <xref:System.GC?displayProperty=nameWithType>  
- <xref:System.GCCollectionMode?displayProperty=nameWithType>  
- <xref:System.GCNotificationStatus?displayProperty=nameWithType>  
- <xref:System.Runtime.GCLatencyMode?displayProperty=nameWithType>  
- <xref:System.Runtime.GCSettings?displayProperty=nameWithType>  
- <xref:System.Runtime.GCSettings.LargeObjectHeapCompactionMode%2A?displayProperty=nameWithType>  
- <xref:System.Object.Finalize%2A?displayProperty=nameWithType>  
- <xref:System.IDisposable?displayProperty=nameWithType>  
  
## <a name="see-also"></a><span data-ttu-id="17d7e-136">См. также</span><span class="sxs-lookup"><span data-stu-id="17d7e-136">See also</span></span>

- [<span data-ttu-id="17d7e-137">Очистка неуправляемых ресурсов</span><span class="sxs-lookup"><span data-stu-id="17d7e-137">Clean up unmanaged resources</span></span>](../../../docs/standard/garbage-collection/unmanaged.md)
