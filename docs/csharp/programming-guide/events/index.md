---
title: Руководство по программированию на C#. События
description: Сведения о событиях. События позволяют классу или объекту уведомлять другие классы или объекты о возникновении каких-либо ситуаций.
ms.date: 07/20/2015
helpviewer_keywords:
- classes [C#], events
- C# language, events
- events [C#]
ms.assetid: a8e51b22-d294-44fb-9539-0072f06c4cb3
ms.openlocfilehash: 86ded81de4b9191c50b993c08b0e87712ff69020
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90545497"
---
# <a name="events-c-programming-guide"></a><span data-ttu-id="bd7d5-104">События (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="bd7d5-104">Events (C# Programming Guide)</span></span>
<span data-ttu-id="bd7d5-105">События позволяют [классу](../../language-reference/keywords/class.md) или объекту уведомлять другие классы или объекты о возникновении каких-либо ситуаций.</span><span class="sxs-lookup"><span data-stu-id="bd7d5-105">Events enable a [class](../../language-reference/keywords/class.md) or object to notify other classes or objects when something of interest occurs.</span></span> <span data-ttu-id="bd7d5-106">Класс, отправляющий (или *порождающий*) событие, называется *издателем* , а классы, принимающие (или *обрабатывающие*) событие, называются *подписчиками*.</span><span class="sxs-lookup"><span data-stu-id="bd7d5-106">The class that sends (or *raises*) the event is called the *publisher* and the classes that receive (or *handle*) the event are called *subscribers*.</span></span>  
  
<span data-ttu-id="bd7d5-107">В типичном веб-приложении или приложении Windows Forms на C# вы подписываетесь на события, вызываемые элементами управления, такими как кнопки и списки.</span><span class="sxs-lookup"><span data-stu-id="bd7d5-107">In a typical C# Windows Forms or Web application, you subscribe to events raised by controls such as buttons and list boxes.</span></span> <span data-ttu-id="bd7d5-108">Вы можете использовать интегрированную среду разработки (IDE) Visual C#, чтобы просмотреть события, публикуемые элементом управления, и выбрать те из них, которые необходимо обрабатывать.</span><span class="sxs-lookup"><span data-stu-id="bd7d5-108">You can use the Visual C# integrated development environment (IDE) to browse the events that a control publishes and select the ones that you want to handle.</span></span> <span data-ttu-id="bd7d5-109">IDE позволяет автоматически добавлять пустой метод обработчика событий и код для подписки на событие.</span><span class="sxs-lookup"><span data-stu-id="bd7d5-109">The IDE provides an easy way to automatically add an empty event handler method and the code to subscribe to the event.</span></span> <span data-ttu-id="bd7d5-110">Дополнительные сведения см. в разделе [Практическое руководство. Подписка и отмена подписки на события](./how-to-subscribe-to-and-unsubscribe-from-events.md).</span><span class="sxs-lookup"><span data-stu-id="bd7d5-110">For more information, see [How to subscribe to and unsubscribe from events](./how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>
  
## <a name="events-overview"></a><span data-ttu-id="bd7d5-111">Общие сведения о событиях</span><span class="sxs-lookup"><span data-stu-id="bd7d5-111">Events Overview</span></span>  
 <span data-ttu-id="bd7d5-112">События имеют следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="bd7d5-112">Events have the following properties:</span></span>  
  
- <span data-ttu-id="bd7d5-113">Издатель определяет, когда возникает событие; подписчики определяют, какое действие выполняется в ответ на событие.</span><span class="sxs-lookup"><span data-stu-id="bd7d5-113">The publisher determines when an event is raised; the subscribers determine what action is taken in response to the event.</span></span>  
  
- <span data-ttu-id="bd7d5-114">У события может быть несколько подписчиков.</span><span class="sxs-lookup"><span data-stu-id="bd7d5-114">An event can have multiple subscribers.</span></span> <span data-ttu-id="bd7d5-115">Подписчик может обрабатывать несколько событий от нескольких издателей.</span><span class="sxs-lookup"><span data-stu-id="bd7d5-115">A subscriber can handle multiple events from multiple publishers.</span></span>  
  
- <span data-ttu-id="bd7d5-116">События, не имеющие подписчиков, никогда не возникают.</span><span class="sxs-lookup"><span data-stu-id="bd7d5-116">Events that have no subscribers are never raised.</span></span>  
  
- <span data-ttu-id="bd7d5-117">Обычно события используются для оповещения о действиях пользователя, например нажатиях кнопок или выборе пунктов меню в графических пользовательских интерфейсах.</span><span class="sxs-lookup"><span data-stu-id="bd7d5-117">Events are typically used to signal user actions such as button clicks or menu selections in graphical user interfaces.</span></span>  
  
- <span data-ttu-id="bd7d5-118">Если событие имеет несколько подписчиков, при возникновении события обработчики событий вызываются синхронно.</span><span class="sxs-lookup"><span data-stu-id="bd7d5-118">When an event has multiple subscribers, the event handlers are invoked synchronously when an event is raised.</span></span> <span data-ttu-id="bd7d5-119">Сведения об асинхронном вызове событий см. в разделе [Асинхронный вызов синхронных методов](../../../standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md).</span><span class="sxs-lookup"><span data-stu-id="bd7d5-119">To invoke events asynchronously, see [Calling Synchronous Methods Asynchronously](../../../standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md).</span></span>  
  
- <span data-ttu-id="bd7d5-120">В библиотеке классов .NET события основываются на делегате <xref:System.EventHandler> и базовом классе <xref:System.EventArgs>.</span><span class="sxs-lookup"><span data-stu-id="bd7d5-120">In the .NET class library, events are based on the <xref:System.EventHandler> delegate and the <xref:System.EventArgs> base class.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="bd7d5-121">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="bd7d5-121">Related Sections</span></span>  
 <span data-ttu-id="bd7d5-122">Дополнительные сведения можно найти в разделе</span><span class="sxs-lookup"><span data-stu-id="bd7d5-122">For more information, see:</span></span>  
  
- [<span data-ttu-id="bd7d5-123">Практическое руководство. Подписка и отмена подписки на события</span><span class="sxs-lookup"><span data-stu-id="bd7d5-123">How to subscribe to and unsubscribe from events</span></span>](./how-to-subscribe-to-and-unsubscribe-from-events.md)

- [<span data-ttu-id="bd7d5-124">Практическое руководство. Публикация событий, соответствующих рекомендациям .NET</span><span class="sxs-lookup"><span data-stu-id="bd7d5-124">How to publish events that conform to .NET Guidelines</span></span>](./how-to-publish-events-that-conform-to-net-framework-guidelines.md)

- [<span data-ttu-id="bd7d5-125">Практическое руководство. Создание событий базового класса в производных классах</span><span class="sxs-lookup"><span data-stu-id="bd7d5-125">How to raise base class events in derived classes</span></span>](./how-to-raise-base-class-events-in-derived-classes.md)

- [<span data-ttu-id="bd7d5-126">Практическое руководство. Реализация событий интерфейса</span><span class="sxs-lookup"><span data-stu-id="bd7d5-126">How to implement interface events</span></span>](./how-to-implement-interface-events.md)

- [<span data-ttu-id="bd7d5-127">Практическое руководство. Реализация пользовательских методов доступа к событиям</span><span class="sxs-lookup"><span data-stu-id="bd7d5-127">How to implement custom event accessors</span></span>](./how-to-implement-custom-event-accessors.md)

## <a name="c-language-specification"></a><span data-ttu-id="bd7d5-128">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="bd7d5-128">C# Language Specification</span></span>  

<span data-ttu-id="bd7d5-129">Дополнительные сведения см. в разделе [События](~/_csharplang/spec/classes.md#events) в [Спецификации языка C#](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="bd7d5-129">For more information, see [Events](~/_csharplang/spec/classes.md#events) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="bd7d5-130">Спецификация языка является предписывающим источником информации о синтаксисе и использовании языка C#.</span><span class="sxs-lookup"><span data-stu-id="bd7d5-130">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="featured-book-chapters"></a><span data-ttu-id="bd7d5-131">Главы в популярных книгах</span><span class="sxs-lookup"><span data-stu-id="bd7d5-131">Featured Book Chapters</span></span>  
 <span data-ttu-id="bd7d5-132">[Делегаты, события и лямбда-выражения](/previous-versions/visualstudio/visual-studio-2008/ff518994(v=orm.10)) в [справочном руководстве по C# 3.0, третье издание. Более 250 решений для программистов на C# 3.0](/previous-versions/visualstudio/visual-studio-2008/ff518995(v=orm.10))</span><span class="sxs-lookup"><span data-stu-id="bd7d5-132">[Delegates, Events, and Lambda Expressions](/previous-versions/visualstudio/visual-studio-2008/ff518994(v=orm.10)) in [C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers](/previous-versions/visualstudio/visual-studio-2008/ff518995(v=orm.10))</span></span>  
  
 <span data-ttu-id="bd7d5-133">[Делегаты и события](/previous-versions/visualstudio/visual-studio-2008/ff652490(v=orm.10)) в [изучении C# 3.0. Овладение основными понятиями C# 3.0](/previous-versions/visualstudio/visual-studio-2008/ff652493(v=orm.10))</span><span class="sxs-lookup"><span data-stu-id="bd7d5-133">[Delegates and Events](/previous-versions/visualstudio/visual-studio-2008/ff652490(v=orm.10)) in [Learning C# 3.0: Master the fundamentals of C# 3.0](/previous-versions/visualstudio/visual-studio-2008/ff652493(v=orm.10))</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd7d5-134">См. также</span><span class="sxs-lookup"><span data-stu-id="bd7d5-134">See also</span></span>

- <xref:System.EventHandler>
- [<span data-ttu-id="bd7d5-135">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="bd7d5-135">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="bd7d5-136">Делегаты</span><span class="sxs-lookup"><span data-stu-id="bd7d5-136">Delegates</span></span>](../delegates/index.md)
- [<span data-ttu-id="bd7d5-137">Создание обработчиков событий в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bd7d5-137">Creating Event Handlers in Windows Forms</span></span>](/dotnet/desktop/winforms/creating-event-handlers-in-windows-forms)
