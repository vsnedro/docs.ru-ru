---
description: 'Дополнительные сведения: сравнения значений (Visual Basic)'
title: Сравнения значений
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], comparing values
- Visual Basic code, operators
- Visual Basic code, expressions
- comparison operators [Visual Basic], comparing expressions
- numeric expressions
- operators [Visual Basic], comparison
- expressions [Visual Basic], comparing
ms.assetid: 60da0c76-9458-4afc-97e9-44a7939c064c
ms.openlocfilehash: b5d2228b5bb6be18aecebcd0247a1e29e29df9ec
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "100472713"
---
# <a name="value-comparisons-visual-basic"></a>Сравнение значений (Visual Basic)

Операторы сравнения можно использовать для создания выражений, которые сравнивают значения числовых переменных. Эти выражения возвращают `Boolean` значение в зависимости от того, имеет ли сравнение значение true или false. Ниже приведены примеры таких выражений.  
  
 `45 > 26`  
  
 `26 > 45`  
  
 Первое выражение принимает значение `True` , так как 45 больше 26. Во втором примере вычисляется значение `False` , поскольку 26 не превышает 45.  
  
 Таким образом можно также сравнить числовые выражения. Сравниваемые выражения могут быть сложными выражениями, как показано в следующем примере.  
  
 `x / 45 * (y +17) >= System.Math.Sqrt(z) / (p - (x * 16))`  
  
 Предыдущее сложное выражение включает литералы, переменные и вызовы функций. Выражения на обеих сторонах оператора сравнения оцениваются, а результирующие значения сравниваются с помощью `>=` оператора сравнения. Если значение выражения в левой части больше или равно значению выражения справа, результатом вычисления всего выражения будет `True` ; в противном случае — значение `False` .  
  
 Выражения, которые сравнивают значения, чаще всего используются в `If...Then` конструкциях, как показано в следующем примере.  
  
 [!code-vb[VbVbalrOperators#84](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#84)]  
  
 `=`Знак является оператором сравнения, а также оператором присваивания. При использовании в качестве оператора сравнения он вычисляет, равно ли значение слева значению справа, как показано в следующем примере.  
  
 [!code-vb[VbVbalrOperators#85](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#85)]  
  
 Можно также использовать выражение сравнения в любом месте `Boolean` , где требуется значение, например в `If` `While` операторе,, `Loop` или `ElseIf` , а также при назначении или передаче значения в `Boolean` переменную. В следующем примере значение, возвращаемое выражением сравнения, присваивается `Boolean` переменной.  
  
 [!code-vb[VbVbalrOperators#86](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#86)]  
  
## <a name="see-also"></a>См. также раздел

- [Логические выражения](boolean-expressions.md)
- [Операторы и выражения](index.md)
- [Comparison Operators in Visual Basic](comparison-operators.md)
- [Практическое руководство. Вычисление числовых значений](how-to-calculate-numeric-values.md)
- [Порядок применения операторов в Visual Basic](../../../language-reference/operators/operator-precedence.md)
