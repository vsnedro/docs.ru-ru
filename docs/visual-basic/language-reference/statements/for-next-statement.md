---
title: Оператор For…Next
ms.date: 07/20/2015
f1_keywords:
- vb.Step
- vb.Next
- vb.To
- vb.for
helpviewer_keywords:
- infinite loops
- Next keyword [Visual Basic], For...Next statements
- For keyword [Visual Basic], For...Next statements
- Step keyword [Visual Basic], For...Next statements
- operator overloading, For...Next statement
- To keyword [Visual Basic], For...Next statements
- endless loops
- loops, endless
- instructions, repeating
- Next statement [Visual Basic], For...Next
- For...Next statements
- loop structures [Visual Basic], For...Next
- loops, infinite
- Exit statement [Visual Basic], For...Next statements
- For statement [Visual Basic]
ms.assetid: f5fc0d51-67ce-4c36-9f09-31c9a91c94e9
ms.openlocfilehash: 6896c6cfb4ec5d6207011e56b72639c459120e53
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404645"
---
# <a name="fornext-statement-visual-basic"></a><span data-ttu-id="031cd-102">Оператор For... Next (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="031cd-102">For...Next Statement (Visual Basic)</span></span>

<span data-ttu-id="031cd-103">Повторяет группу инструкций указанное число раз.</span><span class="sxs-lookup"><span data-stu-id="031cd-103">Repeats a group of statements a specified number of times.</span></span>

## <a name="syntax"></a><span data-ttu-id="031cd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="031cd-104">Syntax</span></span>

```vb
For counter [ As datatype ] = start To end [ Step step ]
    [ statements ]
    [ Continue For ]
    [ statements ]
    [ Exit For ]
    [ statements ]
Next [ counter ]
```

## <a name="parts"></a><span data-ttu-id="031cd-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="031cd-105">Parts</span></span>

|<span data-ttu-id="031cd-106">Часть</span><span class="sxs-lookup"><span data-stu-id="031cd-106">Part</span></span>|<span data-ttu-id="031cd-107">Описание</span><span class="sxs-lookup"><span data-stu-id="031cd-107">Description</span></span>|
|----------|-----------------|
|`counter`|<span data-ttu-id="031cd-108">Требуется в `For` инструкции.</span><span class="sxs-lookup"><span data-stu-id="031cd-108">Required in the `For` statement.</span></span> <span data-ttu-id="031cd-109">Числовая переменная.</span><span class="sxs-lookup"><span data-stu-id="031cd-109">Numeric variable.</span></span> <span data-ttu-id="031cd-110">Управляющая переменная для цикла.</span><span class="sxs-lookup"><span data-stu-id="031cd-110">The control variable for the loop.</span></span> <span data-ttu-id="031cd-111">Дополнительные сведения см. в подразделе [аргумент Counter](#BKMK_Counter) далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="031cd-111">For more information, see [Counter Argument](#BKMK_Counter) later in this topic.</span></span>|
|`datatype`|<span data-ttu-id="031cd-112">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="031cd-112">Optional.</span></span> <span data-ttu-id="031cd-113">Тип данных `counter` .</span><span class="sxs-lookup"><span data-stu-id="031cd-113">Data type of `counter`.</span></span> <span data-ttu-id="031cd-114">Дополнительные сведения см. в подразделе [аргумент Counter](#BKMK_Counter) далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="031cd-114">For more information, see [Counter Argument](#BKMK_Counter) later in this topic.</span></span>|
|`start`|<span data-ttu-id="031cd-115">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="031cd-115">Required.</span></span> <span data-ttu-id="031cd-116">Числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="031cd-116">Numeric expression.</span></span> <span data-ttu-id="031cd-117">Начальное значение `counter`.</span><span class="sxs-lookup"><span data-stu-id="031cd-117">The initial value of `counter`.</span></span>|
|`end`|<span data-ttu-id="031cd-118">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="031cd-118">Required.</span></span> <span data-ttu-id="031cd-119">Числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="031cd-119">Numeric expression.</span></span> <span data-ttu-id="031cd-120">Конечное значение `counter` .</span><span class="sxs-lookup"><span data-stu-id="031cd-120">The final value of `counter`.</span></span>|
|`step`|<span data-ttu-id="031cd-121">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="031cd-121">Optional.</span></span> <span data-ttu-id="031cd-122">Числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="031cd-122">Numeric expression.</span></span> <span data-ttu-id="031cd-123">Величина, на которую `counter` увеличивается каждый раз с помощью цикла.</span><span class="sxs-lookup"><span data-stu-id="031cd-123">The amount by which `counter` is incremented each time through the loop.</span></span>|
|`statements`|<span data-ttu-id="031cd-124">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="031cd-124">Optional.</span></span> <span data-ttu-id="031cd-125">Одна или несколько инструкций между `For` и `Next` выполняются указанное число раз.</span><span class="sxs-lookup"><span data-stu-id="031cd-125">One or more statements between `For` and `Next` that run the specified number of times.</span></span>|
|`Continue For`|<span data-ttu-id="031cd-126">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="031cd-126">Optional.</span></span> <span data-ttu-id="031cd-127">Передает управление в следующую итерацию цикла.</span><span class="sxs-lookup"><span data-stu-id="031cd-127">Transfers control to the next loop iteration.</span></span>|
|`Exit For`|<span data-ttu-id="031cd-128">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="031cd-128">Optional.</span></span> <span data-ttu-id="031cd-129">Передает управление за пределы `For` цикла.</span><span class="sxs-lookup"><span data-stu-id="031cd-129">Transfers control out of the `For` loop.</span></span>|
|`Next`|<span data-ttu-id="031cd-130">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="031cd-130">Required.</span></span> <span data-ttu-id="031cd-131">Завершает определение `For` цикла.</span><span class="sxs-lookup"><span data-stu-id="031cd-131">Terminates the definition of the `For` loop.</span></span>|

> [!NOTE]
> <span data-ttu-id="031cd-132">`To`Ключевое слово используется в этом операторе для указания диапазона счетчика.</span><span class="sxs-lookup"><span data-stu-id="031cd-132">The `To` keyword is used in this statement to specify the range for the counter.</span></span> <span data-ttu-id="031cd-133">Это ключевое слово также можно использовать в [SELECT... Оператор Case](select-case-statement.md) и в объявлениях массивов.</span><span class="sxs-lookup"><span data-stu-id="031cd-133">You can also use this keyword in the [Select...Case Statement](select-case-statement.md) and in array declarations.</span></span> <span data-ttu-id="031cd-134">Дополнительные сведения об объявлениях массивов см. в разделе [оператор Dim](dim-statement.md).</span><span class="sxs-lookup"><span data-stu-id="031cd-134">For more information about array declarations, see [Dim Statement](dim-statement.md).</span></span>

## <a name="simple-examples"></a><span data-ttu-id="031cd-135"> Простые примеры</span><span class="sxs-lookup"><span data-stu-id="031cd-135">Simple Examples</span></span>

<span data-ttu-id="031cd-136">Используйте `For` структуру..., `Next` Если нужно повторить набор инструкций заданное число раз.</span><span class="sxs-lookup"><span data-stu-id="031cd-136">You use a `For`...`Next` structure when you want to repeat a set of statements a set number of times.</span></span>

<span data-ttu-id="031cd-137">В следующем примере `index` переменная начинается со значения 1 и увеличивается при каждой итерации цикла, после чего значение `index` достигает 5.</span><span class="sxs-lookup"><span data-stu-id="031cd-137">In the following example, the `index` variable starts with a value of 1 and is incremented with each iteration of the loop, ending after the value of `index` reaches 5.</span></span>

[!code-vb[VbVbalrStatements#111](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#111)]

<span data-ttu-id="031cd-138">В следующем примере `number` переменная начинается с 2 и уменьшается на 0,25 в каждой итерации цикла, после чего значение `number` достигнет 0.</span><span class="sxs-lookup"><span data-stu-id="031cd-138">In the following example, the `number` variable starts at 2 and is reduced by 0.25 on each iteration of the loop, ending after the value of `number` reaches 0.</span></span> <span data-ttu-id="031cd-139">`Step`Аргумент класса `-.25` сокращает значение на 0,25 при каждой итерации цикла.</span><span class="sxs-lookup"><span data-stu-id="031cd-139">The `Step` argument of `-.25` reduces the value by 0.25 on each iteration of the loop.</span></span>

[!code-vb[VbVbalrStatements#112](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#112)]

> [!TIP]
> <span data-ttu-id="031cd-140">Ответ [... Конец оператора while](while-end-while-statement.md) или [Do... Оператор Loop](do-loop-statement.md) хорошо работает, если заранее неизвестно, сколько раз нужно выполнять инструкции в цикле.</span><span class="sxs-lookup"><span data-stu-id="031cd-140">A [While...End While Statement](while-end-while-statement.md) or [Do...Loop Statement](do-loop-statement.md) works well when you don't know in advance how many times to run the statements in the loop.</span></span> <span data-ttu-id="031cd-141">Однако, если вы планируете выполнять цикл определенное число раз, `For` `Next` лучше выбрать цикл....</span><span class="sxs-lookup"><span data-stu-id="031cd-141">However, when you expect to run the loop a specific number of times, a `For`...`Next` loop is a better choice.</span></span> <span data-ttu-id="031cd-142">Число итераций определяется при первом входе в цикл.</span><span class="sxs-lookup"><span data-stu-id="031cd-142">You determine the number of iterations when you first enter the loop.</span></span>

## <a name="nesting-loops"></a><span data-ttu-id="031cd-143">Вложенные циклы</span><span class="sxs-lookup"><span data-stu-id="031cd-143">Nesting Loops</span></span>

<span data-ttu-id="031cd-144">Можно вложить `For` циклы, поместив один цикл в другой.</span><span class="sxs-lookup"><span data-stu-id="031cd-144">You can nest `For` loops by putting one loop within another.</span></span> <span data-ttu-id="031cd-145">В следующем примере показаны вложенные `For` структуры... `Next` , имеющие разные значения шага.</span><span class="sxs-lookup"><span data-stu-id="031cd-145">The following example demonstrates nested `For`...`Next` structures that have different step values.</span></span> <span data-ttu-id="031cd-146">Внешний цикл создает строку для каждой итерации цикла.</span><span class="sxs-lookup"><span data-stu-id="031cd-146">The outer loop creates a string for every iteration of the loop.</span></span> <span data-ttu-id="031cd-147">Внутренний цикл уменьшает переменную счетчика цикла для каждой итерации цикла.</span><span class="sxs-lookup"><span data-stu-id="031cd-147">The inner loop decrements a loop counter variable for every iteration of the loop.</span></span>

[!code-vb[VbVbalrStatements#113](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#113)]

<span data-ttu-id="031cd-148">При вложенных циклах каждый цикл должен иметь уникальную `counter` переменную.</span><span class="sxs-lookup"><span data-stu-id="031cd-148">When nesting loops, each loop must have a unique `counter` variable.</span></span>

<span data-ttu-id="031cd-149">Вы также можете вкладывать различные виды управления в друг друга.</span><span class="sxs-lookup"><span data-stu-id="031cd-149">You can also nest different kinds control structures within each other.</span></span> <span data-ttu-id="031cd-150">Дополнительные сведения см. в разделе [вложенные структуры управления](../../programming-guide/language-features/control-flow/nested-control-structures.md).</span><span class="sxs-lookup"><span data-stu-id="031cd-150">For more information, see [Nested Control Structures](../../programming-guide/language-features/control-flow/nested-control-structures.md).</span></span>

## <a name="exit-for-and-continue-for"></a><span data-ttu-id="031cd-151">Выход и продолжение для</span><span class="sxs-lookup"><span data-stu-id="031cd-151">Exit For and Continue For</span></span>

<span data-ttu-id="031cd-152">`Exit For`Оператор немедленно завершает работу `For` ...`Next`</span><span class="sxs-lookup"><span data-stu-id="031cd-152">The `Exit For` statement immediately exits the `For`…`Next`</span></span> <span data-ttu-id="031cd-153">выполняет цикл и передает управление оператору, который следует за `Next` оператором.</span><span class="sxs-lookup"><span data-stu-id="031cd-153">loop and transfers control to the statement that follows the `Next` statement.</span></span>

<span data-ttu-id="031cd-154">`Continue For`Оператор передает управление сразу в следующую итерацию цикла.</span><span class="sxs-lookup"><span data-stu-id="031cd-154">The `Continue For` statement transfers control immediately to the next iteration of the loop.</span></span> <span data-ttu-id="031cd-155">Дополнительные сведения см. в разделе [оператор continue](continue-statement.md).</span><span class="sxs-lookup"><span data-stu-id="031cd-155">For more information, see [Continue Statement](continue-statement.md).</span></span>

<span data-ttu-id="031cd-156">В следующем примере показано использование `Continue For` `Exit For` операторов и.</span><span class="sxs-lookup"><span data-stu-id="031cd-156">The following example illustrates the use of the `Continue For` and `Exit For` statements.</span></span>

[!code-vb[VbVbalrStatements#115](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#115)]

<span data-ttu-id="031cd-157">Можно разместить любое количество `Exit For` операторов в `For` ...`Next`</span><span class="sxs-lookup"><span data-stu-id="031cd-157">You can put any number of `Exit For` statements in a `For`…`Next`</span></span> <span data-ttu-id="031cd-158">повторить.</span><span class="sxs-lookup"><span data-stu-id="031cd-158">loop.</span></span> <span data-ttu-id="031cd-159">При использовании внутри вложенного `For` ...`Next`</span><span class="sxs-lookup"><span data-stu-id="031cd-159">When used within nested `For`…`Next`</span></span> <span data-ttu-id="031cd-160">выполняет цикл, `Exit For` выходит из внутреннего цикла и передает управление следующему более высокому уровню вложенности.</span><span class="sxs-lookup"><span data-stu-id="031cd-160">loops, `Exit For` exits the innermost loop and transfers control to the next higher level of nesting.</span></span>

<span data-ttu-id="031cd-161">`Exit For`часто используется после вычисления некоторого условия (например, в `If` ... `Then` ...`Else` структура).</span><span class="sxs-lookup"><span data-stu-id="031cd-161">`Exit For` is often used after you evaluate some condition (for example, in an `If`...`Then`...`Else` structure).</span></span> <span data-ttu-id="031cd-162">Может потребоваться использовать `Exit For` для следующих условий:</span><span class="sxs-lookup"><span data-stu-id="031cd-162">You might want to use `Exit For` for the following conditions:</span></span>

- <span data-ttu-id="031cd-163">Продолжение итерации не требуется или невозможно.</span><span class="sxs-lookup"><span data-stu-id="031cd-163">Continuing to iterate is unnecessary or impossible.</span></span> <span data-ttu-id="031cd-164">Это условие может быть создано с помощью ошибочного значения или запроса на завершение.</span><span class="sxs-lookup"><span data-stu-id="031cd-164">An erroneous value or a termination request might create this condition.</span></span>

- <span data-ttu-id="031cd-165">А.. `Try` . `Catch` ...`Finally` перехватывает исключение.</span><span class="sxs-lookup"><span data-stu-id="031cd-165">A `Try`...`Catch`...`Finally` statement catches an exception.</span></span> <span data-ttu-id="031cd-166">`Exit For`В конце блока можно использовать `Finally` .</span><span class="sxs-lookup"><span data-stu-id="031cd-166">You might use `Exit For` at the end of the `Finally` block.</span></span>

- <span data-ttu-id="031cd-167">У вас есть бесконечный цикл, который может выполняться с большим или даже бесконечным числом раз.</span><span class="sxs-lookup"><span data-stu-id="031cd-167">You have an endless loop, which is a loop that could run a large or even infinite number of times.</span></span> <span data-ttu-id="031cd-168">При обнаружении такого условия можно использовать `Exit For` для экранирования цикла.</span><span class="sxs-lookup"><span data-stu-id="031cd-168">If you detect such a condition, you can use `Exit For` to escape the loop.</span></span> <span data-ttu-id="031cd-169">Дополнительные сведения см. в разделе [Do... Loop, инструкция](do-loop-statement.md).</span><span class="sxs-lookup"><span data-stu-id="031cd-169">For more information, see [Do...Loop Statement](do-loop-statement.md).</span></span>

## <a name="technical-implementation"></a><span data-ttu-id="031cd-170">Техническая реализация</span><span class="sxs-lookup"><span data-stu-id="031cd-170">Technical Implementation</span></span>

<span data-ttu-id="031cd-171">При `For` запуске цикла... `Next` Visual Basic вычисляет `start` , `end` и `step` .</span><span class="sxs-lookup"><span data-stu-id="031cd-171">When a `For`...`Next` loop starts, Visual Basic evaluates `start`, `end`, and `step`.</span></span> <span data-ttu-id="031cd-172">Visual Basic вычисляет эти значения только в данный момент, а затем присваивает значение `start` `counter` .</span><span class="sxs-lookup"><span data-stu-id="031cd-172">Visual Basic evaluates these values only at this time and then assigns `start` to `counter`.</span></span> <span data-ttu-id="031cd-173">Перед выполнением блока операторов Visual Basic сравнивается `counter` с `end` .</span><span class="sxs-lookup"><span data-stu-id="031cd-173">Before the statement block runs, Visual Basic compares `counter` to `end`.</span></span> <span data-ttu-id="031cd-174">Если `counter` уже больше `end` значения (или меньше `step` , если имеет отрицательное значение), `For` цикл завершается, и управление передается оператору, следующему за `Next` оператором.</span><span class="sxs-lookup"><span data-stu-id="031cd-174">If `counter` is already larger than the `end` value (or smaller if `step` is negative), the `For` loop ends and control passes to the statement that follows the `Next` statement.</span></span> <span data-ttu-id="031cd-175">В противном случае выполняется блок операторов.</span><span class="sxs-lookup"><span data-stu-id="031cd-175">Otherwise, the statement block runs.</span></span>

<span data-ttu-id="031cd-176">Каждый раз, когда Visual Basic обнаруживает `Next` оператор, он увеличивается на `counter` `step` и возвращается в `For` оператор.</span><span class="sxs-lookup"><span data-stu-id="031cd-176">Each time Visual Basic encounters the `Next` statement, it increments `counter` by `step` and returns to the `For` statement.</span></span> <span data-ttu-id="031cd-177">Затем он сравнивает `counter` с `end` и снова либо выполняет блок, либо выходит из цикла, в зависимости от результата.</span><span class="sxs-lookup"><span data-stu-id="031cd-177">Again it compares `counter` to `end`, and again it either runs the block or exits the loop, depending on the result.</span></span> <span data-ttu-id="031cd-178">Этот процесс выполняется до тех пор `counter` , пока не будет пройден `end` или `Exit For` не встретится оператор.</span><span class="sxs-lookup"><span data-stu-id="031cd-178">This process continues until `counter` passes `end` or an `Exit For` statement is encountered.</span></span>

<span data-ttu-id="031cd-179">Цикл не останавливается, пока не будет `counter` пройден `end` .</span><span class="sxs-lookup"><span data-stu-id="031cd-179">The loop doesn't stop until `counter` has passed `end`.</span></span> <span data-ttu-id="031cd-180">Если `counter` равно `end` , цикл продолжится.</span><span class="sxs-lookup"><span data-stu-id="031cd-180">If `counter` is equal to `end`, the loop continues.</span></span> <span data-ttu-id="031cd-181">Сравнение, которое определяет, следует ли запускать блок, `counter`  <=  `end` Если `step` является положительным и `counter`  >=  `end` `step` отрицательным.</span><span class="sxs-lookup"><span data-stu-id="031cd-181">The comparison that determines whether to run the block is `counter` <= `end` if `step` is positive and `counter` >= `end` if `step` is negative.</span></span>

<span data-ttu-id="031cd-182">Если изменить значение `counter` во время цикла, код может оказаться труднее для чтения и отладки.</span><span class="sxs-lookup"><span data-stu-id="031cd-182">If you change the value of `counter` while inside a loop, your code might be more difficult to read and debug.</span></span> <span data-ttu-id="031cd-183">Изменение значения `start` , `end` или `step` не влияет на значения итерации, которые были определены при первом входе в цикл.</span><span class="sxs-lookup"><span data-stu-id="031cd-183">Changing the value of `start`, `end`, or `step` doesn't affect the iteration values that were determined when the loop was first entered.</span></span>

<span data-ttu-id="031cd-184">При вложении циклов компилятор сообщает об ошибке, если обнаруживает `Next` оператор внешнего уровня вложенности перед `Next` инструкцией внутреннего уровня.</span><span class="sxs-lookup"><span data-stu-id="031cd-184">If you nest loops, the compiler signals an error if it encounters the `Next` statement of an outer nesting level before the `Next` statement of an inner level.</span></span> <span data-ttu-id="031cd-185">Однако компилятор может обнаружить эту перекрытие ошибки только в том случае, если указать `counter` в каждой `Next` инструкции.</span><span class="sxs-lookup"><span data-stu-id="031cd-185">However, the compiler can detect this overlapping error only if you specify `counter` in every `Next` statement.</span></span>

### <a name="step-argument"></a><span data-ttu-id="031cd-186">Аргумент Step</span><span class="sxs-lookup"><span data-stu-id="031cd-186">Step Argument</span></span>

<span data-ttu-id="031cd-187">Значение `step` может быть либо положительным, либо отрицательным.</span><span class="sxs-lookup"><span data-stu-id="031cd-187">The value of `step` can be either positive or negative.</span></span> <span data-ttu-id="031cd-188">Этот параметр определяет обработку цикла в соответствии со следующей таблицей.</span><span class="sxs-lookup"><span data-stu-id="031cd-188">This parameter determines loop processing according to the following table:</span></span>

|<span data-ttu-id="031cd-189">**Значение шага**</span><span class="sxs-lookup"><span data-stu-id="031cd-189">**Step value**</span></span>|<span data-ttu-id="031cd-190">**Цикл выполняется, если**</span><span class="sxs-lookup"><span data-stu-id="031cd-190">**Loop executes if**</span></span>|
|--------------------|--------------------------|
|<span data-ttu-id="031cd-191">Положительный или нулевой</span><span class="sxs-lookup"><span data-stu-id="031cd-191">Positive or zero</span></span>|`counter` <= `end`|
|<span data-ttu-id="031cd-192">Negative</span><span class="sxs-lookup"><span data-stu-id="031cd-192">Negative</span></span>|`counter` >= `end`|

<span data-ttu-id="031cd-193">Значение `step` по умолчанию — 1.</span><span class="sxs-lookup"><span data-stu-id="031cd-193">The default value of `step` is 1.</span></span>

### <a name="counter-argument"></a><a name="BKMK_Counter"></a><span data-ttu-id="031cd-194">Аргумент счетчика</span><span class="sxs-lookup"><span data-stu-id="031cd-194">Counter Argument</span></span>

<span data-ttu-id="031cd-195">В следующей таблице показано `counter` , определяет ли новая локальная переменная, областью действия которой является весь `For…Next` цикл.</span><span class="sxs-lookup"><span data-stu-id="031cd-195">The following table indicates whether `counter` defines a new local variable that’s scoped to the entire `For…Next` loop.</span></span> <span data-ttu-id="031cd-196">Это определение зависит от того, существует ли оно `datatype` и `counter` уже определено ли оно.</span><span class="sxs-lookup"><span data-stu-id="031cd-196">This determination depends on whether `datatype` is present and whether `counter` is already defined.</span></span>

|<span data-ttu-id="031cd-197">`datatype`Имеется?</span><span class="sxs-lookup"><span data-stu-id="031cd-197">Is `datatype` present?</span></span>|<span data-ttu-id="031cd-198">`counter`Уже определено?</span><span class="sxs-lookup"><span data-stu-id="031cd-198">Is `counter` already defined?</span></span>|<span data-ttu-id="031cd-199">Результат ( `counter` определяет, определена ли новая локальная переменная в пределах всего `For...Next` цикла)</span><span class="sxs-lookup"><span data-stu-id="031cd-199">Result (whether `counter` defines a new local variable that’s scoped to the entire `For...Next` loop)</span></span>|
|----------------------------|-----------------------------------|-------------------------------------------------------------------------------------------------------------|
|<span data-ttu-id="031cd-200">нет</span><span class="sxs-lookup"><span data-stu-id="031cd-200">No</span></span>|<span data-ttu-id="031cd-201">Да</span><span class="sxs-lookup"><span data-stu-id="031cd-201">Yes</span></span>|<span data-ttu-id="031cd-202">Нет, так как `counter` уже определено.</span><span class="sxs-lookup"><span data-stu-id="031cd-202">No, because `counter` is already defined.</span></span> <span data-ttu-id="031cd-203">Если область действия `counter` не является локальной для процедуры, возникает предупреждение во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="031cd-203">If the scope of `counter` isn't local to the procedure, a compile-time warning occurs.</span></span>|
|<span data-ttu-id="031cd-204">нет</span><span class="sxs-lookup"><span data-stu-id="031cd-204">No</span></span>|<span data-ttu-id="031cd-205">Нет</span><span class="sxs-lookup"><span data-stu-id="031cd-205">No</span></span>|<span data-ttu-id="031cd-206">Да.</span><span class="sxs-lookup"><span data-stu-id="031cd-206">Yes.</span></span> <span data-ttu-id="031cd-207">Тип данных выводится из `start` `end` выражений, и `step` .</span><span class="sxs-lookup"><span data-stu-id="031cd-207">The data type is inferred from the `start`, `end`, and `step` expressions.</span></span> <span data-ttu-id="031cd-208">Дополнительные сведения о выводе типа см. в разделе [Option Infer](option-infer-statement.md) и [определение локального типа](../../programming-guide/language-features/variables/local-type-inference.md).</span><span class="sxs-lookup"><span data-stu-id="031cd-208">For information about type inference, see [Option Infer Statement](option-infer-statement.md) and [Local Type Inference](../../programming-guide/language-features/variables/local-type-inference.md).</span></span>|
|<span data-ttu-id="031cd-209">Да</span><span class="sxs-lookup"><span data-stu-id="031cd-209">Yes</span></span>|<span data-ttu-id="031cd-210">Да</span><span class="sxs-lookup"><span data-stu-id="031cd-210">Yes</span></span>|<span data-ttu-id="031cd-211">Да, но только в том случае, если существующая `counter` переменная определена за пределами процедуры.</span><span class="sxs-lookup"><span data-stu-id="031cd-211">Yes, but only if the existing `counter` variable is defined outside the procedure.</span></span> <span data-ttu-id="031cd-212">Эта переменная остается отдельной.</span><span class="sxs-lookup"><span data-stu-id="031cd-212">That variable remains separate.</span></span> <span data-ttu-id="031cd-213">Если область существующей `counter` переменной является локальной для процедуры, возникает ошибка времени компиляции.</span><span class="sxs-lookup"><span data-stu-id="031cd-213">If the scope of the existing `counter` variable is local to the procedure, a compile-time error occurs.</span></span>|
|<span data-ttu-id="031cd-214">Да</span><span class="sxs-lookup"><span data-stu-id="031cd-214">Yes</span></span>|<span data-ttu-id="031cd-215">Нет</span><span class="sxs-lookup"><span data-stu-id="031cd-215">No</span></span>|<span data-ttu-id="031cd-216">Да.</span><span class="sxs-lookup"><span data-stu-id="031cd-216">Yes.</span></span>|

<span data-ttu-id="031cd-217">Тип данных параметра `counter` определяет тип итерации, который должен быть одним из следующих типов:</span><span class="sxs-lookup"><span data-stu-id="031cd-217">The data type of `counter` determines the type of the iteration, which must be one of the following types:</span></span>

- <span data-ttu-id="031cd-218">A `Byte` , `SByte` , `UShort` , `Short` , `UInteger` , `Integer` , `ULong` , `Long` , `Decimal` , `Single` или `Double` .</span><span class="sxs-lookup"><span data-stu-id="031cd-218">A `Byte`, `SByte`, `UShort`, `Short`, `UInteger`, `Integer`, `ULong`, `Long`, `Decimal`, `Single`, or `Double`.</span></span>

- <span data-ttu-id="031cd-219">Перечисление, объявляемое с помощью [инструкции enum](enum-statement.md).</span><span class="sxs-lookup"><span data-stu-id="031cd-219">An enumeration that you declare by using an [Enum Statement](enum-statement.md).</span></span>

- <span data-ttu-id="031cd-220">`Object`.</span><span class="sxs-lookup"><span data-stu-id="031cd-220">An `Object`.</span></span>

- <span data-ttu-id="031cd-221">Тип `T` , имеющий следующие операторы, где `B` — это тип, который можно использовать в `Boolean` выражении.</span><span class="sxs-lookup"><span data-stu-id="031cd-221">A type `T` that has the following operators, where `B` is a type that can be used in a `Boolean` expression.</span></span>

  `Public Shared Operator >= (op1 As T, op2 As T) As B`

  `Public Shared Operator <= (op1 As T, op2 As T) As B`

  `Public Shared Operator - (op1 As T, op2 As T) As T`

  `Public Shared Operator + (op1 As T, op2 As T) As T`

<span data-ttu-id="031cd-222">При необходимости можно указать `counter` переменную в `Next` инструкции.</span><span class="sxs-lookup"><span data-stu-id="031cd-222">You can optionally specify the `counter` variable in the `Next` statement.</span></span> <span data-ttu-id="031cd-223">Этот синтаксис повышает удобочитаемость программы, особенно при наличии вложенных `For` циклов.</span><span class="sxs-lookup"><span data-stu-id="031cd-223">This syntax improves the readability of your program, especially if you have nested `For` loops.</span></span> <span data-ttu-id="031cd-224">Необходимо указать переменную, которая отображается в соответствующем `For` операторе.</span><span class="sxs-lookup"><span data-stu-id="031cd-224">You must specify the variable that appears in the corresponding `For` statement.</span></span>

<span data-ttu-id="031cd-225">`start`Выражения, `end` и `step` могут иметь любой тип данных, который расширяется до типа `counter` .</span><span class="sxs-lookup"><span data-stu-id="031cd-225">The `start`, `end`, and `step` expressions can evaluate to any data type that widens to the type of `counter`.</span></span> <span data-ttu-id="031cd-226">При использовании определяемого пользователем типа для может потребоваться `counter` определить `CType` оператор преобразования для преобразования типов `start` , `end` или `step` в тип `counter` .</span><span class="sxs-lookup"><span data-stu-id="031cd-226">If you use a user-defined type for `counter`, you might have to define the `CType` conversion operator to convert the types of `start`, `end`, or `step` to the type of `counter`.</span></span>

## <a name="example"></a><span data-ttu-id="031cd-227">Пример</span><span class="sxs-lookup"><span data-stu-id="031cd-227">Example</span></span>

<span data-ttu-id="031cd-228">В следующем примере удаляются все элементы из универсального списка.</span><span class="sxs-lookup"><span data-stu-id="031cd-228">The following example removes all elements from a generic list.</span></span> <span data-ttu-id="031cd-229">Вместо a [для каждого... Следующий оператор](for-each-next-statement.md). в примере показана `For` инструкция... `Next` , которая выполняет итерацию в убывающем порядке.</span><span class="sxs-lookup"><span data-stu-id="031cd-229">Instead of a [For Each...Next Statement](for-each-next-statement.md), the example shows a `For`...`Next` statement that iterates in descending order.</span></span> <span data-ttu-id="031cd-230">В этом примере используется этот метод `removeAt` , поскольку метод заставляет элементы после удаленного элемента иметь меньшее значение индекса.</span><span class="sxs-lookup"><span data-stu-id="031cd-230">The example uses this technique because the `removeAt` method causes elements after the removed element to have a lower index value.</span></span>

[!code-vb[VbVbalrStatements#114](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#114)]

## <a name="example"></a><span data-ttu-id="031cd-231">Пример</span><span class="sxs-lookup"><span data-stu-id="031cd-231">Example</span></span>

<span data-ttu-id="031cd-232">В следующем примере перебирается перечисление, объявленное с помощью [инструкции enum](enum-statement.md).</span><span class="sxs-lookup"><span data-stu-id="031cd-232">The following example iterates through an enumeration that's declared by using an [Enum Statement](enum-statement.md).</span></span>

[!code-vb[VbVbalrStatements#116](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#116)]

## <a name="example"></a><span data-ttu-id="031cd-233">Пример</span><span class="sxs-lookup"><span data-stu-id="031cd-233">Example</span></span>

<span data-ttu-id="031cd-234">В следующем примере параметры инструкции используют класс, который содержит перегрузки операторов для `+` операторов,, `-` `>=` и `<=` .</span><span class="sxs-lookup"><span data-stu-id="031cd-234">In the following example, the statement parameters use a class that has operator overloads for the `+`, `-`, `>=`, and `<=` operators.</span></span>

[!code-vb[VbVbalrStatements#117](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#117)]

## <a name="see-also"></a><span data-ttu-id="031cd-235">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="031cd-235">See also</span></span>

- <xref:System.Collections.Generic.List%601>
- [<span data-ttu-id="031cd-236">Циклические структуры</span><span class="sxs-lookup"><span data-stu-id="031cd-236">Loop Structures</span></span>](../../programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="031cd-237">Оператор While…End While</span><span class="sxs-lookup"><span data-stu-id="031cd-237">While...End While Statement</span></span>](while-end-while-statement.md)
- [<span data-ttu-id="031cd-238">Оператор Do…Loop</span><span class="sxs-lookup"><span data-stu-id="031cd-238">Do...Loop Statement</span></span>](do-loop-statement.md)
- [<span data-ttu-id="031cd-239">Вложенные структуры управления</span><span class="sxs-lookup"><span data-stu-id="031cd-239">Nested Control Structures</span></span>](../../programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="031cd-240">Оператор Exit</span><span class="sxs-lookup"><span data-stu-id="031cd-240">Exit Statement</span></span>](exit-statement.md)
- [<span data-ttu-id="031cd-241">Коллекции</span><span class="sxs-lookup"><span data-stu-id="031cd-241">Collections</span></span>](../../programming-guide/concepts/collections.md)
