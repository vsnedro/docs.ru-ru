---
title: Событие <eventname1> не может реализовать событие <eventname2> в интерфейсе <interface>, так как их делегируемые типы <delegate1> и <delegate2> не совпадают
ms.date: 07/20/2015
f1_keywords:
- vbc31423
- bc31423
helpviewer_keywords:
- BC31423
ms.assetid: 2e754b66-5836-48ff-9697-b9c0d7085f18
ms.openlocfilehash: 32d6733580de8798a66c30d486b8439befd2af19
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409612"
---
# <a name="event-eventname1-cannot-implement-event-eventname2-on-interface-interface-because-their-delegate-types-delegate1-and-delegate2-do-not-match"></a><span data-ttu-id="03960-102">Событие \<eventname1> не может реализовать событие \<eventname2> в интерфейсе \<interface>, так как их делегируемые типы \<delegate1> и \<delegate2> не совпадают</span><span class="sxs-lookup"><span data-stu-id="03960-102">Event '\<eventname1>' cannot implement event '\<eventname2>' on interface '\<interface>' because their delegate types '\<delegate1>' and '\<delegate2>' do not match</span></span>
<span data-ttu-id="03960-103">Visual Basic не может реализовать событие, так как тип делегата события не соответствует типу делегата события в интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="03960-103">Visual Basic cannot implement an event because the delegate type of the event does not match the delegate type of the event in the interface.</span></span> <span data-ttu-id="03960-104">Эта ошибка может возникнуть при определении нескольких событий в интерфейсе и последующей попытке их совместной реализации с использованием одного события.</span><span class="sxs-lookup"><span data-stu-id="03960-104">This error can occur when you define multiple events in an interface and then attempt to implement them together with the same event.</span></span> <span data-ttu-id="03960-105">Событие может реализовывать два или более событий, только если все они объявлены с помощью синтаксиса `As` и указывают один и тот же тип делегата.</span><span class="sxs-lookup"><span data-stu-id="03960-105">An event can implement two or more events only if all implemented events are declared using the `As` syntax and specify the same delegate type.</span></span>  
  
 <span data-ttu-id="03960-106">**Идентификатор ошибки:** BC31423</span><span class="sxs-lookup"><span data-stu-id="03960-106">**Error ID:** BC31423</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="03960-107">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="03960-107">To correct this error</span></span>  
  
- <span data-ttu-id="03960-108">Реализуйте события по отдельности.</span><span class="sxs-lookup"><span data-stu-id="03960-108">Implement the events separately.</span></span>  
  
     <span data-ttu-id="03960-109">—или—</span><span class="sxs-lookup"><span data-stu-id="03960-109">—or—</span></span>  
  
- <span data-ttu-id="03960-110">Определите события в интерфейсе с помощью `As` синтаксиса и укажите тот же тип делегата.</span><span class="sxs-lookup"><span data-stu-id="03960-110">Define the events in the interface using the `As` syntax and specify the same delegate type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03960-111">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="03960-111">See also</span></span>

- [<span data-ttu-id="03960-112">Оператор Event</span><span class="sxs-lookup"><span data-stu-id="03960-112">Event Statement</span></span>](../statements/event-statement.md)
- [<span data-ttu-id="03960-113">Оператор Delegate</span><span class="sxs-lookup"><span data-stu-id="03960-113">Delegate Statement</span></span>](../statements/delegate-statement.md)
- [<span data-ttu-id="03960-114">События</span><span class="sxs-lookup"><span data-stu-id="03960-114">Events</span></span>](../../programming-guide/language-features/events/index.md)
