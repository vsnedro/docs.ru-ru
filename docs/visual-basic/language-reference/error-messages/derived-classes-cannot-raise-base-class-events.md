---
title: Производные классы не могут вызывать события базового класса
ms.date: 07/20/2015
f1_keywords:
- vbc30029
- bc30029
helpviewer_keywords:
- BC30029
ms.assetid: 63afa1c6-2f93-4512-a2f0-372455979771
ms.openlocfilehash: 0233a1584c5e871506b5c4762e98874c343f19b8
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874480"
---
# <a name="derived-classes-cannot-raise-base-class-events"></a><span data-ttu-id="11e89-102">Производные классы не могут вызывать события базового класса</span><span class="sxs-lookup"><span data-stu-id="11e89-102">Derived classes cannot raise base class events</span></span>

<span data-ttu-id="11e89-103">Событие может быть вызвано только из области объявления, в которой оно объявлено.</span><span class="sxs-lookup"><span data-stu-id="11e89-103">An event can be raised only from the declaration space in which it is declared.</span></span> <span data-ttu-id="11e89-104">Таким образом, класс не может создавать события из любого другого класса, даже из того, от которого он является производным.</span><span class="sxs-lookup"><span data-stu-id="11e89-104">Therefore, a class cannot raise events from any other class, even one from which it is derived.</span></span>  
  
 <span data-ttu-id="11e89-105">**Идентификатор ошибки:** BC30029</span><span class="sxs-lookup"><span data-stu-id="11e89-105">**Error ID:** BC30029</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="11e89-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="11e89-106">To correct this error</span></span>  
  
- <span data-ttu-id="11e89-107">Переместите `Event` оператор или `RaiseEvent` инструкцию так, чтобы они насовпадали с одним и тем же классом.</span><span class="sxs-lookup"><span data-stu-id="11e89-107">Move the `Event` statement or the `RaiseEvent` statement so they are in the same class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11e89-108">См. также</span><span class="sxs-lookup"><span data-stu-id="11e89-108">See also</span></span>

- [<span data-ttu-id="11e89-109">Оператор Event</span><span class="sxs-lookup"><span data-stu-id="11e89-109">Event Statement</span></span>](../statements/event-statement.md)
- [<span data-ttu-id="11e89-110">Оператор RaiseEvent</span><span class="sxs-lookup"><span data-stu-id="11e89-110">RaiseEvent Statement</span></span>](../statements/raiseevent-statement.md)
