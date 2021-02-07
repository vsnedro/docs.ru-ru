---
description: Дополнительные сведения о операторе Mod (Visual Basic)
title: Оператор Mod
ms.date: 04/24/2018
f1_keywords:
- vb.Mod
helpviewer_keywords:
- remainder (Mod operator)
- division operator [Visual Basic], Mod operator
- modulus operator [Visual Basic], Visual Basic
- Mod operator [Visual Basic]
- operators [Visual Basic], division
- arithmetic operators [Visual Basic], Mod
- math operators [Visual Basic]
ms.assetid: 6ff7e40e-cec8-4c77-bff6-8ddd2791c25b
ms.openlocfilehash: bfec39f54041714258e21f087a044dce24edcb6b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99665436"
---
# <a name="mod-operator-visual-basic"></a>Оператор Mod (Visual Basic)

Делит два числа и возвращает только остаток.

## <a name="syntax"></a>Синтаксис

```vb
result = number1 Mod number2
```

## <a name="parts"></a>Компоненты

`result` \
Обязательный элемент. Любая числовая переменная или свойство.

`number1` \
Обязательный. Произвольное числовое выражение.

`number2` \
Обязательный. Произвольное числовое выражение.

## <a name="supported-types"></a>Поддерживаемые типы

все числовые типы. К ним относятся типы без знака и тип с плавающей запятой и `Decimal` .

## <a name="result"></a>Результат

Результат — остаток от деления на `number1` `number2` . Например, выражение принимает значение `14 Mod 4` 2.

> [!NOTE]
> Существует разница между *остатком* и *остатком* в математике с различными результатами для отрицательных чисел. `Mod`Оператор в Visual Basic, `op_Modulus` оператор платформа .NET Framework и базовая инструкция [REM](<xref:System.Reflection.Emit.OpCodes.Rem>) Il выполняют операцию остатка.

Результат `Mod` операции удерживает знак делимого, `number1` и поэтому он может быть положительным или отрицательным. Результат всегда находится в диапазоне (- `number2` , `number2` ), исключающем. Пример:

```vb
Public Module Example
   Public Sub Main()
      Console.WriteLine($" 8 Mod  3 = {8 Mod 3}")
      Console.WriteLine($"-8 Mod  3 = {-8 Mod 3}")
      Console.WriteLine($" 8 Mod -3 = {8 Mod -3}")
      Console.WriteLine($"-8 Mod -3 = {-8 Mod -3}")
   End Sub
End Module
' The example displays the following output:
'       8 Mod  3 = 2
'      -8 Mod  3 = -2
'       8 Mod -3 = 2
'      -8 Mod -3 = -2
```

## <a name="remarks"></a>Remarks

Если `number1` или `number2` является значением с плавающей запятой, то возвращается остаток от деления с плавающей запятой. Тип данных результата является наименьшим типом данных, который может содержать все возможные значения, являющиеся результатом деления с типами данных `number1` и `number2` .

Если `number1` или `number2` имеет значение [Nothing](../nothing.md), оно считается нулевым.

К связанным операторам относятся следующие.

- [Оператор \ (Visual Basic)](integer-division-operator.md) возвращает целочисленное частное от деления. Например, выражение принимает значение `14 \ 4` 3.

- [Оператор/(Visual Basic)](floating-point-division-operator.md) возвращает полное частное, включая остаток, в виде числа с плавающей запятой. Например, `14 / 4` результатом вычисления выражения является 3,5.

## <a name="attempted-division-by-zero"></a>Попыток деления на ноль

Если `number2` значение равно нулю, поведение `Mod` оператора зависит от типа данных операндов:

- Целочисленное деление вызывает <xref:System.DivideByZeroException> исключение, если `number2` не может быть определено во время компиляции и вызывает ошибку во время компиляции, `BC30542 Division by zero occurred while evaluating this expression` Если `number2` во время компиляции значение равно нулю.
- Деление с плавающей запятой возвращает <xref:System.Double.NaN?displayProperty=nameWithType> .

## <a name="equivalent-formula"></a>Эквивалентная формула

Выражение `a Mod b` эквивалентно любой из следующих формул:

`a - (b * (a \ b))`

`a - (b * Fix(a / b))`

## <a name="floating-point-imprecision"></a>Точность чисел с плавающей запятой

При работе с числами с плавающей запятой Помните, что они не всегда имеют точное десятичное представление в памяти. Это может привести к непредвиденным результатам некоторых операций, таких как сравнение значений и `Mod` оператор. Дополнительные сведения см. в разделе [Устранение неполадок типов данных](../../programming-guide/language-features/data-types/troubleshooting-data-types.md).

## <a name="overloading"></a>Перегрузка

`Mod`Оператор можно *перегрузить*, то есть класс или структура может переопределить его поведение. Если код применяется `Mod` к экземпляру класса или структуры, включающей такую перегрузку, убедитесь, что вы понимаете его переопределенное поведение. Для получения дополнительной информации см. [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).

## <a name="example"></a>Пример

В следующем примере оператор используется `Mod` для деления двух чисел и возврата только остатка. Если любое число является числом с плавающей запятой, результатом является число с плавающей запятой, представляющее остаток.

[!code-vb[VbVbalrOperators#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#31)]

## <a name="example"></a>Пример

В следующем примере показана потенциальная неточность операндов с плавающей запятой. В первой инструкции операнды имеют `Double` значение, а 0,2 — бесконечно повторяющуюся двоичную дробь с хранимым значением 0.20000000000000001. Во второй инструкции символ типа литерала `D` принуждает оба операнда к `Decimal` , и 0,2 имеет точное представление.

[!code-vb[VbVbalrOperators#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#32)]

## <a name="see-also"></a>См. также

- <xref:Microsoft.VisualBasic.Conversion.Int%2A>
- <xref:Microsoft.VisualBasic.Conversion.Fix%2A>
- [Арифметические операторы](arithmetic-operators.md)
- [Порядок применения операторов в Visual Basic](operator-precedence.md)
- [Список операторов, сгруппированных по функциональному назначению](operators-listed-by-functionality.md)
- [Устранение неполадок, связанных с типами данных](../../programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Арифметические операторы в Visual Basic](../../programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [Оператор \ (Visual Basic)](integer-division-operator.md)
