---
title: Символ "." или "!", стоящий в начале оператора, может использоваться только внутри оператора "With"
ms.date: 07/20/2015
f1_keywords:
- vbc30157
- bc30157
helpviewer_keywords:
- BC30157
ms.assetid: 70daaee1-14f9-45b7-9f30-53794310b95e
ms.openlocfilehash: 149acc2baac0f45fa971a11f254d694526d140d7
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397328"
---
# <a name="leading--or--can-only-appear-inside-a-with-statement"></a><span data-ttu-id="83220-102">Символ "." или "!", стоящий в начале оператора, может использоваться только внутри оператора "With"</span><span class="sxs-lookup"><span data-stu-id="83220-102">Leading '.' or '!' can only appear inside a 'With' statement</span></span>
<span data-ttu-id="83220-103">Точка (.) или восклицательный знак (!), не находящиеся внутри `With` блока, происходит без выражения слева.</span><span class="sxs-lookup"><span data-stu-id="83220-103">A period (.) or exclamation point (!) that is not inside a `With` block occurs without an expression on the left.</span></span> <span data-ttu-id="83220-104">Для доступа к членам ( `.` ) и доступа к членам словаря ( `!` ) требуется выражение, указывающее элемент, содержащий элемент.</span><span class="sxs-lookup"><span data-stu-id="83220-104">Member access (`.`) and dictionary member access (`!`) require an expression specifying the element that contains the member.</span></span> <span data-ttu-id="83220-105">Он должен располагаться непосредственно слева от метода доступа или являться целевым объектом блока, `With` содержащего доступ к члену.</span><span class="sxs-lookup"><span data-stu-id="83220-105">This must appear immediately to the left of the accessor or as the target of a `With` block containing the member access.</span></span>  
  
 <span data-ttu-id="83220-106">**Идентификатор ошибки:** BC30157</span><span class="sxs-lookup"><span data-stu-id="83220-106">**Error ID:** BC30157</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="83220-107">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="83220-107">To correct this error</span></span>  
  
1. <span data-ttu-id="83220-108">Убедитесь, что `With` блок имеет правильный формат.</span><span class="sxs-lookup"><span data-stu-id="83220-108">Ensure that the `With` block is correctly formatted.</span></span>  
  
2. <span data-ttu-id="83220-109">Если `With` блок отсутствует, добавьте выражение слева от метода доступа, результатом которого является определенный элемент, содержащий элемент.</span><span class="sxs-lookup"><span data-stu-id="83220-109">If there is no `With` block, add an expression to the left of the accessor that evaluates to a defined element containing the member.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83220-110">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="83220-110">See also</span></span>

- [<span data-ttu-id="83220-111">Специальные символы в коде</span><span class="sxs-lookup"><span data-stu-id="83220-111">Special Characters in Code</span></span>](../../programming-guide/program-structure/special-characters-in-code.md)
- [<span data-ttu-id="83220-112">Оператор With…End With</span><span class="sxs-lookup"><span data-stu-id="83220-112">With...End With Statement</span></span>](../statements/with-end-with-statement.md)
