---
title: Практическое руководство. Возврат значения из процедуры
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], returning from
- procedures [Visual Basic], returning a value
ms.assetid: 4bcc4724-2b4e-4df8-9b4b-16054607f87d
ms.openlocfilehash: 917e52b711645fbf94a132216a3fa90b0dfc15b3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414328"
---
# <a name="how-to-return-a-value-from-a-procedure-visual-basic"></a><span data-ttu-id="5d63e-102">Практическое руководство. Возврат значения из процедуры (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5d63e-102">How to: Return a Value from a Procedure (Visual Basic)</span></span>
<span data-ttu-id="5d63e-103">`Function`Процедура возвращает значение в вызывающий код, выполняя инструкцию или выполняя инструкцию `Return` `Exit Function` или `End Function` .</span><span class="sxs-lookup"><span data-stu-id="5d63e-103">A `Function` procedure returns a value to the calling code either by executing a `Return` statement or by encountering an `Exit Function` or `End Function` statement.</span></span>  
  
### <a name="to-return-a-value-using-the-return-statement"></a><span data-ttu-id="5d63e-104">Возврат значения с помощью оператора return</span><span class="sxs-lookup"><span data-stu-id="5d63e-104">To return a value using the Return statement</span></span>  
  
1. <span data-ttu-id="5d63e-105">Поместите `Return` оператор в точку завершения задачи процедуры.</span><span class="sxs-lookup"><span data-stu-id="5d63e-105">Put a `Return` statement at the point where the procedure's task is completed.</span></span>  
  
2. <span data-ttu-id="5d63e-106">Используйте `Return` ключевое слово с выражением, которое возвращает значение, которое необходимо вернуть в вызывающий код.</span><span class="sxs-lookup"><span data-stu-id="5d63e-106">Follow the `Return` keyword with an expression that yields the value you want to return to the calling code.</span></span>  
  
3. <span data-ttu-id="5d63e-107">В одной и той же процедуре можно использовать несколько операторов `Return`.</span><span class="sxs-lookup"><span data-stu-id="5d63e-107">You can have more than one `Return` statement in the same procedure.</span></span>  
  
     <span data-ttu-id="5d63e-108">Следующая `Function` процедура вычисляет самую длинную сторону (гипотенузу) правого треугольника и возвращает ее в вызывающий код.</span><span class="sxs-lookup"><span data-stu-id="5d63e-108">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, and returns it to the calling code.</span></span>  
  
     [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]  
  
     <span data-ttu-id="5d63e-109">В следующем примере показан типичный вызов метода `hypotenuse` , в котором хранится возвращаемое значение.</span><span class="sxs-lookup"><span data-stu-id="5d63e-109">The following example shows a typical call to `hypotenuse`, which stores the returned value.</span></span>  
  
     [!code-vb[VbVbcnProcedures#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#6)]  
  
### <a name="to-return-a-value-using-exit-function-or-end-function"></a><span data-ttu-id="5d63e-110">Возврат значения с помощью функции exit или функции End</span><span class="sxs-lookup"><span data-stu-id="5d63e-110">To return a value using Exit Function or End Function</span></span>  
  
1. <span data-ttu-id="5d63e-111">По крайней мере в одном месте `Function` процедуры присвойте значение имени процедуры.</span><span class="sxs-lookup"><span data-stu-id="5d63e-111">In at least one place in the `Function` procedure, assign a value to the procedure's name.</span></span>  
  
2. <span data-ttu-id="5d63e-112">При выполнении `Exit Function` `End Function` инструкции или Visual Basic возвращает последнее значение, назначенное имени процедуры.</span><span class="sxs-lookup"><span data-stu-id="5d63e-112">When you execute an `Exit Function` or `End Function` statement, Visual Basic returns the value most recently assigned to the procedure's name.</span></span>  
  
3. <span data-ttu-id="5d63e-113">В одной и той же процедуре можно использовать несколько операторов `Exit Function` и одновременно использовать операторы `Return` и `Exit Function`.</span><span class="sxs-lookup"><span data-stu-id="5d63e-113">You can have more than one `Exit Function` statement in the same procedure, and you can mix `Return` and `Exit Function` statements in the same procedure.</span></span>  
  
4. <span data-ttu-id="5d63e-114">В процедуре может быть только одна `End Function` инструкция `Function` .</span><span class="sxs-lookup"><span data-stu-id="5d63e-114">You can have only one `End Function` statement in a `Function` procedure.</span></span>  
  
     <span data-ttu-id="5d63e-115">Дополнительные сведения и пример см. в разделе "возвращаемое значение" в [операторе Function](../../../language-reference/statements/function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="5d63e-115">For more information and an example, see "Return Value" in [Function Statement](../../../language-reference/statements/function-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d63e-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="5d63e-116">See also</span></span>

- [<span data-ttu-id="5d63e-117">Процедуры</span><span class="sxs-lookup"><span data-stu-id="5d63e-117">Procedures</span></span>](./index.md)
- [<span data-ttu-id="5d63e-118">Подпрограммы</span><span class="sxs-lookup"><span data-stu-id="5d63e-118">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="5d63e-119">Процедуры свойств</span><span class="sxs-lookup"><span data-stu-id="5d63e-119">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="5d63e-120">Процедуры операторов</span><span class="sxs-lookup"><span data-stu-id="5d63e-120">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="5d63e-121">Параметры и аргументы процедуры</span><span class="sxs-lookup"><span data-stu-id="5d63e-121">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="5d63e-122">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="5d63e-122">Function Statement</span></span>](../../../language-reference/statements/function-statement.md)
- [<span data-ttu-id="5d63e-123">Оператор Return</span><span class="sxs-lookup"><span data-stu-id="5d63e-123">Return Statement</span></span>](../../../language-reference/statements/return-statement.md)
- [<span data-ttu-id="5d63e-124">Практическое руководство. Создание процедуры, возвращающей значение</span><span class="sxs-lookup"><span data-stu-id="5d63e-124">How to: Create a Procedure that Returns a Value</span></span>](./how-to-create-a-procedure-that-returns-a-value.md)
- [<span data-ttu-id="5d63e-125">Практическое руководство. Вызов процедуры, возвращающей значение</span><span class="sxs-lookup"><span data-stu-id="5d63e-125">How to: Call a Procedure That Returns a Value</span></span>](./how-to-call-a-procedure-that-returns-a-value.md)
