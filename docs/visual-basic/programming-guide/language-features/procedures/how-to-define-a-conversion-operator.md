---
title: Практическое руководство. Определение оператора преобразования
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- operators [Visual Basic], defining
- procedures [Visual Basic], operator
- operators [Visual Basic], overloading
- return values [Visual Basic], Operator procedures
- operator overloading
ms.assetid: 54203dfa-c24b-463f-9942-d5153e89e762
ms.openlocfilehash: 53b0211c6304625edd7ac24fa52ff0c051d8f0a0
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84388093"
---
# <a name="how-to-define-a-conversion-operator-visual-basic"></a><span data-ttu-id="f319e-102">Практическое руководство. Определение оператора преобразования (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f319e-102">How to: Define a Conversion Operator (Visual Basic)</span></span>
<span data-ttu-id="f319e-103">Если вы определили класс или структуру, можно определить оператор преобразования типа между типом класса или структуры и другим типом данных (например `Integer` ,, `Double` или `String` ).</span><span class="sxs-lookup"><span data-stu-id="f319e-103">If you have defined a class or structure, you can define a type conversion operator between the type of your class or structure and another data type (such as `Integer`, `Double`, or `String`).</span></span>  
  
 <span data-ttu-id="f319e-104">Определите преобразование типа как процедуру [функции CType](../../../language-reference/functions/ctype-function.md) в классе или структуре.</span><span class="sxs-lookup"><span data-stu-id="f319e-104">Define the type conversion as a [CType Function](../../../language-reference/functions/ctype-function.md) procedure within the class or structure.</span></span> <span data-ttu-id="f319e-105">Все процедуры преобразования должны иметь `Public Shared` значение, и каждая из них должна указывать [расширение](../../../language-reference/modifiers/widening.md) или [сужение](../../../language-reference/modifiers/narrowing.md).</span><span class="sxs-lookup"><span data-stu-id="f319e-105">All conversion procedures must be `Public Shared`, and each one must specify either [Widening](../../../language-reference/modifiers/widening.md) or [Narrowing](../../../language-reference/modifiers/narrowing.md).</span></span>  
  
 <span data-ttu-id="f319e-106">Определение оператора для класса или структуры также называется *перегрузкой* оператора.</span><span class="sxs-lookup"><span data-stu-id="f319e-106">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f319e-107">Пример</span><span class="sxs-lookup"><span data-stu-id="f319e-107">Example</span></span>  
 <span data-ttu-id="f319e-108">В следующем примере определяются операторы преобразования между структурой `digit` и `Byte` .</span><span class="sxs-lookup"><span data-stu-id="f319e-108">The following example defines conversion operators between a structure called `digit` and a `Byte`.</span></span>  
  
 [!code-vb[VbVbcnProcedures#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#27)]  
  
 <span data-ttu-id="f319e-109">Структуру можно проверить `digit` с помощью следующего кода.</span><span class="sxs-lookup"><span data-stu-id="f319e-109">You can test the structure `digit` with the following code.</span></span>  
  
 [!code-vb[VbVbcnProcedures#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#28)]  
  
## <a name="see-also"></a><span data-ttu-id="f319e-110">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f319e-110">See also</span></span>

- [<span data-ttu-id="f319e-111">Процедуры операторов</span><span class="sxs-lookup"><span data-stu-id="f319e-111">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="f319e-112">Практическое руководство. Определение оператора</span><span class="sxs-lookup"><span data-stu-id="f319e-112">How to: Define an Operator</span></span>](./how-to-define-an-operator.md)
- [<span data-ttu-id="f319e-113">Практическое руководство. Вызов процедуры оператора</span><span class="sxs-lookup"><span data-stu-id="f319e-113">How to: Call an Operator Procedure</span></span>](./how-to-call-an-operator-procedure.md)
- [<span data-ttu-id="f319e-114">Практическое руководство. Использование класса, в котором определяются операторы</span><span class="sxs-lookup"><span data-stu-id="f319e-114">How to: Use a Class that Defines Operators</span></span>](./how-to-use-a-class-that-defines-operators.md)
- [<span data-ttu-id="f319e-115">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="f319e-115">Operator Statement</span></span>](../../../language-reference/statements/operator-statement.md)
- [<span data-ttu-id="f319e-116">Оператор Structure</span><span class="sxs-lookup"><span data-stu-id="f319e-116">Structure Statement</span></span>](../../../language-reference/statements/structure-statement.md)
- [<span data-ttu-id="f319e-117">Практическое руководство. Объявление структуры</span><span class="sxs-lookup"><span data-stu-id="f319e-117">How to: Declare a Structure</span></span>](../data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="f319e-118">Явные и неявные преобразования</span><span class="sxs-lookup"><span data-stu-id="f319e-118">Implicit and Explicit Conversions</span></span>](../data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="f319e-119">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="f319e-119">Widening and Narrowing Conversions</span></span>](../data-types/widening-and-narrowing-conversions.md)
