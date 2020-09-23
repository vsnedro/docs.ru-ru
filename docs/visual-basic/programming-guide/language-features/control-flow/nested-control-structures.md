---
title: Вложенные структуры управления
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, control flow
- control structures [Visual Basic], nested
- conditional statements [Visual Basic], nested
- statements [Visual Basic], control flow
- control flow [Visual Basic], nested control statements
- structures [Visual Basic], nested control
- nested control statements [Visual Basic]
ms.assetid: cf60b061-65d9-44a8-81f2-b0bdccd23a05
ms.openlocfilehash: 290366d9d9428cefee108ac472fbe7c0eb66d82e
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91084168"
---
# <a name="nested-control-structures-visual-basic"></a><span data-ttu-id="7394d-102">Вложенные структуры управления (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7394d-102">Nested Control Structures (Visual Basic)</span></span>

<span data-ttu-id="7394d-103">Можно разместить управляющие операторы внутри других операторов управления, например `If...Then...Else` блока внутри `For...Next` цикла.</span><span class="sxs-lookup"><span data-stu-id="7394d-103">You can place control statements inside other control statements, for example an `If...Then...Else` block within a `For...Next` loop.</span></span> <span data-ttu-id="7394d-104">Оператор управления, помещенный внутрь другой управляющей инструкции, называется *вложенным*.</span><span class="sxs-lookup"><span data-stu-id="7394d-104">A control statement placed inside another control statement is said to be *nested*.</span></span>  
  
## <a name="nesting-levels"></a><span data-ttu-id="7394d-105">Уровни вложенности</span><span class="sxs-lookup"><span data-stu-id="7394d-105">Nesting Levels</span></span>  

 <span data-ttu-id="7394d-106">Структуры управления в Visual Basic могут быть вложены на столько уровней, сколько нужно.</span><span class="sxs-lookup"><span data-stu-id="7394d-106">Control structures in Visual Basic can be nested to as many levels as you want.</span></span> <span data-ttu-id="7394d-107">Распространенной практикой является более удобочитаемость вложенных структур путем создания отступов для текста каждой из них.</span><span class="sxs-lookup"><span data-stu-id="7394d-107">It is common practice to make nested structures more readable by indenting the body of each one.</span></span> <span data-ttu-id="7394d-108">Редактор интегрированной среды разработки (IDE) автоматически делает это.</span><span class="sxs-lookup"><span data-stu-id="7394d-108">The integrated development environment (IDE) editor automatically does this.</span></span>  
  
 <span data-ttu-id="7394d-109">В следующем примере процедура `sumRows` добавляет вместе положительные элементы каждой строки матрицы.</span><span class="sxs-lookup"><span data-stu-id="7394d-109">In the following example, the procedure `sumRows` adds together the positive elements of each row of the matrix.</span></span>  
  
```vb
Public Sub sumRows(ByVal a(,) As Double, ByRef r() As Double)  
    Dim i, j As Integer  
    For i = 0 To UBound(a, 1)  
        r(i) = 0  
        For j = 0 To UBound(a, 2)  
            If a(i, j) > 0 Then  
                r(i) = r(i) + a(i, j)  
            End If  
        Next j  
    Next i  
End Sub  
```  
  
 <span data-ttu-id="7394d-110">В предыдущем примере первая `Next` инструкция закрывает внутренний `For` цикл, а последняя `Next` инструкция закрывает внешний `For` цикл.</span><span class="sxs-lookup"><span data-stu-id="7394d-110">In the preceding example, the first `Next` statement closes the inner `For` loop and the last `Next` statement closes the outer `For` loop.</span></span>  
  
 <span data-ttu-id="7394d-111">Аналогично, в вложенных `If` инструкциях `End If` инструкции автоматически применяются к ближайшей предыдущей `If` инструкции.</span><span class="sxs-lookup"><span data-stu-id="7394d-111">Likewise, in nested `If` statements, the `End If` statements automatically apply to the nearest prior `If` statement.</span></span> <span data-ttu-id="7394d-112">Вложенные `Do` циклы работают аналогичным образом с самой внутренней `Loop` инструкцией, соответствующей самой внутренней `Do` инструкции.</span><span class="sxs-lookup"><span data-stu-id="7394d-112">Nested `Do` loops work in a similar fashion, with the innermost `Loop` statement matching the innermost `Do` statement.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7394d-113">Для многих структур управления при щелчке ключевого слова все ключевые слова в структуре выделяются.</span><span class="sxs-lookup"><span data-stu-id="7394d-113">For many control structures, when you click a keyword, all of the keywords in the structure are highlighted.</span></span> <span data-ttu-id="7394d-114">Например, если щелкнуть `If` `If...Then...Else` конструкцию, `If` будут выделены все экземпляры,,, `Then` `ElseIf` `Else` и `End If` в конструкции.</span><span class="sxs-lookup"><span data-stu-id="7394d-114">For instance, when you click `If` in an `If...Then...Else` construction, all instances of `If`, `Then`, `ElseIf`, `Else`, and `End If` in the construction are highlighted.</span></span> <span data-ttu-id="7394d-115">Чтобы перейти к следующему или предыдущему выделенному ключевому слову, нажмите клавиши CTRL + SHIFT + стрелка вниз или CTRL + SHIFT + стрелка вверх.</span><span class="sxs-lookup"><span data-stu-id="7394d-115">To move to the next or previous highlighted keyword, press CTRL+SHIFT+DOWN ARROW or CTRL+SHIFT+UP ARROW.</span></span>  
  
## <a name="nesting-different-kinds-of-control-structures"></a><span data-ttu-id="7394d-116">Вложение различных видов структур управления</span><span class="sxs-lookup"><span data-stu-id="7394d-116">Nesting Different Kinds of Control Structures</span></span>  

 <span data-ttu-id="7394d-117">Один тип структуры управления можно вложить в другой тип.</span><span class="sxs-lookup"><span data-stu-id="7394d-117">You can nest one kind of control structure within another kind.</span></span> <span data-ttu-id="7394d-118">В следующем примере используется `With` блок внутри `For Each` цикла и вложенные `If` блоки внутри `With` блока.</span><span class="sxs-lookup"><span data-stu-id="7394d-118">The following example uses a `With` block inside a `For Each` loop and nested `If` blocks inside the `With` block.</span></span>  
  
```vb
For Each ctl As System.Windows.Forms.Control In Me.Controls  
    With ctl  
        .BackColor = System.Drawing.Color.Yellow  
        .ForeColor = System.Drawing.Color.Black  
        If .CanFocus Then  
            .Text = "Colors changed"  
            If Not .Focus() Then  
                ' Insert code to process failed focus.  
            End If  
        End If  
    End With  
Next ctl  
```  
  
## <a name="overlapping-control-structures"></a><span data-ttu-id="7394d-119">Перекрывающиеся структуры элементов управления</span><span class="sxs-lookup"><span data-stu-id="7394d-119">Overlapping Control Structures</span></span>  

 <span data-ttu-id="7394d-120">Нельзя перекрывать структуры управления.</span><span class="sxs-lookup"><span data-stu-id="7394d-120">You cannot overlap control structures.</span></span> <span data-ttu-id="7394d-121">Это означает, что любая вложенная структура должна полностью содержаться в следующей самой внутренней структуре.</span><span class="sxs-lookup"><span data-stu-id="7394d-121">This means that any nested structure must be completely contained within the next innermost structure.</span></span> <span data-ttu-id="7394d-122">Например, следующее расположение недопустимо, так как `For` цикл завершается до `With` завершения внутреннего блока.</span><span class="sxs-lookup"><span data-stu-id="7394d-122">For example, the following arrangement is invalid because the `For` loop terminates before the inner `With` block terminates.</span></span>  
  
 ![Схема, на которой показан пример недопустимого вложения.](./media/nested-control-structures/example-invalid-nesting.gif)
  
 <span data-ttu-id="7394d-124">Компилятор Visual Basic обнаруживает такие перекрывающиеся структуры элементов управления и сигнализирует об ошибке во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="7394d-124">The Visual Basic compiler detects such overlapping control structures and signals a compile-time error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7394d-125">См. также</span><span class="sxs-lookup"><span data-stu-id="7394d-125">See also</span></span>

- [<span data-ttu-id="7394d-126">Поток управления</span><span class="sxs-lookup"><span data-stu-id="7394d-126">Control Flow</span></span>](index.md)
- [<span data-ttu-id="7394d-127">Структуры решений</span><span class="sxs-lookup"><span data-stu-id="7394d-127">Decision Structures</span></span>](decision-structures.md)
- [<span data-ttu-id="7394d-128">Циклические структуры</span><span class="sxs-lookup"><span data-stu-id="7394d-128">Loop Structures</span></span>](loop-structures.md)
- [<span data-ttu-id="7394d-129">Другие структуры управления</span><span class="sxs-lookup"><span data-stu-id="7394d-129">Other Control Structures</span></span>](other-control-structures.md)
