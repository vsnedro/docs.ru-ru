---
title: Практическое руководство. Вызов процедуры, возвращающей значение
ms.date: 07/20/2015
helpviewer_keywords:
- procedure calls [Visual Basic], returning values
- Visual Basic code, procedures
- procedures [Visual Basic], calling
- procedures [Visual Basic], returning a value
ms.assetid: a445127b-0f5f-465a-98fb-3e514b93d115
ms.openlocfilehash: a110cf9f3b42c7244d8d5bf7b49d5e6dac8c2e21
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84388768"
---
# <a name="how-to-call-a-procedure-that-returns-a-value-visual-basic"></a><span data-ttu-id="bee66-102">Практическое руководство. Вызов процедуры, возвращающей значение (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bee66-102">How to: Call a Procedure That Returns a Value (Visual Basic)</span></span>
<span data-ttu-id="bee66-103">`Function`Процедура возвращает значение в вызывающий код.</span><span class="sxs-lookup"><span data-stu-id="bee66-103">A `Function` procedure returns a value to the calling code.</span></span> <span data-ttu-id="bee66-104">Его можно вызвать, указав его имя и аргументы в правой части оператора присваивания или в выражении.</span><span class="sxs-lookup"><span data-stu-id="bee66-104">You call it by including its name and arguments either on the right side of an assignment statement or in an expression.</span></span>  
  
### <a name="to-call-a-function-procedure-within-an-expression"></a><span data-ttu-id="bee66-105">Вызов процедуры Function в выражении</span><span class="sxs-lookup"><span data-stu-id="bee66-105">To call a Function procedure within an expression</span></span>  
  
1. <span data-ttu-id="bee66-106">Используйте `Function` имя процедуры так же, как и переменную.</span><span class="sxs-lookup"><span data-stu-id="bee66-106">Use the `Function` procedure name the same way you would use a variable.</span></span> <span data-ttu-id="bee66-107">Можно использовать `Function` вызов процедуры в любом месте, где можно использовать переменную или константу в выражении.</span><span class="sxs-lookup"><span data-stu-id="bee66-107">You can use a `Function` procedure call anywhere you can use a variable or constant in an expression.</span></span>  
  
2. <span data-ttu-id="bee66-108">Чтобы заключить список аргументов, выполните имя процедуры с круглыми скобками.</span><span class="sxs-lookup"><span data-stu-id="bee66-108">Follow the procedure name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="bee66-109">Если аргументы отсутствуют, можно дополнительно опустить круглые скобки.</span><span class="sxs-lookup"><span data-stu-id="bee66-109">If there are no arguments, you can optionally omit the parentheses.</span></span> <span data-ttu-id="bee66-110">Однако использование круглых скобок упрощает чтение кода.</span><span class="sxs-lookup"><span data-stu-id="bee66-110">However, using the parentheses makes your code easier to read.</span></span>  
  
3. <span data-ttu-id="bee66-111">Поместите аргументы в список аргументов в круглых скобках, разделяя их запятыми.</span><span class="sxs-lookup"><span data-stu-id="bee66-111">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="bee66-112">Убедитесь, что аргументы указываются в том же порядке, в котором `Function` процедура определяет соответствующие параметры.</span><span class="sxs-lookup"><span data-stu-id="bee66-112">Be sure you supply the arguments in the same order that the `Function` procedure defines the corresponding parameters.</span></span>  
  
     <span data-ttu-id="bee66-113">Кроме того, можно передать один или несколько аргументов по имени.</span><span class="sxs-lookup"><span data-stu-id="bee66-113">Alternatively, you can pass one or more arguments by name.</span></span> <span data-ttu-id="bee66-114">Дополнительные сведения см. в разделе [Передача аргументов по положению и по имени](./passing-arguments-by-position-and-by-name.md).</span><span class="sxs-lookup"><span data-stu-id="bee66-114">For more information, see [Passing Arguments by Position and by Name](./passing-arguments-by-position-and-by-name.md).</span></span>  
  
4. <span data-ttu-id="bee66-115">Значение, возвращаемое процедурой, участвует в выражении точно так же, как значение переменной или константы.</span><span class="sxs-lookup"><span data-stu-id="bee66-115">The value returned from the procedure participates in the expression just as the value of a variable or constant would.</span></span>  
  
### <a name="to-call-a-function-procedure-in-an-assignment-statement"></a><span data-ttu-id="bee66-116">Вызов процедуры Function в операторе присваивания</span><span class="sxs-lookup"><span data-stu-id="bee66-116">To call a Function procedure in an assignment statement</span></span>  
  
1. <span data-ttu-id="bee66-117">Используйте `Function` имя процедуры после знака равенства ( `=` ) в операторе присваивания.</span><span class="sxs-lookup"><span data-stu-id="bee66-117">Use the `Function` procedure name following the equal (`=`) sign in the assignment statement.</span></span>  
  
2. <span data-ttu-id="bee66-118">Чтобы заключить список аргументов, выполните имя процедуры с круглыми скобками.</span><span class="sxs-lookup"><span data-stu-id="bee66-118">Follow the procedure name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="bee66-119">Если аргументы отсутствуют, можно дополнительно опустить круглые скобки.</span><span class="sxs-lookup"><span data-stu-id="bee66-119">If there are no arguments, you can optionally omit the parentheses.</span></span> <span data-ttu-id="bee66-120">Однако использование круглых скобок упрощает чтение кода.</span><span class="sxs-lookup"><span data-stu-id="bee66-120">However, using the parentheses makes your code easier to read.</span></span>  
  
3. <span data-ttu-id="bee66-121">Поместите аргументы в список аргументов в круглых скобках, разделяя их запятыми.</span><span class="sxs-lookup"><span data-stu-id="bee66-121">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="bee66-122">Убедитесь, что аргументы указываются в том же порядке, в котором `Function` процедура определяет соответствующие параметры, если не передать их по имени.</span><span class="sxs-lookup"><span data-stu-id="bee66-122">Be sure you supply the arguments in the same order that the `Function` procedure defines the corresponding parameters, unless you are passing them by name.</span></span>  
  
4. <span data-ttu-id="bee66-123">Значение, возвращаемое процедурой, хранится в переменной или свойстве в левой части оператора присваивания.</span><span class="sxs-lookup"><span data-stu-id="bee66-123">The value returned from the procedure is stored in the variable or property on the left side of the assignment statement.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bee66-124">Пример</span><span class="sxs-lookup"><span data-stu-id="bee66-124">Example</span></span>  
 <span data-ttu-id="bee66-125">В следующем примере вызывается Visual Basic <xref:Microsoft.VisualBasic.Interaction.Environ%2A> для получения значения переменной среды операционной системы.</span><span class="sxs-lookup"><span data-stu-id="bee66-125">The following example calls the Visual Basic <xref:Microsoft.VisualBasic.Interaction.Environ%2A> to retrieve the value of an operating system environment variable.</span></span> <span data-ttu-id="bee66-126">Первая строка вызывает `Environ` в выражении, а вторая строка вызывает его в операторе присваивания.</span><span class="sxs-lookup"><span data-stu-id="bee66-126">The first line calls `Environ` within an expression, and the second line calls it in an assignment statement.</span></span> <span data-ttu-id="bee66-127">`Environ`принимает имя переменной в качестве единственного аргумента.</span><span class="sxs-lookup"><span data-stu-id="bee66-127">`Environ` takes the variable name as its sole argument.</span></span> <span data-ttu-id="bee66-128">Он возвращает значение переменной в вызывающий код.</span><span class="sxs-lookup"><span data-stu-id="bee66-128">It returns the variable's value to the calling code.</span></span>  
  
 [!code-vb[VbVbcnProcedures#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="bee66-129">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="bee66-129">See also</span></span>

- [<span data-ttu-id="bee66-130">Процедуры функций</span><span class="sxs-lookup"><span data-stu-id="bee66-130">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="bee66-131">Параметры и аргументы процедуры</span><span class="sxs-lookup"><span data-stu-id="bee66-131">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="bee66-132">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="bee66-132">Function Statement</span></span>](../../../language-reference/statements/function-statement.md)
- [<span data-ttu-id="bee66-133">Практическое руководство. Создание процедуры, возвращающей значение</span><span class="sxs-lookup"><span data-stu-id="bee66-133">How to: Create a Procedure that Returns a Value</span></span>](./how-to-create-a-procedure-that-returns-a-value.md)
- [<span data-ttu-id="bee66-134">Практическое руководство. Возврат значения из процедуры</span><span class="sxs-lookup"><span data-stu-id="bee66-134">How to: Return a Value from a Procedure</span></span>](./how-to-return-a-value-from-a-procedure.md)
- [<span data-ttu-id="bee66-135">Практическое руководство. Вызов процедуры, которая не возвращает значение</span><span class="sxs-lookup"><span data-stu-id="bee66-135">How to: Call a Procedure that Does Not Return a Value</span></span>](./how-to-call-a-procedure-that-does-not-return-a-value.md)
