---
description: foreach, in (справочник по C#)
title: Оператор foreach в C#
ms.date: 07/22/2020
f1_keywords:
- foreach
- foreach_CSharpKeyword
helpviewer_keywords:
- foreach keyword [C#]
- foreach statement [C#]
- in keyword [C#]
ms.assetid: 5a9c5ddc-5fd3-457a-9bb6-9abffcd874ec
ms.openlocfilehash: 2ed89fa52b2d3d369d668bf79ab32eaf7be18a8a
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2020
ms.locfileid: "89142080"
---
# <a name="foreach-in-c-reference"></a><span data-ttu-id="e9457-103">foreach, in (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="e9457-103">foreach, in (C# reference)</span></span>

<span data-ttu-id="e9457-104">Оператор `foreach` выполняет оператор или блок операторов для каждого элемента в экземпляре типа, который реализует интерфейс <xref:System.Collections.IEnumerable?displayProperty=nameWithType> или <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="e9457-104">The `foreach` statement executes a statement or a block of statements for each element in an instance of the type that implements the <xref:System.Collections.IEnumerable?displayProperty=nameWithType> or <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> interface, as the following example shows:</span></span>

:::code language="csharp" source="snippets/IterationKeywordsExamples.cs" id="1" interactive="try-dotnet-method" :::

<span data-ttu-id="e9457-105">Оператор `foreach` не ограничен этими типами.</span><span class="sxs-lookup"><span data-stu-id="e9457-105">The `foreach` statement isn't limited to those types.</span></span> <span data-ttu-id="e9457-106">Его можно использовать с экземпляром любого типа, который удовлетворяет следующим условиям:</span><span class="sxs-lookup"><span data-stu-id="e9457-106">You can use it with an instance of any type that satisfies the following conditions:</span></span>

- <span data-ttu-id="e9457-107">тип содержит открытый метод `GetEnumerator` без параметров со следующим типом возвращаемого значения: класс, структура или тип интерфейса;</span><span class="sxs-lookup"><span data-stu-id="e9457-107">a type has the public parameterless `GetEnumerator` method whose return type is either class, struct, or interface type,</span></span>
- <span data-ttu-id="e9457-108">тип возвращаемого значения метода `GetEnumerator` должен содержать открытое свойство `Current` и открытый метод `MoveNext` без параметров с типом возвращаемого значения <xref:System.Boolean>.</span><span class="sxs-lookup"><span data-stu-id="e9457-108">the return type of the `GetEnumerator` method has the public `Current` property and the public parameterless `MoveNext` method whose return type is <xref:System.Boolean>.</span></span>

<span data-ttu-id="e9457-109">В следующем примере показано использование оператора `foreach` с экземпляром типа <xref:System.Span%601?displayProperty=nameWithType>, который не реализует интерфейс:</span><span class="sxs-lookup"><span data-stu-id="e9457-109">The following example uses the `foreach` statement with an instance of the <xref:System.Span%601?displayProperty=nameWithType> type, which doesn't implement any interfaces:</span></span>

:::code language="csharp" source="snippets/IterationKeywordsExamples.cs" id="2" :::

<span data-ttu-id="e9457-110">Начиная с версии C# 7.3, если свойство перечислителя `Current` возвращает [ссылочное возвращаемое значение](ref.md#reference-return-values) (`ref T`, где `T` — это тип элемента коллекции), вы можете объявить переменную итерации с модификатором `ref` или `ref readonly`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="e9457-110">Beginning with C# 7.3, if the enumerator's `Current` property returns a [reference return value](ref.md#reference-return-values) (`ref T` where `T` is the type of a collection element), you can declare an iteration variable with the `ref` or `ref readonly` modifier, as the following example shows:</span></span>

:::code language="csharp" source="snippets/IterationKeywordsExamples.cs" id="RefSpan" :::

<span data-ttu-id="e9457-111">Начиная с C# 8.0, можно применять оператор `await foreach` для использования асинхронного потока данных, то есть типа коллекции, реализующего интерфейс <xref:System.Collections.Generic.IAsyncEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="e9457-111">Beginning with C# 8.0, you can use the `await foreach` statement to consume an asynchronous stream of data, that is, the collection type that implements the <xref:System.Collections.Generic.IAsyncEnumerable%601> interface.</span></span> <span data-ttu-id="e9457-112">Каждую итерацию цикла можно приостановить, пока будет осуществляться асинхронное извлечение следующего элемента.</span><span class="sxs-lookup"><span data-stu-id="e9457-112">Each iteration of the loop may be suspended while the next element is retrieved asynchronously.</span></span> <span data-ttu-id="e9457-113">В следующем примере показано использование оператора `await foreach`.</span><span class="sxs-lookup"><span data-stu-id="e9457-113">The following example shows how to use the `await foreach` statement:</span></span>

:::code language="csharp" source="snippets/IterationKeywordsExamples.cs" id="AwaitForeach" :::

<span data-ttu-id="e9457-114">Элементы потока по умолчанию обрабатываются в захваченном контексте.</span><span class="sxs-lookup"><span data-stu-id="e9457-114">By default, stream elements are processed in the captured context.</span></span> <span data-ttu-id="e9457-115">Чтобы отключить захват контекста, используйте метод расширения <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e9457-115">If you want to disable capturing of the context, use the <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait%2A?displayProperty=nameWithType> extension method.</span></span> <span data-ttu-id="e9457-116">Дополнительные сведения о контекстах синхронизации и захвате текущего контекста см. в статье [Использование асинхронного шаблона, основанного на задачах](../../../standard/asynchronous-programming-patterns/consuming-the-task-based-asynchronous-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="e9457-116">For more information about synchronization contexts and capturing the current context, see [Consuming the Task-based asynchronous pattern](../../../standard/asynchronous-programming-patterns/consuming-the-task-based-asynchronous-pattern.md).</span></span> <span data-ttu-id="e9457-117">Дополнительные сведения об асинхронных потоках см. в разделе [Асинхронные потоки](../../whats-new/csharp-8.md#asynchronous-streams) статьи [Новые возможности в C# 8.0](../../whats-new/csharp-8.md).</span><span class="sxs-lookup"><span data-stu-id="e9457-117">For more information about asynchronous streams, see the [Asynchronous streams](../../whats-new/csharp-8.md#asynchronous-streams) section of the [What's new in C# 8.0](../../whats-new/csharp-8.md) article.</span></span>

<span data-ttu-id="e9457-118">В любой момент в блоке операторов `foreach` вы можете прервать цикл с помощью оператора [break](break.md) или перейти к следующей итерации в цикле с помощью оператора [continue](continue.md).</span><span class="sxs-lookup"><span data-stu-id="e9457-118">At any point within the `foreach` statement block, you can break out of the loop by using the [break](break.md) statement, or step to the next iteration in the loop by using the [continue](continue.md) statement.</span></span> <span data-ttu-id="e9457-119">Можно также выйти из цикла `foreach` с помощью операторов [goto](goto.md), [return](return.md) или [throw](throw.md).</span><span class="sxs-lookup"><span data-stu-id="e9457-119">You can also exit a `foreach` loop by the [goto](goto.md), [return](return.md), or [throw](throw.md) statements.</span></span>

<span data-ttu-id="e9457-120">Если оператор `foreach` применяется к `null`, возникает исключение <xref:System.NullReferenceException>.</span><span class="sxs-lookup"><span data-stu-id="e9457-120">If the `foreach` statement is applied to `null`, a <xref:System.NullReferenceException> is thrown.</span></span> <span data-ttu-id="e9457-121">Если исходная коллекция инструкции `foreach` пустая, тело цикла `foreach` не выполняется и пропускается.</span><span class="sxs-lookup"><span data-stu-id="e9457-121">If the source collection of the `foreach` statement is empty, the body of the `foreach` loop isn't executed and skipped.</span></span>

## <a name="type-of-an-iteration-variable"></a><span data-ttu-id="e9457-122">Тип переменной итерации</span><span class="sxs-lookup"><span data-stu-id="e9457-122">Type of an iteration variable</span></span>

<span data-ttu-id="e9457-123">Можно использовать ключевое слово `var`, чтобы компилятор мог определить тип переменной итерации в операторе `foreach`, как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="e9457-123">You can use the `var` keyword to let the compiler infer the type of an iteration variable in the `foreach` statement, as the following code shows:</span></span>

```csharp
foreach (var item in collection) { }
```

<span data-ttu-id="e9457-124">Можно также явно указать тип переменной итерации, как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="e9457-124">You can also explicitly specify the type of an iteration variable, as the following code shows:</span></span>

```csharp
IEnumerable<T> collection = new T[5];
foreach (V item in collection) { }
```

<span data-ttu-id="e9457-125">В предыдущей форме тип `T` элемента коллекции должен быть неявно или явно преобразован в тип `V` переменной итерации.</span><span class="sxs-lookup"><span data-stu-id="e9457-125">In the preceding form, type `T` of a collection element must be implicitly or explicitly convertible to type `V` of an iteration variable.</span></span> <span data-ttu-id="e9457-126">Если явное преобразование из `T` в `V` завершается ошибкой во время выполнения, оператор `foreach` выдает исключение <xref:System.InvalidCastException>.</span><span class="sxs-lookup"><span data-stu-id="e9457-126">If an explicit conversion from `T` to `V` fails at run time, the `foreach` statement throws an <xref:System.InvalidCastException>.</span></span> <span data-ttu-id="e9457-127">Например, если `T` является незапечатанным типом класса, `V` может быть любым типом интерфейса, даже тем, который `T` не реализует.</span><span class="sxs-lookup"><span data-stu-id="e9457-127">For example, if `T` is a non-sealed class type, `V` can be any interface type, even the one that `T` doesn't implement.</span></span> <span data-ttu-id="e9457-128">Во время выполнения тип элемента коллекции может быть производным от `T` и фактически реализовать `V`.</span><span class="sxs-lookup"><span data-stu-id="e9457-128">At run time, the type of a collection element may be the one that derives from `T` and actually implements `V`.</span></span> <span data-ttu-id="e9457-129">В противном случае возникает <xref:System.InvalidCastException>.</span><span class="sxs-lookup"><span data-stu-id="e9457-129">If that's not the case, an <xref:System.InvalidCastException> is thrown.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="e9457-130">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="e9457-130">C# language specification</span></span>

<span data-ttu-id="e9457-131">Дополнительные сведения см. в разделе [Оператор foreach](~/_csharplang/spec/statements.md#the-foreach-statement) в документации [Предварительная спецификация C# 6.0](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="e9457-131">For more information, see [The foreach statement](~/_csharplang/spec/statements.md#the-foreach-statement) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e9457-132">См. также</span><span class="sxs-lookup"><span data-stu-id="e9457-132">See also</span></span>

- [<span data-ttu-id="e9457-133">справочник по C#</span><span class="sxs-lookup"><span data-stu-id="e9457-133">C# reference</span></span>](../index.md)
- [<span data-ttu-id="e9457-134">Ключевые слова C#</span><span class="sxs-lookup"><span data-stu-id="e9457-134">C# keywords</span></span>](index.md)
- [<span data-ttu-id="e9457-135">Использование оператора foreach с массивами</span><span class="sxs-lookup"><span data-stu-id="e9457-135">Using foreach with arrays</span></span>](../../programming-guide/arrays/using-foreach-with-arrays.md)
- [<span data-ttu-id="e9457-136">Оператор for</span><span class="sxs-lookup"><span data-stu-id="e9457-136">for statement</span></span>](for.md)
