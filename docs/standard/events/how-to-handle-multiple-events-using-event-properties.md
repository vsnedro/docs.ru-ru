---
title: Практическое руководство. Обработка множества событий с помощью их свойств
description: Сведения о том, как обрабатывать множество событий с помощью их свойств. Определение коллекций делегатов, ключей событий и свойств событий. Реализация методов доступа для добавления и удаления.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- event properties [.NET]
- multiple events [.NET]
- event handling [.NET], with multiple events
- events [.NET], multiple
ms.assetid: 30047cba-e2fd-41c6-b9ca-2ad7a49003db
ms.openlocfilehash: c62073e26ff0831bb582c9e64c16b7ec7c05b26e
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/18/2020
ms.locfileid: "94828379"
---
# <a name="how-to-handle-multiple-events-using-event-properties"></a><span data-ttu-id="af247-105">Практическое руководство. Обработка нескольких событий с помощью их свойств</span><span class="sxs-lookup"><span data-stu-id="af247-105">How to: Handle Multiple Events Using Event Properties</span></span>
<span data-ttu-id="af247-106">Чтобы использовать свойства событий, следует определить свойства событий в классе, который вызывает события, а затем задать делегаты для свойств событий в классах, обрабатывающих события.</span><span class="sxs-lookup"><span data-stu-id="af247-106">To use event properties, you define the event properties in the class that raises the events, and then set the delegates for the event properties in classes that handle the events.</span></span> <span data-ttu-id="af247-107">Для реализации нескольких свойств событий в классе класс должен хранить и обслуживать внутри себя делегата, определенного для каждого события.</span><span class="sxs-lookup"><span data-stu-id="af247-107">To implement multiple event properties in a class, the class must internally store and maintain the delegate defined for each event.</span></span> <span data-ttu-id="af247-108">Типичная стратегия заключается в реализации коллекции делегатов, которая индексируется по ключу события.</span><span class="sxs-lookup"><span data-stu-id="af247-108">A typical approach is to implement a delegate collection that is indexed by an event key.</span></span>  
  
 <span data-ttu-id="af247-109">Для сохранения делегатов для каждого события можно воспользоваться классом <xref:System.ComponentModel.EventHandlerList> или реализовать собственную коллекцию.</span><span class="sxs-lookup"><span data-stu-id="af247-109">To store the delegates for each event, you can use the <xref:System.ComponentModel.EventHandlerList> class, or implement your own collection.</span></span> <span data-ttu-id="af247-110">Класс коллекции должен предоставить методы для установки, извлечения делегата обработчика событий и доступа к нему по ключу события.</span><span class="sxs-lookup"><span data-stu-id="af247-110">The collection class must provide methods for setting, accessing, and retrieving the event handler delegate based on the event key.</span></span> <span data-ttu-id="af247-111">Например, можно использовать класс <xref:System.Collections.Hashtable> или извлечь пользовательский класс от класса <xref:System.Collections.DictionaryBase>.</span><span class="sxs-lookup"><span data-stu-id="af247-111">For example, you could use a <xref:System.Collections.Hashtable> class, or derive a custom class from the <xref:System.Collections.DictionaryBase> class.</span></span> <span data-ttu-id="af247-112">Сведения о реализации коллекции делегатов не обязательно предоставлять за пределами класса.</span><span class="sxs-lookup"><span data-stu-id="af247-112">The implementation details of the delegate collection do not need to be exposed outside your class.</span></span>  
  
 <span data-ttu-id="af247-113">Каждое свойство события внутри класса определяет метод доступа add и remove.</span><span class="sxs-lookup"><span data-stu-id="af247-113">Each event property within the class defines an add accessor method and a remove accessor method.</span></span> <span data-ttu-id="af247-114">Метод доступа add для свойства события добавляет входной экземпляр делегата в коллекцию.</span><span class="sxs-lookup"><span data-stu-id="af247-114">The add accessor for an event property adds the input delegate instance to the delegate collection.</span></span> <span data-ttu-id="af247-115">Метод доступа remove для свойства события удаляет входной экземпляр делегата из коллекции.</span><span class="sxs-lookup"><span data-stu-id="af247-115">The remove accessor for an event property removes the input delegate instance from the delegate collection.</span></span> <span data-ttu-id="af247-116">Методы доступа к свойствам событий используют предопределенный ключ для свойства события, чтобы добавлять экземпляры в коллекцию делегатов и удалять их из нее.</span><span class="sxs-lookup"><span data-stu-id="af247-116">The event property accessors use the predefined key for the event property to add and remove instances from the delegate collection.</span></span>  
  
### <a name="to-handle-multiple-events-using-event-properties"></a><span data-ttu-id="af247-117">Обработка нескольких событий с помощью их свойств</span><span class="sxs-lookup"><span data-stu-id="af247-117">To handle multiple events using event properties</span></span>  
  
1. <span data-ttu-id="af247-118">Определите коллекцию делегатов внутри класса, который вызывает события.</span><span class="sxs-lookup"><span data-stu-id="af247-118">Define a delegate collection within the class that raises the events.</span></span>  
  
2. <span data-ttu-id="af247-119">Определите ключ для каждого события.</span><span class="sxs-lookup"><span data-stu-id="af247-119">Define a key for each event.</span></span>  
  
3. <span data-ttu-id="af247-120">Определите свойства событий в классе, который вызывает события.</span><span class="sxs-lookup"><span data-stu-id="af247-120">Define the event properties in the class that raises the events.</span></span>  
  
4. <span data-ttu-id="af247-121">Используйте коллекцию делегатов для реализации методов доступа add и remove для свойств событий.</span><span class="sxs-lookup"><span data-stu-id="af247-121">Use the delegate collection to implement the add and remove accessor methods for the event properties.</span></span>  
  
5. <span data-ttu-id="af247-122">Используйте открытые свойства событий делегатов обработчика событий добавления и удаления в классах, обрабатывающих эти события.</span><span class="sxs-lookup"><span data-stu-id="af247-122">Use the public event properties to add and remove event handler delegates in the classes that handle the events.</span></span>  
  
## <a name="example"></a><span data-ttu-id="af247-123">Пример</span><span class="sxs-lookup"><span data-stu-id="af247-123">Example</span></span>  
 <span data-ttu-id="af247-124">В следующем примере C# реализуются свойства событий `MouseDown` и `MouseUp` с использованием объекта <xref:System.ComponentModel.EventHandlerList> для хранения делегата каждого события.</span><span class="sxs-lookup"><span data-stu-id="af247-124">The following C# example implements the event properties `MouseDown` and `MouseUp`, using an <xref:System.ComponentModel.EventHandlerList> to store each event's delegate.</span></span> <span data-ttu-id="af247-125">Ключевые слова для конструкции свойств событий выделены жирным шрифтом.</span><span class="sxs-lookup"><span data-stu-id="af247-125">The keywords of the event property constructs are in bold type.</span></span>  
  
 [!code-cpp[Conceptual.Events.Other#31](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.events.other/cpp/example3.cpp#31)]
 [!code-csharp[Conceptual.Events.Other#31](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.events.other/cs/example3.cs#31)]
 [!code-vb[Conceptual.Events.Other#31](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.events.other/vb/example3.vb#31)]  
  
## <a name="see-also"></a><span data-ttu-id="af247-126">См. также</span><span class="sxs-lookup"><span data-stu-id="af247-126">See also</span></span>

- <xref:System.ComponentModel.EventHandlerList?displayProperty=nameWithType>
- [<span data-ttu-id="af247-127">События</span><span class="sxs-lookup"><span data-stu-id="af247-127">Events</span></span>](index.md)
- <xref:System.Web.UI.Control.Events%2A?displayProperty=nameWithType>
- [<span data-ttu-id="af247-128">Практическое руководство. Объявление пользовательских событий для экономии памяти</span><span class="sxs-lookup"><span data-stu-id="af247-128">How to: Declare Custom Events To Conserve Memory</span></span>](../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-conserve-memory.md)
