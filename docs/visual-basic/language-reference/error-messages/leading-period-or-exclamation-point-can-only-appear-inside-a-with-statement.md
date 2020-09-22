---
title: Символ "." или "!", стоящий в начале оператора, может использоваться только внутри оператора "With"
ms.date: 07/20/2015
f1_keywords:
- vbc30157
- bc30157
helpviewer_keywords:
- BC30157
ms.assetid: 70daaee1-14f9-45b7-9f30-53794310b95e
ms.openlocfilehash: c39339a49c4aad4ba643facc2372333e7379ffa7
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873846"
---
# <a name="leading--or--can-only-appear-inside-a-with-statement"></a><span data-ttu-id="b5f3c-102">Символ "." или "!", стоящий в начале оператора, может использоваться только внутри оператора "With"</span><span class="sxs-lookup"><span data-stu-id="b5f3c-102">Leading '.' or '!' can only appear inside a 'With' statement</span></span>

<span data-ttu-id="b5f3c-103">Точка (.) или восклицательный знак (!), не находящиеся внутри `With` блока, происходит без выражения слева.</span><span class="sxs-lookup"><span data-stu-id="b5f3c-103">A period (.) or exclamation point (!) that is not inside a `With` block occurs without an expression on the left.</span></span> <span data-ttu-id="b5f3c-104">Для доступа к членам ( `.` ) и доступа к членам словаря ( `!` ) требуется выражение, указывающее элемент, содержащий элемент.</span><span class="sxs-lookup"><span data-stu-id="b5f3c-104">Member access (`.`) and dictionary member access (`!`) require an expression specifying the element that contains the member.</span></span> <span data-ttu-id="b5f3c-105">Он должен располагаться непосредственно слева от метода доступа или являться целевым объектом блока, `With` содержащего доступ к члену.</span><span class="sxs-lookup"><span data-stu-id="b5f3c-105">This must appear immediately to the left of the accessor or as the target of a `With` block containing the member access.</span></span>  
  
 <span data-ttu-id="b5f3c-106">**Идентификатор ошибки:** BC30157</span><span class="sxs-lookup"><span data-stu-id="b5f3c-106">**Error ID:** BC30157</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b5f3c-107">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="b5f3c-107">To correct this error</span></span>  
  
1. <span data-ttu-id="b5f3c-108">Убедитесь, что `With` блок имеет правильный формат.</span><span class="sxs-lookup"><span data-stu-id="b5f3c-108">Ensure that the `With` block is correctly formatted.</span></span>  
  
2. <span data-ttu-id="b5f3c-109">Если `With` блок отсутствует, добавьте выражение слева от метода доступа, результатом которого является определенный элемент, содержащий элемент.</span><span class="sxs-lookup"><span data-stu-id="b5f3c-109">If there is no `With` block, add an expression to the left of the accessor that evaluates to a defined element containing the member.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5f3c-110">См. также</span><span class="sxs-lookup"><span data-stu-id="b5f3c-110">See also</span></span>

- [<span data-ttu-id="b5f3c-111">Специальные символы в коде</span><span class="sxs-lookup"><span data-stu-id="b5f3c-111">Special Characters in Code</span></span>](../../programming-guide/program-structure/special-characters-in-code.md)
- [<span data-ttu-id="b5f3c-112">Оператор With…End With</span><span class="sxs-lookup"><span data-stu-id="b5f3c-112">With...End With Statement</span></span>](../statements/with-end-with-statement.md)
