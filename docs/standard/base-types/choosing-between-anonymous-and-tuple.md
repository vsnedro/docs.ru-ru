---
title: Выбор между анонимными типами и кортежами
description: Сведения о том, как сделать выбор между анонимными типами и кортежами.
author: IEvangelist
ms.author: dapine
ms.date: 07/01/2020
ms.openlocfilehash: f8465b2f22ecfafd739355ddd35635e2eee49232
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/18/2020
ms.locfileid: "94823203"
---
# <a name="choosing-between-anonymous-and-tuple-types"></a><span data-ttu-id="0fddc-103">Выбор между анонимными типами и кортежами</span><span class="sxs-lookup"><span data-stu-id="0fddc-103">Choosing between anonymous and tuple types</span></span>

<span data-ttu-id="0fddc-104">При выборе подходящего типа необходимо учитывать его применимость, производительность и недостатки по сравнению с другими типами.</span><span class="sxs-lookup"><span data-stu-id="0fddc-104">Choosing the appropriate type involves considering its usability, performance, and tradeoffs compared to other types.</span></span> <span data-ttu-id="0fddc-105">Анонимные типы были представлены в C# 3.0, а универсальные типы <xref:System.Tuple%602?displayProperty=nameWithType> — в .NET Framework 4.0.</span><span class="sxs-lookup"><span data-stu-id="0fddc-105">Anonymous types have been available since C# 3.0, while generic <xref:System.Tuple%602?displayProperty=nameWithType> types were introduced with .NET Framework 4.0.</span></span> <span data-ttu-id="0fddc-106">После этого появились новые поддерживаемые на уровне языка параметры, например <xref:System.ValueTuple%602?displayProperty=nameWithType>, который, как следует из его имени, реализует тип значения, обладающий универсальностью анонимного типа.</span><span class="sxs-lookup"><span data-stu-id="0fddc-106">Since then new options have been introduced with language level support, such as <xref:System.ValueTuple%602?displayProperty=nameWithType> - which as the name implies, provide a value type with the flexibility of anonymous types.</span></span> <span data-ttu-id="0fddc-107">В этой статье мы расскажем о том, в каких случаях следует выбирать тот или иной тип.</span><span class="sxs-lookup"><span data-stu-id="0fddc-107">In this article, you'll learn when it's appropriate to choose one type over the other.</span></span>

## <a name="usability-and-functionality"></a><span data-ttu-id="0fddc-108">Применимость и функциональность</span><span class="sxs-lookup"><span data-stu-id="0fddc-108">Usability and functionality</span></span>

<span data-ttu-id="0fddc-109">Анонимные типы были представлены в C# 3.0 вместе с выражениями LINQ.</span><span class="sxs-lookup"><span data-stu-id="0fddc-109">Anonymous types were introduced in C# 3.0 with Language-Integrated Query (LINQ) expressions.</span></span> <span data-ttu-id="0fddc-110">С помощью LINQ разработчики часто проецируют результаты запросов в анонимные типы, содержащие некоторые из свойств объектов, с которыми они работают.</span><span class="sxs-lookup"><span data-stu-id="0fddc-110">With LINQ, developers often project results from queries into anonymous types that hold a few select properties from the objects they're working with.</span></span> <span data-ttu-id="0fddc-111">Рассмотрим следующий пример, где создается экземпляр массива объектов <xref:System.DateTime>, которые посредством итераций проецируются в анонимный тип с двумя свойствами.</span><span class="sxs-lookup"><span data-stu-id="0fddc-111">Consider the following example, that instantiates an array of <xref:System.DateTime> objects, and iterates through them projecting into an anonymous type with two properties.</span></span>

```csharp-interactive
var dates = new[]
{
    DateTime.UtcNow.AddHours(-1),
    DateTime.UtcNow,
    DateTime.UtcNow.AddHours(1),
};

foreach (var anonymous in
             dates.Select(
                 date => new { Formatted = $"{date:MMM dd, yyyy hh:mm zzz}", date.Ticks }))
{
    Console.WriteLine($"Ticks: {anonymous.Ticks}, formatted: {anonymous.Formatted}");
}
```

<span data-ttu-id="0fddc-112">Экземпляры анонимных типов создаются с помощью оператора [`new`](../../csharp/language-reference/operators/new-operator.md), а имена свойств и типы при этом выводятся из объявления.</span><span class="sxs-lookup"><span data-stu-id="0fddc-112">Anonymous types are instantiated by using the [`new`](../../csharp/language-reference/operators/new-operator.md) operator, and the property names and types are inferred from the declaration.</span></span> <span data-ttu-id="0fddc-113">Если несколько инициализаторов анонимных объектов в одной сборке указывают на последовательность свойств, идущих в том же порядке и имеющих те же типы и имена, компилятор обрабатывает объекты как экземпляры одного типа.</span><span class="sxs-lookup"><span data-stu-id="0fddc-113">If two or more anonymous object initializers in the same assembly specify a sequence of properties that are in the same order and that have the same names and types, the compiler treats the objects as instances of the same type.</span></span> <span data-ttu-id="0fddc-114">Они используют одни и те же сведения типа, созданные компилятором.</span><span class="sxs-lookup"><span data-stu-id="0fddc-114">They share the same compiler-generated type information.</span></span>

<span data-ttu-id="0fddc-115">В приведенном выше фрагменте кода C# выполняется проецирование в анонимный тип с двумя свойствами, что во многом аналогично создаваемому компилятором классу C#:</span><span class="sxs-lookup"><span data-stu-id="0fddc-115">The previous C# snippet projects an anonymous type with two properties, much like the following compiler-generated C# class:</span></span>

```csharp
internal sealed class f__AnonymousType0
{
    public string Formatted { get; }
    public long Ticks { get; }

    public f__AnonymousType0(string formatted, long ticks)
    {
        Formatted = formatted;
        Ticks = ticks;
    }
}
```

<span data-ttu-id="0fddc-116">Дополнительные сведения см. в статье [Анонимные типы](../../csharp/programming-guide/classes-and-structs/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="0fddc-116">For more information, see [anonymous types](../../csharp/programming-guide/classes-and-structs/anonymous-types.md).</span></span> <span data-ttu-id="0fddc-117">Аналогичная ситуация складывается с кортежами: при проецировании в запросы LINQ вы можете выбирать свойства для кортежа.</span><span class="sxs-lookup"><span data-stu-id="0fddc-117">The same functionality exists with tuples when projecting into LINQ queries, you can select properties into tuples.</span></span> <span data-ttu-id="0fddc-118">Такие кортежи обрабатываются в рамках запроса так же, как и анонимные типы.</span><span class="sxs-lookup"><span data-stu-id="0fddc-118">These tuples flow through the query, just as anonymous types would.</span></span> <span data-ttu-id="0fddc-119">Рассмотрим следующий пример, в котором используется `System.Tuple<string, long>`.</span><span class="sxs-lookup"><span data-stu-id="0fddc-119">Now consider the following example using the `System.Tuple<string, long>`.</span></span>

```csharp-interactive
var dates = new[]
{
    DateTime.UtcNow.AddHours(-1),
    DateTime.UtcNow,
    DateTime.UtcNow.AddHours(1),
};

foreach (var tuple in
            dates.Select(
                date => new Tuple<string, long>($"{date:MMM dd, yyyy hh:mm zzz}", date.Ticks)))
{
    Console.WriteLine($"Ticks: {tuple.Item2}, formatted: {tuple.Item1}");
}
```

<span data-ttu-id="0fddc-120">С помощью <xref:System.Tuple%602?displayProperty=nameWithType> экземпляр предоставляет свойства нумерованного элемента, такие как `Item1` и `Item2`.</span><span class="sxs-lookup"><span data-stu-id="0fddc-120">With the <xref:System.Tuple%602?displayProperty=nameWithType>, the instance exposes numbered item properties, such as `Item1`, and `Item2`.</span></span> <span data-ttu-id="0fddc-121">При использовании таких имен свойств, которые содержат только порядковые номера, сложно понять предназначение их значений.</span><span class="sxs-lookup"><span data-stu-id="0fddc-121">These property names can make it more difficult to understand the intent of the property values, as the property name only provides the ordinal.</span></span> <span data-ttu-id="0fddc-122">Кроме того, типы `System.Tuple` являются ссылочными типами `class`.</span><span class="sxs-lookup"><span data-stu-id="0fddc-122">Furthermore, the `System.Tuple` types are reference `class` types.</span></span> <span data-ttu-id="0fddc-123">Тем не менее, <xref:System.ValueTuple%602?displayProperty=nameWithType> является типом значения `struct`.</span><span class="sxs-lookup"><span data-stu-id="0fddc-123">The <xref:System.ValueTuple%602?displayProperty=nameWithType> however, is a value `struct` type.</span></span> <span data-ttu-id="0fddc-124">В следующем фрагменте кода C# выполняется проецирование в `ValueTuple<string, long>`.</span><span class="sxs-lookup"><span data-stu-id="0fddc-124">The following C# snippet, uses `ValueTuple<string, long>` to project into.</span></span> <span data-ttu-id="0fddc-125">При этом назначение осуществляется с использованием литерального синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="0fddc-125">In doing so, it assigns using a literal syntax.</span></span>

```csharp-interactive
var dates = new[]
{
    DateTime.UtcNow.AddHours(-1),
    DateTime.UtcNow,
    DateTime.UtcNow.AddHours(1),
};

foreach (var (formatted, ticks) in
            dates.Select(
                date => (Formatted: $"{date:MMM dd, yyyy at hh:mm zzz}", date.Ticks)))
{
    Console.WriteLine($"Ticks: {ticks}, formatted: {formatted}");
}
```

<span data-ttu-id="0fddc-126">Дополнительные сведения о кортежах см. в статьях [Типы кортежей (справочник по C#)](../../csharp/language-reference/builtin-types/value-tuples.md) или [Кортежи (Visual Basic)](../../visual-basic/programming-guide/language-features/data-types/tuples.md).</span><span class="sxs-lookup"><span data-stu-id="0fddc-126">For more information about tuples, see [Tuple types (C# reference)](../../csharp/language-reference/builtin-types/value-tuples.md) or [Tuples (Visual Basic)](../../visual-basic/programming-guide/language-features/data-types/tuples.md).</span></span>

<span data-ttu-id="0fddc-127">И все же приведенные выше примеры эквивалентны с функциональной точки зрения и незначительно различаются в контексте применимости и базовой реализации.</span><span class="sxs-lookup"><span data-stu-id="0fddc-127">The previous examples are all functionally equivalent, however; there are slight differences in their usability and their underlying implementations.</span></span>

## <a name="tradeoffs"></a><span data-ttu-id="0fddc-128">Компромиссы</span><span class="sxs-lookup"><span data-stu-id="0fddc-128">Tradeoffs</span></span>

<span data-ttu-id="0fddc-129">Вы можете во всех случаях использовать <xref:System.ValueTuple> вместо <xref:System.Tuple> и анонимные типы, однако при этом необходимо учитывать свойственные им недостатки.</span><span class="sxs-lookup"><span data-stu-id="0fddc-129">You might want to always use <xref:System.ValueTuple> over <xref:System.Tuple>, and anonymous types, but there are tradeoffs you should consider.</span></span> <span data-ttu-id="0fddc-130">Типы <xref:System.ValueTuple> являются изменяемыми, тогда как типы <xref:System.Tuple> доступны только для чтения.</span><span class="sxs-lookup"><span data-stu-id="0fddc-130">The <xref:System.ValueTuple> types are mutable, whereas <xref:System.Tuple> are read-only.</span></span> <span data-ttu-id="0fddc-131">В отличие от кортежей, анонимные типы можно использовать в деревьях выражений.</span><span class="sxs-lookup"><span data-stu-id="0fddc-131">Anonymous types can be used in expression trees, while tuples cannot.</span></span> <span data-ttu-id="0fddc-132">В следующей таблице представлен обзор некоторых основных различий между ними.</span><span class="sxs-lookup"><span data-stu-id="0fddc-132">The following table is an overview of some of the key differences.</span></span>

### <a name="key-differences"></a><span data-ttu-id="0fddc-133">Основные отличия</span><span class="sxs-lookup"><span data-stu-id="0fddc-133">Key differences</span></span>

| <span data-ttu-id="0fddc-134">name</span><span class="sxs-lookup"><span data-stu-id="0fddc-134">Name</span></span>                     | <span data-ttu-id="0fddc-135">Модификатор доступа</span><span class="sxs-lookup"><span data-stu-id="0fddc-135">Access modifier</span></span> | <span data-ttu-id="0fddc-136">Type</span><span class="sxs-lookup"><span data-stu-id="0fddc-136">Type</span></span>     | <span data-ttu-id="0fddc-137">Имя пользовательского элемента</span><span class="sxs-lookup"><span data-stu-id="0fddc-137">Custom member name</span></span> | <span data-ttu-id="0fddc-138">Поддержка деконструирования</span><span class="sxs-lookup"><span data-stu-id="0fddc-138">Deconstruction support</span></span> | <span data-ttu-id="0fddc-139">Поддержка деревьев выражений</span><span class="sxs-lookup"><span data-stu-id="0fddc-139">Expression tree support</span></span> |
|--------------------------|-----------------|----------|----------------------|------------------------|-------------------------|
| <span data-ttu-id="0fddc-140">Анонимные типы</span><span class="sxs-lookup"><span data-stu-id="0fddc-140">Anonymous types</span></span>          | `internal`      | `class`  | <span data-ttu-id="0fddc-141">✔️</span><span class="sxs-lookup"><span data-stu-id="0fddc-141">✔️</span></span>                   | ❌                     | <span data-ttu-id="0fddc-142">✔️</span><span class="sxs-lookup"><span data-stu-id="0fddc-142">✔️</span></span>                     |
| <xref:System.Tuple>      | `public`        | `class`  | ❌                   | ❌                     | <span data-ttu-id="0fddc-143">✔️</span><span class="sxs-lookup"><span data-stu-id="0fddc-143">✔️</span></span>                     |
| <xref:System.ValueTuple> | `public`        | `struct` | <span data-ttu-id="0fddc-144">✔️</span><span class="sxs-lookup"><span data-stu-id="0fddc-144">✔️</span></span>                   | <span data-ttu-id="0fddc-145">✔️</span><span class="sxs-lookup"><span data-stu-id="0fddc-145">✔️</span></span>                     | ❌                     |

### <a name="serialization"></a><span data-ttu-id="0fddc-146">Сериализация</span><span class="sxs-lookup"><span data-stu-id="0fddc-146">Serialization</span></span>

<span data-ttu-id="0fddc-147">При выборе типа важно учитывать необходимость в его сериализации.</span><span class="sxs-lookup"><span data-stu-id="0fddc-147">One important consideration when choosing a type, is whether or not it will need to be serialized.</span></span> <span data-ttu-id="0fddc-148">Сериализация представляет собой процесс преобразования состояния объекта в форму, пригодную для сохранения или передачи.</span><span class="sxs-lookup"><span data-stu-id="0fddc-148">Serialization is the process of converting the state of an object into a form that can be persisted or transported.</span></span> <span data-ttu-id="0fddc-149">Дополнительные сведения см. в статье [Сериализация](../../csharp/programming-guide/concepts/serialization/index.md).</span><span class="sxs-lookup"><span data-stu-id="0fddc-149">For more information, see [serialization](../../csharp/programming-guide/concepts/serialization/index.md).</span></span> <span data-ttu-id="0fddc-150">Если сериализация нужна, вместо анонимных типов или кортежей рекомендуется создавать `class` или `struct`.</span><span class="sxs-lookup"><span data-stu-id="0fddc-150">When serialization is important, creating a `class` or `struct` is preferred over anonymous types or tuple types.</span></span>

## <a name="performance"></a><span data-ttu-id="0fddc-151">Производительность</span><span class="sxs-lookup"><span data-stu-id="0fddc-151">Performance</span></span>

<span data-ttu-id="0fddc-152">Различия в производительности между этими типами зависят от сценария их применения.</span><span class="sxs-lookup"><span data-stu-id="0fddc-152">Performance between these types depends on the scenario.</span></span> <span data-ttu-id="0fddc-153">Основным фактором, влияющим на производительность, является достижение компромисса между возможностями выделения памяти и копирования.</span><span class="sxs-lookup"><span data-stu-id="0fddc-153">The major impact involves the tradeoff between allocations and copying.</span></span> <span data-ttu-id="0fddc-154">В большинстве случаев это влияние незначительно.</span><span class="sxs-lookup"><span data-stu-id="0fddc-154">In most scenarios, the impact is small.</span></span> <span data-ttu-id="0fddc-155">Тем не менее, если возникают проблемы, следует выполнить измерения, по результатам которых будет приниматься взвешенное решение.</span><span class="sxs-lookup"><span data-stu-id="0fddc-155">When major impacts could arise, measurements should be taken to inform the decision.</span></span>

## <a name="conclusion"></a><span data-ttu-id="0fddc-156">Заключение</span><span class="sxs-lookup"><span data-stu-id="0fddc-156">Conclusion</span></span>

<span data-ttu-id="0fddc-157">При выборе между анонимными типами и кортежами разработчику необходимо учитывать ряд факторов.</span><span class="sxs-lookup"><span data-stu-id="0fddc-157">As a developer choosing between tuples and anonymous types, there are several factors to consider.</span></span> <span data-ttu-id="0fddc-158">В общем случае, если вы не работаете с [деревьями выражений](../../csharp/expression-trees.md) и хорошо знакомы с синтаксисом кортежей, мы рекомендуем выбирать типы <xref:System.ValueTuple>, которые предоставляют тип значений с возможностью именования свойств.</span><span class="sxs-lookup"><span data-stu-id="0fddc-158">Generally speaking, if you're not working with [expression trees](../../csharp/expression-trees.md), and you're comfortable with tuple syntax then choose <xref:System.ValueTuple> as they provide a value type with the flexibility to name properties.</span></span> <span data-ttu-id="0fddc-159">Если вы работаете с деревьями выражений и предпочитаете именованные свойства, следует выбирать анонимные типы.</span><span class="sxs-lookup"><span data-stu-id="0fddc-159">If you're working with expression trees, and you'd prefer to name properties, choose anonymous types.</span></span> <span data-ttu-id="0fddc-160">В противном случае используйте коллекцию <xref:System.Tuple>.</span><span class="sxs-lookup"><span data-stu-id="0fddc-160">Otherwise, use <xref:System.Tuple>.</span></span>

## <a name="see-also"></a><span data-ttu-id="0fddc-161">См. также</span><span class="sxs-lookup"><span data-stu-id="0fddc-161">See also</span></span>

- [<span data-ttu-id="0fddc-162">Анонимные типы</span><span class="sxs-lookup"><span data-stu-id="0fddc-162">Anonymous types</span></span>](../../csharp/programming-guide/classes-and-structs/anonymous-types.md)
- [<span data-ttu-id="0fddc-163">Деревья выражений</span><span class="sxs-lookup"><span data-stu-id="0fddc-163">Expression trees</span></span>](../../csharp/expression-trees.md)
- [<span data-ttu-id="0fddc-164">Типы кортежей (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="0fddc-164">Tuple types (C# reference)</span></span>](../../csharp/language-reference/builtin-types/value-tuples.md)
- [<span data-ttu-id="0fddc-165">Кортежи (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0fddc-165">Tuples (Visual Basic)</span></span>](../../visual-basic/programming-guide/language-features/data-types/tuples.md)
- [<span data-ttu-id="0fddc-166">Правила разработки типов</span><span class="sxs-lookup"><span data-stu-id="0fddc-166">Type design guidelines</span></span>](../design-guidelines/type.md)
