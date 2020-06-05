---
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
ms.openlocfilehash: 0884b71c24742286e695e720add9d00dd4bfe52b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404593"
---
# <a name="ifthenelse-statement-visual-basic"></a><span data-ttu-id="63dd2-102">Оператор If...Then...Else (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="63dd2-102">If...Then...Else Statement (Visual Basic)</span></span>

<span data-ttu-id="63dd2-103">Выполняет ту или иную группу операторов в зависимости от значения выражения.</span><span class="sxs-lookup"><span data-stu-id="63dd2-103">Conditionally executes a group of statements, depending on the value of an expression.</span></span>

## <a name="syntax"></a><span data-ttu-id="63dd2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="63dd2-104">Syntax</span></span>

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

## <a name="quick-links-to-example-code"></a><span data-ttu-id="63dd2-105">Быстрые ссылки на примеры кода</span><span class="sxs-lookup"><span data-stu-id="63dd2-105">Quick links to example code</span></span>

<span data-ttu-id="63dd2-106">Эта статья содержит несколько примеров, демонстрирующих использование `If` ... `Then` ...`Else` баланс</span><span class="sxs-lookup"><span data-stu-id="63dd2-106">This article includes several examples that illustrate uses of the `If`...`Then`...`Else` statement:</span></span>

- [<span data-ttu-id="63dd2-107">Пример многострочного синтаксиса</span><span class="sxs-lookup"><span data-stu-id="63dd2-107">Multiline syntax example</span></span>](#multi-line)
- [<span data-ttu-id="63dd2-108">Пример вложенного синтаксиса</span><span class="sxs-lookup"><span data-stu-id="63dd2-108">Nested syntax example</span></span>](#nested)
- [<span data-ttu-id="63dd2-109">Пример однострочного синтаксиса</span><span class="sxs-lookup"><span data-stu-id="63dd2-109">Single-line syntax example</span></span>](#single-line)

## <a name="parts"></a><span data-ttu-id="63dd2-110">Компоненты</span><span class="sxs-lookup"><span data-stu-id="63dd2-110">Parts</span></span>

`condition` \
<span data-ttu-id="63dd2-111">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="63dd2-111">Required.</span></span> <span data-ttu-id="63dd2-112">Выражение.</span><span class="sxs-lookup"><span data-stu-id="63dd2-112">Expression.</span></span> <span data-ttu-id="63dd2-113">Должен иметь значение `True` или `False` , или, или к типу данных, который неявно преобразуется в `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="63dd2-113">Must evaluate to `True` or `False`, or to a data type that is implicitly convertible to `Boolean`.</span></span>

<span data-ttu-id="63dd2-114">Если выражение является переменной, [допускающей значение NULL](../../programming-guide/language-features/data-types/nullable-value-types.md) `Boolean` , значением которого является [Nothing](../nothing.md), условие обрабатывается так, как если `False` бы выражение было, а `ElseIf` блоки оцениваются, если они существуют, или `Else` блок выполняется, если он существует.</span><span class="sxs-lookup"><span data-stu-id="63dd2-114">If the expression is a [Nullable](../../programming-guide/language-features/data-types/nullable-value-types.md) `Boolean` variable that evaluates to [Nothing](../nothing.md), the condition is treated as if the expression is `False`, and the `ElseIf` blocks are evaluated if they exist, or the `Else` block is executed if it exists.</span></span>

`Then` \
<span data-ttu-id="63dd2-115">Требуется в однострочном синтаксисе; Необязательный в многострочном синтаксисе.</span><span class="sxs-lookup"><span data-stu-id="63dd2-115">Required in the single-line syntax; optional in the multiline syntax.</span></span>

`statements` \
<span data-ttu-id="63dd2-116">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="63dd2-116">Optional.</span></span> <span data-ttu-id="63dd2-117">Один или несколько инструкций, следующих за `If` ... `Then` , которые выполняются, если `condition` имеет значение `True` .</span><span class="sxs-lookup"><span data-stu-id="63dd2-117">One or more statements following `If`...`Then` that are executed if `condition` evaluates to `True`.</span></span>

`elseifcondition` \
<span data-ttu-id="63dd2-118">Требуется, если имеется `ElseIf` .</span><span class="sxs-lookup"><span data-stu-id="63dd2-118">Required if `ElseIf` is present.</span></span> <span data-ttu-id="63dd2-119">Выражение.</span><span class="sxs-lookup"><span data-stu-id="63dd2-119">Expression.</span></span> <span data-ttu-id="63dd2-120">Должен иметь значение `True` или `False` , или, или к типу данных, который неявно преобразуется в `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="63dd2-120">Must evaluate to `True` or `False`, or to a data type that is implicitly convertible to `Boolean`.</span></span>

`elseifstatements` \
<span data-ttu-id="63dd2-121">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="63dd2-121">Optional.</span></span> <span data-ttu-id="63dd2-122">Один или несколько инструкций, следующих за `ElseIf` ... `Then` , которые выполняются, если `elseifcondition` имеет значение `True` .</span><span class="sxs-lookup"><span data-stu-id="63dd2-122">One or more statements following `ElseIf`...`Then` that are executed if `elseifcondition` evaluates to `True`.</span></span>

`elsestatements` \
<span data-ttu-id="63dd2-123">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="63dd2-123">Optional.</span></span> <span data-ttu-id="63dd2-124">Одна или несколько инструкций, выполняемых, если ни Предыдущая, ни `condition` `elseifcondition` выражение не имеет значение `True` .</span><span class="sxs-lookup"><span data-stu-id="63dd2-124">One or more statements that are executed if no previous `condition` or `elseifcondition` expression evaluates to `True`.</span></span>

`End If` \
<span data-ttu-id="63dd2-125">Завершает многострочную версию `If` ... `Then` ...`Else` блок.</span><span class="sxs-lookup"><span data-stu-id="63dd2-125">Terminates the multiline version of `If`...`Then`...`Else` block.</span></span>

## <a name="remarks"></a><span data-ttu-id="63dd2-126">Комментарии</span><span class="sxs-lookup"><span data-stu-id="63dd2-126">Remarks</span></span>

### <a name="multiline-syntax"></a><span data-ttu-id="63dd2-127">Многострочный синтаксис</span><span class="sxs-lookup"><span data-stu-id="63dd2-127">Multiline syntax</span></span>

<span data-ttu-id="63dd2-128">Когда `If` ... `Then` ...`Else` , проверяется `condition` .</span><span class="sxs-lookup"><span data-stu-id="63dd2-128">When an `If`...`Then`...`Else` statement is encountered, `condition` is tested.</span></span> <span data-ttu-id="63dd2-129">Если `condition` имеет значение `True` , выполняются следующие операторы `Then` .</span><span class="sxs-lookup"><span data-stu-id="63dd2-129">If `condition` is `True`, the statements following `Then` are executed.</span></span> <span data-ttu-id="63dd2-130">Если `condition` имеет значение `False` , то каждый `ElseIf` оператор (если таковые имеются) вычисляется по порядку.</span><span class="sxs-lookup"><span data-stu-id="63dd2-130">If `condition` is `False`, each `ElseIf` statement (if there are any) is evaluated in order.</span></span> <span data-ttu-id="63dd2-131">Когда `True` `elseifcondition` обнаруживается, выполняются операторы, непосредственно следующие за ними `ElseIf` .</span><span class="sxs-lookup"><span data-stu-id="63dd2-131">When a `True` `elseifcondition` is found, the statements immediately following the associated `ElseIf` are executed.</span></span> <span data-ttu-id="63dd2-132">Если `elseifcondition` значение не равно `True` или если нет `ElseIf` инструкций, выполняются следующие операторы `Else` .</span><span class="sxs-lookup"><span data-stu-id="63dd2-132">If no `elseifcondition` evaluates to `True`, or if there are no `ElseIf` statements, the statements following `Else` are executed.</span></span> <span data-ttu-id="63dd2-133">После выполнения инструкций, указанных после `Then` , `ElseIf` или `Else` , выполнение переходит к следующей инструкции `End If` .</span><span class="sxs-lookup"><span data-stu-id="63dd2-133">After executing the statements following `Then`, `ElseIf`, or `Else`, execution continues with the statement following `End If`.</span></span>

<span data-ttu-id="63dd2-134">`ElseIf`Предложения и `Else` являются необязательными.</span><span class="sxs-lookup"><span data-stu-id="63dd2-134">The `ElseIf` and `Else` clauses are both optional.</span></span> <span data-ttu-id="63dd2-135">Можно использовать любое количество `ElseIf` предложений в `If` ... `Then` ...`Else` , но `ElseIf` после предложения предложение не может быть указано `Else` .</span><span class="sxs-lookup"><span data-stu-id="63dd2-135">You can have as many `ElseIf` clauses as you want in an `If`...`Then`...`Else` statement, but no `ElseIf` clause can appear after an `Else` clause.</span></span> <span data-ttu-id="63dd2-136">`If`...`Then` ...`Else` операторы могут быть вложенными друг в друга.</span><span class="sxs-lookup"><span data-stu-id="63dd2-136">`If`...`Then`...`Else` statements can be nested within each other.</span></span>

<span data-ttu-id="63dd2-137">В многострочном синтаксисе `If` оператор должен быть единственным оператором в первой строке.</span><span class="sxs-lookup"><span data-stu-id="63dd2-137">In the multiline syntax, the `If` statement must be the only statement on the first line.</span></span> <span data-ttu-id="63dd2-138">`ElseIf` `Else` Операторам, и `End If` может предшествовать только метка строки.</span><span class="sxs-lookup"><span data-stu-id="63dd2-138">The `ElseIf`, `Else`, and `End If` statements can be preceded only by a line label.</span></span> <span data-ttu-id="63dd2-139">.. `If` . `Then` ...`Else` блок должен заканчиваться `End If` оператором.</span><span class="sxs-lookup"><span data-stu-id="63dd2-139">The `If`...`Then`...`Else` block must end with an `End If` statement.</span></span>

> [!TIP]
> <span data-ttu-id="63dd2-140">[Выберите... Оператор Case](select-case-statement.md) может оказаться более полезным при вычислении одного выражения, имеющего несколько возможных значений.</span><span class="sxs-lookup"><span data-stu-id="63dd2-140">The [Select...Case Statement](select-case-statement.md) might be more useful when you evaluate a single expression that has several possible values.</span></span>

### <a name="single-line-syntax"></a><span data-ttu-id="63dd2-141">Однострочный синтаксис</span><span class="sxs-lookup"><span data-stu-id="63dd2-141">Single-Line syntax</span></span>

<span data-ttu-id="63dd2-142">Можно использовать однострочный синтаксис для одного условия с кодом для выполнения, если это так.</span><span class="sxs-lookup"><span data-stu-id="63dd2-142">You can use the single-line syntax for a single condition with code to execute if it's true.</span></span> <span data-ttu-id="63dd2-143">Однако многострочный синтаксис обеспечивает большую структуру и гибкость и проще в чтении, обслуживании и отладке.</span><span class="sxs-lookup"><span data-stu-id="63dd2-143">However, the multiple-line syntax provides more structure and flexibility and is easier to read, maintain, and debug.</span></span>

<span data-ttu-id="63dd2-144">Что следует за `Then` ключевым словом, проверяется, является ли оператор однострочным `If` .</span><span class="sxs-lookup"><span data-stu-id="63dd2-144">What follows the `Then` keyword is examined to determine whether a statement is a single-line `If`.</span></span> <span data-ttu-id="63dd2-145">Если после `Then` на той же строке появляется нечто, кроме комментария, инструкция рассматривается как однострочный `If` оператор.</span><span class="sxs-lookup"><span data-stu-id="63dd2-145">If anything other than a comment appears after `Then` on the same line, the statement is treated as a single-line `If` statement.</span></span> <span data-ttu-id="63dd2-146">Если `Then` параметр отсутствует, он должен быть началом многострочного `If` ... `Then` ...`Else`.</span><span class="sxs-lookup"><span data-stu-id="63dd2-146">If `Then` is absent, it must be the start of a multiple-line `If`...`Then`...`Else`.</span></span>

<span data-ttu-id="63dd2-147">В однострочном синтаксисе можно использовать несколько инструкций, выполняемых в результате `If` принятия решения... `Then`</span><span class="sxs-lookup"><span data-stu-id="63dd2-147">In the single-line syntax, you can have multiple statements executed as the result of an `If`...`Then` decision.</span></span> <span data-ttu-id="63dd2-148">Все операторы должны находиться в одной строке и быть разделены двоеточиями.</span><span class="sxs-lookup"><span data-stu-id="63dd2-148">All statements must be on the same line and be separated by colons.</span></span>

## <a name="multiline-syntax-example"></a><span data-ttu-id="63dd2-149">Пример многострочного синтаксиса</span><span class="sxs-lookup"><span data-stu-id="63dd2-149">Multiline syntax example</span></span>

<a name="multi-line"></a>

<span data-ttu-id="63dd2-150">В следующем примере показано использование многострочного синтаксиса `If` ... `Then` ...`Else` баланс.</span><span class="sxs-lookup"><span data-stu-id="63dd2-150">The following example illustrates the use of the multiline syntax of the `If`...`Then`...`Else` statement.</span></span>

[!code-vb[VbVbalrStatements#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#101)]

## <a name="nested-syntax-example"></a><span data-ttu-id="63dd2-151">Пример вложенного синтаксиса</span><span class="sxs-lookup"><span data-stu-id="63dd2-151">Nested syntax example</span></span>

<a name="nested"></a>

<span data-ttu-id="63dd2-152">Следующий пример содержит вложенные `If` ... `Then` ...`Else` инструкции.</span><span class="sxs-lookup"><span data-stu-id="63dd2-152">The following example contains nested `If`...`Then`...`Else` statements.</span></span>

[!code-vb[VbVbalrStatements#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#102)]

## <a name="single-line-syntax-example"></a><span data-ttu-id="63dd2-153">Пример однострочного синтаксиса</span><span class="sxs-lookup"><span data-stu-id="63dd2-153">Single-Line syntax example</span></span>

<a name="single-line"></a><span data-ttu-id="63dd2-154">В следующем примере показано использование однострочного синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="63dd2-154">The following example illustrates the use of the single-line syntax.</span></span>

[!code-vb[VbVbalrStatements#103](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#103)]

## <a name="see-also"></a><span data-ttu-id="63dd2-155">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="63dd2-155">See also</span></span>

- <xref:Microsoft.VisualBasic.Interaction.Choose%2A>
- <xref:Microsoft.VisualBasic.Interaction.Switch%2A>
- [<span data-ttu-id="63dd2-156">Директивы #If...Then...#Else</span><span class="sxs-lookup"><span data-stu-id="63dd2-156">#If...Then...#Else Directives</span></span>](../directives/if-then-else-directives.md)
- [<span data-ttu-id="63dd2-157">Оператор Select…Case</span><span class="sxs-lookup"><span data-stu-id="63dd2-157">Select...Case Statement</span></span>](select-case-statement.md)
- [<span data-ttu-id="63dd2-158">Вложенные структуры управления</span><span class="sxs-lookup"><span data-stu-id="63dd2-158">Nested Control Structures</span></span>](../../programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="63dd2-159">Структуры решений</span><span class="sxs-lookup"><span data-stu-id="63dd2-159">Decision Structures</span></span>](../../programming-guide/language-features/control-flow/decision-structures.md)
- [<span data-ttu-id="63dd2-160">Логические и побитовые операторы в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="63dd2-160">Logical and Bitwise Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
- [<span data-ttu-id="63dd2-161">Оператор If</span><span class="sxs-lookup"><span data-stu-id="63dd2-161">If Operator</span></span>](../operators/if-operator.md)
