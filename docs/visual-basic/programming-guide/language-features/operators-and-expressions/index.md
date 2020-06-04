---
title: Операторы и выражения
ms.date: 07/20/2015
helpviewer_keywords:
- operators [Visual Basic], operands
- operators [Visual Basic]
- operands [Visual Basic], definition
- Visual Basic code, operators
- Visual Basic code, expressions
- operands
- expressions [Visual Basic]
ms.assetid: b86f3131-94ee-448f-96cd-79611e028b26
ms.openlocfilehash: dcf52c6200193f81070f323c8037ad82d747942d
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403437"
---
# <a name="operators-and-expressions-in-visual-basic"></a>Операторы и выражения в Visual Basic
*Оператор* представляет собой элемент кода, который выполняет операцию с одним элементом кода или несколькими, содержащими значения. К элементам значений относятся переменные, константы, литералы, свойства, возвращаемые значения из процедур `Function` и `Operator`, а также выражения.  
  
 *Выражение* представляет собой набор элементов значений в сочетании с операторами, результатом которого является новое значение. Операторы работают с элементами значений, выполняя вычисления, сравнения и другие операции.  
  
## <a name="types-of-operators"></a>Типы операторов  
 Visual Basic предоставляет следующие типы операторов:  
  
- [Арифметические операторы](arithmetic-operators.md) выполняют обычные вычисления с числовыми значениями, включая сдвиг их битовых шаблонов.  
  
- [Операторы сравнения](comparison-operators.md) сравнивают два выражения и возвращают значение `Boolean`, соответствующее результату сравнения.  
  
- [Операторы объединения](concatenation-operators.md) соединяют несколько строк в одну.  
  
- [Логические и побитовые операторы в Visual Basic](logical-and-bitwise-operators.md) объединяют `Boolean` или числовые значения и возвращают результат того же типа данных, что и значения.  
  
 Элементы значений, объединенные с оператором, называются *операндами* этого оператора. Операторы, объединенные с элементами значений, формируют выражения. Исключением является оператор присваивания, который образует *инструкцию*. Дополнительные сведения см. в разделе [Инструкции](../statements.md).  
  
## <a name="evaluation-of-expressions"></a>Вычисление выражений  
 Конечный результат выражения представляет собой значение, которое обычно имеет знакомый тип данных, например `Boolean`, `String` или числовой тип.  
  
 Ниже приведены примеры выражений.  
  
 `5 + 4`  
  
 `' The preceding expression evaluates to 9.`  
  
 `15 * System.Math.Sqrt(9) + x`  
  
 `' The preceding expression evaluates to 45 plus the value of x.`  
  
 `"Concat" & "ena" & "tion"`  
  
 `' The preceding expression evaluates to "Concatenation".`  
  
 `763 < 23`  
  
 `' The preceding expression evaluates to False.`  
  
 Несколько операторов могут выполнять действия в одном выражении или инструкции, как показано в следующем примере.  
  
 [!code-vb[VbVbalrOperators#56](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#56)]  
  
 В предыдущем примере Visual Basic выполняет операции в выражении с правой стороны оператора присваивания ( `=` ), а затем присваивает результирующее значение переменной `x` слева. С практической точки зрения в выражение можно объединять сколько угодно операторов, но следует учитывать [приоритет операторов в Visual Basic](../../../language-reference/operators/operator-precedence.md) для получения желаемых результатов.  

## <a name="see-also"></a>См. также раздел

- [Операторы](../../../language-reference/operators/index.md)
- [Эффективное сочетание операторов](efficient-combination-of-operators.md)
- [Операторы](../../../language-reference/statements/index.md)
