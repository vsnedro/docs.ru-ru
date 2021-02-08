---
description: Дополнительные сведения о типе данных Decimal (Visual Basic)
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
ms.openlocfilehash: 5806041e7737b8fe0f1c7ffa63f6cbadcbf92e42
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99792236"
---
# <a name="decimal-data-type-visual-basic"></a>Тип данных Decimal (Visual Basic)

Содержит 128-разрядные (16-байтные) значения со знаком, представляющие 96-разрядные (12-байтные) целые числа с переменной степенью, кратной 10. Коэффициент масштабирования определяет количество цифр справа от десятичной запятой. Он находится в диапазоне от 0 до 28. С масштабом 0 (без десятичных знаков) максимально возможное значение — +/-79,228,162,514,264,337,593,543,950,335 (+/-7.9228162514264337593543950335E + 28). С 28 десятичными разрядами максимальное значение — +/-7.9228162514264337593543950335, а наименьшее ненулевое значение — +/-0,0000000000000000000000000001 (+/-1E-28).

## <a name="remarks"></a>Remarks

`Decimal`Тип данных предоставляет наибольшее количество значащих цифр для числа. Он поддерживает до 29 значащих цифр и может представлять значения, превышающие 7,9228 x 10 ^ 28. Он особенно подходит для вычислений, например финансовых, которые нуждаются в большом количестве цифр, но не могут допускать ошибки округления.

Значение по умолчанию для типа `Decimal` — 0.

## <a name="programming-tips"></a>Советы по программированию

- **Обеспечивают.** `Decimal` не является типом данных с плавающей запятой. `Decimal`Структура содержит двоичное целочисленное значение, а также бит знака и целочисленный коэффициент масштабирования, указывающий, какая часть значения является десятичной дробью. По этой причине `Decimal` числа имеют более точное представление в памяти, чем типы с плавающей запятой ( `Single` и `Double` ).

- **Производительность.** `Decimal`Тип данных является самым медленным из всех числовых типов. Перед выбором типа данных следует оценить важность точности в соответствии с производительностью.

- **Расширяющие.** `Decimal`Тип данных расширяется до `Single` или `Double` . Это означает, что можно преобразовать `Decimal` в любой из этих типов без возникновения <xref:System.OverflowException?displayProperty=nameWithType> ошибки.

- **Нули в конце.** Visual Basic не сохраняет конечные нули в `Decimal` литерале. Однако `Decimal` переменная сохраняет все конечные нули, полученные при вычислении. Это показано в следующем примере.

  ```vb
  Dim d1, d2, d3, d4 As Decimal
  d1 = 2.375D
  d2 = 1.625D
  d3 = d1 + d2
  d4 = 4.000D
  MsgBox("d1 = " & CStr(d1) & ", d2 = " & CStr(d2) &
        ", d3 = " & CStr(d3) & ", d4 = " & CStr(d4))
  ```

  Выходные данные `MsgBox` в предыдущем примере имеют следующий вид:

  ```console
  d1 = 2.375, d2 = 1.625, d3 = 4.000, d4 = 4
  ```

- **Символы типа.** При добавлении к литералу символа типа литерала `D` производится принудительное приведение литерала к типу данных `Decimal`. При добавлении символа идентификатора типа `@` к любому идентификатору производится принудительное приведение этого идентификатора к типу `Decimal`.

- **Тип Framework.** В .NET Framework данный тип соответствует структуре <xref:System.Decimal?displayProperty=nameWithType>.

## <a name="range"></a>Диапазон

 Может потребоваться использовать `D` символ типа, чтобы присвоить большое значение `Decimal` переменной или константе. Это требование обусловлено тем, что компилятор интерпретирует литерал как `Long` , если символ типа литерала не соответствует литералу, как показано в следующем примере.

```vb
Dim bigDec1 As Decimal = 9223372036854775807   ' No overflow.
Dim bigDec2 As Decimal = 9223372036854775808   ' Overflow.
Dim bigDec3 As Decimal = 9223372036854775808D  ' No overflow.
```

Объявление для `bigDec1` не создает переполнение, так как присваиваемое ему значение попадает в диапазон для `Long` . `Long`Значение может быть присвоено `Decimal` переменной.

Объявление для `bigDec2` создает ошибку переполнения, так как присвоенное ей значение слишком велико для `Long` . Поскольку числовой литерал не может быть интерпретирован как `Long` , он не может быть назначен `Decimal` переменной.

Для `bigDec3` символ типа литерала `D` решает проблему, вызывая компилятору интерпретировать литерал как, `Decimal` а не как `Long` .

## <a name="see-also"></a>См. также

- <xref:System.Decimal?displayProperty=nameWithType>
- <xref:System.Decimal.%23ctor%2A>
- <xref:System.Math.Round%2A?displayProperty=nameWithType>
- [Типы данных](index.md)
- [Тип данных Single](single-data-type.md)
- [Тип данных Double](double-data-type.md)
- [Type Conversion Functions](../functions/type-conversion-functions.md)
- [Сводка по преобразованию](../keywords/conversion-summary.md)
- [Эффективное использование типов данных](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
