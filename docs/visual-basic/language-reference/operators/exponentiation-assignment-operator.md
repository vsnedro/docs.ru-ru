---
title: Оператор ^=
ms.date: 07/20/2015
f1_keywords:
- vb.^=
helpviewer_keywords:
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- ^= operator [Visual Basic]
- compound assignment statements [Visual Basic]
ms.assetid: 397da132-2d96-4a85-a7bc-f7c730a608c9
ms.openlocfilehash: a956ffdaa3456ed09443f25c3383b6aab52fb5bf
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90867067"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="b2317-102">Оператор ^= (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b2317-102">^= Operator (Visual Basic)</span></span>

<span data-ttu-id="b2317-103">Возвращает значение переменной или свойства в степень выражения и присваивает результат переменной или свойству.</span><span class="sxs-lookup"><span data-stu-id="b2317-103">Raises the value of a variable or property to the power of an expression and assigns the result back to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2317-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b2317-104">Syntax</span></span>  
  
```vb  
variableorproperty ^= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="b2317-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="b2317-105">Parts</span></span>  

 `variableorproperty`  
 <span data-ttu-id="b2317-106">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="b2317-106">Required.</span></span> <span data-ttu-id="b2317-107">Любая числовая переменная или свойство.</span><span class="sxs-lookup"><span data-stu-id="b2317-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="b2317-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="b2317-108">Required.</span></span> <span data-ttu-id="b2317-109">Произвольное числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="b2317-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b2317-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="b2317-110">Remarks</span></span>  

 <span data-ttu-id="b2317-111">Элемент в левой части `^=` оператора может быть простой скалярной переменной, свойством или элементом массива.</span><span class="sxs-lookup"><span data-stu-id="b2317-111">The element on the left side of the `^=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="b2317-112">Переменная или свойство не может быть [ReadOnly](../modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="b2317-112">The variable or property cannot be [ReadOnly](../modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="b2317-113">`^=`Оператор сначала выдает значение переменной или свойства (в левой части оператора) в степень значения выражения (в правой части оператора) (справа).</span><span class="sxs-lookup"><span data-stu-id="b2317-113">The `^=` operator first raises the value of the variable or property (on the left-hand side of the operator) to the power of the value of the expression (on the right-hand side of the operator).</span></span> <span data-ttu-id="b2317-114">Затем оператор присваивает результат этой операции с переменной или свойством.</span><span class="sxs-lookup"><span data-stu-id="b2317-114">The operator then assigns the result of that operation back to the variable or property.</span></span>  
  
 <span data-ttu-id="b2317-115">Visual Basic всегда выполняет возведение в степень в [типе данных Double](../data-types/double-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="b2317-115">Visual Basic always performs exponentiation in the [Double Data Type](../data-types/double-data-type.md).</span></span> <span data-ttu-id="b2317-116">Операнды любого другого типа преобразуются в `Double` , а результат всегда равен `Double` .</span><span class="sxs-lookup"><span data-stu-id="b2317-116">Operands of any different type are converted to `Double`, and the result is always `Double`.</span></span>  
  
 <span data-ttu-id="b2317-117">Значение `expression` может быть дробным, отрицательным или обоими.</span><span class="sxs-lookup"><span data-stu-id="b2317-117">The value of `expression` can be fractional, negative, or both.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="b2317-118">Перегрузка</span><span class="sxs-lookup"><span data-stu-id="b2317-118">Overloading</span></span>  

 <span data-ttu-id="b2317-119">[Оператор ^](exponentiation-operator.md) может быть *перегружен*, что означает, что класс или структура может переопределить свое поведение, если операнд имеет тип этого класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="b2317-119">The [^ Operator](exponentiation-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="b2317-120">Перегрузка `^` оператора влияет на поведение `^=` оператора.</span><span class="sxs-lookup"><span data-stu-id="b2317-120">Overloading the `^` operator affects the behavior of the `^=` operator.</span></span> <span data-ttu-id="b2317-121">Если ваш код использует `^=` класс или структуру, перегрузки `^` , убедитесь, что вы понимаете его переопределенное поведение.</span><span class="sxs-lookup"><span data-stu-id="b2317-121">If your code uses `^=` on a class or structure that overloads `^`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="b2317-122">Для получения дополнительной информации см. [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="b2317-122">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b2317-123">Пример</span><span class="sxs-lookup"><span data-stu-id="b2317-123">Example</span></span>  

 <span data-ttu-id="b2317-124">В следующем примере оператор используется `^=` для возведения значения одной `Integer` переменной в степень второй переменной и присваивания результата первой переменной.</span><span class="sxs-lookup"><span data-stu-id="b2317-124">The following example uses the `^=` operator to raise the value of one `Integer` variable to the power of a second variable and assign the result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#21)]  
  
## <a name="see-also"></a><span data-ttu-id="b2317-125">См. также</span><span class="sxs-lookup"><span data-stu-id="b2317-125">See also</span></span>

- [<span data-ttu-id="b2317-126">Оператор ^</span><span class="sxs-lookup"><span data-stu-id="b2317-126">^ Operator</span></span>](exponentiation-operator.md)
- [<span data-ttu-id="b2317-127">Операторы присваивания</span><span class="sxs-lookup"><span data-stu-id="b2317-127">Assignment Operators</span></span>](assignment-operators.md)
- [<span data-ttu-id="b2317-128">Арифметические операторы</span><span class="sxs-lookup"><span data-stu-id="b2317-128">Arithmetic Operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="b2317-129">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b2317-129">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="b2317-130">Список операторов, сгруппированных по функциональному назначению</span><span class="sxs-lookup"><span data-stu-id="b2317-130">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="b2317-131">Операторы</span><span class="sxs-lookup"><span data-stu-id="b2317-131">Statements</span></span>](../../programming-guide/language-features/statements.md)
