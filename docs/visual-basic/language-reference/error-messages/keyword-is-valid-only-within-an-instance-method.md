---
title: <keyword> разрешено использовать только в методе экземпляра
ms.date: 07/20/2015
f1_keywords:
- bc30043
- vbc30043
helpviewer_keywords:
- BC30043
ms.assetid: 7973aa82-a681-440c-9bca-242627d7ba86
ms.openlocfilehash: 537689405ea30bdd7c075320eba58a8723a93cdb
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397406"
---
# <a name="keyword-is-valid-only-within-an-instance-method"></a><span data-ttu-id="16c7d-102">\<keyword> разрешено использовать только в методе экземпляра</span><span class="sxs-lookup"><span data-stu-id="16c7d-102">'\<keyword>' is valid only within an instance method</span></span>
<span data-ttu-id="16c7d-103">`Me` `MyClass` Ключевые слова, и `MyBase` относятся к конкретным экземплярам класса.</span><span class="sxs-lookup"><span data-stu-id="16c7d-103">The `Me`, `MyClass`, and `MyBase` keywords refer to specific class instances.</span></span> <span data-ttu-id="16c7d-104">Их нельзя использовать в общей `Function` или `Sub` процедурной среде.</span><span class="sxs-lookup"><span data-stu-id="16c7d-104">You cannot use them inside a shared `Function` or `Sub` procedure.</span></span>  
  
 <span data-ttu-id="16c7d-105">**Идентификатор ошибки:** BC30043</span><span class="sxs-lookup"><span data-stu-id="16c7d-105">**Error ID:** BC30043</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="16c7d-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="16c7d-106">To correct this error</span></span>  
  
- <span data-ttu-id="16c7d-107">Удалите ключевое слово из процедуры или удалите `Shared` ключевое слово из объявления процедуры.</span><span class="sxs-lookup"><span data-stu-id="16c7d-107">Remove the keyword from the procedure, or remove the `Shared` keyword from the procedure declaration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16c7d-108">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="16c7d-108">See also</span></span>

- [<span data-ttu-id="16c7d-109">Присваивание объектных переменных</span><span class="sxs-lookup"><span data-stu-id="16c7d-109">Object Variable Assignment</span></span>](../../programming-guide/language-features/variables/object-variable-assignment.md)
- [<span data-ttu-id="16c7d-110">Me, My, MyBase и MyClass</span><span class="sxs-lookup"><span data-stu-id="16c7d-110">Me, My, MyBase, and MyClass</span></span>](../../programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [<span data-ttu-id="16c7d-111">Основы наследования</span><span class="sxs-lookup"><span data-stu-id="16c7d-111">Inheritance Basics</span></span>](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md)
