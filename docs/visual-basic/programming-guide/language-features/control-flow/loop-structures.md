---
title: Циклические структуры
ms.date: 07/20/2015
helpviewer_keywords:
- control flow [Visual Basic], loops
- For keyword [Visual Basic], loop structures
- loops
- loop structures [Visual Basic]
- statements [Visual Basic], loop
- Do statement [Visual Basic], Do loops
- conditional statements [Visual Basic], loop structures
ms.assetid: ecacb09b-a4c9-42be-98b2-a15d368b5db8
ms.openlocfilehash: 3f60e9dc83dc7174e765903be13f2870ea40ce4c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403526"
---
# <a name="loop-structures-visual-basic"></a><span data-ttu-id="cffda-102">Циклические структуры (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cffda-102">Loop Structures (Visual Basic)</span></span>
<span data-ttu-id="cffda-103">Структуры циклов Visual Basic позволяют многократно выполнять одну или несколько строк кода.</span><span class="sxs-lookup"><span data-stu-id="cffda-103">Visual Basic loop structures allow you to run one or more lines of code repetitively.</span></span> <span data-ttu-id="cffda-104">Операторы можно повторять в структуре цикла, пока условие не будет равно, `True` пока условие не будет равно `False` , заданное число раз или один раз для каждого элемента в коллекции.</span><span class="sxs-lookup"><span data-stu-id="cffda-104">You can repeat the statements in a loop structure until a condition is `True`, until a condition is `False`, a specified number of times, or once for each element in a collection.</span></span>  
  
 <span data-ttu-id="cffda-105">На следующем рисунке показана структура цикла, выполняющая набор инструкций, пока условие не примет значение true:</span><span class="sxs-lookup"><span data-stu-id="cffda-105">The following illustration shows a loop structure that runs a set of statements until a condition becomes true:</span></span>  
  
 ![Блок-схема, на которой показано действие Do... Цикл Until.](./media/loop-structures/do-until-loop-true-condition.gif)  
  
## <a name="while-loops"></a><span data-ttu-id="cffda-107">Циклы while</span><span class="sxs-lookup"><span data-stu-id="cffda-107">While Loops</span></span>  
 <span data-ttu-id="cffda-108">`While`Конструкция... `End While` выполняет набор инструкций, пока условие, заданное в `While` инструкции, имеет значение `True` .</span><span class="sxs-lookup"><span data-stu-id="cffda-108">The `While`...`End While` construction runs a set of statements as long as the condition specified in the `While` statement is `True`.</span></span> <span data-ttu-id="cffda-109">Дополнительные сведения см. в разделе [while... Конец оператора while](../../../language-reference/statements/while-end-while-statement.md).</span><span class="sxs-lookup"><span data-stu-id="cffda-109">For more information, see [While...End While Statement](../../../language-reference/statements/while-end-while-statement.md).</span></span>  
  
## <a name="do-loops"></a><span data-ttu-id="cffda-110">Do Loops</span><span class="sxs-lookup"><span data-stu-id="cffda-110">Do Loops</span></span>  
 <span data-ttu-id="cffda-111">`Do`Конструкция... `Loop` позволяет проверить условие в начале или в конце структуры цикла.</span><span class="sxs-lookup"><span data-stu-id="cffda-111">The `Do`...`Loop` construction allows you to test a condition at either the beginning or the end of a loop structure.</span></span> <span data-ttu-id="cffda-112">Можно также указать, следует ли повторять цикл, пока условие остается, `True` или пока не станет `True` .</span><span class="sxs-lookup"><span data-stu-id="cffda-112">You can also specify whether to repeat the loop while the condition remains `True` or until it becomes `True`.</span></span> <span data-ttu-id="cffda-113">Дополнительные сведения см. в разделе [Do... Loop, инструкция](../../../language-reference/statements/do-loop-statement.md).</span><span class="sxs-lookup"><span data-stu-id="cffda-113">For more information, see [Do...Loop Statement](../../../language-reference/statements/do-loop-statement.md).</span></span>  
  
## <a name="for-loops"></a><span data-ttu-id="cffda-114">Циклы for</span><span class="sxs-lookup"><span data-stu-id="cffda-114">For Loops</span></span>  
 <span data-ttu-id="cffda-115">`For`Конструкция... `Next` выполняет цикл в заданное число раз.</span><span class="sxs-lookup"><span data-stu-id="cffda-115">The `For`...`Next` construction performs the loop a set number of times.</span></span> <span data-ttu-id="cffda-116">Для наблюдения за повторениями используется управляющая переменная цикла, также называемая *счетчиком*.</span><span class="sxs-lookup"><span data-stu-id="cffda-116">It uses a loop control variable, also called a *counter*, to keep track of the repetitions.</span></span> <span data-ttu-id="cffda-117">Вы указываете начальное и конечное значения для этого счетчика, а также можете указать величину, на которую увеличивается от одного повтора до следующего.</span><span class="sxs-lookup"><span data-stu-id="cffda-117">You specify the starting and ending values for this counter, and you can optionally specify the amount by which it increases from one repetition to the next.</span></span> <span data-ttu-id="cffda-118">Дополнительные сведения см. в разделе [for... Следующий оператор](../../../language-reference/statements/for-next-statement.md).</span><span class="sxs-lookup"><span data-stu-id="cffda-118">For more information, see [For...Next Statement](../../../language-reference/statements/for-next-statement.md).</span></span>  
  
## <a name="for-each-loops"></a><span data-ttu-id="cffda-119">Циклы for each</span><span class="sxs-lookup"><span data-stu-id="cffda-119">For Each Loops</span></span>  
 <span data-ttu-id="cffda-120">`For Each`Конструкция... `Next` выполняет набор инструкций один раз для каждого элемента в коллекции.</span><span class="sxs-lookup"><span data-stu-id="cffda-120">The `For Each`...`Next` construction runs a set of statements once for each element in a collection.</span></span> <span data-ttu-id="cffda-121">Вы указываете управляющую переменную цикла, но не нужно определять начальные или конечные значения для нее.</span><span class="sxs-lookup"><span data-stu-id="cffda-121">You specify the loop control variable, but you do not have to determine starting or ending values for it.</span></span> <span data-ttu-id="cffda-122">Дополнительные сведения см. в разделе [For Each... Следующий оператор](../../../language-reference/statements/for-each-next-statement.md).</span><span class="sxs-lookup"><span data-stu-id="cffda-122">For more information, see [For Each...Next Statement](../../../language-reference/statements/for-each-next-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cffda-123">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="cffda-123">See also</span></span>

- [<span data-ttu-id="cffda-124">Поток управления</span><span class="sxs-lookup"><span data-stu-id="cffda-124">Control Flow</span></span>](index.md)
- [<span data-ttu-id="cffda-125">Структуры решений</span><span class="sxs-lookup"><span data-stu-id="cffda-125">Decision Structures</span></span>](decision-structures.md)
- [<span data-ttu-id="cffda-126">Другие структуры управления</span><span class="sxs-lookup"><span data-stu-id="cffda-126">Other Control Structures</span></span>](other-control-structures.md)
- [<span data-ttu-id="cffda-127">Вложенные структуры управления</span><span class="sxs-lookup"><span data-stu-id="cffda-127">Nested Control Structures</span></span>](nested-control-structures.md)
