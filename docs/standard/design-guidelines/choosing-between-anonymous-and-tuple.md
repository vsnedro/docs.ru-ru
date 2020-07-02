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
# <a name="choosing-between-anonymous-and-tuple-types"></a>Выбор между анонимными и типами кортежей

Выбор подходящего типа предполагает возможность использования, производительности и компромиссов по сравнению с другими типами. С момента выпуска C# 3,0 были доступны анонимные типы, а универсальные <xref:System.Tuple%602?displayProperty=nameWithType> типы были введены с помощью .NET Framework 4,0. Так как новые параметры были введены с поддержкой языкового уровня, например <xref:System.ValueTuple%602?displayProperty=nameWithType> , в качестве названия, укажите тип значения с гибкостью анонимных типов. В этой статье вы узнаете, когда нужно выбрать один тип для другого.

## <a name="usability-and-functionality"></a>Удобство использования и функциональность

Анонимные типы появились в C# 3,0 с выражениями LINQ. С помощью LINQ разработчики часто получают результаты из запросов в анонимные типы, которые содержат несколько выбранных свойств из объектов, с которыми они работают. Рассмотрим следующий пример, в котором создается массив <xref:System.DateTime> объектов, и выполняется итерация по проецированию в анонимный тип с двумя свойствами.

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

Экземпляры анонимных типов создаются с помощью [`new`](../../csharp/language-reference/operators/new-operator.md) оператора, а имена и типы свойств выводятся из объявления. Если два или более инициализаторов анонимных объектов в одной сборке указывают последовательность свойств, которые находятся в том же порядке и имеют одинаковые имена и типы, компилятор рассматривает эти объекты как экземпляры одного типа. Они используют одни и те же сведения типа, созданные компилятором.

Предыдущий фрагмент кода C# проецирует анонимный тип с двумя свойствами, похожим на следующий созданный компилятором класс C#:

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

Дополнительные сведения см. в разделе [анонимные типы](../../csharp/programming-guide/classes-and-structs/anonymous-types.md). Те же функциональные возможности, что и кортежи при проецировании на запросы LINQ, можно выбрать в виде кортежей. Эти кортежи проходят через запрос так же, как и анонимные типы. Теперь рассмотрим следующий пример с помощью `System.Tuple<string, long>` .

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

В <xref:System.Tuple%602?displayProperty=nameWithType> экземпляр предоставляет свойства нумерованного элемента, такие как `Item1` , и `Item2` . Эти имена свойств могут усложнить понимание намерения значений свойств, так как имя свойства предоставляет только порядковый номер. Более того, `System.Tuple` типы являются ссылочными `class` типами. <xref:System.ValueTuple%602?displayProperty=nameWithType>Однако является `struct` типом значения. Следующий фрагмент кода C#, используемый `ValueTuple<string, long>` для проецирования в. При этом он назначается с помощью литерального синтаксиса.

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

C# предоставляет языковую поддержку кортежей с <xref:System.ValueTuple> типом и семантикой для:

- [Присваивание кортежа](../../csharp/tuples.md#assignment-and-tuples)
- [Деконструкция кортежа](../../csharp/deconstruct.md) (не ограничена кортежами)
- [Проверки равенства кортежей](../../csharp/tuples.md#equality-and-tuples)
- [Инициализаторы проекций кортежа](../../csharp/tuples.md#tuple-projection-initializers)

Однако предыдущие примеры функционально эквивалентны. существуют небольшие различия в удобстве их использования и их базовых реализациях.

## <a name="tradeoffs"></a>Компромиссы

Можно всегда использовать <xref:System.ValueTuple> <xref:System.Tuple> и анонимные типы, но есть компромиссы, которые следует учитывать. <xref:System.ValueTuple>Типы являются изменяемыми, тогда как <xref:System.Tuple> доступны только для чтения. Анонимные типы можно использовать в деревьях выражений, тогда как кортежи — нет. В следующей таблице представлен обзор некоторых ключевых различий.

### <a name="key-differences"></a>Основные различия

| name                     | Модификатор доступа | Тип     | Имя настраиваемого свойства | Поддержка деконструкции | Поддержка дерева выражений |
|--------------------------|-----------------|----------|----------------------|------------------------|-------------------------|
| Анонимные типы          | `internal`      | `class`  | ✔️                   | ❌                     | ✔️                     |
| <xref:System.Tuple>      | `public`        | `class`  | ❌                   | ❌                     | ✔️                     |
| <xref:System.ValueTuple> | `public`        | `struct` | ✔️                   | ✔️                     | ❌                     |

### <a name="serialization"></a>Сериализация

При выборе типа важно учитывать, что он должен быть сериализован. Сериализация представляет собой процесс преобразования состояния объекта в форму, пригодную для сохранения или передачи. Дополнительные сведения см. в разделе [сериализация](../../csharp/programming-guide/concepts/serialization/index.md). При наличии важности сериализации создание `class` или `struct` предпочтительнее для анонимных типов или типов кортежей.

## <a name="performance"></a>Производительность

Производительность между этими типами зависит от сценария. Основное влияние заключается в компромиссе между выделением и копированием. В большинстве случаев влияние очень мало. Когда могут возникнуть серьезные последствия, следует принять меры для информирования решения.

## <a name="conclusion"></a>Заключение

В качестве разработчика, который выбирает между кортежами и анонимными типами, следует учитывать несколько факторов. В общем случае, если вы не работаете с [деревьями выражений](../../csharp/expression-trees.md), и вы знакомы с синтаксисом кортежей, выберите <xref:System.ValueTuple> , так как они предоставляют тип значения с гибкостью именования свойств. Если вы работаете с деревьями выражений и предпочитаете имена свойств, выберите Анонимные типы. Или используйте <xref:System.Tuple>.

## <a name="see-also"></a>См. также

- [Анонимные типы](../../csharp/programming-guide/classes-and-structs/anonymous-types.md)
- [Деревья выражений](../../csharp/expression-trees.md)
- [Рекомендации по разработке платформы](index.md)
- [Типы кортежей](../../csharp/tuples.md)
- [Правила разработки типов](type.md)
