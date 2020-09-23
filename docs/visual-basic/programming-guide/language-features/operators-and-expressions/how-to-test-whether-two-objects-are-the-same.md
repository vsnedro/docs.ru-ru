---
title: Практическое руководство. Проверка совпадения двух объектов
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], reference
- Is operator [Visual Basic], comparing objects
- reference variables [Visual Basic]
- variables [Visual Basic], referring to same object
- objects [Visual Basic], variables referring to same
- Visual Basic code, operators
ms.assetid: f760e828-8704-4256-bc2d-c22a4c93b524
ms.openlocfilehash: d29d1b0026b3f62d47859cd5b4b7a601532e27b8
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91071694"
---
# <a name="how-to-test-whether-two-objects-are-the-same-visual-basic"></a><span data-ttu-id="b047f-102">Практическое руководство. Проверка совпадения двух объектов (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b047f-102">How to: Test Whether Two Objects Are the Same (Visual Basic)</span></span>

<span data-ttu-id="b047f-103">При наличии двух переменных, ссылающихся на объекты, можно использовать либо `Is` `IsNot` оператор OR, либо и то, и другое, чтобы определить, ссылаются ли они на один и тот же экземпляр.</span><span class="sxs-lookup"><span data-stu-id="b047f-103">If you have two variables that refer to objects, you can use either the `Is` or `IsNot` operator, or both, to determine whether they refer to the same instance.</span></span>  
  
### <a name="to-test-whether-two-objects-are-the-same"></a><span data-ttu-id="b047f-104">Проверка того, совпадают ли два объекта</span><span class="sxs-lookup"><span data-stu-id="b047f-104">To test whether two objects are the same</span></span>  
  
- <span data-ttu-id="b047f-105">Используйте [оператор is](../../../language-reference/operators/is-operator.md) или [IsNot](../../../language-reference/operators/isnot-operator.md) с двумя переменными в качестве операндов.</span><span class="sxs-lookup"><span data-stu-id="b047f-105">Use the [Is Operator](../../../language-reference/operators/is-operator.md) or the [IsNot Operator](../../../language-reference/operators/isnot-operator.md) with the two variables as operands.</span></span>  
  
     [!code-vb[VbVbalrOperators#69](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#69)]  
  
 <span data-ttu-id="b047f-106">Может потребоваться выполнить определенное действие в зависимости от того, ссылаются ли два объекта на один и тот же экземпляр.</span><span class="sxs-lookup"><span data-stu-id="b047f-106">You might want to take a certain action depending on whether two objects refer to the same instance.</span></span> <span data-ttu-id="b047f-107">Предыдущий пример сравнивает элемент управления с `c` активным элементом управления в форме `f` .</span><span class="sxs-lookup"><span data-stu-id="b047f-107">The preceding example compares control `c` against the active control on form `f`.</span></span> <span data-ttu-id="b047f-108">Если активный элемент управления отсутствует или имеется, но он не является одним и тем же экземпляром элемента управления `c` , то `If` выполнение инструкции завершается ошибкой и процедура возвращается без дальнейшей обработки.</span><span class="sxs-lookup"><span data-stu-id="b047f-108">If there is no active control, or if there is one but it is not the same control instance as `c`, then the `If` statement fails and the procedure returns without further processing.</span></span>  
  
 <span data-ttu-id="b047f-109">Независимо от того, используется ли `Is` `IsNot` для вас персональное удобство.</span><span class="sxs-lookup"><span data-stu-id="b047f-109">Whether you use `Is` or `IsNot` is a matter of personal convenience to you.</span></span> <span data-ttu-id="b047f-110">Один из них может быть проще читать, чем другой в данном выражении.</span><span class="sxs-lookup"><span data-stu-id="b047f-110">One might be easier to read than the other in a given expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b047f-111">См. также</span><span class="sxs-lookup"><span data-stu-id="b047f-111">See also</span></span>

- [<span data-ttu-id="b047f-112">Comparison Operators in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b047f-112">Comparison Operators in Visual Basic</span></span>](comparison-operators.md)
