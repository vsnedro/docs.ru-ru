---
title: Шаблоны слабых событий
description: Сведения о шаблоне слабых событий Windows Presentation Foundation, который решает выдачу неуничтоженных обработчиков, избегая утечки памяти.
ms.date: 03/30/2017
helpviewer_keywords:
- weak event pattern implementation [WPF]
- event handlers [WPF], weak event pattern
- IWeakEventListener interface [WPF]
ms.assetid: e7c62920-4812-4811-94d8-050a65c856f6
ms.openlocfilehash: 75c6888c8ac20c41d13e3787005377c75248c5d9
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2020
ms.locfileid: "87168260"
---
# <a name="weak-event-patterns"></a><span data-ttu-id="73ca8-103">Шаблоны слабых событий</span><span class="sxs-lookup"><span data-stu-id="73ca8-103">Weak Event Patterns</span></span>
<span data-ttu-id="73ca8-104">В приложениях возможно, что обработчики, присоединенные к источникам событий, не будут уничтожены в координации с объектом прослушивателя, который присоединил обработчик к источнику.</span><span class="sxs-lookup"><span data-stu-id="73ca8-104">In applications, it is possible that handlers that are attached to event sources will not be destroyed in coordination with the listener object that attached the handler to the source.</span></span> <span data-ttu-id="73ca8-105">Такая ситуация может привести к утечке памяти.</span><span class="sxs-lookup"><span data-stu-id="73ca8-105">This situation can lead to memory leaks.</span></span> [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]<span data-ttu-id="73ca8-106">представляет шаблон проектирования, который можно использовать для решения этой проблемы, предоставляя выделенный класс Manager для конкретных событий и реализуя интерфейс для прослушивателей этого события.</span><span class="sxs-lookup"><span data-stu-id="73ca8-106">introduces a design pattern that can be used to address this issue, by providing a dedicated manager class for particular events and implementing an interface on listeners for that event.</span></span> <span data-ttu-id="73ca8-107">Этот шаблон разработки известен как *шаблон слабых событий*.</span><span class="sxs-lookup"><span data-stu-id="73ca8-107">This design pattern is known as the *weak event pattern*.</span></span>  
  
## <a name="why-implement-the-weak-event-pattern"></a><span data-ttu-id="73ca8-108">Зачем реализовывать шаблон слабых событий?</span><span class="sxs-lookup"><span data-stu-id="73ca8-108">Why Implement the Weak Event Pattern?</span></span>  
 <span data-ttu-id="73ca8-109">Прослушивание событий может привести к утечке памяти.</span><span class="sxs-lookup"><span data-stu-id="73ca8-109">Listening for events can lead to memory leaks.</span></span> <span data-ttu-id="73ca8-110">Типичным приемом для прослушивания события является использование синтаксиса, зависящего от языка, который прикрепляет обработчик к событию в источнике.</span><span class="sxs-lookup"><span data-stu-id="73ca8-110">The typical technique for listening to an event is to use the language-specific syntax that attaches a handler to an event on a source.</span></span> <span data-ttu-id="73ca8-111">Например, в C# этот синтаксис: `source.SomeEvent += new SomeEventHandler(MyEventHandler)` .</span><span class="sxs-lookup"><span data-stu-id="73ca8-111">For example, in C#, that syntax is: `source.SomeEvent += new SomeEventHandler(MyEventHandler)`.</span></span>  
  
 <span data-ttu-id="73ca8-112">Этот метод создает строгую ссылку из источника событий в прослушиватель событий.</span><span class="sxs-lookup"><span data-stu-id="73ca8-112">This technique creates a strong reference from the event source to the event listener.</span></span> <span data-ttu-id="73ca8-113">Обычно присоединение обработчика событий для прослушивателя приводит к тому, что прослушиватель имеет время существования объекта, на которое влияет время существования объекта источника (если только обработчик событий не удаляется явным образом).</span><span class="sxs-lookup"><span data-stu-id="73ca8-113">Ordinarily, attaching an event handler for a listener causes the listener to have an object lifetime that is influenced by the object lifetime of the source (unless the event handler is explicitly removed).</span></span> <span data-ttu-id="73ca8-114">Но в некоторых случаях может потребоваться, чтобы время существования объекта прослушивателя управлялось другими факторами, например, если он принадлежит визуальному дереву приложения, а не времени существования источника.</span><span class="sxs-lookup"><span data-stu-id="73ca8-114">But in certain circumstances, you might want the object lifetime of the listener to be controlled by other factors, such as whether it currently belongs to the visual tree of the application, and not by the lifetime of the source.</span></span> <span data-ttu-id="73ca8-115">Каждый раз, когда время существования исходного объекта выходит за пределы времени существования объекта прослушивателя, шаблон обычного события приводит к утечке памяти: прослушиватель поддерживается дольше, чем планировалось.</span><span class="sxs-lookup"><span data-stu-id="73ca8-115">Whenever the source object lifetime extends beyond the object lifetime of the listener, the normal event pattern leads to a memory leak: the listener is kept alive longer than intended.</span></span>  
  
 <span data-ttu-id="73ca8-116">Шаблон слабых событий предназначен для решения этой проблемы утечки памяти.</span><span class="sxs-lookup"><span data-stu-id="73ca8-116">The weak event pattern is designed to solve this memory leak problem.</span></span> <span data-ttu-id="73ca8-117">Шаблон слабых событий можно использовать всякий раз, когда прослушивателю необходимо зарегистрироваться для события, но прослушиватель не знает, когда следует отменять регистрацию.</span><span class="sxs-lookup"><span data-stu-id="73ca8-117">The weak event pattern can be used whenever a listener needs to register for an event, but the listener does not explicitly know when to unregister.</span></span> <span data-ttu-id="73ca8-118">Шаблон слабых событий также можно использовать всякий раз, когда время существования объекта источника превышает полезное время существования объекта прослушивателя.</span><span class="sxs-lookup"><span data-stu-id="73ca8-118">The weak event pattern can also be used whenever the object lifetime of the source exceeds the useful object lifetime of the listener.</span></span> <span data-ttu-id="73ca8-119">(В этом случае *полезно* определить.) Шаблон слабых событий позволяет прослушивателю регистрироваться и принимать события, не влияя на характеристики времени существования объекта прослушивателя любым способом.</span><span class="sxs-lookup"><span data-stu-id="73ca8-119">(In this case, *useful* is determined by you.) The weak event pattern allows the listener to register for and receive the event without affecting the object lifetime characteristics of the listener in any way.</span></span> <span data-ttu-id="73ca8-120">Фактически неявная ссылка из источника не определяет, подходит ли прослушиватель для сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="73ca8-120">In effect, the implied reference from the source does not determine whether the listener is eligible for garbage collection.</span></span> <span data-ttu-id="73ca8-121">Ссылка является слабой ссылкой, то есть наименованием шаблона слабых событий и связанных с ним API.</span><span class="sxs-lookup"><span data-stu-id="73ca8-121">The reference is a weak reference, thus the naming of the weak event pattern and the related APIs.</span></span> <span data-ttu-id="73ca8-122">Прослушиватель может быть собран или удален сборщиком мусора, и источник можно продолжить без удержания ссылок на Несобираемые обработчики на уже уничтоженный объект.</span><span class="sxs-lookup"><span data-stu-id="73ca8-122">The listener can be garbage collected or otherwise destroyed, and the source can continue without retaining noncollectible handler references to a now destroyed object.</span></span>  
  
## <a name="who-should-implement-the-weak-event-pattern"></a><span data-ttu-id="73ca8-123">Кто должен реализовывать шаблон слабых событий?</span><span class="sxs-lookup"><span data-stu-id="73ca8-123">Who Should Implement the Weak Event Pattern?</span></span>  
 <span data-ttu-id="73ca8-124">Реализация шаблона слабых событий является наиболее интересной в основном для авторов элементов управления.</span><span class="sxs-lookup"><span data-stu-id="73ca8-124">Implementing the weak event pattern is interesting primarily for control authors.</span></span> <span data-ttu-id="73ca8-125">Как автор элемента управления, вы в основном отвечаете за поведение и включение элемента управления и влияние его на приложения, в которых он вставлен.</span><span class="sxs-lookup"><span data-stu-id="73ca8-125">As a control author, you are largely responsible for the behavior and containment of your control and the impact it has on applications in which it is inserted.</span></span> <span data-ttu-id="73ca8-126">Это включает в себя поведение времени существования управляющего объекта, в частности, обработку описанной проблемы утечки памяти.</span><span class="sxs-lookup"><span data-stu-id="73ca8-126">This includes the control object lifetime behavior, in particular the handling of the described memory leak problem.</span></span>  
  
 <span data-ttu-id="73ca8-127">Некоторые сценарии изначально предоставляются для применения шаблона слабых событий.</span><span class="sxs-lookup"><span data-stu-id="73ca8-127">Certain scenarios inherently lend themselves to the application of the weak event pattern.</span></span> <span data-ttu-id="73ca8-128">Одним из таких сценариев является привязка данных.</span><span class="sxs-lookup"><span data-stu-id="73ca8-128">One such scenario is data binding.</span></span> <span data-ttu-id="73ca8-129">В привязке данных обычно исходный объект полностью независим от объекта listener, который является целевым объектом привязки.</span><span class="sxs-lookup"><span data-stu-id="73ca8-129">In data binding, it is common for the source object to be completely independent of the listener object, which is a target of a binding.</span></span> <span data-ttu-id="73ca8-130">Многие аспекты [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] привязки данных уже имеют шаблон слабых событий, применяемый в способе реализации событий.</span><span class="sxs-lookup"><span data-stu-id="73ca8-130">Many aspects of [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] data binding already have the weak event pattern applied in how the events are implemented.</span></span>  
  
## <a name="how-to-implement-the-weak-event-pattern"></a><span data-ttu-id="73ca8-131">Реализация шаблона слабых событий</span><span class="sxs-lookup"><span data-stu-id="73ca8-131">How to Implement the Weak Event Pattern</span></span>  
 <span data-ttu-id="73ca8-132">Существует три способа реализации шаблона слабых событий.</span><span class="sxs-lookup"><span data-stu-id="73ca8-132">There are three ways to implement weak event pattern.</span></span> <span data-ttu-id="73ca8-133">В следующей таблице перечислены три подхода и приведены некоторые рекомендации по их использованию.</span><span class="sxs-lookup"><span data-stu-id="73ca8-133">The following table lists the three approaches and provides some guidance for when you should use each.</span></span>  
  
|<span data-ttu-id="73ca8-134">Подход</span><span class="sxs-lookup"><span data-stu-id="73ca8-134">Approach</span></span>|<span data-ttu-id="73ca8-135">Когда следует реализовывать</span><span class="sxs-lookup"><span data-stu-id="73ca8-135">When to Implement</span></span>|  
|--------------|-----------------------|  
|<span data-ttu-id="73ca8-136">Использование существующего класса диспетчера слабых событий</span><span class="sxs-lookup"><span data-stu-id="73ca8-136">Use an existing weak event manager class</span></span>|<span data-ttu-id="73ca8-137">Если событие, на которое нужно подписываться, имеет соответствующее значение <xref:System.Windows.WeakEventManager> , используйте существующий диспетчер слабых событий.</span><span class="sxs-lookup"><span data-stu-id="73ca8-137">If the event you want to subscribe to has a corresponding <xref:System.Windows.WeakEventManager>, use the existing weak event manager.</span></span> <span data-ttu-id="73ca8-138">Список слабых диспетчеров событий, входящих в состав WPF, см. в разделе Иерархия наследования в <xref:System.Windows.WeakEventManager> классе.</span><span class="sxs-lookup"><span data-stu-id="73ca8-138">For a list of weak event managers that are included with WPF, see the inheritance hierarchy in the <xref:System.Windows.WeakEventManager> class.</span></span> <span data-ttu-id="73ca8-139">Поскольку входящие диспетчеры событий ограничены, вам, вероятно, потребуется выбрать один из других подходов.</span><span class="sxs-lookup"><span data-stu-id="73ca8-139">Because the included weak event managers are limited, you will probably need to choose one of the other approaches.</span></span>|  
|<span data-ttu-id="73ca8-140">Использование универсального класса диспетчера слабых событий</span><span class="sxs-lookup"><span data-stu-id="73ca8-140">Use a generic weak event manager class</span></span>|<span data-ttu-id="73ca8-141">Использовать универсальный, <xref:System.Windows.WeakEventManager%602> Если существующий объект <xref:System.Windows.WeakEventManager> недоступен, вы хотите легко реализовать и не беспокоиться об эффективности.</span><span class="sxs-lookup"><span data-stu-id="73ca8-141">Use a generic <xref:System.Windows.WeakEventManager%602> when an existing <xref:System.Windows.WeakEventManager> is not available, you want an easy way to implement, and you are not concerned about efficiency.</span></span> <span data-ttu-id="73ca8-142">Универсальный объект <xref:System.Windows.WeakEventManager%602> менее эффективен, чем существующий или пользовательский диспетчер слабых событий.</span><span class="sxs-lookup"><span data-stu-id="73ca8-142">The generic <xref:System.Windows.WeakEventManager%602> is less efficient than an existing or custom weak event manager.</span></span> <span data-ttu-id="73ca8-143">Например, универсальный класс делает больше отражения для обнаружения события в заданном имени события.</span><span class="sxs-lookup"><span data-stu-id="73ca8-143">For example, the generic class does more reflection to discover the event given the event's name.</span></span> <span data-ttu-id="73ca8-144">Кроме того, код для регистрации события с помощью универсального <xref:System.Windows.WeakEventManager%602> типа является более подробным, чем использование существующего или пользовательского <xref:System.Windows.WeakEventManager> .</span><span class="sxs-lookup"><span data-stu-id="73ca8-144">Also, the code to register the event by using the generic <xref:System.Windows.WeakEventManager%602> is more verbose than using an existing or custom <xref:System.Windows.WeakEventManager>.</span></span>|  
|<span data-ttu-id="73ca8-145">Создание пользовательского класса диспетчера слабых событий</span><span class="sxs-lookup"><span data-stu-id="73ca8-145">Create a custom weak event manager class</span></span>|<span data-ttu-id="73ca8-146">Создание настраиваемого объекта, <xref:System.Windows.WeakEventManager> Если существующий объект <xref:System.Windows.WeakEventManager> недоступен и требуется лучшая эффективность.</span><span class="sxs-lookup"><span data-stu-id="73ca8-146">Create a custom <xref:System.Windows.WeakEventManager> when an existing <xref:System.Windows.WeakEventManager> is not available and you want the best efficiency.</span></span> <span data-ttu-id="73ca8-147">Использование настраиваемого объекта <xref:System.Windows.WeakEventManager> для подписки на событие будет более эффективным, однако стоимость написания кода в начале не взимается.</span><span class="sxs-lookup"><span data-stu-id="73ca8-147">Using a custom <xref:System.Windows.WeakEventManager> to subscribe to an event will be more efficient, but you do incur the cost of writing more code at the beginning.</span></span>|  
|<span data-ttu-id="73ca8-148">Использование стороннего диспетчера слабых событий</span><span class="sxs-lookup"><span data-stu-id="73ca8-148">Use a third-party weak event manager</span></span>|<span data-ttu-id="73ca8-149">NuGet имеет [несколько диспетчеров слабых событий](https://www.nuget.org/packages?q=weak+event+manager&prerel=false) , а многие платформы WPF также поддерживают шаблон (например, см. [документацию по Prism по слабо связанной подписке на события](https://github.com/PrismLibrary/Prism-Documentation/blob/master/docs/wpf/legacy/Communication.md#subscribing-to-events)).</span><span class="sxs-lookup"><span data-stu-id="73ca8-149">NuGet has [several weak event managers](https://www.nuget.org/packages?q=weak+event+manager&prerel=false) and many WPF frameworks also support the pattern (for instance, see [Prism's documentation on loosely coupled event subscription](https://github.com/PrismLibrary/Prism-Documentation/blob/master/docs/wpf/legacy/Communication.md#subscribing-to-events)).</span></span>|

 <span data-ttu-id="73ca8-150">В следующих разделах описывается реализация шаблона слабых событий.</span><span class="sxs-lookup"><span data-stu-id="73ca8-150">The following sections describe how to implement the weak event pattern.</span></span>  <span data-ttu-id="73ca8-151">В рамках этого обсуждения событие, для которого подписывается, имеет следующие характеристики.</span><span class="sxs-lookup"><span data-stu-id="73ca8-151">For purposes of this discussion, the event to subscribe to has the following characteristics.</span></span>  
  
- <span data-ttu-id="73ca8-152">Имя события — `SomeEvent` .</span><span class="sxs-lookup"><span data-stu-id="73ca8-152">The event name is `SomeEvent`.</span></span>  
  
- <span data-ttu-id="73ca8-153">Событие вызывается `EventSource` классом.</span><span class="sxs-lookup"><span data-stu-id="73ca8-153">The event is raised by the `EventSource` class.</span></span>  
  
- <span data-ttu-id="73ca8-154">Обработчик событий имеет тип: `SomeEventEventHandler` (или `EventHandler<SomeEventEventArgs>` ).</span><span class="sxs-lookup"><span data-stu-id="73ca8-154">The event handler has type: `SomeEventEventHandler` (or `EventHandler<SomeEventEventArgs>`).</span></span>  
  
- <span data-ttu-id="73ca8-155">Событие передает параметр типа `SomeEventEventArgs` в обработчики событий.</span><span class="sxs-lookup"><span data-stu-id="73ca8-155">The event passes a parameter of type `SomeEventEventArgs` to the event handlers.</span></span>  
  
### <a name="using-an-existing-weak-event-manager-class"></a><span data-ttu-id="73ca8-156">Использование существующего класса диспетчера слабых событий</span><span class="sxs-lookup"><span data-stu-id="73ca8-156">Using an Existing Weak Event Manager Class</span></span>  
  
1. <span data-ttu-id="73ca8-157">Найдите существующий диспетчер слабых событий.</span><span class="sxs-lookup"><span data-stu-id="73ca8-157">Find an existing weak event manager.</span></span>  
  
     <span data-ttu-id="73ca8-158">Список слабых диспетчеров событий, входящих в состав WPF, см. в разделе Иерархия наследования в <xref:System.Windows.WeakEventManager> классе.</span><span class="sxs-lookup"><span data-stu-id="73ca8-158">For a list of weak event managers that are included with WPF, see the inheritance hierarchy in the <xref:System.Windows.WeakEventManager> class.</span></span>  
  
2. <span data-ttu-id="73ca8-159">Используйте новый диспетчер слабых событий вместо обычного подключения к событию.</span><span class="sxs-lookup"><span data-stu-id="73ca8-159">Use the new weak event manager instead of the normal event hookup.</span></span>  
  
     <span data-ttu-id="73ca8-160">Например, если в коде для подписки на событие используется следующий шаблон:</span><span class="sxs-lookup"><span data-stu-id="73ca8-160">For example, if your code uses the following pattern to subscribe to an event:</span></span>  
  
    ```csharp  
    source.SomeEvent += new SomeEventEventHandler(OnSomeEvent);  
    ```  
  
     <span data-ttu-id="73ca8-161">Измените его на следующий шаблон:</span><span class="sxs-lookup"><span data-stu-id="73ca8-161">Change it to the following pattern:</span></span>  
  
    ```csharp  
    SomeEventWeakEventManager.AddHandler(source, OnSomeEvent);  
    ```  
  
     <span data-ttu-id="73ca8-162">Аналогично, если в коде используется следующий шаблон для отмены подписки на событие:</span><span class="sxs-lookup"><span data-stu-id="73ca8-162">Similarly, if your code uses the following pattern to unsubscribe from an event:</span></span>  
  
    ```csharp  
    source.SomeEvent -= new SomeEventEventHandler(OnSomeEvent);  
    ```  
  
     <span data-ttu-id="73ca8-163">Измените его на следующий шаблон:</span><span class="sxs-lookup"><span data-stu-id="73ca8-163">Change it to the following pattern:</span></span>  
  
    ```csharp  
    SomeEventWeakEventManager.RemoveHandler(source, OnSomeEvent);  
    ```  
  
### <a name="using-the-generic-weak-event-manager-class"></a><span data-ttu-id="73ca8-164">Использование универсального класса диспетчера слабых событий</span><span class="sxs-lookup"><span data-stu-id="73ca8-164">Using the Generic Weak Event Manager Class</span></span>  
  
1. <span data-ttu-id="73ca8-165">Используйте универсальный <xref:System.Windows.WeakEventManager%602> класс вместо обычной подписки на событие.</span><span class="sxs-lookup"><span data-stu-id="73ca8-165">Use the generic <xref:System.Windows.WeakEventManager%602> class instead of the normal event hookup.</span></span>  
  
     <span data-ttu-id="73ca8-166">При использовании <xref:System.Windows.WeakEventManager%602> для регистрации прослушивателей событий необходимо указать источник события и тип в <xref:System.EventArgs> качестве параметров типа для класса и вызвать <xref:System.Windows.WeakEventManager%602.AddHandler%2A> , как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="73ca8-166">When you use <xref:System.Windows.WeakEventManager%602> to register event listeners, you supply the event source and <xref:System.EventArgs> type as the type parameters to the class and call <xref:System.Windows.WeakEventManager%602.AddHandler%2A> as shown in the following code:</span></span>  
  
    ```csharp  
    WeakEventManager<EventSource, SomeEventEventArgs>.AddHandler(source, "SomeEvent", source_SomeEvent);  
    ```  
  
### <a name="creating-a-custom-weak-event-manager-class"></a><span data-ttu-id="73ca8-167">Создание пользовательского класса диспетчера слабых событий</span><span class="sxs-lookup"><span data-stu-id="73ca8-167">Creating a Custom Weak Event Manager Class</span></span>  
  
1. <span data-ttu-id="73ca8-168">Скопируйте следующий шаблон класса в проект.</span><span class="sxs-lookup"><span data-stu-id="73ca8-168">Copy the following class template to your project.</span></span>  
  
     <span data-ttu-id="73ca8-169">Этот класс наследуется от <xref:System.Windows.WeakEventManager> класса.</span><span class="sxs-lookup"><span data-stu-id="73ca8-169">This class inherits from the <xref:System.Windows.WeakEventManager> class.</span></span>  
  
     [!code-csharp[WeakEvents#WeakEventManagerTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/WeakEvents/CSharp/WeakEventManagerTemplate.cs#weakeventmanagertemplate)]  
  
2. <span data-ttu-id="73ca8-170">Замените имя своим именем `SomeEventWeakEventManager` .</span><span class="sxs-lookup"><span data-stu-id="73ca8-170">Replace the `SomeEventWeakEventManager` name with your own name.</span></span>  
  
3. <span data-ttu-id="73ca8-171">Замените три имени, описанные выше, соответствующими именами для события.</span><span class="sxs-lookup"><span data-stu-id="73ca8-171">Replace the three names described previously with the corresponding names for your event.</span></span> <span data-ttu-id="73ca8-172">( `SomeEvent` , `EventSource` и `SomeEventEventArgs` )</span><span class="sxs-lookup"><span data-stu-id="73ca8-172">(`SomeEvent`, `EventSource`, and `SomeEventEventArgs`)</span></span>  
  
4. <span data-ttu-id="73ca8-173">Задайте для свойства Visibility (открытый/внутренний/частный) класс диспетчера событий ту же видимость, что и управляемое им событие.</span><span class="sxs-lookup"><span data-stu-id="73ca8-173">Set the visibility (public / internal / private) of the weak event manager class to the same visibility as event it manages.</span></span>  
  
5. <span data-ttu-id="73ca8-174">Используйте новый диспетчер слабых событий вместо обычного подключения к событию.</span><span class="sxs-lookup"><span data-stu-id="73ca8-174">Use the new weak event manager instead of the normal event hookup.</span></span>  
  
     <span data-ttu-id="73ca8-175">Например, если в коде для подписки на событие используется следующий шаблон:</span><span class="sxs-lookup"><span data-stu-id="73ca8-175">For example, if your code uses the following pattern to subscribe to an event:</span></span>  
  
    ```csharp  
    source.SomeEvent += new SomeEventEventHandler(OnSomeEvent);  
    ```  
  
     <span data-ttu-id="73ca8-176">Измените его на следующий шаблон:</span><span class="sxs-lookup"><span data-stu-id="73ca8-176">Change it to the following pattern:</span></span>  
  
    ```csharp  
    SomeEventWeakEventManager.AddHandler(source, OnSomeEvent);  
    ```  
  
     <span data-ttu-id="73ca8-177">Аналогично, если в коде используется следующий шаблон для отмены подписки на событие:</span><span class="sxs-lookup"><span data-stu-id="73ca8-177">Similarly, if your code uses the following pattern to unsubscribe to an event:</span></span>  
  
    ```csharp  
    source.SomeEvent -= new SomeEventEventHandler(OnSome);  
    ```  
  
     <span data-ttu-id="73ca8-178">Измените его на следующий шаблон:</span><span class="sxs-lookup"><span data-stu-id="73ca8-178">Change it to the following pattern:</span></span>  
  
    ```csharp  
    SomeEventWeakEventManager.RemoveHandler(source, OnSomeEvent);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="73ca8-179">См. также</span><span class="sxs-lookup"><span data-stu-id="73ca8-179">See also</span></span>

- <xref:System.Windows.WeakEventManager>
- <xref:System.Windows.IWeakEventListener>
- [<span data-ttu-id="73ca8-180">Общие сведения о перенаправленных событиях</span><span class="sxs-lookup"><span data-stu-id="73ca8-180">Routed Events Overview</span></span>](routed-events-overview.md)
- [<span data-ttu-id="73ca8-181">Общие сведения о привязке данных</span><span class="sxs-lookup"><span data-stu-id="73ca8-181">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
