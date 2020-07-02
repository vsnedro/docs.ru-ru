---
title: Выбор между анонимными и типами кортежей
description: Узнайте, когда нужно выбрать между анонимными типами и типом кортежа.
ms.date: 06/29/2020
ms.technology: dotnet-standard
ms.openlocfilehash: bc17695830a42a6eed9d60c0e097ee9d02a7957e
ms.sourcegitcommit: c23d9666ec75b91741da43ee3d91c317d68c7327
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85803772"
---
# <a name="choosing-between-anonymous-and-tuple-types"></a><span data-ttu-id="d1dae-103">Выбор между анонимными и типами кортежей</span><span class="sxs-lookup"><span data-stu-id="d1dae-103">Choosing between anonymous and tuple types</span></span>

<span data-ttu-id="d1dae-104">Выбор подходящего типа предполагает возможность использования, производительности и компромиссов по сравнению с другими типами.</span><span class="sxs-lookup"><span data-stu-id="d1dae-104">Choosing the appropriate type involves considering its usability, performance, and tradeoffs compared to other types.</span></span> <span data-ttu-id="d1dae-105">С момента выпуска C# 3,0 были доступны анонимные типы, а универсальные <xref:System.Tuple%602?displayProperty=nameWithType> типы были введены с помощью .NET Framework 4,0.</span><span class="sxs-lookup"><span data-stu-id="d1dae-105">Anonymous types have been available since C# 3.0, while generic <xref:System.Tuple%602?displayProperty=nameWithType> types were introduced with .NET Framework 4.0.</span></span> <span data-ttu-id="d1dae-106">Так как новые параметры были введены с поддержкой языкового уровня, например <xref:System.ValueTuple%602?displayProperty=nameWithType> , в качестве названия, укажите тип значения с гибкостью анонимных типов.</span><span class="sxs-lookup"><span data-stu-id="d1dae-106">Since then new options have been introduced with language level support, such as <xref:System.ValueTuple%602?displayProperty=nameWithType> - which as the name implies, provide a value type with the flexibility of anonymous types.</span></span> <span data-ttu-id="d1dae-107">В этой статье вы узнаете, когда нужно выбрать один тип для другого.</span><span class="sxs-lookup"><span data-stu-id="d1dae-107">In this article, you'll learn when it's appropriate to choose one type over the other.</span></span>

## <a name="usability-and-functionality"></a><span data-ttu-id="d1dae-108">Удобство использования и функциональность</span><span class="sxs-lookup"><span data-stu-id="d1dae-108">Usability and functionality</span></span>

<span data-ttu-id="d1dae-109">Анонимные типы появились в C# 3,0 с выражениями LINQ.</span><span class="sxs-lookup"><span data-stu-id="d1dae-109">Anonymous types were introduced in C# 3.0 with Language-Integrated Query (LINQ) expressions.</span></span> <span data-ttu-id="d1dae-110">С помощью LINQ разработчики часто получают результаты из запросов в анонимные типы, которые содержат несколько выбранных свойств из объектов, с которыми они работают.</span><span class="sxs-lookup"><span data-stu-id="d1dae-110">With LINQ, developers often project results from queries into anonymous types that hold a few select properties from the objects they're working with.</span></span> <span data-ttu-id="d1dae-111">Рассмотрим следующий пример, в котором создается массив <xref:System.DateTime> объектов, и выполняется итерация по проецированию в анонимный тип с двумя свойствами.</span><span class="sxs-lookup"><span data-stu-id="d1dae-111">Consider the following example, that instantiates an array of <xref:System.DateTime> objects, and iterates through them projecting into an anonymous type with two properties.</span></span>

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

<span data-ttu-id="d1dae-112">Экземпляры анонимных типов создаются с помощью [`new`](../../csharp/language-reference/operators/new-operator.md) оператора, а имена и типы свойств выводятся из объявления.</span><span class="sxs-lookup"><span data-stu-id="d1dae-112">Anonymous types are instantiated by using the [`new`](../../csharp/language-reference/operators/new-operator.md) operator, and the property names and types are inferred from the declaration.</span></span> <span data-ttu-id="d1dae-113">Если два или более инициализаторов анонимных объектов в одной сборке указывают последовательность свойств, которые находятся в том же порядке и имеют одинаковые имена и типы, компилятор рассматривает эти объекты как экземпляры одного типа.</span><span class="sxs-lookup"><span data-stu-id="d1dae-113">If two or more anonymous object initializers in the same assembly specify a sequence of properties that are in the same order and that have the same names and types, the compiler treats the objects as instances of the same type.</span></span> <span data-ttu-id="d1dae-114">Они используют одни и те же сведения типа, созданные компилятором.</span><span class="sxs-lookup"><span data-stu-id="d1dae-114">They share the same compiler-generated type information.</span></span>

<span data-ttu-id="d1dae-115">Предыдущий фрагмент кода C# проецирует анонимный тип с двумя свойствами, похожим на следующий созданный компилятором класс C#:</span><span class="sxs-lookup"><span data-stu-id="d1dae-115">The previous C# snippet projects an anonymous type with two properties, much like the following compiler-generated C# class:</span></span>

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

<span data-ttu-id="d1dae-116">Дополнительные сведения см. в разделе [анонимные типы](../../csharp/programming-guide/classes-and-structs/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="d1dae-116">For more information, see [anonymous types](../../csharp/programming-guide/classes-and-structs/anonymous-types.md).</span></span> <span data-ttu-id="d1dae-117">Те же функциональные возможности, что и кортежи при проецировании на запросы LINQ, можно выбрать в виде кортежей.</span><span class="sxs-lookup"><span data-stu-id="d1dae-117">The same functionality exists with tuples when projecting into LINQ queries, you can select properties into tuples.</span></span> <span data-ttu-id="d1dae-118">Эти кортежи проходят через запрос так же, как и анонимные типы.</span><span class="sxs-lookup"><span data-stu-id="d1dae-118">These tuples flow through the query, just as anonymous types would.</span></span> <span data-ttu-id="d1dae-119">Теперь рассмотрим следующий пример с помощью `System.Tuple<string, long>` .</span><span class="sxs-lookup"><span data-stu-id="d1dae-119">Now consider the following example using the `System.Tuple<string, long>`.</span></span>

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

<span data-ttu-id="d1dae-120">В <xref:System.Tuple%602?displayProperty=nameWithType> экземпляр предоставляет свойства нумерованного элемента, такие как `Item1` , и `Item2` .</span><span class="sxs-lookup"><span data-stu-id="d1dae-120">With the <xref:System.Tuple%602?displayProperty=nameWithType>, the instance exposes numbered item properties, such as `Item1`, and `Item2`.</span></span> <span data-ttu-id="d1dae-121">Эти имена свойств могут усложнить понимание намерения значений свойств, так как имя свойства предоставляет только порядковый номер.</span><span class="sxs-lookup"><span data-stu-id="d1dae-121">These property names can make it more difficult to understand the intent of the property values, as the property name only provides the ordinal.</span></span> <span data-ttu-id="d1dae-122">Более того, `System.Tuple` типы являются ссылочными `class` типами.</span><span class="sxs-lookup"><span data-stu-id="d1dae-122">Furthermore, the `System.Tuple` types are reference `class` types.</span></span> <span data-ttu-id="d1dae-123"><xref:System.ValueTuple%602?displayProperty=nameWithType>Однако является `struct` типом значения.</span><span class="sxs-lookup"><span data-stu-id="d1dae-123">The <xref:System.ValueTuple%602?displayProperty=nameWithType> however, is a value `struct` type.</span></span> <span data-ttu-id="d1dae-124">Следующий фрагмент кода C#, используемый `ValueTuple<string, long>` для проецирования в.</span><span class="sxs-lookup"><span data-stu-id="d1dae-124">The following C# snippet, uses `ValueTuple<string, long>` to project into.</span></span> <span data-ttu-id="d1dae-125">При этом он назначается с помощью литерального синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="d1dae-125">In doing so, it assigns using a literal syntax.</span></span>

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

<span data-ttu-id="d1dae-126">C# предоставляет языковую поддержку кортежей с <xref:System.ValueTuple> типом и семантикой для:</span><span class="sxs-lookup"><span data-stu-id="d1dae-126">C# provides language support of tuples with the <xref:System.ValueTuple> type, and semantics for:</span></span>

- [<span data-ttu-id="d1dae-127">Присваивание кортежа</span><span class="sxs-lookup"><span data-stu-id="d1dae-127">Tuple assignment</span></span>](../../csharp/tuples.md#assignment-and-tuples)
- <span data-ttu-id="d1dae-128">[Деконструкция кортежа](../../csharp/deconstruct.md) (не ограничена кортежами)</span><span class="sxs-lookup"><span data-stu-id="d1dae-128">[Tuple deconstruction](../../csharp/deconstruct.md) (not limited to tuples)</span></span>
- [<span data-ttu-id="d1dae-129">Проверки равенства кортежей</span><span class="sxs-lookup"><span data-stu-id="d1dae-129">Tuple equality checks</span></span>](../../csharp/tuples.md#equality-and-tuples)
- [<span data-ttu-id="d1dae-130">Инициализаторы проекций кортежа</span><span class="sxs-lookup"><span data-stu-id="d1dae-130">Tuple projection initializers</span></span>](../../csharp/tuples.md#tuple-projection-initializers)

<span data-ttu-id="d1dae-131">Однако предыдущие примеры функционально эквивалентны. существуют небольшие различия в удобстве их использования и их базовых реализациях.</span><span class="sxs-lookup"><span data-stu-id="d1dae-131">The previous examples are all functionally equivalent, however; there are slight differences in their usability and their underlying implementations.</span></span>

## <a name="tradeoffs"></a><span data-ttu-id="d1dae-132">Компромиссы</span><span class="sxs-lookup"><span data-stu-id="d1dae-132">Tradeoffs</span></span>

<span data-ttu-id="d1dae-133">Можно всегда использовать <xref:System.ValueTuple> <xref:System.Tuple> и анонимные типы, но есть компромиссы, которые следует учитывать.</span><span class="sxs-lookup"><span data-stu-id="d1dae-133">You might want to always use <xref:System.ValueTuple> over <xref:System.Tuple>, and anonymous types, but there are tradeoffs you should consider.</span></span> <span data-ttu-id="d1dae-134"><xref:System.ValueTuple>Типы являются изменяемыми, тогда как <xref:System.Tuple> доступны только для чтения.</span><span class="sxs-lookup"><span data-stu-id="d1dae-134">The <xref:System.ValueTuple> types are mutable, whereas <xref:System.Tuple> are read-only.</span></span> <span data-ttu-id="d1dae-135">Анонимные типы можно использовать в деревьях выражений, тогда как кортежи — нет.</span><span class="sxs-lookup"><span data-stu-id="d1dae-135">Anonymous types can be used in expression trees, while tuples cannot.</span></span> <span data-ttu-id="d1dae-136">В следующей таблице представлен обзор некоторых ключевых различий.</span><span class="sxs-lookup"><span data-stu-id="d1dae-136">The following table is an overview of some of the key differences.</span></span>

### <a name="key-differences"></a><span data-ttu-id="d1dae-137">Основные различия</span><span class="sxs-lookup"><span data-stu-id="d1dae-137">Key differences</span></span>

| <span data-ttu-id="d1dae-138">name</span><span class="sxs-lookup"><span data-stu-id="d1dae-138">Name</span></span>                     | <span data-ttu-id="d1dae-139">Модификатор доступа</span><span class="sxs-lookup"><span data-stu-id="d1dae-139">Access modifier</span></span> | <span data-ttu-id="d1dae-140">Тип</span><span class="sxs-lookup"><span data-stu-id="d1dae-140">Type</span></span>     | <span data-ttu-id="d1dae-141">Имя настраиваемого свойства</span><span class="sxs-lookup"><span data-stu-id="d1dae-141">Custom property name</span></span> | <span data-ttu-id="d1dae-142">Поддержка деконструкции</span><span class="sxs-lookup"><span data-stu-id="d1dae-142">Deconstruction support</span></span> | <span data-ttu-id="d1dae-143">Поддержка дерева выражений</span><span class="sxs-lookup"><span data-stu-id="d1dae-143">Expression tree support</span></span> |
|--------------------------|-----------------|----------|----------------------|------------------------|-------------------------|
| <span data-ttu-id="d1dae-144">Анонимные типы</span><span class="sxs-lookup"><span data-stu-id="d1dae-144">Anonymous types</span></span>          | `internal`      | `class`  | <span data-ttu-id="d1dae-145">✔️</span><span class="sxs-lookup"><span data-stu-id="d1dae-145">✔️</span></span>                   | ❌                     | <span data-ttu-id="d1dae-146">✔️</span><span class="sxs-lookup"><span data-stu-id="d1dae-146">✔️</span></span>                     |
| <xref:System.Tuple>      | `public`        | `class`  | ❌                   | ❌                     | <span data-ttu-id="d1dae-147">✔️</span><span class="sxs-lookup"><span data-stu-id="d1dae-147">✔️</span></span>                     |
| <xref:System.ValueTuple> | `public`        | `struct` | <span data-ttu-id="d1dae-148">✔️</span><span class="sxs-lookup"><span data-stu-id="d1dae-148">✔️</span></span>                   | <span data-ttu-id="d1dae-149">✔️</span><span class="sxs-lookup"><span data-stu-id="d1dae-149">✔️</span></span>                     | ❌                     |

### <a name="serialization"></a><span data-ttu-id="d1dae-150">Сериализация</span><span class="sxs-lookup"><span data-stu-id="d1dae-150">Serialization</span></span>

<span data-ttu-id="d1dae-151">При выборе типа важно учитывать, что он должен быть сериализован.</span><span class="sxs-lookup"><span data-stu-id="d1dae-151">One important consideration when choosing a type, is whether or not it will need to be serialized.</span></span> <span data-ttu-id="d1dae-152">Сериализация представляет собой процесс преобразования состояния объекта в форму, пригодную для сохранения или передачи.</span><span class="sxs-lookup"><span data-stu-id="d1dae-152">Serialization is the process of converting the state of an object into a form that can be persisted or transported.</span></span> <span data-ttu-id="d1dae-153">Дополнительные сведения см. в разделе [сериализация](../../csharp/programming-guide/concepts/serialization/index.md).</span><span class="sxs-lookup"><span data-stu-id="d1dae-153">For more information, see [serialization](../../csharp/programming-guide/concepts/serialization/index.md).</span></span> <span data-ttu-id="d1dae-154">При наличии важности сериализации создание `class` или `struct` предпочтительнее для анонимных типов или типов кортежей.</span><span class="sxs-lookup"><span data-stu-id="d1dae-154">When serialization is important, creating a `class` or `struct` is preferred over anonymous types or tuple types.</span></span>

## <a name="performance"></a><span data-ttu-id="d1dae-155">Производительность</span><span class="sxs-lookup"><span data-stu-id="d1dae-155">Performance</span></span>

<span data-ttu-id="d1dae-156">Производительность между этими типами зависит от сценария.</span><span class="sxs-lookup"><span data-stu-id="d1dae-156">Performance between these types depends on the scenario.</span></span> <span data-ttu-id="d1dae-157">Основное влияние заключается в компромиссе между выделением и копированием.</span><span class="sxs-lookup"><span data-stu-id="d1dae-157">The major impact involves the tradeoff between allocations and copying.</span></span> <span data-ttu-id="d1dae-158">В большинстве случаев влияние очень мало.</span><span class="sxs-lookup"><span data-stu-id="d1dae-158">In most scenarios, the impact is small.</span></span> <span data-ttu-id="d1dae-159">Когда могут возникнуть серьезные последствия, следует принять меры для информирования решения.</span><span class="sxs-lookup"><span data-stu-id="d1dae-159">When major impacts could arise, measurements should be taken to inform the decision.</span></span>

## <a name="conclusion"></a><span data-ttu-id="d1dae-160">Заключение</span><span class="sxs-lookup"><span data-stu-id="d1dae-160">Conclusion</span></span>

<span data-ttu-id="d1dae-161">В качестве разработчика, который выбирает между кортежами и анонимными типами, следует учитывать несколько факторов.</span><span class="sxs-lookup"><span data-stu-id="d1dae-161">As a developer choosing between tuples and anonymous types, there are several factors to consider.</span></span> <span data-ttu-id="d1dae-162">В общем случае, если вы не работаете с [деревьями выражений](../../csharp/expression-trees.md), и вы знакомы с синтаксисом кортежей, выберите <xref:System.ValueTuple> , так как они предоставляют тип значения с гибкостью именования свойств.</span><span class="sxs-lookup"><span data-stu-id="d1dae-162">Generally speaking, if you're not working with [expression trees](../../csharp/expression-trees.md), and you're comfortable with tuple syntax then choose <xref:System.ValueTuple> as they provide a value type with the flexibility to name properties.</span></span> <span data-ttu-id="d1dae-163">Если вы работаете с деревьями выражений и предпочитаете имена свойств, выберите Анонимные типы.</span><span class="sxs-lookup"><span data-stu-id="d1dae-163">If you're working with expression trees, and you'd prefer to name properties, choose anonymous types.</span></span> <span data-ttu-id="d1dae-164">Или используйте <xref:System.Tuple>.</span><span class="sxs-lookup"><span data-stu-id="d1dae-164">Otherwise, use <xref:System.Tuple>.</span></span>

## <a name="see-also"></a><span data-ttu-id="d1dae-165">См. также</span><span class="sxs-lookup"><span data-stu-id="d1dae-165">See also</span></span>

- [<span data-ttu-id="d1dae-166">Анонимные типы</span><span class="sxs-lookup"><span data-stu-id="d1dae-166">Anonymous types</span></span>](../../csharp/programming-guide/classes-and-structs/anonymous-types.md)
- [<span data-ttu-id="d1dae-167">Деревья выражений</span><span class="sxs-lookup"><span data-stu-id="d1dae-167">Expression trees</span></span>](../../csharp/expression-trees.md)
- [<span data-ttu-id="d1dae-168">Рекомендации по разработке платформы</span><span class="sxs-lookup"><span data-stu-id="d1dae-168">Framework design guidelines</span></span>](index.md)
- [<span data-ttu-id="d1dae-169">Типы кортежей</span><span class="sxs-lookup"><span data-stu-id="d1dae-169">Tuple types</span></span>](../../csharp/tuples.md)
- [<span data-ttu-id="d1dae-170">Правила разработки типов</span><span class="sxs-lookup"><span data-stu-id="d1dae-170">Type design guidelines</span></span>](type.md)
