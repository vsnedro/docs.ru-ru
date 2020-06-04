---
title: Практическое руководство. Создание процедуры, возвращающей значение
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedures [Visual Basic], returning a value
ms.assetid: 8ee19f95-a9ef-4033-963b-d224dca207c4
ms.openlocfilehash: 2655aba6ce37be831d8dd4202ffd484cfd3fd5ef
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84388353"
---
# <a name="how-to-create-a-procedure-that-returns-a-value-visual-basic"></a><span data-ttu-id="a6d4c-102">Практическое руководство. Создание процедуры, возвращающей значение (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a6d4c-102">How to: Create a Procedure that Returns a Value (Visual Basic)</span></span>
<span data-ttu-id="a6d4c-103">Для `Function` возврата значения в вызывающий код используется процедура.</span><span class="sxs-lookup"><span data-stu-id="a6d4c-103">You use a `Function` procedure to return a value to the calling code.</span></span>  
  
### <a name="to-create-a-procedure-that-returns-a-value"></a><span data-ttu-id="a6d4c-104">Создание процедуры, возвращающей значение</span><span class="sxs-lookup"><span data-stu-id="a6d4c-104">To create a procedure that returns a value</span></span>  
  
1. <span data-ttu-id="a6d4c-105">За пределами любой другой процедуры используйте `Function` оператор, за которым следует `End Function` оператор.</span><span class="sxs-lookup"><span data-stu-id="a6d4c-105">Outside any other procedure, use a `Function` statement, followed by an `End Function` statement.</span></span>  
  
2. <span data-ttu-id="a6d4c-106">В `Function` инструкции используйте `Function` ключевое слово с именем процедуры, а затем список параметров в круглых скобках.</span><span class="sxs-lookup"><span data-stu-id="a6d4c-106">In the `Function` statement, follow the `Function` keyword with the name of the procedure, and then the parameter list in parentheses.</span></span>  
  
3. <span data-ttu-id="a6d4c-107">Используйте круглые скобки с `As` предложением, чтобы указать тип данных возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="a6d4c-107">Follow the parentheses with an `As` clause to specify the data type of the returned value.</span></span>  
  
4. <span data-ttu-id="a6d4c-108">Поместите операторы кода процедуры между `Function` `End Function` операторами и.</span><span class="sxs-lookup"><span data-stu-id="a6d4c-108">Place the procedure's code statements between the `Function` and `End Function` statements.</span></span>  
  
5. <span data-ttu-id="a6d4c-109">Используйте `Return` оператор, чтобы вернуть значение в вызывающий код.</span><span class="sxs-lookup"><span data-stu-id="a6d4c-109">Use a `Return` statement to return the value to the calling code.</span></span>  
  
     <span data-ttu-id="a6d4c-110">Следующая `Function` процедура вычисляет самую длинную сторону (гипотенузу) правого треугольника, учитывая значения двух других сторон.</span><span class="sxs-lookup"><span data-stu-id="a6d4c-110">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, given the values for the other two sides.</span></span>  
  
     [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]  
  
     <span data-ttu-id="a6d4c-111">В следующем примере показан типичный вызов метода `hypotenuse` .</span><span class="sxs-lookup"><span data-stu-id="a6d4c-111">The following example shows a typical call to `hypotenuse`.</span></span>  
  
     [!code-vb[VbVbcnProcedures#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="a6d4c-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="a6d4c-112">See also</span></span>

- [<span data-ttu-id="a6d4c-113">Процедуры</span><span class="sxs-lookup"><span data-stu-id="a6d4c-113">Procedures</span></span>](./index.md)
- [<span data-ttu-id="a6d4c-114">Подпрограммы</span><span class="sxs-lookup"><span data-stu-id="a6d4c-114">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="a6d4c-115">Процедуры свойств</span><span class="sxs-lookup"><span data-stu-id="a6d4c-115">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="a6d4c-116">Процедуры операторов</span><span class="sxs-lookup"><span data-stu-id="a6d4c-116">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="a6d4c-117">Параметры и аргументы процедуры</span><span class="sxs-lookup"><span data-stu-id="a6d4c-117">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="a6d4c-118">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="a6d4c-118">Function Statement</span></span>](../../../language-reference/statements/function-statement.md)
- [<span data-ttu-id="a6d4c-119">Практическое руководство. Возврат значения из процедуры</span><span class="sxs-lookup"><span data-stu-id="a6d4c-119">How to: Return a Value from a Procedure</span></span>](./how-to-return-a-value-from-a-procedure.md)
- [<span data-ttu-id="a6d4c-120">Практическое руководство. Вызов процедуры, возвращающей значение</span><span class="sxs-lookup"><span data-stu-id="a6d4c-120">How to: Call a Procedure That Returns a Value</span></span>](./how-to-call-a-procedure-that-returns-a-value.md)
