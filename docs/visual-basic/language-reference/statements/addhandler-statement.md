---
title: Оператор AddHandler
ms.date: 07/20/2015
f1_keywords:
- vb.AddHandlerMethod
- addhandler
- vb.addhandler
helpviewer_keywords:
- AddHandler statement [Visual Basic]
ms.assetid: cfe69799-2a0f-42c0-a99e-09fed954da01
ms.openlocfilehash: 79dbe174209e91f13f5b43e8cdeb0b42edc4d163
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90866707"
---
# <a name="addhandler-statement"></a><span data-ttu-id="88bed-102">Оператор AddHandler</span><span class="sxs-lookup"><span data-stu-id="88bed-102">AddHandler Statement</span></span>

<span data-ttu-id="88bed-103">Связывает событие с обработчиком событий во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="88bed-103">Associates an event with an event handler at run time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88bed-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="88bed-104">Syntax</span></span>  
  
```vb  
AddHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a><span data-ttu-id="88bed-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="88bed-105">Parts</span></span>  

|||
|---|---|
|<span data-ttu-id="88bed-106">event</span><span class="sxs-lookup"><span data-stu-id="88bed-106">event</span></span>|<span data-ttu-id="88bed-107">Имя обрабатываемого события.</span><span class="sxs-lookup"><span data-stu-id="88bed-107">The name of the event to handle.</span></span>|  
|`eventhandler`|<span data-ttu-id="88bed-108">Имя процедуры, которая обрабатывает событие.</span><span class="sxs-lookup"><span data-stu-id="88bed-108">The name of a procedure that handles the event.</span></span>|
|||
  
## <a name="remarks"></a><span data-ttu-id="88bed-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="88bed-109">Remarks</span></span>  

 <span data-ttu-id="88bed-110">`AddHandler`Инструкции и `RemoveHandler` позволяют запускать и прекращать обработку событий в любое время во время выполнения программы.</span><span class="sxs-lookup"><span data-stu-id="88bed-110">The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling at any time during program execution.</span></span>  
  
 <span data-ttu-id="88bed-111">Сигнатура `eventhandler` процедуры должна соответствовать сигнатуре события `event` .</span><span class="sxs-lookup"><span data-stu-id="88bed-111">The signature of the `eventhandler` procedure must match the signature of the event `event`.</span></span>  
  
 <span data-ttu-id="88bed-112">Как ключевое слово `Handles` так и оператор `AddHandler` позволяют задать обработку определенных событий конкретными процедурами, но между ними существуют различия.</span><span class="sxs-lookup"><span data-stu-id="88bed-112">The `Handles` keyword and the `AddHandler` statement both allow you to specify that particular procedures handle particular events, but there are differences.</span></span> <span data-ttu-id="88bed-113">Оператор `AddHandler` подключает процедуры к событиям во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="88bed-113">The `AddHandler` statement connects procedures to events at run time.</span></span> <span data-ttu-id="88bed-114">Используйте ключевое слово `Handles` при определении процедуры, чтобы указать, что она обрабатывает определенное событие.</span><span class="sxs-lookup"><span data-stu-id="88bed-114">Use the `Handles` keyword when defining a procedure to specify that it handles a particular event.</span></span> <span data-ttu-id="88bed-115">Дополнительные сведения см. в разделе [Handles](handles-clause.md).</span><span class="sxs-lookup"><span data-stu-id="88bed-115">For more information, see [Handles](handles-clause.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="88bed-116">Для пользовательских событий `AddHandler` оператор вызывает `AddHandler` метод доступа события.</span><span class="sxs-lookup"><span data-stu-id="88bed-116">For custom events, the `AddHandler` statement invokes the event's `AddHandler` accessor.</span></span> <span data-ttu-id="88bed-117">Дополнительные сведения о пользовательских событиях см. в разделе [оператор Event](event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="88bed-117">For more information on custom events, see [Event Statement](event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="88bed-118">Пример</span><span class="sxs-lookup"><span data-stu-id="88bed-118">Example</span></span>  

 [!code-vb[VbVbalrEvents#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#17)]  
  
## <a name="see-also"></a><span data-ttu-id="88bed-119">См. также</span><span class="sxs-lookup"><span data-stu-id="88bed-119">See also</span></span>

- [<span data-ttu-id="88bed-120">Оператор RemoveHandler</span><span class="sxs-lookup"><span data-stu-id="88bed-120">RemoveHandler Statement</span></span>](removehandler-statement.md)
- [<span data-ttu-id="88bed-121">Маркеры</span><span class="sxs-lookup"><span data-stu-id="88bed-121">Handles</span></span>](handles-clause.md)
- [<span data-ttu-id="88bed-122">Оператор Event</span><span class="sxs-lookup"><span data-stu-id="88bed-122">Event Statement</span></span>](event-statement.md)
- [<span data-ttu-id="88bed-123">События</span><span class="sxs-lookup"><span data-stu-id="88bed-123">Events</span></span>](../../programming-guide/language-features/events/index.md)
