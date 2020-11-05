---
title: Асинхронная модель на основе событий (EAP)
description: См. ссылки на статьи, посвященные асинхронной модели на основе событий (EAP) в .NET, в том числе с информацией о реализации, рекомендациях, реализации клиента EAP и многом другом.
ms.date: 07/23/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- asynchronous calls
- asynchronous programming, design patterns
- asynchronous programming
ms.assetid: c6baed9f-2a25-4728-9a9a-53b7b14840cf
ms.openlocfilehash: 16aabeb55a56c63449a865d00044c463657de740
ms.sourcegitcommit: 4a938327bad8b2e20cabd0f46a9dc50882596f13
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/28/2020
ms.locfileid: "92888845"
---
# <a name="event-based-asynchronous-pattern-eap"></a><span data-ttu-id="7f6cc-103">Асинхронная модель на основе событий (EAP)</span><span class="sxs-lookup"><span data-stu-id="7f6cc-103">Event-based Asynchronous Pattern (EAP)</span></span>

<span data-ttu-id="7f6cc-104">Существует несколько способов предоставить асинхронные возможности клиентскому коду.</span><span class="sxs-lookup"><span data-stu-id="7f6cc-104">There are a number of ways to expose asynchronous features to client code.</span></span> <span data-ttu-id="7f6cc-105">Асинхронная модель на основе событий задает для классов рекомендуемый способ работы в асинхронном режиме.</span><span class="sxs-lookup"><span data-stu-id="7f6cc-105">The Event-based Asynchronous Pattern prescribes one way for classes to present asynchronous behavior.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7f6cc-106">Начиная с версии .NET Framework 4, библиотека параллельных задач предоставляет новую модель для асинхронного и параллельного программирования.</span><span class="sxs-lookup"><span data-stu-id="7f6cc-106">Starting with .NET Framework 4, the Task Parallel Library provides a new model for asynchronous and parallel programming.</span></span> <span data-ttu-id="7f6cc-107">Дополнительные сведения см. в разделах [Библиотека параллельных задач (TPL)](../parallel-programming/task-parallel-library-tpl.md) и [Асинхронная модель на основе задач (TAP)](task-based-asynchronous-pattern-tap.md).</span><span class="sxs-lookup"><span data-stu-id="7f6cc-107">For more information, see [Task Parallel Library (TPL)](../parallel-programming/task-parallel-library-tpl.md) and [Task-based Asynchronous Pattern (TAP)](task-based-asynchronous-pattern-tap.md).</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="7f6cc-108">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="7f6cc-108">In This Section</span></span>

 [<span data-ttu-id="7f6cc-109">Обзор асинхронной модели, основанной на событиях</span><span class="sxs-lookup"><span data-stu-id="7f6cc-109">Event-based Asynchronous Pattern Overview</span></span>](event-based-asynchronous-pattern-overview.md)  
 <span data-ttu-id="7f6cc-110">Описывает, как асинхронная модель на основе событий позволяет использовать преимущества многопоточных приложений и устраняет многие сложности, присущие многопоточности.</span><span class="sxs-lookup"><span data-stu-id="7f6cc-110">Describes how the Event-based Asynchronous Pattern makes available the advantages of multithreaded applications while hiding many of the complex issues inherent in multithreaded design.</span></span>  
  
 [<span data-ttu-id="7f6cc-111">Реализация асинхронной модели, основанной на событиях</span><span class="sxs-lookup"><span data-stu-id="7f6cc-111">Implementing the Event-based Asynchronous Pattern</span></span>](implementing-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="7f6cc-112">Описывает стандартизированный способ упаковки класса, имеющего асинхронные возможности.</span><span class="sxs-lookup"><span data-stu-id="7f6cc-112">Describes the standardized way to package a class that has asynchronous features.</span></span>  
  
 [<span data-ttu-id="7f6cc-113">Рекомендации по реализации асинхронной модели, основанной на событиях</span><span class="sxs-lookup"><span data-stu-id="7f6cc-113">Best Practices for Implementing the Event-based Asynchronous Pattern</span></span>](best-practices-for-implementing-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="7f6cc-114">Описывает требования для предоставления асинхронных возможностей в соответствии с асинхронной моделью на основе событий.</span><span class="sxs-lookup"><span data-stu-id="7f6cc-114">Describes the requirements for exposing asynchronous features according to the Event-based Asynchronous Pattern.</span></span>  
  
 [<span data-ttu-id="7f6cc-115">Определение, когда следует реализовать асинхронную модель, основанную на событиях</span><span class="sxs-lookup"><span data-stu-id="7f6cc-115">Deciding When to Implement the Event-based Asynchronous Pattern</span></span>](deciding-when-to-implement-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="7f6cc-116">Описывает, в каких случаях следует реализовать асинхронную модель на основе событий вместо шаблона <xref:System.IAsyncResult>, представленного [асинхронной моделью программирования (APM)](asynchronous-programming-model-apm.md)</span><span class="sxs-lookup"><span data-stu-id="7f6cc-116">Describes how to determine when you should choose to implement the Event-based Asynchronous Pattern instead of the <xref:System.IAsyncResult> pattern represented by the [Asynchronous Programming Model (APM)](asynchronous-programming-model-apm.md)</span></span>
  
 [<span data-ttu-id="7f6cc-117">Практическое руководство. Реализация компонента, поддерживающего асинхронную модель на основе событий</span><span class="sxs-lookup"><span data-stu-id="7f6cc-117">How to: Implement a Component That Supports the Event-based Asynchronous Pattern</span></span>](component-that-supports-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="7f6cc-118">Описывает, как создать компонент, реализующий асинхронную модель на основе событий.</span><span class="sxs-lookup"><span data-stu-id="7f6cc-118">Describes how to create a component that implements the Event-based Asynchronous Pattern.</span></span> <span data-ttu-id="7f6cc-119">Она реализуется с использованием вспомогательных классов из пространства имен <xref:System.ComponentModel?displayProperty=nameWithType>, что обеспечивает правильную работу компонента при любой модели приложения.</span><span class="sxs-lookup"><span data-stu-id="7f6cc-119">It is implemented using helper classes from the <xref:System.ComponentModel?displayProperty=nameWithType> namespace, which ensures that the component works correctly under any application model.</span></span>  

 [<span data-ttu-id="7f6cc-120">Практическое руководство. Реализация клиента асинхронной модели на основе событий</span><span class="sxs-lookup"><span data-stu-id="7f6cc-120">How to: Implement a Client of the Event-based Asynchronous Pattern</span></span>](how-to-implement-a-client-of-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="7f6cc-121">Описывает, как создать клиент, который использует компонент, реализующий асинхронную модель на основе событий.</span><span class="sxs-lookup"><span data-stu-id="7f6cc-121">Describes how to create a client that uses a component that implements the Event-based Asynchronous Pattern.</span></span>
  
 [<span data-ttu-id="7f6cc-122">Практическое руководство. Использование компонентов, поддерживающих асинхронную модель, основанную на событиях</span><span class="sxs-lookup"><span data-stu-id="7f6cc-122">How to: Use Components That Support the Event-based Asynchronous Pattern</span></span>](how-to-use-components-that-support-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="7f6cc-123">Описывает использование компонента, поддерживающего асинхронную модель на основе событий.</span><span class="sxs-lookup"><span data-stu-id="7f6cc-123">Describes how to use a component that supports the Event-based Asynchronous Pattern.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="7f6cc-124">Справочник</span><span class="sxs-lookup"><span data-stu-id="7f6cc-124">Reference</span></span>

 <xref:System.ComponentModel.AsyncOperation>  
 <span data-ttu-id="7f6cc-125">Описывает класс <xref:System.ComponentModel.AsyncOperation> и содержит ссылки на все его члены.</span><span class="sxs-lookup"><span data-stu-id="7f6cc-125">Describes the <xref:System.ComponentModel.AsyncOperation> class and has links to all its members.</span></span>  
  
 <xref:System.ComponentModel.AsyncOperationManager>  
 <span data-ttu-id="7f6cc-126">Описывает класс <xref:System.ComponentModel.AsyncOperationManager> и содержит ссылки на все его члены.</span><span class="sxs-lookup"><span data-stu-id="7f6cc-126">Describes the <xref:System.ComponentModel.AsyncOperationManager> class and has links to all its members.</span></span>  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 <span data-ttu-id="7f6cc-127">Описывает компонент <xref:System.ComponentModel.BackgroundWorker> и содержит ссылки на все его члены.</span><span class="sxs-lookup"><span data-stu-id="7f6cc-127">Describes the <xref:System.ComponentModel.BackgroundWorker> component and has links to all its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="7f6cc-128">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="7f6cc-128">Related Sections</span></span>

 [<span data-ttu-id="7f6cc-129">Библиотека параллельных задач (TPL)</span><span class="sxs-lookup"><span data-stu-id="7f6cc-129">Task Parallel Library (TPL)</span></span>](../parallel-programming/task-parallel-library-tpl.md)  
 <span data-ttu-id="7f6cc-130">Описание модели программирования для асинхронных и параллельных операций.</span><span class="sxs-lookup"><span data-stu-id="7f6cc-130">Describes a programming model for asynchronous and parallel operations.</span></span>  
  
 [<span data-ttu-id="7f6cc-131">Работа с потоками</span><span class="sxs-lookup"><span data-stu-id="7f6cc-131">Threading</span></span>](../threading/index.md)  
 <span data-ttu-id="7f6cc-132">Описывает многопоточные функциональные возможности в .NET.</span><span class="sxs-lookup"><span data-stu-id="7f6cc-132">Describes multithreading features in .NET.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f6cc-133">См. также</span><span class="sxs-lookup"><span data-stu-id="7f6cc-133">See also</span></span>

- [<span data-ttu-id="7f6cc-134">Рекомендации по работе с потоками</span><span class="sxs-lookup"><span data-stu-id="7f6cc-134">Managed Threading Best Practices</span></span>](../threading/managed-threading-best-practices.md)
- [<span data-ttu-id="7f6cc-135">События</span><span class="sxs-lookup"><span data-stu-id="7f6cc-135">Events</span></span>](../events/index.md)
- [<span data-ttu-id="7f6cc-136">Шаблоны асинхронного программирования</span><span class="sxs-lookup"><span data-stu-id="7f6cc-136">Asynchronous Programming Design Patterns</span></span>](index.md)
