---
title: Сравнения значений
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], comparing values
- Visual Basic code, operators
- Visual Basic code, expressions
- comparison operators [Visual Basic], comparing expressions
- numeric expressions
- operators [Visual Basic], comparison
- expressions [Visual Basic], comparing
ms.assetid: 60da0c76-9458-4afc-97e9-44a7939c064c
ms.openlocfilehash: e424dd58cada8cda250554a4a8870e1900d0fa7d
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91085975"
---
# <a name="value-comparisons-visual-basic"></a><span data-ttu-id="add44-102">Сравнение значений (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="add44-102">Value Comparisons (Visual Basic)</span></span>

<span data-ttu-id="add44-103">Операторы сравнения можно использовать для создания выражений, которые сравнивают значения числовых переменных.</span><span class="sxs-lookup"><span data-stu-id="add44-103">Comparison operators can be used to construct expressions that compare the values of numeric variables.</span></span> <span data-ttu-id="add44-104">Эти выражения возвращают `Boolean` значение в зависимости от того, имеет ли сравнение значение true или false.</span><span class="sxs-lookup"><span data-stu-id="add44-104">These expressions return a `Boolean` value based on whether the comparison is true or false.</span></span> <span data-ttu-id="add44-105">Ниже приведены примеры таких выражений.</span><span class="sxs-lookup"><span data-stu-id="add44-105">Examples of such an expression are as follows.</span></span>  
  
 `45 > 26`  
  
 `26 > 45`  
  
 <span data-ttu-id="add44-106">Первое выражение принимает значение `True` , так как 45 больше 26.</span><span class="sxs-lookup"><span data-stu-id="add44-106">The first expression evaluates to `True`, because 45 is greater than 26.</span></span> <span data-ttu-id="add44-107">Во втором примере вычисляется значение `False` , поскольку 26 не превышает 45.</span><span class="sxs-lookup"><span data-stu-id="add44-107">The second example evaluates to `False`, because 26 is not greater than 45.</span></span>  
  
 <span data-ttu-id="add44-108">Таким образом можно также сравнить числовые выражения.</span><span class="sxs-lookup"><span data-stu-id="add44-108">You can also compare numeric expressions in this fashion.</span></span> <span data-ttu-id="add44-109">Сравниваемые выражения могут быть сложными выражениями, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="add44-109">The expressions you compare can themselves be complex expressions, as in the following example.</span></span>  
  
 `x / 45 * (y +17) >= System.Math.Sqrt(z) / (p - (x * 16))`  
  
 <span data-ttu-id="add44-110">Предыдущее сложное выражение включает литералы, переменные и вызовы функций.</span><span class="sxs-lookup"><span data-stu-id="add44-110">The preceding complex expression includes literals, variables, and function calls.</span></span> <span data-ttu-id="add44-111">Выражения на обеих сторонах оператора сравнения оцениваются, а результирующие значения сравниваются с помощью `>=` оператора сравнения.</span><span class="sxs-lookup"><span data-stu-id="add44-111">The expressions on both sides of the comparison operator are evaluated, and the resulting values are then compared using the `>=` comparison operator.</span></span> <span data-ttu-id="add44-112">Если значение выражения в левой части больше или равно значению выражения справа, результатом вычисления всего выражения будет `True` ; в противном случае — значение `False` .</span><span class="sxs-lookup"><span data-stu-id="add44-112">If the value of the expression on the left side is greater than or equal to the value of the expression on the right, the entire expression evaluates to `True`; otherwise, it evaluates to `False`.</span></span>  
  
 <span data-ttu-id="add44-113">Выражения, которые сравнивают значения, чаще всего используются в `If...Then` конструкциях, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="add44-113">Expressions that compare values are most commonly used in `If...Then` constructions, as in the following example.</span></span>  
  
 [!code-vb[VbVbalrOperators#84](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#84)]  
  
 <span data-ttu-id="add44-114">`=`Знак является оператором сравнения, а также оператором присваивания.</span><span class="sxs-lookup"><span data-stu-id="add44-114">The `=` sign is a comparison operator as well as an assignment operator.</span></span> <span data-ttu-id="add44-115">При использовании в качестве оператора сравнения он вычисляет, равно ли значение слева значению справа, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="add44-115">When used as a comparison operator, it evaluates whether the value on the left is equal to the value on the right, as shown in the following example.</span></span>  
  
 [!code-vb[VbVbalrOperators#85](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#85)]  
  
 <span data-ttu-id="add44-116">Можно также использовать выражение сравнения в любом месте `Boolean` , где требуется значение, например в `If` `While` операторе,, `Loop` или `ElseIf` , а также при назначении или передаче значения в `Boolean` переменную.</span><span class="sxs-lookup"><span data-stu-id="add44-116">You can also use a comparison expression anywhere a `Boolean` value is needed, such as in an `If`, `While`, `Loop`, or `ElseIf` statement, or when assigning to or passing a value to a `Boolean` variable.</span></span> <span data-ttu-id="add44-117">В следующем примере значение, возвращаемое выражением сравнения, присваивается `Boolean` переменной.</span><span class="sxs-lookup"><span data-stu-id="add44-117">In the following example, the value returned by the comparison expression is assigned to a `Boolean` variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#86](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#86)]  
  
## <a name="see-also"></a><span data-ttu-id="add44-118">См. также</span><span class="sxs-lookup"><span data-stu-id="add44-118">See also</span></span>

- [<span data-ttu-id="add44-119">Логические выражения</span><span class="sxs-lookup"><span data-stu-id="add44-119">Boolean Expressions</span></span>](boolean-expressions.md)
- [<span data-ttu-id="add44-120">Операторы и выражения</span><span class="sxs-lookup"><span data-stu-id="add44-120">Operators and Expressions</span></span>](index.md)
- [<span data-ttu-id="add44-121">Comparison Operators in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="add44-121">Comparison Operators in Visual Basic</span></span>](comparison-operators.md)
- [<span data-ttu-id="add44-122">Практическое руководство. Вычисление числовых значений</span><span class="sxs-lookup"><span data-stu-id="add44-122">How to: Calculate Numeric Values</span></span>](how-to-calculate-numeric-values.md)
- [<span data-ttu-id="add44-123">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="add44-123">Operator Precedence in Visual Basic</span></span>](../../../language-reference/operators/operator-precedence.md)
