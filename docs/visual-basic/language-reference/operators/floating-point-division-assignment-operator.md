---
title: Оператор /=
ms.date: 07/20/2015
f1_keywords:
- vb./=
helpviewer_keywords:
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- /= operator [Visual Basic]
- operator /=
- compound assignment statements [Visual Basic]
ms.assetid: a1e22d0e-8380-4761-9da1-84fb51c34821
ms.openlocfilehash: d47a69e454305ce9417a46b5bbfbbb55a1ad1dc3
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90867079"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="b7008-102">Оператор /= (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b7008-102">/= Operator (Visual Basic)</span></span>

<span data-ttu-id="b7008-103">Делит значение переменной или свойства на значение выражения и присваивает результат с плавающей запятой переменной или свойству.</span><span class="sxs-lookup"><span data-stu-id="b7008-103">Divides the value of a variable or property by the value of an expression and assigns the floating-point result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7008-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b7008-104">Syntax</span></span>  
  
```vb  
variableorproperty /= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="b7008-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="b7008-105">Parts</span></span>  

 `variableorproperty`  
 <span data-ttu-id="b7008-106">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="b7008-106">Required.</span></span> <span data-ttu-id="b7008-107">Любая числовая переменная или свойство.</span><span class="sxs-lookup"><span data-stu-id="b7008-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="b7008-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="b7008-108">Required.</span></span> <span data-ttu-id="b7008-109">Произвольное числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="b7008-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b7008-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="b7008-110">Remarks</span></span>  

 <span data-ttu-id="b7008-111">Элемент в левой части `/=` оператора может быть простой скалярной переменной, свойством или элементом массива.</span><span class="sxs-lookup"><span data-stu-id="b7008-111">The element on the left side of the `/=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="b7008-112">Переменная или свойство не может быть [ReadOnly](../modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="b7008-112">The variable or property cannot be [ReadOnly](../modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="b7008-113">`/=`Оператор сначала делит значение переменной или свойства (в левой части оператора) на значение выражения (в правой части оператора). в противном случае.</span><span class="sxs-lookup"><span data-stu-id="b7008-113">The `/=` operator first divides the value of the variable or property (on the left-hand side of the operator) by the value of the expression (on the right-hand side of the operator).</span></span> <span data-ttu-id="b7008-114">Затем оператор присваивает результат операции с плавающей запятой переменной или свойству.</span><span class="sxs-lookup"><span data-stu-id="b7008-114">The operator then assigns the floating-point result of that operation to the variable or property.</span></span>  
  
 <span data-ttu-id="b7008-115">Эта инструкция присваивает `Double` значение переменной или свойству слева.</span><span class="sxs-lookup"><span data-stu-id="b7008-115">This statement assigns a `Double` value to the variable or property on the left.</span></span> <span data-ttu-id="b7008-116">Если `Option Strict` имеет значение `On` , `variableorproperty` должно быть `Double` .</span><span class="sxs-lookup"><span data-stu-id="b7008-116">If `Option Strict` is `On`, `variableorproperty` must be a `Double`.</span></span> <span data-ttu-id="b7008-117">Если `Option Strict` параметр имеет значение `Off` , Visual Basic выполняет неявное преобразование и присваивает результирующее значение `variableorproperty` с возможной ошибкой во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="b7008-117">If `Option Strict` is `Off`, Visual Basic performs an implicit conversion and assigns the resulting value to `variableorproperty`, with a possible error at run time.</span></span> <span data-ttu-id="b7008-118">Дополнительные сведения см. в разделе [расширяющие и сужающие преобразования](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) и [Option](../statements/option-strict-statement.md)parallelism.</span><span class="sxs-lookup"><span data-stu-id="b7008-118">For more information, see [Widening and Narrowing Conversions](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) and [Option Strict Statement](../statements/option-strict-statement.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="b7008-119">Перегрузка</span><span class="sxs-lookup"><span data-stu-id="b7008-119">Overloading</span></span>  

 <span data-ttu-id="b7008-120">[Оператор/(Visual Basic)](floating-point-division-operator.md) может быть *перегружен*, что означает, что класс или структура может переопределить свое поведение, когда операнд имеет тип этого класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="b7008-120">The [/ Operator (Visual Basic)](floating-point-division-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="b7008-121">Перегрузка `/` оператора влияет на поведение `/=` оператора.</span><span class="sxs-lookup"><span data-stu-id="b7008-121">Overloading the `/` operator affects the behavior of the `/=` operator.</span></span> <span data-ttu-id="b7008-122">Если ваш код использует `/=` класс или структуру, перегрузки `/` , убедитесь, что вы понимаете его переопределенное поведение.</span><span class="sxs-lookup"><span data-stu-id="b7008-122">If your code uses `/=` on a class or structure that overloads `/`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="b7008-123">Для получения дополнительной информации см. [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="b7008-123">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b7008-124">Пример</span><span class="sxs-lookup"><span data-stu-id="b7008-124">Example</span></span>  

 <span data-ttu-id="b7008-125">В следующем примере оператор используется `/=` для разделения одной `Integer` переменной на вторую и присваивания значения частного для первой переменной.</span><span class="sxs-lookup"><span data-stu-id="b7008-125">The following example uses the `/=` operator to divide one `Integer` variable by a second and assign the quotient to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#17)]  
  
## <a name="see-also"></a><span data-ttu-id="b7008-126">См. также</span><span class="sxs-lookup"><span data-stu-id="b7008-126">See also</span></span>

- [<span data-ttu-id="b7008-127">Оператор/(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b7008-127">/ Operator (Visual Basic)</span></span>](floating-point-division-operator.md)
- [<span data-ttu-id="b7008-128">\\Оператор =</span><span class="sxs-lookup"><span data-stu-id="b7008-128">\\= Operator</span></span>](integer-division-assignment-operator.md)
- [<span data-ttu-id="b7008-129">Операторы присваивания</span><span class="sxs-lookup"><span data-stu-id="b7008-129">Assignment Operators</span></span>](assignment-operators.md)
- [<span data-ttu-id="b7008-130">Арифметические операторы</span><span class="sxs-lookup"><span data-stu-id="b7008-130">Arithmetic Operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="b7008-131">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b7008-131">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="b7008-132">Список операторов, сгруппированных по функциональному назначению</span><span class="sxs-lookup"><span data-stu-id="b7008-132">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="b7008-133">Операторы</span><span class="sxs-lookup"><span data-stu-id="b7008-133">Statements</span></span>](../../programming-guide/language-features/statements.md)
