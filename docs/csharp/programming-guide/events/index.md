---
title: Руководство по программированию на C#. События
description: Сведения о событиях. События позволяют классу или объекту уведомлять другие классы или объекты о возникновении каких-либо ситуаций.
ms.date: 07/20/2015
helpviewer_keywords:
- classes [C#], events
- C# language, events
- events [C#]
ms.assetid: a8e51b22-d294-44fb-9539-0072f06c4cb3
ms.openlocfilehash: f56de15dd2c7b0a10e40a886dbd82a4147a03014
ms.sourcegitcommit: e7acba36517134238065e4d50bb4a1cfe47ebd06
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2020
ms.locfileid: "89466161"
---
# <a name="events-c-programming-guide"></a><span data-ttu-id="ba436-104">События (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="ba436-104">Events (C# Programming Guide)</span></span>
<span data-ttu-id="ba436-105">События позволяют [классу](../../language-reference/keywords/class.md) или объекту уведомлять другие классы или объекты о возникновении каких-либо ситуаций.</span><span class="sxs-lookup"><span data-stu-id="ba436-105">Events enable a [class](../../language-reference/keywords/class.md) or object to notify other classes or objects when something of interest occurs.</span></span> <span data-ttu-id="ba436-106">Класс, отправляющий (или *порождающий*) событие, называется *издателем* , а классы, принимающие (или *обрабатывающие*) событие, называются *подписчиками*.</span><span class="sxs-lookup"><span data-stu-id="ba436-106">The class that sends (or *raises*) the event is called the *publisher* and the classes that receive (or *handle*) the event are called *subscribers*.</span></span>  
  
<span data-ttu-id="ba436-107">В типичном веб-приложении или приложении Windows Forms на C# вы подписываетесь на события, вызываемые элементами управления, такими как кнопки и списки.</span><span class="sxs-lookup"><span data-stu-id="ba436-107">In a typical C# Windows Forms or Web application, you subscribe to events raised by controls such as buttons and list boxes.</span></span> <span data-ttu-id="ba436-108">Вы можете использовать интегрированную среду разработки (IDE) Visual C#, чтобы просмотреть события, публикуемые элементом управления, и выбрать те из них, которые необходимо обрабатывать.</span><span class="sxs-lookup"><span data-stu-id="ba436-108">You can use the Visual C# integrated development environment (IDE) to browse the events that a control publishes and select the ones that you want to handle.</span></span> <span data-ttu-id="ba436-109">IDE позволяет автоматически добавлять пустой метод обработчика событий и код для подписки на событие.</span><span class="sxs-lookup"><span data-stu-id="ba436-109">The IDE provides an easy way to automatically add an empty event handler method and the code to subscribe to the event.</span></span> <span data-ttu-id="ba436-110">Дополнительные сведения см. в разделе [Практическое руководство. Подписка и отмена подписки на события](./how-to-subscribe-to-and-unsubscribe-from-events.md).</span><span class="sxs-lookup"><span data-stu-id="ba436-110">For more information, see [How to subscribe to and unsubscribe from events](./how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>
  
## <a name="events-overview"></a><span data-ttu-id="ba436-111">Общие сведения о событиях</span><span class="sxs-lookup"><span data-stu-id="ba436-111">Events Overview</span></span>  
 <span data-ttu-id="ba436-112">События имеют следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="ba436-112">Events have the following properties:</span></span>  
  
- <span data-ttu-id="ba436-113">Издатель определяет, когда возникает событие; подписчики определяют, какое действие выполняется в ответ на событие.</span><span class="sxs-lookup"><span data-stu-id="ba436-113">The publisher determines when an event is raised; the subscribers determine what action is taken in response to the event.</span></span>  
  
- <span data-ttu-id="ba436-114">У события может быть несколько подписчиков.</span><span class="sxs-lookup"><span data-stu-id="ba436-114">An event can have multiple subscribers.</span></span> <span data-ttu-id="ba436-115">Подписчик может обрабатывать несколько событий от нескольких издателей.</span><span class="sxs-lookup"><span data-stu-id="ba436-115">A subscriber can handle multiple events from multiple publishers.</span></span>  
  
- <span data-ttu-id="ba436-116">События, не имеющие подписчиков, никогда не возникают.</span><span class="sxs-lookup"><span data-stu-id="ba436-116">Events that have no subscribers are never raised.</span></span>  
  
- <span data-ttu-id="ba436-117">Обычно события используются для оповещения о действиях пользователя, например нажатиях кнопок или выборе пунктов меню в графических пользовательских интерфейсах.</span><span class="sxs-lookup"><span data-stu-id="ba436-117">Events are typically used to signal user actions such as button clicks or menu selections in graphical user interfaces.</span></span>  
  
- <span data-ttu-id="ba436-118">Если событие имеет несколько подписчиков, при возникновении события обработчики событий вызываются синхронно.</span><span class="sxs-lookup"><span data-stu-id="ba436-118">When an event has multiple subscribers, the event handlers are invoked synchronously when an event is raised.</span></span> <span data-ttu-id="ba436-119">Сведения об асинхронном вызове событий см. в разделе [Асинхронный вызов синхронных методов](../../../standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md).</span><span class="sxs-lookup"><span data-stu-id="ba436-119">To invoke events asynchronously, see [Calling Synchronous Methods Asynchronously](../../../standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md).</span></span>  
  
- <span data-ttu-id="ba436-120">В библиотеке классов .NET события основываются на делегате <xref:System.EventHandler> и базовом классе <xref:System.EventArgs>.</span><span class="sxs-lookup"><span data-stu-id="ba436-120">In the .NET class library, events are based on the <xref:System.EventHandler> delegate and the <xref:System.EventArgs> base class.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="ba436-121">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="ba436-121">Related Sections</span></span>  
 <span data-ttu-id="ba436-122">Дополнительные сведения можно найти в разделе</span><span class="sxs-lookup"><span data-stu-id="ba436-122">For more information, see:</span></span>  
  
- [<span data-ttu-id="ba436-123">Практическое руководство. Подписка и отмена подписки на события</span><span class="sxs-lookup"><span data-stu-id="ba436-123">How to subscribe to and unsubscribe from events</span></span>](./how-to-subscribe-to-and-unsubscribe-from-events.md)

- [<span data-ttu-id="ba436-124">Практическое руководство. Публикация событий, соответствующих рекомендациям .NET</span><span class="sxs-lookup"><span data-stu-id="ba436-124">How to publish events that conform to .NET Guidelines</span></span>](./how-to-publish-events-that-conform-to-net-framework-guidelines.md)

- [<span data-ttu-id="ba436-125">Практическое руководство. Создание событий базового класса в производных классах</span><span class="sxs-lookup"><span data-stu-id="ba436-125">How to raise base class events in derived classes</span></span>](./how-to-raise-base-class-events-in-derived-classes.md)

- [<span data-ttu-id="ba436-126">Практическое руководство. Реализация событий интерфейса</span><span class="sxs-lookup"><span data-stu-id="ba436-126">How to implement interface events</span></span>](./how-to-implement-interface-events.md)

- [<span data-ttu-id="ba436-127">Практическое руководство. Реализация пользовательских методов доступа к событиям</span><span class="sxs-lookup"><span data-stu-id="ba436-127">How to implement custom event accessors</span></span>](./how-to-implement-custom-event-accessors.md)

## <a name="c-language-specification"></a><span data-ttu-id="ba436-128">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="ba436-128">C# Language Specification</span></span>  

<span data-ttu-id="ba436-129">Дополнительные сведения см. в разделе [События](~/_csharplang/spec/classes.md#events) в [Спецификации языка C#](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="ba436-129">For more information, see [Events](~/_csharplang/spec/classes.md#events) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="ba436-130">Спецификация языка является предписывающим источником информации о синтаксисе и использовании языка C#.</span><span class="sxs-lookup"><span data-stu-id="ba436-130">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="featured-book-chapters"></a><span data-ttu-id="ba436-131">Главы в популярных книгах</span><span class="sxs-lookup"><span data-stu-id="ba436-131">Featured Book Chapters</span></span>  
 <span data-ttu-id="ba436-132">[Делегаты, события и лямбда-выражения](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518994%28v=orm.10%29) в [справочном руководстве по C# 3.0, третье издание. Более 250 решений для программистов на C# 3.0](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518995%28v=orm.10%29)</span><span class="sxs-lookup"><span data-stu-id="ba436-132">[Delegates, Events, and Lambda Expressions](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518994%28v=orm.10%29) in [C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518995%28v=orm.10%29)</span></span>  
  
 <span data-ttu-id="ba436-133">[Делегаты и события](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652490%28v=orm.10%29) в [изучении C# 3.0. Овладение основными понятиями C# 3.0](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652493%28v=orm.10%29)</span><span class="sxs-lookup"><span data-stu-id="ba436-133">[Delegates and Events](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652490%28v=orm.10%29) in [Learning C# 3.0: Master the fundamentals of C# 3.0](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652493%28v=orm.10%29)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba436-134">См. также</span><span class="sxs-lookup"><span data-stu-id="ba436-134">See also</span></span>

- <xref:System.EventHandler>
- [<span data-ttu-id="ba436-135">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="ba436-135">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="ba436-136">Делегаты</span><span class="sxs-lookup"><span data-stu-id="ba436-136">Delegates</span></span>](../delegates/index.md)
- [<span data-ttu-id="ba436-137">Создание обработчиков событий в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ba436-137">Creating Event Handlers in Windows Forms</span></span>](../../../framework/winforms/creating-event-handlers-in-windows-forms.md)
