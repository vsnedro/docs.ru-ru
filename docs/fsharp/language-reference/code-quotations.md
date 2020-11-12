---
title: Цитирование кода
description: 'Узнайте о цитатах кода F #, языковой функции, позволяющей программно создавать выражения кода F # и работать с ними.'
ms.date: 08/13/2020
ms.openlocfilehash: dc37fdbd6cd29e5ee94e5c0186dfe2bfeb666f32
ms.sourcegitcommit: f99115e12a5eb75638abe45072e023a3ce3351ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2020
ms.locfileid: "94557198"
---
# <a name="code-quotations"></a><span data-ttu-id="1c161-103">Цитаты кода</span><span class="sxs-lookup"><span data-stu-id="1c161-103">Code quotations</span></span>

<span data-ttu-id="1c161-104">В этой статье описываются *цитаты кода* , функции языка, позволяющие программно создавать выражения кода F # и работать с ними.</span><span class="sxs-lookup"><span data-stu-id="1c161-104">This article describes *code quotations* , a language feature that enables you to generate and work with F# code expressions programmatically.</span></span> <span data-ttu-id="1c161-105">Эта функция позволяет создать абстрактное дерево синтаксиса, представляющее код F #.</span><span class="sxs-lookup"><span data-stu-id="1c161-105">This feature lets you generate an abstract syntax tree that represents F# code.</span></span> <span data-ttu-id="1c161-106">Затем дерево абстрактного синтаксиса можно просмотреть и обработать в соответствии с потребностями приложения.</span><span class="sxs-lookup"><span data-stu-id="1c161-106">The abstract syntax tree can then be traversed and processed according to the needs of your application.</span></span> <span data-ttu-id="1c161-107">Например, дерево можно использовать для создания кода F # или создания кода на другом языке.</span><span class="sxs-lookup"><span data-stu-id="1c161-107">For example, you can use the tree to generate F# code or generate code in some other language.</span></span>

## <a name="quoted-expressions"></a><span data-ttu-id="1c161-108">Выражения в кавычках</span><span class="sxs-lookup"><span data-stu-id="1c161-108">Quoted Expressions</span></span>

<span data-ttu-id="1c161-109">*Заключенное в кавычки выражение* — это выражение F # в коде, которое отделяется таким образом, что оно не компилируется как часть программы, а компилируется в объект, представляющий выражение f #.</span><span class="sxs-lookup"><span data-stu-id="1c161-109">A *quoted expression* is an F# expression in your code that is delimited in such a way that it is not compiled as part of your program, but instead is compiled into an object that represents an F# expression.</span></span> <span data-ttu-id="1c161-110">Можно пометить выражение в кавычках одним из двух способов: с информацией о типе или без сведений о типе.</span><span class="sxs-lookup"><span data-stu-id="1c161-110">You can mark a quoted expression in one of two ways: either with type information or without type information.</span></span> <span data-ttu-id="1c161-111">Если вы хотите включить сведения о типах, используйте символы `<@` и `@>` для разделения выражения в кавычках.</span><span class="sxs-lookup"><span data-stu-id="1c161-111">If you want to include type information, you use the symbols `<@` and `@>` to delimit the quoted expression.</span></span> <span data-ttu-id="1c161-112">Если сведения о типах не требуются, используются символы `<@@` и `@@>` .</span><span class="sxs-lookup"><span data-stu-id="1c161-112">If you do not need type information, you use the symbols `<@@` and `@@>`.</span></span> <span data-ttu-id="1c161-113">В следующем коде показаны типизированные и нетипизированные предложения.</span><span class="sxs-lookup"><span data-stu-id="1c161-113">The following code shows typed and untyped quotations.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet501.fs)]

<span data-ttu-id="1c161-114">Обход большого дерева выражения выполняется быстрее, если не включать сведения о типе.</span><span class="sxs-lookup"><span data-stu-id="1c161-114">Traversing a large expression tree is faster if you do not include type information.</span></span> <span data-ttu-id="1c161-115">Результирующий тип выражения, заключенного в кавычки с типизированными символами, — это `Expr<'T>` , где параметр типа имеет тип выражения, как определено алгоритмом вывода типа компилятора F #.</span><span class="sxs-lookup"><span data-stu-id="1c161-115">The resulting type of an expression quoted with the typed symbols is `Expr<'T>`, where the type parameter has the type of the expression as determined by the F# compiler's type inference algorithm.</span></span> <span data-ttu-id="1c161-116">При использовании цитат кода без сведений о типе тип выражения, заключенного в кавычки, является выражением типа, не являющимся универсальным типом [expr](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-fsharpexpr.html).</span><span class="sxs-lookup"><span data-stu-id="1c161-116">When you use code quotations without type information, the type of the quoted expression is the non-generic type [Expr](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-fsharpexpr.html).</span></span> <span data-ttu-id="1c161-117">[Raw](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-fsharpexpr-1.html#Raw) `Expr` Для получения нетипизированного объекта можно вызвать свойство RAW для типизированного класса `Expr` .</span><span class="sxs-lookup"><span data-stu-id="1c161-117">You can call the [Raw](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-fsharpexpr-1.html#Raw) property on the typed `Expr` class to obtain the untyped `Expr` object.</span></span>

<span data-ttu-id="1c161-118">Существуют разнообразные статические методы, позволяющие программно создавать объекты выражений F # в `Expr` классе без использования заключенных в кавычки выражений.</span><span class="sxs-lookup"><span data-stu-id="1c161-118">There are a variety of static methods that allow you to generate F# expression objects programmatically in the `Expr` class without using quoted expressions.</span></span>

<span data-ttu-id="1c161-119">Обратите внимание, что цитата кода должна включать выражение Complete.</span><span class="sxs-lookup"><span data-stu-id="1c161-119">Note that a code quotation must include a complete expression.</span></span> <span data-ttu-id="1c161-120">Например, для `let` привязки требуется как определение связанного имени, так и дополнительное выражение, использующее привязку.</span><span class="sxs-lookup"><span data-stu-id="1c161-120">For a `let` binding, for example, you need both the definition of the bound name and an additional expression that uses the binding.</span></span> <span data-ttu-id="1c161-121">В подробном синтаксисе это выражение, следующее за `in` ключевым словом.</span><span class="sxs-lookup"><span data-stu-id="1c161-121">In verbose syntax, this is an expression that follows the `in` keyword.</span></span> <span data-ttu-id="1c161-122">На верхнем уровне в модуле это просто следующее выражение в модуле, но в кавычках оно требуется явным образом.</span><span class="sxs-lookup"><span data-stu-id="1c161-122">At the top-level in a module, this is just the next expression in the module, but in a quotation, it is explicitly required.</span></span>

<span data-ttu-id="1c161-123">Поэтому следующее выражение является недопустимым.</span><span class="sxs-lookup"><span data-stu-id="1c161-123">Therefore, the following expression is not valid.</span></span>

```fsharp
// Not valid:
// <@ let f x = x + 1 @>
```

<span data-ttu-id="1c161-124">Однако следующие выражения являются допустимыми.</span><span class="sxs-lookup"><span data-stu-id="1c161-124">But the following expressions are valid.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet502.fs)]

<span data-ttu-id="1c161-125">Для вычисления предложений F # необходимо использовать [средство оценки предложений f #](https://github.com/fsprojects/FSharp.Quotations.Evaluator).</span><span class="sxs-lookup"><span data-stu-id="1c161-125">To evaluate F# quotations, you must use the [F# Quotation Evaluator](https://github.com/fsprojects/FSharp.Quotations.Evaluator).</span></span> <span data-ttu-id="1c161-126">Он обеспечивает поддержку оценки и исполнения объектов выражений F #.</span><span class="sxs-lookup"><span data-stu-id="1c161-126">It provides support for evaluating and executing F# expression objects.</span></span>

<span data-ttu-id="1c161-127">В кавычки F # также сохранены сведения об ограничениях типов.</span><span class="sxs-lookup"><span data-stu-id="1c161-127">F# quotations also retain type constraint information.</span></span> <span data-ttu-id="1c161-128">Рассмотрим следующий пример.</span><span class="sxs-lookup"><span data-stu-id="1c161-128">Consider the following example:</span></span>

```fsharp
open FSharp.Linq.RuntimeHelpers

let eval q = LeafExpressionConverter.EvaluateQuotation q

let inline negate x = -x
// val inline negate: x: ^a ->  ^a when  ^a : (static member ( ~- ) :  ^a ->  ^a)

<@ negate 1.0 @>  |> eval
```

<span data-ttu-id="1c161-129">Ограничение, созданное `inline` функцией, сохраняется в коде кутоатион.</span><span class="sxs-lookup"><span data-stu-id="1c161-129">The constraint generated by the `inline` function is retained in the code qutoation.</span></span> <span data-ttu-id="1c161-130">`negate`Теперь можно вычислить форму куотатед функции.</span><span class="sxs-lookup"><span data-stu-id="1c161-130">The `negate` function's quotated form can now be evaluated.</span></span>

## <a name="expr-type"></a><span data-ttu-id="1c161-131">Тип выражения</span><span class="sxs-lookup"><span data-stu-id="1c161-131">Expr Type</span></span>

<span data-ttu-id="1c161-132">Экземпляр `Expr` типа представляет выражение F #.</span><span class="sxs-lookup"><span data-stu-id="1c161-132">An instance of the `Expr` type represents an F# expression.</span></span> <span data-ttu-id="1c161-133">Универсальные и неуниверсальные `Expr` типы описаны в документации по библиотеке F #.</span><span class="sxs-lookup"><span data-stu-id="1c161-133">Both the generic and the non-generic `Expr` types are documented in the F# library documentation.</span></span> <span data-ttu-id="1c161-134">Дополнительные сведения см. в разделе Классы [FSharp. цитирований](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations.html) и [предложения. expr](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-fsharpexpr.html).</span><span class="sxs-lookup"><span data-stu-id="1c161-134">For more information, see [FSharp.Quotations Namespace](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations.html) and [Quotations.Expr Class](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-fsharpexpr.html).</span></span>

## <a name="splicing-operators"></a><span data-ttu-id="1c161-135">Операторы объединения</span><span class="sxs-lookup"><span data-stu-id="1c161-135">Splicing Operators</span></span>

<span data-ttu-id="1c161-136">Объединение позволяет комбинировать цитаты с литеральным кодом с выражениями, созданными программно или из другой цитаты в виде кода.</span><span class="sxs-lookup"><span data-stu-id="1c161-136">Splicing enables you to combine literal code quotations with expressions that you have created programmatically or from another code quotation.</span></span> <span data-ttu-id="1c161-137">`%`Операторы и `%%` позволяют добавлять объект выражения F # в цитату кода.</span><span class="sxs-lookup"><span data-stu-id="1c161-137">The `%` and `%%` operators enable you to add an F# expression object into a code quotation.</span></span> <span data-ttu-id="1c161-138">`%`Оператор используется для вставки объекта типизированного выражения в типизированную кавычку; `%%` оператор используется для вставки нетипизированного объекта выражения в нетипизированное предложение.</span><span class="sxs-lookup"><span data-stu-id="1c161-138">You use the `%` operator to insert a typed expression object into a typed quotation; you use the `%%` operator to insert an untyped expression object into an untyped quotation.</span></span> <span data-ttu-id="1c161-139">Оба оператора являются унарными префиксными операторами.</span><span class="sxs-lookup"><span data-stu-id="1c161-139">Both operators are unary prefix operators.</span></span> <span data-ttu-id="1c161-140">Таким образом `expr` , если является нетипизированным выражением типа `Expr` , следующий код является допустимым.</span><span class="sxs-lookup"><span data-stu-id="1c161-140">Thus if `expr` is an untyped expression of type `Expr`, the following code is valid.</span></span>

```fsharp
<@@ 1 + %%expr @@>
```

<span data-ttu-id="1c161-141">И если `expr` является типизированной кавычкой типа `Expr<int>` , следующий код является допустимым.</span><span class="sxs-lookup"><span data-stu-id="1c161-141">And if `expr` is a typed quotation of type `Expr<int>`, the following code is valid.</span></span>

```fsharp
<@ 1 + %expr @>
```

## <a name="example"></a><span data-ttu-id="1c161-142">Пример</span><span class="sxs-lookup"><span data-stu-id="1c161-142">Example</span></span>

### <a name="description"></a><span data-ttu-id="1c161-143">Описание</span><span class="sxs-lookup"><span data-stu-id="1c161-143">Description</span></span>

<span data-ttu-id="1c161-144">В следующем примере показано использование цитат кода для помещения кода F # в объект выражения, а затем Печать кода F #, представляющего выражение.</span><span class="sxs-lookup"><span data-stu-id="1c161-144">The following example illustrates the use of code quotations to put F# code into an expression object and then print the F# code that represents the expression.</span></span> <span data-ttu-id="1c161-145">`println`Определена функция, которая содержит рекурсивную функцию `print` , которая отображает объект выражения F # (типа `Expr` ) в удобном формате.</span><span class="sxs-lookup"><span data-stu-id="1c161-145">A function `println` is defined that contains a recursive function `print` that displays an F# expression object (of type `Expr`) in a friendly format.</span></span> <span data-ttu-id="1c161-146">Существует несколько активных шаблонов в модулях [FSharp. цитирований. Patterns](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-patternsmodule.html) и [FSharp. цитирований. активный шаблон derivedpatterns](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-derivedpatternsmodule.html) , которые можно использовать для анализа объектов выражений.</span><span class="sxs-lookup"><span data-stu-id="1c161-146">There are several active patterns in the [FSharp.Quotations.Patterns](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-patternsmodule.html) and [FSharp.Quotations.DerivedPatterns](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-derivedpatternsmodule.html) modules that can be used to analyze expression objects.</span></span> <span data-ttu-id="1c161-147">Этот пример не включает все возможные закономерности, которые могут появляться в выражении F #.</span><span class="sxs-lookup"><span data-stu-id="1c161-147">This example does not include all the possible patterns that might appear in an F# expression.</span></span> <span data-ttu-id="1c161-148">Любой нераспознанный шаблон активирует совпадение с шаблоном шаблона ( `_` ) и подготавливается к просмотру с помощью `ToString` метода, который в `Expr` типе позволяет знать активный шаблон для добавления в выражение соответствия.</span><span class="sxs-lookup"><span data-stu-id="1c161-148">Any unrecognized pattern triggers a match to the wildcard pattern (`_`) and is rendered by using the `ToString` method, which, on the `Expr` type, lets you know the active pattern to add to your match expression.</span></span>

### <a name="code"></a><span data-ttu-id="1c161-149">Код</span><span class="sxs-lookup"><span data-stu-id="1c161-149">Code</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet601.fs)]

### <a name="output"></a><span data-ttu-id="1c161-150">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="1c161-150">Output</span></span>

```fsharp
fun (x:System.Int32) -> x + 1
a + 1
let f = fun (x:System.Int32) -> x + 10 in f 10
```

## <a name="example"></a><span data-ttu-id="1c161-151">Пример</span><span class="sxs-lookup"><span data-stu-id="1c161-151">Example</span></span>

### <a name="description"></a><span data-ttu-id="1c161-152">Описание</span><span class="sxs-lookup"><span data-stu-id="1c161-152">Description</span></span>

<span data-ttu-id="1c161-153">Вы также можете использовать три активных шаблона в [модуле експршапе](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-exprshapemodule.html) для прохода по деревьям выражений с меньшим количеством активных шаблонов.</span><span class="sxs-lookup"><span data-stu-id="1c161-153">You can also use the three active patterns in the [ExprShape module](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-exprshapemodule.html) to traverse expression trees with fewer active patterns.</span></span> <span data-ttu-id="1c161-154">Эти активные шаблоны могут оказаться полезными, если требуется пройти по дереву, но не требуется вся информация в большинстве узлов.</span><span class="sxs-lookup"><span data-stu-id="1c161-154">These active patterns can be useful when you want to traverse a tree but you do not need all the information in most of the nodes.</span></span> <span data-ttu-id="1c161-155">При использовании этих шаблонов любое выражение F # соответствует одному из следующих трех шаблонов: `ShapeVar` , если выражение является переменной, `ShapeLambda` Если выражение является лямбда-выражением, или `ShapeCombination` Если выражение является любым другим.</span><span class="sxs-lookup"><span data-stu-id="1c161-155">When you use these patterns, any F# expression matches one of the following three patterns: `ShapeVar` if the expression is a variable, `ShapeLambda` if the expression is a lambda expression, or `ShapeCombination` if the expression is anything else.</span></span> <span data-ttu-id="1c161-156">Если вы просматриваете дерево выражения с помощью активных шаблонов, как в предыдущем примере кода, необходимо использовать гораздо больше шаблонов для управления всеми возможными типами выражений F #, и код будет более сложен.</span><span class="sxs-lookup"><span data-stu-id="1c161-156">If you traverse an expression tree by using the active patterns as in the previous code example, you have to use many more patterns to handle all possible F# expression types, and your code will be more complex.</span></span> <span data-ttu-id="1c161-157">Дополнительные сведения см. в разделе [експршапе. шапевар&#124;шапеламбда&#124;Шапекомбинатион Active Pattern](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-exprshapemodule.html#(%20|ShapeVar|ShapeLambda|ShapeCombination|%20)).</span><span class="sxs-lookup"><span data-stu-id="1c161-157">For more information, see [ExprShape.ShapeVar&#124;ShapeLambda&#124;ShapeCombination Active Pattern](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-exprshapemodule.html#(%20|ShapeVar|ShapeLambda|ShapeCombination|%20)).</span></span>

<span data-ttu-id="1c161-158">Следующий пример кода можно использовать в качестве основания для более сложных обходов.</span><span class="sxs-lookup"><span data-stu-id="1c161-158">The following code example can be used as a basis for more complex traversals.</span></span> <span data-ttu-id="1c161-159">В этом коде дерево выражения создается для выражения, включающего вызов функции, `add` .</span><span class="sxs-lookup"><span data-stu-id="1c161-159">In this code, an expression tree is created for an expression that involves a function call, `add`.</span></span> <span data-ttu-id="1c161-160">Активный шаблон [спеЦификкалл](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-derivedpatternsmodule.html#(%20|SpecificCall|_|%20)) используется для обнаружения любого вызова `add` в дереве выражения.</span><span class="sxs-lookup"><span data-stu-id="1c161-160">The [SpecificCall](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-derivedpatternsmodule.html#(%20|SpecificCall|_|%20)) active pattern is used to detect any call to `add` in the expression tree.</span></span> <span data-ttu-id="1c161-161">Этот активный шаблон назначает аргументы вызова `exprList` значения.</span><span class="sxs-lookup"><span data-stu-id="1c161-161">This active pattern assigns the arguments of the call to the `exprList` value.</span></span> <span data-ttu-id="1c161-162">В этом случае существует только два, поэтому они извлекаются, и функция вызывается рекурсивно для аргументов.</span><span class="sxs-lookup"><span data-stu-id="1c161-162">In this case, there are only two, so these are pulled out and the function is called recursively on the arguments.</span></span> <span data-ttu-id="1c161-163">Результаты вставляются в цитату кода, которая представляет вызов с `mul` помощью оператора splice ( `%%` ).</span><span class="sxs-lookup"><span data-stu-id="1c161-163">The results are inserted into a code quotation that represents a call to `mul` by using the splice operator (`%%`).</span></span> <span data-ttu-id="1c161-164">`println`Функция из предыдущего примера используется для вывода результатов.</span><span class="sxs-lookup"><span data-stu-id="1c161-164">The `println` function from the previous example is used to display the results.</span></span>

<span data-ttu-id="1c161-165">Код в других активных ветвях шаблонов просто повторно создает одно и то же дерево выражения, поэтому единственное изменение в результирующем выражении — это изменение с `add` на `mul` .</span><span class="sxs-lookup"><span data-stu-id="1c161-165">The code in the other active pattern branches just regenerates the same expression tree, so the only change in the resulting expression is the change from `add` to `mul`.</span></span>

### <a name="code"></a><span data-ttu-id="1c161-166">Код</span><span class="sxs-lookup"><span data-stu-id="1c161-166">Code</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet701.fs)]

### <a name="output"></a><span data-ttu-id="1c161-167">Вывод</span><span class="sxs-lookup"><span data-stu-id="1c161-167">Output</span></span>

```fsharp
1 + Module1.add(2,Module1.add(3,4))
1 + Module1.mul(2,Module1.mul(3,4))
```

## <a name="see-also"></a><span data-ttu-id="1c161-168">См. также</span><span class="sxs-lookup"><span data-stu-id="1c161-168">See also</span></span>

- [<span data-ttu-id="1c161-169">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="1c161-169">F# Language Reference</span></span>](index.md)
