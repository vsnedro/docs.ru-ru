---
description: Дополнительные сведения о типе данных Double (Visual Basic)
title: Тип данных Double
ms.date: 07/20/2015
f1_keywords:
- vb.Double
helpviewer_keywords:
- 'identifier type characters [Visual Basic], #'
- trailing zeros
- real numbers
- trailing 0 characters [Visual Basic]
- 0 characters [Visual Basic], trailing
- literal type characters [Visual Basic], R
- data types [Visual Basic], assigning
- Double data type [Visual Basic]
- '# identifier type character'
- double-precision numbers
- floating-point numbers [Visual Basic], Double data type
- R literal type character [Visual Basic]
- zeros, trailing
- Double data type
ms.assetid: 0c5670f7-fcb1-453a-bef1-374730cd38fd
ms.openlocfilehash: ae7b87b392038c67ba47e09d7ca995562bf06c1d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99792223"
---
# <a name="double-data-type-visual-basic"></a>Тип данных Double (Visual Basic)

Содержит подписанные 64-разрядные (8-байтные) числа с плавающей запятой двойной точности, которые находятся в диапазоне от-1.79769313486231570 E + 308 до-4.94065645841246544 E-324 для отрицательных значений и от 4.94065645841246544 E-324 до 1.79769313486231570 E + 308 для положительных значений. Числа двойной точности хранят приближение вещественного числа.

## <a name="remarks"></a>Remarks

`Double`Тип данных предоставляет самые большие и наименьшие возможные величины числа.

Значение по умолчанию для типа `Double` — 0.

## <a name="programming-tips"></a>Советы по программированию

- **Обеспечивают.** При работе с числами с плавающей запятой Помните, что они не всегда имеют точное представление в памяти. Это может привести к непредвиденным результатам некоторых операций, таких как сравнение значений и `Mod` оператор. Дополнительные сведения см. в разделе [Устранение неполадок типов данных](../../programming-guide/language-features/data-types/troubleshooting-data-types.md).

- **Нули в конце.** Типы данных с плавающей запятой не имеют внутреннего представления конечных нулей. Например, они не различаются между 4,2000 и 4,2. Следовательно, конечные нули не отображаются при отображении или печати значений с плавающей запятой.

- **Символы типа.** При добавлении к литералу символа типа литерала `R` производится принудительное приведение литерала к типу данных `Double`. Например, если после целочисленного значения указывается `R` , значение изменяется на `Double` .

  ```vb
  ' Visual Basic expands the 4 in the statement Dim dub As Double = 4R to 4.0:
  Dim dub As Double = 4.0R
  ```

  При добавлении символа идентификатора типа `#` к любому идентификатору производится принудительное приведение этого идентификатора к типу `Double`. В следующем примере переменная `num` типизирована как `Double` :

  ```vb
  Dim num# = 3
  ```

- **Тип Framework.** В .NET Framework данный тип соответствует структуре <xref:System.Double?displayProperty=nameWithType>.

## <a name="see-also"></a>См. также

- <xref:System.Double?displayProperty=nameWithType>
- [Типы данных](index.md)
- [Тип данных Decimal](decimal-data-type.md)
- [Тип данных Single](single-data-type.md)
- [Type Conversion Functions](../functions/type-conversion-functions.md)
- [Сводка по преобразованию](../keywords/conversion-summary.md)
- [Эффективное использование типов данных](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [Устранение неполадок, связанных с типами данных](../../programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Символы типов](../../programming-guide/language-features/data-types/type-characters.md)
