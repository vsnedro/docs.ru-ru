---
title: <eventname> является событием, поэтому его прямой вызов невозможен
ms.date: 07/20/2015
f1_keywords:
- bc32022
- vbc32022
helpviewer_keywords:
- BC32022
ms.assetid: 4dcfcb8d-a9fa-46a7-a034-29d9ff3a59b3
ms.openlocfilehash: 510fff5370e63a31ee271421c0ab6f154518899f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409599"
---
# <a name="eventname-is-an-event-and-cannot-be-called-directly"></a><span data-ttu-id="2ea88-102">\<eventname> является событием, поэтому его прямой вызов невозможен</span><span class="sxs-lookup"><span data-stu-id="2ea88-102">'\<eventname>' is an event, and cannot be called directly</span></span>
<span data-ttu-id="2ea88-103">"<`eventname`>" является событием, поэтому его нельзя вызывать напрямую.</span><span class="sxs-lookup"><span data-stu-id="2ea88-103">'<`eventname`>' is an event, and so cannot be called directly.</span></span> <span data-ttu-id="2ea88-104">`RaiseEvent`Для вызова события используйте инструкцию.</span><span class="sxs-lookup"><span data-stu-id="2ea88-104">Use a `RaiseEvent` statement to raise an event.</span></span>  
  
 <span data-ttu-id="2ea88-105">Вызов процедуры задает событие для имени процедуры.</span><span class="sxs-lookup"><span data-stu-id="2ea88-105">A procedure call specifies an event for the procedure name.</span></span> <span data-ttu-id="2ea88-106">Обработчик событий — это процедура, но само событие является сигнальным устройством, которое должно быть вызвано и обработано.</span><span class="sxs-lookup"><span data-stu-id="2ea88-106">An event handler is a procedure, but the event itself is a signaling device, which must be raised and handled.</span></span>  
  
 <span data-ttu-id="2ea88-107">**Идентификатор ошибки:** BC32022</span><span class="sxs-lookup"><span data-stu-id="2ea88-107">**Error ID:** BC32022</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="2ea88-108">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="2ea88-108">To correct this error</span></span>  
  
1. <span data-ttu-id="2ea88-109">Используйте `RaiseEvent` оператор, чтобы сообщить о событии и вызвать процедуру или процедуры, которые ее обработают.</span><span class="sxs-lookup"><span data-stu-id="2ea88-109">Use a `RaiseEvent` statement to signal an event and invoke the procedure or procedures that handle it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ea88-110">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="2ea88-110">See also</span></span>

- [<span data-ttu-id="2ea88-111">Оператор RaiseEvent</span><span class="sxs-lookup"><span data-stu-id="2ea88-111">RaiseEvent Statement</span></span>](../statements/raiseevent-statement.md)
