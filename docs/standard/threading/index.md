---
title: Управляемая поточность
description: Ссылки на статьи об управляемых потоках в .NET, охватывающие основы, рекомендации, объекты и функции потоков, справочные страницы и многое другое.
ms.date: 03/30/2017
helpviewer_keywords:
- threading [.NET], about threading
- managed threading
ms.assetid: 7b46a7d9-c6f1-46d1-a947-ae97471bba87
ms.openlocfilehash: 28ba05c345d22b14512d280f3855934d727b3142
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728450"
---
# <a name="managed-threading"></a><span data-ttu-id="d3174-103">Управляемая поточность</span><span class="sxs-lookup"><span data-stu-id="d3174-103">Managed threading</span></span>

<span data-ttu-id="d3174-104">При разработке для компьютеров с одним или с несколькими процессорами необходимо, чтобы приложение обеспечивало наиболее эффективное взаимодействие с пользователем, даже если в приложении выполняются другие задачи.</span><span class="sxs-lookup"><span data-stu-id="d3174-104">Whether you're developing for computers with one processor or several, you want your application to provide the most responsive interaction with the user, even if the application is currently doing other work.</span></span> <span data-ttu-id="d3174-105">Использование нескольких потоков выполнения — это один из способов обеспечить в приложении возможность реагирования на действия пользователя при одновременном использовании процессора для выполнения задач между появлением или даже во время появления событий пользователя.</span><span class="sxs-lookup"><span data-stu-id="d3174-105">Using multiple threads of execution is one of the most powerful ways to keep your application responsive to the user and at the same time make use of the processor in between or even during user events.</span></span> <span data-ttu-id="d3174-106">Хотя в этом разделе приведены основные сведения о потоковом выполнении, здесь также рассматриваются принципы работы управляемых потоков и их использование.</span><span class="sxs-lookup"><span data-stu-id="d3174-106">While this section introduces the basic concepts of threading, it focuses on managed threading concepts and using managed threading.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d3174-107">Начиная с .NET Framework 4 многопоточное программирование значительно упростилось благодаря классам <xref:System.Threading.Tasks.Parallel?displayProperty=nameWithType> и <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>, [Parallel LINQ (PLINQ)](../parallel-programming/introduction-to-plinq.md), классам параллельных коллекций из пространства имен <xref:System.Collections.Concurrent?displayProperty=nameWithType> и модели программирования, которая вместо потоков использует концепцию задач.</span><span class="sxs-lookup"><span data-stu-id="d3174-107">Starting with .NET Framework 4, multithreaded programming is greatly simplified with the <xref:System.Threading.Tasks.Parallel?displayProperty=nameWithType> and <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> classes, [Parallel LINQ (PLINQ)](../parallel-programming/introduction-to-plinq.md), concurrent collection classes in the <xref:System.Collections.Concurrent?displayProperty=nameWithType> namespace, and a programming model that is based on the concept of tasks rather than threads.</span></span> <span data-ttu-id="d3174-108">Дополнительные сведения см. в разделе [Параллельное программирование](../parallel-programming/index.md).</span><span class="sxs-lookup"><span data-stu-id="d3174-108">For more information, see [Parallel Programming](../parallel-programming/index.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d3174-109">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="d3174-109">In This Section</span></span>  

 [<span data-ttu-id="d3174-110">Основы управляемых потоков</span><span class="sxs-lookup"><span data-stu-id="d3174-110">Managed Threading Basics</span></span>](managed-threading-basics.md)  
 <span data-ttu-id="d3174-111">Обзор управляемых потоков и случаев использования нескольких потоков.</span><span class="sxs-lookup"><span data-stu-id="d3174-111">Provides an overview of managed threading and discusses when to use multiple threads.</span></span>  
  
 [<span data-ttu-id="d3174-112">Использование потоков и работа с потоками</span><span class="sxs-lookup"><span data-stu-id="d3174-112">Using Threads and Threading</span></span>](using-threads-and-threading.md)  
 <span data-ttu-id="d3174-113">Описание способов создания, запуска, приостановки, возобновления и отмены потоков.</span><span class="sxs-lookup"><span data-stu-id="d3174-113">Explains how to create, start, pause, resume, and abort threads.</span></span>  
  
 [<span data-ttu-id="d3174-114">Рекомендации по работе с потоками</span><span class="sxs-lookup"><span data-stu-id="d3174-114">Managed Threading Best Practices</span></span>](managed-threading-best-practices.md)  
 <span data-ttu-id="d3174-115">Обсуждение уровней синхронизации, способов предотвращения взаимоблокировки и состояния гонки и других проблем, связанных с многопоточностью.</span><span class="sxs-lookup"><span data-stu-id="d3174-115">Discusses levels of synchronization, how to avoid deadlocks and race conditions, and other threading issues.</span></span>  
  
 [<span data-ttu-id="d3174-116">Объекты и функциональные возможности работы с потоками</span><span class="sxs-lookup"><span data-stu-id="d3174-116">Threading Objects and Features</span></span>](threading-objects-and-features.md)  
 <span data-ttu-id="d3174-117">Описание управляемых классов, которые можно использовать для синхронизации действий потоков и данных объектов, доступных в разных потоках, а также обзор пула потоков.</span><span class="sxs-lookup"><span data-stu-id="d3174-117">Describes the managed classes you can use to synchronize the activities of threads and the data of objects accessed on different threads, and provides an overview of thread pool threads.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="d3174-118">Справочник</span><span class="sxs-lookup"><span data-stu-id="d3174-118">Reference</span></span>  

 <xref:System.Threading>  
 <span data-ttu-id="d3174-119">Содержит классы для использования и синхронизации управляемых потоков.</span><span class="sxs-lookup"><span data-stu-id="d3174-119">Contains classes for using and synchronizing managed threads.</span></span>  
  
 <xref:System.Collections.Concurrent>  
 <span data-ttu-id="d3174-120">Содержит классы коллекций, которые могут безопасно использоваться несколькими потоками.</span><span class="sxs-lookup"><span data-stu-id="d3174-120">Contains collection classes that are safe for use with multiple threads.</span></span>  
  
 <xref:System.Threading.Tasks>  
 <span data-ttu-id="d3174-121">Содержит классы для создания и планирования задач параллельной обработки.</span><span class="sxs-lookup"><span data-stu-id="d3174-121">Contains classes for creating and scheduling concurrent processing tasks.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="d3174-122">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="d3174-122">Related Sections</span></span>  

 [<span data-ttu-id="d3174-123">Домены приложений</span><span class="sxs-lookup"><span data-stu-id="d3174-123">Application Domains</span></span>](../../framework/app-domains/application-domains.md)  
 <span data-ttu-id="d3174-124">Общие сведения о доменах приложений и их использовании в Common Language Infrastructure.</span><span class="sxs-lookup"><span data-stu-id="d3174-124">Provides an overview of application domains and their use by the Common Language Infrastructure.</span></span>  
  
 [<span data-ttu-id="d3174-125">Асинхронный файловый ввод-вывод</span><span class="sxs-lookup"><span data-stu-id="d3174-125">Asynchronous File I/O</span></span>](../io/asynchronous-file-i-o.md)  
 <span data-ttu-id="d3174-126">Описывает преимущества и основные операции асинхронного ввода и вывода.</span><span class="sxs-lookup"><span data-stu-id="d3174-126">Describes the performance advantages and basic operation of asynchronous I/O.</span></span>  
  
 <span data-ttu-id="d3174-127">[Task-based Asynchronous Pattern (TAP)](../asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md) (Асинхронный шаблон, основанный на задачах (TAP))</span><span class="sxs-lookup"><span data-stu-id="d3174-127">[Task-based Asynchronous Pattern (TAP)](../asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md)</span></span>  
 <span data-ttu-id="d3174-128">Предоставляет общие рекомендации по асинхронному программированию в .NET.</span><span class="sxs-lookup"><span data-stu-id="d3174-128">Provides an overview of the recommended pattern for asynchronous programming in .NET.</span></span>  
  
 [<span data-ttu-id="d3174-129">Асинхронный вызов синхронных методов</span><span class="sxs-lookup"><span data-stu-id="d3174-129">Calling Synchronous Methods Asynchronously</span></span>](../asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md)  
 <span data-ttu-id="d3174-130">Описание способов вызова методов в потоках пула потоков с помощью встроенных функций делегатов.</span><span class="sxs-lookup"><span data-stu-id="d3174-130">Explains how to call methods on thread pool threads using built-in features of delegates.</span></span>  
  
 [<span data-ttu-id="d3174-131">Параллельное программирование</span><span class="sxs-lookup"><span data-stu-id="d3174-131">Parallel Programming</span></span>](../parallel-programming/index.md)  
 <span data-ttu-id="d3174-132">Описание библиотек параллельного программирования, упрощающих использование нескольких потоков в приложениях.</span><span class="sxs-lookup"><span data-stu-id="d3174-132">Describes the parallel programming libraries, which simplify the use of multiple threads in applications.</span></span>  
  
 [<span data-ttu-id="d3174-133">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="d3174-133">Parallel LINQ (PLINQ)</span></span>](../parallel-programming/introduction-to-plinq.md)  
 <span data-ttu-id="d3174-134">Описание системы для выполнения запросов в параллельном режиме, позволяющей воспользоваться преимуществами нескольких процессоров.</span><span class="sxs-lookup"><span data-stu-id="d3174-134">Describes a system for running queries in parallel, to take advantage of multiple processors.</span></span>
