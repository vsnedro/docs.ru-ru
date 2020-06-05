---
title: Оператор RemoveHandler
ms.date: 07/20/2015
f1_keywords:
- vb.RemoveHandlerMethod
- vb.RemoveHandler
- RemoveHandler
helpviewer_keywords:
- RemoveHandler keyword [Visual Basic]
- RemoveHandler statement [Visual Basic]
ms.assetid: 647cd825-e877-4910-b4f1-8d168beebe6a
ms.openlocfilehash: 3514a79f2430b148e6a3727b83029b4e207a677b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404256"
---
# <a name="removehandler-statement"></a><span data-ttu-id="4d573-102">Оператор RemoveHandler</span><span class="sxs-lookup"><span data-stu-id="4d573-102">RemoveHandler Statement</span></span>
<span data-ttu-id="4d573-103">Удаляет связь между событием и обработчиком событий.</span><span class="sxs-lookup"><span data-stu-id="4d573-103">Removes the association between an event and an event handler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d573-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4d573-104">Syntax</span></span>  
  
```vb  
RemoveHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a><span data-ttu-id="4d573-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="4d573-105">Parts</span></span>  
  
|<span data-ttu-id="4d573-106">Термин</span><span class="sxs-lookup"><span data-stu-id="4d573-106">Term</span></span>|<span data-ttu-id="4d573-107">Определение</span><span class="sxs-lookup"><span data-stu-id="4d573-107">Definition</span></span>|  
|---|---|  
|`event`|<span data-ttu-id="4d573-108">Имя обрабатываемого события.</span><span class="sxs-lookup"><span data-stu-id="4d573-108">The name of the event being handled.</span></span>|  
|`eventhandler`|<span data-ttu-id="4d573-109">Имя процедуры, которая в настоящее время обрабатывает событие.</span><span class="sxs-lookup"><span data-stu-id="4d573-109">The name of the procedure currently handling the event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4d573-110">Комментарии</span><span class="sxs-lookup"><span data-stu-id="4d573-110">Remarks</span></span>  
 <span data-ttu-id="4d573-111">`AddHandler`Инструкции и `RemoveHandler` позволяют запускать и прекращать обработку событий для определенного события в любое время во время выполнения программы.</span><span class="sxs-lookup"><span data-stu-id="4d573-111">The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling for a specific event at any time during program execution.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4d573-112">Для пользовательских событий `RemoveHandler` оператор вызывает `RemoveHandler` метод доступа события.</span><span class="sxs-lookup"><span data-stu-id="4d573-112">For custom events, the `RemoveHandler` statement invokes the event's `RemoveHandler` accessor.</span></span> <span data-ttu-id="4d573-113">Дополнительные сведения о пользовательских событиях см. в разделе [оператор Event](event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="4d573-113">For more information on custom events, see [Event Statement](event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4d573-114">Пример</span><span class="sxs-lookup"><span data-stu-id="4d573-114">Example</span></span>  
 [!code-vb[VbVbalrEvents#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#17)]  
  
## <a name="see-also"></a><span data-ttu-id="4d573-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="4d573-115">See also</span></span>

- [<span data-ttu-id="4d573-116">Оператор AddHandler</span><span class="sxs-lookup"><span data-stu-id="4d573-116">AddHandler Statement</span></span>](addhandler-statement.md)
- [<span data-ttu-id="4d573-117">Маркеры</span><span class="sxs-lookup"><span data-stu-id="4d573-117">Handles</span></span>](handles-clause.md)
- [<span data-ttu-id="4d573-118">Оператор Event</span><span class="sxs-lookup"><span data-stu-id="4d573-118">Event Statement</span></span>](event-statement.md)
- [<span data-ttu-id="4d573-119">События</span><span class="sxs-lookup"><span data-stu-id="4d573-119">Events</span></span>](../../programming-guide/language-features/events/index.md)
