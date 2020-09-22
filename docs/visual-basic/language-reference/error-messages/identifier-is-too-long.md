---
title: Слишком длинный идентификатор
ms.date: 07/20/2015
f1_keywords:
- bc30033
- vbc30033
helpviewer_keywords:
- BC30033
ms.assetid: 3d07f6d0-9a2f-49ca-94e8-1e354932e855
ms.openlocfilehash: 084e3d9306ad84d7e6e36e5fe4bbfc868b8dfac6
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874009"
---
# <a name="identifier-is-too-long"></a><span data-ttu-id="76c08-102">Слишком длинный идентификатор</span><span class="sxs-lookup"><span data-stu-id="76c08-102">Identifier is too long</span></span>

<span data-ttu-id="76c08-103">Имя или идентификатор каждого элемента программирования ограничено 1023 символами.</span><span class="sxs-lookup"><span data-stu-id="76c08-103">The name, or identifier, of every programming element is limited to 1023 characters.</span></span> <span data-ttu-id="76c08-104">Кроме того, полное имя не может содержать более 1023 символов.</span><span class="sxs-lookup"><span data-stu-id="76c08-104">In addition, a fully qualified name cannot exceed 1023 characters.</span></span> <span data-ttu-id="76c08-105">Это означает, что длина строки идентификатора ( `<namespace>.<...>.<namespace>.<class>.<element>` ) не может превышать 1023 символов, включая символы оператора доступа к членам ( `.` ).</span><span class="sxs-lookup"><span data-stu-id="76c08-105">This means that the entire identifier string (`<namespace>.<...>.<namespace>.<class>.<element>`) cannot be more than 1023 characters long, including the member-access operator (`.`) characters.</span></span>  
  
 <span data-ttu-id="76c08-106">**Идентификатор ошибки:** BC30033</span><span class="sxs-lookup"><span data-stu-id="76c08-106">**Error ID:** BC30033</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="76c08-107">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="76c08-107">To correct this error</span></span>  
  
- <span data-ttu-id="76c08-108">Уменьшите длину идентификатора.</span><span class="sxs-lookup"><span data-stu-id="76c08-108">Reduce the length of the identifier.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76c08-109">См. также</span><span class="sxs-lookup"><span data-stu-id="76c08-109">See also</span></span>

- [<span data-ttu-id="76c08-110">Declared Element Names</span><span class="sxs-lookup"><span data-stu-id="76c08-110">Declared Element Names</span></span>](../../programming-guide/language-features/declared-elements/declared-element-names.md)
