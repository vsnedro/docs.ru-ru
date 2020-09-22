---
title: Оператор GoTo
ms.date: 07/20/2015
f1_keywords:
- vb.GoTo
helpviewer_keywords:
- GoTo statement [Visual Basic]
- control flow [Visual Basic], branching
- unconditional branching [Visual Basic]
- branching [Visual Basic]
- branching [Visual Basic], unconditional
- branching [Visual Basic], conditional
- conditional statements [Visual Basic], GoTo statement
- GoTo statement [Visual Basic], syntax
ms.assetid: 313274c2-8ab3-4b9c-9ba3-0fd6798e4f6d
ms.openlocfilehash: 000f6754575bcce6b2d79d85541e755219aca956
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90866616"
---
# <a name="goto-statement"></a><span data-ttu-id="8b4b8-102">Оператор GoTo</span><span class="sxs-lookup"><span data-stu-id="8b4b8-102">GoTo Statement</span></span>

<span data-ttu-id="8b4b8-103">Безусловно подразделяется на указанную строку в процедуре.</span><span class="sxs-lookup"><span data-stu-id="8b4b8-103">Branches unconditionally to a specified line in a procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b4b8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8b4b8-104">Syntax</span></span>  
  
```vb  
GoTo line  
```  
  
## <a name="part"></a><span data-ttu-id="8b4b8-105">Отделение</span><span class="sxs-lookup"><span data-stu-id="8b4b8-105">Part</span></span>  

 `line`  
 <span data-ttu-id="8b4b8-106">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="8b4b8-106">Required.</span></span> <span data-ttu-id="8b4b8-107">Метка любой линии.</span><span class="sxs-lookup"><span data-stu-id="8b4b8-107">Any line label.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8b4b8-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="8b4b8-108">Remarks</span></span>  

 <span data-ttu-id="8b4b8-109">`GoTo`Оператор может создать ветвь только для строк в процедуре, в которой она отображается.</span><span class="sxs-lookup"><span data-stu-id="8b4b8-109">The `GoTo` statement can branch only to lines in the procedure in which it appears.</span></span> <span data-ttu-id="8b4b8-110">Строка должна иметь метку, которая `GoTo` может ссылаться на.</span><span class="sxs-lookup"><span data-stu-id="8b4b8-110">The line must have a line label that `GoTo` can refer to.</span></span> <span data-ttu-id="8b4b8-111">Дополнительные сведения см. [в разделе инструкции. Метки](../../programming-guide/program-structure/how-to-label-statements.md).</span><span class="sxs-lookup"><span data-stu-id="8b4b8-111">For more information, see [How to: Label Statements](../../programming-guide/program-structure/how-to-label-statements.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8b4b8-112">`GoTo` инструкции могут усложнить чтение и поддержку кода.</span><span class="sxs-lookup"><span data-stu-id="8b4b8-112">`GoTo` statements can make code difficult to read and maintain.</span></span> <span data-ttu-id="8b4b8-113">Везде, где это возможно, следует использовать структуру элементов управления.</span><span class="sxs-lookup"><span data-stu-id="8b4b8-113">Whenever possible, use a control structure instead.</span></span> <span data-ttu-id="8b4b8-114">Дополнительные сведения см. в разделе [Поток управления](../../programming-guide/language-features/control-flow/index.md).</span><span class="sxs-lookup"><span data-stu-id="8b4b8-114">For more information, see [Control Flow](../../programming-guide/language-features/control-flow/index.md).</span></span>  
  
 <span data-ttu-id="8b4b8-115">Нельзя использовать `GoTo` оператор для ветвления извне `For` ... `Next` , `For Each` ... `Next` , `SyncLock` ... `End SyncLock` , `Try` . `Catch` .. ... `Finally` , `With` ... `End With` или `Using` ... `End Using` конструкция к метке внутри.</span><span class="sxs-lookup"><span data-stu-id="8b4b8-115">You cannot use a `GoTo` statement to branch from outside a `For`...`Next`, `For Each`...`Next`, `SyncLock`...`End SyncLock`, `Try`...`Catch`...`Finally`, `With`...`End With`, or `Using`...`End Using` construction to a label inside.</span></span>  
  
## <a name="branching-and-try-constructions"></a><span data-ttu-id="8b4b8-116">Ветвление и конструкции try</span><span class="sxs-lookup"><span data-stu-id="8b4b8-116">Branching and Try Constructions</span></span>  

 <span data-ttu-id="8b4b8-117">В `Try` ... `Catch` ...`Finally` для создания ветвления с помощью оператора применяются следующие правила `GoTo` .</span><span class="sxs-lookup"><span data-stu-id="8b4b8-117">Within a `Try`...`Catch`...`Finally` construction, the following rules apply to branching with the `GoTo` statement.</span></span>  
  
|<span data-ttu-id="8b4b8-118">Блок или область</span><span class="sxs-lookup"><span data-stu-id="8b4b8-118">Block or region</span></span>|<span data-ttu-id="8b4b8-119">Ветвление вне</span><span class="sxs-lookup"><span data-stu-id="8b4b8-119">Branching in from outside</span></span>|<span data-ttu-id="8b4b8-120">Ветвление из внутрь</span><span class="sxs-lookup"><span data-stu-id="8b4b8-120">Branching out from inside</span></span>|  
|---------------------|-------------------------------|-------------------------------|  
|<span data-ttu-id="8b4b8-121">Блок `Try`</span><span class="sxs-lookup"><span data-stu-id="8b4b8-121">`Try` block</span></span>|<span data-ttu-id="8b4b8-122">Только из `Catch` блока одной конструкции <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="8b4b8-122">Only from a `Catch` block of the same construction <sup>1</sup></span></span>|<span data-ttu-id="8b4b8-123">Только за пределами всей конструкции</span><span class="sxs-lookup"><span data-stu-id="8b4b8-123">Only to outside the whole construction</span></span>|  
|<span data-ttu-id="8b4b8-124">Блок `Catch`</span><span class="sxs-lookup"><span data-stu-id="8b4b8-124">`Catch` block</span></span>|<span data-ttu-id="8b4b8-125">Никогда не разрешено</span><span class="sxs-lookup"><span data-stu-id="8b4b8-125">Never allowed</span></span>|<span data-ttu-id="8b4b8-126">Только за пределами всей конструкции или с `Try` блоком той же конструкции <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="8b4b8-126">Only to outside the whole construction, or to the `Try` block of the same construction <sup>1</sup></span></span>|  
|<span data-ttu-id="8b4b8-127">Блок `Finally`</span><span class="sxs-lookup"><span data-stu-id="8b4b8-127">`Finally` block</span></span>|<span data-ttu-id="8b4b8-128">Никогда не разрешено</span><span class="sxs-lookup"><span data-stu-id="8b4b8-128">Never allowed</span></span>|<span data-ttu-id="8b4b8-129">Никогда не разрешено</span><span class="sxs-lookup"><span data-stu-id="8b4b8-129">Never allowed</span></span>|  
  
 <span data-ttu-id="8b4b8-130"><sup>1</sup> , если один `Try` ... `Catch` ...`Finally` Конструкция вложена в другую, `Catch` блок может выполнять ветвление в `Try` блок на своем собственном уровне вложенности, но не в другой `Try` блок.</span><span class="sxs-lookup"><span data-stu-id="8b4b8-130"><sup>1</sup> If one `Try`...`Catch`...`Finally` construction is nested within another, a `Catch` block can branch into the `Try` block at its own nesting level, but not into any other `Try` block.</span></span> <span data-ttu-id="8b4b8-131">Вложенный `Try` ... `Catch` ...`Finally` конструкция должна полностью содержаться в `Try` `Catch` блоке или конструкции, внутри которой она вложена.</span><span class="sxs-lookup"><span data-stu-id="8b4b8-131">A nested `Try`...`Catch`...`Finally` construction must be contained completely in a `Try` or `Catch` block of the construction within which it is nested.</span></span>  
  
 <span data-ttu-id="8b4b8-132">На следующем рисунке показана одна `Try` конструкция, вложенная в другую.</span><span class="sxs-lookup"><span data-stu-id="8b4b8-132">The following illustration shows one `Try` construction nested within another.</span></span> <span data-ttu-id="8b4b8-133">Различные ветви между блоками двух конструкций указываются как допустимые или недопустимые.</span><span class="sxs-lookup"><span data-stu-id="8b4b8-133">Various branches among the blocks of the two constructions are indicated as valid or invalid.</span></span>  
  
 ![Графическая схема ветвления в конструкциях Try](./media/goto-statement/try-construction-branching.gif)  
  
## <a name="example"></a><span data-ttu-id="8b4b8-135">Пример</span><span class="sxs-lookup"><span data-stu-id="8b4b8-135">Example</span></span>  

 <span data-ttu-id="8b4b8-136">В следующем примере оператор используется `GoTo` для перехода к меткам линии в процедуре.</span><span class="sxs-lookup"><span data-stu-id="8b4b8-136">The following example uses the `GoTo` statement to branch to line labels in a procedure.</span></span>  
  
 [!code-vb[VbVbalrStatements#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#31)]  
  
## <a name="see-also"></a><span data-ttu-id="8b4b8-137">См. также</span><span class="sxs-lookup"><span data-stu-id="8b4b8-137">See also</span></span>

- [<span data-ttu-id="8b4b8-138">Оператор Do…Loop</span><span class="sxs-lookup"><span data-stu-id="8b4b8-138">Do...Loop Statement</span></span>](do-loop-statement.md)
- [<span data-ttu-id="8b4b8-139">Оператор For…Next</span><span class="sxs-lookup"><span data-stu-id="8b4b8-139">For...Next Statement</span></span>](for-next-statement.md)
- [<span data-ttu-id="8b4b8-140">Оператор For Each…Next</span><span class="sxs-lookup"><span data-stu-id="8b4b8-140">For Each...Next Statement</span></span>](for-each-next-statement.md)
- [<span data-ttu-id="8b4b8-141">Оператор If…Then…Else</span><span class="sxs-lookup"><span data-stu-id="8b4b8-141">If...Then...Else Statement</span></span>](if-then-else-statement.md)
- [<span data-ttu-id="8b4b8-142">Оператор Select…Case</span><span class="sxs-lookup"><span data-stu-id="8b4b8-142">Select...Case Statement</span></span>](select-case-statement.md)
- [<span data-ttu-id="8b4b8-143">Оператор Try…Catch…Finally</span><span class="sxs-lookup"><span data-stu-id="8b4b8-143">Try...Catch...Finally Statement</span></span>](try-catch-finally-statement.md)
- [<span data-ttu-id="8b4b8-144">Оператор While…End While</span><span class="sxs-lookup"><span data-stu-id="8b4b8-144">While...End While Statement</span></span>](while-end-while-statement.md)
- [<span data-ttu-id="8b4b8-145">Оператор With…End With</span><span class="sxs-lookup"><span data-stu-id="8b4b8-145">With...End With Statement</span></span>](with-end-with-statement.md)
