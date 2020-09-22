---
title: '&amp;Оператор ='
ms.date: 07/20/2015
f1_keywords:
- vb.&=
helpviewer_keywords:
- operator &=
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- '&= operator [Visual Basic]'
- compound assignment statements [Visual Basic]
ms.assetid: 0cf262fc-1a05-419a-a503-60013f111c8a
ms.openlocfilehash: 9b77c44aa77afd59e36e1d21451205d3929ef527
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874870"
---
# <a name="amp-operator-visual-basic"></a><span data-ttu-id="1338d-102">&amp;Оператор = (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1338d-102">&amp;= Operator (Visual Basic)</span></span>

<span data-ttu-id="1338d-103">Сцепляет `String` выражение с `String` переменной или свойством и присваивает результат переменной или свойству.</span><span class="sxs-lookup"><span data-stu-id="1338d-103">Concatenates a `String` expression to a `String` variable or property and assigns the result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1338d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1338d-104">Syntax</span></span>  
  
```vb  
variableorproperty &= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="1338d-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="1338d-105">Parts</span></span>  

 `variableorproperty`  
 <span data-ttu-id="1338d-106">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="1338d-106">Required.</span></span> <span data-ttu-id="1338d-107">Любая `String` переменная или свойство.</span><span class="sxs-lookup"><span data-stu-id="1338d-107">Any `String` variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="1338d-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="1338d-108">Required.</span></span> <span data-ttu-id="1338d-109">Произвольное выражение `String` .</span><span class="sxs-lookup"><span data-stu-id="1338d-109">Any `String` expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1338d-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="1338d-110">Remarks</span></span>  

 <span data-ttu-id="1338d-111">Элемент в левой части `&=` оператора может быть простой скалярной переменной, свойством или элементом массива.</span><span class="sxs-lookup"><span data-stu-id="1338d-111">The element on the left side of the `&=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="1338d-112">Переменная или свойство не может быть [ReadOnly](../modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="1338d-112">The variable or property cannot be [ReadOnly](../modifiers/readonly.md).</span></span> <span data-ttu-id="1338d-113">`&=`Оператор объединяет `String` выражение непосредственно с `String` переменной или свойством слева, а затем присваивает результат переменной или свойству слева.</span><span class="sxs-lookup"><span data-stu-id="1338d-113">The `&=` operator concatenates the `String` expression on its right to the `String` variable or property on its left, and assigns the result to the variable or property on its left.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="1338d-114">Перегрузка</span><span class="sxs-lookup"><span data-stu-id="1338d-114">Overloading</span></span>  

 <span data-ttu-id="1338d-115">[Оператор&](concatenation-operator.md) может быть *перегружен*, что означает, что класс или структура может переопределить свое поведение, если операнд имеет тип этого класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="1338d-115">The [& Operator](concatenation-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="1338d-116">Перегрузка `&` оператора влияет на поведение `&=` оператора.</span><span class="sxs-lookup"><span data-stu-id="1338d-116">Overloading the `&` operator affects the behavior of the `&=` operator.</span></span> <span data-ttu-id="1338d-117">Если ваш код использует `&=` класс или структуру, перегрузки `&` , убедитесь, что вы понимаете его переопределенное поведение.</span><span class="sxs-lookup"><span data-stu-id="1338d-117">If your code uses `&=` on a class or structure that overloads `&`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="1338d-118">Для получения дополнительной информации см. [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="1338d-118">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1338d-119">Пример</span><span class="sxs-lookup"><span data-stu-id="1338d-119">Example</span></span>  

 <span data-ttu-id="1338d-120">В следующем примере оператор используется `&=` для сцепления двух `String` переменных и присваивания результата первой переменной.</span><span class="sxs-lookup"><span data-stu-id="1338d-120">The following example uses the `&=` operator to concatenate two `String` variables and assign the result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="1338d-121">См. также</span><span class="sxs-lookup"><span data-stu-id="1338d-121">See also</span></span>

- [<span data-ttu-id="1338d-122"> Оператор&</span><span class="sxs-lookup"><span data-stu-id="1338d-122">& Operator</span></span>](concatenation-operator.md)
- [<span data-ttu-id="1338d-123">Оператор + =</span><span class="sxs-lookup"><span data-stu-id="1338d-123">+= Operator</span></span>](addition-assignment-operator.md)
- [<span data-ttu-id="1338d-124">Операторы присваивания</span><span class="sxs-lookup"><span data-stu-id="1338d-124">Assignment Operators</span></span>](assignment-operators.md)
- [<span data-ttu-id="1338d-125">Операторы объединения</span><span class="sxs-lookup"><span data-stu-id="1338d-125">Concatenation Operators</span></span>](concatenation-operators.md)
- [<span data-ttu-id="1338d-126">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1338d-126">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="1338d-127">Список операторов, сгруппированных по функциональному назначению</span><span class="sxs-lookup"><span data-stu-id="1338d-127">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="1338d-128">Операторы</span><span class="sxs-lookup"><span data-stu-id="1338d-128">Statements</span></span>](../../programming-guide/language-features/statements.md)
