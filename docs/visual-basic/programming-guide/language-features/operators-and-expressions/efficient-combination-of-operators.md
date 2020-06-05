---
title: Эффективное сочетание операторов
ms.date: 07/20/2015
helpviewer_keywords:
- expressions [Visual Basic], parentheses
- operators [Visual Basic], associativity
- expressions [Visual Basic], operators
- operators [Visual Basic], precedence
- Visual Basic code, operators
- Visual Basic code, expressions
- operators [Visual Basic], complex expressions
- expressions [Visual Basic], complex
- parentheses [Visual Basic], complex expressions
- numeric expressions
ms.assetid: bd22340e-b5be-458b-8772-3916c02309a4
ms.openlocfilehash: 3088072646278dac13e4d483cb4f99297eaad9ca
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403476"
---
# <a name="efficient-combination-of-operators-visual-basic"></a><span data-ttu-id="c08af-102">Эффективное сочетание операторов (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c08af-102">Efficient Combination of Operators (Visual Basic)</span></span>
<span data-ttu-id="c08af-103">Сложные выражения могут содержать множество различных операторов.</span><span class="sxs-lookup"><span data-stu-id="c08af-103">Complex expressions can contain many different operators.</span></span> <span data-ttu-id="c08af-104">Это показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="c08af-104">The following example illustrates this.</span></span>  
  
 `x = (45 * (y + z)) ^ (2 / 85) * 5 + z`  
  
 <span data-ttu-id="c08af-105">Создание сложных выражений, например, в предыдущем примере, требует тщательного понимания правил приоритета операторов.</span><span class="sxs-lookup"><span data-stu-id="c08af-105">Creating complex expressions such as the one in the preceding example requires a thorough understanding of the rules of operator precedence.</span></span> <span data-ttu-id="c08af-106">Дополнительные сведения см. [в разделе приоритет операторов в Visual Basic](../../../language-reference/operators/operator-precedence.md).</span><span class="sxs-lookup"><span data-stu-id="c08af-106">For more information, see [Operator Precedence in Visual Basic](../../../language-reference/operators/operator-precedence.md).</span></span>  
  
## <a name="parenthetical-expressions"></a><span data-ttu-id="c08af-107">Выражения в скобках</span><span class="sxs-lookup"><span data-stu-id="c08af-107">Parenthetical Expressions</span></span>  
 <span data-ttu-id="c08af-108">Часто требуется, чтобы операции продвигается в порядке, отличном от того, который определяется приоритетом операторов.</span><span class="sxs-lookup"><span data-stu-id="c08af-108">Often you want operations to proceed in a different order from that determined by operator precedence.</span></span> <span data-ttu-id="c08af-109">Рассмотрим следующий пример.</span><span class="sxs-lookup"><span data-stu-id="c08af-109">Consider the following example.</span></span>  
  
 `x = z * y + 4`  
  
 <span data-ttu-id="c08af-110">Предыдущий пример умножается на `z` `y` , а затем добавляет результат в `4` .</span><span class="sxs-lookup"><span data-stu-id="c08af-110">The preceding example multiplies `z` by `y`, then adds the result to `4`.</span></span> <span data-ttu-id="c08af-111">Но если вы хотите добавить `y` и `4` перед умножением результата на `z` , можно переопределить нормальный приоритет операторов с помощью круглых скобок.</span><span class="sxs-lookup"><span data-stu-id="c08af-111">But if you want to add `y` and `4` before multiplying the result by `z`, you can override normal operator precedence by using parentheses.</span></span> <span data-ttu-id="c08af-112">Заключив выражение в круглые скобки, вы принудительно выдаете выражение первым, независимо от приоритета операторов.</span><span class="sxs-lookup"><span data-stu-id="c08af-112">By enclosing an expression in parentheses, you force that expression to be evaluated first, regardless of operator precedence.</span></span> <span data-ttu-id="c08af-113">Чтобы выполнить предыдущий пример для первого добавления, можно переписать его, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="c08af-113">To force the preceding example to do the addition first, you could rewrite it as in the following example.</span></span>  
  
 `x = z * (y + 4)`  
  
 <span data-ttu-id="c08af-114">В предыдущем примере добавляются `y` `4` функции и, а затем вычисляется сумма по `z` .</span><span class="sxs-lookup"><span data-stu-id="c08af-114">The preceding example adds `y` and `4`, then multiplies that sum by `z`.</span></span>  
  
### <a name="nested-parenthetical-expressions"></a><span data-ttu-id="c08af-115">Вложенные выражения в скобках</span><span class="sxs-lookup"><span data-stu-id="c08af-115">Nested Parenthetical Expressions</span></span>  
 <span data-ttu-id="c08af-116">Можно вкладывать выражения на нескольких уровнях круглых скобок для более детального переопределения приоритета.</span><span class="sxs-lookup"><span data-stu-id="c08af-116">You can nest expressions in multiple levels of parentheses to override precedence even further.</span></span> <span data-ttu-id="c08af-117">Выражения, наиболее глубоко вложенные в круглые скобки, сначала оцениваются, за которыми следуют более глубокий уровень вложенности, и так далее, и, наконец, выражения за пределами круглых скобок.</span><span class="sxs-lookup"><span data-stu-id="c08af-117">The expressions most deeply nested in parentheses are evaluated first, followed by the next most deeply nested, and so on to the least deeply nested, and finally the expressions outside parentheses.</span></span> <span data-ttu-id="c08af-118">Это показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="c08af-118">The following example illustrates this.</span></span>  
  
 `x = (z * 4) ^ (y * (z + 2))`  
  
 <span data-ttu-id="c08af-119">В предыдущем примере `z + 2` вычисляется первым, а затем другими выражениями в скобках.</span><span class="sxs-lookup"><span data-stu-id="c08af-119">In the preceding example, `z + 2` is evaluated first, then the other parenthetical expressions.</span></span> <span data-ttu-id="c08af-120">Возведение в степень, которое обычно имеет более высокий приоритет, чем сложение или умножение, в этом примере вычисляется последним, так как другие выражения заключаются в круглые скобки.</span><span class="sxs-lookup"><span data-stu-id="c08af-120">Exponentiation, which normally has higher precedence than addition or multiplication, is evaluated last in this example because the other expressions are enclosed in parentheses.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c08af-121">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="c08af-121">See also</span></span>

- [<span data-ttu-id="c08af-122">Арифметические операторы в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c08af-122">Arithmetic Operators in Visual Basic</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="c08af-123">Comparison Operators in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c08af-123">Comparison Operators in Visual Basic</span></span>](comparison-operators.md)
- [<span data-ttu-id="c08af-124">Логические и побитовые операторы в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c08af-124">Logical and Bitwise Operators in Visual Basic</span></span>](logical-and-bitwise-operators.md)
- [<span data-ttu-id="c08af-125">Логические (побитовые) операторы (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c08af-125">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="c08af-126">Логические выражения</span><span class="sxs-lookup"><span data-stu-id="c08af-126">Boolean Expressions</span></span>](boolean-expressions.md)
- [<span data-ttu-id="c08af-127">Сравнения значений</span><span class="sxs-lookup"><span data-stu-id="c08af-127">Value Comparisons</span></span>](value-comparisons.md)
- [<span data-ttu-id="c08af-128">Практическое руководство. Вычисление числовых значений</span><span class="sxs-lookup"><span data-stu-id="c08af-128">How to: Calculate Numeric Values</span></span>](how-to-calculate-numeric-values.md)
- [<span data-ttu-id="c08af-129">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c08af-129">Operator Precedence in Visual Basic</span></span>](../../../language-reference/operators/operator-precedence.md)
