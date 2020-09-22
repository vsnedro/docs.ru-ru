---
title: Оператор \=
ms.date: 07/20/2015
f1_keywords:
- '\='
- vb.\=
helpviewer_keywords:
- '\= operator [Visual Basic]'
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- operator \= [Visual Basic]
- compound assignment statements [Visual Basic]
ms.assetid: 6f39915d-e398-4045-afcc-da6885e57b9c
ms.openlocfilehash: 6e749e13c0427354db9e361538d4bef10b6c6b04
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873405"
---
# <a name="-operator"></a><span data-ttu-id="05314-102">\\Оператор =</span><span class="sxs-lookup"><span data-stu-id="05314-102">\\= Operator</span></span>

<span data-ttu-id="05314-103">Делит значение переменной или свойства на значение выражения и присваивает целочисленный результат переменной или свойству.</span><span class="sxs-lookup"><span data-stu-id="05314-103">Divides the value of a variable or property by the value of an expression and assigns the integer result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05314-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="05314-104">Syntax</span></span>  
  
```vb  
variableorproperty \= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="05314-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="05314-105">Parts</span></span>  

 `variableorproperty`  
 <span data-ttu-id="05314-106">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="05314-106">Required.</span></span> <span data-ttu-id="05314-107">Любая числовая переменная или свойство.</span><span class="sxs-lookup"><span data-stu-id="05314-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="05314-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="05314-108">Required.</span></span> <span data-ttu-id="05314-109">Произвольное числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="05314-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="05314-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="05314-110">Remarks</span></span>  

 <span data-ttu-id="05314-111">Элемент в левой части `\=` оператора может быть простой скалярной переменной, свойством или элементом массива.</span><span class="sxs-lookup"><span data-stu-id="05314-111">The element on the left side of the `\=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="05314-112">Переменная или свойство не может быть [ReadOnly](../modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="05314-112">The variable or property cannot be [ReadOnly](../modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="05314-113">`\=`Оператор делит значение переменной или свойства слева на значение справа, а целочисленный результат присваивается переменной или свойству слева.</span><span class="sxs-lookup"><span data-stu-id="05314-113">The `\=` operator divides the value of a variable or property on its left by the value on its right, and assigns the integer result to the variable or property on its left</span></span>  
  
 <span data-ttu-id="05314-114">Дополнительные сведения о целочисленном делении см. в разделе [оператор \ (Visual Basic)](integer-division-operator.md).</span><span class="sxs-lookup"><span data-stu-id="05314-114">For further information on integer division, see [\ Operator (Visual Basic)](integer-division-operator.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="05314-115">Перегрузка</span><span class="sxs-lookup"><span data-stu-id="05314-115">Overloading</span></span>  

 <span data-ttu-id="05314-116">`\`Оператор можно *перегрузить*, что означает, что класс или структура может переопределить свое поведение, когда операнд имеет тип этого класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="05314-116">The `\` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="05314-117">Перегрузка `\` оператора влияет на поведение `\=` оператора.</span><span class="sxs-lookup"><span data-stu-id="05314-117">Overloading the `\` operator affects the behavior of the `\=` operator.</span></span> <span data-ttu-id="05314-118">Если ваш код использует `\=` класс или структуру, перегрузки `\` , убедитесь, что вы понимаете его переопределенное поведение.</span><span class="sxs-lookup"><span data-stu-id="05314-118">If your code uses `\=` on a class or structure that overloads `\`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="05314-119">Для получения дополнительной информации см. [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="05314-119">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="05314-120">Пример</span><span class="sxs-lookup"><span data-stu-id="05314-120">Example</span></span>  

 <span data-ttu-id="05314-121">В следующем примере оператор используется `\=` для разделения одной `Integer` переменной на вторую и присваивания целочисленного результата первой переменной.</span><span class="sxs-lookup"><span data-stu-id="05314-121">The following example uses the `\=` operator to divide one `Integer` variable by a second and assign the integer result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#19)]  
  
## <a name="see-also"></a><span data-ttu-id="05314-122">См. также</span><span class="sxs-lookup"><span data-stu-id="05314-122">See also</span></span>

- [<span data-ttu-id="05314-123">Оператор \ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="05314-123">\ Operator (Visual Basic)</span></span>](integer-division-operator.md)
- [<span data-ttu-id="05314-124">Оператор/= (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="05314-124">/= Operator (Visual Basic)</span></span>](floating-point-division-assignment-operator.md)
- [<span data-ttu-id="05314-125">Операторы присваивания</span><span class="sxs-lookup"><span data-stu-id="05314-125">Assignment Operators</span></span>](assignment-operators.md)
- [<span data-ttu-id="05314-126">Арифметические операторы</span><span class="sxs-lookup"><span data-stu-id="05314-126">Arithmetic Operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="05314-127">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="05314-127">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="05314-128">Список операторов, сгруппированных по функциональному назначению</span><span class="sxs-lookup"><span data-stu-id="05314-128">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="05314-129">Операторы</span><span class="sxs-lookup"><span data-stu-id="05314-129">Statements</span></span>](../../programming-guide/language-features/statements.md)
