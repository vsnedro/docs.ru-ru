---
title: Шаблоны асинхронного программирования
description: Описание асинхронной модели на основе задач (TAP), асинхронной модели на основе событий (EAP) и асинхронной модели программирования (APM) в .NET.
ms.date: 10/16/2018
helpviewer_keywords:
- asynchronous design patterns, .NET
- .NET, asynchronous design patterns
ms.assetid: 4ece5c0b-f8fe-4114-9862-ac02cfe5a5d7
ms.openlocfilehash: bc0e37c060ab6375f943b4b50053e3046c05a556
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/18/2020
ms.locfileid: "94830341"
---
# <a name="asynchronous-programming-patterns"></a><span data-ttu-id="fbddd-103">Шаблоны асинхронного программирования</span><span class="sxs-lookup"><span data-stu-id="fbddd-103">Asynchronous programming patterns</span></span>

<span data-ttu-id="fbddd-104">В .NET есть три шаблона для выполнения асинхронных операций:</span><span class="sxs-lookup"><span data-stu-id="fbddd-104">.NET provides three patterns for performing asynchronous operations:</span></span>  

- <span data-ttu-id="fbddd-105">**Асинхронный шаблон на основе задач (TAP)** , который использует один метод для запуска и завершения асинхронной операции.</span><span class="sxs-lookup"><span data-stu-id="fbddd-105">**Task-based Asynchronous Pattern (TAP)**, which uses a single method to represent the initiation and completion of an asynchronous operation.</span></span> <span data-ttu-id="fbddd-106">Шаблон TAP был реализован в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="fbddd-106">TAP was introduced in .NET Framework 4.</span></span> <span data-ttu-id="fbddd-107">**Именно его рекомендуется использовать для асинхронного программирования в .NET**.</span><span class="sxs-lookup"><span data-stu-id="fbddd-107">**It's the recommended approach to asynchronous programming in .NET.**</span></span> <span data-ttu-id="fbddd-108">Ключевые слова [async](../../csharp/language-reference/keywords/async.md) и [await](../../csharp/language-reference/operators/await.md) в C#, а также операторы [Async](../../visual-basic/language-reference/modifiers/async.md) и [Await](../../visual-basic/language-reference/operators/await-operator.md) в Visual Basic добавляют для TAP поддержку языка.</span><span class="sxs-lookup"><span data-stu-id="fbddd-108">The [async](../../csharp/language-reference/keywords/async.md) and [await](../../csharp/language-reference/operators/await.md) keywords in C# and the [Async](../../visual-basic/language-reference/modifiers/async.md) and [Await](../../visual-basic/language-reference/operators/await-operator.md) operators in Visual Basic add language support for TAP.</span></span> <span data-ttu-id="fbddd-109">Дополнительные сведения см. в разделе [Асинхронный шаблон, основанный на задачах (TAP)](task-based-asynchronous-pattern-tap.md).</span><span class="sxs-lookup"><span data-stu-id="fbddd-109">For more information, see [Task-based Asynchronous Pattern (TAP)](task-based-asynchronous-pattern-tap.md).</span></span>  

- <span data-ttu-id="fbddd-110">**Асинхронная модель на основе событий (EAP)** . Это устаревшая модель на основе событий, обеспечивающая работу в асинхронном режиме.</span><span class="sxs-lookup"><span data-stu-id="fbddd-110">**Event-based Asynchronous Pattern (EAP)**, which is the event-based legacy model for providing asynchronous behavior.</span></span> <span data-ttu-id="fbddd-111">Для нее требуется метод с суффиксом `Async`, одно или несколько событий, типы делегатов обработчика событий и производные типы `EventArg`.</span><span class="sxs-lookup"><span data-stu-id="fbddd-111">It requires a method that has the `Async` suffix and one or more events, event handler delegate types, and `EventArg`-derived types.</span></span> <span data-ttu-id="fbddd-112">Модель EAP была реализована в .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="fbddd-112">EAP was introduced in .NET Framework 2.0.</span></span> <span data-ttu-id="fbddd-113">Ее не рекомендуется использовать для новых разработок.</span><span class="sxs-lookup"><span data-stu-id="fbddd-113">It's no longer recommended for new development.</span></span> <span data-ttu-id="fbddd-114">Дополнительные сведения см. в разделе [Асинхронная модель на основе событий (EAP)](event-based-asynchronous-pattern-eap.md).</span><span class="sxs-lookup"><span data-stu-id="fbddd-114">For more information, see [Event-based Asynchronous Pattern (EAP)](event-based-asynchronous-pattern-eap.md).</span></span>  

- <span data-ttu-id="fbddd-115">**Модель асинхронного программирования (APM)** (также называется шаблоном <xref:System.IAsyncResult>). Это устаревшая модель, в которой для реализации асинхронного поведения используется интерфейс <xref:System.IAsyncResult>.</span><span class="sxs-lookup"><span data-stu-id="fbddd-115">**Asynchronous Programming Model (APM)** pattern (also called the <xref:System.IAsyncResult> pattern), which is the legacy model that uses the <xref:System.IAsyncResult> interface to provide asynchronous behavior.</span></span> <span data-ttu-id="fbddd-116">В этом шаблоне для синхронных операций требуются методы `Begin` и `End` (например, `BeginWrite` и `EndWrite` позволяют реализовать асинхронную операцию записи).</span><span class="sxs-lookup"><span data-stu-id="fbddd-116">In this pattern, synchronous operations require `Begin` and `End` methods (for example, `BeginWrite` and `EndWrite` to implement an asynchronous write operation).</span></span> <span data-ttu-id="fbddd-117">Этот шаблон не рекомендуется использовать для разработки новых приложений.</span><span class="sxs-lookup"><span data-stu-id="fbddd-117">This pattern is no longer recommended for new development.</span></span> <span data-ttu-id="fbddd-118">Дополнительные сведения см. в статье [Асинхронная модель программирования (APM)](asynchronous-programming-model-apm.md).</span><span class="sxs-lookup"><span data-stu-id="fbddd-118">For more information, see [Asynchronous Programming Model (APM)](asynchronous-programming-model-apm.md).</span></span>  
  
## <a name="comparison-of-patterns"></a><span data-ttu-id="fbddd-119">Сравнение шаблонов</span><span class="sxs-lookup"><span data-stu-id="fbddd-119">Comparison of patterns</span></span>

<span data-ttu-id="fbddd-120">Для быстрого сравнения, как с помощью трех шаблонов моделировать асинхронные операции, рассмотрим метод `Read`, который считывает указанный объем данных в предоставленный буфер, начиная с заданного смещения:</span><span class="sxs-lookup"><span data-stu-id="fbddd-120">For a quick comparison of how the three patterns model asynchronous operations, consider a `Read` method that reads a specified amount of data into a provided buffer starting at a specified offset:</span></span>  
  
```csharp  
public class MyClass  
{  
    public int Read(byte [] buffer, int offset, int count);  
}  
```  

<span data-ttu-id="fbddd-121">Этот же метод с использованием TAP предоставит такой метод `ReadAsync`:</span><span class="sxs-lookup"><span data-stu-id="fbddd-121">The TAP counterpart of this method would expose the following single `ReadAsync` method:</span></span>  
  
```csharp
public class MyClass  
{  
    public Task<int> ReadAsync(byte [] buffer, int offset, int count);  
}  
```

<span data-ttu-id="fbddd-122">Аналог EAP будут предоставлять следующий набор типов и членов:</span><span class="sxs-lookup"><span data-stu-id="fbddd-122">The EAP counterpart would expose the following set of types and members:</span></span>  
  
```csharp  
public class MyClass  
{  
    public void ReadAsync(byte [] buffer, int offset, int count);  
    public event ReadCompletedEventHandler ReadCompleted;  
}  
```  
  
<span data-ttu-id="fbddd-123">Этот же метод с APM предоставит методы `BeginRead` и `EndRead`:</span><span class="sxs-lookup"><span data-stu-id="fbddd-123">The APM counterpart would expose the `BeginRead` and `EndRead` methods:</span></span>  
  
```csharp  
public class MyClass  
{  
    public IAsyncResult BeginRead(  
        byte [] buffer, int offset, int count,
        AsyncCallback callback, object state);  
    public int EndRead(IAsyncResult asyncResult);  
}  
```  

## <a name="see-also"></a><span data-ttu-id="fbddd-124">См. также</span><span class="sxs-lookup"><span data-stu-id="fbddd-124">See also</span></span>

- [<span data-ttu-id="fbddd-125">Подробный обзор асинхронного программирования</span><span class="sxs-lookup"><span data-stu-id="fbddd-125">Async in depth</span></span>](../async-in-depth.md)
- [<span data-ttu-id="fbddd-126">Асинхронное программирование на C#</span><span class="sxs-lookup"><span data-stu-id="fbddd-126">Asynchronous programming in C#</span></span>](../../csharp/async.md)
- [<span data-ttu-id="fbddd-127">Асинхронное программирование на F#</span><span class="sxs-lookup"><span data-stu-id="fbddd-127">Async Programming in F#</span></span>](../../fsharp/tutorials/asynchronous-and-concurrent-programming/async.md)
- [<span data-ttu-id="fbddd-128">Асинхронное программирование с использованием ключевых слов Async и Await (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fbddd-128">Asynchronous Programming with Async and Await (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/async/index.md)
