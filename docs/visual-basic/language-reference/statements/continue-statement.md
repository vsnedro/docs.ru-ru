---
title: Оператор Continue
ms.date: 07/20/2015
f1_keywords:
- vb.continue
helpviewer_keywords:
- Continue statement [Visual Basic]
- loops, transferring to next iteration
ms.assetid: 3ad00103-358b-4af3-a3a8-1b9ea0e995d3
ms.openlocfilehash: fd604b281a590073a5e76398788d7648cadd145c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84382098"
---
# <a name="continue-statement-visual-basic"></a><span data-ttu-id="5bc1c-102">Оператор Continue (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5bc1c-102">Continue Statement (Visual Basic)</span></span>
<span data-ttu-id="5bc1c-103">Немедленно передает управление следующей итерации цикла.</span><span class="sxs-lookup"><span data-stu-id="5bc1c-103">Transfers control immediately to the next iteration of a loop.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5bc1c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5bc1c-104">Syntax</span></span>  
  
```vb  
Continue { Do | For | While }  
```  
  
## <a name="remarks"></a><span data-ttu-id="5bc1c-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="5bc1c-105">Remarks</span></span>  
 <span data-ttu-id="5bc1c-106">Можно переносить из `Do` `For` цикла, или `While` в следующую итерацию этого цикла.</span><span class="sxs-lookup"><span data-stu-id="5bc1c-106">You can transfer from inside a `Do`, `For`, or `While` loop to the next iteration of that loop.</span></span> <span data-ttu-id="5bc1c-107">Элемент управления сразу же передается в условие цикла, что эквивалентно передаче `For` инструкции или или `While` `Do` `Loop` инструкции или, содержащей `Until` `While` предложение OR.</span><span class="sxs-lookup"><span data-stu-id="5bc1c-107">Control passes immediately to the loop condition test, which is equivalent to transferring to the `For` or `While` statement, or to the `Do` or `Loop` statement that contains the `Until` or `While` clause.</span></span>  
  
 <span data-ttu-id="5bc1c-108">Можно использовать `Continue` в любом расположении в цикле, допускающем передачу данных.</span><span class="sxs-lookup"><span data-stu-id="5bc1c-108">You can use `Continue` at any location in the loop that allows transfers.</span></span> <span data-ttu-id="5bc1c-109">Правила, допускающие перемещение элементов управления, аналогичны [инструкциям оператора goto](goto-statement.md).</span><span class="sxs-lookup"><span data-stu-id="5bc1c-109">The rules allowing transfer of control are the same as with the [GoTo Statement](goto-statement.md).</span></span>  
  
 <span data-ttu-id="5bc1c-110">Например, если цикл полностью содержится в `Try` блоке, `Catch` блоке или `Finally` блоке, можно использовать `Continue` для перемещения цикла.</span><span class="sxs-lookup"><span data-stu-id="5bc1c-110">For example, if a loop is totally contained within a `Try` block, a `Catch` block, or a `Finally` block, you can use `Continue` to transfer out of the loop.</span></span> <span data-ttu-id="5bc1c-111">Если, с другой стороны, `Try` структура... `End Try` содержится в цикле, нельзя использовать `Continue` для передачи управления из `Finally` блока, и ее можно использовать для передачи из `Try` блока или только в том `Catch` случае, если полностью передать из `Try` структуры... `End Try` .</span><span class="sxs-lookup"><span data-stu-id="5bc1c-111">If, on the other hand, the `Try`...`End Try` structure is contained within the loop, you cannot use `Continue` to transfer control out of the `Finally` block, and you can use it to transfer out of a `Try` or `Catch` block only if you transfer completely out of the `Try`...`End Try` structure.</span></span>  
  
 <span data-ttu-id="5bc1c-112">При наличии вложенных циклов одного и того же типа, например `Do` цикла в другом `Do` цикле, `Continue Do` оператор переходит к следующей итерации самого внутреннего `Do` цикла, который его содержит.</span><span class="sxs-lookup"><span data-stu-id="5bc1c-112">If you have nested loops of the same type, for example a `Do` loop within another `Do` loop, a `Continue Do` statement skips to the next iteration of the innermost `Do` loop that contains it.</span></span> <span data-ttu-id="5bc1c-113">Нельзя использовать `Continue` для перехода к следующей итерации содержащего цикла того же типа.</span><span class="sxs-lookup"><span data-stu-id="5bc1c-113">You cannot use `Continue` to skip to the next iteration of a containing loop of the same type.</span></span>  
  
 <span data-ttu-id="5bc1c-114">При наличии вложенных циклов разных типов, например цикла в `Do` `For` цикле, можно перейти к следующей итерации любого цикла, используя либо `Continue Do` или `Continue For` .</span><span class="sxs-lookup"><span data-stu-id="5bc1c-114">If you have nested loops of different types, for example a `Do` loop within a `For` loop, you can skip to the next iteration of either loop by using either `Continue Do` or `Continue For`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5bc1c-115">Пример</span><span class="sxs-lookup"><span data-stu-id="5bc1c-115">Example</span></span>  
 <span data-ttu-id="5bc1c-116">В следующем примере кода инструкция используется `Continue While` для перехода к следующему столбцу массива, если делитель равен нулю.</span><span class="sxs-lookup"><span data-stu-id="5bc1c-116">The following code example uses the `Continue While` statement to skip to the next column of an array if a divisor is zero.</span></span> <span data-ttu-id="5bc1c-117">`Continue While`Находится внутри `For` цикла.</span><span class="sxs-lookup"><span data-stu-id="5bc1c-117">The `Continue While` is inside a `For` loop.</span></span> <span data-ttu-id="5bc1c-118">Он передает `While col < lastcol` оператору, который является следующей итерацией самого внутреннего `While` цикла, содержащего `For` цикл.</span><span class="sxs-lookup"><span data-stu-id="5bc1c-118">It transfers to the `While col < lastcol` statement, which is the next iteration of the innermost `While` loop that contains the `For` loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#14)]  
  
## <a name="see-also"></a><span data-ttu-id="5bc1c-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="5bc1c-119">See also</span></span>

- [<span data-ttu-id="5bc1c-120">Оператор Do…Loop</span><span class="sxs-lookup"><span data-stu-id="5bc1c-120">Do...Loop Statement</span></span>](do-loop-statement.md)
- [<span data-ttu-id="5bc1c-121">Оператор For…Next</span><span class="sxs-lookup"><span data-stu-id="5bc1c-121">For...Next Statement</span></span>](for-next-statement.md)
- [<span data-ttu-id="5bc1c-122">Оператор While…End While</span><span class="sxs-lookup"><span data-stu-id="5bc1c-122">While...End While Statement</span></span>](while-end-while-statement.md)
- [<span data-ttu-id="5bc1c-123">Оператор Try…Catch…Finally</span><span class="sxs-lookup"><span data-stu-id="5bc1c-123">Try...Catch...Finally Statement</span></span>](try-catch-finally-statement.md)
