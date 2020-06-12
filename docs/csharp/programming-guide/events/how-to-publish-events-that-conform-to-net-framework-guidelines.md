---
title: Руководство по программированию на C#. Публикация событий, соответствующих рекомендациям .NET
ms.date: 05/26/2020
helpviewer_keywords:
- events [C#], implementation guidelines
ms.assetid: 9310ae16-8627-44a2-b08c-05e5976202b1
ms.openlocfilehash: df2f643f867b93b74d04d8fbd673df545c28938e
ms.sourcegitcommit: a241301495a84cc8c64fe972330d16edd619868b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/01/2020
ms.locfileid: "84240750"
---
# <a name="how-to-publish-events-that-conform-to-net-guidelines-c-programming-guide"></a><span data-ttu-id="a58b1-102">Публикация событий, соответствующих рекомендациям .NET (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="a58b1-102">How to publish events that conform to .NET Guidelines (C# Programming Guide)</span></span>

<span data-ttu-id="a58b1-103">Следующая процедура демонстрирует добавление событий, которые соответствуют стандартному шаблону .NET для классов и структур.</span><span class="sxs-lookup"><span data-stu-id="a58b1-103">The following procedure demonstrates how to add events that follow the standard .NET pattern to your classes and structs.</span></span> <span data-ttu-id="a58b1-104">Все события в библиотеке классов .NET Framework основаны на делегате <xref:System.EventHandler>, который определен следующим образом:</span><span class="sxs-lookup"><span data-stu-id="a58b1-104">All events in the .NET Framework class library are based on the <xref:System.EventHandler> delegate, which is defined as follows:</span></span>

```csharp
public delegate void EventHandler(object sender, EventArgs e);
```

> [!NOTE]
> <span data-ttu-id="a58b1-105">В .NET Framework 2.0 представлена универсальная версия этого делегата, <xref:System.EventHandler%601>.</span><span class="sxs-lookup"><span data-stu-id="a58b1-105">.NET Framework 2.0 introduces a generic version of this delegate, <xref:System.EventHandler%601>.</span></span> <span data-ttu-id="a58b1-106">В следующих примерах демонстрируется использование обеих версий.</span><span class="sxs-lookup"><span data-stu-id="a58b1-106">The following examples show how to use both versions.</span></span>

<span data-ttu-id="a58b1-107">Хотя события в определяемых классах могут быть основаны на любом допустимом типе делегата, даже на делегатах, возвращающих значение, обычно рекомендуется основывать события на шаблоне .NET с помощью <xref:System.EventHandler>, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="a58b1-107">Although events in classes that you define can be based on any valid delegate type, even delegates that return a value, it is generally recommended that you base your events on the .NET pattern by using <xref:System.EventHandler>, as shown in the following example.</span></span>

<span data-ttu-id="a58b1-108">Имя `EventHandler` может привести к путанице, так как на самом деле этот делегат не обрабатывает событие.</span><span class="sxs-lookup"><span data-stu-id="a58b1-108">The name `EventHandler` can lead to a bit of confusion as it doesn't actually handle the event.</span></span> <span data-ttu-id="a58b1-109">Делегат <xref:System.EventHandler> и универсальный делегат <xref:System.EventHandler%601> являются типами делегатов.</span><span class="sxs-lookup"><span data-stu-id="a58b1-109">The <xref:System.EventHandler>, and generic <xref:System.EventHandler%601> are delegate types.</span></span> <span data-ttu-id="a58b1-110">Метод или лямбда-выражение, сигнатура которого соответствует определению делегата, является *обработчиком событий* и будет вызываться при возникновении события.</span><span class="sxs-lookup"><span data-stu-id="a58b1-110">A method or lambda expression whose signature matches the delegate definition is the *event handler* and will be invoked when the event is raised.</span></span>

## <a name="publish-events-based-on-the-eventhandler-pattern"></a><span data-ttu-id="a58b1-111">Публикация событий, основанных на шаблоне EventHandler</span><span class="sxs-lookup"><span data-stu-id="a58b1-111">Publish events based on the EventHandler pattern</span></span>

1. <span data-ttu-id="a58b1-112">(Пропустите этот шаг и перейдите к шагу 3a, если не нужно отправлять пользовательские данные с определенным событием.) Объявите класс для пользовательских данных в области, видимой для классов Publisher и Subscriber.</span><span class="sxs-lookup"><span data-stu-id="a58b1-112">(Skip this step and go to Step 3a if you do not have to send custom data with your event.) Declare the class for your custom data at a scope that is visible to both your publisher and subscriber classes.</span></span> <span data-ttu-id="a58b1-113">Затем добавьте необходимые члены для хранения пользовательских данных о событиях.</span><span class="sxs-lookup"><span data-stu-id="a58b1-113">Then add the required members to hold your custom event data.</span></span> <span data-ttu-id="a58b1-114">В этом примере возвращается простая строка.</span><span class="sxs-lookup"><span data-stu-id="a58b1-114">In this example, a simple string is returned.</span></span>

    ```csharp
    public class CustomEventArgs : EventArgs
    {
        public CustomEventArgs(string message)
        {
            Message = message;
        }

        public string Message { get; set; }
    }
    ```

2. <span data-ttu-id="a58b1-115">(Пропустите этот шаг, если используется универсальная версия <xref:System.EventHandler%601>.) Объявите делегат в своем классе публикации.</span><span class="sxs-lookup"><span data-stu-id="a58b1-115">(Skip this step if you are using the generic version of <xref:System.EventHandler%601>.) Declare a delegate in your publishing class.</span></span> <span data-ttu-id="a58b1-116">Присвойте ему имя, которое заканчивается на `EventHandler`.</span><span class="sxs-lookup"><span data-stu-id="a58b1-116">Give it a name that ends with `EventHandler`.</span></span> <span data-ttu-id="a58b1-117">Второй параметр указывает настраиваемый тип `EventArgs`.</span><span class="sxs-lookup"><span data-stu-id="a58b1-117">The second parameter specifies your custom `EventArgs` type.</span></span>

    ```csharp
    public delegate void CustomEventHandler(object sender, CustomEventArgs args);
    ```

3. <span data-ttu-id="a58b1-118">Объявите событие в своем классе публикации, выполнив одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="a58b1-118">Declare the event in your publishing class by using one of the following steps.</span></span>

    1. <span data-ttu-id="a58b1-119">Если у вас нет пользовательского класса EventArgs, тип события будет неуниверсальным делегатом EventHandler.</span><span class="sxs-lookup"><span data-stu-id="a58b1-119">If you have no custom EventArgs class, your Event type will be the non-generic EventHandler delegate.</span></span> <span data-ttu-id="a58b1-120">Нет необходимости объявлять делегат, так как он уже объявлен в пространстве имен <xref:System>, которое включается при создании проекта C#.</span><span class="sxs-lookup"><span data-stu-id="a58b1-120">You do not have to declare the delegate because it is already declared in the <xref:System> namespace that is included when you create your C# project.</span></span> <span data-ttu-id="a58b1-121">Добавьте следующий код в класс Publisher.</span><span class="sxs-lookup"><span data-stu-id="a58b1-121">Add the following code to your publisher class.</span></span>

        ```csharp
        public event EventHandler RaiseCustomEvent;
        ```

    2. <span data-ttu-id="a58b1-122">Если вы используете неуниверсальную версию <xref:System.EventHandler> и имеется пользовательский класс, производный от <xref:System.EventArgs>, объявите событие внутри класса публикации и используйте делегат из шага 2 в качестве типа.</span><span class="sxs-lookup"><span data-stu-id="a58b1-122">If you are using the non-generic version of <xref:System.EventHandler> and you have a custom class derived from <xref:System.EventArgs>, declare your event inside your publishing class and use your delegate from step 2 as the type.</span></span>

        ```csharp
        public event CustomEventHandler RaiseCustomEvent;
        ```

    3. <span data-ttu-id="a58b1-123">Если используется универсальная версия, пользовательский делегат не требуется.</span><span class="sxs-lookup"><span data-stu-id="a58b1-123">If you are using the generic version, you do not need a custom delegate.</span></span> <span data-ttu-id="a58b1-124">Вместо этого в классе публикации укажите тип события как `EventHandler<CustomEventArgs>`, подставив имя своего класса в угловые скобки.</span><span class="sxs-lookup"><span data-stu-id="a58b1-124">Instead, in your publishing class, you specify your event type as `EventHandler<CustomEventArgs>`, substituting the name of your own class between the angle brackets.</span></span>

        ```csharp
        public event EventHandler<CustomEventArgs> RaiseCustomEvent;
        ```

## <a name="example"></a><span data-ttu-id="a58b1-125">Пример</span><span class="sxs-lookup"><span data-stu-id="a58b1-125">Example</span></span>

<span data-ttu-id="a58b1-126">В следующем примере показана вышеописанная процедура с использованием пользовательского класса EventArgs и <xref:System.EventHandler%601> в качестве типа событий.</span><span class="sxs-lookup"><span data-stu-id="a58b1-126">The following example demonstrates the previous steps by using a custom EventArgs class and <xref:System.EventHandler%601> as the event type.</span></span>

[!code-csharp[csProgGuideEvents#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEvents/CS/Events.cs#2)]

## <a name="see-also"></a><span data-ttu-id="a58b1-127">См. также</span><span class="sxs-lookup"><span data-stu-id="a58b1-127">See also</span></span>

- <xref:System.Delegate>
- [<span data-ttu-id="a58b1-128">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="a58b1-128">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="a58b1-129">События</span><span class="sxs-lookup"><span data-stu-id="a58b1-129">Events</span></span>](index.md)
- [<span data-ttu-id="a58b1-130">Делегаты</span><span class="sxs-lookup"><span data-stu-id="a58b1-130">Delegates</span></span>](../delegates/index.md)
