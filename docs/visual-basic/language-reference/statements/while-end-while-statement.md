---
title: Оператор While…End While
ms.date: 07/20/2015
f1_keywords:
- vb.While
- vb.While...EndWhile
helpviewer_keywords:
- While statement [Visual Basic], While...End While
- While statement [Visual Basic]
- While...End While statements [Visual Basic]
ms.assetid: b931d1ce-e8ed-44d8-a13d-92a4f5458a1e
ms.openlocfilehash: e3ab95f43e101a9ad8abe6fa61b94ae7542e409c
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90869480"
---
# <a name="whileend-while-statement-visual-basic"></a><span data-ttu-id="5bfd4-102">Оператор While... End While (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5bfd4-102">While...End While Statement (Visual Basic)</span></span>

<span data-ttu-id="5bfd4-103">Выполняет последовательность операторов, если заданное условие имеет значение `True` .</span><span class="sxs-lookup"><span data-stu-id="5bfd4-103">Runs a series of statements as long as a given condition is `True`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5bfd4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5bfd4-104">Syntax</span></span>  
  
```vb  
While condition  
    [ statements ]  
    [ Continue While ]  
    [ statements ]  
    [ Exit While ]  
    [ statements ]  
End While  
```  
  
## <a name="parts"></a><span data-ttu-id="5bfd4-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="5bfd4-105">Parts</span></span>  
  
|<span data-ttu-id="5bfd4-106">Термин</span><span class="sxs-lookup"><span data-stu-id="5bfd4-106">Term</span></span>|<span data-ttu-id="5bfd4-107">Определение</span><span class="sxs-lookup"><span data-stu-id="5bfd4-107">Definition</span></span>|  
|---|---|  
|`condition`|<span data-ttu-id="5bfd4-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="5bfd4-108">Required.</span></span> <span data-ttu-id="5bfd4-109">Выражение `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="5bfd4-109">`Boolean` expression.</span></span> <span data-ttu-id="5bfd4-110">Если `condition` имеет значение `Nothing` , Visual Basic обрабатывает его как `False` .</span><span class="sxs-lookup"><span data-stu-id="5bfd4-110">If `condition` is `Nothing`, Visual Basic treats it as `False`.</span></span>|  
|`statements`|<span data-ttu-id="5bfd4-111">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="5bfd4-111">Optional.</span></span> <span data-ttu-id="5bfd4-112">Один или несколько следующих инструкций `While` , которые выполняются каждый раз, `condition` — `True` .</span><span class="sxs-lookup"><span data-stu-id="5bfd4-112">One or more statements following `While`, which run every time `condition` is `True`.</span></span>|  
|`Continue While`|<span data-ttu-id="5bfd4-113">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="5bfd4-113">Optional.</span></span> <span data-ttu-id="5bfd4-114">Передает управление следующей итерации `While` блока.</span><span class="sxs-lookup"><span data-stu-id="5bfd4-114">Transfers control to the next iteration of the `While` block.</span></span>|  
|`Exit While`|<span data-ttu-id="5bfd4-115">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="5bfd4-115">Optional.</span></span> <span data-ttu-id="5bfd4-116">Передает управление за пределы `While` блока.</span><span class="sxs-lookup"><span data-stu-id="5bfd4-116">Transfers control out of the `While` block.</span></span>|  
|`End While`|<span data-ttu-id="5bfd4-117">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="5bfd4-117">Required.</span></span> <span data-ttu-id="5bfd4-118">Завершает определение блока `While`.</span><span class="sxs-lookup"><span data-stu-id="5bfd4-118">Terminates the definition of the `While` block.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5bfd4-119">Remarks</span><span class="sxs-lookup"><span data-stu-id="5bfd4-119">Remarks</span></span>  

 <span data-ttu-id="5bfd4-120">Используйте `While...End While` структуру, если необходимо повторить набор инструкций неопределенное количество раз, если условие остается `True` .</span><span class="sxs-lookup"><span data-stu-id="5bfd4-120">Use a `While...End While` structure when you want to repeat a set of statements an indefinite number of times, as long as a condition remains `True`.</span></span> <span data-ttu-id="5bfd4-121">Если вы хотите обеспечить большую гибкость при тестировании условия или результата тестирования, вы можете предпочесть оператору [Do... Loop, инструкция](do-loop-statement.md).</span><span class="sxs-lookup"><span data-stu-id="5bfd4-121">If you want more flexibility with where you test the condition or what result you test it for, you might prefer the [Do...Loop Statement](do-loop-statement.md).</span></span> <span data-ttu-id="5bfd4-122">Если нужно повторить инструкции заданное число раз, то [для... ](for-next-statement.md) Обычно лучше подходит следующий оператор.</span><span class="sxs-lookup"><span data-stu-id="5bfd4-122">If you want to repeat the statements a set number of times, the [For...Next Statement](for-next-statement.md) is usually a better choice.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5bfd4-123">`While`Ключевое слово также используется в [инструкции Do... Оператор Loop](do-loop-statement.md), [предложение Skip While](../queries/skip-while-clause.md) и [предложение Take While](../queries/take-while-clause.md).</span><span class="sxs-lookup"><span data-stu-id="5bfd4-123">The `While` keyword is also used in the [Do...Loop Statement](do-loop-statement.md), the [Skip While Clause](../queries/skip-while-clause.md) and the [Take While Clause](../queries/take-while-clause.md).</span></span>  
  
 <span data-ttu-id="5bfd4-124">Если `condition` имеет значение `True` , все `statements` выполняется до тех пор, пока `End While` не будет обнаружен оператор.</span><span class="sxs-lookup"><span data-stu-id="5bfd4-124">If `condition` is `True`, all of the `statements` run until the `End While` statement is encountered.</span></span> <span data-ttu-id="5bfd4-125">Затем элемент управления возвращается в `While` инструкцию и `condition` снова проверяется.</span><span class="sxs-lookup"><span data-stu-id="5bfd4-125">Control then returns to the `While` statement, and `condition` is again checked.</span></span> <span data-ttu-id="5bfd4-126">Если `condition` по-прежнему `True` , процесс повторяется.</span><span class="sxs-lookup"><span data-stu-id="5bfd4-126">If `condition` is still `True`, the process is repeated.</span></span> <span data-ttu-id="5bfd4-127">Если это так `False` , управление передается оператору, следующему за `End While` оператором.</span><span class="sxs-lookup"><span data-stu-id="5bfd4-127">If it’s `False`, control passes to the statement that follows the `End While` statement.</span></span>  
  
 <span data-ttu-id="5bfd4-128">`While`Оператор всегда проверяет условие перед началом цикла.</span><span class="sxs-lookup"><span data-stu-id="5bfd4-128">The `While` statement always checks the condition before it starts the loop.</span></span> <span data-ttu-id="5bfd4-129">Цикл продолжается, пока условие остается `True` .</span><span class="sxs-lookup"><span data-stu-id="5bfd4-129">Looping continues while the condition remains `True`.</span></span> <span data-ttu-id="5bfd4-130">Если параметр `condition` имеет значение `False` при первом входе в цикл, он не выполняется даже один раз.</span><span class="sxs-lookup"><span data-stu-id="5bfd4-130">If `condition` is `False` when you first enter the loop, it doesn’t run even once.</span></span>  
  
 <span data-ttu-id="5bfd4-131">`condition`Обычно результат сравнения двух значений, но может быть любым выражением, результатом вычисления которого является [логическое значение типа данных](../data-types/boolean-data-type.md) ( `True` или `False` ).</span><span class="sxs-lookup"><span data-stu-id="5bfd4-131">The `condition` usually results from a comparison of two values, but it can be any expression that evaluates to a [Boolean Data Type](../data-types/boolean-data-type.md) value (`True` or `False`).</span></span> <span data-ttu-id="5bfd4-132">Это выражение может включать в себя значение другого типа данных, например числовой тип, который был преобразован в `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="5bfd4-132">This expression can include a value of another data type, such as a numeric type, that has been converted to `Boolean`.</span></span>  
  
 <span data-ttu-id="5bfd4-133">Можно вложить `While` циклы, поместив один цикл в другой.</span><span class="sxs-lookup"><span data-stu-id="5bfd4-133">You can nest `While` loops by placing one loop within another.</span></span> <span data-ttu-id="5bfd4-134">Можно также вкладывать различные виды управляющих структур друг в друга.</span><span class="sxs-lookup"><span data-stu-id="5bfd4-134">You can also nest different kinds of control structures within one another.</span></span> <span data-ttu-id="5bfd4-135">Дополнительные сведения см. в разделе [вложенные структуры управления](../../programming-guide/language-features/control-flow/nested-control-structures.md).</span><span class="sxs-lookup"><span data-stu-id="5bfd4-135">For more information, see [Nested Control Structures](../../programming-guide/language-features/control-flow/nested-control-structures.md).</span></span>  
  
## <a name="exit-while"></a><span data-ttu-id="5bfd4-136">Выйти, пока</span><span class="sxs-lookup"><span data-stu-id="5bfd4-136">Exit While</span></span>  

 <span data-ttu-id="5bfd4-137">Оператор [Exit While](exit-statement.md) может предоставить другой способ выхода из `While` цикла.</span><span class="sxs-lookup"><span data-stu-id="5bfd4-137">The [Exit While](exit-statement.md) statement can provide another way to exit a `While` loop.</span></span> <span data-ttu-id="5bfd4-138">`Exit While` немедленно передает управление оператору, который следует за `End While` оператором.</span><span class="sxs-lookup"><span data-stu-id="5bfd4-138">`Exit While` immediately transfers control to the statement that follows the `End While` statement.</span></span>  
  
 <span data-ttu-id="5bfd4-139">Обычно используется `Exit While` после вычисления некоторого условия (например, в `If...Then...Else` структуре).</span><span class="sxs-lookup"><span data-stu-id="5bfd4-139">You typically use `Exit While` after some condition is evaluated (for example, in an `If...Then...Else` structure).</span></span> <span data-ttu-id="5bfd4-140">Может потребоваться выйти из цикла, если обнаруживается условие, которое делает ненужным или невозможным продолжение итераций, например ошибочное значение или запрос на завершение.</span><span class="sxs-lookup"><span data-stu-id="5bfd4-140">You might want to exit a loop if you detect a condition that makes it unnecessary or impossible to continue iterating, such as an erroneous value or a termination request.</span></span> <span data-ttu-id="5bfd4-141">Можно использовать `Exit While` при проверке условия, которое может вызвать *бесконечный цикл*, что является циклом, который может выполнять очень большое или даже бесконечное число раз.</span><span class="sxs-lookup"><span data-stu-id="5bfd4-141">You can use `Exit While` when you test for a condition that could cause an *endless loop*, which is a loop that could run an extremely large or even infinite number of times.</span></span> <span data-ttu-id="5bfd4-142">Затем можно использовать `Exit While` для экранирования цикла.</span><span class="sxs-lookup"><span data-stu-id="5bfd4-142">You can then use `Exit While` to escape the loop.</span></span>  
  
 <span data-ttu-id="5bfd4-143">Любое количество операторов можно разместить `Exit While` в любом месте `While` цикла.</span><span class="sxs-lookup"><span data-stu-id="5bfd4-143">You can place any number of `Exit While` statements anywhere in the `While` loop.</span></span>  
  
 <span data-ttu-id="5bfd4-144">При использовании внутри вложенных `While` циклов `Exit While` передает управление за пределы самого внутреннего цикла и в следующий более высокий уровень вложенности.</span><span class="sxs-lookup"><span data-stu-id="5bfd4-144">When used within nested `While` loops, `Exit While` transfers control out of the innermost loop and into the next higher level of nesting.</span></span>  
  
 <span data-ttu-id="5bfd4-145">`Continue While`Оператор немедленно передает управление следующей итерации цикла.</span><span class="sxs-lookup"><span data-stu-id="5bfd4-145">The `Continue While` statement immediately transfers control to the next iteration of the loop.</span></span> <span data-ttu-id="5bfd4-146">Дополнительные сведения см. в разделе [оператор continue](continue-statement.md).</span><span class="sxs-lookup"><span data-stu-id="5bfd4-146">For more information, see [Continue Statement](continue-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5bfd4-147">Пример</span><span class="sxs-lookup"><span data-stu-id="5bfd4-147">Example</span></span>  

 <span data-ttu-id="5bfd4-148">В следующем примере операторы в цикле продолжают выполняться до тех пор, пока `index` переменная не будет больше 10.</span><span class="sxs-lookup"><span data-stu-id="5bfd4-148">In the following example, the statements in the loop continue to run until the `index` variable is greater than 10.</span></span>  
  
 [!code-vb[VbVbalrStatements#171](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#171)]  
  
## <a name="example"></a><span data-ttu-id="5bfd4-149">Пример</span><span class="sxs-lookup"><span data-stu-id="5bfd4-149">Example</span></span>  

 <span data-ttu-id="5bfd4-150">В следующем примере показано использование `Continue While` `Exit While` операторов и.</span><span class="sxs-lookup"><span data-stu-id="5bfd4-150">The following example illustrates the use of the `Continue While` and `Exit While` statements.</span></span>  
  
 [!code-vb[VbVbalrStatements#172](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#172)]  
  
## <a name="example"></a><span data-ttu-id="5bfd4-151">Пример</span><span class="sxs-lookup"><span data-stu-id="5bfd4-151">Example</span></span>  

 <span data-ttu-id="5bfd4-152">В следующем примере считываются все строки в текстовом файле.</span><span class="sxs-lookup"><span data-stu-id="5bfd4-152">The following example reads all lines in a text file.</span></span> <span data-ttu-id="5bfd4-153"><xref:System.IO.File.OpenText%2A>Метод открывает файл и возвращает объект <xref:System.IO.StreamReader> , считывающий символы.</span><span class="sxs-lookup"><span data-stu-id="5bfd4-153">The <xref:System.IO.File.OpenText%2A> method opens the file and returns a <xref:System.IO.StreamReader> that reads the characters.</span></span> <span data-ttu-id="5bfd4-154">В `While` условии <xref:System.IO.StreamReader.Peek%2A> метод `StreamReader` определяет, содержит ли файл дополнительные символы.</span><span class="sxs-lookup"><span data-stu-id="5bfd4-154">In the `While` condition, the <xref:System.IO.StreamReader.Peek%2A> method of the `StreamReader` determines whether the file contains additional characters.</span></span>  
  
 [!code-vb[VbVbalrStatements#173](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#173)]  
  
## <a name="see-also"></a><span data-ttu-id="5bfd4-155">См. также</span><span class="sxs-lookup"><span data-stu-id="5bfd4-155">See also</span></span>

- [<span data-ttu-id="5bfd4-156">Циклические структуры</span><span class="sxs-lookup"><span data-stu-id="5bfd4-156">Loop Structures</span></span>](../../programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="5bfd4-157">Оператор Do…Loop</span><span class="sxs-lookup"><span data-stu-id="5bfd4-157">Do...Loop Statement</span></span>](do-loop-statement.md)
- [<span data-ttu-id="5bfd4-158">Оператор For…Next</span><span class="sxs-lookup"><span data-stu-id="5bfd4-158">For...Next Statement</span></span>](for-next-statement.md)
- [<span data-ttu-id="5bfd4-159">Логический тип данных</span><span class="sxs-lookup"><span data-stu-id="5bfd4-159">Boolean Data Type</span></span>](../data-types/boolean-data-type.md)
- [<span data-ttu-id="5bfd4-160">Вложенные структуры управления</span><span class="sxs-lookup"><span data-stu-id="5bfd4-160">Nested Control Structures</span></span>](../../programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="5bfd4-161">Оператор Exit</span><span class="sxs-lookup"><span data-stu-id="5bfd4-161">Exit Statement</span></span>](exit-statement.md)
- [<span data-ttu-id="5bfd4-162">Оператор Continue</span><span class="sxs-lookup"><span data-stu-id="5bfd4-162">Continue Statement</span></span>](continue-statement.md)
