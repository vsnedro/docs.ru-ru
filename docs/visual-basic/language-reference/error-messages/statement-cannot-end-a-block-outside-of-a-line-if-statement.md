---
title: Оператор не может завершить блок за пределами однострочной инструкции If
ms.date: 07/20/2015
f1_keywords:
- vbc32005
- bc32005
helpviewer_keywords:
- BC32005
ms.assetid: 4039f51b-e0ee-4789-a89b-45d06de06b5d
ms.openlocfilehash: 3fe3faaa3637446bb6ab443ba1d6e1d1004b4d48
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400322"
---
# <a name="statement-cannot-end-a-block-outside-of-a-line-if-statement"></a><span data-ttu-id="61629-102">Оператор не может завершить блок за пределами однострочной инструкции If</span><span class="sxs-lookup"><span data-stu-id="61629-102">Statement cannot end a block outside of a line 'If' statement</span></span>
<span data-ttu-id="61629-103">Однострочный `If` оператор содержит несколько операторов, разделенных двоеточиями (:), одна из которых является `End` оператором для блока управления за пределами однострочного `If` .</span><span class="sxs-lookup"><span data-stu-id="61629-103">A single-line `If` statement contains several statements separated by colons (:), one of which is an `End` statement for a control block outside the single-line `If`.</span></span> <span data-ttu-id="61629-104">Однострочные `If` операторы не используют `End If` инструкцию.</span><span class="sxs-lookup"><span data-stu-id="61629-104">Single-line `If` statements do not use the `End If` statement.</span></span>  
  
 <span data-ttu-id="61629-105">**Идентификатор ошибки:** BC32005</span><span class="sxs-lookup"><span data-stu-id="61629-105">**Error ID:** BC32005</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="61629-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="61629-106">To correct this error</span></span>  
  
- <span data-ttu-id="61629-107">Переместите однострочный `If` оператор за пределы блока управления, содержащего `End If` оператор.</span><span class="sxs-lookup"><span data-stu-id="61629-107">Move the single-line `If` statement outside the control block that contains the `End If` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61629-108">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="61629-108">See also</span></span>

- [<span data-ttu-id="61629-109">Оператор If…Then…Else</span><span class="sxs-lookup"><span data-stu-id="61629-109">If...Then...Else Statement</span></span>](../statements/if-then-else-statement.md)
