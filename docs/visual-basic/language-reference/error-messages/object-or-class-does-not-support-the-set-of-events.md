---
title: Объект или класс не поддерживает набор событий
ms.date: 07/20/2015
f1_keywords:
- vbrID459
ms.assetid: 785df3f3-2aae-4a25-af36-1f9879d4e5fd
ms.openlocfilehash: e55a5515d88bd2782e31fdea7c07e16c595d43b5
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873658"
---
# <a name="object-or-class-does-not-support-the-set-of-events"></a><span data-ttu-id="89320-102">Объект или класс не поддерживает набор событий</span><span class="sxs-lookup"><span data-stu-id="89320-102">Object or class does not support the set of events</span></span>

<span data-ttu-id="89320-103">Предпринята попытка использовать `WithEvents` переменную с компонентом, который не может работать в качестве источника событий для указанного набора событий.</span><span class="sxs-lookup"><span data-stu-id="89320-103">You tried to use a `WithEvents` variable with a component that cannot work as an event source for the specified set of events.</span></span> <span data-ttu-id="89320-104">Например, необходимо принять события объекта, а затем создать другой объект, который является `Implements` первым объектом.</span><span class="sxs-lookup"><span data-stu-id="89320-104">For example, you wanted to sink the events of an object, then create another object that `Implements` the first object.</span></span> <span data-ttu-id="89320-105">Хотя можно подумать о том, что вы можете передавать события из реализованного объекта, это не всегда так.</span><span class="sxs-lookup"><span data-stu-id="89320-105">Although you might think you could sink the events from the implemented object, this is not always the case.</span></span> <span data-ttu-id="89320-106">`Implements` реализует интерфейс только для методов и свойств.</span><span class="sxs-lookup"><span data-stu-id="89320-106">`Implements` only implements an interface for methods and properties.</span></span> <span data-ttu-id="89320-107">`WithEvents` не поддерживается для Private `UserControls` , так как сведения о типе, необходимые для вызова, недоступны `ObjectEvent` во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="89320-107">`WithEvents` is not supported for private `UserControls`, because the type info needed to raise the `ObjectEvent` is not available at run time.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="89320-108">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="89320-108">To correct this error</span></span>  
  
1. <span data-ttu-id="89320-109">Вы не можете заменять события для компонента, который не является источником событий.</span><span class="sxs-lookup"><span data-stu-id="89320-109">You cannot sink events for a component that does not source events.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89320-110">См. также</span><span class="sxs-lookup"><span data-stu-id="89320-110">See also</span></span>

- [<span data-ttu-id="89320-111">WithEvents</span><span class="sxs-lookup"><span data-stu-id="89320-111">WithEvents</span></span>](../modifiers/withevents.md)
- [<span data-ttu-id="89320-112">Оператор Implements</span><span class="sxs-lookup"><span data-stu-id="89320-112">Implements Statement</span></span>](../statements/implements-statement.md)
