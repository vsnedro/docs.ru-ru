---
title: Выбор между анонимными типами и кортежами
description: Сведения о том, как сделать выбор между анонимными типами и кортежами.
author: IEvangelist
ms.author: dapine
ms.date: 07/01/2020
ms.technology: dotnet-standard
ms.openlocfilehash: 9c186133a639faf187c89d872856d860a20f5a2d
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174222"
---
# <a name="choosing-between-anonymous-and-tuple-types"></a>Выбор между анонимными типами и кортежами

При выборе подходящего типа необходимо учитывать его применимость, производительность и недостатки по сравнению с другими типами. Анонимные типы были представлены в C# 3.0, а универсальные типы <xref:System.Tuple%602?displayProperty=nameWithType> — в .NET Framework 4.0. После этого появились новые поддерживаемые на уровне языка параметры, например <xref:System.ValueTuple%602?displayProperty=nameWithType>, который, как следует из его имени, реализует тип значения, обладающий универсальностью анонимного типа. В этой статье мы расскажем о том, в каких случаях следует выбирать тот или иной тип.

## <a name="usability-and-functionality"></a>Применимость и функциональность

Анонимные типы были представлены в C# 3.0 вместе с выражениями LINQ. С помощью LINQ разработчики часто проецируют результаты запросов в анонимные типы, содержащие некоторые из свойств объектов, с которыми они работают. Рассмотрим следующий пример, где создается экземпляр массива объектов <xref:System.DateTime>, которые посредством итераций проецируются в анонимный тип с двумя свойствами.

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

Экземпляры анонимных типов создаются с помощью оператора [`new`](../../csharp/language-reference/operators/new-operator.md), а имена свойств и типы при этом выводятся из объявления. Если несколько инициализаторов анонимных объектов в одной сборке указывают на последовательность свойств, идущих в том же порядке и имеющих те же типы и имена, компилятор обрабатывает объекты как экземпляры одного типа. Они используют одни и те же сведения типа, созданные компилятором.

В приведенном выше фрагменте кода C# выполняется проецирование в анонимный тип с двумя свойствами, что во многом аналогично создаваемому компилятором классу C#:

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

Дополнительные сведения см. в статье [Анонимные типы](../../csharp/programming-guide/classes-and-structs/anonymous-types.md). Аналогичная ситуация складывается с кортежами: при проецировании в запросы LINQ вы можете выбирать свойства для кортежа. Такие кортежи обрабатываются в рамках запроса так же, как и анонимные типы. Рассмотрим следующий пример, в котором используется `System.Tuple<string, long>`.

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

С помощью <xref:System.Tuple%602?displayProperty=nameWithType> экземпляр предоставляет свойства нумерованного элемента, такие как `Item1` и `Item2`. При использовании таких имен свойств, которые содержат только порядковые номера, сложно понять предназначение их значений. Кроме того, типы `System.Tuple` являются ссылочными типами `class`. Тем не менее, <xref:System.ValueTuple%602?displayProperty=nameWithType> является типом значения `struct`. В следующем фрагменте кода C# выполняется проецирование в `ValueTuple<string, long>`. При этом назначение осуществляется с использованием литерального синтаксиса.

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

Дополнительные сведения о кортежах см. в статьях [Типы кортежей (справочник по C#)](../../csharp/language-reference/builtin-types/value-tuples.md) или [Кортежи (Visual Basic)](../../visual-basic/programming-guide/language-features/data-types/tuples.md).

И все же приведенные выше примеры эквивалентны с функциональной точки зрения и незначительно различаются в контексте применимости и базовой реализации.

## <a name="tradeoffs"></a>Компромиссы

Вы можете во всех случаях использовать <xref:System.ValueTuple> вместо <xref:System.Tuple> и анонимные типы, однако при этом необходимо учитывать свойственные им недостатки. Типы <xref:System.ValueTuple> являются изменяемыми, тогда как типы <xref:System.Tuple> доступны только для чтения. В отличие от кортежей, анонимные типы можно использовать в деревьях выражений. В следующей таблице представлен обзор некоторых основных различий между ними.

### <a name="key-differences"></a>Основные отличия

| name                     | Модификатор доступа | Type     | Имя пользовательского элемента | Поддержка деконструирования | Поддержка деревьев выражений |
|--------------------------|-----------------|----------|----------------------|------------------------|-------------------------|
| Анонимные типы          | `internal`      | `class`  | ✔️                   | ❌                     | ✔️                     |
| <xref:System.Tuple>      | `public`        | `class`  | ❌                   | ❌                     | ✔️                     |
| <xref:System.ValueTuple> | `public`        | `struct` | ✔️                   | ✔️                     | ❌                     |

### <a name="serialization"></a>Сериализация

При выборе типа важно учитывать необходимость в его сериализации. Сериализация представляет собой процесс преобразования состояния объекта в форму, пригодную для сохранения или передачи. Дополнительные сведения см. в статье [Сериализация](../../csharp/programming-guide/concepts/serialization/index.md). Если сериализация нужна, вместо анонимных типов или кортежей рекомендуется создавать `class` или `struct`.

## <a name="performance"></a>Производительность

Различия в производительности между этими типами зависят от сценария их применения. Основным фактором, влияющим на производительность, является достижение компромисса между возможностями выделения памяти и копирования. В большинстве случаев это влияние незначительно. Тем не менее, если возникают проблемы, следует выполнить измерения, по результатам которых будет приниматься взвешенное решение.

## <a name="conclusion"></a>Заключение

При выборе между анонимными типами и кортежами разработчику необходимо учитывать ряд факторов. В общем случае, если вы не работаете с [деревьями выражений](../../csharp/expression-trees.md) и хорошо знакомы с синтаксисом кортежей, мы рекомендуем выбирать типы <xref:System.ValueTuple>, которые предоставляют тип значений с возможностью именования свойств. Если вы работаете с деревьями выражений и предпочитаете именованные свойства, следует выбирать анонимные типы. В противном случае используйте коллекцию <xref:System.Tuple>.

## <a name="see-also"></a>См. также

- [Анонимные типы](../../csharp/programming-guide/classes-and-structs/anonymous-types.md)
- [Деревья выражений](../../csharp/expression-trees.md)
- [Типы кортежей (справочник по C#)](../../csharp/language-reference/builtin-types/value-tuples.md)
- [Кортежи (Visual Basic)](../../visual-basic/programming-guide/language-features/data-types/tuples.md)
- [Правила разработки типов](../design-guidelines/type.md)
