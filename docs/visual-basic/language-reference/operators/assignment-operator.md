---
title: Оператор =
ms.date: 07/20/2015
f1_keywords:
- vb.Assign
- vb.=
helpviewer_keywords:
- = operator [Visual Basic]
- = assignment statements [Visual Basic]
ms.assetid: 2dac2e49-86c8-42f8-80c1-458452fb5e29
ms.openlocfilehash: eccea0b43564a4980778c9d1a5b8f9a8c2a9207d
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874830"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="7673f-102">Оператор = (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7673f-102">= Operator (Visual Basic)</span></span>

<span data-ttu-id="7673f-103">Присваивает значение переменной или свойству.</span><span class="sxs-lookup"><span data-stu-id="7673f-103">Assigns a value to a variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7673f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7673f-104">Syntax</span></span>  
  
```vb  
variableorproperty = value  
```  
  
## <a name="parts"></a><span data-ttu-id="7673f-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="7673f-105">Parts</span></span>  

 `variableorproperty`  
 <span data-ttu-id="7673f-106">Любая изменяемая переменная или любое свойство.</span><span class="sxs-lookup"><span data-stu-id="7673f-106">Any writable variable or any property.</span></span>  
  
 `value`  
 <span data-ttu-id="7673f-107">Любой литерал, константа или выражение.</span><span class="sxs-lookup"><span data-stu-id="7673f-107">Any literal, constant, or expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7673f-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="7673f-108">Remarks</span></span>  

 <span data-ttu-id="7673f-109">Элемент в левой части знака равенства ( `=` ) может быть простой скалярной переменной, свойством или элементом массива.</span><span class="sxs-lookup"><span data-stu-id="7673f-109">The element on the left side of the equal sign (`=`) can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="7673f-110">Переменная или свойство не может быть [ReadOnly](../modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="7673f-110">The variable or property cannot be [ReadOnly](../modifiers/readonly.md).</span></span> <span data-ttu-id="7673f-111">`=`Оператор присваивает значение справа переменной или свойству слева.</span><span class="sxs-lookup"><span data-stu-id="7673f-111">The `=` operator assigns the value on its right to the variable or property on its left.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7673f-112">`=`Оператор также используется в качестве оператора сравнения.</span><span class="sxs-lookup"><span data-stu-id="7673f-112">The `=` operator is also used as a comparison operator.</span></span> <span data-ttu-id="7673f-113">Дополнительные сведения см. в разделе [Операторы сравнения](comparison-operators.md).</span><span class="sxs-lookup"><span data-stu-id="7673f-113">For details, see [Comparison Operators](comparison-operators.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="7673f-114">Перегрузка</span><span class="sxs-lookup"><span data-stu-id="7673f-114">Overloading</span></span>  

 <span data-ttu-id="7673f-115">`=`Оператор может быть перегружен только как оператор реляционного сравнения, а не как оператор присваивания.</span><span class="sxs-lookup"><span data-stu-id="7673f-115">The `=` operator can be overloaded only as a relational comparison operator, not as an assignment operator.</span></span> <span data-ttu-id="7673f-116">Для получения дополнительной информации см. [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="7673f-116">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7673f-117">Пример</span><span class="sxs-lookup"><span data-stu-id="7673f-117">Example</span></span>  

 <span data-ttu-id="7673f-118">В следующем примере показан оператор присваивания.</span><span class="sxs-lookup"><span data-stu-id="7673f-118">The following example demonstrates the assignment operator.</span></span> <span data-ttu-id="7673f-119">Значение справа присваивается переменной слева.</span><span class="sxs-lookup"><span data-stu-id="7673f-119">The value on the right is assigned to the variable on the left.</span></span>  
  
 [!code-vb[VbVbalrOperators#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#9)]  
  
## <a name="see-also"></a><span data-ttu-id="7673f-120">См. также</span><span class="sxs-lookup"><span data-stu-id="7673f-120">See also</span></span>

- [<span data-ttu-id="7673f-121"> Оператор&=</span><span class="sxs-lookup"><span data-stu-id="7673f-121">&= Operator</span></span>](and-assignment-operator.md)
- [<span data-ttu-id="7673f-122">Оператор \* =</span><span class="sxs-lookup"><span data-stu-id="7673f-122">\*= Operator</span></span>](multiplication-assignment-operator.md)
- [<span data-ttu-id="7673f-123">Оператор + =</span><span class="sxs-lookup"><span data-stu-id="7673f-123">+= Operator</span></span>](addition-assignment-operator.md)
- [<span data-ttu-id="7673f-124">Оператор-= (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7673f-124">-= Operator (Visual Basic)</span></span>](subtraction-assignment-operator.md)
- [<span data-ttu-id="7673f-125">Оператор/= (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7673f-125">/= Operator (Visual Basic)</span></span>](floating-point-division-assignment-operator.md)
- [<span data-ttu-id="7673f-126">\\Оператор =</span><span class="sxs-lookup"><span data-stu-id="7673f-126">\\= Operator</span></span>](integer-division-assignment-operator.md)
- [<span data-ttu-id="7673f-127">Оператор ^ =</span><span class="sxs-lookup"><span data-stu-id="7673f-127">^= Operator</span></span>](exponentiation-assignment-operator.md)
- [<span data-ttu-id="7673f-128">Операторы</span><span class="sxs-lookup"><span data-stu-id="7673f-128">Statements</span></span>](../../programming-guide/language-features/statements.md)
- [<span data-ttu-id="7673f-129">Операторы сравнения</span><span class="sxs-lookup"><span data-stu-id="7673f-129">Comparison Operators</span></span>](comparison-operators.md)
- [<span data-ttu-id="7673f-130">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="7673f-130">ReadOnly</span></span>](../modifiers/readonly.md)
- [<span data-ttu-id="7673f-131">Вывод локального типа</span><span class="sxs-lookup"><span data-stu-id="7673f-131">Local Type Inference</span></span>](../../programming-guide/language-features/variables/local-type-inference.md)
