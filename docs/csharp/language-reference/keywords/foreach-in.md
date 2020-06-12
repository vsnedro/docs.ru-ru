---
title: Оператор foreach в C#
ms.date: 06/03/2020
f1_keywords:
- foreach
- foreach_CSharpKeyword
helpviewer_keywords:
- foreach keyword [C#]
- foreach statement [C#]
- in keyword [C#]
ms.assetid: 5a9c5ddc-5fd3-457a-9bb6-9abffcd874ec
ms.openlocfilehash: 1645a246c9feee2a92c0d4e4bbeda47f0afde7d9
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401892"
---
# <a name="foreach-in-c-reference"></a><span data-ttu-id="0189d-102">foreach, in (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="0189d-102">foreach, in (C# reference)</span></span>

<span data-ttu-id="0189d-103">Оператор `foreach` выполняет оператор или блок операторов для каждого элемента в экземпляре типа, который реализует интерфейс <xref:System.Collections.IEnumerable?displayProperty=nameWithType> или <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0189d-103">The `foreach` statement executes a statement or a block of statements for each element in an instance of the type that implements the <xref:System.Collections.IEnumerable?displayProperty=nameWithType> or <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> interface.</span></span> <span data-ttu-id="0189d-104">Оператор `foreach` не ограничивается этими типами. Он может применяться к экземпляру любого типа, который удовлетворяет следующим условиям:</span><span class="sxs-lookup"><span data-stu-id="0189d-104">The `foreach` statement isn't limited to those types and can be applied to an instance of any type that satisfies the following conditions:</span></span>

- <span data-ttu-id="0189d-105">включает открытый метод `GetEnumerator` без параметров со следующим типом возвращаемого значения: класс, структура или тип интерфейса;</span><span class="sxs-lookup"><span data-stu-id="0189d-105">has the public parameterless `GetEnumerator` method whose return type is either class, struct, or interface type,</span></span>
- <span data-ttu-id="0189d-106">тип возвращаемого значения метода `GetEnumerator` должен содержать открытое свойство `Current` и открытый метод `MoveNext` без параметров с типом возвращаемого значения <xref:System.Boolean>.</span><span class="sxs-lookup"><span data-stu-id="0189d-106">the return type of the `GetEnumerator` method has the public `Current` property and the public parameterless `MoveNext` method whose return type is <xref:System.Boolean>.</span></span>

<span data-ttu-id="0189d-107">В большинстве случаев `foreach` выполняет итерацию по выражению `IEnumerable<T>`, в котором каждый элемент имеет тип `T`.</span><span class="sxs-lookup"><span data-stu-id="0189d-107">In most uses, `foreach` iterates an `IEnumerable<T>` expression where each element is of type `T`.</span></span> <span data-ttu-id="0189d-108">Однако элементы могут быть любого типа, который имеет явное или неявное преобразование из типа свойства `Current`.</span><span class="sxs-lookup"><span data-stu-id="0189d-108">However, the elements may be any type that has an implicit or explicit conversion from the type of the `Current` property.</span></span> <span data-ttu-id="0189d-109">Если свойство `Current` возвращает `SomeType`, тип элементов может быть следующим:</span><span class="sxs-lookup"><span data-stu-id="0189d-109">If the `Current` property returns `SomeType`, the type of the elements may be:</span></span>

- <span data-ttu-id="0189d-110">базовые классы класса `SomeType`;</span><span class="sxs-lookup"><span data-stu-id="0189d-110">Any of the base classes of `SomeType`.</span></span>
- <span data-ttu-id="0189d-111">интерфейсы, реализованные с помощью класса `SomeType`.</span><span class="sxs-lookup"><span data-stu-id="0189d-111">Any of the interfaces implemented by `SomeType`.</span></span>

<span data-ttu-id="0189d-112">Кроме того, если `SomeType` является `class` или `interface`, а не `sealed`, то тип элементов может включать:</span><span class="sxs-lookup"><span data-stu-id="0189d-112">Furthermore, if `SomeType` is a `class` or an `interface` and not `sealed`, the type of elements may include:</span></span>

- <span data-ttu-id="0189d-113">любой тип, производный от `SomeType`;</span><span class="sxs-lookup"><span data-stu-id="0189d-113">Any type derived from `SomeType`.</span></span>
- <span data-ttu-id="0189d-114">любой произвольный интерфейс.</span><span class="sxs-lookup"><span data-stu-id="0189d-114">Any arbitrary interface.</span></span> <span data-ttu-id="0189d-115">Разрешен любой интерфейс, так как он может быть реализован классом, производным от `SomeType` или реализующим этот класс.</span><span class="sxs-lookup"><span data-stu-id="0189d-115">Any interface is allowed because any interface may be implemented by a class derived from or implementing `SomeType`.</span></span>

<span data-ttu-id="0189d-116">Переменную итерации можно объявить с помощью любого типа, который соответствует предыдущим правилам.</span><span class="sxs-lookup"><span data-stu-id="0189d-116">You may declare the iteration variable using any type that matches the preceding rules.</span></span> <span data-ttu-id="0189d-117">Если для преобразования из `SomeType` в тип переменной итерации требуется явное приведение, эта операция может вызвать исключение <xref:System.InvalidCastException> при сбое преобразования.</span><span class="sxs-lookup"><span data-stu-id="0189d-117">If the conversion from `SomeType` to the type of the iteration variable requires an explicit cast, that operation may throw an <xref:System.InvalidCastException> when the conversion fails.</span></span>

<span data-ttu-id="0189d-118">Начиная с версии C# 7.3, если свойство перечислителя `Current` возвращает [ссылочное возвращаемое значение](ref.md#reference-return-values) (`ref T`, где `T` — это тип элемента коллекции), вы можете объявить переменную итерации с модификатором `ref` или `ref readonly`.</span><span class="sxs-lookup"><span data-stu-id="0189d-118">Beginning with C# 7.3, if the enumerator's `Current` property returns a [reference return value](ref.md#reference-return-values) (`ref T` where `T` is the type of the collection element), you can declare the iteration variable with the `ref` or `ref readonly` modifier.</span></span>

<span data-ttu-id="0189d-119">Начиная с версии C# 8.0, можно применять оператор `await` к инструкции `foreach`, если тип коллекции реализует интерфейс <xref:System.Collections.Generic.IAsyncEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="0189d-119">Beginning with C# 8.0, the `await` operator may be applied to the `foreach` statement when the collection type implements the <xref:System.Collections.Generic.IAsyncEnumerable%601> interface.</span></span> <span data-ttu-id="0189d-120">Каждую итерацию цикла можно приостановить, пока будет осуществляться асинхронное извлечение следующего элемента.</span><span class="sxs-lookup"><span data-stu-id="0189d-120">Each iteration of the loop may be suspended while the next element is retrieved asynchronously.</span></span> <span data-ttu-id="0189d-121">Элементы потока по умолчанию обрабатываются в захваченном контексте.</span><span class="sxs-lookup"><span data-stu-id="0189d-121">By default, stream elements are processed in the captured context.</span></span> <span data-ttu-id="0189d-122">Чтобы отключить захват контекста, используйте метод расширения <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0189d-122">If you want to disable capturing of the context, use the <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait%2A?displayProperty=nameWithType> extension method.</span></span> <span data-ttu-id="0189d-123">Дополнительные сведения о контекстах синхронизации и захвате текущего контекста см. в [статье](../../../standard/asynchronous-programming-patterns/consuming-the-task-based-asynchronous-pattern.md), посвященной использованию асинхронной модели на основе задач.</span><span class="sxs-lookup"><span data-stu-id="0189d-123">For more information about synchronization contexts and capturing the current context, see the article on [consuming the Task-based asynchronous pattern](../../../standard/asynchronous-programming-patterns/consuming-the-task-based-asynchronous-pattern.md).</span></span>

<span data-ttu-id="0189d-124">В любой момент в блоке операторов `foreach` вы можете прервать цикл с помощью оператора [break](break.md) или перейти к следующей итерации в цикле с помощью оператора [continue](continue.md).</span><span class="sxs-lookup"><span data-stu-id="0189d-124">At any point within the `foreach` statement block, you can break out of the loop by using the [break](break.md) statement, or step to the next iteration in the loop by using the [continue](continue.md) statement.</span></span> <span data-ttu-id="0189d-125">Можно также выйти из цикла `foreach` с помощью операторов [goto](goto.md), [return](return.md) или [throw](throw.md).</span><span class="sxs-lookup"><span data-stu-id="0189d-125">You can also exit a `foreach` loop by the [goto](goto.md), [return](return.md), or [throw](throw.md) statements.</span></span>

<span data-ttu-id="0189d-126">Если оператор `foreach` применяется к `null`, возникает исключение <xref:System.NullReferenceException>.</span><span class="sxs-lookup"><span data-stu-id="0189d-126">If the `foreach` statement is applied to `null`, a <xref:System.NullReferenceException> is thrown.</span></span> <span data-ttu-id="0189d-127">Если исходная коллекция инструкции `foreach` пустая, тело цикла `foreach` не выполняется и пропускается.</span><span class="sxs-lookup"><span data-stu-id="0189d-127">If the source collection of the `foreach` statement is empty, the body of the `foreach` loop isn't executed and skipped.</span></span>

## <a name="examples"></a><span data-ttu-id="0189d-128">Примеры</span><span class="sxs-lookup"><span data-stu-id="0189d-128">Examples</span></span>

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

<span data-ttu-id="0189d-129">В следующем примере показано использование оператора `foreach` с экземпляром типа <xref:System.Collections.Generic.List%601>, который реализует интерфейс <xref:System.Collections.Generic.IEnumerable%601>:</span><span class="sxs-lookup"><span data-stu-id="0189d-129">The following example shows usage of the `foreach` statement with an instance of the <xref:System.Collections.Generic.List%601> type that implements the <xref:System.Collections.Generic.IEnumerable%601> interface:</span></span>

:::code language="csharp" source="snippets/IterationKeywordsExamples.cs" id="1" interactive="try-dotnet-method" :::

<span data-ttu-id="0189d-130">В следующем примере показано использование оператора `foreach` с экземпляром типа <xref:System.Span%601?displayProperty=nameWithType>, который не реализует интерфейс:</span><span class="sxs-lookup"><span data-stu-id="0189d-130">The next example uses the `foreach` statement with an instance of the <xref:System.Span%601?displayProperty=nameWithType> type, which doesn't implement any interfaces:</span></span>

:::code language="csharp" source="snippets/IterationKeywordsExamples.cs" id="2" :::

<span data-ttu-id="0189d-131">В следующем примере с помощью переменной итерации `ref` устанавливается значение каждого элемента в массиве stackalloc.</span><span class="sxs-lookup"><span data-stu-id="0189d-131">The following example uses a `ref` iteration variable to set the value of each item in a stackalloc array.</span></span> <span data-ttu-id="0189d-132">В версии `ref readonly` выполняется перебор коллекции для печати всех значений.</span><span class="sxs-lookup"><span data-stu-id="0189d-132">The `ref readonly` version iterates the collection to print all the values.</span></span> <span data-ttu-id="0189d-133">В объявлении `readonly` используется неявное объявление локальной переменной.</span><span class="sxs-lookup"><span data-stu-id="0189d-133">The `readonly` declaration uses an implicit local variable declaration.</span></span> <span data-ttu-id="0189d-134">Неявные объявления переменных могут использоваться с объявлениями `ref` или `ref readonly`, так же как и явно типизированные объявления переменных.</span><span class="sxs-lookup"><span data-stu-id="0189d-134">Implicit variable declarations can be used with either `ref` or `ref readonly` declarations, as can explicitly typed variable declarations.</span></span>

:::code language="csharp" source="snippets/IterationKeywordsExamples.cs" id="RefSpan" :::

<span data-ttu-id="0189d-135">В следующем примере используется `await foreach` для выполнения итерации коллекции с асинхронным созданием каждого элемента:</span><span class="sxs-lookup"><span data-stu-id="0189d-135">The following example uses `await foreach` to iterate a collection that generates each element asynchronously:</span></span>

:::code language="csharp" source="snippets/IterationKeywordsExamples.cs" id="AwaitForeach"  :::

## <a name="c-language-specification"></a><span data-ttu-id="0189d-136">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="0189d-136">C# language specification</span></span>

<span data-ttu-id="0189d-137">Дополнительные сведения см. в разделе [Оператор foreach](~/_csharplang/spec/statements.md#the-foreach-statement) в документации [Предварительная спецификация C# 6.0](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="0189d-137">For more information, see [The foreach statement](~/_csharplang/spec/statements.md#the-foreach-statement) section of the [C# language specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span>

## <a name="see-also"></a><span data-ttu-id="0189d-138">См. также</span><span class="sxs-lookup"><span data-stu-id="0189d-138">See also</span></span>

- [<span data-ttu-id="0189d-139">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="0189d-139">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="0189d-140">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="0189d-140">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="0189d-141">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="0189d-141">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="0189d-142">Использование оператора foreach с массивами</span><span class="sxs-lookup"><span data-stu-id="0189d-142">Using foreach with arrays</span></span>](../../programming-guide/arrays/using-foreach-with-arrays.md)
- [<span data-ttu-id="0189d-143">Оператор for</span><span class="sxs-lookup"><span data-stu-id="0189d-143">for statement</span></span>](for.md)
