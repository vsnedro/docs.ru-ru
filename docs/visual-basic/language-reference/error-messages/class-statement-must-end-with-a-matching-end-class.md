---
title: Оператор Class должен заканчиваться соответствующим End Class
ms.date: 07/20/2015
f1_keywords:
- vbc30481
- bc30481
helpviewer_keywords:
- BC30481
ms.assetid: 583f3029-bc3a-4e06-866f-92dbecc46f19
ms.openlocfilehash: 6889e97aad913f6911ce438892752542de0d10f0
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163198"
---
# <a name="bc30481-class-statement-must-end-with-a-matching-end-class"></a><span data-ttu-id="2f4c4-102">BC30481: оператор Class должен заканчиваться соответствующим оператором End Class</span><span class="sxs-lookup"><span data-stu-id="2f4c4-102">BC30481: 'Class' statement must end with a matching 'End Class'</span></span>

<span data-ttu-id="2f4c4-103">`Class` используется для запуска `Class` блока, поэтому он может находиться только в начале блока, при этом `End Class` блоку соответствует оператор сопоставления.</span><span class="sxs-lookup"><span data-stu-id="2f4c4-103">`Class` is used to initiate a `Class` block; hence it can only appear at the beginning of the block, with a matching `End Class` statement ending the block.</span></span> <span data-ttu-id="2f4c4-104">Либо имеется избыточный `Class` оператор, либо вы не закончили `Class` блок с помощью `End Class` .</span><span class="sxs-lookup"><span data-stu-id="2f4c4-104">Either you have a redundant `Class` statement, or you have not ended your `Class` block with `End Class`.</span></span>

 <span data-ttu-id="2f4c4-105">**Идентификатор ошибки:** BC30481</span><span class="sxs-lookup"><span data-stu-id="2f4c4-105">**Error ID:** BC30481</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="2f4c4-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="2f4c4-106">To correct this error</span></span>

- <span data-ttu-id="2f4c4-107">Найдите и удалите ненужный оператор `Class` .</span><span class="sxs-lookup"><span data-stu-id="2f4c4-107">Locate and remove the unnecessary `Class` statement.</span></span>

- <span data-ttu-id="2f4c4-108">Заключение `Class` блока с соответствующим `End Class` .</span><span class="sxs-lookup"><span data-stu-id="2f4c4-108">Conclude the `Class` block with a matching `End Class`.</span></span>

## <a name="see-also"></a><span data-ttu-id="2f4c4-109">См. также</span><span class="sxs-lookup"><span data-stu-id="2f4c4-109">See also</span></span>

- [<span data-ttu-id="2f4c4-110">End, \<keyword> Инструкция</span><span class="sxs-lookup"><span data-stu-id="2f4c4-110">End \<keyword> Statement</span></span>](../statements/end-keyword-statement.md)
- [<span data-ttu-id="2f4c4-111">Оператор Class</span><span class="sxs-lookup"><span data-stu-id="2f4c4-111">Class Statement</span></span>](../statements/class-statement.md)
