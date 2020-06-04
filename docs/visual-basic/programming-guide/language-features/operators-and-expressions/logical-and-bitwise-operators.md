---
title: Логические и побитовые операторы
ms.date: 07/20/2015
helpviewer_keywords:
- short-circuiting
- Boolean expressions
- logical operators [Visual Basic], Boolean expressions
- operators [Visual Basic], logical
- AndAlso operator [Visual Basic]
- Not operator [Visual Basic], Boolean expressions
- Xor operator [Visual Basic], Boolean expressions
- And operator [Visual Basic], logical operators
- logical operators [Visual Basic]
- expressions [Visual Basic], Boolean
- Or operator [Visual Basic], logical operators
- Visual Basic code, operators
- short-circuiting [Visual Basic], logical operators
- logical operators [Visual Basic], short-circuiting
- Visual Basic code, expressions
- logical operators [Visual Basic], binary
- OrElse operator [Visual Basic]
- logical operators [Visual Basic], unary
ms.assetid: ca474e13-567d-4b1d-a18b-301433705e57
ms.openlocfilehash: 19d3511363f19319c2bd8ce872b62c1462b1370f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403412"
---
# <a name="logical-and-bitwise-operators-in-visual-basic"></a>Логические и побитовые операторы в Visual Basic
Логические операторы сравнивают `Boolean` выражения и возвращают `Boolean` результат. `And`Операторы, `Or` , `AndAlso` , `OrElse` и `Xor` являются *двоичными* , поскольку они принимают два операнда, а `Not` оператор является *унарным* , так как он принимает один операнд. Некоторые из этих операторов также могут выполнять побитовые логические операции над целочисленными значениями.  
  
## <a name="unary-logical-operator"></a>Унарный логический оператор  
 [Оператор not](../../../language-reference/operators/not-operator.md) выполняет логическое *отрицание* в `Boolean` выражении. Он возвращает логическое противоположное значение операнда. Если результатом вычисления выражения является `True` , возвращается значение `Not` `False` ; Если результат вычисления выражения равен `False` , возвращается значение `Not` `True` . Это показано в следующем примере.  
  
 [!code-vb[VbVbalrOperators#77](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#77)]  
  
## <a name="binary-logical-operators"></a>Бинарные логические операторы  
 [Оператор and](../../../language-reference/operators/and-operator.md) выполняет логическое *умножение* двух `Boolean` выражений. Если оба выражения имеют значение `True` , `And` возвращается значение `True` . Если хотя бы одно из выражений имеет значение `False` , `And` возвращается значение `False` .  
  
 [Оператор OR](../../../language-reference/operators/or-operator.md) выполняет логическое *сложение* или *Включение* двух `Boolean` выражений. Если любое из выражений принимает значение `True` , или оба значения имеют значение `True` , `Or` возвращается значение `True` . Если ни одно из выражений не имеет значение `True` , `Or` возвращает `False` .  
  
 [Оператор XOR](../../../language-reference/operators/xor-operator.md) выполняет логическое *исключение* для двух `Boolean` выражений. Если только одно выражение имеет значение `True` , но не оба, `Xor` возвращает `True` . Если оба выражения имеют значение `True` или `False` , `Xor` возвращает `False` .  
  
 В следующем примере показаны `And` операторы, `Or` и `Xor` .  
  
 [!code-vb[VbVbalrOperators#78](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#78)]  
  
## <a name="short-circuiting-logical-operations"></a>Сокращенное вычисление логических операций  
 [Оператор AndAlso](../../../language-reference/operators/andalso-operator.md) очень похож на `And` оператор, в котором он также выполняет логическое умножение двух `Boolean` выражений. Основное различие между ними состоит в том, что приводит к `AndAlso` *сокращению* поведения. Если первое выражение в `AndAlso` выражении имеет значение `False` , второе выражение не вычисляется, так как не может изменить окончательный результат и `AndAlso` возвращает `False` .  
  
 Аналогично [оператор OrElse](../../../language-reference/operators/orelse-operator.md) выполняет сокращенное вычисление логического сложения двух `Boolean` выражений. Если первое выражение в `OrElse` выражении имеет значение `True` , второе выражение не вычисляется, так как не может изменить окончательный результат и `OrElse` возвращает `True` .  
  
### <a name="short-circuiting-trade-offs"></a>Сокращенное вычисление компромиссов  
 Сокращенное вычисление может повысить производительность, не вычисляя выражение, которое не может изменить результат логической операции. Однако если это выражение выполняет дополнительные действия, сокращенное вычисление пропускает эти действия. Например, если выражение содержит вызов `Function` процедуры, эта процедура не вызывается, если выражение сокращено, а любой дополнительный код, содержащийся в, `Function` не выполняется. Таким образом, функция может выполняться только иногда и может быть некорректно проверена. Или логика программы может зависеть от кода в `Function` .  
  
 В следующем примере показана разница между `And` , `Or` и их сокращенными аналогами.  
  
 [!code-vb[VbVbalrOperators#81](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#81)]  
  
 [!code-vb[VbVbalrOperators#80](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#80)]  
  
 [!code-vb[VbVbalrOperators#79](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#79)]  
  
 Обратите внимание, что в предыдущем примере некоторый важный код внутри не `checkIfValid()` выполняется при сокращенном вызове. Первый `If` оператор вызывает `checkIfValid()` `12 > 45` , хотя возвращает `False` , так как `And` не выполняет сокращенное вычисление. Вторая `If` инструкция не вызывает метод `checkIfValid()` , поскольку при `12 > 45` возврате `False` происходит `AndAlso` сокращенное значение второго выражения. Третья `If` инструкция вызывает `checkIfValid()` , даже если `12 < 45` возвращает `True` , так как `Or` не выполняет сокращенное вычисление. Четвертый `If` оператор не вызывает метод `checkIfValid()` , поскольку при `12 < 45` возврате `True` происходит `OrElse` сокращенное значение второго выражения.  
  
## <a name="bitwise-operations"></a>Битовые операции  
 Побитовые операции оценивают два целочисленных значения в форме binary (основание 2). Они сравнивают биты в соответствующих позициях и затем присваивают значения на основе сравнения. В следующем примере показан `And` оператор.  
  
 [!code-vb[VbVbalrConcepts#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConcepts/VB/Class1.vb#2)]  
  
 В предыдущем примере задается значение `x` 1. Это происходит по следующим причинам.  
  
- Значения рассматриваются как двоичные:  
  
     3 в двоичном формате = 011  
  
     5 в двоичном формате = 101  
  
- `And`Оператор сравнивает двоичные представления, по одной двоичной позиции (бит) за раз. Если оба бита в заданной позиции равны 1, то в результате в эту точку помещается 1. Если любой из битов равен 0, то в результат помещается 0. В предыдущем примере это работает следующим образом:  
  
     011 (3 в двоичной форме)  
  
     101 (5 в двоичной форме)  
  
     001 (результат в двоичной форме)  
  
- Результат считается десятичным. Значение 001 является двоичным представлением 1, то есть `x` = 1.  
  
 Побитовая `Or` Операция аналогична, за исключением того, что 1 назначается биту результата, если один или оба сравниваемых бита равны 1. `Xor`присваивает значение 1 результирующему биту, если ровно один из сравниваемых битов (не оба) равен 1. `Not`принимает один операнд и инвертирует все биты, включая бит знака, и присваивает это значение результату. Это означает, что для положительных чисел со знаком `Not` всегда возвращает отрицательное значение, а для отрицательных чисел `Not` всегда возвращает положительное или нулевое значение.  
  
 `AndAlso`Операторы и `OrElse` не поддерживают побитовые операции.  
  
> [!NOTE]
> Битовые операции могут выполняться только с целыми типами. Перед выполнением побитовой операции значения с плавающей запятой необходимо преобразовать в целочисленные типы.  
  
## <a name="see-also"></a>См. также раздел

- [Логические (побитовые) операторы (Visual Basic)](../../../language-reference/operators/logical-bitwise-operators.md)
- [Логические выражения](boolean-expressions.md)
- [Арифметические операторы в Visual Basic](arithmetic-operators.md)
- [Comparison Operators in Visual Basic](comparison-operators.md)
- [Операторы объединения в Visual Basic](concatenation-operators.md)
- [Эффективное сочетание операторов](efficient-combination-of-operators.md)
