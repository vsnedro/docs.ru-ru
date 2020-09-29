---
title: Руководство по программированию на C#. Подписка и отмена подписки на события
description: Сведения о подписке и отмене подписки на события. Узнайте, как подписаться на события с помощью Visual Studio IDE, программных средств или анонимного метода.
ms.date: 07/20/2015
helpviewer_keywords:
- event handlers [C#], creating
- Code Editor, event handlers
- events [C#], creating using the IDE
ms.assetid: 6319f39f-282c-4173-8a62-6c4657cf51cd
ms.openlocfilehash: 1e090301982a785fed2a8a6a95ee48bd1c7457ab
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91167487"
---
# <a name="how-to-subscribe-to-and-unsubscribe-from-events-c-programming-guide"></a><span data-ttu-id="bee38-104">Руководство по программированию на C#. Подписка и отмена подписки на события</span><span class="sxs-lookup"><span data-stu-id="bee38-104">How to subscribe to and unsubscribe from events (C# Programming Guide)</span></span>

<span data-ttu-id="bee38-105">Необходимость подписки на событие, опубликованное другим классом, может возникнуть, когда требуется написать пользовательский код, вызываемый при инициировании такого события.</span><span class="sxs-lookup"><span data-stu-id="bee38-105">You subscribe to an event that is published by another class when you want to write custom code that is called when that event is raised.</span></span> <span data-ttu-id="bee38-106">Например, можно подписаться на событие кнопки `click`, чтобы приложение выполняло некоторое действие при нажатии пользователем кнопки.</span><span class="sxs-lookup"><span data-stu-id="bee38-106">For example, you might subscribe to a button's `click` event in order to make your application do something useful when the user clicks the button.</span></span>  
  
### <a name="to-subscribe-to-events-by-using-the-visual-studio-ide"></a><span data-ttu-id="bee38-107">Подписка на события в интегрированной среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="bee38-107">To subscribe to events by using the Visual Studio IDE</span></span>  
  
1. <span data-ttu-id="bee38-108">Если окно **Свойства** закрыто, в представлении **Конструктор** щелкните правой кнопкой мыши форму или элемент управления, для которого требуется создать обработчик событий, и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="bee38-108">If you cannot see the **Properties** window, in **Design** view, right-click the form or control for which you want to create an event handler, and select **Properties**.</span></span>  
  
2. <span data-ttu-id="bee38-109">Вверху окна **Свойства** щелкните значок **События**.</span><span class="sxs-lookup"><span data-stu-id="bee38-109">On top of the **Properties** window, click the **Events** icon.</span></span>  
  
3. <span data-ttu-id="bee38-110">Дважды щелкните событие, которое требуется создать, например событие `Load`.</span><span class="sxs-lookup"><span data-stu-id="bee38-110">Double-click the event that you want to create, for example the `Load` event.</span></span>  
  
     <span data-ttu-id="bee38-111">Visual C# создаст пустой метод обработчика событий и добавит его в код.</span><span class="sxs-lookup"><span data-stu-id="bee38-111">Visual C# creates an empty event handler method and adds it to your code.</span></span> <span data-ttu-id="bee38-112">Код можно также добавить вручную в представлении **Код**.</span><span class="sxs-lookup"><span data-stu-id="bee38-112">Alternatively you can add the code manually in **Code** view.</span></span> <span data-ttu-id="bee38-113">Например, приведенные ниже строки кода объявляют метод обработчика событий, который будет выполнен при вызове классом `Form` события `Load`.</span><span class="sxs-lookup"><span data-stu-id="bee38-113">For example, the following lines of code declare an event handler method that will be called when the `Form` class raises the `Load` event.</span></span>  
  
     [!code-csharp[csProgGuideEvents#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEvents/CS/Events.cs#11)]  
  
     <span data-ttu-id="bee38-114">Строка кода, требуемая для подписки на событие, также создается автоматически в методе `InitializeComponent` в файле Form1.Designer.cs проекта.</span><span class="sxs-lookup"><span data-stu-id="bee38-114">The line of code that is required to subscribe to the event is also automatically generated in the `InitializeComponent` method in the Form1.Designer.cs file in your project.</span></span> <span data-ttu-id="bee38-115">Она имеет следующий вид:</span><span class="sxs-lookup"><span data-stu-id="bee38-115">It resembles this:</span></span>  
  
    ```csharp
    this.Load += new System.EventHandler(this.Form1_Load);  
    ```  
  
### <a name="to-subscribe-to-events-programmatically"></a><span data-ttu-id="bee38-116">Подписка на события программными средствами</span><span class="sxs-lookup"><span data-stu-id="bee38-116">To subscribe to events programmatically</span></span>  
  
1. <span data-ttu-id="bee38-117">Определите метод обработчика событий, сигнатура которого соответствует сигнатуре делегата для события.</span><span class="sxs-lookup"><span data-stu-id="bee38-117">Define an event handler method whose signature matches the delegate signature for the event.</span></span> <span data-ttu-id="bee38-118">Например, если событие основано на типе делегата <xref:System.EventHandler>, то следующий код представляет заглушку метода:</span><span class="sxs-lookup"><span data-stu-id="bee38-118">For example, if the event is based on the <xref:System.EventHandler> delegate type, the following code represents the method stub:</span></span>  
  
    ```csharp
    void HandleCustomEvent(object sender, CustomEventArgs a)  
    {  
       // Do something useful here.  
    }  
    ```  
  
2. <span data-ttu-id="bee38-119">Чтобы присоединить обработчик событий к событию, используйте оператор присваивания сложения (`+=`).</span><span class="sxs-lookup"><span data-stu-id="bee38-119">Use the addition assignment operator (`+=`) to attach an event handler to the event.</span></span> <span data-ttu-id="bee38-120">В приведенном ниже примере предположим, что объект с именем `publisher` имеет событие с именем `RaiseCustomEvent`.</span><span class="sxs-lookup"><span data-stu-id="bee38-120">In the following example, assume that an object named `publisher` has an event named `RaiseCustomEvent`.</span></span> <span data-ttu-id="bee38-121">Обратите внимание на то, что классу подписчика требуется ссылка на класс издателя, чтобы подписаться на его события.</span><span class="sxs-lookup"><span data-stu-id="bee38-121">Note that the subscriber class needs a reference to the publisher class in order to subscribe to its events.</span></span>  
  
    ```csharp
    publisher.RaiseCustomEvent += HandleCustomEvent;  
    ```  
  
     <span data-ttu-id="bee38-122">Обратите внимание, что приведенный выше синтаксис появился только в C# 2.0.</span><span class="sxs-lookup"><span data-stu-id="bee38-122">Note that the previous syntax is new in C# 2.0.</span></span> <span data-ttu-id="bee38-123">Он в точности соответствует синтаксису C# 1.0, в котором с помощью ключевого слова `new` должен быть явно создан инкапсулирующий делегат.</span><span class="sxs-lookup"><span data-stu-id="bee38-123">It is exactly equivalent to the C# 1.0 syntax in which the encapsulating delegate must be explicitly created by using the `new` keyword:</span></span>  
  
    ```csharp
    publisher.RaiseCustomEvent += new CustomEventHandler(HandleCustomEvent);  
    ```  
  
     <span data-ttu-id="bee38-124">Чтобы указать обработчик событий, можно также воспользоваться [лямбда-выражением](../../language-reference/operators/lambda-expressions.md):</span><span class="sxs-lookup"><span data-stu-id="bee38-124">You can also use a [lambda expression](../../language-reference/operators/lambda-expressions.md) to specify an event handler:</span></span>
  
    ```csharp
    public Form1()  
    {  
        InitializeComponent();  
        this.Click += (s,e) =>
            {
                MessageBox.Show(((MouseEventArgs)e).Location.ToString());
            };
    }  
    ```  
  
### <a name="to-subscribe-to-events-by-using-an-anonymous-method"></a><span data-ttu-id="bee38-125">Подписка на события с помощью анонимного метода</span><span class="sxs-lookup"><span data-stu-id="bee38-125">To subscribe to events by using an anonymous method</span></span>  
  
- <span data-ttu-id="bee38-126">Если не нужно будет позже отменять подписку на событие, можно использовать оператор присваивания сложения (`+=`) для прикрепления к событию анонимного метода.</span><span class="sxs-lookup"><span data-stu-id="bee38-126">If you will not have to unsubscribe to an event later, you can use the addition assignment operator (`+=`) to attach an anonymous method to the event.</span></span> <span data-ttu-id="bee38-127">В следующем примере предположим, что объект с именем `publisher` имеет событие с именем `RaiseCustomEvent` и что класс `CustomEventArgs` также был определен и содержит некие относящиеся к событию сведения.</span><span class="sxs-lookup"><span data-stu-id="bee38-127">In the following example, assume that an object named `publisher` has an event named `RaiseCustomEvent` and that a `CustomEventArgs` class has also been defined to carry some kind of specialized event information.</span></span> <span data-ttu-id="bee38-128">Обратите внимание на то, что классу подписчика требуется ссылка на `publisher`, чтобы подписаться на его события.</span><span class="sxs-lookup"><span data-stu-id="bee38-128">Note that the subscriber class needs a reference to `publisher` in order to subscribe to its events.</span></span>  
  
    ```csharp
    publisher.RaiseCustomEvent += delegate(object o, CustomEventArgs e)  
    {  
      string s = o.ToString() + " " + e.ToString();  
      Console.WriteLine(s);  
    };  
    ```  
  
     <span data-ttu-id="bee38-129">Важно отметить, что отменить подписку на событие не так просто, если для подписки на него использовалась анонимная функция.</span><span class="sxs-lookup"><span data-stu-id="bee38-129">It is important to notice that you cannot easily unsubscribe from an event if you used an anonymous function to subscribe to it.</span></span> <span data-ttu-id="bee38-130">Чтобы отменить подписку в этом случае, необходимо вернуться к коду, в котором была выполнена подписка на событие, сохранить анонимный метод в переменной делегата, а затем добавить делегат к событию.</span><span class="sxs-lookup"><span data-stu-id="bee38-130">To unsubscribe in this scenario, it is necessary to go back to the code where you subscribe to the event, store the anonymous method in a delegate variable, and then add the delegate to the event.</span></span> <span data-ttu-id="bee38-131">Как правило, мы рекомендуем не использовать анонимных функций для подписки на события, если предполагается, что в будущем будет нужно отменять подписку на событие.</span><span class="sxs-lookup"><span data-stu-id="bee38-131">In general, we recommend that you do not use anonymous functions to subscribe to events if you will have to unsubscribe from the event at some later point in your code.</span></span> <span data-ttu-id="bee38-132">Дополнительные сведения об анонимных функциях см. в разделе [Анонимные функции](../statements-expressions-operators/anonymous-functions.md).</span><span class="sxs-lookup"><span data-stu-id="bee38-132">For more information about anonymous functions, see [Anonymous Functions](../statements-expressions-operators/anonymous-functions.md).</span></span>  
  
## <a name="unsubscribing"></a><span data-ttu-id="bee38-133">Отмена подписки</span><span class="sxs-lookup"><span data-stu-id="bee38-133">Unsubscribing</span></span>  

 <span data-ttu-id="bee38-134">Чтобы предотвратить вызов обработчика событий при инициировании события, подписку на событие необходимо отменить.</span><span class="sxs-lookup"><span data-stu-id="bee38-134">To prevent your event handler from being invoked when the event is raised, unsubscribe from the event.</span></span> <span data-ttu-id="bee38-135">Во избежание утечки ресурсов отменять подписку на события следует до удаления объекта подписчика.</span><span class="sxs-lookup"><span data-stu-id="bee38-135">In order to prevent resource leaks, you should unsubscribe from events before you dispose of a subscriber object.</span></span> <span data-ttu-id="bee38-136">До тех пор пока подписка на событие не отменена, делегат многоадресной рассылки, лежащий в основе события в публикующем объекте, будет ссылаться на делегат, инкапсулирующий обработчик событий подписчика.</span><span class="sxs-lookup"><span data-stu-id="bee38-136">Until you unsubscribe from an event, the multicast delegate that underlies the event in the publishing object has a reference to the delegate that encapsulates the subscriber's event handler.</span></span> <span data-ttu-id="bee38-137">Если ссылка присутствует в публикующем объекте, объект подписчика не будет удален при сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="bee38-137">As long as the publishing object holds that reference, garbage collection will not delete your subscriber object.</span></span>  
  
#### <a name="to-unsubscribe-from-an-event"></a><span data-ttu-id="bee38-138">Отмена подписки на событие</span><span class="sxs-lookup"><span data-stu-id="bee38-138">To unsubscribe from an event</span></span>  
  
- <span data-ttu-id="bee38-139">Чтобы отменить подписку на событие, воспользуйтесь оператором присваивания вычитания (`-=`).</span><span class="sxs-lookup"><span data-stu-id="bee38-139">Use the subtraction assignment operator (`-=`) to unsubscribe from an event:</span></span>  
  
    ```csharp
    publisher.RaiseCustomEvent -= HandleCustomEvent;  
    ```  
  
     <span data-ttu-id="bee38-140">Если подписка на событие отменена для всех подписчиков, экземпляр события в классе издателя получает значение `null`.</span><span class="sxs-lookup"><span data-stu-id="bee38-140">When all subscribers have unsubscribed from an event, the event instance in the publisher class is set to `null`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bee38-141">См. также</span><span class="sxs-lookup"><span data-stu-id="bee38-141">See also</span></span>

- [<span data-ttu-id="bee38-142">События</span><span class="sxs-lookup"><span data-stu-id="bee38-142">Events</span></span>](./index.md)
- [<span data-ttu-id="bee38-143">event</span><span class="sxs-lookup"><span data-stu-id="bee38-143">event</span></span>](../../language-reference/keywords/event.md)
- [<span data-ttu-id="bee38-144">Практическое руководство. Публикация событий, соответствующих рекомендациям .NET</span><span class="sxs-lookup"><span data-stu-id="bee38-144">How to publish events that conform to .NET Guidelines</span></span>](./how-to-publish-events-that-conform-to-net-framework-guidelines.md)
- [<span data-ttu-id="bee38-145">Операторы - и -=</span><span class="sxs-lookup"><span data-stu-id="bee38-145">- and -= operators</span></span>](../../language-reference/operators/subtraction-operator.md)
- [<span data-ttu-id="bee38-146">Операторы + и +=</span><span class="sxs-lookup"><span data-stu-id="bee38-146">+ and += operators</span></span>](../../language-reference/operators/addition-operator.md)
