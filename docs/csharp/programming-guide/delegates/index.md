---
title: Руководство по программированию на C#. Делегаты
description: Делегат в C# — это тип, который представляет ссылки на методы со списком параметров и типом возвращаемого значения. Делегаты используются для передачи методов в качестве аргументов к другим методам.
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, delegates
- delegates [C#]
ms.assetid: 97de039b-c76b-4b9c-a27d-8c1e1c8d93da
ms.openlocfilehash: 7365cb89ad617148fb26d5a01c07f13a7888bbf8
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91178701"
---
# <a name="delegates-c-programming-guide"></a><span data-ttu-id="7fe98-104">Делегаты (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="7fe98-104">Delegates (C# Programming Guide)</span></span>

<span data-ttu-id="7fe98-105">[Делегат](../../language-reference/builtin-types/reference-types.md) — это тип, который представляет ссылки на методы с определенным списком параметров и типом возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="7fe98-105">A [delegate](../../language-reference/builtin-types/reference-types.md) is a type that represents references to methods with a particular parameter list and return type.</span></span> <span data-ttu-id="7fe98-106">При создании экземпляра делегата этот экземпляр можно связать с любым методом с совместимой сигнатурой и типом возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="7fe98-106">When you instantiate a delegate, you can associate its instance with any method with a compatible signature and return type.</span></span> <span data-ttu-id="7fe98-107">Метод можно вызвать (активировать) с помощью экземпляра делегата.</span><span class="sxs-lookup"><span data-stu-id="7fe98-107">You can invoke (or call) the method through the delegate instance.</span></span>  
  
 <span data-ttu-id="7fe98-108">Делегаты используются для передачи методов в качестве аргументов к другим методам.</span><span class="sxs-lookup"><span data-stu-id="7fe98-108">Delegates are used to pass methods as arguments to other methods.</span></span> <span data-ttu-id="7fe98-109">Обработчики событий — это ничто иное, как методы, вызываемые с помощью делегатов.</span><span class="sxs-lookup"><span data-stu-id="7fe98-109">Event handlers are nothing more than methods that are invoked through delegates.</span></span> <span data-ttu-id="7fe98-110">При создании пользовательского метода класс (например, элемент управления Windows) может вызывать этот метод при появлении определенного события.</span><span class="sxs-lookup"><span data-stu-id="7fe98-110">You create a custom method, and a class such as a windows control can call your method when a certain event occurs.</span></span> <span data-ttu-id="7fe98-111">В следующем примере показано объявление делегата:</span><span class="sxs-lookup"><span data-stu-id="7fe98-111">The following example shows a delegate declaration:</span></span>  
  
 [!code-csharp[csProgGuideDelegates#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#20)]  
  
 <span data-ttu-id="7fe98-112">Делегату можно назначить любой метод из любого доступного класса или структуры, соответствующей типу делегата.</span><span class="sxs-lookup"><span data-stu-id="7fe98-112">Any method from any accessible class or struct that matches the delegate type can be assigned to the delegate.</span></span> <span data-ttu-id="7fe98-113">Этот метод должен быть статическим методом или методом экземпляра.</span><span class="sxs-lookup"><span data-stu-id="7fe98-113">The method can be either static or an instance method.</span></span> <span data-ttu-id="7fe98-114">Это позволяет программно изменять вызовы метода, а также включать новый код в существующие классы.</span><span class="sxs-lookup"><span data-stu-id="7fe98-114">This makes it possible to programmatically change method calls, and also plug new code into existing classes.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7fe98-115">В контексте перегрузки метода его сигнатура не содержит возвращаемое значение.</span><span class="sxs-lookup"><span data-stu-id="7fe98-115">In the context of method overloading, the signature of a method does not include the return value.</span></span> <span data-ttu-id="7fe98-116">Однако в контексте делегатов сигнатура метода содержит возвращаемое значение.</span><span class="sxs-lookup"><span data-stu-id="7fe98-116">But in the context of delegates, the signature does include the return value.</span></span> <span data-ttu-id="7fe98-117">Другими словами, метод должен иметь тот же возвращаемый тип, что и делегат.</span><span class="sxs-lookup"><span data-stu-id="7fe98-117">In other words, a method must have the same return type as the delegate.</span></span>  
  
 <span data-ttu-id="7fe98-118">Благодаря возможности ссылаться на метод как на параметр делегаты идеально подходят для определения методов обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="7fe98-118">This ability to refer to a method as a parameter makes delegates ideal for defining callback methods.</span></span> <span data-ttu-id="7fe98-119">Например, ссылка на метод, сравнивающий два объекта, может быть передана в качестве аргумента алгоритму сортировки.</span><span class="sxs-lookup"><span data-stu-id="7fe98-119">For example, a reference to a method that compares two objects could be passed as an argument to a sort algorithm.</span></span> <span data-ttu-id="7fe98-120">Поскольку код сравнения находится в отдельной процедуре, алгоритм сортировки может быть написан более общим способом.</span><span class="sxs-lookup"><span data-stu-id="7fe98-120">Because the comparison code is in a separate procedure, the sort algorithm can be written in a more general way.</span></span>  
  
## <a name="delegates-overview"></a><span data-ttu-id="7fe98-121">Общие сведения о делегатах</span><span class="sxs-lookup"><span data-stu-id="7fe98-121">Delegates Overview</span></span>  

 <span data-ttu-id="7fe98-122">Делегаты имеют следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="7fe98-122">Delegates have the following properties:</span></span>  
  
- <span data-ttu-id="7fe98-123">Делегаты подобны указателям на функции в C++, но являются полностью объектно-ориентированными и, в отличие от указателей C++ на функции-члены, инкапсулируют экземпляр объекта вместе с методом.</span><span class="sxs-lookup"><span data-stu-id="7fe98-123">Delegates are similar to C++ function pointers, but delegates are fully object-oriented, and unlike C++ pointers to member functions, delegates encapsulate both an object instance and a method.</span></span>
  
- <span data-ttu-id="7fe98-124">Делегаты допускают передачу методов в качестве параметров.</span><span class="sxs-lookup"><span data-stu-id="7fe98-124">Delegates allow methods to be passed as parameters.</span></span>  
  
- <span data-ttu-id="7fe98-125">Делегаты можно использовать для определения методов обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="7fe98-125">Delegates can be used to define callback methods.</span></span>  
  
- <span data-ttu-id="7fe98-126">Делегаты можно связывать друг с другом; например, при появлении одного события можно вызывать несколько методов.</span><span class="sxs-lookup"><span data-stu-id="7fe98-126">Delegates can be chained together; for example, multiple methods can be called on a single event.</span></span>  
  
- <span data-ttu-id="7fe98-127">Точное соответствие методов типу делегата не требуется.</span><span class="sxs-lookup"><span data-stu-id="7fe98-127">Methods do not have to match the delegate type exactly.</span></span> <span data-ttu-id="7fe98-128">Дополнительные сведения см. в разделе [Использование вариативности в делегатах](../concepts/covariance-contravariance/using-variance-in-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="7fe98-128">For more information, see [Using Variance in Delegates](../concepts/covariance-contravariance/using-variance-in-delegates.md).</span></span>  
  
- <span data-ttu-id="7fe98-129">В C# версии 2.0 введена концепция [анонимных методов](../../language-reference/operators/delegate-operator.md), которые позволяют передавать блоки кода в виде параметров вместо использования отдельно определенного метода.</span><span class="sxs-lookup"><span data-stu-id="7fe98-129">C# version 2.0 introduced the concept of [anonymous methods](../../language-reference/operators/delegate-operator.md), which allow code blocks to be passed as parameters in place of a separately defined method.</span></span> <span data-ttu-id="7fe98-130">В C# 3.0 для краткой записи встроенных блоков кода введены лямбда-выражения.</span><span class="sxs-lookup"><span data-stu-id="7fe98-130">C# 3.0 introduced lambda expressions as a more concise way of writing inline code blocks.</span></span> <span data-ttu-id="7fe98-131">В результате компиляции как анонимных методов, так и лямбда-выражений (в определенном контексте) получаются типы делегатов.</span><span class="sxs-lookup"><span data-stu-id="7fe98-131">Both anonymous methods and lambda expressions (in certain contexts) are compiled to delegate types.</span></span> <span data-ttu-id="7fe98-132">В настоящее время эти возможности называются анонимными возможностями.</span><span class="sxs-lookup"><span data-stu-id="7fe98-132">Together, these features are now known as anonymous functions.</span></span> <span data-ttu-id="7fe98-133">Дополнительные сведения о лямбда-выражениях см. в разделе [Лямбда-выражения](../../language-reference/operators/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="7fe98-133">For more information about lambda expressions, see [Lambda expressions](../../language-reference/operators/lambda-expressions.md).</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="7fe98-134">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="7fe98-134">In This Section</span></span>  
  
- [<span data-ttu-id="7fe98-135">Использование делегатов</span><span class="sxs-lookup"><span data-stu-id="7fe98-135">Using Delegates</span></span>](./using-delegates.md)  
  
- <span data-ttu-id="7fe98-136">[Использование делегатов вместо интерфейсов (руководство по программированию на C#)](/previous-versions/visualstudio/visual-studio-2010/ms173173(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="7fe98-136">[When to Use Delegates Instead of Interfaces (C# Programming Guide)](/previous-versions/visualstudio/visual-studio-2010/ms173173(v=vs.100))</span></span>  
  
- [<span data-ttu-id="7fe98-137">Делегаты с именованными методами и делегаты с анонимными методами</span><span class="sxs-lookup"><span data-stu-id="7fe98-137">Delegates with Named vs. Anonymous Methods</span></span>](./delegates-with-named-vs-anonymous-methods.md)  
  
- [<span data-ttu-id="7fe98-138">Использование расхождения в делегатах</span><span class="sxs-lookup"><span data-stu-id="7fe98-138">Using Variance in Delegates</span></span>](../concepts/covariance-contravariance/using-variance-in-delegates.md)  
  
- [<span data-ttu-id="7fe98-139">Практическое руководство. Объединение делегатов (многоадресные делегаты)</span><span class="sxs-lookup"><span data-stu-id="7fe98-139">How to combine delegates (Multicast Delegates)</span></span>](./how-to-combine-delegates-multicast-delegates.md)  
  
- [<span data-ttu-id="7fe98-140">Практическое руководство. Объявление, создание и использование делегата</span><span class="sxs-lookup"><span data-stu-id="7fe98-140">How to declare, instantiate, and use a delegate</span></span>](./how-to-declare-instantiate-and-use-a-delegate.md)

## <a name="c-language-specification"></a><span data-ttu-id="7fe98-141">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="7fe98-141">C# Language Specification</span></span>  

<span data-ttu-id="7fe98-142">Дополнительные сведения см. в разделе [Делегаты](~/_csharplang/spec/delegates.md) в [Спецификации языка C#](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="7fe98-142">For more information, see [Delegates](~/_csharplang/spec/delegates.md) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="7fe98-143">Спецификация языка является предписывающим источником информации о синтаксисе и использовании языка C#.</span><span class="sxs-lookup"><span data-stu-id="7fe98-143">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="featured-book-chapters"></a><span data-ttu-id="7fe98-144">Главы в популярных книгах</span><span class="sxs-lookup"><span data-stu-id="7fe98-144">Featured Book Chapters</span></span>  

 <span data-ttu-id="7fe98-145">[Делегаты, события и лямбда-выражения](/previous-versions/visualstudio/visual-studio-2008/ff518994(v=orm.10)) в [справочном руководстве по C# 3.0, третье издание. Более 250 решений для программистов на C# 3.0](/previous-versions/visualstudio/visual-studio-2008/ff518995(v=orm.10))</span><span class="sxs-lookup"><span data-stu-id="7fe98-145">[Delegates, Events, and Lambda Expressions](/previous-versions/visualstudio/visual-studio-2008/ff518994(v=orm.10)) in [C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers](/previous-versions/visualstudio/visual-studio-2008/ff518995(v=orm.10))</span></span>  
  
 <span data-ttu-id="7fe98-146">[Делегаты и события](/previous-versions/visualstudio/visual-studio-2008/ff652490(v=orm.10)) в [изучении C# 3.0. Овладение основными понятиями C# 3.0](/previous-versions/visualstudio/visual-studio-2008/ff652493(v=orm.10))</span><span class="sxs-lookup"><span data-stu-id="7fe98-146">[Delegates and Events](/previous-versions/visualstudio/visual-studio-2008/ff652490(v=orm.10)) in [Learning C# 3.0: Master the fundamentals of C# 3.0](/previous-versions/visualstudio/visual-studio-2008/ff652493(v=orm.10))</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fe98-147">См. также</span><span class="sxs-lookup"><span data-stu-id="7fe98-147">See also</span></span>

- <xref:System.Delegate>
- [<span data-ttu-id="7fe98-148">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="7fe98-148">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="7fe98-149">События</span><span class="sxs-lookup"><span data-stu-id="7fe98-149">Events</span></span>](../events/index.md)
