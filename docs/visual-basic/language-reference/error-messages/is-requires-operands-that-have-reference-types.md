---
title: При использовании оператора сравнения Is требуются операнды со ссылочным типом, однако данный операнд имеет тип значения <typename>
ms.date: 07/20/2015
f1_keywords:
- bc30020
- vbc30020
helpviewer_keywords:
- BC30020
ms.assetid: 228afebd-1203-4bd3-8d7a-c5c56f3cedc4
ms.openlocfilehash: 5c9f156272cd0c3cbaeadbc0e162129f41619cc6
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163354"
---
# <a name="bc30020-is-requires-operands-that-have-reference-types-but-this-operand-has-the-value-type-typename"></a><span data-ttu-id="5e008-102">BC30020: для "is" требуются операнды, имеющие ссылочные типы, но этот операнд имеет тип значения " \<typename> "</span><span class="sxs-lookup"><span data-stu-id="5e008-102">BC30020: 'Is' requires operands that have reference types, but this operand has the value type '\<typename>'</span></span>

<span data-ttu-id="5e008-103">`Is`Оператор сравнения определяет, ссылаются ли две объектные переменные на один и тот же экземпляр.</span><span class="sxs-lookup"><span data-stu-id="5e008-103">The `Is` comparison operator determines whether two object variables refer to the same instance.</span></span> <span data-ttu-id="5e008-104">Это сравнение не определено для типов значений.</span><span class="sxs-lookup"><span data-stu-id="5e008-104">This comparison is not defined for value types.</span></span>

 <span data-ttu-id="5e008-105">**Идентификатор ошибки:** BC30020</span><span class="sxs-lookup"><span data-stu-id="5e008-105">**Error ID:** BC30020</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="5e008-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="5e008-106">To correct this error</span></span>

- <span data-ttu-id="5e008-107">Используйте соответствующий оператор арифметического сравнения или `Like` оператор для сравнения двух типов значений.</span><span class="sxs-lookup"><span data-stu-id="5e008-107">Use the appropriate arithmetic comparison operator or the `Like` operator to compare two value types.</span></span>

## <a name="see-also"></a><span data-ttu-id="5e008-108">См. также</span><span class="sxs-lookup"><span data-stu-id="5e008-108">See also</span></span>

- [<span data-ttu-id="5e008-109">Оператор Is</span><span class="sxs-lookup"><span data-stu-id="5e008-109">Is Operator</span></span>](../operators/is-operator.md)
- [<span data-ttu-id="5e008-110">Оператор Like</span><span class="sxs-lookup"><span data-stu-id="5e008-110">Like Operator</span></span>](../operators/like-operator.md)
- [<span data-ttu-id="5e008-111">Операторы сравнения</span><span class="sxs-lookup"><span data-stu-id="5e008-111">Comparison Operators</span></span>](../operators/comparison-operators.md)
