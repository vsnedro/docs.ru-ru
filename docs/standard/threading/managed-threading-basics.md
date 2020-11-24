---
title: Основы управляемых потоков
description: См. ссылки на другие статьи об управляемых потоках, охватывающие такие темы, как исключения, синхронизация данных, основные и фоновые потоки, локальное хранилище и многое другое.
ms.date: 03/30/2017
helpviewer_keywords:
- multiple threads
- threading [.NET], multiple threads
- threading [.NET], about threading
- managed threading
ms.assetid: b2944911-0e8f-427d-a8bb-077550618935
ms.openlocfilehash: 16785b1c21c5810e55429f6756dcf591c90d8499
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/18/2020
ms.locfileid: "94819673"
---
# <a name="managed-threading-basics"></a><span data-ttu-id="ed08f-103">Основы управляемых потоков</span><span class="sxs-lookup"><span data-stu-id="ed08f-103">Managed threading basics</span></span>

<span data-ttu-id="ed08f-104">Первые пять статей этого раздела помогут вам понять, в каких случаях уместно применять управляемые потоки, и предоставят описания их основных компонентов.</span><span class="sxs-lookup"><span data-stu-id="ed08f-104">The first five articles of this section are designed to help you determine when to use managed threading and to explain some basic features.</span></span> <span data-ttu-id="ed08f-105">Сведения о классах, которые предоставляют дополнительные возможности, вы найдете в статьях [Объекты и функциональные возможности работы с потоками](threading-objects-and-features.md) и [Обзор примитивов синхронизации](overview-of-synchronization-primitives.md).</span><span class="sxs-lookup"><span data-stu-id="ed08f-105">For information on classes that provide additional features, see [Threading Objects and Features](threading-objects-and-features.md) and [Overview of Synchronization Primitives](overview-of-synchronization-primitives.md).</span></span>  
  
 <span data-ttu-id="ed08f-106">Остальные статьи этого раздела посвящены дополнительным возможностям, включая взаимодействие управляемых потоков с операционной системой Windows.</span><span class="sxs-lookup"><span data-stu-id="ed08f-106">The remaining articles in this section cover advanced topics, including the interaction of managed threading with the Windows operating system.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ed08f-107">Начиная с .NET Framework 4, библиотека параллельных задач и PLINQ предоставляют интерфейсы API для поддержки параллелизма задач и данных в многопоточных программах.</span><span class="sxs-lookup"><span data-stu-id="ed08f-107">Starting with .NET Framework 4, the Task Parallel Library and PLINQ provide APIs for task and data parallelism in multi-threaded programs.</span></span> <span data-ttu-id="ed08f-108">Дополнительные сведения см. в разделе [Параллельное программирование](../parallel-programming/index.md).</span><span class="sxs-lookup"><span data-stu-id="ed08f-108">For more information, see [Parallel Programming](../parallel-programming/index.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ed08f-109">Содержание раздела</span><span class="sxs-lookup"><span data-stu-id="ed08f-109">In this section</span></span>

 [<span data-ttu-id="ed08f-110">Потоки и работа с потоками</span><span class="sxs-lookup"><span data-stu-id="ed08f-110">Threads and Threading</span></span>](threads-and-threading.md)  
 <span data-ttu-id="ed08f-111">Преимущества и недостатки использования нескольких потоков, а также описание сценариев, в которых целесообразно создавать потоки или использовать пул потоков.</span><span class="sxs-lookup"><span data-stu-id="ed08f-111">Discusses the advantages and drawbacks of multiple threads, and outlines the scenarios in which you might create threads or use thread pool threads.</span></span>  
  
 [<span data-ttu-id="ed08f-112">Исключения в управляемых потоках</span><span class="sxs-lookup"><span data-stu-id="ed08f-112">Exceptions in Managed Threads</span></span>](exceptions-in-managed-threads.md)  
 <span data-ttu-id="ed08f-113">Описание поведения необработанных исключений в потоках для разных версий .NET с особым вниманием к тем ситуациям, в которых они приведут к завершению работы приложения.</span><span class="sxs-lookup"><span data-stu-id="ed08f-113">Describes the behavior of unhandled exceptions in threads for different versions of .NET, in particular the situations in which they result in termination of the application.</span></span>  
  
 [<span data-ttu-id="ed08f-114">Синхронизация данных для многопоточности</span><span class="sxs-lookup"><span data-stu-id="ed08f-114">Synchronizing Data for Multithreading</span></span>](synchronizing-data-for-multithreading.md)  
 <span data-ttu-id="ed08f-115">Описание стратегий синхронизации данных в классах, которые следует применять при работе с несколькими потоками.</span><span class="sxs-lookup"><span data-stu-id="ed08f-115">Describes strategies for synchronizing data in classes that will be used with multiple threads.</span></span>  
  
 [<span data-ttu-id="ed08f-116">Основные и фоновые потоки</span><span class="sxs-lookup"><span data-stu-id="ed08f-116">Foreground and Background Threads</span></span>](foreground-and-background-threads.md)  
 <span data-ttu-id="ed08f-117">Описание различий между основными и фоновыми потоками.</span><span class="sxs-lookup"><span data-stu-id="ed08f-117">Explains the differences between foreground and background threads.</span></span>  
  
 [<span data-ttu-id="ed08f-118">Управляемые и неуправляемые потоки в Windows</span><span class="sxs-lookup"><span data-stu-id="ed08f-118">Managed and Unmanaged Threading in Windows</span></span>](managed-and-unmanaged-threading-in-windows.md)  
 <span data-ttu-id="ed08f-119">Описание соотношений между управляемыми и неуправляемыми потоками, список управляемых эквивалентов для работы с API-интерфейсами потоков в Windows, описание взаимодействий между подразделениями COM и управляемыми потоками.</span><span class="sxs-lookup"><span data-stu-id="ed08f-119">Discusses the relationship between managed and unmanaged threading, lists managed equivalents for Windows threading APIs, and discusses the interaction of COM apartments and managed threads.</span></span>  
  
 [<span data-ttu-id="ed08f-120">Локальное хранилище потока: статические поля потока и области данных</span><span class="sxs-lookup"><span data-stu-id="ed08f-120">Thread Local Storage: Thread-Relative Static Fields and Data Slots</span></span>](thread-local-storage-thread-relative-static-fields-and-data-slots.md)  
 <span data-ttu-id="ed08f-121">Описание механизмов хранения для отдельных потоков.</span><span class="sxs-lookup"><span data-stu-id="ed08f-121">Describes thread-relative storage mechanisms.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="ed08f-122">Справочник</span><span class="sxs-lookup"><span data-stu-id="ed08f-122">Reference</span></span>

 <xref:System.Threading.Thread>  
 <span data-ttu-id="ed08f-123">Справочная документация по классу **Thread**, который представляет управляемый поток вне зависимости от того, был ли он получен из неуправляемого кода или создан в управляемом приложении.</span><span class="sxs-lookup"><span data-stu-id="ed08f-123">Provides reference documentation for the **Thread** class, which represents a managed thread, whether it came from unmanaged code or was created in a managed application.</span></span>  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 <span data-ttu-id="ed08f-124">Описание безопасного подхода к многопоточности при работе с объектами пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="ed08f-124">Provides a safe way to implement multithreading in conjunction with user-interface objects.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="ed08f-125">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="ed08f-125">Related sections</span></span>

 [<span data-ttu-id="ed08f-126">Обзор примитивов синхронизации</span><span class="sxs-lookup"><span data-stu-id="ed08f-126">Overview of Synchronization Primitives</span></span>](overview-of-synchronization-primitives.md)  
 <span data-ttu-id="ed08f-127">Описание управляемых классов, которые применяются для синхронизации действий в нескольких потоках.</span><span class="sxs-lookup"><span data-stu-id="ed08f-127">Describes the managed classes used to synchronize the activities of multiple threads.</span></span>  
  
 [<span data-ttu-id="ed08f-128">Рекомендации по работе с потоками</span><span class="sxs-lookup"><span data-stu-id="ed08f-128">Managed Threading Best Practices</span></span>](managed-threading-best-practices.md)  
 <span data-ttu-id="ed08f-129">Описание распространенных проблем с многопоточностью и стратегий для предотвращения проблем.</span><span class="sxs-lookup"><span data-stu-id="ed08f-129">Describes common problems with multithreading and strategies for avoiding problems.</span></span>  
  
 [<span data-ttu-id="ed08f-130">Параллельное программирование</span><span class="sxs-lookup"><span data-stu-id="ed08f-130">Parallel Programming</span></span>](../parallel-programming/index.md)  
 <span data-ttu-id="ed08f-131">Описание библиотеки параллельных задач и PLINQ, которые существенно упрощают создание асинхронных и многопоточных приложений .NET.</span><span class="sxs-lookup"><span data-stu-id="ed08f-131">Describes the Task Parallel Library and PLINQ, which greatly simplify the work of creating asynchronous and multi-threaded .NET applications.</span></span>
