---
title: При использовании оператора сравнения Is требуются операнды со ссылочным типом, однако данный операнд имеет тип значения <typename>
ms.date: 07/20/2015
f1_keywords:
- bc30020
- vbc30020
helpviewer_keywords:
- BC30020
ms.assetid: 228afebd-1203-4bd3-8d7a-c5c56f3cedc4
ms.openlocfilehash: daf9724fef81b4d7adb4f571ee950723aec09d8d
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873914"
---
# <a name="is-requires-operands-that-have-reference-types-but-this-operand-has-the-value-type-typename"></a><span data-ttu-id="d2cb7-102">При использовании оператора сравнения Is требуются операнды со ссылочным типом, однако данный операнд имеет тип значения \<typename></span><span class="sxs-lookup"><span data-stu-id="d2cb7-102">'Is' requires operands that have reference types, but this operand has the value type '\<typename>'</span></span>

<span data-ttu-id="d2cb7-103">`Is`Оператор сравнения определяет, ссылаются ли две объектные переменные на один и тот же экземпляр.</span><span class="sxs-lookup"><span data-stu-id="d2cb7-103">The `Is` comparison operator determines whether two object variables refer to the same instance.</span></span> <span data-ttu-id="d2cb7-104">Это сравнение не определено для типов значений.</span><span class="sxs-lookup"><span data-stu-id="d2cb7-104">This comparison is not defined for value types.</span></span>  
  
 <span data-ttu-id="d2cb7-105">**Идентификатор ошибки:** BC30020</span><span class="sxs-lookup"><span data-stu-id="d2cb7-105">**Error ID:** BC30020</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d2cb7-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="d2cb7-106">To correct this error</span></span>  
  
- <span data-ttu-id="d2cb7-107">Используйте соответствующий оператор арифметического сравнения или `Like` оператор для сравнения двух типов значений.</span><span class="sxs-lookup"><span data-stu-id="d2cb7-107">Use the appropriate arithmetic comparison operator or the `Like` operator to compare two value types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2cb7-108">См. также</span><span class="sxs-lookup"><span data-stu-id="d2cb7-108">See also</span></span>

- [<span data-ttu-id="d2cb7-109">Оператор Is</span><span class="sxs-lookup"><span data-stu-id="d2cb7-109">Is Operator</span></span>](../operators/is-operator.md)
- [<span data-ttu-id="d2cb7-110">Оператор Like</span><span class="sxs-lookup"><span data-stu-id="d2cb7-110">Like Operator</span></span>](../operators/like-operator.md)
- [<span data-ttu-id="d2cb7-111">Операторы сравнения</span><span class="sxs-lookup"><span data-stu-id="d2cb7-111">Comparison Operators</span></span>](../operators/comparison-operators.md)
