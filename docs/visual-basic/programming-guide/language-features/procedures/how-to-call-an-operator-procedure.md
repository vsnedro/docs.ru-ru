---
title: Практическое руководство. Вызов процедуры оператора
ms.date: 07/20/2015
helpviewer_keywords:
- operator procedures [Visual Basic], calling
- procedures [Visual Basic], operator
- procedure calls [Visual Basic], operator overloading
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- return values [Visual Basic], Operator procedures
- overloaded operators [Visual Basic], calling
- operator overloading
ms.assetid: 0dce42cc-f0b0-4c14-9f62-018b21f33497
ms.openlocfilehash: fa2bc5417b8b917ff48502a5bd0a4daa21fab67e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84388573"
---
# <a name="how-to-call-an-operator-procedure-visual-basic"></a><span data-ttu-id="3e7c7-102">Практическое руководство. Вызов процедуры оператора (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3e7c7-102">How to: Call an Operator Procedure (Visual Basic)</span></span>
<span data-ttu-id="3e7c7-103">Для вызова процедуры оператора используется символ оператора в выражении.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-103">You call an operator procedure by using the operator symbol in an expression.</span></span> <span data-ttu-id="3e7c7-104">В случае оператора преобразования вызывается [Функция CType](../../../language-reference/functions/ctype-function.md) для преобразования значения из одного типа данных в другой.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-104">In the case of a conversion operator, you call the [CType Function](../../../language-reference/functions/ctype-function.md) to convert a value from one data type to another.</span></span>  
  
 <span data-ttu-id="3e7c7-105">Процедуры оператора не вызываются явным образом.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-105">You do not call operator procedures explicitly.</span></span> <span data-ttu-id="3e7c7-106">Вы просто используете оператор или `CType` функцию в операторе присваивания или выражении так же, как обычно используется оператор.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-106">You just use the operator, or the `CType` function, in an assignment statement or an expression, the same way you ordinarily use an operator.</span></span> <span data-ttu-id="3e7c7-107">Visual Basic выполняет вызов процедуры оператора.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-107">Visual Basic makes the call to the operator procedure.</span></span>  
  
 <span data-ttu-id="3e7c7-108">Определение оператора для класса или структуры также называется *перегрузкой* оператора.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-108">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
### <a name="to-call-an-operator-procedure"></a><span data-ttu-id="3e7c7-109">Вызов процедуры оператора</span><span class="sxs-lookup"><span data-stu-id="3e7c7-109">To call an operator procedure</span></span>  
  
1. <span data-ttu-id="3e7c7-110">Используйте символ оператора в выражении обычным образом.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-110">Use the operator symbol in an expression in the ordinary way.</span></span>  
  
2. <span data-ttu-id="3e7c7-111">Убедитесь, что типы данных операндов подходят для оператора, и в правильном порядке.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-111">Be sure the data types of the operands are appropriate for the operator, and in the correct order.</span></span>  
  
3. <span data-ttu-id="3e7c7-112">Оператор влияет на значение выражения, как и ожидалось.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-112">The operator contributes to the value of the expression as expected.</span></span>  
  
### <a name="to-call-a-conversion-operator-procedure"></a><span data-ttu-id="3e7c7-113">Вызов процедуры оператора преобразования</span><span class="sxs-lookup"><span data-stu-id="3e7c7-113">To call a conversion operator procedure</span></span>  
  
1. <span data-ttu-id="3e7c7-114">Используйте `CType` внутри выражения.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-114">Use `CType` inside an expression.</span></span>  
  
2. <span data-ttu-id="3e7c7-115">Убедитесь, что типы данных операндов подходят для преобразования, и в правильном порядке.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-115">Be sure the data types of the operands are appropriate for the conversion, and in the correct order.</span></span>  
  
3. <span data-ttu-id="3e7c7-116">`CType`вызывает процедуру оператора преобразования и возвращает преобразованное значение.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-116">`CType` calls the conversion operator procedure and returns the converted value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3e7c7-117">Пример</span><span class="sxs-lookup"><span data-stu-id="3e7c7-117">Example</span></span>  
 <span data-ttu-id="3e7c7-118">Следующий пример создает две <xref:System.TimeSpan> структуры, добавляет их вместе и сохраняет результат в третьей <xref:System.TimeSpan> структуре.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-118">The following example creates two <xref:System.TimeSpan> structures, adds them together, and stores the result in a third <xref:System.TimeSpan> structure.</span></span> <span data-ttu-id="3e7c7-119"><xref:System.TimeSpan>Структура определяет процедуры операторов для перегрузки нескольких стандартных операторов.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-119">The <xref:System.TimeSpan> structure defines operator procedures to overload several standard operators.</span></span>  
  
 [!code-vb[VbVbcnProcedures#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#29)]  
  
 <span data-ttu-id="3e7c7-120">Поскольку <xref:System.TimeSpan> перегружает Стандартный `+` оператор, предыдущий пример вызывает процедуру оператора при вычислении значения `combinedSpan` .</span><span class="sxs-lookup"><span data-stu-id="3e7c7-120">Because <xref:System.TimeSpan> overloads the standard `+` operator, the previous example calls an operator procedure when it calculates the value of `combinedSpan`.</span></span>  
  
 <span data-ttu-id="3e7c7-121">Пример вызова процедуры оператора диалога см. [в разделе как использовать класс, определяющий операторы](./how-to-use-a-class-that-defines-operators.md).</span><span class="sxs-lookup"><span data-stu-id="3e7c7-121">For an example of calling a conversation operator procedure, see [How to: Use a Class that Defines Operators](./how-to-use-a-class-that-defines-operators.md).</span></span>  
  
## <a name="compile-the-code"></a><span data-ttu-id="3e7c7-122">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="3e7c7-122">Compile the code</span></span>  
 <span data-ttu-id="3e7c7-123">Убедитесь, что используемый класс или структура определяет оператор, который вы хотите использовать.</span><span class="sxs-lookup"><span data-stu-id="3e7c7-123">Be sure the class or structure you are using defines the operator you want to use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e7c7-124">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="3e7c7-124">See also</span></span>

- [<span data-ttu-id="3e7c7-125">Процедуры операторов</span><span class="sxs-lookup"><span data-stu-id="3e7c7-125">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="3e7c7-126">Практическое руководство. Определение оператора</span><span class="sxs-lookup"><span data-stu-id="3e7c7-126">How to: Define an Operator</span></span>](./how-to-define-an-operator.md)
- [<span data-ttu-id="3e7c7-127">Практическое руководство. Определение оператора преобразования</span><span class="sxs-lookup"><span data-stu-id="3e7c7-127">How to: Define a Conversion Operator</span></span>](./how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="3e7c7-128">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="3e7c7-128">Operator Statement</span></span>](../../../language-reference/statements/operator-statement.md)
- [<span data-ttu-id="3e7c7-129">Widening</span><span class="sxs-lookup"><span data-stu-id="3e7c7-129">Widening</span></span>](../../../language-reference/modifiers/widening.md)
- [<span data-ttu-id="3e7c7-130">Narrowing</span><span class="sxs-lookup"><span data-stu-id="3e7c7-130">Narrowing</span></span>](../../../language-reference/modifiers/narrowing.md)
- [<span data-ttu-id="3e7c7-131">Оператор Structure</span><span class="sxs-lookup"><span data-stu-id="3e7c7-131">Structure Statement</span></span>](../../../language-reference/statements/structure-statement.md)
- [<span data-ttu-id="3e7c7-132">Практическое руководство. Объявление структуры</span><span class="sxs-lookup"><span data-stu-id="3e7c7-132">How to: Declare a Structure</span></span>](../data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="3e7c7-133">Явные и неявные преобразования</span><span class="sxs-lookup"><span data-stu-id="3e7c7-133">Implicit and Explicit Conversions</span></span>](../data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="3e7c7-134">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="3e7c7-134">Widening and Narrowing Conversions</span></span>](../data-types/widening-and-narrowing-conversions.md)
