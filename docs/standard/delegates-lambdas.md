---
title: Делегаты и лямбда-выражения
description: Сведения о том, как делегаты, которые определяют тип, указывающий конкретную сигнатуру метода, можно вызывать напрямую или передать другому методу и вызвать.
author: richlander
ms.author: wiwagn
ms.date: 06/20/2016
ms.technology: dotnet-standard
ms.assetid: fe2e4b4c-6483-4106-a4b4-a33e2e306591
ms.openlocfilehash: a9ca935814d1a7f77ded5f371ccd496c3859c523
ms.sourcegitcommit: 1c1a1f9ec0bd1efb3040d86a79f7ee94e207cca5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/03/2020
ms.locfileid: "80635929"
---
# <a name="delegates-and-lambdas"></a><span data-ttu-id="48ec8-103">Делегаты и лямбда-выражения</span><span class="sxs-lookup"><span data-stu-id="48ec8-103">Delegates and lambdas</span></span>

<span data-ttu-id="48ec8-104">Делегаты определяют тип, указывающий конкретную сигнатуру метода.</span><span class="sxs-lookup"><span data-stu-id="48ec8-104">Delegates define a type that specifies a particular method signature.</span></span> <span data-ttu-id="48ec8-105">Метод (статический или экземпляр), удовлетворяющий сигнатуре, можно присвоить переменной этого типа и затем вызвать напрямую (с соответствующими аргументами) или передать в качестве аргумента другому методу и затем вызвать.</span><span class="sxs-lookup"><span data-stu-id="48ec8-105">A method (static or instance) that satisfies this signature can be assigned to a variable of that type, then called directly (with the appropriate arguments) or passed as an argument itself to another method and then called.</span></span> <span data-ttu-id="48ec8-106">В следующем примере показано использование делегата.</span><span class="sxs-lookup"><span data-stu-id="48ec8-106">The following example demonstrates delegate use.</span></span>

```csharp
using System;
using System.Linq;

public class Program
{
    public delegate string Reverse(string s);

    static string ReverseString(string s)
    {
        return new string(s.Reverse().ToArray());
    }

    static void Main(string[] args)
    {
        Reverse rev = ReverseString;

        Console.WriteLine(rev("a string"));
    }
}
```

* <span data-ttu-id="48ec8-107">В строке `public delegate string Reverse(string s);` создается тип делегата для определенной сигнатуры. В данном случае это метод, принимающий и возвращающий строковый параметр.</span><span class="sxs-lookup"><span data-stu-id="48ec8-107">The `public delegate string Reverse(string s);` line creates a delegate type of a certain signature, in this case a method that takes a string parameter and then returns a string parameter.</span></span>
* <span data-ttu-id="48ec8-108">Метод `static string ReverseString(string s)`, имеющий такую же сигнатуру, как и определенный тип делегата, реализует этот делегат.</span><span class="sxs-lookup"><span data-stu-id="48ec8-108">The `static string ReverseString(string s)` method, which has the exact same signature as the defined delegate type, implements the delegate.</span></span>
* <span data-ttu-id="48ec8-109">Строка `Reverse rev = ReverseString;` показывает, что метод можно назначить переменной соответствующего типа делегата.</span><span class="sxs-lookup"><span data-stu-id="48ec8-109">The `Reverse rev = ReverseString;` line shows that you can assign a method to a variable of the corresponding delegate type.</span></span>
* <span data-ttu-id="48ec8-110">Строка `Console.WriteLine(rev("a string"));` показывает, как использовать переменную типа делегата для вызова этого делегата.</span><span class="sxs-lookup"><span data-stu-id="48ec8-110">The `Console.WriteLine(rev("a string"));` line demonstrates how to use a variable of a delegate type to invoke the delegate.</span></span>

<span data-ttu-id="48ec8-111">Чтобы упростить процесс разработки, платформа .NET содержит набор типов делегата, которые программисты могут повторно использовать, не создавая новые.</span><span class="sxs-lookup"><span data-stu-id="48ec8-111">In order to streamline the development process, .NET includes a set of delegate types that programmers can reuse and not have to create new types.</span></span> <span data-ttu-id="48ec8-112">Это типы `Func<>`, `Action<>` и `Predicate<>`, и их можно использовать без определения новых типов делегатов.</span><span class="sxs-lookup"><span data-stu-id="48ec8-112">These types are `Func<>`, `Action<>` and `Predicate<>`, and they can be used without having to define new delegate types.</span></span> <span data-ttu-id="48ec8-113">Между этими типами существуют некоторые различия, связанные с их назначением.</span><span class="sxs-lookup"><span data-stu-id="48ec8-113">There are some differences between the three types that have to do with the way they were intended to be used:</span></span>

* <span data-ttu-id="48ec8-114">`Action<>` применяется, когда требуется выполнить действие с использованием аргументов делегата.</span><span class="sxs-lookup"><span data-stu-id="48ec8-114">`Action<>` is used when there is a need to perform an action using the arguments of the delegate.</span></span> <span data-ttu-id="48ec8-115">Метод, который он инкапсулирует, не возвращает значение.</span><span class="sxs-lookup"><span data-stu-id="48ec8-115">The method it encapsulates does not return a value.</span></span>
* <span data-ttu-id="48ec8-116">`Func<>` обычно используется при наличии преобразования, то есть когда требуется преобразовать аргументы делегата в другой результат.</span><span class="sxs-lookup"><span data-stu-id="48ec8-116">`Func<>` is used usually when you have a transformation on hand, that is, you need to transform the arguments of the delegate into a different result.</span></span> <span data-ttu-id="48ec8-117">В качестве примера можно привести проекции.</span><span class="sxs-lookup"><span data-stu-id="48ec8-117">Projections are a good example.</span></span> <span data-ttu-id="48ec8-118">Метод, который он инкапсулирует, возвращает указанное значение.</span><span class="sxs-lookup"><span data-stu-id="48ec8-118">The method it encapsulates returns a specified value.</span></span>
* <span data-ttu-id="48ec8-119">`Predicate<>` используется, когда требуется определить, удовлетворяет ли аргумент условию делегата.</span><span class="sxs-lookup"><span data-stu-id="48ec8-119">`Predicate<>` is used when you need to determine if the argument satisfies the condition of the delegate.</span></span> <span data-ttu-id="48ec8-120">Он также может быть записан как `Func<T, bool>`, что означает, что метод возвращает логическое значение.</span><span class="sxs-lookup"><span data-stu-id="48ec8-120">It can also be written as a `Func<T, bool>`, which means the method returns a boolean value.</span></span>

<span data-ttu-id="48ec8-121">Теперь можно обратиться к приведенному выше примеру и переписать его, используя делегат `Func<>` вместо пользовательского типа.</span><span class="sxs-lookup"><span data-stu-id="48ec8-121">We can now take our example above and rewrite it using the `Func<>` delegate instead of a custom type.</span></span> <span data-ttu-id="48ec8-122">При этом работа программы не изменится.</span><span class="sxs-lookup"><span data-stu-id="48ec8-122">The program will continue running exactly the same.</span></span>

```csharp
using System;
using System.Linq;

public class Program
{
    static string ReverseString(string s)
    {
        return new string(s.Reverse().ToArray());
    }

    static void Main(string[] args)
    {
        Func<string, string> rev = ReverseString;

        Console.WriteLine(rev("a string"));
    }
}
```

<span data-ttu-id="48ec8-123">В этом простом примере определение метода за пределами метода `Main` может показаться излишним.</span><span class="sxs-lookup"><span data-stu-id="48ec8-123">For this simple example, having a method defined outside of the `Main` method seems a bit superfluous.</span></span> <span data-ttu-id="48ec8-124">В .NET Framework 2.0 введена концепция *анонимных делегатов*, с помощью которых можно создавать "встроенные" делегаты без указания дополнительного типа или метода.</span><span class="sxs-lookup"><span data-stu-id="48ec8-124">.NET Framework 2.0 introduced the concept of *anonymous delegates*, which let you create "inline" delegates without having to specify any additional type or method.</span></span>

<span data-ttu-id="48ec8-125">В следующем примере анонимный делегат отфильтровывает из списка только четные числа, а затем выводит их на консоль.</span><span class="sxs-lookup"><span data-stu-id="48ec8-125">In the following example, an anonymous delegate filters a list to just the even numbers and then prints them to the console.</span></span>

```csharp
using System;
using System.Collections.Generic;

public class Program
{
    public static void Main(string[] args)
    {
        List<int> list = new List<int>();

        for (int i = 1; i <= 100; i++)
        {
            list.Add(i);
        }

        List<int> result = list.FindAll(
          delegate (int no)
          {
              return (no % 2 == 0);
          }
        );

        foreach (var item in result)
        {
            Console.WriteLine(item);
        }
    }
}
```

<span data-ttu-id="48ec8-126">Как видно, тело делегата представляет собой набор выражений, как в любом другом делегате.</span><span class="sxs-lookup"><span data-stu-id="48ec8-126">As you can see, the body of the delegate is just a set of expressions, as any other delegate.</span></span> <span data-ttu-id="48ec8-127">Но вместо использования отдельного определения мы описали его _напрямую_ в нашем вызове метода <xref:System.Collections.Generic.List%601.FindAll%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="48ec8-127">But instead of it being a separate definition, we've introduced it _ad hoc_ in our call to the <xref:System.Collections.Generic.List%601.FindAll%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="48ec8-128">Однако даже при таком подходе остается довольно много кода, от которого можно избавиться.</span><span class="sxs-lookup"><span data-stu-id="48ec8-128">However, even with this approach, there is still much code that we can throw away.</span></span> <span data-ttu-id="48ec8-129">Как раз для этого и могут пригодиться *лямбда-выражения*.</span><span class="sxs-lookup"><span data-stu-id="48ec8-129">This is where *lambda expressions* come into play.</span></span> <span data-ttu-id="48ec8-130">Лямбда-выражения были введены в C# 3.0 в качестве одного из стандартных блоков LINQ.</span><span class="sxs-lookup"><span data-stu-id="48ec8-130">Lambda expressions, or just "lambdas" for short, were introduced in C# 3.0 as one of the core building blocks of Language Integrated Query (LINQ).</span></span> <span data-ttu-id="48ec8-131">Они предоставляют более удобный синтаксис для использования делегатов.</span><span class="sxs-lookup"><span data-stu-id="48ec8-131">They are just a more convenient syntax for using delegates.</span></span> <span data-ttu-id="48ec8-132">Они объявляют сигнатуру и тела метода, но не имеют собственного формального удостоверения, пока не будут назначены делегату.</span><span class="sxs-lookup"><span data-stu-id="48ec8-132">They declare a signature and a method body, but don't have a formal identity of their own, unless they are assigned to a delegate.</span></span> <span data-ttu-id="48ec8-133">В отличие от делегатов их можно напрямую назначать в левой части при регистрации событий, а также в различных предложениях и методах LINQ.</span><span class="sxs-lookup"><span data-stu-id="48ec8-133">Unlike delegates, they can be directly assigned as the left-hand side of event registration or in various LINQ clauses and methods.</span></span>

<span data-ttu-id="48ec8-134">Поскольку лямбда-выражение представляет собой просто еще один способ указания делегата, можно переписать приведенный выше пример, чтобы использовать лямбда-выражение вместо анонимного делегата.</span><span class="sxs-lookup"><span data-stu-id="48ec8-134">Since a lambda expression is just another way of specifying a delegate, we should be able to rewrite the above sample to use a lambda expression instead of an anonymous delegate.</span></span>

```csharp
using System;
using System.Collections.Generic;

public class Program
{
    public static void Main(string[] args)
    {
        List<int> list = new List<int>();

        for (int i = 1; i <= 100; i++)
        {
            list.Add(i);
        }

        List<int> result = list.FindAll(i => i % 2 == 0);

        foreach (var item in result)
        {
            Console.WriteLine(item);
        }
    }
}
```

<span data-ttu-id="48ec8-135">В предыдущем примере используется лямбда-выражение `i => i % 2 == 0`.</span><span class="sxs-lookup"><span data-stu-id="48ec8-135">In the preceding example, the lambda expression used is `i => i % 2 == 0`.</span></span> <span data-ttu-id="48ec8-136">Повторим, что это просто очень удобный синтаксис для использования делегатов.</span><span class="sxs-lookup"><span data-stu-id="48ec8-136">Again, it is just a convenient syntax for using delegates.</span></span> <span data-ttu-id="48ec8-137">Сам принцип действия аналогичен анонимному делегату.</span><span class="sxs-lookup"><span data-stu-id="48ec8-137">What happens under the covers is similar to what happens with the anonymous delegate.</span></span>

<span data-ttu-id="48ec8-138">Лямбда-выражения — это обычные делегаты, поэтому их без проблем можно использовать в качестве обработчика событий, как показано в следующем фрагменте кода.</span><span class="sxs-lookup"><span data-stu-id="48ec8-138">Again, lambdas are just delegates, which means that they can be used as an event handler without any problems, as the following code snippet illustrates.</span></span>

```csharp
public MainWindow()
{
    InitializeComponent();

    Loaded += (o, e) =>
    {
        this.Title = "Loaded";
    };
}
```

<span data-ttu-id="48ec8-139">В этом контексте оператор `+=` используется для подписки на [событие](../../docs/csharp/language-reference/keywords/event.md).</span><span class="sxs-lookup"><span data-stu-id="48ec8-139">The `+=` operator in this context is used to subscribe to an [event](../../docs/csharp/language-reference/keywords/event.md).</span></span> <span data-ttu-id="48ec8-140">Дополнительные сведения см. в разделе [Практическое руководство. Подписка и отмена подписки на события](../../docs/csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span><span class="sxs-lookup"><span data-stu-id="48ec8-140">For more information, see [How to subscribe to and unsubscribe from events](../../docs/csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>

## <a name="further-reading-and-resources"></a><span data-ttu-id="48ec8-141">Дополнительные сведения и ресурсы</span><span class="sxs-lookup"><span data-stu-id="48ec8-141">Further reading and resources</span></span>

* [<span data-ttu-id="48ec8-142">Делегаты</span><span class="sxs-lookup"><span data-stu-id="48ec8-142">Delegates</span></span>](../../docs/csharp/programming-guide/delegates/index.md)
* [<span data-ttu-id="48ec8-143">Анонимные функции</span><span class="sxs-lookup"><span data-stu-id="48ec8-143">Anonymous Functions</span></span>](../../docs/csharp/programming-guide/statements-expressions-operators/anonymous-functions.md)
* [<span data-ttu-id="48ec8-144">Лямбда-выражения</span><span class="sxs-lookup"><span data-stu-id="48ec8-144">Lambda expressions</span></span>](../../docs/csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)
