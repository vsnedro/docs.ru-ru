---
title: Оператор *=
ms.date: 07/20/2015
f1_keywords:
- vb.*=
helpviewer_keywords:
- operator *=
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- '*= operator [Visual Basic]'
- compound assignment statements [Visual Basic]
ms.assetid: 96c86509-6eb8-4682-8226-3852e049376f
ms.openlocfilehash: 4e2f18fb2b8110d97390390b3934d3c1761baa35
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90866735"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="567df-102">Оператор \*= (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="567df-102">\*= Operator (Visual Basic)</span></span>

<span data-ttu-id="567df-103">Умножает значение переменной или свойства на значение выражения и присваивает результат переменной или свойству.</span><span class="sxs-lookup"><span data-stu-id="567df-103">Multiplies the value of a variable or property by the value of an expression and assigns the result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="567df-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="567df-104">Syntax</span></span>  
  
```vb  
variableorproperty *= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="567df-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="567df-105">Parts</span></span>  

 `variableorproperty`  
 <span data-ttu-id="567df-106">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="567df-106">Required.</span></span> <span data-ttu-id="567df-107">Любая числовая переменная или свойство.</span><span class="sxs-lookup"><span data-stu-id="567df-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="567df-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="567df-108">Required.</span></span> <span data-ttu-id="567df-109">Произвольное числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="567df-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="567df-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="567df-110">Remarks</span></span>  

 <span data-ttu-id="567df-111">Элемент в левой части `*=` оператора может быть простой скалярной переменной, свойством или элементом массива.</span><span class="sxs-lookup"><span data-stu-id="567df-111">The element on the left side of the `*=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="567df-112">Переменная или свойство не может быть [ReadOnly](../modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="567df-112">The variable or property cannot be [ReadOnly](../modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="567df-113">`*=`Оператор вначале умножает значение выражения (в правой части оператора) на значение переменной или свойства (в левой части оператора) (слева).</span><span class="sxs-lookup"><span data-stu-id="567df-113">The `*=` operator first multiplies the value of the expression (on the right-hand side of the operator) by the value of the variable or property (on the left-hand side of the operator).</span></span> <span data-ttu-id="567df-114">Затем оператор присваивает результат этой операции переменной или свойству.</span><span class="sxs-lookup"><span data-stu-id="567df-114">The operator then assigns the result of that operation to the variable or property.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="567df-115">Перегрузка</span><span class="sxs-lookup"><span data-stu-id="567df-115">Overloading</span></span>  

 <span data-ttu-id="567df-116">[Оператор \*](multiplication-operator.md) может быть *перегружен*, что означает, что класс или структура может переопределить свое поведение, если операнд имеет тип этого класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="567df-116">The [\* Operator](multiplication-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="567df-117">Перегрузка `*` оператора влияет на поведение `*=` оператора.</span><span class="sxs-lookup"><span data-stu-id="567df-117">Overloading the `*` operator affects the behavior of the `*=` operator.</span></span> <span data-ttu-id="567df-118">Если ваш код использует `*=` класс или структуру, перегрузки `*` , убедитесь, что вы понимаете его переопределенное поведение.</span><span class="sxs-lookup"><span data-stu-id="567df-118">If your code uses `*=` on a class or structure that overloads `*`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="567df-119">Для получения дополнительной информации см. [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="567df-119">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="567df-120">Пример</span><span class="sxs-lookup"><span data-stu-id="567df-120">Example</span></span>  

 <span data-ttu-id="567df-121">В следующем примере оператор используется `*=` для умножения одной `Integer` переменной на вторую и присваивания результата первой переменной.</span><span class="sxs-lookup"><span data-stu-id="567df-121">The following example uses the `*=` operator to multiply one `Integer` variable by a second and assign the result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="567df-122">См. также</span><span class="sxs-lookup"><span data-stu-id="567df-122">See also</span></span>

- [<span data-ttu-id="567df-123">\* Оператор</span><span class="sxs-lookup"><span data-stu-id="567df-123">\* Operator</span></span>](multiplication-operator.md)
- [<span data-ttu-id="567df-124">Операторы присваивания</span><span class="sxs-lookup"><span data-stu-id="567df-124">Assignment Operators</span></span>](assignment-operators.md)
- [<span data-ttu-id="567df-125">Арифметические операторы</span><span class="sxs-lookup"><span data-stu-id="567df-125">Arithmetic Operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="567df-126">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="567df-126">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="567df-127">Список операторов, сгруппированных по функциональному назначению</span><span class="sxs-lookup"><span data-stu-id="567df-127">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="567df-128">Операторы</span><span class="sxs-lookup"><span data-stu-id="567df-128">Statements</span></span>](../../programming-guide/language-features/statements.md)
