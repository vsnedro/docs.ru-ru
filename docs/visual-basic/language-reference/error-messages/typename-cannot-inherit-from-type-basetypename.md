---
title: <typename> не может наследоваться от <type><basetypename>, поскольку он расширяет доступ базового типа <type> за пределы сборки
ms.date: 07/20/2015
f1_keywords:
- vbc30910
- bc30910
helpviewer_keywords:
- BC30910
ms.assetid: 68fc05c5-5d55-4742-9a3b-ea04312594f4
ms.openlocfilehash: 5adb5a74c220c7b2f95ac7370040a7fa2bd34299
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90872073"
---
# <a name="typename-cannot-inherit-from-type-basetypename-because-it-expands-the-access-of-the-base-type-outside-the-assembly"></a><span data-ttu-id="2a4a8-102">\<typename> не может наследоваться от \<type>\<basetypename>, поскольку он расширяет доступ базового типа \<type> за пределы сборки</span><span class="sxs-lookup"><span data-stu-id="2a4a8-102">'\<typename>' cannot inherit from \<type> '\<basetypename>' because it expands the access of the base \<type> outside the assembly</span></span>

<span data-ttu-id="2a4a8-103">Класс или интерфейс наследует от базового класса или интерфейса, но имеет менее четкий уровень доступа.</span><span class="sxs-lookup"><span data-stu-id="2a4a8-103">A class or interface inherits from a base class or interface but has a less restrictive access level.</span></span>  
  
 <span data-ttu-id="2a4a8-104">Например, `Public` интерфейс наследует от `Friend` интерфейса, или `Protected` класс наследует от `Private` класса.</span><span class="sxs-lookup"><span data-stu-id="2a4a8-104">For example, a `Public` interface inherits from a `Friend` interface, or a `Protected` class inherits from a `Private` class.</span></span> <span data-ttu-id="2a4a8-105">Это предоставляет базовый класс или интерфейс для доступа за пределами предполагаемого уровня.</span><span class="sxs-lookup"><span data-stu-id="2a4a8-105">This exposes the base class or interface to access beyond the intended level.</span></span>  
  
 <span data-ttu-id="2a4a8-106">**Идентификатор ошибки:** BC30910</span><span class="sxs-lookup"><span data-stu-id="2a4a8-106">**Error ID:** BC30910</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="2a4a8-107">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="2a4a8-107">To correct this error</span></span>  
  
- <span data-ttu-id="2a4a8-108">Измените уровень доступа производного класса или интерфейса, чтобы он был по крайней мере максимальным по отношению к базовому классу или интерфейсу.</span><span class="sxs-lookup"><span data-stu-id="2a4a8-108">Change the access level of the derived class or interface to be at least as restrictive as that of the base class or interface.</span></span>  
  
     <span data-ttu-id="2a4a8-109">-или-</span><span class="sxs-lookup"><span data-stu-id="2a4a8-109">-or-</span></span>  
  
- <span data-ttu-id="2a4a8-110">Если требуется менее четкий уровень доступа, удалите `Inherits` оператор.</span><span class="sxs-lookup"><span data-stu-id="2a4a8-110">If you require the less restrictive access level, remove the `Inherits` statement.</span></span> <span data-ttu-id="2a4a8-111">Наследование от более ограниченного базового класса или интерфейса невозможно.</span><span class="sxs-lookup"><span data-stu-id="2a4a8-111">You cannot inherit from a more restricted base class or interface.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a4a8-112">См. также</span><span class="sxs-lookup"><span data-stu-id="2a4a8-112">See also</span></span>

- [<span data-ttu-id="2a4a8-113">Оператор Class</span><span class="sxs-lookup"><span data-stu-id="2a4a8-113">Class Statement</span></span>](../statements/class-statement.md)
- [<span data-ttu-id="2a4a8-114">Оператор Interface</span><span class="sxs-lookup"><span data-stu-id="2a4a8-114">Interface Statement</span></span>](../statements/interface-statement.md)
- [<span data-ttu-id="2a4a8-115">Inherits Statement</span><span class="sxs-lookup"><span data-stu-id="2a4a8-115">Inherits Statement</span></span>](../statements/inherits-statement.md)
- [<span data-ttu-id="2a4a8-116">Уровни доступа в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2a4a8-116">Access levels in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/access-levels.md)
