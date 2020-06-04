---
title: Логические выражения
ms.date: 07/20/2015
helpviewer_keywords:
- short-circuiting
- Boolean expressions
- logical operators [Visual Basic], Boolean expressions
- expressions [Visual Basic], Boolean
- expression evaluation [Visual Basic], Boolean expressions
- operators [Visual Basic], short-circuiting
- Visual Basic code, operators
- short-circuit evaluation
- logical operators [Visual Basic], short-circuiting
- operators [Visual Basic], Boolean
- Visual Basic code, expressions
ms.assetid: d3d90406-55c8-4404-8143-50fd7f0d0d1a
ms.openlocfilehash: 8d34eb4c8b14bb4754f2a3cf5b6f9a7601aa4662
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84388962"
---
# <a name="boolean-expressions-visual-basic"></a>Логические выражения (Visual Basic)
*Логическое выражение* — это выражение, результатом вычисления которого является значение [логического типа данных](../../../language-reference/data-types/boolean-data-type.md): `True` или `False` . `Boolean`выражения могут принимать несколько форм. Простейшим является прямое сравнение значения `Boolean` переменной с `Boolean` литералом, как показано в следующем примере.  
  
 [!code-vb[VbVbalrOperators#87](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#87)]  
  
## <a name="two-meanings-of-the--operator"></a>Два значения оператора =  
 Обратите внимание, что оператор присваивания `newCustomer = True` выглядит так же, как выражение в предыдущем примере, но выполняет другую функцию и используется по-разному. В предыдущем примере выражение `newCustomer = True` представляет логическое значение, а `=` знак интерпретируется как оператор сравнения. В изолированном операторе `=` знак интерпретируется как оператор присваивания и присваивает значение справа переменной слева. Это показано в следующем примере.  
  
 [!code-vb[VbVbalrOperators#88](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#88)]  
  
 Дополнительные сведения см. в разделе [сравнения значений](value-comparisons.md) и [инструкции](../../../language-reference/statements/index.md).  
  
## <a name="comparison-operators"></a>Операторы сравнения  
 Операторы сравнения, такие как `=` ,, `<` ,, `>` `<>` `<=` , и `>=` создают логические выражения путем сравнения выражения с левой стороны оператора с выражением в правой части оператора и вычисления результата в виде `True` или `False` . Это показано в следующем примере.  
  
 `42 < 81`  
  
 Поскольку 42 меньше 81, логическое выражение в предыдущем примере вычисляется как `True` . Дополнительные сведения об этом типе выражения см. в разделе [сравнения значений](value-comparisons.md).  
  
### <a name="comparison-operators-combined-with-logical-operators"></a>Операторы сравнения в сочетании с логическими операторами  
 Выражения сравнения можно комбинировать с помощью логических операторов для создания более сложных логических выражений. В следующем примере показано использование операторов сравнения в сочетании с логическим оператором.  
  
 `x > y And x < 1000`  
  
 В предыдущем примере значение общего выражения зависит от значений выражений на каждой стороне `And` оператора. Если оба выражения имеют значение `True` , то общее выражение принимает значение `True` . Если любое из выражений имеет значение `False` , результатом вычисления всего выражения будет значение `False` .  
  
## <a name="short-circuiting-operators"></a>Операторы сокращенного вычисления  
 Логические операторы `AndAlso` и `OrElse` демонстрируют поведение, называемое *сокращенным вычислением*. Оператор сокращенного вычисления сначала вычисляет левый операнд. Если левый операнд определяет значение всего выражения, выполнение программы продолжается без вычисления правого выражения. Это показано в следующем примере.  
  
 [!code-vb[VbVbalrOperators#89](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#89)]  
  
 В предыдущем примере оператор вычисляет левое выражение `45 < 12` . Так как левое выражение принимает значение `False` , все логическое выражение должно иметь значение `False` . Таким результатом, выполнение программы пропускает выполнение кода в `If` блоке без вычисления правого выражения `testFunction(3)` . Этот пример не вызывается `testFunction()` , поскольку левое выражение фалсифиес все выражение.  
  
 Аналогично, если левое выражение в логическом выражении с помощью метода `OrElse` Evaluate имеет значение `True` , выполнение переходит к следующей строке кода без вычисления правого выражения, поскольку левое выражение уже проверило все выражение.  
  
### <a name="comparison-with-non-short-circuiting-operators"></a>Сравнение с операторами, не являющимися сокращенными  
 Напротив, обе стороны логического оператора оцениваются при использовании логических операторов `And` и `Or` . Это показано в следующем примере.  
  
 [!code-vb[VbVbalrOperators#90](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#90)]  
  
 В предыдущем примере вызывается, несмотря на то, `testFunction()` что левое выражение имеет значение `False` .  
  
## <a name="parenthetical-expressions"></a>Выражения в скобках  
 Можно использовать круглые скобки для управления порядком вычисления логических выражений. Выражения, заключенные в круглые скобки, сначала оцениваются. Для нескольких уровней вложенности приоритет предоставляется самым глубоким вложенным выражениям. В круглых скобках вычисление продолжается в соответствии с правилами приоритета операторов. Дополнительные сведения см. [в разделе приоритет операторов в Visual Basic](../../../language-reference/operators/operator-precedence.md).  
  
## <a name="see-also"></a>См. также раздел

- [Логические и побитовые операторы в Visual Basic](logical-and-bitwise-operators.md)
- [Сравнения значений](value-comparisons.md)
- [Операторы](../statements.md)
- [Операторы сравнения](../../../language-reference/operators/comparison-operators.md)
- [Эффективное сочетание операторов](efficient-combination-of-operators.md)
- [Порядок применения операторов в Visual Basic](../../../language-reference/operators/operator-precedence.md)
- [Логический тип данных](../../../language-reference/data-types/boolean-data-type.md)
