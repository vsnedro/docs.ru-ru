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
ms.openlocfilehash: b215225dbc2d8c0d2bdfe2206e5d4a4f1faa6d0c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403425"
---
# <a name="how-to-test-whether-two-objects-are-the-same-visual-basic"></a><span data-ttu-id="20d03-102">Практическое руководство. Проверка совпадения двух объектов (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="20d03-102">How to: Test Whether Two Objects Are the Same (Visual Basic)</span></span>
<span data-ttu-id="20d03-103">При наличии двух переменных, ссылающихся на объекты, можно использовать либо `Is` `IsNot` оператор OR, либо и то, и другое, чтобы определить, ссылаются ли они на один и тот же экземпляр.</span><span class="sxs-lookup"><span data-stu-id="20d03-103">If you have two variables that refer to objects, you can use either the `Is` or `IsNot` operator, or both, to determine whether they refer to the same instance.</span></span>  
  
### <a name="to-test-whether-two-objects-are-the-same"></a><span data-ttu-id="20d03-104">Проверка того, совпадают ли два объекта</span><span class="sxs-lookup"><span data-stu-id="20d03-104">To test whether two objects are the same</span></span>  
  
- <span data-ttu-id="20d03-105">Используйте [оператор is](../../../language-reference/operators/is-operator.md) или [IsNot](../../../language-reference/operators/isnot-operator.md) с двумя переменными в качестве операндов.</span><span class="sxs-lookup"><span data-stu-id="20d03-105">Use the [Is Operator](../../../language-reference/operators/is-operator.md) or the [IsNot Operator](../../../language-reference/operators/isnot-operator.md) with the two variables as operands.</span></span>  
  
     [!code-vb[VbVbalrOperators#69](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#69)]  
  
 <span data-ttu-id="20d03-106">Может потребоваться выполнить определенное действие в зависимости от того, ссылаются ли два объекта на один и тот же экземпляр.</span><span class="sxs-lookup"><span data-stu-id="20d03-106">You might want to take a certain action depending on whether two objects refer to the same instance.</span></span> <span data-ttu-id="20d03-107">Предыдущий пример сравнивает элемент управления с `c` активным элементом управления в форме `f` .</span><span class="sxs-lookup"><span data-stu-id="20d03-107">The preceding example compares control `c` against the active control on form `f`.</span></span> <span data-ttu-id="20d03-108">Если активный элемент управления отсутствует или имеется, но он не является одним и тем же экземпляром элемента управления `c` , то `If` выполнение инструкции завершается ошибкой и процедура возвращается без дальнейшей обработки.</span><span class="sxs-lookup"><span data-stu-id="20d03-108">If there is no active control, or if there is one but it is not the same control instance as `c`, then the `If` statement fails and the procedure returns without further processing.</span></span>  
  
 <span data-ttu-id="20d03-109">Независимо от того, используется ли `Is` `IsNot` для вас персональное удобство.</span><span class="sxs-lookup"><span data-stu-id="20d03-109">Whether you use `Is` or `IsNot` is a matter of personal convenience to you.</span></span> <span data-ttu-id="20d03-110">Один из них может быть проще читать, чем другой в данном выражении.</span><span class="sxs-lookup"><span data-stu-id="20d03-110">One might be easier to read than the other in a given expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20d03-111">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="20d03-111">See also</span></span>

- [<span data-ttu-id="20d03-112">Comparison Operators in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="20d03-112">Comparison Operators in Visual Basic</span></span>](comparison-operators.md)
