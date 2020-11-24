---
title: Использование объектов, реализующих IDisposable
description: Узнайте, как использовать объекты, реализующие интерфейс IDisposable в .NET. Типы, использующие неуправляемые ресурсы, реализуют IDisposable, чтобы обеспечить высвобождение ресурсов.
ms.date: 05/13/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Dispose method
- try/finally block
- garbage collection, encapsulating resources
ms.assetid: 81b2cdb5-c91a-4a31-9c83-eadc52da5cf0
ms.openlocfilehash: 50769bdf684f6eb3a51dc2bd00c6a774a02976b7
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/18/2020
ms.locfileid: "94827455"
---
# <a name="using-objects-that-implement-idisposable"></a><span data-ttu-id="eabf3-104">Использование объектов, реализующих IDisposable</span><span class="sxs-lookup"><span data-stu-id="eabf3-104">Using objects that implement IDisposable</span></span>

<span data-ttu-id="eabf3-105">Сборщик мусора среды CLR освобождает память, используемую управляемыми объектами. Но типы, которые используют неуправляемые ресурсы, реализуют интерфейс <xref:System.IDisposable>, который позволяет освободить ресурсы, которые требуются этим неуправляемым ресурсам.</span><span class="sxs-lookup"><span data-stu-id="eabf3-105">The common language runtime's garbage collector reclaims the memory used by managed objects, but types that use unmanaged resources implement the <xref:System.IDisposable> interface to allow the resources needed by these unmanaged resources to be reclaimed.</span></span> <span data-ttu-id="eabf3-106">По окончании использования объекта, который реализует интерфейс <xref:System.IDisposable>, необходимо вызвать реализацию объекта <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="eabf3-106">When you finish using an object that implements <xref:System.IDisposable>, you should call the object's <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> implementation.</span></span> <span data-ttu-id="eabf3-107">Это можно сделать одним из двух способов.</span><span class="sxs-lookup"><span data-stu-id="eabf3-107">You can do this in one of two ways:</span></span>

- <span data-ttu-id="eabf3-108">С помощью оператора `using` (C#) или `Using` (Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="eabf3-108">With the C# `using` statement (`Using` in Visual Basic).</span></span>
- <span data-ttu-id="eabf3-109">Путем реализации блока `try/finally` и вызова <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> в `finally`.</span><span class="sxs-lookup"><span data-stu-id="eabf3-109">By implementing a `try/finally` block, and calling the <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> in the `finally`.</span></span>

## <a name="the-using-statement"></a><span data-ttu-id="eabf3-110">Оператор using</span><span class="sxs-lookup"><span data-stu-id="eabf3-110">The using statement</span></span>

<span data-ttu-id="eabf3-111">[Оператор `using`](../../csharp/language-reference/keywords/using-statement.md) (C#) и [оператор `Using`](../../visual-basic/language-reference/statements/using-statement.md) (Visual Basic) упрощают написание кода для очистки объекта.</span><span class="sxs-lookup"><span data-stu-id="eabf3-111">The [`using` statement](../../csharp/language-reference/keywords/using-statement.md) in C# and the [`Using` statement](../../visual-basic/language-reference/statements/using-statement.md) in Visual Basic simplify the code that you must write to cleanup an object.</span></span> <span data-ttu-id="eabf3-112">Оператор `using` получает один или больше ресурсов, выполняет заданные операторы, после чего автоматически освобождает объект.</span><span class="sxs-lookup"><span data-stu-id="eabf3-112">The `using` statement obtains one or more resources, executes the statements that you specify, and automatically disposes of the object.</span></span> <span data-ttu-id="eabf3-113">Однако оператор `using` полезен только для объектов в области действия метода, в котором они созданы.</span><span class="sxs-lookup"><span data-stu-id="eabf3-113">However, the `using` statement is useful only for objects that are used within the scope of the method in which they are constructed.</span></span>

<span data-ttu-id="eabf3-114">В следующем примере для создания и освобождения объекта `using` используется оператор <xref:System.IO.StreamReader?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="eabf3-114">The following example uses the `using` statement to create and release a <xref:System.IO.StreamReader?displayProperty=nameWithType> object.</span></span>

[!code-csharp[Conceptual.Disposable#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/using1.cs#1)]
[!code-vb[Conceptual.Disposable#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/using1.vb#1)]

<span data-ttu-id="eabf3-115">Хотя класс <xref:System.IO.StreamReader> реализует интерфейс <xref:System.IDisposable>, который указывает, что используется неуправляемый ресурс, пример явно не вызывает метод <xref:System.IO.StreamReader.Dispose%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="eabf3-115">Although the <xref:System.IO.StreamReader> class implements the <xref:System.IDisposable> interface, which indicates that it uses an unmanaged resource, the example doesn't explicitly call the <xref:System.IO.StreamReader.Dispose%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="eabf3-116">Когда компилятор C# или Visual Basic встречает оператор `using`, он создает промежуточный язык, эквивалентный следующему коду, который явно содержит блок `try/finally`.</span><span class="sxs-lookup"><span data-stu-id="eabf3-116">When the C# or Visual Basic compiler encounters the `using` statement, it emits intermediate language (IL) that is equivalent to the following code that explicitly contains a `try/finally` block.</span></span>

[!code-csharp[Conceptual.Disposable#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/using3.cs#3)]
[!code-vb[Conceptual.Disposable#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/using3.vb#3)]

<span data-ttu-id="eabf3-117">Оператор `using` в C# позволяет присоединять несколько ресурсов в одном операторе, что эквивалентно использованию вложенных инструкций `using`.</span><span class="sxs-lookup"><span data-stu-id="eabf3-117">The C# `using` statement also allows you to acquire multiple resources in a single statement, which is internally equivalent to nested `using` statements.</span></span> <span data-ttu-id="eabf3-118">В следующем примере создается два объекта <xref:System.IO.StreamReader> для чтения содержимого двух разных файлов.</span><span class="sxs-lookup"><span data-stu-id="eabf3-118">The following example instantiates two <xref:System.IO.StreamReader> objects to read the contents of two different files.</span></span>

[!code-csharp[Conceptual.Disposable#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/using4.cs#4)]

## <a name="tryfinally-block"></a><span data-ttu-id="eabf3-119">Блок try/finally</span><span class="sxs-lookup"><span data-stu-id="eabf3-119">Try/finally block</span></span>

<span data-ttu-id="eabf3-120">Вместо размещения блока `try/finally` в операторе `using` можно реализовать блок `try/finally` напрямую.</span><span class="sxs-lookup"><span data-stu-id="eabf3-120">Instead of wrapping a `try/finally` block in a `using` statement, you may choose to implement the `try/finally` block directly.</span></span> <span data-ttu-id="eabf3-121">Это может отражать ваш стиль программирования или же осуществляться по одной из следующих причин:</span><span class="sxs-lookup"><span data-stu-id="eabf3-121">It may be your personal coding style, or you might want to do this for one of the following reasons:</span></span>

- <span data-ttu-id="eabf3-122">Чтобы включить блок `catch` для обработки исключений, вызванных в блоке `try`.</span><span class="sxs-lookup"><span data-stu-id="eabf3-122">To include a `catch` block to handle exceptions thrown in the `try` block.</span></span> <span data-ttu-id="eabf3-123">В противном случае любые исключения, вызванные в операторе `using`, не обрабатываются.</span><span class="sxs-lookup"><span data-stu-id="eabf3-123">Otherwise, any exceptions thrown within the `using` statement are unhandled.</span></span>

- <span data-ttu-id="eabf3-124">Чтобы создать экземпляр объекта, реализующего интерфейс <xref:System.IDisposable>, область действия которого не является локальной для блока, в котором он объявлен.</span><span class="sxs-lookup"><span data-stu-id="eabf3-124">To instantiate an object that implements <xref:System.IDisposable> whose scope is not local to the block within which it is declared.</span></span>

<span data-ttu-id="eabf3-125">Следующий пример похож на предыдущий с тем отличием, что в нем используется блок `try/catch/finally`для создания, использования и удаления экземпляра объекта <xref:System.IO.StreamReader>, а также для обработки исключений, создаваемых конструктором <xref:System.IO.StreamReader> и его методом <xref:System.IO.StreamReader.ReadToEnd%2A>.</span><span class="sxs-lookup"><span data-stu-id="eabf3-125">The following example is similar to the previous example, except that it uses a `try/catch/finally` block to instantiate, use, and dispose of a <xref:System.IO.StreamReader> object, and to handle any exceptions thrown by the <xref:System.IO.StreamReader> constructor and its <xref:System.IO.StreamReader.ReadToEnd%2A> method.</span></span> <span data-ttu-id="eabf3-126">Перед вызовом метода <xref:System.IDisposable.Dispose%2A> код в блоке `finally` проверяет, что объект, реализующий <xref:System.IDisposable>, не является `null`.</span><span class="sxs-lookup"><span data-stu-id="eabf3-126">The code in the `finally` block checks that the object that implements <xref:System.IDisposable> isn't `null` before it calls the <xref:System.IDisposable.Dispose%2A> method.</span></span> <span data-ttu-id="eabf3-127">Если этого сделать не удастся, это может привести к исключению <xref:System.NullReferenceException> во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="eabf3-127">Failure to do this can result in a <xref:System.NullReferenceException> exception at run time.</span></span>

[!code-csharp[Conceptual.Disposable#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/using5.cs#6)]
[!code-vb[Conceptual.Disposable#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/using5.vb#6)]

<span data-ttu-id="eabf3-128">Вы можете применить этот базовый шаблон, если есть желание или необходимость реализовать блок `try/finally` на языке программирования, который не поддерживает оператор `using`, но допускает прямые вызовы метода <xref:System.IDisposable.Dispose%2A>.</span><span class="sxs-lookup"><span data-stu-id="eabf3-128">You can follow this basic pattern if you choose to implement or must implement a `try/finally` block, because your programming language doesn't support a `using` statement but does allow direct calls to the <xref:System.IDisposable.Dispose%2A> method.</span></span>

## <a name="idisposable-instance-members"></a><span data-ttu-id="eabf3-129">Члены экземпляра IDisposable</span><span class="sxs-lookup"><span data-stu-id="eabf3-129">IDisposable instance members</span></span>

<span data-ttu-id="eabf3-130">Если класс содержит реализацию <xref:System.IDisposable> в качестве члена экземпляра (поля или свойства), класс также должен реализовывать <xref:System.IDisposable>.</span><span class="sxs-lookup"><span data-stu-id="eabf3-130">If a class holds an <xref:System.IDisposable> implementation as an instance member, either a field or a property, the class should also implement <xref:System.IDisposable>.</span></span> <span data-ttu-id="eabf3-131">См. сведения о [реализации каскадного удаления](implementing-dispose.md#cascade-dispose-calls).</span><span class="sxs-lookup"><span data-stu-id="eabf3-131">For more information, see [implement a cascade dispose](implementing-dispose.md#cascade-dispose-calls).</span></span>

## <a name="see-also"></a><span data-ttu-id="eabf3-132">См. также</span><span class="sxs-lookup"><span data-stu-id="eabf3-132">See also</span></span>

- [<span data-ttu-id="eabf3-133">Очистка неуправляемых ресурсов</span><span class="sxs-lookup"><span data-stu-id="eabf3-133">Cleaning up unmanaged resources</span></span>](unmanaged.md)
- [<span data-ttu-id="eabf3-134">Оператор using (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="eabf3-134">using Statement (C# Reference)</span></span>](../../csharp/language-reference/keywords/using-statement.md)
- [<span data-ttu-id="eabf3-135">Оператор Using (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="eabf3-135">Using Statement (Visual Basic)</span></span>](../../visual-basic/language-reference/statements/using-statement.md)
