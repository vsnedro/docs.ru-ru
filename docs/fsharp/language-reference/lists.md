---
title: Списки
description: 'Сведения о списках F #, упорядоченной, неизменяемой последовательности элементов одного и того же типа.'
ms.date: 08/13/2020
ms.openlocfilehash: 16d7195039d25cf63630f5cc3be6563b1bf45c44
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/18/2020
ms.locfileid: "88559171"
---
# <a name="lists"></a><span data-ttu-id="ad50a-103">Списки</span><span class="sxs-lookup"><span data-stu-id="ad50a-103">Lists</span></span>

<span data-ttu-id="ad50a-104">В языке F# список — это упорядоченная, неизменная серия элементов одного типа.</span><span class="sxs-lookup"><span data-stu-id="ad50a-104">A list in F# is an ordered, immutable series of elements of the same type.</span></span> <span data-ttu-id="ad50a-105">Для выполнения основных операций со списками используйте функции в [модуле List](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html).</span><span class="sxs-lookup"><span data-stu-id="ad50a-105">To perform basic operations on lists, use the functions in the [List module](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html).</span></span>

## <a name="creating-and-initializing-lists"></a><span data-ttu-id="ad50a-106">Создание и инициализация списков</span><span class="sxs-lookup"><span data-stu-id="ad50a-106">Creating and Initializing Lists</span></span>

<span data-ttu-id="ad50a-107">Список можно определить путем прямого перечисления элементов, разделенных точкой с запятой и заключенных в квадратные скобки, как показано в следующей строке кода.</span><span class="sxs-lookup"><span data-stu-id="ad50a-107">You can define a list by explicitly listing out the elements, separated by semicolons and enclosed in square brackets, as shown in the following line of code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1301.fs)]

<span data-ttu-id="ad50a-108">Вместо точки с запятой для разделения элементов можно также использовать разрыв строки.</span><span class="sxs-lookup"><span data-stu-id="ad50a-108">You can also put line breaks between elements, in which case the semicolons are optional.</span></span> <span data-ttu-id="ad50a-109">Такой синтаксис позволяет получить более удобный для чтения код, если список содержит длинные выражения инициализации или к каждому элементу необходимо написать комментарий.</span><span class="sxs-lookup"><span data-stu-id="ad50a-109">The latter syntax can result in more readable code when the element initialization expressions are longer, or when you want to include a comment for each element.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet13011.fs)]

<span data-ttu-id="ad50a-110">Обычно все элементы в списке должны быть одного типа.</span><span class="sxs-lookup"><span data-stu-id="ad50a-110">Normally, all list elements must be the same type.</span></span> <span data-ttu-id="ad50a-111">Исключением является список, в котором элементы основного типа могут иметь элементы производных типов.</span><span class="sxs-lookup"><span data-stu-id="ad50a-111">An exception is that a list in which the elements are specified to be a base type can have elements that are derived types.</span></span> <span data-ttu-id="ad50a-112">Следующий вариант считается приемлемым, так как типы `Button` и `CheckBox` являются производными от типа `Control`.</span><span class="sxs-lookup"><span data-stu-id="ad50a-112">Thus the following is acceptable, because both `Button` and `CheckBox` derive from `Control`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet13012.fs)]

<span data-ttu-id="ad50a-113">Определить элементы списка можно также с помощью диапазона, который будет ограничен целыми числами, разделенными оператором (`..`), как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="ad50a-113">You can also define list elements by using a range indicated by integers separated by the range operator (`..`), as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1302.fs)]

<span data-ttu-id="ad50a-114">Пустой список определяется парой квадратных скобок, между которыми ничего не указано.</span><span class="sxs-lookup"><span data-stu-id="ad50a-114">An empty list is specified by a pair of square brackets with nothing in between them.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1304.fs)]

<span data-ttu-id="ad50a-115">Также список можно создать с помощью выражения последовательности.</span><span class="sxs-lookup"><span data-stu-id="ad50a-115">You can also use a sequence expression to create a list.</span></span> <span data-ttu-id="ad50a-116">Дополнительные сведения см. в разделе [выражения последовательностей](sequences.md#sequence-expressions) .</span><span class="sxs-lookup"><span data-stu-id="ad50a-116">See [Sequence Expressions](sequences.md#sequence-expressions) for more information.</span></span> <span data-ttu-id="ad50a-117">Например, в следующем коде создается список квадратов целочисленных значений от 1 до 10.</span><span class="sxs-lookup"><span data-stu-id="ad50a-117">For example, the following code creates a list of squares of integers from 1 to 10.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1303.fs)]

## <a name="operators-for-working-with-lists"></a><span data-ttu-id="ad50a-118">Операторы для работы со списками</span><span class="sxs-lookup"><span data-stu-id="ad50a-118">Operators for Working with Lists</span></span>

<span data-ttu-id="ad50a-119">Оператор `::` позволяет добавлять элементы в список.</span><span class="sxs-lookup"><span data-stu-id="ad50a-119">You can attach elements to a list by using the `::` (cons) operator.</span></span> <span data-ttu-id="ad50a-120">Если список `list1` включает `[2; 3; 4]`, то следующий код создает список `list2` как `[100; 2; 3; 4]`.</span><span class="sxs-lookup"><span data-stu-id="ad50a-120">If `list1` is `[2; 3; 4]`, the following code creates `list2` as `[100; 2; 3; 4]`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1305.fs)]

<span data-ttu-id="ad50a-121">Оператор `@` позволяет объединять списки совместимых типов, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="ad50a-121">You can concatenate lists that have compatible types by using the `@` operator, as in the following code.</span></span> <span data-ttu-id="ad50a-122">Если список `list1` включает `[2; 3; 4]`, список `list2` — `[100; 2; 3; 4]`, то следующий код создает список `list3` как `[2; 3; 4; 100; 2; 3; 4]`.</span><span class="sxs-lookup"><span data-stu-id="ad50a-122">If `list1` is `[2; 3; 4]` and `list2` is `[100; 2; 3; 4]`, this code creates `list3` as `[2; 3; 4; 100; 2; 3; 4]`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1306.fs)]

<span data-ttu-id="ad50a-123">Функции для выполнения операций с списками доступны в [модуле List](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html).</span><span class="sxs-lookup"><span data-stu-id="ad50a-123">Functions for performing operations on lists are available in the [List module](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html).</span></span>

<span data-ttu-id="ad50a-124">Поскольку списки в языке F# являются неизменными, то операции изменения не изменяют существующие списки, а создают новые.</span><span class="sxs-lookup"><span data-stu-id="ad50a-124">Because lists in F# are immutable, any modifying operations generate new lists instead of modifying existing lists.</span></span>

<span data-ttu-id="ad50a-125">Списки в F # реализуются как однонаправленные списки. Это означает, что операции, обращающиеся только к заголовку списка, являются O (1), а доступ к элементу — O (*n*).</span><span class="sxs-lookup"><span data-stu-id="ad50a-125">Lists in F# are implemented as singly linked lists, which means that operations that access only the head of the list are O(1), and element access is O(*n*).</span></span>

## <a name="properties"></a><span data-ttu-id="ad50a-126">Свойства</span><span class="sxs-lookup"><span data-stu-id="ad50a-126">Properties</span></span>

<span data-ttu-id="ad50a-127">Тип списка поддерживает следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="ad50a-127">The list type supports the following properties:</span></span>

|<span data-ttu-id="ad50a-128">Свойство</span><span class="sxs-lookup"><span data-stu-id="ad50a-128">Property</span></span>|<span data-ttu-id="ad50a-129">Тип</span><span class="sxs-lookup"><span data-stu-id="ad50a-129">Type</span></span>|<span data-ttu-id="ad50a-130">Описание</span><span class="sxs-lookup"><span data-stu-id="ad50a-130">Description</span></span>|
|--------|----|-----------|
|[<span data-ttu-id="ad50a-131">Глава</span><span class="sxs-lookup"><span data-stu-id="ad50a-131">Head</span></span>](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Head)|`'T`|<span data-ttu-id="ad50a-132">Первый элемент</span><span class="sxs-lookup"><span data-stu-id="ad50a-132">The first element.</span></span>|
|[<span data-ttu-id="ad50a-133">Пустой</span><span class="sxs-lookup"><span data-stu-id="ad50a-133">Empty</span></span>](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Empty)|`'T list`|<span data-ttu-id="ad50a-134">Статическое свойство, которое возвращает пустой список соответствующего типа.</span><span class="sxs-lookup"><span data-stu-id="ad50a-134">A static property that returns an empty list of the appropriate type.</span></span>|
|[<span data-ttu-id="ad50a-135">IsEmpty</span><span class="sxs-lookup"><span data-stu-id="ad50a-135">IsEmpty</span></span>](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#IsEmpty)|`bool`|<span data-ttu-id="ad50a-136">`true` значение, если список не содержит элементов.</span><span class="sxs-lookup"><span data-stu-id="ad50a-136">`true` if the list has no elements.</span></span>|
|[<span data-ttu-id="ad50a-137">Item</span><span class="sxs-lookup"><span data-stu-id="ad50a-137">Item</span></span>](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Item)|`'T`|<span data-ttu-id="ad50a-138">Элемент с указанным индексом (начинается с нуля).</span><span class="sxs-lookup"><span data-stu-id="ad50a-138">The element at the specified index (zero-based).</span></span>|
|[<span data-ttu-id="ad50a-139">Длина</span><span class="sxs-lookup"><span data-stu-id="ad50a-139">Length</span></span>](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Length)|`int`|<span data-ttu-id="ad50a-140">Число элементов.</span><span class="sxs-lookup"><span data-stu-id="ad50a-140">The number of elements.</span></span>|
|[<span data-ttu-id="ad50a-141">Tail</span><span class="sxs-lookup"><span data-stu-id="ad50a-141">Tail</span></span>](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Tail)|`'T list`|<span data-ttu-id="ad50a-142">Список без первого элемента</span><span class="sxs-lookup"><span data-stu-id="ad50a-142">The list without the first element.</span></span>|

<span data-ttu-id="ad50a-143">Ниже приведены некоторые примеры использования данных свойств.</span><span class="sxs-lookup"><span data-stu-id="ad50a-143">Following are some examples of using these properties.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1307.fs)]

## <a name="using-lists"></a><span data-ttu-id="ad50a-144">Использование списков</span><span class="sxs-lookup"><span data-stu-id="ad50a-144">Using Lists</span></span>

<span data-ttu-id="ad50a-145">Программирование с использованием списков позволяет выполнять сложные операции с небольшим количеством кода.</span><span class="sxs-lookup"><span data-stu-id="ad50a-145">Programming with lists enables you to perform complex operations with a small amount of code.</span></span> <span data-ttu-id="ad50a-146">В данном разделе описываются операции со списками, важные для функционального программирования.</span><span class="sxs-lookup"><span data-stu-id="ad50a-146">This section describes common operations on lists that are important to functional programming.</span></span>

### <a name="recursion-with-lists"></a><span data-ttu-id="ad50a-147">Рекурсия со списками</span><span class="sxs-lookup"><span data-stu-id="ad50a-147">Recursion with Lists</span></span>

<span data-ttu-id="ad50a-148">Списки однозначно подходят для техник рекурсивного программирования.</span><span class="sxs-lookup"><span data-stu-id="ad50a-148">Lists are uniquely suited to recursive programming techniques.</span></span> <span data-ttu-id="ad50a-149">Рассмотрим операцию, в которой должен участвовать каждый элемент списка.</span><span class="sxs-lookup"><span data-stu-id="ad50a-149">Consider an operation that must be performed on every element of a list.</span></span> <span data-ttu-id="ad50a-150">Это можно сделать рекурсивно, т. е. сначала обработать начало списка, затем перейти к хвосту — более короткому списку, состоящему из первоначального списка без первого элемента, а потом снова перейти на следующий уровень рекурсии.</span><span class="sxs-lookup"><span data-stu-id="ad50a-150">You can do this recursively by operating on the head of the list and then passing the tail of the list, which is a smaller list that consists of the original list without the first element, back again to the next level of recursion.</span></span>

<span data-ttu-id="ad50a-151">Для написания такой рекурсивной функции используется оператор (`::`) в сопоставлении шаблонов, который позволяет отделить начало списка от хвоста.</span><span class="sxs-lookup"><span data-stu-id="ad50a-151">To write such a recursive function, you use the cons operator (`::`) in pattern matching, which enables you to separate the head of a list from the tail.</span></span>

<span data-ttu-id="ad50a-152">Следующий пример кода показывает, как использовать сопоставление шаблонов для реализации рекурсивной функции, выполняющей операции над списком.</span><span class="sxs-lookup"><span data-stu-id="ad50a-152">The following code example shows how to use pattern matching to implement a recursive function that performs operations on a list.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet13071.fs)]

<span data-ttu-id="ad50a-153">Предыдущий код хорошо работает для небольших списков, но при работе со списками большого размера может случиться переполнение стека.</span><span class="sxs-lookup"><span data-stu-id="ad50a-153">The previous code works well for small lists, but for larger lists, it could overflow the stack.</span></span> <span data-ttu-id="ad50a-154">Следующий код улучшает предыдущий за счет использования аргумента аккумулирования — это стандартная техника работы с рекурсивными функциями.</span><span class="sxs-lookup"><span data-stu-id="ad50a-154">The following code improves on this code by using an accumulator argument, a standard technique for working with recursive functions.</span></span> <span data-ttu-id="ad50a-155">Использование аргумента аккумулирования делает функцию рекурсивной по отношению к хвосту, что экономит место в стеке.</span><span class="sxs-lookup"><span data-stu-id="ad50a-155">The use of the accumulator argument makes the function tail recursive, which saves stack space.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet13072.fs)]

<span data-ttu-id="ad50a-156">Функция `RemoveAllMultiples` — это рекурсивная функция, которая обрабатывает два списка.</span><span class="sxs-lookup"><span data-stu-id="ad50a-156">The function `RemoveAllMultiples` is a recursive function that takes two lists.</span></span> <span data-ttu-id="ad50a-157">Первый список содержит цифры, кратные которым будут удалены, а второй представляет собой список, из которого будут удаляться цифры.</span><span class="sxs-lookup"><span data-stu-id="ad50a-157">The first list contains the numbers whose multiples will be removed, and the second list is the list from which to remove the numbers.</span></span> <span data-ttu-id="ad50a-158">Код в следующем примере использует рекурсивную функцию для удаления всех непростых чисел из списка. После его выполнения в списке остаются только простые числа.</span><span class="sxs-lookup"><span data-stu-id="ad50a-158">The code in the following example uses this recursive function to eliminate all the non-prime numbers from a list, leaving a list of prime numbers as the result.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1308.fs)]

<span data-ttu-id="ad50a-159">Вывод выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="ad50a-159">The output is as follows:</span></span>

```console
Primes Up To 100:
[2; 3; 5; 7; 11; 13; 17; 19; 23; 29; 31; 37; 41; 43; 47; 53; 59; 61; 67; 71; 73; 79; 83; 89; 97]
```

## <a name="module-functions"></a><span data-ttu-id="ad50a-160">Функции модуля</span><span class="sxs-lookup"><span data-stu-id="ad50a-160">Module Functions</span></span>

<span data-ttu-id="ad50a-161">[Модуль List](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html) предоставляет функции, которые обращаются к элементам списка.</span><span class="sxs-lookup"><span data-stu-id="ad50a-161">The [List module](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html) provides functions that access the elements of a list.</span></span> <span data-ttu-id="ad50a-162">Самым легким и быстрым для доступа является первоначальный элемент.</span><span class="sxs-lookup"><span data-stu-id="ad50a-162">The head element is the fastest and easiest to access.</span></span> <span data-ttu-id="ad50a-163">Используйте [заголовок](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Head) свойства или список функций модуля [. Head](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#head).</span><span class="sxs-lookup"><span data-stu-id="ad50a-163">Use the property [Head](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Head) or the module function [List.head](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#head).</span></span> <span data-ttu-id="ad50a-164">Можно получить доступ к заключительному фрагменту списка с помощью свойства [tail](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Tail) или функции [List. tail](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#tail) .</span><span class="sxs-lookup"><span data-stu-id="ad50a-164">You can access the tail of a list by using the [Tail](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Tail) property or the [List.tail](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#tail) function.</span></span> <span data-ttu-id="ad50a-165">Чтобы найти элемент по индексу, используйте функцию [List. nth](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#nth) .</span><span class="sxs-lookup"><span data-stu-id="ad50a-165">To find an element by index, use the [List.nth](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#nth) function.</span></span> <span data-ttu-id="ad50a-166">`List.nth` проходит по списку.</span><span class="sxs-lookup"><span data-stu-id="ad50a-166">`List.nth` traverses the list.</span></span> <span data-ttu-id="ad50a-167">Таким образом, это O (*n*).</span><span class="sxs-lookup"><span data-stu-id="ad50a-167">Therefore, it is O(*n*).</span></span> <span data-ttu-id="ad50a-168">Если в коде часто используется `List.nth`, то вместо списка можно использовать массив.</span><span class="sxs-lookup"><span data-stu-id="ad50a-168">If your code uses `List.nth` frequently, you might want to consider using an array instead of a list.</span></span> <span data-ttu-id="ad50a-169">Доступ к элементам массива осуществляется через O(1).</span><span class="sxs-lookup"><span data-stu-id="ad50a-169">Element access in arrays is O(1).</span></span>

### <a name="boolean-operations-on-lists"></a><span data-ttu-id="ad50a-170">Логические операции со списками</span><span class="sxs-lookup"><span data-stu-id="ad50a-170">Boolean Operations on Lists</span></span>

<span data-ttu-id="ad50a-171">Функция [List. isEmpty](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#isEmpty) определяет, содержит ли список какие-либо элементы.</span><span class="sxs-lookup"><span data-stu-id="ad50a-171">The [List.isEmpty](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#isEmpty) function determines whether a list has any elements.</span></span>

<span data-ttu-id="ad50a-172">Функция [List. Exists](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#exists) применяет логический тест к элементам списка и возвращает значение `true` , если какой-либо элемент удовлетворяет данному тесту.</span><span class="sxs-lookup"><span data-stu-id="ad50a-172">The [List.exists](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#exists) function applies a Boolean test to elements of a list and returns `true` if any element satisfies the test.</span></span> <span data-ttu-id="ad50a-173">[List. exists2-](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#exists2) аналогичен, но работает с последовательными парами элементов в двух списках.</span><span class="sxs-lookup"><span data-stu-id="ad50a-173">[List.exists2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#exists2) is similar but operates on successive pairs of elements in two lists.</span></span>

<span data-ttu-id="ad50a-174">В следующем коде показано использование функции `List.exists`.</span><span class="sxs-lookup"><span data-stu-id="ad50a-174">The following code demonstrates the use of `List.exists`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet1.fs)]

<span data-ttu-id="ad50a-175">Вывод выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="ad50a-175">The output is as follows:</span></span>

```console
For list [0; 1; 2; 3], contains zero is true
```

<span data-ttu-id="ad50a-176">В следующем примере показано использование функции `List.exists2`.</span><span class="sxs-lookup"><span data-stu-id="ad50a-176">The following example demonstrates the use of `List.exists2`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet2.fs)]

<span data-ttu-id="ad50a-177">Вывод выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="ad50a-177">The output is as follows:</span></span>

```console
Lists [1; 2; 3; 4; 5] and [5; 4; 3; 2; 1] have at least one equal element at the same position.
```

<span data-ttu-id="ad50a-178">[List. forall](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#forall) можно использовать, если требуется проверить, соответствуют ли все элементы списка условию.</span><span class="sxs-lookup"><span data-stu-id="ad50a-178">You can use [List.forall](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#forall) if you want to test whether all the elements of a list meet a condition.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet3.fs)]

<span data-ttu-id="ad50a-179">Вывод выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="ad50a-179">The output is as follows:</span></span>

```console
true
false
```

<span data-ttu-id="ad50a-180">Аналогичным образом [List. forall2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#forall2) определяет, соответствуют ли все элементы в соответствующих позициях в двух списках логическому выражению, включающему в себя каждую пару элементов.</span><span class="sxs-lookup"><span data-stu-id="ad50a-180">Similarly, [List.forall2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#forall2) determines whether all elements in the corresponding positions in two lists satisfy a Boolean expression that involves each pair of elements.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet4.fs)]

<span data-ttu-id="ad50a-181">Вывод выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="ad50a-181">The output is as follows:</span></span>

```console
true
false
```

### <a name="sort-operations-on-lists"></a><span data-ttu-id="ad50a-182">Операции сортировки списков</span><span class="sxs-lookup"><span data-stu-id="ad50a-182">Sort Operations on Lists</span></span>

<span data-ttu-id="ad50a-183">Функции [List. Sort](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#sort), [List. sortBy](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#sortBy)и [List. сортвис](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#sortWith) сортируют списки сортировки.</span><span class="sxs-lookup"><span data-stu-id="ad50a-183">The [List.sort](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#sort), [List.sortBy](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#sortBy), and [List.sortWith](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#sortWith) functions sort lists.</span></span> <span data-ttu-id="ad50a-184">Функция сортировки определяет, какую из этих трех функций использовать.</span><span class="sxs-lookup"><span data-stu-id="ad50a-184">The sorting function determines which of these three functions to use.</span></span> <span data-ttu-id="ad50a-185">`List.sort` использует универсальное сравнение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ad50a-185">`List.sort` uses default generic comparison.</span></span> <span data-ttu-id="ad50a-186">Общее сравнение выполняется с помощью глобальных операторов на основе функции общего сравнения значений.</span><span class="sxs-lookup"><span data-stu-id="ad50a-186">Generic comparison uses global operators based on the generic compare function to compare values.</span></span> <span data-ttu-id="ad50a-187">Оно эффективно работает с различными типами элементов, такими как числовые типы, кортежи, записи, размеченные объединения, списки, массивы и любой другой тип, включающий `System.IComparable`.</span><span class="sxs-lookup"><span data-stu-id="ad50a-187">It works efficiently with a wide variety of element types, such as simple numeric types, tuples, records, discriminated unions, lists, arrays, and any type that implements `System.IComparable`.</span></span> <span data-ttu-id="ad50a-188">Для типов, включающих `System.IComparable`, общее сравнение выполняется с помощью функции `System.IComparable.CompareTo()`.</span><span class="sxs-lookup"><span data-stu-id="ad50a-188">For types that implement `System.IComparable`, generic comparison uses the `System.IComparable.CompareTo()` function.</span></span> <span data-ttu-id="ad50a-189">Общее сравнение также работает со строками, но использует культурно-независимый порядок сортировки.</span><span class="sxs-lookup"><span data-stu-id="ad50a-189">Generic comparison also works with strings, but uses a culture-independent sorting order.</span></span> <span data-ttu-id="ad50a-190">Общее сравнение не следует применять к неподдерживаемым типам, например типам функций.</span><span class="sxs-lookup"><span data-stu-id="ad50a-190">Generic comparison should not be used on unsupported types, such as function types.</span></span> <span data-ttu-id="ad50a-191">К тому же выполнение общего сравнения по умолчанию лучше всего подходит для слабо структурированных типов. Для сильно структурированных типов, которые необходимо часто сравнивать и сортировать, можно использовать функцию `System.IComparable` и метод `System.IComparable.CompareTo()`.</span><span class="sxs-lookup"><span data-stu-id="ad50a-191">Also, the performance of the default generic comparison is best for small structured types; for larger structured types that need to be compared and sorted frequently, consider implementing `System.IComparable` and providing an efficient implementation of the `System.IComparable.CompareTo()` method.</span></span>

<span data-ttu-id="ad50a-192">`List.sortBy` принимает функцию, которая возвращает значение, используемое в качестве критерия сортировки, и `List.sortWith` принимает в качестве аргумента функцию сравнения.</span><span class="sxs-lookup"><span data-stu-id="ad50a-192">`List.sortBy` takes a function that returns a value that is used as the sort criterion, and `List.sortWith` takes a comparison function as an argument.</span></span> <span data-ttu-id="ad50a-193">Две последние функции полезны при работе с типами, которые не поддерживают сравнение, а также если сравнение требует более сложной семантики, например в случае со строками, учитывающими язык и регион.</span><span class="sxs-lookup"><span data-stu-id="ad50a-193">These latter two functions are useful when you are working with types that do not support comparison, or when the comparison requires more complex comparison semantics, as in the case of culture-aware strings.</span></span>

<span data-ttu-id="ad50a-194">В следующем примере показано использование функции `List.sort`.</span><span class="sxs-lookup"><span data-stu-id="ad50a-194">The following example demonstrates the use of `List.sort`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet5.fs)]

<span data-ttu-id="ad50a-195">Вывод выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="ad50a-195">The output is as follows:</span></span>

```console
[-2; 1; 4; 5; 8]
```

<span data-ttu-id="ad50a-196">В следующем примере показано использование функции `List.sortBy`.</span><span class="sxs-lookup"><span data-stu-id="ad50a-196">The following example demonstrates the use of `List.sortBy`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet6.fs)]

<span data-ttu-id="ad50a-197">Вывод выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="ad50a-197">The output is as follows:</span></span>

```console
[1; -2; 4; 5; 8]
```

<span data-ttu-id="ad50a-198">В следующем примере показано использование `List.sortWith`.</span><span class="sxs-lookup"><span data-stu-id="ad50a-198">The next example demonstrates the use of `List.sortWith`.</span></span> <span data-ttu-id="ad50a-199">В этом примере обычная функция сравнения `compareWidgets` используется сначала для сравнения одного поля пользовательского типа, а затем другого, если значения первого поля равны.</span><span class="sxs-lookup"><span data-stu-id="ad50a-199">In this example, the custom comparison function `compareWidgets` is used to first compare one field of a custom type, and then another when the values of the first field are equal.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet7.fs)]

<span data-ttu-id="ad50a-200">Вывод выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="ad50a-200">The output is as follows:</span></span>

```console
[{ID = 92;
Rev = 1;}; {ID = 92;
Rev = 1;}; {ID = 100;
Rev = 2;}; {ID = 100;
Rev = 5;}; {ID = 110;
Rev = 1;}]
```

### <a name="search-operations-on-lists"></a><span data-ttu-id="ad50a-201">Операции поиска в списках</span><span class="sxs-lookup"><span data-stu-id="ad50a-201">Search Operations on Lists</span></span>

<span data-ttu-id="ad50a-202">Списки поддерживают различные операции поиска.</span><span class="sxs-lookup"><span data-stu-id="ad50a-202">Numerous search operations are supported for lists.</span></span> <span data-ttu-id="ad50a-203">Простейшая функция [List. Find](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#find)позволяет найти первый элемент, соответствующий заданному условию.</span><span class="sxs-lookup"><span data-stu-id="ad50a-203">The simplest, [List.find](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#find), enables you to find the first element that matches a given condition.</span></span>

<span data-ttu-id="ad50a-204">В следующем примере кода показано, как использовать `List.find` для поиска первого числа в списке, которое делится на 5.</span><span class="sxs-lookup"><span data-stu-id="ad50a-204">The following code example demonstrates the use of `List.find` to find the first number that is divisible by 5 in a list.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet8.fs)]

<span data-ttu-id="ad50a-205">Результат — 5.</span><span class="sxs-lookup"><span data-stu-id="ad50a-205">The result is 5.</span></span>

<span data-ttu-id="ad50a-206">Если элементы должны быть преобразованы первыми, вызовите [List. Pick](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#pick), который принимает функцию, возвращающую параметр, и ищет первое значение параметра, равное `Some(x)` .</span><span class="sxs-lookup"><span data-stu-id="ad50a-206">If the elements must be transformed first, call [List.pick](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#pick), which takes a function that returns an option, and looks for the first option value that is `Some(x)`.</span></span> <span data-ttu-id="ad50a-207">Вместо возвращения элемента функция `List.pick` возвращает результат `x`.</span><span class="sxs-lookup"><span data-stu-id="ad50a-207">Instead of returning the element, `List.pick` returns the result `x`.</span></span> <span data-ttu-id="ad50a-208">Если совпадения не найдены, функция `List.pick` возвращает `System.Collections.Generic.KeyNotFoundException`.</span><span class="sxs-lookup"><span data-stu-id="ad50a-208">If no matching element is found, `List.pick` throws `System.Collections.Generic.KeyNotFoundException`.</span></span> <span data-ttu-id="ad50a-209">В следующем коде показано использование `List.pick`.</span><span class="sxs-lookup"><span data-stu-id="ad50a-209">The following code shows the use of `List.pick`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet9.fs)]

<span data-ttu-id="ad50a-210">Вывод выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="ad50a-210">The output is as follows:</span></span>

```console
"b"
```

<span data-ttu-id="ad50a-211">Другая группа операций поиска, [List. tryFind](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#tryFind) и связанных функций, возвращает значение параметра.</span><span class="sxs-lookup"><span data-stu-id="ad50a-211">Another group of search operations, [List.tryFind](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#tryFind) and related functions, return an option value.</span></span> <span data-ttu-id="ad50a-212">Функция `List.tryFind` возвращает первый элемент списка, который удовлетворяет условию, если такой элемент есть, и значение параметра `None`, если нет.</span><span class="sxs-lookup"><span data-stu-id="ad50a-212">The `List.tryFind` function returns the first element of a list that satisfies a condition if such an element exists, but the option value `None` if not.</span></span> <span data-ttu-id="ad50a-213">Список вариантов [. tryFindIndex](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#tryFindIndex) возвращает индекс элемента, если он найден, а не сам элемент.</span><span class="sxs-lookup"><span data-stu-id="ad50a-213">The variation [List.tryFindIndex](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#tryFindIndex) returns the index of the element, if one is found, rather than the element itself.</span></span> <span data-ttu-id="ad50a-214">Эти функции представлены в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="ad50a-214">These functions are illustrated in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet10.fs)]

<span data-ttu-id="ad50a-215">Вывод выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="ad50a-215">The output is as follows:</span></span>

```console
The first even value is 22.
The first even value is at position 8.
```

### <a name="arithmetic-operations-on-lists"></a><span data-ttu-id="ad50a-216">Арифметические операции со списками</span><span class="sxs-lookup"><span data-stu-id="ad50a-216">Arithmetic Operations on Lists</span></span>

<span data-ttu-id="ad50a-217">Общие арифметические операции, такие как Sum и Average, встроены в [модуль List](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html).</span><span class="sxs-lookup"><span data-stu-id="ad50a-217">Common arithmetic operations such as sum and average are built into the [List module](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html).</span></span> <span data-ttu-id="ad50a-218">Для работы с [List. Sum](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#sum)тип элемента списка должен поддерживать `+` оператор и иметь нулевое значение.</span><span class="sxs-lookup"><span data-stu-id="ad50a-218">To work with [List.sum](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#sum), the list element type must support the `+` operator and have a zero value.</span></span> <span data-ttu-id="ad50a-219">Все встроенные арифметические типы удовлетворяют этим условиям.</span><span class="sxs-lookup"><span data-stu-id="ad50a-219">All built-in arithmetic types satisfy these conditions.</span></span> <span data-ttu-id="ad50a-220">Для работы с [List. Average](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#average)тип элемента должен поддерживать деление без остатка, который исключает целочисленные типы, но допускает типы с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="ad50a-220">To work with [List.average](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#average), the element type must support division without a remainder, which excludes integral types but allows for floating point types.</span></span> <span data-ttu-id="ad50a-221">Функции [List. sumBy](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#sumBy) и [List. averageBy](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#averageBy) принимают в качестве параметра функцию, а результаты этой функции используются для вычисления значений суммы или среднего значения.</span><span class="sxs-lookup"><span data-stu-id="ad50a-221">The [List.sumBy](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#sumBy) and [List.averageBy](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#averageBy) functions take a function as a parameter, and this function's results are used to calculate the values for the sum or average.</span></span>

<span data-ttu-id="ad50a-222">В следующем коде показано использование `List.sum`, `List.sumBy` и `List.average`.</span><span class="sxs-lookup"><span data-stu-id="ad50a-222">The following code demonstrates the use of `List.sum`, `List.sumBy`, and `List.average`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet11.fs)]

<span data-ttu-id="ad50a-223">В результате получается `1.000000`.</span><span class="sxs-lookup"><span data-stu-id="ad50a-223">The output is `1.000000`.</span></span>

<span data-ttu-id="ad50a-224">В следующем коде показано использование `List.averageBy`.</span><span class="sxs-lookup"><span data-stu-id="ad50a-224">The following code shows the use of `List.averageBy`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet12.fs)]

<span data-ttu-id="ad50a-225">В результате получается `5.5`.</span><span class="sxs-lookup"><span data-stu-id="ad50a-225">The output is `5.5`.</span></span>

### <a name="lists-and-tuples"></a><span data-ttu-id="ad50a-226">Списки и кортежи</span><span class="sxs-lookup"><span data-stu-id="ad50a-226">Lists and Tuples</span></span>

<span data-ttu-id="ad50a-227">Для работы со списками, содержащими кортежи, можно использовать функции упаковки и распаковки.</span><span class="sxs-lookup"><span data-stu-id="ad50a-227">Lists that contain tuples can be manipulated by zip and unzip functions.</span></span> <span data-ttu-id="ad50a-228">Они объединяют два списка с одним значением в один список кортежей или разбивают один список кортежей на два списка с одним значением.</span><span class="sxs-lookup"><span data-stu-id="ad50a-228">These functions combine two lists of single values into one list of tuples or separate one list of tuples into two lists of single values.</span></span> <span data-ttu-id="ad50a-229">Самая простая функция [List.zip](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#zip) принимает два списка отдельных элементов и создает один список пар кортежей.</span><span class="sxs-lookup"><span data-stu-id="ad50a-229">The simplest [List.zip](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#zip) function takes two lists of single elements and produces a single list of tuple pairs.</span></span> <span data-ttu-id="ad50a-230">Другая версия, [List.zip3](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#zip3), принимает три списка отдельных элементов и создает один список кортежей с тремя элементами.</span><span class="sxs-lookup"><span data-stu-id="ad50a-230">Another version, [List.zip3](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#zip3), takes three lists of single elements and produces a single list of tuples that have three elements.</span></span> <span data-ttu-id="ad50a-231">В следующем коде показано использование функции `List.zip`.</span><span class="sxs-lookup"><span data-stu-id="ad50a-231">The following code example demonstrates the use of `List.zip`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet13.fs)]

<span data-ttu-id="ad50a-232">Вывод выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="ad50a-232">The output is as follows:</span></span>

```console
[(1, -1); (2, -2); (3; -3)]
```

<span data-ttu-id="ad50a-233">В следующем коде показано использование функции `List.zip3`.</span><span class="sxs-lookup"><span data-stu-id="ad50a-233">The following code example demonstrates the use of `List.zip3`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet14.fs)]

<span data-ttu-id="ad50a-234">Вывод выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="ad50a-234">The output is as follows:</span></span>

```console
[(1, -1, 0); (2, -2, 0); (3, -3, 0)]
```

<span data-ttu-id="ad50a-235">Соответствующие версии распаковать, [List. unzip](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#unzip) и [List. unzip3](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#unzip3), принимают списки кортежей и возвращаемых списков в кортеже, где первый список содержит все элементы, которые были первыми в каждом кортеже, а второй список содержит второй элемент каждого кортежа и т. д.</span><span class="sxs-lookup"><span data-stu-id="ad50a-235">The corresponding unzip versions, [List.unzip](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#unzip) and [List.unzip3](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#unzip3), take lists of tuples and return lists in a tuple, where the first list contains all the elements that were first in each tuple, and the second list contains the second element of each tuple, and so on.</span></span>

<span data-ttu-id="ad50a-236">В следующем примере кода показано использование [List. unzip](https://msdn.microsoft.com/library/639db80c-41b5-45bb-a6b4-1eaa04d61d21).</span><span class="sxs-lookup"><span data-stu-id="ad50a-236">The following code example demonstrates the use of [List.unzip](https://msdn.microsoft.com/library/639db80c-41b5-45bb-a6b4-1eaa04d61d21).</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet15.fs)]

<span data-ttu-id="ad50a-237">Вывод выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="ad50a-237">The output is as follows:</span></span>

```console
([1; 3], [2; 4])
[1; 3] [2; 4]
```

<span data-ttu-id="ad50a-238">В следующем примере кода показано использование [List. unzip3](https://msdn.microsoft.com/library/43078c77-32ec-4342-85b3-c31ccf984db4).</span><span class="sxs-lookup"><span data-stu-id="ad50a-238">The following code example demonstrates the use of [List.unzip3](https://msdn.microsoft.com/library/43078c77-32ec-4342-85b3-c31ccf984db4).</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet16.fs)]

<span data-ttu-id="ad50a-239">Вывод выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="ad50a-239">The output is as follows:</span></span>

```console
([1; 4], [2; 5], [3; 6])
```

### <a name="operating-on-list-elements"></a><span data-ttu-id="ad50a-240">Операции с элементами списка</span><span class="sxs-lookup"><span data-stu-id="ad50a-240">Operating on List Elements</span></span>

<span data-ttu-id="ad50a-241">F# поддерживает различные операции с элементами списка.</span><span class="sxs-lookup"><span data-stu-id="ad50a-241">F# supports a variety of operations on list elements.</span></span> <span data-ttu-id="ad50a-242">Самый простой — [List. iter](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#iter), который позволяет вызывать функцию для каждого элемента списка.</span><span class="sxs-lookup"><span data-stu-id="ad50a-242">The simplest is [List.iter](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#iter), which enables you to call a function on every element of a list.</span></span> <span data-ttu-id="ad50a-243">Варианты включают [List. iter2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#iter2), который позволяет выполнить операцию над элементами двух списков, [List. iteri](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#iteri), которая похожа на `List.iter` , за исключением того, что индекс каждого элемента передается в качестве аргумента функции, которая вызывается для каждого элемента, и [List. iteri2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#iteri2), являющийся сочетанием функций `List.iter2` и `List.iteri` .</span><span class="sxs-lookup"><span data-stu-id="ad50a-243">Variations include [List.iter2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#iter2), which enables you to perform an operation on elements of two lists, [List.iteri](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#iteri), which is like `List.iter` except that the index of each element is passed as an argument to the function that is called for each element, and [List.iteri2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#iteri2), which is a combination of the functionality of `List.iter2` and `List.iteri`.</span></span> <span data-ttu-id="ad50a-244">Эти функции показаны в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="ad50a-244">The following code example illustrates these functions.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet17.fs)]

<span data-ttu-id="ad50a-245">Вывод выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="ad50a-245">The output is as follows:</span></span>

```console
List.iter: element is 1
List.iter: element is 2
List.iter: element is 3
List.iteri: element 0 is 1
List.iteri: element 1 is 2
List.iteri: element 2 is 3
List.iter2: elements are 1 4
List.iter2: elements are 2 5
List.iter2: elements are 3 6
List.iteri2: element 0 of list1 is 1; element 0 of list2 is 4
List.iteri2: element 1 of list1 is 2; element 1 of list2 is 5
List.iteri2: element 2 of list1 is 3; element 2 of list2 is 6
```

<span data-ttu-id="ad50a-246">Другой часто используемой функцией, которая преобразует элементы списка, является [List. Map](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#map), которая позволяет применить функцию к каждому элементу списка и поместит все результаты в новый список.</span><span class="sxs-lookup"><span data-stu-id="ad50a-246">Another frequently used function that transforms list elements is [List.map](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#map), which enables you to apply a function to each element of a list and put all the results into a new list.</span></span> <span data-ttu-id="ad50a-247">[List. map2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#map2) и [List. map3](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#map3) — это варианты, принимающие несколько списков.</span><span class="sxs-lookup"><span data-stu-id="ad50a-247">[List.map2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#map2) and [List.map3](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#map3) are variations that take multiple lists.</span></span> <span data-ttu-id="ad50a-248">Можно также использовать [List. MAPI](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#mapi) и [List. mapi2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#mapi2), если в дополнение к элементу, функции необходимо передать индекс каждого элемента.</span><span class="sxs-lookup"><span data-stu-id="ad50a-248">You can also use [List.mapi](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#mapi) and [List.mapi2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#mapi2), if, in addition to the element, the function needs to be passed the index of each element.</span></span> <span data-ttu-id="ad50a-249">Единственное различие между `List.mapi2` и `List.mapi` состоит в том, что функция `List.mapi2` работает с двумя списками.</span><span class="sxs-lookup"><span data-stu-id="ad50a-249">The only difference between `List.mapi2` and `List.mapi` is that `List.mapi2` works with two lists.</span></span> <span data-ttu-id="ad50a-250">В следующем примере показан [List. Map](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#map).</span><span class="sxs-lookup"><span data-stu-id="ad50a-250">The following example illustrates [List.map](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#map).</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet18.fs)]

<span data-ttu-id="ad50a-251">Вывод выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="ad50a-251">The output is as follows:</span></span>

```console
[2; 3; 4]
```

<span data-ttu-id="ad50a-252">В следующем примере показано использование `List.map2`.</span><span class="sxs-lookup"><span data-stu-id="ad50a-252">The following example shows the use of `List.map2`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet19.fs)]

<span data-ttu-id="ad50a-253">Вывод выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="ad50a-253">The output is as follows:</span></span>

```console
[5; 7; 9]
```

<span data-ttu-id="ad50a-254">В следующем примере показано использование `List.map3`.</span><span class="sxs-lookup"><span data-stu-id="ad50a-254">The following example shows the use of `List.map3`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet20.fs)]

<span data-ttu-id="ad50a-255">Вывод выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="ad50a-255">The output is as follows:</span></span>

```console
[7; 10; 13]
```

<span data-ttu-id="ad50a-256">В следующем примере показано использование `List.mapi`.</span><span class="sxs-lookup"><span data-stu-id="ad50a-256">The following example shows the use of `List.mapi`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet21.fs)]

<span data-ttu-id="ad50a-257">Вывод выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="ad50a-257">The output is as follows:</span></span>

```console
[1; 3; 5]
```

<span data-ttu-id="ad50a-258">В следующем примере показано использование `List.mapi2`.</span><span class="sxs-lookup"><span data-stu-id="ad50a-258">The following example shows the use of `List.mapi2`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet22.fs)]

<span data-ttu-id="ad50a-259">Вывод выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="ad50a-259">The output is as follows:</span></span>

```console
[0; 7; 18]
```

<span data-ttu-id="ad50a-260">[List. собирающий](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#collect) аналогичен `List.map` , за исключением того, что каждый элемент создает список, а все эти списки объединяются в окончательный список.</span><span class="sxs-lookup"><span data-stu-id="ad50a-260">[List.collect](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#collect) is like `List.map`, except that each element produces a list and all these lists are concatenated into a final list.</span></span> <span data-ttu-id="ad50a-261">В следующем коде каждый элемент списка генерирует три числа.</span><span class="sxs-lookup"><span data-stu-id="ad50a-261">In the following code, each element of the list generates three numbers.</span></span> <span data-ttu-id="ad50a-262">Все они собираются в один список.</span><span class="sxs-lookup"><span data-stu-id="ad50a-262">These are all collected into one list.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet23.fs)]

<span data-ttu-id="ad50a-263">Вывод выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="ad50a-263">The output is as follows:</span></span>

```console
[1; 2; 3; 2; 4; 6; 3; 6; 9]
```

<span data-ttu-id="ad50a-264">Можно также использовать [List. Filter](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#filter), который принимает логическое условие и создает новый список, состоящий только из элементов, которые соответствуют заданному условию.</span><span class="sxs-lookup"><span data-stu-id="ad50a-264">You can also use [List.filter](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#filter), which takes a Boolean condition and produces a new list that consists only of elements that satisfy the given condition.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet24.fs)]

<span data-ttu-id="ad50a-265">Результатом является список `[2; 4; 6]`.</span><span class="sxs-lookup"><span data-stu-id="ad50a-265">The resulting list is `[2; 4; 6]`.</span></span>

<span data-ttu-id="ad50a-266">Сочетание Map и Filter, [List. Choose](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#choose) позволяет одновременно преобразовывать и выбирать элементы.</span><span class="sxs-lookup"><span data-stu-id="ad50a-266">A combination of map and filter, [List.choose](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#choose) enables you to transform and select elements at the same time.</span></span> <span data-ttu-id="ad50a-267">`List.choose` применяет функцию, возвращающую параметр для каждого элемента списка, и возвращает новый список результатов для элементов, когда функция возвращает значение параметра `Some` .</span><span class="sxs-lookup"><span data-stu-id="ad50a-267">`List.choose` applies a function that returns an option to each element of a list, and returns a new list of the results for elements when the function returns the option value `Some`.</span></span>

<span data-ttu-id="ad50a-268">В следующем коде показано использование функции `List.choose` для выбора из списка слов с заглавными буквами.</span><span class="sxs-lookup"><span data-stu-id="ad50a-268">The following code demonstrates the use of `List.choose` to select capitalized words out of a list of words.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet25.fs)]

<span data-ttu-id="ad50a-269">Вывод выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="ad50a-269">The output is as follows:</span></span>

```console
["Rome's"; "Bob's"]
```

### <a name="operating-on-multiple-lists"></a><span data-ttu-id="ad50a-270">Операции с несколькими списками</span><span class="sxs-lookup"><span data-stu-id="ad50a-270">Operating on Multiple Lists</span></span>

<span data-ttu-id="ad50a-271">Списки могут быть объединены.</span><span class="sxs-lookup"><span data-stu-id="ad50a-271">Lists can be joined together.</span></span> <span data-ttu-id="ad50a-272">Чтобы объединить два списка в один, используйте [List. append](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#append).</span><span class="sxs-lookup"><span data-stu-id="ad50a-272">To join two lists into one, use [List.append](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#append).</span></span> <span data-ttu-id="ad50a-273">Для объединения более двух списков используйте [List. Concat](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#concat).</span><span class="sxs-lookup"><span data-stu-id="ad50a-273">To join more than two lists, use [List.concat](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#concat).</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet26.fs)]

### <a name="fold-and-scan-operations"></a><span data-ttu-id="ad50a-274">Операции сворачивания и сканирования</span><span class="sxs-lookup"><span data-stu-id="ad50a-274">Fold and Scan Operations</span></span>

<span data-ttu-id="ad50a-275">Некоторые операции со списками включают взаимозависимости между всеми элементами списка.</span><span class="sxs-lookup"><span data-stu-id="ad50a-275">Some list operations involve interdependencies between all of the list elements.</span></span> <span data-ttu-id="ad50a-276">Операции свертывания и сканирования подобны `List.iter` и `List.map` в том, что вы вызываете функцию для каждого элемента, но эти операции предоставляют дополнительный параметр, называемый *накопительным* , который передает информацию через вычисления.</span><span class="sxs-lookup"><span data-stu-id="ad50a-276">The fold and scan operations are like `List.iter` and `List.map` in that you invoke a function on each element, but these operations provide an additional parameter called the *accumulator* that carries information through the computation.</span></span>

<span data-ttu-id="ad50a-277">`List.fold` можно использовать для выполнения расчетов со списком.</span><span class="sxs-lookup"><span data-stu-id="ad50a-277">Use `List.fold` to perform a calculation on a list.</span></span>

<span data-ttu-id="ad50a-278">В следующем примере кода показано использование [List. fold](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#fold) для выполнения различных операций.</span><span class="sxs-lookup"><span data-stu-id="ad50a-278">The following code example demonstrates the use of [List.fold](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#fold) to perform various operations.</span></span>

<span data-ttu-id="ad50a-279">Лист обходится. Аккумулятор `acc` — это значение, которое передается дальше, пока продолжается расчет.</span><span class="sxs-lookup"><span data-stu-id="ad50a-279">The list is traversed; the accumulator `acc` is a value that is passed along as the calculation proceeds.</span></span> <span data-ttu-id="ad50a-280">Первый аргумент забирает аккумулятор и элемент списка и возвращает промежуточный результат расчета для этого элемента списка.</span><span class="sxs-lookup"><span data-stu-id="ad50a-280">The first argument takes the accumulator and the list element, and returns the interim result of the calculation for that list element.</span></span> <span data-ttu-id="ad50a-281">Второй аргумент является исходным значением аккумулятора.</span><span class="sxs-lookup"><span data-stu-id="ad50a-281">The second argument is the initial value of the accumulator.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet27.fs)]

<span data-ttu-id="ad50a-282">Версии этих функций с цифрой в имени функции работают с несколькими списками.</span><span class="sxs-lookup"><span data-stu-id="ad50a-282">The versions of these functions that have a digit in the function name operate on more than one list.</span></span> <span data-ttu-id="ad50a-283">Например, [List. fold2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#fold2) выполняет вычисления в двух списках.</span><span class="sxs-lookup"><span data-stu-id="ad50a-283">For example, [List.fold2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#fold2) performs computations on two lists.</span></span>

<span data-ttu-id="ad50a-284">В следующем примере показано использование функции `List.fold2`.</span><span class="sxs-lookup"><span data-stu-id="ad50a-284">The following example demonstrates the use of `List.fold2`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet28.fs)]

<span data-ttu-id="ad50a-285">`List.fold` и [List. Scan](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#scan) различаются в, `List.fold` возвращающие окончательное значение дополнительного параметра, но `List.scan` возвращает список промежуточных значений (вместе с окончательным значением) дополнительного параметра.</span><span class="sxs-lookup"><span data-stu-id="ad50a-285">`List.fold` and [List.scan](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#scan) differ in that `List.fold` returns the final value of the extra parameter, but `List.scan` returns the list of the intermediate values (along with the final value) of the extra parameter.</span></span>

<span data-ttu-id="ad50a-286">Каждая из этих функций включает обратную вариацию, например [List. foldBack](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#foldBack), которая отличается в порядке обхода списка и порядком аргументов.</span><span class="sxs-lookup"><span data-stu-id="ad50a-286">Each of these functions includes a reverse variation, for example, [List.foldBack](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#foldBack), which differs in the order in which the list is traversed and the order of the arguments.</span></span> <span data-ttu-id="ad50a-287">Кроме того, `List.fold` и `List.foldBack` имеют варианты [List. fold2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#fold2) и [List. foldBack2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#foldBack2), которые принимают два списка одинаковой длины.</span><span class="sxs-lookup"><span data-stu-id="ad50a-287">Also, `List.fold` and `List.foldBack` have variations, [List.fold2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#fold2) and [List.foldBack2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#foldBack2), that take two lists of equal length.</span></span> <span data-ttu-id="ad50a-288">Функция, которая выполняется по каждому элементу, может использовать соответствующие элементы обоих списков для выполнения некоторых действий.</span><span class="sxs-lookup"><span data-stu-id="ad50a-288">The function that executes on each element can use corresponding elements of both lists to perform some action.</span></span> <span data-ttu-id="ad50a-289">Типы элементов этих списков могут отличаться, как в следующем примере, где один список содержит суммы транзакций на банковском счете, а другой — типы транзакций (внесение или снятие).</span><span class="sxs-lookup"><span data-stu-id="ad50a-289">The element types of the two lists can be different, as in the following example, in which one list contains transaction amounts for a bank account, and the other list contains the type of transaction: deposit or withdrawal.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet29.fs)]

<span data-ttu-id="ad50a-290">При расчете суммы функции `List.fold` и `List.foldBack` действуют одинаково, так как результат не зависит от порядка обхода.</span><span class="sxs-lookup"><span data-stu-id="ad50a-290">For a calculation like summation, `List.fold` and `List.foldBack` have the same effect because the result does not depend on the order of traversal.</span></span> <span data-ttu-id="ad50a-291">В следующем примере кода функция `List.foldBack` используется для добавления элемента в список.</span><span class="sxs-lookup"><span data-stu-id="ad50a-291">In the following example, `List.foldBack` is used to add the elements in a list.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet30.fs)]

<span data-ttu-id="ad50a-292">В следующем примере снова используется банковский счет.</span><span class="sxs-lookup"><span data-stu-id="ad50a-292">The following example returns to the bank account example.</span></span> <span data-ttu-id="ad50a-293">В этот раз добавляется новый тип транзакций: расчет процентов.</span><span class="sxs-lookup"><span data-stu-id="ad50a-293">This time a new transaction type is added: an interest calculation.</span></span> <span data-ttu-id="ad50a-294">Конечный баланс теперь зависит от порядка транзакций.</span><span class="sxs-lookup"><span data-stu-id="ad50a-294">The ending balance now depends on the order of transactions.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet34.fs)]

<span data-ttu-id="ad50a-295">Список функций [. reduce](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#reduce) в некоторой степени аналогичен `List.fold` и `List.scan` , за исключением того, что вместо того, чтобы передавать отдельный агрегат, `List.reduce` принимает функцию, которая принимает два аргумента типа элемента, а не только один, а один из этих аргументов выступает в качестве совокупного, то есть сохраняет промежуточный результат вычисления.</span><span class="sxs-lookup"><span data-stu-id="ad50a-295">The function [List.reduce](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#reduce) is somewhat like `List.fold` and `List.scan`, except that instead of passing around a separate accumulator, `List.reduce` takes a function that takes two arguments of the element type instead of just one, and one of those arguments acts as the accumulator, meaning that it stores the intermediate result of the computation.</span></span> <span data-ttu-id="ad50a-296">`List.reduce` начинается с работы на первых двух элементах списка, а затем использует результат операции вместе со следующим элементом.</span><span class="sxs-lookup"><span data-stu-id="ad50a-296">`List.reduce` starts by operating on the first two list elements, and then uses the result of the operation along with the next element.</span></span> <span data-ttu-id="ad50a-297">Так как здесь нет отдельного аккумулятора с собственным типом, функция `List.reduce` может использоваться вместо `List.fold` только в том случае, если аккумулятор и элемент имеют одинаковые типы.</span><span class="sxs-lookup"><span data-stu-id="ad50a-297">Because there is not a separate accumulator that has its own type, `List.reduce` can be used in place of `List.fold` only when the accumulator and the element type have the same type.</span></span> <span data-ttu-id="ad50a-298">В следующем коде показано использование функции `List.reduce`.</span><span class="sxs-lookup"><span data-stu-id="ad50a-298">The following code demonstrates the use of `List.reduce`.</span></span> <span data-ttu-id="ad50a-299">`List.reduce` создает исключение, если предоставленный список не содержит элементов.</span><span class="sxs-lookup"><span data-stu-id="ad50a-299">`List.reduce` throws an exception if the list provided has no elements.</span></span>

<span data-ttu-id="ad50a-300">В следующем коде первый вызов лямбда-выражения дает аргументы 2 и 4 и возвращает 6. В следующем вызове даются аргументы 6 и 10 и возвращается результат 16.</span><span class="sxs-lookup"><span data-stu-id="ad50a-300">In the following code, the first call to the lambda expression is given the arguments 2 and 4, and returns 6, and the next call is given the arguments 6 and 10, so the result is 16.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet33.fs)]

### <a name="converting-between-lists-and-other-collection-types"></a><span data-ttu-id="ad50a-301">Конвертация списков и другие типы коллекций</span><span class="sxs-lookup"><span data-stu-id="ad50a-301">Converting Between Lists and Other Collection Types</span></span>

<span data-ttu-id="ad50a-302">Модуль `List` предоставляет функции для прямой и обратной конвертации обоих последовательностей и массивов.</span><span class="sxs-lookup"><span data-stu-id="ad50a-302">The `List` module provides functions for converting to and from both sequences and arrays.</span></span> <span data-ttu-id="ad50a-303">Для преобразования в последовательность или из последовательности используйте [List. toSeq](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#toSeq) или [List. ofSeq](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#ofSeq).</span><span class="sxs-lookup"><span data-stu-id="ad50a-303">To convert to or from a sequence, use [List.toSeq](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#toSeq) or [List.ofSeq](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#ofSeq).</span></span> <span data-ttu-id="ad50a-304">Для преобразования в массив или из массива используйте [List. ToArray](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#toArray) или [List. офаррай](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#ofArray).</span><span class="sxs-lookup"><span data-stu-id="ad50a-304">To convert to or from an array, use [List.toArray](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#toArray) or [List.ofArray](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#ofArray).</span></span>

### <a name="additional-operations"></a><span data-ttu-id="ad50a-305">Дополнительные операции</span><span class="sxs-lookup"><span data-stu-id="ad50a-305">Additional Operations</span></span>

<span data-ttu-id="ad50a-306">Дополнительные сведения о дополнительных операциях [со списками см. в](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html)разделе Справочник по библиотекам.</span><span class="sxs-lookup"><span data-stu-id="ad50a-306">For information about additional operations on lists, see the library reference topic [List Module](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html).</span></span>

## <a name="see-also"></a><span data-ttu-id="ad50a-307">См. также</span><span class="sxs-lookup"><span data-stu-id="ad50a-307">See also</span></span>

- [<span data-ttu-id="ad50a-308">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="ad50a-308">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="ad50a-309">Типы языка F#</span><span class="sxs-lookup"><span data-stu-id="ad50a-309">F# Types</span></span>](fsharp-types.md)
- [<span data-ttu-id="ad50a-310">Последовательности</span><span class="sxs-lookup"><span data-stu-id="ad50a-310">Sequences</span></span>](sequences.md)
- [<span data-ttu-id="ad50a-311">Массивы</span><span class="sxs-lookup"><span data-stu-id="ad50a-311">Arrays</span></span>](arrays.md)
- [<span data-ttu-id="ad50a-312">Параметры</span><span class="sxs-lookup"><span data-stu-id="ad50a-312">Options</span></span>](options.md)
