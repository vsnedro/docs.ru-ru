---
title: 'Оператору #ElseIf должен предшествовать соответствующий оператор #If или #ElseIf'
ms.date: 07/20/2015
f1_keywords:
- vbc30014
- bc30014
helpviewer_keywords:
- BC30014
ms.assetid: 5215585e-2efa-485a-9efe-9833a1cc83a0
ms.openlocfilehash: 06af269508db6a2b258251272fdc18ef20eb1c0f
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874441"
---
# <a name="elseif-must-be-preceded-by-a-matching-if-or-elseif"></a><span data-ttu-id="d8b11-102">Оператору #ElseIf должен предшествовать соответствующий оператор #If или #ElseIf</span><span class="sxs-lookup"><span data-stu-id="d8b11-102">'#ElseIf' must be preceded by a matching '#If' or '#ElseIf'</span></span>

<span data-ttu-id="d8b11-103">`#ElseIf` является директивой условной компиляции.</span><span class="sxs-lookup"><span data-stu-id="d8b11-103">`#ElseIf` is a conditional compilation directive.</span></span> <span data-ttu-id="d8b11-104">`#ElseIf`Оператору должно предшествовать соответствующее `#If` `#ElseIf` предложение или.</span><span class="sxs-lookup"><span data-stu-id="d8b11-104">An `#ElseIf` clause must be preceded by a matching `#If` or `#ElseIf` clause.</span></span>  
  
 <span data-ttu-id="d8b11-105">**Идентификатор ошибки:** BC30014</span><span class="sxs-lookup"><span data-stu-id="d8b11-105">**Error ID:** BC30014</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d8b11-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="d8b11-106">To correct this error</span></span>  
  
1. <span data-ttu-id="d8b11-107">Убедитесь, что предыдущий `#If` или `#ElseIf` не был отделен от него `#ElseIf` промежуточным блоком условной компиляции или неправильно размещен `#End If` .</span><span class="sxs-lookup"><span data-stu-id="d8b11-107">Check that a preceding `#If` or `#ElseIf` has not been separated from this `#ElseIf` by an intervening conditional compilation block or an incorrectly placed `#End If`.</span></span>  
  
2. <span data-ttu-id="d8b11-108">Если `#ElseIf` перед `#Else` директивой стоит либо удалить, `#Else` либо изменить ее на `#ElseIf` .</span><span class="sxs-lookup"><span data-stu-id="d8b11-108">If the `#ElseIf` is preceded by a `#Else` directive, either remove the `#Else` or change it to an `#ElseIf`.</span></span>  
  
3. <span data-ttu-id="d8b11-109">Если все остальное в порядке, добавьте директиву `#If` в начало блока условной компиляции.</span><span class="sxs-lookup"><span data-stu-id="d8b11-109">If everything else is in order, add an `#If` directive to the beginning of the conditional compilation block.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8b11-110">См. также</span><span class="sxs-lookup"><span data-stu-id="d8b11-110">See also</span></span>

- [<span data-ttu-id="d8b11-111">Директивы #If...Then...#Else</span><span class="sxs-lookup"><span data-stu-id="d8b11-111">#If...Then...#Else Directives</span></span>](../directives/if-then-else-directives.md)
