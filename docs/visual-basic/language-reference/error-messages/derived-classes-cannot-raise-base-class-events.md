---
title: Производные классы не могут вызывать события базового класса
ms.date: 07/20/2015
f1_keywords:
- vbc30029
- bc30029
helpviewer_keywords:
- BC30029
ms.assetid: 63afa1c6-2f93-4512-a2f0-372455979771
ms.openlocfilehash: c59212a28ba27123a7db9163ff7437c159a3d310
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409703"
---
# <a name="derived-classes-cannot-raise-base-class-events"></a><span data-ttu-id="e8902-102">Производные классы не могут вызывать события базового класса</span><span class="sxs-lookup"><span data-stu-id="e8902-102">Derived classes cannot raise base class events</span></span>
<span data-ttu-id="e8902-103">Событие может быть вызвано только из области объявления, в которой оно объявлено.</span><span class="sxs-lookup"><span data-stu-id="e8902-103">An event can be raised only from the declaration space in which it is declared.</span></span> <span data-ttu-id="e8902-104">Таким образом, класс не может создавать события из любого другого класса, даже из того, от которого он является производным.</span><span class="sxs-lookup"><span data-stu-id="e8902-104">Therefore, a class cannot raise events from any other class, even one from which it is derived.</span></span>  
  
 <span data-ttu-id="e8902-105">**Идентификатор ошибки:** BC30029</span><span class="sxs-lookup"><span data-stu-id="e8902-105">**Error ID:** BC30029</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e8902-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="e8902-106">To correct this error</span></span>  
  
- <span data-ttu-id="e8902-107">Переместите `Event` оператор или `RaiseEvent` инструкцию так, чтобы они насовпадали с одним и тем же классом.</span><span class="sxs-lookup"><span data-stu-id="e8902-107">Move the `Event` statement or the `RaiseEvent` statement so they are in the same class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8902-108">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e8902-108">See also</span></span>

- [<span data-ttu-id="e8902-109">Оператор Event</span><span class="sxs-lookup"><span data-stu-id="e8902-109">Event Statement</span></span>](../statements/event-statement.md)
- [<span data-ttu-id="e8902-110">Оператор RaiseEvent</span><span class="sxs-lookup"><span data-stu-id="e8902-110">RaiseEvent Statement</span></span>](../statements/raiseevent-statement.md)
