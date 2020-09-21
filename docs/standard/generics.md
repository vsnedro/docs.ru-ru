---
title: Обзор универсальных типов (универсальных шаблонов)
description: Сведения о том, как универсальные шаблоны действуют в качестве шаблона кода, позволяющего разработчикам определять типобезопасные структуры данных, не выполняя реальный тип данных.
author: kuhlenh
ms.author: wiwagn
ms.date: 10/09/2018
ms.openlocfilehash: 5f6e84e23b5bcdcb3dcd742823d83728fb43d195
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557948"
---
# <a name="generic-types-overview"></a><span data-ttu-id="41be4-103">Обзор универсальных типов</span><span class="sxs-lookup"><span data-stu-id="41be4-103">Generic types overview</span></span>

<span data-ttu-id="41be4-104">Каждый разработчик для .NET постоянно использует универсальные шаблоны, прямо или косвенно.</span><span class="sxs-lookup"><span data-stu-id="41be4-104">Developers use generics all the time in .NET, whether implicitly or explicitly.</span></span> <span data-ttu-id="41be4-105">Замечали ли вы, что используете <xref:System.Collections.Generic.IEnumerable%601> при работе с LINQ в C#?</span><span class="sxs-lookup"><span data-stu-id="41be4-105">When you use LINQ in .NET, did you ever notice that you're working with <xref:System.Collections.Generic.IEnumerable%601>?</span></span> <span data-ttu-id="41be4-106">Или, может быть, вы замечали, что большинство методов возвращает `IQueryable<T>` в примере "универсального репозитория" для обращения к базам данных через Entity Framework?</span><span class="sxs-lookup"><span data-stu-id="41be4-106">Or if you ever saw an online sample of a "generic repository" for talking to databases using Entity Framework, did you see that most methods return `IQueryable<T>`?</span></span> <span data-ttu-id="41be4-107">Возможно, вы задавались вопросом, что в этих примерах означает **T** и зачем это нужно.</span><span class="sxs-lookup"><span data-stu-id="41be4-107">You may have wondered what the **T** is in these examples and why it's in there.</span></span>

<span data-ttu-id="41be4-108">Универсальные шаблоны, которые появились в .NET Framework версии 2.0, представляют собой шаблон кода, позволяющий разработчикам определять [типобезопасные](/previous-versions/dotnet/netframework-4.0/hbzz1a9a(v=vs.100)) структуры данных, не привязываясь к конкретному типу данных.</span><span class="sxs-lookup"><span data-stu-id="41be4-108">First introduced in the .NET Framework 2.0, generics are essentially a "code template" that allows developers to define [type-safe](/previous-versions/dotnet/netframework-4.0/hbzz1a9a(v=vs.100)) data structures without committing to an actual data type.</span></span> <span data-ttu-id="41be4-109">Например, <xref:System.Collections.Generic.List%601> — это [универсальная коллекция](xref:System.Collections.Generic), которую можно объявить и использовать с любым типом, например `List<int>`, `List<string>`, `List<Person>` и т. д.</span><span class="sxs-lookup"><span data-stu-id="41be4-109">For example, <xref:System.Collections.Generic.List%601> is a [generic collection](xref:System.Collections.Generic) that can be declared and used with any type, such as `List<int>`, `List<string>`, or `List<Person>`.</span></span>

<span data-ttu-id="41be4-110">Чтобы понять, чем полезны универсальные шаблоны, давайте рассмотрим конкретный пример класса до и после добавления универсальных шаблонов: <xref:System.Collections.ArrayList>.</span><span class="sxs-lookup"><span data-stu-id="41be4-110">To understand why generics are useful, let's take a look at a specific class before and after adding generics: <xref:System.Collections.ArrayList>.</span></span> <span data-ttu-id="41be4-111">В .NET Framework 1.0 все элементы `ArrayList` имели тип <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="41be4-111">In .NET Framework 1.0, the `ArrayList` elements were of type <xref:System.Object>.</span></span> <span data-ttu-id="41be4-112">Любой добавленный в коллекцию элемент негласно преобразовывался в `Object`.</span><span class="sxs-lookup"><span data-stu-id="41be4-112">Any element added to the collection was silently converted into an `Object`.</span></span> <span data-ttu-id="41be4-113">То же самое происходило и при чтении элементов из списка.</span><span class="sxs-lookup"><span data-stu-id="41be4-113">The same would happen when reading elements from the list.</span></span> <span data-ttu-id="41be4-114">Эти процессы называются [упаковка-преобразование и распаковка-преобразование](../csharp/programming-guide/types/boxing-and-unboxing.md), и их использование ухудшает производительность.</span><span class="sxs-lookup"><span data-stu-id="41be4-114">This process is known as [boxing and unboxing](../csharp/programming-guide/types/boxing-and-unboxing.md), and it impacts performance.</span></span> <span data-ttu-id="41be4-115">Более того, отсутствует надежный способ определения типа данных в списке во время компиляции. Это приводит к созданию кода, который неудобно обслуживать.</span><span class="sxs-lookup"><span data-stu-id="41be4-115">Aside from performance, however, there's no way to determine the type of data in the list at compile time, which makes for some fragile code.</span></span> <span data-ttu-id="41be4-116">Универсальные шаблоны решают эту проблему, определяя тип данных для каждого экземпляра в списке.</span><span class="sxs-lookup"><span data-stu-id="41be4-116">Generics solve this problem by defining the type of data each instance of list will contain.</span></span> <span data-ttu-id="41be4-117">Например, вы можете указать, что `List<int>` всегда будет содержать целые числа, а `List<Person>` — объекты Person.</span><span class="sxs-lookup"><span data-stu-id="41be4-117">For example, you can only add integers to `List<int>` and only add Persons to `List<Person>`.</span></span>

<span data-ttu-id="41be4-118">Универсальные шаблоны также используются во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="41be4-118">Generics are also available at run time.</span></span> <span data-ttu-id="41be4-119">Среда выполнения знает, какой тип структуры вы используете, что позволяет эффективнее хранить ее в памяти.</span><span class="sxs-lookup"><span data-stu-id="41be4-119">The runtime knows what type of data structure you're using and can store it in memory more efficiently.</span></span>

<span data-ttu-id="41be4-120">В следующем примере приведена небольшая программа, которая демонстрирует преимущества понимания типов структуры данных во время выполнения:</span><span class="sxs-lookup"><span data-stu-id="41be4-120">The following example is a small program that illustrates the efficiency of knowing the data structure type at run time:</span></span>

```csharp
  using System;
  using System.Collections;
  using System.Collections.Generic;
  using System.Diagnostics;

  namespace GenericsExample {
    class Program {
      static void Main(string[] args) {
        //generic list
        List<int> ListGeneric = new List<int> { 5, 9, 1, 4 };
        //non-generic list
        ArrayList ListNonGeneric = new ArrayList { 5, 9, 1, 4 };
        // timer for generic list sort
        Stopwatch s = Stopwatch.StartNew();
        ListGeneric.Sort();
        s.Stop();
        Console.WriteLine($"Generic Sort: {ListGeneric}  \n Time taken: {s.Elapsed.TotalMilliseconds}ms");

        //timer for non-generic list sort
        Stopwatch s2 = Stopwatch.StartNew();
        ListNonGeneric.Sort();
        s2.Stop();
        Console.WriteLine($"Non-Generic Sort: {ListNonGeneric}  \n Time taken: {s2.Elapsed.TotalMilliseconds}ms");
        Console.ReadLine();
      }
    }
  }
```

<span data-ttu-id="41be4-121">Эта программа возвращает приблизительно следующее:</span><span class="sxs-lookup"><span data-stu-id="41be4-121">This program produces output similar to the following:</span></span>

```console
Generic Sort: System.Collections.Generic.List`1[System.Int32]
 Time taken: 0.0034ms
Non-Generic Sort: System.Collections.ArrayList
 Time taken: 0.2592ms
```

<span data-ttu-id="41be4-122">Первое, что можно заметить, — сортировка списка с универсальным шаблоном осуществляется значительно быстрее, чем без него.</span><span class="sxs-lookup"><span data-stu-id="41be4-122">The first thing you can notice here is that sorting the generic list is significantly faster than sorting the non-generic list.</span></span> <span data-ttu-id="41be4-123">Также видно, что для списка с универсальным шаблоном указан конкретный тип ([System.Int32]), а обычный список остается обобщенным.</span><span class="sxs-lookup"><span data-stu-id="41be4-123">You might also notice that the type for the generic list is distinct ([System.Int32]), whereas the type for the non-generic list is generalized.</span></span> <span data-ttu-id="41be4-124">Так как среда выполнения знает, что `List<int>` с универсальным шаблоном имеет тип <xref:System.Int32>, она может применить целочисленный массив для хранения элементов списка в памяти. В то же время для `ArrayList` без универсального списка нужно приводить все элементы к объекту.</span><span class="sxs-lookup"><span data-stu-id="41be4-124">Because the runtime knows the generic `List<int>` is of type <xref:System.Int32>, it can store the list elements in an underlying integer array in memory, while the non-generic `ArrayList` has to cast each list element to an object.</span></span> <span data-ttu-id="41be4-125">Как вы видите этом примере, дополнительные приведения занимают время и замедляют сортировку списка.</span><span class="sxs-lookup"><span data-stu-id="41be4-125">As this example shows, the extra casts take up time and slow down the list sort.</span></span>

<span data-ttu-id="41be4-126">Еще одно преимущество понимания типа универсального шаблона заключается в упрощении отладки.</span><span class="sxs-lookup"><span data-stu-id="41be4-126">An additional advantage of the runtime knowing the type of your generic is a better debugging experience.</span></span> <span data-ttu-id="41be4-127">При отладке универсального шаблона в C# вы заранее знаете тип каждого элемента в структуре данных.</span><span class="sxs-lookup"><span data-stu-id="41be4-127">When you're debugging a generic in C#, you know what type each element is in your data structure.</span></span> <span data-ttu-id="41be4-128">Без универсальных шаблонов вы бы не имели об этом никакого понятия.</span><span class="sxs-lookup"><span data-stu-id="41be4-128">Without generics, you would have no idea what type each element was.</span></span>

## <a name="see-also"></a><span data-ttu-id="41be4-129">См. также</span><span class="sxs-lookup"><span data-stu-id="41be4-129">See also</span></span>

- [<span data-ttu-id="41be4-130">Руководство по программированию на C# — универсальные шаблоны</span><span class="sxs-lookup"><span data-stu-id="41be4-130">C# Programming Guide - Generics</span></span>](../csharp/programming-guide/generics/index.md)
