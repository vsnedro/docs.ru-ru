---
description: 'Дополнительные сведения о: if... Затем... Оператор else (Visual Basic)'
title: Оператор If…Then…Else
ms.date: 04/16/2018
f1_keywords:
- vb.ElseIf
- vb.Then
- vb.If
- vb.EndIf
helpviewer_keywords:
- ElseIf statement [Visual Basic], If...Then...Else
- Then statement [Visual Basic], If...Then...Else
- control flow [Visual Basic], branching
- execution [Visual Basic], conditional
- TypeOf...Is expression, and If...Then...Else statements
- If...Then...Else statements
- If statement [Visual Basic], If...Then...Else
- If statement [Visual Basic]
- Is operator [Visual Basic], in If...Then...Else statements
- If Operator [Visual Basic]
- branching [Visual Basic], conditional
- If function [Visual Basic], and If...Then...Else statements
- Else statement [Visual Basic]
ms.assetid: 790068a2-1307-4e28-8a72-be5ebda099e9
ms.openlocfilehash: 83850771354b95f0e2d9c1bf1360a61d5264fe2e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99769017"
---
# <a name="ifthenelse-statement-visual-basic"></a>Оператор If...Then...Else (Visual Basic)

Выполняет ту или иную группу операторов в зависимости от значения выражения.

## <a name="syntax"></a>Синтаксис

```vb
' Multiline syntax:
If condition [ Then ]
    [ statements ]
[ ElseIf elseifcondition [ Then ]
    [ elseifstatements ] ]
[ Else
    [ elsestatements ] ]
End If

' Single-line syntax:
If condition Then [ statements ] [ Else [ elsestatements ] ]
```

## <a name="quick-links-to-example-code"></a>Быстрые ссылки на примеры кода

Эта статья содержит несколько примеров, демонстрирующих использование `If` ... `Then` ...`Else` баланс

- [Пример многострочного синтаксиса](#multi-line)
- [Пример вложенного синтаксиса](#nested)
- [Пример однострочного синтаксиса](#single-line)

## <a name="parts"></a>Компоненты

`condition` \
Обязательный элемент. Выражение. Должен иметь значение `True` или `False` , или, или к типу данных, который неявно преобразуется в `Boolean` .

Если выражение является переменной, [допускающей значение NULL](../../programming-guide/language-features/data-types/nullable-value-types.md) `Boolean` , значением которого является [Nothing](../nothing.md), условие обрабатывается так, как если `False` бы выражение было, а `ElseIf` блоки оцениваются, если они существуют, или `Else` блок выполняется, если он существует.

`Then` \
Требуется в однострочном синтаксисе; Необязательный в многострочном синтаксисе.

`statements` \
Необязательный элемент. Один или несколько инструкций, следующих за `If` ... `Then` , которые выполняются, если `condition` имеет значение `True` .

`elseifcondition` \
Требуется, если имеется `ElseIf` . Выражение. Должен иметь значение `True` или `False` , или, или к типу данных, который неявно преобразуется в `Boolean` .

`elseifstatements` \
Необязательный элемент. Один или несколько инструкций, следующих за `ElseIf` ... `Then` , которые выполняются, если `elseifcondition` имеет значение `True` .

`elsestatements` \
Необязательный элемент. Одна или несколько инструкций, выполняемых, если ни Предыдущая, ни `condition` `elseifcondition` выражение не имеет значение `True` .

`End If` \
Завершает многострочную версию `If` ... `Then` ...`Else` блок.

## <a name="remarks"></a>Remarks

### <a name="multiline-syntax"></a>Многострочный синтаксис

Когда `If` ... `Then` ...`Else` , проверяется `condition` . Если `condition` имеет значение `True` , выполняются следующие операторы `Then` . Если `condition` имеет значение `False` , то каждый `ElseIf` оператор (если таковые имеются) вычисляется по порядку. Когда `True` `elseifcondition` обнаруживается, выполняются операторы, непосредственно следующие за ними `ElseIf` . Если `elseifcondition` значение не равно `True` или если нет `ElseIf` инструкций, выполняются следующие операторы `Else` . После выполнения инструкций, указанных после `Then` , `ElseIf` или `Else` , выполнение переходит к следующей инструкции `End If` .

`ElseIf`Предложения и `Else` являются необязательными. Можно использовать любое количество `ElseIf` предложений в `If` ... `Then` ...`Else` , но `ElseIf` после предложения предложение не может быть указано `Else` . `If`...`Then` ...`Else` операторы могут быть вложенными друг в друга.

В многострочном синтаксисе `If` оператор должен быть единственным оператором в первой строке. `ElseIf` `Else` Операторам, и `End If` может предшествовать только метка строки. .. `If` . `Then` ...`Else` блок должен заканчиваться `End If` оператором.

> [!TIP]
> [Выберите... Оператор Case](select-case-statement.md) может оказаться более полезным при вычислении одного выражения, имеющего несколько возможных значений.

### <a name="single-line-syntax"></a>Синтаксис Single-Line

Можно использовать однострочный синтаксис для одного условия с кодом для выполнения, если это так. Однако многострочный синтаксис обеспечивает большую структуру и гибкость и проще в чтении, обслуживании и отладке.

Что следует за `Then` ключевым словом, проверяется, является ли оператор однострочным `If` . Если после `Then` на той же строке появляется нечто, кроме комментария, инструкция рассматривается как однострочный `If` оператор. Если `Then` параметр отсутствует, он должен быть началом многострочного `If` ... `Then` ...`Else`.

В однострочном синтаксисе можно использовать несколько инструкций, выполняемых в результате `If` принятия решения... `Then` Все операторы должны находиться в одной строке и быть разделены двоеточиями.

## <a name="multiline-syntax-example"></a>Пример многострочного синтаксиса

<a name="multi-line"></a>

В следующем примере показано использование многострочного синтаксиса `If` ... `Then` ...`Else` баланс.

[!code-vb[VbVbalrStatements#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#101)]

## <a name="nested-syntax-example"></a>Пример вложенного синтаксиса

<a name="nested"></a>

Следующий пример содержит вложенные `If` ... `Then` ...`Else` инструкции.

[!code-vb[VbVbalrStatements#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#102)]

## <a name="single-line-syntax-example"></a>Пример синтаксиса Single-Line

<a name="single-line"></a> В следующем примере показано использование однострочного синтаксиса.

[!code-vb[VbVbalrStatements#103](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#103)]

## <a name="see-also"></a>См. также

- <xref:Microsoft.VisualBasic.Interaction.Choose%2A>
- <xref:Microsoft.VisualBasic.Interaction.Switch%2A>
- [Директивы #If...Then...#Else](../directives/if-then-else-directives.md)
- [Оператор Select…Case](select-case-statement.md)
- [Вложенные структуры управления](../../programming-guide/language-features/control-flow/nested-control-structures.md)
- [Структуры решений](../../programming-guide/language-features/control-flow/decision-structures.md)
- [Логические и побитовые операторы в Visual Basic](../../programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
- [Оператор If](../operators/if-operator.md)
