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
ms.openlocfilehash: de995a13b34678410e2af74b59f2d0c467982b75
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84408488"
---
# <a name="addhandler-statement"></a><span data-ttu-id="b54aa-102">Оператор AddHandler</span><span class="sxs-lookup"><span data-stu-id="b54aa-102">AddHandler Statement</span></span>
<span data-ttu-id="b54aa-103">Связывает событие с обработчиком событий во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="b54aa-103">Associates an event with an event handler at run time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b54aa-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b54aa-104">Syntax</span></span>  
  
```vb  
AddHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a><span data-ttu-id="b54aa-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="b54aa-105">Parts</span></span>  
|||
|---|---|
|<span data-ttu-id="b54aa-106">event</span><span class="sxs-lookup"><span data-stu-id="b54aa-106">event</span></span>|<span data-ttu-id="b54aa-107">Имя обрабатываемого события.</span><span class="sxs-lookup"><span data-stu-id="b54aa-107">The name of the event to handle.</span></span>|  
|`eventhandler`|<span data-ttu-id="b54aa-108">Имя процедуры, которая обрабатывает событие.</span><span class="sxs-lookup"><span data-stu-id="b54aa-108">The name of a procedure that handles the event.</span></span>|
|||
  
## <a name="remarks"></a><span data-ttu-id="b54aa-109">Комментарии</span><span class="sxs-lookup"><span data-stu-id="b54aa-109">Remarks</span></span>  
 <span data-ttu-id="b54aa-110">`AddHandler`Инструкции и `RemoveHandler` позволяют запускать и прекращать обработку событий в любое время во время выполнения программы.</span><span class="sxs-lookup"><span data-stu-id="b54aa-110">The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling at any time during program execution.</span></span>  
  
 <span data-ttu-id="b54aa-111">Сигнатура `eventhandler` процедуры должна соответствовать сигнатуре события `event` .</span><span class="sxs-lookup"><span data-stu-id="b54aa-111">The signature of the `eventhandler` procedure must match the signature of the event `event`.</span></span>  
  
 <span data-ttu-id="b54aa-112">Как ключевое слово `Handles` так и оператор `AddHandler` позволяют задать обработку определенных событий конкретными процедурами, но между ними существуют различия.</span><span class="sxs-lookup"><span data-stu-id="b54aa-112">The `Handles` keyword and the `AddHandler` statement both allow you to specify that particular procedures handle particular events, but there are differences.</span></span> <span data-ttu-id="b54aa-113">Оператор `AddHandler` подключает процедуры к событиям во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="b54aa-113">The `AddHandler` statement connects procedures to events at run time.</span></span> <span data-ttu-id="b54aa-114">Используйте ключевое слово `Handles` при определении процедуры, чтобы указать, что она обрабатывает определенное событие.</span><span class="sxs-lookup"><span data-stu-id="b54aa-114">Use the `Handles` keyword when defining a procedure to specify that it handles a particular event.</span></span> <span data-ttu-id="b54aa-115">Дополнительные сведения см. в разделе [Handles](handles-clause.md).</span><span class="sxs-lookup"><span data-stu-id="b54aa-115">For more information, see [Handles](handles-clause.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b54aa-116">Для пользовательских событий `AddHandler` оператор вызывает `AddHandler` метод доступа события.</span><span class="sxs-lookup"><span data-stu-id="b54aa-116">For custom events, the `AddHandler` statement invokes the event's `AddHandler` accessor.</span></span> <span data-ttu-id="b54aa-117">Дополнительные сведения о пользовательских событиях см. в разделе [оператор Event](event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="b54aa-117">For more information on custom events, see [Event Statement](event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b54aa-118">Пример</span><span class="sxs-lookup"><span data-stu-id="b54aa-118">Example</span></span>  
 [!code-vb[VbVbalrEvents#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#17)]  
  
## <a name="see-also"></a><span data-ttu-id="b54aa-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b54aa-119">See also</span></span>

- [<span data-ttu-id="b54aa-120">Оператор RemoveHandler</span><span class="sxs-lookup"><span data-stu-id="b54aa-120">RemoveHandler Statement</span></span>](removehandler-statement.md)
- [<span data-ttu-id="b54aa-121">Маркеры</span><span class="sxs-lookup"><span data-stu-id="b54aa-121">Handles</span></span>](handles-clause.md)
- [<span data-ttu-id="b54aa-122">Оператор Event</span><span class="sxs-lookup"><span data-stu-id="b54aa-122">Event Statement</span></span>](event-statement.md)
- [<span data-ttu-id="b54aa-123">События</span><span class="sxs-lookup"><span data-stu-id="b54aa-123">Events</span></span>](../../programming-guide/language-features/events/index.md)
