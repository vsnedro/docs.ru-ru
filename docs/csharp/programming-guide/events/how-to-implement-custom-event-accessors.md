---
title: Руководство по программированию на C#. Реализация пользовательских методов доступа к событиям
description: Сведения о реализации пользовательских методов доступа к событиям. Изучите пример кода и ознакомьтесь с дополнительными ресурсами.
ms.date: 07/20/2015
helpviewer_keywords:
- accessors [C#], event accessors
- add accessor [C#]
- events [C#], add accessor
- events [C#], remove accessor
- remove accessor [C#]
ms.assetid: bf903abf-03a4-4f7b-ab6b-b7e59bc2ee1e
ms.openlocfilehash: 41c9bd255bf66cd914982b6044c4acaef66b8fcf
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91167565"
---
# <a name="how-to-implement-custom-event-accessors-c-programming-guide"></a><span data-ttu-id="35645-104">Руководство по программированию на C#. Реализация пользовательских методов доступа к событиям</span><span class="sxs-lookup"><span data-stu-id="35645-104">How to implement custom event accessors (C# Programming Guide)</span></span>

<span data-ttu-id="35645-105">Событие представляет собой особый вид многоадресного делегата, который можно вызвать только из класса, где он объявлен.</span><span class="sxs-lookup"><span data-stu-id="35645-105">An event is a special kind of multicast delegate that can only be invoked from within the class that  it is declared in.</span></span> <span data-ttu-id="35645-106">В клиентском коде создается подписка на событие. Для этого предоставляется ссылка на метод, который должен вызываться при возникновении этого события.</span><span class="sxs-lookup"><span data-stu-id="35645-106">Client code subscribes to the event by providing a reference to a method that should be invoked when the event is fired.</span></span> <span data-ttu-id="35645-107">Эти методы добавляются в список вызова делегата с помощью методов доступа к событиям, которые схожи с методами доступа к свойствам и отличаются только именами (`add` и `remove`).</span><span class="sxs-lookup"><span data-stu-id="35645-107">These methods are added to the delegate's invocation list through event accessors, which resemble property accessors, except that event accessors are named `add` and `remove`.</span></span> <span data-ttu-id="35645-108">В большинстве случаев реализовывать настраиваемые методы доступа к событиям не требуется.</span><span class="sxs-lookup"><span data-stu-id="35645-108">In most cases, you do not have to supply custom event accessors.</span></span> <span data-ttu-id="35645-109">Если в коде отсутствуют настраиваемые методы доступа к событиям, компилятор добавляет их автоматически.</span><span class="sxs-lookup"><span data-stu-id="35645-109">When no custom event accessors are supplied in your code, the compiler will add them automatically.</span></span> <span data-ttu-id="35645-110">Тем не менее в некоторых случаях требуется реализовать настраиваемое поведение.</span><span class="sxs-lookup"><span data-stu-id="35645-110">However, in some cases you may have to provide custom behavior.</span></span> <span data-ttu-id="35645-111">Один из таких сценариев показан в руководстве по [реализации событий интерфейса](./how-to-implement-interface-events.md).</span><span class="sxs-lookup"><span data-stu-id="35645-111">One such case is shown in the topic [How to implement interface events](./how-to-implement-interface-events.md).</span></span>
  
## <a name="example"></a><span data-ttu-id="35645-112">Пример</span><span class="sxs-lookup"><span data-stu-id="35645-112">Example</span></span>  

 <span data-ttu-id="35645-113">В следующем примере показано, как реализовать настраиваемые методы доступа add и remove для события.</span><span class="sxs-lookup"><span data-stu-id="35645-113">The following example shows how to implement custom add and remove event accessors.</span></span> <span data-ttu-id="35645-114">При необходимости вы можете заменять любой код в методах доступа, однако мы рекомендуем заблокировать событие, прежде чем добавлять или удалять новый метод обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="35645-114">Although you can substitute any code inside the accessors, we recommend that you lock the event before you add or remove a new event handler method.</span></span>  
  
[!code-csharp[IDrawingObject.OnDraw](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEvents/CS/Events.cs#IDrawingObjectOnDraw)]  
  
## <a name="see-also"></a><span data-ttu-id="35645-115">См. также</span><span class="sxs-lookup"><span data-stu-id="35645-115">See also</span></span>

- [<span data-ttu-id="35645-116">События</span><span class="sxs-lookup"><span data-stu-id="35645-116">Events</span></span>](./index.md)
- [<span data-ttu-id="35645-117">event</span><span class="sxs-lookup"><span data-stu-id="35645-117">event</span></span>](../../language-reference/keywords/event.md)
