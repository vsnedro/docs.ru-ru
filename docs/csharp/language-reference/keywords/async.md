---
description: Справочник по C#. Модификатор async
title: Справочник по C#. Модификатор async
ms.date: 05/22/2017
f1_keywords:
- async_CSharpKeyword
helpviewer_keywords:
- async keyword [C#]
- async method [C#]
- async [C#]
ms.assetid: 16f14f09-b2ce-42c7-a875-e4eca5d50674
ms.openlocfilehash: 5a70389c9c423300fad03123cfc4738dfe10e481
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2020
ms.locfileid: "89118524"
---
# <a name="async-c-reference"></a><span data-ttu-id="a5c0d-103">async (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="a5c0d-103">async (C# Reference)</span></span>

<span data-ttu-id="a5c0d-104">Модификатор `async` позволяет указать, что метод, [лямбда-выражение](../operators/lambda-expressions.md) или [анонимный метод](../operators/delegate-operator.md) является асинхронным.</span><span class="sxs-lookup"><span data-stu-id="a5c0d-104">Use the `async` modifier to specify that a method, [lambda expression](../operators/lambda-expressions.md), or [anonymous method](../operators/delegate-operator.md) is asynchronous.</span></span> <span data-ttu-id="a5c0d-105">Если этот модификатор используется в методе или выражении, они называются *асинхронными методами*.</span><span class="sxs-lookup"><span data-stu-id="a5c0d-105">If you use this modifier on a method or expression, it's referred to as an *async method*.</span></span> <span data-ttu-id="a5c0d-106">Ниже приводится пример асинхронного метода с именем `ExampleMethodAsync`:</span><span class="sxs-lookup"><span data-stu-id="a5c0d-106">The following example defines an async method named `ExampleMethodAsync`:</span></span>

```csharp
public async Task<int> ExampleMethodAsync()
{
    //...
}
```

<span data-ttu-id="a5c0d-107">Если вы только начали заниматься асинхронным программированием или не понимаете, как в асинхронном методе используется [оператор `await`](../operators/await.md) для выполнения потенциально долгих операций без блокировки потока вызывающего объекта, ознакомьтесь с общими сведениями в статье [Асинхронное программирование с использованием ключевых слов async и await](../../programming-guide/concepts/async/index.md).</span><span class="sxs-lookup"><span data-stu-id="a5c0d-107">If you're new to asynchronous programming or do not understand how an async method uses the [`await` operator](../operators/await.md) to do potentially long-running work without blocking the caller's thread, read the introduction in [Asynchronous programming with async and await](../../programming-guide/concepts/async/index.md).</span></span> <span data-ttu-id="a5c0d-108">Следующий код размещается внутри асинхронного метода и вызывает метод <xref:System.Net.Http.HttpClient.GetStringAsync%2a?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="a5c0d-108">The following code is found inside an async method and calls the <xref:System.Net.Http.HttpClient.GetStringAsync%2a?displayProperty=nameWithType> method:</span></span>

```csharp
string contents = await httpClient.GetStringAsync(requestUrl);
```

<span data-ttu-id="a5c0d-109">Асинхронный метод выполняется синхронным образом до тех пор, пока не будет достигнуто первое выражение `await`, после чего метод приостанавливается, пока не будет завершена ожидаемая задача.</span><span class="sxs-lookup"><span data-stu-id="a5c0d-109">An async method runs synchronously until it reaches its first `await` expression, at which point the method is suspended until the awaited task is complete.</span></span> <span data-ttu-id="a5c0d-110">В то же время управление возвращается в вызывающий объект метода, как показано в примере в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="a5c0d-110">In the meantime, control returns to the caller of the method, as the example in the next section shows.</span></span>

<span data-ttu-id="a5c0d-111">Если метод, который изменяется ключевым словом `async`, не содержит выражения или оператора `await`, метод выполняется синхронно.</span><span class="sxs-lookup"><span data-stu-id="a5c0d-111">If the method that the `async` keyword modifies doesn't contain an `await` expression or statement, the method executes synchronously.</span></span> <span data-ttu-id="a5c0d-112">Компилятор выводит предупреждения обо всех асинхронных методах, не содержащих операторы `await`, поскольку такая ситуация может указывать на ошибку.</span><span class="sxs-lookup"><span data-stu-id="a5c0d-112">A compiler warning alerts you to any async methods that don't contain `await` statements, because that situation might indicate an error.</span></span> <span data-ttu-id="a5c0d-113">См. раздел [Предупреждение компилятора (уровень 1) CS4014](../compiler-messages/cs4014.md).</span><span class="sxs-lookup"><span data-stu-id="a5c0d-113">See [Compiler Warning (level 1) CS4014](../compiler-messages/cs4014.md).</span></span>

 <span data-ttu-id="a5c0d-114">Ключевое слово `async` — это контекстно-зависимо ключевое слово, которое является ключевым словом, когда оно изменяет метод, лямбда-выражение или анонимный метод.</span><span class="sxs-lookup"><span data-stu-id="a5c0d-114">The `async` keyword is contextual in that it's a keyword only when it modifies a method, a lambda expression, or an anonymous method.</span></span> <span data-ttu-id="a5c0d-115">Во всех других контекстах он интерпретируется как идентификатор.</span><span class="sxs-lookup"><span data-stu-id="a5c0d-115">In all other contexts, it's interpreted as an identifier.</span></span>

## <a name="example"></a><span data-ttu-id="a5c0d-116">Пример</span><span class="sxs-lookup"><span data-stu-id="a5c0d-116">Example</span></span>
<span data-ttu-id="a5c0d-117">В следующем примере показана структура и поток управления между обработчиком асинхронных событий `StartButton_Click` и асинхронным методом `ExampleMethodAsync`.</span><span class="sxs-lookup"><span data-stu-id="a5c0d-117">The following example shows the structure and flow of control between an async event handler, `StartButton_Click`, and an async method, `ExampleMethodAsync`.</span></span> <span data-ttu-id="a5c0d-118">В результате выполнения этого асинхронного метода возвращается число символов на веб-странице.</span><span class="sxs-lookup"><span data-stu-id="a5c0d-118">The result from the async method is the number of characters of a web page.</span></span> <span data-ttu-id="a5c0d-119">Код подходит для приложения Windows Presentation Foundation (WPF) или приложения для Магазина Windows Presentation Foundation (WPF), которые создаются в Visual Studio; см. комментарии к коду для настройки приложения.</span><span class="sxs-lookup"><span data-stu-id="a5c0d-119">The code is suitable for a Windows Presentation Foundation (WPF) app or Windows Store app that you create in Visual Studio; see the code comments for setting up the app.</span></span>

<span data-ttu-id="a5c0d-120">Этот код можно выполнить в Visual Studio как приложение Windows Presentation Foundation (WPF) или приложение Магазина Windows.</span><span class="sxs-lookup"><span data-stu-id="a5c0d-120">You can run this code in Visual Studio as a Windows Presentation Foundation (WPF) app or a Windows Store app.</span></span> <span data-ttu-id="a5c0d-121">Вам понадобятся элементы управления типа "Кнопка" (`StartButton`) и "Текстовое поле" (`ResultsTextBox`).</span><span class="sxs-lookup"><span data-stu-id="a5c0d-121">You need a Button control named `StartButton` and a Textbox control named `ResultsTextBox`.</span></span> <span data-ttu-id="a5c0d-122">Не забудьте задать имена и обработчик, чтобы получить код следующего вида:</span><span class="sxs-lookup"><span data-stu-id="a5c0d-122">Remember to set the names and handler so that you have something like this:</span></span>

```xaml
<Button Content="Button" HorizontalAlignment="Left" Margin="88,77,0,0" VerticalAlignment="Top" Width="75"
        Click="StartButton_Click" Name="StartButton"/>
<TextBox HorizontalAlignment="Left" Height="137" Margin="88,140,0,0" TextWrapping="Wrap"
         Text="&lt;Enter a URL&gt;" VerticalAlignment="Top" Width="310" Name="ResultsTextBox"/>
```

<span data-ttu-id="a5c0d-123">Выполнение кода в виде приложения WPF:</span><span class="sxs-lookup"><span data-stu-id="a5c0d-123">To run the code as a WPF app:</span></span>

- <span data-ttu-id="a5c0d-124">Вставьте этот код в класс `MainWindow` в MainWindow.xaml.cs.</span><span class="sxs-lookup"><span data-stu-id="a5c0d-124">Paste this code into the `MainWindow` class in MainWindow.xaml.cs.</span></span>
- <span data-ttu-id="a5c0d-125">Добавьте ссылку на System.Net.Http.</span><span class="sxs-lookup"><span data-stu-id="a5c0d-125">Add a reference to System.Net.Http.</span></span>
- <span data-ttu-id="a5c0d-126">Добавьте директиву `using` для System.Net.Http.</span><span class="sxs-lookup"><span data-stu-id="a5c0d-126">Add a `using` directive for System.Net.Http.</span></span>

<span data-ttu-id="a5c0d-127">Выполнение кода в виде приложения Магазина Windows:</span><span class="sxs-lookup"><span data-stu-id="a5c0d-127">To run the code as a Windows Store app:</span></span>

- <span data-ttu-id="a5c0d-128">Вставьте этот код в класс `MainPage` в MainPage.xaml.cs.</span><span class="sxs-lookup"><span data-stu-id="a5c0d-128">Paste this code into the `MainPage` class in MainPage.xaml.cs.</span></span>
- <span data-ttu-id="a5c0d-129">Добавьте директивы using для System.Net.Http и System.Threading.Tasks.</span><span class="sxs-lookup"><span data-stu-id="a5c0d-129">Add using directives for System.Net.Http and System.Threading.Tasks.</span></span>

[!code-csharp[wpf-async](../../../../samples/snippets/csharp/language-reference/keywords/async/wpf/mainwindow.xaml.cs#1)]

> [!IMPORTANT]
> <span data-ttu-id="a5c0d-130">Дополнительные сведения о задачах и коде, который выполняется во время ожидания задачи, см. в разделе [Асинхронное программирование с использованием ключевых слов async и await](../../programming-guide/concepts/async/index.md).</span><span class="sxs-lookup"><span data-stu-id="a5c0d-130">For more information about tasks and the code that executes while waiting for a task, see [Asynchronous programming with async and await](../../programming-guide/concepts/async/index.md).</span></span> <span data-ttu-id="a5c0d-131">Полный пример консоли, в котором используются похожие элементы, см. в разделе [Обработка асинхронных задач по мере их завершения (C#)](../../programming-guide/concepts/async/start-multiple-async-tasks-and-process-them-as-they-complete.md).</span><span class="sxs-lookup"><span data-stu-id="a5c0d-131">For a full console example that uses similar elements, see [Process asynchronous tasks as they complete (C#)](../../programming-guide/concepts/async/start-multiple-async-tasks-and-process-them-as-they-complete.md).</span></span>

## <a name="return-types"></a><span data-ttu-id="a5c0d-132">Типы возвращаемых значений</span><span class="sxs-lookup"><span data-stu-id="a5c0d-132">Return Types</span></span>
<span data-ttu-id="a5c0d-133">Асинхронные методы могут иметь следующие типы возвращаемых значений:</span><span class="sxs-lookup"><span data-stu-id="a5c0d-133">An async method can have the following return types:</span></span>

- <xref:System.Threading.Tasks.Task>
- <xref:System.Threading.Tasks.Task%601>
- <span data-ttu-id="a5c0d-134">[void](../builtin-types/void.md).</span><span class="sxs-lookup"><span data-stu-id="a5c0d-134">[void](../builtin-types/void.md).</span></span> <span data-ttu-id="a5c0d-135">Методы `async void` обычно рекомендуются для кода, отличного от обработчиков событий, поскольку вызывающие объекты не могут `await` эти методы и должны реализовать другой механизм уведомления об успешном завершении или ошибках.</span><span class="sxs-lookup"><span data-stu-id="a5c0d-135">`async void` methods are generally discouraged for code other than event handlers because callers cannot `await` those methods and must implement a different mechanism to report successful completion or error conditions.</span></span>
- <span data-ttu-id="a5c0d-136">Начиная с версии 7.0 в языке C# поддерживаются любые типы с доступным методом `GetAwaiter`.</span><span class="sxs-lookup"><span data-stu-id="a5c0d-136">Starting with C# 7.0, any type that has an accessible `GetAwaiter` method.</span></span> <span data-ttu-id="a5c0d-137">Одной из таких реализаций является тип `System.Threading.Tasks.ValueTask<TResult>`.</span><span class="sxs-lookup"><span data-stu-id="a5c0d-137">The `System.Threading.Tasks.ValueTask<TResult>` type is one such implementation.</span></span> <span data-ttu-id="a5c0d-138">Доступ к нему осуществляется посредством пакета NuGet `System.Threading.Tasks.Extensions`.</span><span class="sxs-lookup"><span data-stu-id="a5c0d-138">It is available by adding the NuGet package `System.Threading.Tasks.Extensions`.</span></span>

<span data-ttu-id="a5c0d-139">Асинхронный метод не может объявлять параметры [in](./in-parameter-modifier.md), [ref](./ref.md) или [out](./out-parameter-modifier.md), а также иметь [ссылочное возвращаемое значение](../../programming-guide/classes-and-structs/ref-returns.md), но он может вызывать методы с такими параметрами.</span><span class="sxs-lookup"><span data-stu-id="a5c0d-139">The async method can't declare any [in](./in-parameter-modifier.md), [ref](./ref.md) or [out](./out-parameter-modifier.md) parameters, nor can it have a [reference return value](../../programming-guide/classes-and-structs/ref-returns.md), but it can call methods that have such parameters.</span></span>

<span data-ttu-id="a5c0d-140">`Task<TResult>` указывается в качестве возвращаемого типа асинхронного метода, если оператор [return](./return.md) метода задает операнд типа `TResult`.</span><span class="sxs-lookup"><span data-stu-id="a5c0d-140">You specify `Task<TResult>` as the return type of an async method if the [return](./return.md) statement of the method specifies an operand of type `TResult`.</span></span> <span data-ttu-id="a5c0d-141">Класс `Task` используется при отсутствии содержательного значения, возвращаемого методом при его завершении.</span><span class="sxs-lookup"><span data-stu-id="a5c0d-141">You use `Task` if no meaningful value is returned when the method is completed.</span></span> <span data-ttu-id="a5c0d-142">То есть вызов метода возвращает `Task`, однако когда `Task` завершен, любое выражение `await`, которое ожидает `Task`, возвращает значение `void`.</span><span class="sxs-lookup"><span data-stu-id="a5c0d-142">That is, a call to the method returns a `Task`, but when the `Task` is completed, any `await` expression that's awaiting the `Task` evaluates to `void`.</span></span>

<span data-ttu-id="a5c0d-143">Возвращаемый тип `void` используется в основном для определения обработчиков событий, которые требуют этого возвращаемого типа.</span><span class="sxs-lookup"><span data-stu-id="a5c0d-143">You use the `void` return type primarily to define event handlers, which require that return type.</span></span> <span data-ttu-id="a5c0d-144">Вызывающий объект асинхронного метода, возвращающего `void`, не может ожидать его и перехватывать создаваемые методом исключения.</span><span class="sxs-lookup"><span data-stu-id="a5c0d-144">The caller of a `void`-returning async method can't await it and can't catch exceptions that the method throws.</span></span>

<span data-ttu-id="a5c0d-145">Начиная с версии C# 7.0, возвращается другой тип, обычно тип значения, с методом `GetAwaiter`, что позволяет свести к минимуму операции выделения памяти в разделах кода с критическими требованиями к производительности.</span><span class="sxs-lookup"><span data-stu-id="a5c0d-145">Starting with C# 7.0, you return another type, typically a value type, that has a `GetAwaiter` method to minimize memory allocations in performance-critical sections of code.</span></span>

<span data-ttu-id="a5c0d-146">Дополнительные сведения и примеры см. в разделе [Асинхронные типы возвращаемых значений](../../programming-guide/concepts/async/async-return-types.md).</span><span class="sxs-lookup"><span data-stu-id="a5c0d-146">For more information and examples, see [Async Return Types](../../programming-guide/concepts/async/async-return-types.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a5c0d-147">См. также</span><span class="sxs-lookup"><span data-stu-id="a5c0d-147">See also</span></span>

- <xref:System.Runtime.CompilerServices.AsyncStateMachineAttribute>
- [<span data-ttu-id="a5c0d-148">await</span><span class="sxs-lookup"><span data-stu-id="a5c0d-148">await</span></span>](../operators/await.md)
- [<span data-ttu-id="a5c0d-149">Асинхронное программирование с использованием ключевых слов async и await</span><span class="sxs-lookup"><span data-stu-id="a5c0d-149">Asynchronous programming with async and await</span></span>](../../programming-guide/concepts/async/index.md)
- [<span data-ttu-id="a5c0d-150">Обработка асинхронных задач по мере завершения</span><span class="sxs-lookup"><span data-stu-id="a5c0d-150">Process asynchronous tasks as they complete</span></span>](../../programming-guide/concepts/async/start-multiple-async-tasks-and-process-them-as-they-complete.md)
