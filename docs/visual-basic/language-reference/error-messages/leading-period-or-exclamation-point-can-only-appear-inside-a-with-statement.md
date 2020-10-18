---
title: Символ "." или "!", стоящий в начале оператора, может использоваться только внутри оператора "With"
ms.date: 07/20/2015
f1_keywords:
- vbc30157
- bc30157
helpviewer_keywords:
- BC30157
ms.assetid: 70daaee1-14f9-45b7-9f30-53794310b95e
ms.openlocfilehash: 4ff273d5930fe58a5bccf0f4f4c10e971d777d01
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162509"
---
# <a name="bc30157-leading--or--can-only-appear-inside-a-with-statement"></a><span data-ttu-id="a9a64-102">BC30157: ведущие "." или "!" могут использоваться только в операторе "with"</span><span class="sxs-lookup"><span data-stu-id="a9a64-102">BC30157: Leading '.' or '!' can only appear inside a 'With' statement</span></span>

<span data-ttu-id="a9a64-103">Точка (.) или восклицательный знак (!), не находящиеся внутри `With` блока, происходит без выражения слева.</span><span class="sxs-lookup"><span data-stu-id="a9a64-103">A period (.) or exclamation point (!) that is not inside a `With` block occurs without an expression on the left.</span></span> <span data-ttu-id="a9a64-104">Для доступа к членам ( `.` ) и доступа к членам словаря ( `!` ) требуется выражение, указывающее элемент, содержащий элемент.</span><span class="sxs-lookup"><span data-stu-id="a9a64-104">Member access (`.`) and dictionary member access (`!`) require an expression specifying the element that contains the member.</span></span> <span data-ttu-id="a9a64-105">Он должен располагаться непосредственно слева от метода доступа или являться целевым объектом блока, `With` содержащего доступ к члену.</span><span class="sxs-lookup"><span data-stu-id="a9a64-105">This must appear immediately to the left of the accessor or as the target of a `With` block containing the member access.</span></span>

 <span data-ttu-id="a9a64-106">**Идентификатор ошибки:** BC30157</span><span class="sxs-lookup"><span data-stu-id="a9a64-106">**Error ID:** BC30157</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="a9a64-107">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="a9a64-107">To correct this error</span></span>

1. <span data-ttu-id="a9a64-108">Убедитесь, что `With` блок имеет правильный формат.</span><span class="sxs-lookup"><span data-stu-id="a9a64-108">Ensure that the `With` block is correctly formatted.</span></span>

2. <span data-ttu-id="a9a64-109">Если `With` блок отсутствует, добавьте выражение слева от метода доступа, результатом которого является определенный элемент, содержащий элемент.</span><span class="sxs-lookup"><span data-stu-id="a9a64-109">If there is no `With` block, add an expression to the left of the accessor that evaluates to a defined element containing the member.</span></span>

## <a name="see-also"></a><span data-ttu-id="a9a64-110">См. также</span><span class="sxs-lookup"><span data-stu-id="a9a64-110">See also</span></span>

- [<span data-ttu-id="a9a64-111">Специальные символы в коде</span><span class="sxs-lookup"><span data-stu-id="a9a64-111">Special Characters in Code</span></span>](../../programming-guide/program-structure/special-characters-in-code.md)
- [<span data-ttu-id="a9a64-112">Оператор With…End With</span><span class="sxs-lookup"><span data-stu-id="a9a64-112">With...End With Statement</span></span>](../statements/with-end-with-statement.md)
