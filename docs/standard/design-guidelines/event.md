---
title: Разработка событий
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- pre-events
- events [.NET Framework], design guidelines
- member design guidelines, events
- event handlers [.NET Framework], event design guidelines
- post-events
- signatures, event handling
ms.assetid: 67b3c6e2-6a8f-480d-a78f-ebeeaca1b95a
ms.openlocfilehash: 852c99b1a41691911f7ae82d3b8104526811757d
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "84289828"
---
# <a name="event-design"></a><span data-ttu-id="0f9d3-102">Разработка событий</span><span class="sxs-lookup"><span data-stu-id="0f9d3-102">Event Design</span></span>
<span data-ttu-id="0f9d3-103">События — это наиболее часто используемая форма обратных вызовов (конструкций, позволяющая платформе вызывать пользовательский код).</span><span class="sxs-lookup"><span data-stu-id="0f9d3-103">Events are the most commonly used form of callbacks (constructs that allow the framework to call into user code).</span></span> <span data-ttu-id="0f9d3-104">К другим механизмам обратного вызова относятся участники, принимающие делегаты, виртуальные элементы и подключаемые модули на основе интерфейсов. данные из исследований удобства использования указывают на то, что большинство разработчиков более удобно использовать при использовании событий, чем другие механизмы обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="0f9d3-104">Other callback mechanisms include members taking delegates, virtual members, and interface-based plug-ins. Data from usability studies indicate that the majority of developers are more comfortable using events than they are using the other callback mechanisms.</span></span> <span data-ttu-id="0f9d3-105">События хорошо интегрируются с Visual Studio и многими языками.</span><span class="sxs-lookup"><span data-stu-id="0f9d3-105">Events are nicely integrated with Visual Studio and many languages.</span></span>

 <span data-ttu-id="0f9d3-106">Важно отметить, что существует две группы событий: события, вызванные до изменения состояния системы, называемые событиями pre-Events, и события, возникающие после изменения состояния, называемые событиями после.</span><span class="sxs-lookup"><span data-stu-id="0f9d3-106">It is important to note that there are two groups of events: events raised before a state of the system changes, called pre-events, and events raised after a state changes, called post-events.</span></span> <span data-ttu-id="0f9d3-107">Примером предварительного события может быть `Form.Closing` , что происходит перед закрытием формы.</span><span class="sxs-lookup"><span data-stu-id="0f9d3-107">An example of a pre-event would be `Form.Closing`, which is raised before a form is closed.</span></span> <span data-ttu-id="0f9d3-108">Примером поступающего события может быть `Form.Closed` , что возникает после закрытия формы.</span><span class="sxs-lookup"><span data-stu-id="0f9d3-108">An example of a post-event would be `Form.Closed`, which is raised after a form is closed.</span></span>

 <span data-ttu-id="0f9d3-109">✔️ использовать термин «raise» для событий, а не «пожар» или «Trigger».</span><span class="sxs-lookup"><span data-stu-id="0f9d3-109">✔️ DO use the term "raise" for events rather than "fire" or "trigger."</span></span>

 <span data-ttu-id="0f9d3-110">✔️ использовать <xref:System.EventHandler%601?displayProperty=nameWithType> вместо ручного создания новых делегатов для использования в качестве обработчиков событий.</span><span class="sxs-lookup"><span data-stu-id="0f9d3-110">✔️ DO use <xref:System.EventHandler%601?displayProperty=nameWithType> instead of manually creating new delegates to be used as event handlers.</span></span>

 <span data-ttu-id="0f9d3-111">✔️ Рассмотрите возможность использования подкласса в <xref:System.EventArgs> качестве аргумента события, если только вы не уверены, что событие никогда не будет передавать какие-либо данные в метод обработки событий. в этом случае можно использовать `EventArgs` тип напрямую.</span><span class="sxs-lookup"><span data-stu-id="0f9d3-111">✔️ CONSIDER using a subclass of <xref:System.EventArgs> as the event argument, unless you are absolutely sure the event will never need to carry any data to the event handling method, in which case you can use the `EventArgs` type directly.</span></span>

 <span data-ttu-id="0f9d3-112">Если вы подаете API `EventArgs` напрямую, вы никогда не сможете добавлять данные, которые будут перенесены с событием без нарушения совместимости.</span><span class="sxs-lookup"><span data-stu-id="0f9d3-112">If you ship an API using `EventArgs` directly, you will never be able to add any data to be carried with the event without breaking compatibility.</span></span> <span data-ttu-id="0f9d3-113">Если вы используете подкласс, даже если изначально он полностью пуст, вы сможете добавлять свойства в подкласс при необходимости.</span><span class="sxs-lookup"><span data-stu-id="0f9d3-113">If you use a subclass, even if initially completely empty, you will be able to add properties to the subclass when needed.</span></span>

 <span data-ttu-id="0f9d3-114">для вызова каждого события ✔️ использовать защищенный виртуальный метод.</span><span class="sxs-lookup"><span data-stu-id="0f9d3-114">✔️ DO use a protected virtual method to raise each event.</span></span> <span data-ttu-id="0f9d3-115">Это применимо только к нестатическим событиям в незапечатанных классах, а не к структурам, запечатанным классам или статическим событиям.</span><span class="sxs-lookup"><span data-stu-id="0f9d3-115">This is only applicable to nonstatic events on unsealed classes, not to structs, sealed classes, or static events.</span></span>

 <span data-ttu-id="0f9d3-116">Цель метода — предоставить способ для производного класса, обрабатывающий событие с помощью переопределения.</span><span class="sxs-lookup"><span data-stu-id="0f9d3-116">The purpose of the method is to provide a way for a derived class to handle the event using an override.</span></span> <span data-ttu-id="0f9d3-117">Переопределение является более гибким, быстрым и естественным способом управления событиями базового класса в производных классах.</span><span class="sxs-lookup"><span data-stu-id="0f9d3-117">Overriding is a more flexible, faster, and more natural way to handle base class events in derived classes.</span></span> <span data-ttu-id="0f9d3-118">По соглашению имя метода должно начинаться с "on" и состоять из имени события.</span><span class="sxs-lookup"><span data-stu-id="0f9d3-118">By convention, the name of the method should start with "On" and be followed with the name of the event.</span></span>

 <span data-ttu-id="0f9d3-119">Производный класс может не вызывать базовую реализацию метода в его переопределении.</span><span class="sxs-lookup"><span data-stu-id="0f9d3-119">The derived class can choose not to call the base implementation of the method in its override.</span></span> <span data-ttu-id="0f9d3-120">Будьте готовы к этому, не включая обработку в методе, который требуется для правильной работы базового класса.</span><span class="sxs-lookup"><span data-stu-id="0f9d3-120">Be prepared for this by not including any processing in the method that is required for the base class to work correctly.</span></span>

 <span data-ttu-id="0f9d3-121">✔️ принимать один параметр для защищенного метода, который вызывает событие.</span><span class="sxs-lookup"><span data-stu-id="0f9d3-121">✔️ DO take one parameter to the protected method that raises an event.</span></span>

 <span data-ttu-id="0f9d3-122">Параметр должен иметь имя `e` и быть типизированным в качестве класса аргумента события.</span><span class="sxs-lookup"><span data-stu-id="0f9d3-122">The parameter should be named `e` and should be typed as the event argument class.</span></span>

 <span data-ttu-id="0f9d3-123">❌НЕ передавайте значение NULL в качестве отправителя при вызове нестатического события.</span><span class="sxs-lookup"><span data-stu-id="0f9d3-123">❌ DO NOT pass null as the sender when raising a nonstatic event.</span></span>

 <span data-ttu-id="0f9d3-124">✔️ передать NULL в качестве отправителя при вызове статического события.</span><span class="sxs-lookup"><span data-stu-id="0f9d3-124">✔️ DO pass null as the sender when raising a static event.</span></span>

 <span data-ttu-id="0f9d3-125">❌НЕ передавайте значение NULL в качестве параметра данных события при вызове события.</span><span class="sxs-lookup"><span data-stu-id="0f9d3-125">❌ DO NOT pass null as the event data parameter when raising an event.</span></span>

 <span data-ttu-id="0f9d3-126">`EventArgs.Empty`Если вы не хотите передавать какие бы то ни было данные в метод обработки событий, необходимо передать значение.</span><span class="sxs-lookup"><span data-stu-id="0f9d3-126">You should pass `EventArgs.Empty` if you don’t want to pass any data to the event handling method.</span></span> <span data-ttu-id="0f9d3-127">Разработчики предполагают, что этот параметр не должен иметь значение null.</span><span class="sxs-lookup"><span data-stu-id="0f9d3-127">Developers expect this parameter not to be null.</span></span>

 <span data-ttu-id="0f9d3-128">✔️ Рассмотрите возможность вызова событий, которые может отменить конечный пользователь.</span><span class="sxs-lookup"><span data-stu-id="0f9d3-128">✔️ CONSIDER raising events that the end user can cancel.</span></span> <span data-ttu-id="0f9d3-129">Это относится только к предварительным событиям.</span><span class="sxs-lookup"><span data-stu-id="0f9d3-129">This only applies to pre-events.</span></span>

 <span data-ttu-id="0f9d3-130">Используйте <xref:System.ComponentModel.CancelEventArgs?displayProperty=nameWithType> или его подкласс в качестве аргумента события, чтобы разрешить конечному пользователю отменять события.</span><span class="sxs-lookup"><span data-stu-id="0f9d3-130">Use <xref:System.ComponentModel.CancelEventArgs?displayProperty=nameWithType> or its subclass as the event argument to allow the end user to cancel events.</span></span>

### <a name="custom-event-handler-design"></a><span data-ttu-id="0f9d3-131">Разработка пользовательского обработчика событий</span><span class="sxs-lookup"><span data-stu-id="0f9d3-131">Custom Event Handler Design</span></span>
 <span data-ttu-id="0f9d3-132">Существуют случаи, в которых `EventHandler<T>` нельзя использовать, например, если платформе требуется работать с более ранними версиями среды CLR, которые не поддерживали универсальные шаблоны.</span><span class="sxs-lookup"><span data-stu-id="0f9d3-132">There are cases in which `EventHandler<T>` cannot be used, such as when the framework needs to work with earlier versions of the CLR, which did not support Generics.</span></span> <span data-ttu-id="0f9d3-133">В таких случаях может потребоваться разработать и разработать пользовательский делегат обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="0f9d3-133">In such cases, you might need to design and develop a custom event handler delegate.</span></span>

 <span data-ttu-id="0f9d3-134">✔️ использовать тип возвращаемого значения void для обработчиков событий.</span><span class="sxs-lookup"><span data-stu-id="0f9d3-134">✔️ DO use a return type of void for event handlers.</span></span>

 <span data-ttu-id="0f9d3-135">Обработчик событий может вызывать несколько методов обработки событий, возможно, для нескольких объектов.</span><span class="sxs-lookup"><span data-stu-id="0f9d3-135">An event handler can invoke multiple event handling methods, possibly on multiple objects.</span></span> <span data-ttu-id="0f9d3-136">Если методы обработки событий позволяли возвращать значение, то для каждого вызова события было бы несколько возвращаемых значений.</span><span class="sxs-lookup"><span data-stu-id="0f9d3-136">If event handling methods were allowed to return a value, there would be multiple return values for each event invocation.</span></span>

 <span data-ttu-id="0f9d3-137">✔️ использовать в `object` качестве типа первого параметра обработчика событий и вызывать его `sender` .</span><span class="sxs-lookup"><span data-stu-id="0f9d3-137">✔️ DO use `object` as the type of the first parameter of the event handler, and call it `sender`.</span></span>

 <span data-ttu-id="0f9d3-138">✔️ использовать <xref:System.EventArgs?displayProperty=nameWithType> или его подкласс в качестве типа второго параметра обработчика событий и вызвать его `e` .</span><span class="sxs-lookup"><span data-stu-id="0f9d3-138">✔️ DO use <xref:System.EventArgs?displayProperty=nameWithType> or its subclass as the type of the second parameter of the event handler, and call it `e`.</span></span>

 <span data-ttu-id="0f9d3-139">❌В обработчиках событий не более двух параметров.</span><span class="sxs-lookup"><span data-stu-id="0f9d3-139">❌ DO NOT have more than two parameters on event handlers.</span></span>

 <span data-ttu-id="0f9d3-140">*Части © 2005, 2009 Корпорация Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="0f9d3-140">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="0f9d3-141">*Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="0f9d3-141">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="0f9d3-142">См. также</span><span class="sxs-lookup"><span data-stu-id="0f9d3-142">See also</span></span>

- [<span data-ttu-id="0f9d3-143">Рекомендации по проектированию членов</span><span class="sxs-lookup"><span data-stu-id="0f9d3-143">Member Design Guidelines</span></span>](member.md)
- [<span data-ttu-id="0f9d3-144">Рекомендации по проектированию платформы</span><span class="sxs-lookup"><span data-stu-id="0f9d3-144">Framework Design Guidelines</span></span>](index.md)
