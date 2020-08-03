---
title: Руководство по программированию на C#. Конструкторы
description: Конструктор в C# вызывается при создании класса или структуры. Используйте конструкторы для установки значений по умолчанию, ограничения числа создаваемых экземпляров и написания гибкого и удобного для чтения кода.
ms.date: 05/05/2017
helpviewer_keywords:
- constructors [C#]
- classes [C#], constructors
- C# language, constructors
ms.assetid: df2e2e9d-7998-418b-8e7d-890c17ff6c95
ms.openlocfilehash: 4a731e648143f5e0ecf8860625962d8baa29fe26
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/20/2020
ms.locfileid: "86474908"
---
# <a name="constructors-c-programming-guide"></a><span data-ttu-id="b44f5-104">Конструкторы (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="b44f5-104">Constructors (C# Programming Guide)</span></span>

<span data-ttu-id="b44f5-105">Каждый раз, когда создается [класс](../../language-reference/keywords/class.md) или [структура](../../language-reference/builtin-types/struct.md), вызывается конструктор.</span><span class="sxs-lookup"><span data-stu-id="b44f5-105">Whenever a [class](../../language-reference/keywords/class.md) or [struct](../../language-reference/builtin-types/struct.md) is created, its constructor is called.</span></span> <span data-ttu-id="b44f5-106">Класс или структура может иметь несколько конструкторов, принимающих различные аргументы.</span><span class="sxs-lookup"><span data-stu-id="b44f5-106">A class or struct may have multiple constructors that take different arguments.</span></span> <span data-ttu-id="b44f5-107">Конструкторы позволяют программисту задавать значения по умолчанию, ограничивать число установок и писать код, который является гибким и удобным для чтения.</span><span class="sxs-lookup"><span data-stu-id="b44f5-107">Constructors enable the programmer to set default values, limit instantiation, and write code that is flexible and easy to read.</span></span> <span data-ttu-id="b44f5-108">Дополнительные сведения и примеры см. в разделах [Использование конструкторов](./using-constructors.md) и [Конструкторы экземпляров](./instance-constructors.md).</span><span class="sxs-lookup"><span data-stu-id="b44f5-108">For more information and examples, see [Using Constructors](./using-constructors.md) and [Instance Constructors](./instance-constructors.md).</span></span>  

## <a name="parameterless-constructors"></a><span data-ttu-id="b44f5-109">Конструкторы без параметров</span><span class="sxs-lookup"><span data-stu-id="b44f5-109">Parameterless constructors</span></span>
  
<span data-ttu-id="b44f5-110">Если не предоставить конструктор для класса, C# создаст конструктор по умолчанию, который создает экземпляр объекта и задает переменным-членам значения по умолчанию, как показано в статье [Значения по умолчанию типов C#](../../language-reference/builtin-types/default-values.md).</span><span class="sxs-lookup"><span data-stu-id="b44f5-110">If you don't provide a constructor for your class, C# creates one by default that instantiates the object and sets member variables to the default values as listed in the [Default values of C# types](../../language-reference/builtin-types/default-values.md) article.</span></span> <span data-ttu-id="b44f5-111">Если не предоставить конструктор для структуры, C# будет использовать *неявный конструктор без параметров*, чтобы автоматически инициализировать каждое поле значением по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b44f5-111">If you don't provide a constructor for your struct, C# relies on an *implicit parameterless constructor* to automatically initialize each field to its default value.</span></span> <span data-ttu-id="b44f5-112">Дополнительные сведения и примеры см. в разделе [Конструкторы экземпляров](instance-constructors.md).</span><span class="sxs-lookup"><span data-stu-id="b44f5-112">For more information and examples, see [Instance constructors](instance-constructors.md).</span></span>  

## <a name="constructor-syntax"></a><span data-ttu-id="b44f5-113">Синтаксис конструктора</span><span class="sxs-lookup"><span data-stu-id="b44f5-113">Constructor syntax</span></span>

<span data-ttu-id="b44f5-114">Конструктор — это метод, имя которого совпадает с именем его типа.</span><span class="sxs-lookup"><span data-stu-id="b44f5-114">A constructor is a method whose name is the same as the name of its type.</span></span> <span data-ttu-id="b44f5-115">Его сигнатура метода содержит только имя метода и список параметров. Она не содержит возвращаемый тип.</span><span class="sxs-lookup"><span data-stu-id="b44f5-115">Its method signature includes only the method name and its parameter list; it does not include a return type.</span></span> <span data-ttu-id="b44f5-116">В приведенном ниже примере демонстрируется конструктор для класса с именем `Person`.</span><span class="sxs-lookup"><span data-stu-id="b44f5-116">The following example shows the constructor for a class named `Person`.</span></span>

[!code-csharp[constructors](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#1)]  

<span data-ttu-id="b44f5-117">Если конструктор поддерживает реализацию в виде оператора, можно использовать [определение тела выражения](../statements-expressions-operators/expression-bodied-members.md).</span><span class="sxs-lookup"><span data-stu-id="b44f5-117">If a constructor can be implemented as a single statement, you can use an [expression body definition](../statements-expressions-operators/expression-bodied-members.md).</span></span> <span data-ttu-id="b44f5-118">В следующем примере определяется класс `Location`, конструктор которого имеет один строковый параметр *name*.</span><span class="sxs-lookup"><span data-stu-id="b44f5-118">The following example defines a `Location` class whose constructor has a single string parameter named *name*.</span></span> <span data-ttu-id="b44f5-119">Определение тела выражения присваивает аргумент полю `locationName`.</span><span class="sxs-lookup"><span data-stu-id="b44f5-119">The expression body definition assigns the argument to the `locationName` field.</span></span>

[!code-csharp[expression-bodied-constructor](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]  

## <a name="static-constructors"></a><span data-ttu-id="b44f5-120">Статические конструкторы</span><span class="sxs-lookup"><span data-stu-id="b44f5-120">Static constructors</span></span>

<span data-ttu-id="b44f5-121">В приведенных выше примерах показаны конструкторы экземпляров, которые создают новый объект.</span><span class="sxs-lookup"><span data-stu-id="b44f5-121">The previous examples have all shown instance constructors, which create a new object.</span></span> <span data-ttu-id="b44f5-122">В классе или структуре также может быть статический конструктор, который инициализирует статические члены типа.</span><span class="sxs-lookup"><span data-stu-id="b44f5-122">A class or struct can also have a static constructor, which initializes static members of the type.</span></span>  <span data-ttu-id="b44f5-123">Статические конструкторы не имеют параметров.</span><span class="sxs-lookup"><span data-stu-id="b44f5-123">Static constructors are parameterless.</span></span> <span data-ttu-id="b44f5-124">Если вы не предоставили статический конструктор для инициализации статических полей, компилятор C# инициализирует статические поля значениями по умолчанию, как показано в статье [Значения по умолчанию типов C#](../../language-reference/builtin-types/default-values.md).</span><span class="sxs-lookup"><span data-stu-id="b44f5-124">If you don't provide a static constructor to initialize static fields, the C# compiler initializes static fields to their default value as listed in the [Default values of C# types](../../language-reference/builtin-types/default-values.md) article.</span></span>

<span data-ttu-id="b44f5-125">В следующем примере статический конструктор используется для инициализации статического поля.</span><span class="sxs-lookup"><span data-stu-id="b44f5-125">The following example uses a static constructor to initialize a static field.</span></span>

[!code-csharp[constructors](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#2)]  

<span data-ttu-id="b44f5-126">Можно также определить статический конструктор с помощью определения тела выражения, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="b44f5-126">You can also define a static constructor with an expression body definition, as the following example shows.</span></span>

[!code-csharp[constructors](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#3)]  

<span data-ttu-id="b44f5-127">Дополнительные сведения и примеры см. в разделе [Статические конструкторы](./static-constructors.md).</span><span class="sxs-lookup"><span data-stu-id="b44f5-127">For more information and examples, see [Static Constructors](./static-constructors.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b44f5-128">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="b44f5-128">In This Section</span></span>  
 [<span data-ttu-id="b44f5-129">Использование конструкторов</span><span class="sxs-lookup"><span data-stu-id="b44f5-129">Using Constructors</span></span>](./using-constructors.md)  
  
 [<span data-ttu-id="b44f5-130">Конструкторы экземпляров</span><span class="sxs-lookup"><span data-stu-id="b44f5-130">Instance Constructors</span></span>](./instance-constructors.md)  
  
 [<span data-ttu-id="b44f5-131">Закрытые конструкторы</span><span class="sxs-lookup"><span data-stu-id="b44f5-131">Private Constructors</span></span>](./private-constructors.md)  
  
 [<span data-ttu-id="b44f5-132">Статические конструкторы</span><span class="sxs-lookup"><span data-stu-id="b44f5-132">Static Constructors</span></span>](./static-constructors.md)  
  
 [<span data-ttu-id="b44f5-133">Практическое руководство. Создание конструктора копий</span><span class="sxs-lookup"><span data-stu-id="b44f5-133">How to write a copy constructor</span></span>](./how-to-write-a-copy-constructor.md)  
  
## <a name="see-also"></a><span data-ttu-id="b44f5-134">См. также</span><span class="sxs-lookup"><span data-stu-id="b44f5-134">See also</span></span>

- [<span data-ttu-id="b44f5-135">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="b44f5-135">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="b44f5-136">Классы и структуры</span><span class="sxs-lookup"><span data-stu-id="b44f5-136">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="b44f5-137">Методы завершения</span><span class="sxs-lookup"><span data-stu-id="b44f5-137">Finalizers</span></span>](./destructors.md)
- [<span data-ttu-id="b44f5-138">static</span><span class="sxs-lookup"><span data-stu-id="b44f5-138">static</span></span>](../../language-reference/keywords/static.md)
- <span data-ttu-id="b44f5-139">[Why Do Initializers Run In The Opposite Order As Constructors? Part One](https://docs.microsoft.com/archive/blogs/ericlippert/why-do-initializers-run-in-the-opposite-order-as-constructors-part-one) (Почему инициализаторы выполняются в порядке, обратном действию конструкторов? Часть 1)</span><span class="sxs-lookup"><span data-stu-id="b44f5-139">[Why Do Initializers Run In The Opposite Order As Constructors? Part One](https://docs.microsoft.com/archive/blogs/ericlippert/why-do-initializers-run-in-the-opposite-order-as-constructors-part-one)</span></span>
