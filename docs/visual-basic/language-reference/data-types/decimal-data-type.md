---
title: Тип данных Decimal
ms.date: 07/20/2015
f1_keywords:
- vb.Decimal
helpviewer_keywords:
- literal type characters [Visual Basic], D
- trailing zeros
- real numbers
- trailing 0 characters [Visual Basic]
- Decimal data type
- D literal type character [Visual Basic]
- decimals, Decimal data type
- 0 characters [Visual Basic], trailing
- data types [Visual Basic], assigning
- decimal keyword [Visual Basic]
- numbers [Visual Basic], real
- variable-precision numbers
- zeros, trailing
- '@ identifier type character'
- identifier type characters [Visual Basic], @
ms.assetid: 1d855b45-afe2-45b0-a623-96b6f63a43d5
ms.openlocfilehash: d4d868ba7c05cf3c2d538de1217231df91d4f43d
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/13/2020
ms.locfileid: "81243327"
---
# <a name="decimal-data-type-visual-basic"></a>Тип данных Decimal (Visual Basic)

Содержит 128-разрядные (16-байтные) значения со знаком, представляющие 96-разрядные (12-байтные) целые числа с переменной степенью, кратной 10. Коэффициент масштабирования определяет количество цифр справа от десятичной точки; она колеблется от 0 до 28. С шкалой 0 (без десятичных мест), максимально возможное значение составляет 79,228,162,514,264,337,593,543,950,335 (No /-7,92281625511144355933334433344330E-28). С 28 десятичных мест, наибольшее значение является No / 7,922816251426337593543950335, и наименьшее ненулевое значение является No / 0,0000000000000000000000000000000000 (/-1E-28).

## <a name="remarks"></a>Remarks

Тип `Decimal` данных обеспечивает наибольшее количество значительных цифр для числа. Он поддерживает до 29 значительных цифр и может представлять значения, превышающие 7,9228 х 10 х 28. Он особенно подходит для расчетов, таких как финансовые, которые требуют большого количества цифр, но не могут мириться с ошибками округления.

Значение по умолчанию для типа `Decimal` — 0.

## <a name="programming-tips"></a>Советы по программированию

- **Точность.** `Decimal`не является типом данных плавающей точки. Структура `Decimal` содержит двоичное значение рядом, вместе с битом знака и коэффициентом масштабирования, который определяет, какая часть значения является десятичной фракцией. Из-за `Decimal` этого, числа имеют более точное представление в`Single` `Double`памяти, чем плавающие точки типов (и ).

- **Производительности.** Тип `Decimal` данных является самым медленным из всех числовых типов. Прежде чем выбирать тип данных, следует взвесить важность точности с производительностью.

- **Расширение.** Тип `Decimal` данных расширяется до `Single` или `Double`. Это означает, `Decimal` что вы можете преобразовать <xref:System.OverflowException?displayProperty=nameWithType> в любой из этих типов, не сталкиваясь с ошибкой.

- **Трейлинг Ноль.** Visual Basic не хранит задние `Decimal` нули в буквальном смысле. Тем не `Decimal` менее, переменная сохраняет любые задние нули, приобретенные в расчете. Это показано в следующем примере.

  ```vb
  Dim d1, d2, d3, d4 As Decimal
  d1 = 2.375D
  d2 = 1.625D
  d3 = d1 + d2
  d4 = 4.000D
  MsgBox("d1 = " & CStr(d1) & ", d2 = " & CStr(d2) &
        ", d3 = " & CStr(d3) & ", d4 = " & CStr(d4))
  ```

  Выход `MsgBox` в предыдущем примере заключается в следующем:

  ```console
  d1 = 2.375, d2 = 1.625, d3 = 4.000, d4 = 4
  ```

- **Тип символов.** При добавлении к литералу символа типа литерала `D` производится принудительное приведение литерала к типу данных `Decimal`. При добавлении символа идентификатора типа `@` к любому идентификатору производится принудительное приведение этого идентификатора к типу `Decimal`.

- **Тип Framework.** В .NET Framework данный тип соответствует структуре <xref:System.Decimal?displayProperty=nameWithType>.

## <a name="range"></a>Диапазон

 Возможно, потребуется `D` использовать символ типа для присвоения большого значения переменной или постоянной. `Decimal` Это требование объясняется тем, что компилятор интерпретирует буквальный как `Long` если бы персонаж буквального типа не следовал буквальному, как показано в следующем примере.

```vb
Dim bigDec1 As Decimal = 9223372036854775807   ' No overflow.
Dim bigDec2 As Decimal = 9223372036854775808   ' Overflow.
Dim bigDec3 As Decimal = 9223372036854775808D  ' No overflow.
```

Декларация `bigDec1` не производит переполнения, потому что значение, которое назначено `Long`ему, подпадает под диапазон. Значение `Long` может быть присвоено `Decimal` переменной.

Декларация `bigDec2` для генерирует ошибку переполнения, поскольку значение, назначенное ей, слишком велико для. `Long` Поскольку числовой буквальный не может быть `Long`сначала истолкован как, `Decimal` он не может быть назначен переменной.

Ибо, `bigDec3`буквального `D` типа символ решает проблему, заставляя компилятор `Decimal` интерпретировать буквальное как вместо как `Long`.

## <a name="see-also"></a>См. также раздел

- <xref:System.Decimal?displayProperty=nameWithType>
- <xref:System.Decimal.%23ctor%2A>
- <xref:System.Math.Round%2A?displayProperty=nameWithType>
- [Типы данных](../../../visual-basic/language-reference/data-types/index.md)
- [Тип данных Single](../../../visual-basic/language-reference/data-types/single-data-type.md)
- [Тип данных Double](../../../visual-basic/language-reference/data-types/double-data-type.md)
- [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Сводка по преобразованию](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Эффективное использование типов данных](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
