---
title: Справочник по C#. Типы кортежей
description: Сведения о кортежах C# — упрощенных структурах данных, которые можно использовать для группировки слабо связанных элементов данных.
ms.date: 07/09/2020
helpviewer_keywords:
- value tuples [C#]
ms.openlocfilehash: d996c7afecba1b58bfd8337fa444fd71790dd482
ms.sourcegitcommit: 870bc4b4087510f6fba3c7b1c0d391f02bcc1f3e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/23/2020
ms.locfileid: "92471776"
---
# <a name="tuple-types-c-reference"></a><span data-ttu-id="5572c-103">Типы кортежей (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="5572c-103">Tuple types (C# reference)</span></span>

<span data-ttu-id="5572c-104">*Кортежи* , доступные в C# 7.0 и более поздних версиях, предоставляют краткий синтаксис для группирования нескольких элементов данных в упрощенную структуру данных.</span><span class="sxs-lookup"><span data-stu-id="5572c-104">Available in C# 7.0 and later, the *tuples* feature provides concise syntax to group multiple data elements in a lightweight data structure.</span></span> <span data-ttu-id="5572c-105">В следующем примере показано, как можно объявить переменную кортежа, инициализировать ее и получить доступ к ее элементам данных.</span><span class="sxs-lookup"><span data-stu-id="5572c-105">The following example shows how you can declare a tuple variable, initialize it, and access its data members:</span></span>

[!code-csharp-interactive[tuple intro](snippets/shared/ValueTuples.cs#Introduction)]

<span data-ttu-id="5572c-106">Как показано в предыдущем примере, для определения типа кортежа необходимо указать типы всех его элементов данных и, при необходимости, [имена полей](#tuple-field-names).</span><span class="sxs-lookup"><span data-stu-id="5572c-106">As the preceding example shows, to define a tuple type, you specify types of all its data members and, optionally, the [field names](#tuple-field-names).</span></span> <span data-ttu-id="5572c-107">В типе кортежа невозможно определить методы, но можно использовать методы, предоставляемые .NET, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="5572c-107">You cannot define methods in a tuple type, but you can use the methods provided by .NET, as the following example shows:</span></span>

[!code-csharp-interactive[tuple methods](snippets/shared/ValueTuples.cs#MethodOnTuples)]

<span data-ttu-id="5572c-108">Начиная с C# 7.3, типы кортежей поддерживают [операторы равенства](../operators/equality-operators.md) `==` и `!=`.</span><span class="sxs-lookup"><span data-stu-id="5572c-108">Beginning with C# 7.3, tuple types support [equality operators](../operators/equality-operators.md) `==` and `!=`.</span></span> <span data-ttu-id="5572c-109">Дополнительные сведения см. в разделе [Равенство кортежей](#tuple-equality).</span><span class="sxs-lookup"><span data-stu-id="5572c-109">For more information, see the [Tuple equality](#tuple-equality) section.</span></span>

<span data-ttu-id="5572c-110">Типы кортежей являются [типами значений](value-types.md), а элементы кортежа — общедоступными полями.</span><span class="sxs-lookup"><span data-stu-id="5572c-110">Tuple types are [value types](value-types.md); tuple elements are public fields.</span></span> <span data-ttu-id="5572c-111">Поэтому кортежи представляют собой *изменяемые* типы значений.</span><span class="sxs-lookup"><span data-stu-id="5572c-111">That makes tuples *mutable* value types.</span></span>

> [!NOTE]
> <span data-ttu-id="5572c-112">Для кортежей требуется тип <xref:System.ValueTuple?displayProperty=nameWithType> и связанные универсальные типы (например, <xref:System.ValueTuple%602?displayProperty=nameWithType>), доступные в .NET Core и .NET Framework 4.7 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="5572c-112">The tuples feature requires the <xref:System.ValueTuple?displayProperty=nameWithType> type and related generic types (for example, <xref:System.ValueTuple%602?displayProperty=nameWithType>), which are available in .NET Core and .NET Framework 4.7 and later.</span></span> <span data-ttu-id="5572c-113">Чтобы использовать кортежи в проекте, предназначенном для .NET Framework 4.6.2 или более ранней версии, добавьте в проект пакет NuGet [`System.ValueTuple`](https://www.nuget.org/packages/System.ValueTuple/).</span><span class="sxs-lookup"><span data-stu-id="5572c-113">To use tuples in a project that targets .NET Framework 4.6.2 or earlier, add the NuGet package [`System.ValueTuple`](https://www.nuget.org/packages/System.ValueTuple/) to the project.</span></span>

<span data-ttu-id="5572c-114">Можно определить кортежи со сколь угодно большим числом элементов.</span><span class="sxs-lookup"><span data-stu-id="5572c-114">You can define tuples with an arbitrary large number of elements:</span></span>

[!code-csharp-interactive[large tuple](snippets/shared/ValueTuples.cs#LargeTuple)]

## <a name="use-cases-of-tuples"></a><span data-ttu-id="5572c-115">Варианты использования кортежей</span><span class="sxs-lookup"><span data-stu-id="5572c-115">Use cases of tuples</span></span>

<span data-ttu-id="5572c-116">Чаще всего кортежи используются как возвращаемый методом тип.</span><span class="sxs-lookup"><span data-stu-id="5572c-116">One of the most common use cases of tuples is as a method return type.</span></span> <span data-ttu-id="5572c-117">То есть вместо определения [параметров метода `out`](../keywords/out-parameter-modifier.md) можно сгруппировать результаты метода в возвращаемый тип кортежа, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="5572c-117">That is, instead of defining [`out` method parameters](../keywords/out-parameter-modifier.md), you can group method results in a tuple return type, as the following example shows:</span></span>

[!code-csharp-interactive[multiple method outputs](snippets/shared/ValueTuples.cs#MultipleReturns)]

<span data-ttu-id="5572c-118">Как показано в предыдущем примере, с возвращаемым экземпляром кортежа можно работать напрямую или [деконструировать](#tuple-assignment-and-deconstruction) его в отдельные переменные.</span><span class="sxs-lookup"><span data-stu-id="5572c-118">As the preceding example shows, you can work with the returned tuple instance directly or [deconstruct](#tuple-assignment-and-deconstruction) it in separate variables.</span></span>

<span data-ttu-id="5572c-119">Типы кортежей можно также использовать вместо [анонимных типов](../../programming-guide/classes-and-structs/anonymous-types.md), например в запросах LINQ.</span><span class="sxs-lookup"><span data-stu-id="5572c-119">You can also use tuple types instead of [anonymous types](../../programming-guide/classes-and-structs/anonymous-types.md); for example, in LINQ queries.</span></span> <span data-ttu-id="5572c-120">Дополнительные сведения см. в статье [Выбор между анонимными типами и кортежами](../../../standard/base-types/choosing-between-anonymous-and-tuple.md).</span><span class="sxs-lookup"><span data-stu-id="5572c-120">For more information, see [Choosing between anonymous and tuple types](../../../standard/base-types/choosing-between-anonymous-and-tuple.md).</span></span>

<span data-ttu-id="5572c-121">Как правило, кортежи используются для группирования слабо связанных элементов данных.</span><span class="sxs-lookup"><span data-stu-id="5572c-121">Typically, you use tuples to group loosely related data elements.</span></span> <span data-ttu-id="5572c-122">Это целесообразно в закрытых и внутренних служебных методах.</span><span class="sxs-lookup"><span data-stu-id="5572c-122">That is usually useful within private and internal utility methods.</span></span> <span data-ttu-id="5572c-123">При работе с общедоступным API рассмотрите возможность определения типа [класса](../keywords/class.md) или [структуры](struct.md).</span><span class="sxs-lookup"><span data-stu-id="5572c-123">In the case of public API, consider defining a [class](../keywords/class.md) or a [structure](struct.md) type.</span></span>

## <a name="tuple-field-names"></a><span data-ttu-id="5572c-124">Имена полей кортежей</span><span class="sxs-lookup"><span data-stu-id="5572c-124">Tuple field names</span></span>

<span data-ttu-id="5572c-125">Имена полей кортежей указываются явным образом либо в выражении инициализации кортежа, либо в определении типа кортежа, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="5572c-125">You can explicitly specify the names of tuple fields either in a tuple initialization expression or in the definition of a tuple type, as the following example shows:</span></span>

[!code-csharp-interactive[explicit field names](snippets/shared/ValueTuples.cs#ExplicitFieldNames)]

<span data-ttu-id="5572c-126">Начиная с C# 7.1, если имя поля не указано, оно может быть выведено из имени соответствующей переменной в выражении инициализации кортежа, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="5572c-126">Beginning with C# 7.1, if you don't specify a field name, it may be inferred from the name of the corresponding variable in a tuple initialization expression, as the following example shows:</span></span>

[!code-csharp-interactive[inferred field names](snippets/shared/ValueTuples.cs#InferFieldNames)]

<span data-ttu-id="5572c-127">Это называется инициализаторами проекций кортежа.</span><span class="sxs-lookup"><span data-stu-id="5572c-127">That's known as tuple projection initializers.</span></span> <span data-ttu-id="5572c-128">Имя переменной не проецируется на имя поля кортежа в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="5572c-128">The name of a variable isn't projected onto a tuple field name in the following cases:</span></span>

- <span data-ttu-id="5572c-129">Имя кандидата — это имя элемента типа кортежа, например `Item3`, `ToString`или `Rest`.</span><span class="sxs-lookup"><span data-stu-id="5572c-129">The candidate name is a member name of a tuple type, for example, `Item3`, `ToString`, or `Rest`.</span></span>
- <span data-ttu-id="5572c-130">Имя кандидата является дубликатом другого имени поля кортежа, явного или неявного.</span><span class="sxs-lookup"><span data-stu-id="5572c-130">The candidate name is a duplicate of another tuple field name, either explicit or implicit.</span></span>

<span data-ttu-id="5572c-131">В этих случаях необходимо либо явно указать имя поля, либо получить доступ к полю по имени по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5572c-131">In those cases you either explicitly specify the name of a field or access a field by its default name.</span></span>

<span data-ttu-id="5572c-132">По умолчанию поля кортежа имеют имена `Item1`, `Item2`, `Item3` и т. д.</span><span class="sxs-lookup"><span data-stu-id="5572c-132">The default names of tuple fields are `Item1`, `Item2`, `Item3` and so on.</span></span> <span data-ttu-id="5572c-133">Всегда можно использовать имя поля по умолчанию, даже если имя поля указано явно или является выводимым, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="5572c-133">You can always use the default name of a field, even when a field name is specified explicitly or inferred, as the following example shows:</span></span>

[!code-csharp-interactive[default field names](snippets/shared/ValueTuples.cs#DefaultFieldNames)]

<span data-ttu-id="5572c-134">Имена полей не учитываются при [присваивании кортежа](#tuple-assignment-and-deconstruction) и [сравнении кортежей на равенство](#tuple-equality).</span><span class="sxs-lookup"><span data-stu-id="5572c-134">[Tuple assignment](#tuple-assignment-and-deconstruction) and [tuple equality comparisons](#tuple-equality) don't take field names into account.</span></span>

<span data-ttu-id="5572c-135">Во время компиляции компилятор заменяет имена полей не по умолчанию соответствующими именами по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5572c-135">At compile time, the compiler replaces non-default field names with the corresponding default names.</span></span> <span data-ttu-id="5572c-136">В результате явно указанные или выводимые имена полей будут недоступны во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="5572c-136">As a result, explicitly specified or inferred field names aren't available at run time.</span></span>

## <a name="tuple-assignment-and-deconstruction"></a><span data-ttu-id="5572c-137">Присваивание и деконструкция кортежей</span><span class="sxs-lookup"><span data-stu-id="5572c-137">Tuple assignment and deconstruction</span></span>

<span data-ttu-id="5572c-138">В C# поддерживается присваивание между типами кортежей, которые соответствуют обоим следующим условиям:</span><span class="sxs-lookup"><span data-stu-id="5572c-138">C# supports assignment between tuple types that satisfy both of the following conditions:</span></span>

- <span data-ttu-id="5572c-139">оба типа кортежей должны содержать одинаковое количество элементов;</span><span class="sxs-lookup"><span data-stu-id="5572c-139">both tuple types have the same number of elements</span></span>
- <span data-ttu-id="5572c-140">для каждой позиции кортежа тип правого элемента кортежа аналогичен типу соответствующего левого элемента кортежа или может быть неявно преобразован в этот тип.</span><span class="sxs-lookup"><span data-stu-id="5572c-140">for each tuple position, the type of the right-hand tuple element is the same as or implicitly convertible to the type of the corresponding left-hand tuple element</span></span>

<span data-ttu-id="5572c-141">Значения элементов кортежа присваиваются в порядке расположения элементов кортежа.</span><span class="sxs-lookup"><span data-stu-id="5572c-141">Tuple element values are assigned following the order of tuple elements.</span></span> <span data-ttu-id="5572c-142">Имена полей кортежа не учитываются и не присваиваются, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="5572c-142">The names of tuple fields are ignored and not assigned, as the following example shows:</span></span>

[!code-csharp-interactive[tuple assignment](snippets/shared/ValueTuples.cs#Assignment)]

<span data-ttu-id="5572c-143">Оператор присваивания `=` можно также использовать для *деконструкции* экземпляра кортежа в отдельные переменные.</span><span class="sxs-lookup"><span data-stu-id="5572c-143">You can also use the assignment operator `=` to *deconstruct* a tuple instance in separate variables.</span></span> <span data-ttu-id="5572c-144">Существует три способа деконструкции кортежа.</span><span class="sxs-lookup"><span data-stu-id="5572c-144">You can do that in one of the following ways:</span></span>

- <span data-ttu-id="5572c-145">Вы можете явно объявить тип каждой переменной в скобках.</span><span class="sxs-lookup"><span data-stu-id="5572c-145">Explicitly declare the type of each variable inside parentheses:</span></span>

  [!code-csharp-interactive[specify types of variables](snippets/shared/ValueTuples.cs#DeconstructExplicit)]

- <span data-ttu-id="5572c-146">Вы можете использовать ключевое слово `var` за пределами круглых скобок, чтобы объявить неявно типизированные переменные и позволить компилятору вывести их типы.</span><span class="sxs-lookup"><span data-stu-id="5572c-146">Use the `var` keyword outside the parentheses to declare implicitly typed variables and let the compiler infer their types:</span></span>

  [!code-csharp-interactive[implicitly typed variables](snippets/shared/ValueTuples.cs#DeconstructVar)]

- <span data-ttu-id="5572c-147">Вы можете использовать существующие переменные.</span><span class="sxs-lookup"><span data-stu-id="5572c-147">Use existing variables:</span></span>

  [!code-csharp-interactive[existing variables](snippets/shared/ValueTuples.cs#DeconstructExisting)]

<span data-ttu-id="5572c-148">Подробнее о деконструкции кортежей с помощью и других типов см. в статье [Деконструкция кортежей и других типов](../../deconstruct.md).</span><span class="sxs-lookup"><span data-stu-id="5572c-148">For more information about deconstruction of tuples and other types, see [Deconstructing tuples and other types](../../deconstruct.md).</span></span>

## <a name="tuple-equality"></a><span data-ttu-id="5572c-149">Равенство кортежей</span><span class="sxs-lookup"><span data-stu-id="5572c-149">Tuple equality</span></span>

<span data-ttu-id="5572c-150">Начиная с C# 7.3, типы кортежей поддерживают операторы `==` и `!=`.</span><span class="sxs-lookup"><span data-stu-id="5572c-150">Beginning with C# 7.3, tuple types support the `==` and `!=` operators.</span></span> <span data-ttu-id="5572c-151">Эти операторы сравнивают элементы левого операнда с соответствующими элементами правого операнда в соответствии с порядком расположения элементов кортежа.</span><span class="sxs-lookup"><span data-stu-id="5572c-151">These operators compare members of the left-hand operand with the corresponding members of the right-hand operand following the order of tuple elements.</span></span>

[!code-csharp-interactive[tuple equality](snippets/shared/ValueTuples.cs#TupleEquality)]

<span data-ttu-id="5572c-152">Как показано в предыдущем примере, в операциях `==` и `!=` не учитываются имена полей кортежей.</span><span class="sxs-lookup"><span data-stu-id="5572c-152">As the preceding example shows, the `==` and `!=` operations don't take into account tuple field names.</span></span>

<span data-ttu-id="5572c-153">Два кортежа сравнимы, если выполнены оба следующих условия:</span><span class="sxs-lookup"><span data-stu-id="5572c-153">Two tuples are comparable when both of the following conditions are satisfied:</span></span>

- <span data-ttu-id="5572c-154">оба кортежа содержат одинаковое количество элементов.</span><span class="sxs-lookup"><span data-stu-id="5572c-154">Both tuples have the same number of elements.</span></span> <span data-ttu-id="5572c-155">Например, `t1 != t2` не компилируется, если `t1` и `t2` имеют разное количество элементов.</span><span class="sxs-lookup"><span data-stu-id="5572c-155">For example, `t1 != t2` doesn't compile if `t1` and `t2` have different numbers of elements.</span></span>
- <span data-ttu-id="5572c-156">Для каждой позиции кортежа соответствующие элементы из левого и правого операндов кортежа сравниваются с помощью операторов `==` и `!=`.</span><span class="sxs-lookup"><span data-stu-id="5572c-156">For each tuple position, the corresponding elements from the left-hand and right-hand tuple operands are comparable with the `==` and `!=` operators.</span></span> <span data-ttu-id="5572c-157">Например, `(1, (2, 3)) == ((1, 2), 3)` не компилируется, поскольку `1` не сравнивается с помощью `(1, 2)`.</span><span class="sxs-lookup"><span data-stu-id="5572c-157">For example, `(1, (2, 3)) == ((1, 2), 3)` doesn't compile because `1` is not comparable with `(1, 2)`.</span></span>

<span data-ttu-id="5572c-158">Операторы `==` и `!=` сравнивают кортежи с сокращенной обработкой.</span><span class="sxs-lookup"><span data-stu-id="5572c-158">The `==` and `!=` operators compare tuples in short-circuiting way.</span></span> <span data-ttu-id="5572c-159">Это значит, что операция останавливается, как только она соответствует паре неравных элементов или достигает конца кортежей.</span><span class="sxs-lookup"><span data-stu-id="5572c-159">That is, an operation stops as soon as it meets a pair of non equal elements or reaches the ends of tuples.</span></span> <span data-ttu-id="5572c-160">Однако перед любым сравнением *все* элементы кортежа вычисляются, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="5572c-160">However, before any comparison, *all* tuple elements are evaluated, as the following example shows:</span></span>

[!code-csharp-interactive[tuple element evaluation](snippets/shared/ValueTuples.cs#TupleEvaluationForEquality)]

## <a name="tuples-as-out-parameters"></a><span data-ttu-id="5572c-161">Кортежи как параметры вывода</span><span class="sxs-lookup"><span data-stu-id="5572c-161">Tuples as out parameters</span></span>

<span data-ttu-id="5572c-162">Как правило, вы выполняете рефакторинг метода, имеющего [параметры `out`](../keywords/out-parameter-modifier.md), в метод, возвращающий кортеж.</span><span class="sxs-lookup"><span data-stu-id="5572c-162">Typically, you refactor a method that has [`out` parameters](../keywords/out-parameter-modifier.md) into a method that returns a tuple.</span></span> <span data-ttu-id="5572c-163">Однако бывают случаи, когда параметр `out` может иметь тип кортежа.</span><span class="sxs-lookup"><span data-stu-id="5572c-163">However, there are cases in which an `out` parameter can be of a tuple type.</span></span> <span data-ttu-id="5572c-164">В следующем примере показано, как работать с кортежами в виде параметров `out`.</span><span class="sxs-lookup"><span data-stu-id="5572c-164">The following example shows how to work with tuples as `out` parameters:</span></span>

[!code-csharp-interactive[tuple as out parameter](snippets/shared/ValueTuples.cs#TupleAsOutParameter)]

## <a name="tuples-vs-systemtuple"></a><span data-ttu-id="5572c-165">Кортежи и `System.Tuple`</span><span class="sxs-lookup"><span data-stu-id="5572c-165">Tuples vs `System.Tuple`</span></span>

<span data-ttu-id="5572c-166">Кортежи C# с типами <xref:System.ValueTuple?displayProperty=nameWithType>, отличаются от кортежей, представленных типами <xref:System.Tuple?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="5572c-166">C# tuples, which are backed by <xref:System.ValueTuple?displayProperty=nameWithType> types, are different from tuples that are represented by <xref:System.Tuple?displayProperty=nameWithType> types.</span></span> <span data-ttu-id="5572c-167">Основные различия заключаются в следующем.</span><span class="sxs-lookup"><span data-stu-id="5572c-167">The main differences are as follows:</span></span>

- <span data-ttu-id="5572c-168">Типы `ValueTuple` являются [типами значений](value-types.md).</span><span class="sxs-lookup"><span data-stu-id="5572c-168">`ValueTuple` types are [value types](value-types.md).</span></span> <span data-ttu-id="5572c-169">Типы `Tuple` являются [ссылочными типами](../keywords/reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="5572c-169">`Tuple` types are [reference types](../keywords/reference-types.md).</span></span>
- <span data-ttu-id="5572c-170">Типы `ValueTuple` являются изменяемыми.</span><span class="sxs-lookup"><span data-stu-id="5572c-170">`ValueTuple` types are mutable.</span></span> <span data-ttu-id="5572c-171">Типы `Tuple` являются неизменяемыми.</span><span class="sxs-lookup"><span data-stu-id="5572c-171">`Tuple` types are immutable.</span></span>
- <span data-ttu-id="5572c-172">Элементами данных типов `ValueTuple` являются поля.</span><span class="sxs-lookup"><span data-stu-id="5572c-172">Data members of `ValueTuple` types are fields.</span></span> <span data-ttu-id="5572c-173">Элементами данных типов `Tuple` являются свойства.</span><span class="sxs-lookup"><span data-stu-id="5572c-173">Data members of `Tuple` types are properties.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="5572c-174">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="5572c-174">C# language specification</span></span>

<span data-ttu-id="5572c-175">Дополнительные сведения см. в следующих примечаниях к предлагаемой функции.</span><span class="sxs-lookup"><span data-stu-id="5572c-175">For more information, see the following feature proposal notes:</span></span>

- [<span data-ttu-id="5572c-176">Выводимые имена кортежей (инициализаторы проекций кортежа)</span><span class="sxs-lookup"><span data-stu-id="5572c-176">Infer tuple names (aka. tuple projection initializers)</span></span>](~/_csharplang/proposals/csharp-7.1/infer-tuple-names.md)
- [<span data-ttu-id="5572c-177">Поддержка `==` и `!=` для типов кортежей</span><span class="sxs-lookup"><span data-stu-id="5572c-177">Support for `==` and `!=` on tuple types</span></span>](~/_csharplang/proposals/csharp-7.3/tuple-equality.md)

## <a name="see-also"></a><span data-ttu-id="5572c-178">См. также</span><span class="sxs-lookup"><span data-stu-id="5572c-178">See also</span></span>

- [<span data-ttu-id="5572c-179">справочник по C#</span><span class="sxs-lookup"><span data-stu-id="5572c-179">C# reference</span></span>](../index.md)
- [<span data-ttu-id="5572c-180">Типы значений</span><span class="sxs-lookup"><span data-stu-id="5572c-180">Value types</span></span>](value-types.md)
- [<span data-ttu-id="5572c-181">Выбор между анонимными типами и кортежами</span><span class="sxs-lookup"><span data-stu-id="5572c-181">Choosing between anonymous and tuple types</span></span>](../../../standard/base-types/choosing-between-anonymous-and-tuple.md)
- <xref:System.ValueTuple?displayProperty=nameWithType>
