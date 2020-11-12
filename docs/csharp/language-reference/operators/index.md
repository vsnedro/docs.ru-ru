---
title: Операторы и выражения C# — справочник по C#
description: Сведения об операторах и выражениях C#, приоритете и ассоциативности операторов
ms.date: 08/04/2020
f1_keywords:
- cs.operators
helpviewer_keywords:
- operators [C#]
- operator precedence [C#]
- operator associativity [C#]
- expressions [C#]
ms.assetid: 0301e31f-22ad-49af-ac3c-d5eae7f0ac43
ms.openlocfilehash: 9e7ca2087938317f7369043e21fd455dbad7f07b
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2020
ms.locfileid: "94439666"
---
# <a name="c-operators-and-expressions-c-reference"></a>Операторы и выражения C# (справочник по C#)

C# предоставляет ряд операторов. Многие из них поддерживаются [встроенными типами](../builtin-types/built-in-types.md) и позволяют выполнять базовые операции со значениями этих типов. В число этих операторов входят следующие группы:

- [Арифметические операторы](arithmetic-operators.md), выполняющие арифметические операции с числовыми операндами.
- [Операторы сравнения](comparison-operators.md), сравнивающие числовые операнды.
- [Логические операторы](boolean-logical-operators.md), выполняющие логические операции с операндами [`bool`](../builtin-types/bool.md).
- [Битовые операторы и операторы сдвига](bitwise-and-shift-operators.md) выполняют битовые операции или операции сдвига с операндами целочисленных типов.
- [Операторы равенства](equality-operators.md) проверяют равенство или неравенство своих операндов.

Как правило, можно выполнить [перегрузку](operator-overloading.md) этих операторов, то есть указать поведение оператора для операндов определяемого пользователем типа.

Простейшими выражениями C# являются литералы (например, [целые](../builtin-types/integral-numeric-types.md#integer-literals) и [реальные](../builtin-types/floating-point-numeric-types.md#real-literals) числа) и имена переменных. Их можно объединить в сложные выражения с помощью операторов. [Приоритет](#operator-precedence) и [ассоциативность](#operator-associativity) операторов определяют порядок выполнения операций в выражении. Порядок вычисления, определяемый приоритетом и ассоциативностью операторов, можно изменить с помощью скобок.

В следующем коде примеры выражений находятся в правой части назначений:

[!code-csharp[expression examples](snippets/shared/Overview.cs#Expressions)]

Как правило, выражение выдает результат и может быть заключено в другое выражение. Вызов метода [`void`](../builtin-types/void.md) является примером выражения, которое дает результат. Его можно использовать только в качестве [оператора](../../programming-guide/statements-expressions-operators/statements.md), как показано в следующем примере:

```csharp
Console.WriteLine("Hello, world!");
```

Ниже приведены некоторые другие виды выражений, доступные в C#:

- [Выражения интерполированных строк](../tokens/interpolated.md), которые предоставляют удобный синтаксис для создания форматированных строк:

  [!code-csharp-interactive[interpolated string](snippets/shared/Overview.cs#InterpolatedString)]

- [Лямбда-выражения](lambda-expressions.md), позволяющие создавать анонимные функции:

  [!code-csharp-interactive[lambda expression](snippets/shared/Overview.cs#Lambda)]

- [Выражения запроса](../keywords/query-keywords.md), позволяющие использовать возможности запросов непосредственно в C#:

  [!code-csharp-interactive[query expression](snippets/shared/Overview.cs#Query)]

[Определение тела выражения](../../programming-guide/statements-expressions-operators/expression-bodied-members.md) можно использовать, чтобы предоставить краткое определение для метода, конструктора, свойства, индексатора или метода завершения.

## <a name="operator-precedence"></a>Приоритет операторов

В выражении с несколькими операторами операторы с более высоким приоритетом оцениваются до операторов с более низким приоритетом. В следующем примере умножение выполняется сначала, так как оно имеет более высокий приоритет, чем сложение:

```csharp-interactive
var a = 2 + 2 * 2;
Console.WriteLine(a); //  output: 6
```

Используйте скобки, чтобы изменить порядок вычисления, накладываемый приоритетом операторов:

```csharp-interactive
var a = (2 + 2) * 2;
Console.WriteLine(a); //  output: 8
```

В следующей таблице перечислены операторы C# в порядке убывания приоритета. Операторы в каждой строке имеют одинаковый приоритет.

| Операторы | Категория или имя |
| --------- | ---------------- |
| [x.y](member-access-operators.md#member-access-expression-), [f(x)](member-access-operators.md#invocation-expression-), [a&#91;i&#93;](member-access-operators.md#indexer-operator-), [`x?.y`](member-access-operators.md#null-conditional-operators--and-), [`x?[y]`](member-access-operators.md#null-conditional-operators--and-), [x++](arithmetic-operators.md#increment-operator-), [x--](arithmetic-operators.md#decrement-operator---), [x!](null-forgiving.md), [new](new-operator.md), [typeof](type-testing-and-cast.md#typeof-operator), [checked](../keywords/checked.md), [unchecked](../keywords/unchecked.md), [default](default.md), [nameof](nameof.md), [delegate](delegate-operator.md), [sizeof](sizeof.md), [stackalloc](stackalloc.md), [x->y](pointer-related-operators.md#pointer-member-access-operator--) | Первичный |
| [+x](arithmetic-operators.md#unary-plus-and-minus-operators), [-x](arithmetic-operators.md#unary-plus-and-minus-operators), [\!x](boolean-logical-operators.md#logical-negation-operator-), [~x](bitwise-and-shift-operators.md#bitwise-complement-operator-), [++x](arithmetic-operators.md#increment-operator-), [--x](arithmetic-operators.md#decrement-operator---), [^x](member-access-operators.md#index-from-end-operator-), [(T)x](type-testing-and-cast.md#cast-expression), [await](await.md), [&x](pointer-related-operators.md#address-of-operator-), [*x](pointer-related-operators.md#pointer-indirection-operator-), [true и false](true-false-operators.md) | Унарный |
| [x..y](member-access-operators.md#range-operator-) | Диапазон |
| [switch](switch-expression.md) | Выражение `switch` |
| [with](with-expression.md) | Выражение `with` |
| [x * y](arithmetic-operators.md#multiplication-operator-), [x / y](arithmetic-operators.md#division-operator-), [x % y](arithmetic-operators.md#remainder-operator-) | Мультипликативный|
| [x + y](arithmetic-operators.md#addition-operator-), [x – y](arithmetic-operators.md#subtraction-operator--) | Аддитивный |
| [x \<\<  y](bitwise-and-shift-operators.md#left-shift-operator-), [x >> y](bitwise-and-shift-operators.md#right-shift-operator-) | Сдвиг |
| [x \< y](comparison-operators.md#less-than-operator-), [x > y](comparison-operators.md#greater-than-operator-), [x \<= y](comparison-operators.md#less-than-or-equal-operator-), [x >= y](comparison-operators.md#greater-than-or-equal-operator-), [is](type-testing-and-cast.md#is-operator), [as](type-testing-and-cast.md#as-operator) | Тестирование типов и относительный |
| [x == y](equality-operators.md#equality-operator-), [x != y](equality-operators.md#inequality-operator-) | Равенство |
| `x & y` | [Логическое И](boolean-logical-operators.md#logical-and-operator-) или [побитовое логическое И](bitwise-and-shift-operators.md#logical-and-operator-) |
| `x ^ y` | [Логическое исключающее ИЛИ](boolean-logical-operators.md#logical-exclusive-or-operator-) или [побитовое логическое исключающее ИЛИ](bitwise-and-shift-operators.md#logical-exclusive-or-operator-) |
| <code>x &#124; y</code> | [Логическое ИЛИ](boolean-logical-operators.md#logical-or-operator-) или [побитовое логическое ИЛИ](bitwise-and-shift-operators.md#logical-or-operator-) |
| [x && y](boolean-logical-operators.md#conditional-logical-and-operator-) | Условное И |
| [x &#124;&#124; y](boolean-logical-operators.md#conditional-logical-or-operator-) | Условное ИЛИ |
| [x ?? y](null-coalescing-operator.md) | Оператор объединения с NULL |
| [c ? t : f](conditional-operator.md) | Условный оператор |
| [x = y](assignment-operator.md), [x += y](arithmetic-operators.md#compound-assignment), [x -= y](arithmetic-operators.md#compound-assignment), [x *= y](arithmetic-operators.md#compound-assignment), [x /= y](arithmetic-operators.md#compound-assignment), [x %= y](arithmetic-operators.md#compound-assignment), [x &= y](boolean-logical-operators.md#compound-assignment), [x &#124;= y](boolean-logical-operators.md#compound-assignment), [x ^= y](boolean-logical-operators.md#compound-assignment), [x <<= y](bitwise-and-shift-operators.md#compound-assignment), [x >>= y](bitwise-and-shift-operators.md#compound-assignment), [x ??= y](null-coalescing-operator.md), [=>](lambda-operator.md) | Назначение и объявление лямбда-выражений |

## <a name="operator-associativity"></a>Ассоциативность операторов

Если операторы имеют одинаковый приоритет, порядок их выполнения определяется ассоциативностью операторов:

- Операторы с *левой ассоциативностью* вычисляются слева направо. За исключением [операторов присваивания](assignment-operator.md) и [оператора объединения со значением NULL](null-coalescing-operator.md), все бинарные операторы имеют левую ассоциативность. Например, выражение `a + b - c` вычисляется как `(a + b) - c`.
- Операторы с *правой ассоциативностью* вычисляются справа налево. Операторы присваивания, оператор объединения со значением NULL и [условный оператор `?:`](conditional-operator.md) имеют правую ассоциативность. Например, выражение `x = y = z` вычисляется как `x = (y = z)`.

Используйте скобки, чтобы изменить порядок вычисления, накладываемый ассоциативностью операторов:

```csharp-interactive
int a = 13 / 5 / 2;
int b = 13 / (5 / 2);
Console.WriteLine($"a = {a}, b = {b}");  // output: a = 1, b = 6
```

## <a name="operand-evaluation"></a>Вычисление операнда

Не связанные с приоритетом и ассоциативностью операторов операнды в выражении вычисляются слева направо. В следующих примерах иллюстрируется порядок вычисления операторов и операндов:

| Выражение | Порядок вычислений |
| ---------- | ------------------- |
|`a + b`|a, b, +|
|`a + b * c`|a, b, c, *, +|
|`a / b + c * d`|a, b, /, c, d, *, +|
|`a / (b + c) * d`|a, b, c, +, /, d, *|

Как правило, оцениваются все операнды операторов. Однако некоторые операторы оценивают операнды условно. То есть значение крайнего левого операнда такого оператора определяет, следует ли оценивать другие операнды. Эти операторы являются условными логическими операторами [И (`&&`)](boolean-logical-operators.md#conditional-logical-and-operator-) и [ИЛИ (`||`) ](boolean-logical-operators.md#conditional-logical-or-operator-), [операторами объединения со значением NULL`??` и `??=`](null-coalescing-operator.md), [условными операторами со значением NULL `?.` и `?[]` и ](member-access-operators.md#null-conditional-operators--and-)[условным оператором `?:`](conditional-operator.md). Дополнительные сведения см. в описании каждого оператора.

## <a name="c-language-specification"></a>Спецификация языка C#

Дополнительные сведения см. в следующих разделах статьи [Спецификация языка C#](~/_csharplang/spec/introduction.md):

- [Выражения](~/_csharplang/spec/expressions.md)
- [Инструкции](~/_csharplang/spec/expressions.md#operators)

## <a name="see-also"></a>См. также

- [справочник по C#](../index.md)
- [Перегрузка операторов](operator-overloading.md)
- [Деревья выражений](../../programming-guide/concepts/expression-trees/index.md)
