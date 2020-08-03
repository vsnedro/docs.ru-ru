---
title: Коллекции (C#)
description: Узнайте о коллекциях в C#, которые используются для работы с группами объектов. Коллекции могут увеличиваться и сжиматься динамически при изменении потребностей приложения.
ms.date: 07/20/2015
ms.assetid: 317d7dc3-8587-4873-8b3e-556f86497939
ms.openlocfilehash: 2375980e2915d4daa5a221a94eee2aea41959852
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/22/2020
ms.locfileid: "86924933"
---
# <a name="collections-c"></a><span data-ttu-id="69d2d-104">Коллекции (C#)</span><span class="sxs-lookup"><span data-stu-id="69d2d-104">Collections (C#)</span></span>

<span data-ttu-id="69d2d-105">Во многих приложениях требуется создавать группы связанных объектов и управлять ими.</span><span class="sxs-lookup"><span data-stu-id="69d2d-105">For many applications, you want to create and manage groups of related objects.</span></span> <span data-ttu-id="69d2d-106">Существует два способа группировки объектов: создать массив объектов и создать коллекцию.</span><span class="sxs-lookup"><span data-stu-id="69d2d-106">There are two ways to group objects: by creating arrays of objects, and by creating collections of objects.</span></span>

<span data-ttu-id="69d2d-107">Массивы удобнее всего использовать для создания фиксированного числа строго типизированных объектов и работы с ними.</span><span class="sxs-lookup"><span data-stu-id="69d2d-107">Arrays are most useful for creating and working with a fixed number of strongly typed objects.</span></span> <span data-ttu-id="69d2d-108">Информацию о массивах см. в разделе [Массивы](../arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="69d2d-108">For information about arrays, see [Arrays](../arrays/index.md).</span></span>

<span data-ttu-id="69d2d-109">Коллекции предоставляют более гибкий способ работы с группами объектов.</span><span class="sxs-lookup"><span data-stu-id="69d2d-109">Collections provide a more flexible way to work with groups of objects.</span></span> <span data-ttu-id="69d2d-110">В отличие от массивов, коллекция, с которой вы работаете, может расти или уменьшаться динамически при необходимости.</span><span class="sxs-lookup"><span data-stu-id="69d2d-110">Unlike arrays, the group of objects you work with can grow and shrink dynamically as the needs of the application change.</span></span> <span data-ttu-id="69d2d-111">Некоторые коллекции допускают назначение ключа любому объекту, который добавляется в коллекцию, чтобы в дальнейшем можно было быстро извлечь связанный с ключом объект из коллекции.</span><span class="sxs-lookup"><span data-stu-id="69d2d-111">For some collections, you can assign a key to any object that you put into the collection so that you can quickly retrieve the object by using the key.</span></span>

<span data-ttu-id="69d2d-112">Коллекция является классом, поэтому необходимо объявить экземпляр класса перед добавлением в коллекцию элементов.</span><span class="sxs-lookup"><span data-stu-id="69d2d-112">A collection is a class, so you must declare an instance of the class before you can add elements to that collection.</span></span>

<span data-ttu-id="69d2d-113">Если коллекция содержит элементы только одного типа данных, можно использовать один из классов в пространстве имен <xref:System.Collections.Generic?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="69d2d-113">If your collection contains elements of only one data type, you can use one of the classes in the <xref:System.Collections.Generic?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="69d2d-114">Универсальная коллекция обеспечивает строгую типизацию, так что в нее нельзя добавить другие типы данных.</span><span class="sxs-lookup"><span data-stu-id="69d2d-114">A generic collection enforces type safety so that no other data type can be added to it.</span></span> <span data-ttu-id="69d2d-115">При извлечении элемента из универсальной коллекции не нужно определять или преобразовывать его тип данных.</span><span class="sxs-lookup"><span data-stu-id="69d2d-115">When you retrieve an element from a generic collection, you do not have to determine its data type or convert it.</span></span>

> [!NOTE]
> <span data-ttu-id="69d2d-116">Для примеров в этом разделе включите директивы [using](../../language-reference/keywords/using-directive.md) для пространств имен `System.Collections.Generic` и `System.Linq`.</span><span class="sxs-lookup"><span data-stu-id="69d2d-116">For the examples in this topic, include [using](../../language-reference/keywords/using-directive.md) directives for the `System.Collections.Generic` and `System.Linq` namespaces.</span></span>

 <span data-ttu-id="69d2d-117">**Содержание раздела**</span><span class="sxs-lookup"><span data-stu-id="69d2d-117">**In this topic**</span></span>

- [<span data-ttu-id="69d2d-118">Использование простой коллекции</span><span class="sxs-lookup"><span data-stu-id="69d2d-118">Using a Simple Collection</span></span>](#BKMK_SimpleCollection)

- [<span data-ttu-id="69d2d-119">Виды коллекций</span><span class="sxs-lookup"><span data-stu-id="69d2d-119">Kinds of Collections</span></span>](#BKMK_KindsOfCollections)

  - [<span data-ttu-id="69d2d-120">Классы System.Collections.Generic</span><span class="sxs-lookup"><span data-stu-id="69d2d-120">System.Collections.Generic Classes</span></span>](#BKMK_Generic)

  - [<span data-ttu-id="69d2d-121">Классы System.Collections.Concurrent</span><span class="sxs-lookup"><span data-stu-id="69d2d-121">System.Collections.Concurrent Classes</span></span>](#BKMK_Concurrent)

  - [<span data-ttu-id="69d2d-122">Классы System.Collections</span><span class="sxs-lookup"><span data-stu-id="69d2d-122">System.Collections Classes</span></span>](#BKMK_Collections)

- [<span data-ttu-id="69d2d-123">Реализация коллекции пар "ключ-значение"</span><span class="sxs-lookup"><span data-stu-id="69d2d-123">Implementing a Collection of Key/Value Pairs</span></span>](#BKMK_KeyValuePairs)

- [<span data-ttu-id="69d2d-124">Использование LINQ для доступа к коллекции</span><span class="sxs-lookup"><span data-stu-id="69d2d-124">Using LINQ to Access a Collection</span></span>](#BKMK_LINQ)

- [<span data-ttu-id="69d2d-125">Сортировка коллекции</span><span class="sxs-lookup"><span data-stu-id="69d2d-125">Sorting a Collection</span></span>](#BKMK_Sorting)

- [<span data-ttu-id="69d2d-126">Определение настраиваемой коллекции</span><span class="sxs-lookup"><span data-stu-id="69d2d-126">Defining a Custom Collection</span></span>](#BKMK_CustomCollection)

- [<span data-ttu-id="69d2d-127">Итераторы</span><span class="sxs-lookup"><span data-stu-id="69d2d-127">Iterators</span></span>](#BKMK_Iterators)

<a name="BKMK_SimpleCollection"></a>

## <a name="using-a-simple-collection"></a><span data-ttu-id="69d2d-128">Использование простой коллекции</span><span class="sxs-lookup"><span data-stu-id="69d2d-128">Using a Simple Collection</span></span>

<span data-ttu-id="69d2d-129">В примерах этого раздела используется универсальный класс <xref:System.Collections.Generic.List%601>, который позволяет работать со строго типизированными списками объектов.</span><span class="sxs-lookup"><span data-stu-id="69d2d-129">The examples in this section use the generic <xref:System.Collections.Generic.List%601> class, which enables you to work with a strongly typed list of objects.</span></span>

<span data-ttu-id="69d2d-130">В приведенном ниже примере создается список строк, а затем выполняется перебор строк с помощью оператора [foreach](../../language-reference/keywords/foreach-in.md).</span><span class="sxs-lookup"><span data-stu-id="69d2d-130">The following example creates a list of strings and then iterates through the strings by using a [foreach](../../language-reference/keywords/foreach-in.md) statement.</span></span>

```csharp
// Create a list of strings.
var salmons = new List<string>();
salmons.Add("chinook");
salmons.Add("coho");
salmons.Add("pink");
salmons.Add("sockeye");

// Iterate through the list.
foreach (var salmon in salmons)
{
    Console.Write(salmon + " ");
}
// Output: chinook coho pink sockeye
```

<span data-ttu-id="69d2d-131">Если содержимое коллекции известно заранее, для ее инициализации можно использовать *инициализатор коллекции*.</span><span class="sxs-lookup"><span data-stu-id="69d2d-131">If the contents of a collection are known in advance, you can use a *collection initializer* to initialize the collection.</span></span> <span data-ttu-id="69d2d-132">Дополнительные сведения см. в разделе [Инициализаторы объектов и коллекций](../classes-and-structs/object-and-collection-initializers.md).</span><span class="sxs-lookup"><span data-stu-id="69d2d-132">For more information, see [Object and Collection Initializers](../classes-and-structs/object-and-collection-initializers.md).</span></span>

<span data-ttu-id="69d2d-133">Следующий пример аналогичен предыдущему за исключением того, что для добавления элементов в коллекцию используется инициализатор коллекции.</span><span class="sxs-lookup"><span data-stu-id="69d2d-133">The following example is the same as the previous example, except a collection initializer is used to add elements to the collection.</span></span>

```csharp
// Create a list of strings by using a
// collection initializer.
var salmons = new List<string> { "chinook", "coho", "pink", "sockeye" };

// Iterate through the list.
foreach (var salmon in salmons)
{
    Console.Write(salmon + " ");
}
// Output: chinook coho pink sockeye
```

<span data-ttu-id="69d2d-134">Для перебора коллекции можно использовать оператор [for](../../language-reference/keywords/for.md) вместо оператора `foreach`.</span><span class="sxs-lookup"><span data-stu-id="69d2d-134">You can use a [for](../../language-reference/keywords/for.md) statement instead of a `foreach` statement to iterate through a collection.</span></span> <span data-ttu-id="69d2d-135">Для этого доступ к элементам коллекции осуществляется по позиции индекса.</span><span class="sxs-lookup"><span data-stu-id="69d2d-135">You accomplish this by accessing the collection elements by the index position.</span></span> <span data-ttu-id="69d2d-136">Индекс элементов начинается с 0 и заканчивается числом, равным количеству элементов минус 1.</span><span class="sxs-lookup"><span data-stu-id="69d2d-136">The index of the elements starts at 0 and ends at the element count minus 1.</span></span>

<span data-ttu-id="69d2d-137">В приведенном ниже примере выполняется перебор элементов коллекции с помощью оператора `for` вместо `foreach`.</span><span class="sxs-lookup"><span data-stu-id="69d2d-137">The following example iterates through the elements of a collection by using `for` instead of `foreach`.</span></span>

```csharp
// Create a list of strings by using a
// collection initializer.
var salmons = new List<string> { "chinook", "coho", "pink", "sockeye" };

for (var index = 0; index < salmons.Count; index++)
{
    Console.Write(salmons[index] + " ");
}
// Output: chinook coho pink sockeye
```

<span data-ttu-id="69d2d-138">В приведенном ниже примере элемент удаляется из коллекции путем указания удаляемого объекта.</span><span class="sxs-lookup"><span data-stu-id="69d2d-138">The following example removes an element from the collection by specifying the object to remove.</span></span>

```csharp
// Create a list of strings by using a
// collection initializer.
var salmons = new List<string> { "chinook", "coho", "pink", "sockeye" };

// Remove an element from the list by specifying
// the object.
salmons.Remove("coho");

// Iterate through the list.
foreach (var salmon in salmons)
{
    Console.Write(salmon + " ");
}
// Output: chinook pink sockeye
```

<span data-ttu-id="69d2d-139">В приведенном ниже примере удаляются элементы из универсального списка.</span><span class="sxs-lookup"><span data-stu-id="69d2d-139">The following example removes elements from a generic list.</span></span> <span data-ttu-id="69d2d-140">Вместо оператора `foreach` используется оператор [for](../../language-reference/keywords/for.md), выполняющий перебор в порядке убывания.</span><span class="sxs-lookup"><span data-stu-id="69d2d-140">Instead of a `foreach` statement, a [for](../../language-reference/keywords/for.md) statement that iterates in descending order is used.</span></span> <span data-ttu-id="69d2d-141">Связано это с тем, что в результате работы метода <xref:System.Collections.Generic.List%601.RemoveAt%2A> элементы, следующие за удаленным элементом, получают меньшее значение индекса.</span><span class="sxs-lookup"><span data-stu-id="69d2d-141">This is because the <xref:System.Collections.Generic.List%601.RemoveAt%2A> method causes elements after a removed element to have a lower index value.</span></span>

```csharp
var numbers = new List<int> { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };

// Remove odd numbers.
for (var index = numbers.Count - 1; index >= 0; index--)
{
    if (numbers[index] % 2 == 1)
    {
        // Remove the element by specifying
        // the zero-based index in the list.
        numbers.RemoveAt(index);
    }
}

// Iterate through the list.
// A lambda expression is placed in the ForEach method
// of the List(T) object.
numbers.ForEach(
    number => Console.Write(number + " "));
// Output: 0 2 4 6 8
```

<span data-ttu-id="69d2d-142">Для типа элементов в <xref:System.Collections.Generic.List%601> можно также определить собственный класс.</span><span class="sxs-lookup"><span data-stu-id="69d2d-142">For the type of elements in the <xref:System.Collections.Generic.List%601>, you can also define your own class.</span></span> <span data-ttu-id="69d2d-143">В приведенном ниже примере класс `Galaxy`, который используется объектом <xref:System.Collections.Generic.List%601>, определен в коде.</span><span class="sxs-lookup"><span data-stu-id="69d2d-143">In the following example, the `Galaxy` class that is used by the <xref:System.Collections.Generic.List%601> is defined in the code.</span></span>

```csharp
private static void IterateThroughList()
{
    var theGalaxies = new List<Galaxy>
        {
            new Galaxy() { Name="Tadpole", MegaLightYears=400},
            new Galaxy() { Name="Pinwheel", MegaLightYears=25},
            new Galaxy() { Name="Milky Way", MegaLightYears=0},
            new Galaxy() { Name="Andromeda", MegaLightYears=3}
        };

    foreach (Galaxy theGalaxy in theGalaxies)
    {
        Console.WriteLine(theGalaxy.Name + "  " + theGalaxy.MegaLightYears);
    }

    // Output:
    //  Tadpole  400
    //  Pinwheel  25
    //  Milky Way  0
    //  Andromeda  3
}

public class Galaxy
{
    public string Name { get; set; }
    public int MegaLightYears { get; set; }
}
```

<a name="BKMK_KindsOfCollections"></a>

## <a name="kinds-of-collections"></a><span data-ttu-id="69d2d-144">Виды коллекций</span><span class="sxs-lookup"><span data-stu-id="69d2d-144">Kinds of Collections</span></span>

<span data-ttu-id="69d2d-145">Многие типовые коллекции предоставляются платформой .NET.</span><span class="sxs-lookup"><span data-stu-id="69d2d-145">Many common collections are provided by .NET.</span></span> <span data-ttu-id="69d2d-146">Каждый тип коллекции предназначен для определенной цели.</span><span class="sxs-lookup"><span data-stu-id="69d2d-146">Each type of collection is designed for a specific purpose.</span></span>

<span data-ttu-id="69d2d-147">В этом разделе описываются следующие часто используемые классы коллекций:</span><span class="sxs-lookup"><span data-stu-id="69d2d-147">Some of the common collection classes are described in this section:</span></span>

- <span data-ttu-id="69d2d-148">Классы <xref:System.Collections.Generic></span><span class="sxs-lookup"><span data-stu-id="69d2d-148"><xref:System.Collections.Generic> classes</span></span>

- <span data-ttu-id="69d2d-149">Классы <xref:System.Collections.Concurrent></span><span class="sxs-lookup"><span data-stu-id="69d2d-149"><xref:System.Collections.Concurrent> classes</span></span>

- <span data-ttu-id="69d2d-150">Классы <xref:System.Collections></span><span class="sxs-lookup"><span data-stu-id="69d2d-150"><xref:System.Collections> classes</span></span>

<a name="BKMK_Generic"></a>

### <a name="systemcollectionsgeneric-classes"></a><span data-ttu-id="69d2d-151">Классы System.Collections.Generic</span><span class="sxs-lookup"><span data-stu-id="69d2d-151">System.Collections.Generic Classes</span></span>

<span data-ttu-id="69d2d-152">Универсальную коллекцию можно создать, используя один из классов в пространстве имен <xref:System.Collections.Generic>.</span><span class="sxs-lookup"><span data-stu-id="69d2d-152">You can create a generic collection by using one of the classes in the <xref:System.Collections.Generic> namespace.</span></span> <span data-ttu-id="69d2d-153">Универсальная коллекция применяется в том случае, если все элементы в коллекции имеют одинаковый тип данных.</span><span class="sxs-lookup"><span data-stu-id="69d2d-153">A generic collection is useful when every item in the collection has the same data type.</span></span> <span data-ttu-id="69d2d-154">Универсальная коллекция обеспечивает строгую типизацию, позволяя добавлять данные только необходимого типа.</span><span class="sxs-lookup"><span data-stu-id="69d2d-154">A generic collection enforces strong typing by allowing only the desired data type to be added.</span></span>

<span data-ttu-id="69d2d-155">В таблице ниже перечислены некоторые из часто используемых классов пространства имен <xref:System.Collections.Generic?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="69d2d-155">The following table lists some of the frequently used classes of the <xref:System.Collections.Generic?displayProperty=nameWithType> namespace:</span></span>

|<span data-ttu-id="69d2d-156">Класс</span><span class="sxs-lookup"><span data-stu-id="69d2d-156">Class</span></span>|<span data-ttu-id="69d2d-157">Описание</span><span class="sxs-lookup"><span data-stu-id="69d2d-157">Description</span></span>|
|---|---|
|<xref:System.Collections.Generic.Dictionary%602>|<span data-ttu-id="69d2d-158">Предоставляет коллекцию пар «ключ-значение», которые упорядочены по ключу.</span><span class="sxs-lookup"><span data-stu-id="69d2d-158">Represents a collection of key/value pairs that are organized based on the key.</span></span>|
|<xref:System.Collections.Generic.List%601>|<span data-ttu-id="69d2d-159">Представляет список объектов, доступных по индексу.</span><span class="sxs-lookup"><span data-stu-id="69d2d-159">Represents a list of objects that can be accessed by index.</span></span> <span data-ttu-id="69d2d-160">Предоставляет методы для поиска по списку, его сортировки и изменения.</span><span class="sxs-lookup"><span data-stu-id="69d2d-160">Provides methods to search, sort, and modify lists.</span></span>|
|<xref:System.Collections.Generic.Queue%601>|<span data-ttu-id="69d2d-161">Представляет коллекцию объектов, которая обслуживается в порядке поступления (FIFO).</span><span class="sxs-lookup"><span data-stu-id="69d2d-161">Represents a first in, first out (FIFO) collection of objects.</span></span>|
|<xref:System.Collections.Generic.SortedList%602>|<span data-ttu-id="69d2d-162">Представляет коллекцию пар "ключ-значение", упорядоченных по ключу на основе реализации <xref:System.Collections.Generic.IComparer%601>.</span><span class="sxs-lookup"><span data-stu-id="69d2d-162">Represents a collection of key/value pairs that are sorted by key based on the associated <xref:System.Collections.Generic.IComparer%601> implementation.</span></span>|
|<xref:System.Collections.Generic.Stack%601>|<span data-ttu-id="69d2d-163">Представляет коллекцию объектов, которая обслуживается в обратном порядке (LIFO).</span><span class="sxs-lookup"><span data-stu-id="69d2d-163">Represents a last in, first out (LIFO) collection of objects.</span></span>|

<span data-ttu-id="69d2d-164">Дополнительные сведения см. в разделе [Часто используемые типы коллекций](../../../standard/collections/commonly-used-collection-types.md), [Выбор класса коллекции](../../../standard/collections/selecting-a-collection-class.md) и <xref:System.Collections.Generic>.</span><span class="sxs-lookup"><span data-stu-id="69d2d-164">For additional information, see [Commonly Used Collection Types](../../../standard/collections/commonly-used-collection-types.md), [Selecting a Collection Class](../../../standard/collections/selecting-a-collection-class.md), and <xref:System.Collections.Generic>.</span></span>

<a name="BKMK_Concurrent"></a>

### <a name="systemcollectionsconcurrent-classes"></a><span data-ttu-id="69d2d-165">Классы System.Collections.Concurrent</span><span class="sxs-lookup"><span data-stu-id="69d2d-165">System.Collections.Concurrent Classes</span></span>

<span data-ttu-id="69d2d-166">В .NET Framework 4 или более поздних версиях коллекции пространства имен <xref:System.Collections.Concurrent> предоставляют эффективные потокобезопасные операции для доступа к элементам коллекции из нескольких потоков.</span><span class="sxs-lookup"><span data-stu-id="69d2d-166">In .NET Framework 4 and later versions, the collections in the <xref:System.Collections.Concurrent> namespace provide efficient thread-safe operations for accessing collection items from multiple threads.</span></span>

<span data-ttu-id="69d2d-167">Классы пространства имен <xref:System.Collections.Concurrent> следует использовать вместо соответствующих типов пространств имен <xref:System.Collections.Generic?displayProperty=nameWithType> и <xref:System.Collections?displayProperty=nameWithType>, если несколько потоков параллельно обращаются к такой коллекции.</span><span class="sxs-lookup"><span data-stu-id="69d2d-167">The classes in the <xref:System.Collections.Concurrent> namespace should be used instead of the corresponding types in the <xref:System.Collections.Generic?displayProperty=nameWithType> and <xref:System.Collections?displayProperty=nameWithType> namespaces whenever multiple threads are accessing the collection concurrently.</span></span> <span data-ttu-id="69d2d-168">Дополнительные сведения см. в статьях [Потокобезопасные коллекции](../../../standard/collections/thread-safe/index.md) и <xref:System.Collections.Concurrent>.</span><span class="sxs-lookup"><span data-stu-id="69d2d-168">For more information, see [Thread-Safe Collections](../../../standard/collections/thread-safe/index.md) and <xref:System.Collections.Concurrent>.</span></span>

<span data-ttu-id="69d2d-169">Некоторые из классов, входящих в пространство имен <xref:System.Collections.Concurrent>, — это <xref:System.Collections.Concurrent.BlockingCollection%601>, <xref:System.Collections.Concurrent.ConcurrentDictionary%602>, <xref:System.Collections.Concurrent.ConcurrentQueue%601> и <xref:System.Collections.Concurrent.ConcurrentStack%601>.</span><span class="sxs-lookup"><span data-stu-id="69d2d-169">Some classes included in the <xref:System.Collections.Concurrent> namespace are <xref:System.Collections.Concurrent.BlockingCollection%601>, <xref:System.Collections.Concurrent.ConcurrentDictionary%602>, <xref:System.Collections.Concurrent.ConcurrentQueue%601>, and <xref:System.Collections.Concurrent.ConcurrentStack%601>.</span></span>

<a name="BKMK_Collections"></a>

### <a name="systemcollections-classes"></a><span data-ttu-id="69d2d-170">Классы System.Collections</span><span class="sxs-lookup"><span data-stu-id="69d2d-170">System.Collections Classes</span></span>

<span data-ttu-id="69d2d-171">Классы в пространстве имен <xref:System.Collections?displayProperty=nameWithType> хранят элементы не в виде конкретно типизированных объектов, а как объекты типа `Object`.</span><span class="sxs-lookup"><span data-stu-id="69d2d-171">The classes in the <xref:System.Collections?displayProperty=nameWithType> namespace do not store elements as specifically typed objects, but as objects of type `Object`.</span></span>

<span data-ttu-id="69d2d-172">Везде, где это возможно, следует использовать универсальные коллекции пространства имен <xref:System.Collections.Generic?displayProperty=nameWithType> или пространства имен <xref:System.Collections.Concurrent> вместо устаревших типов пространства имен `System.Collections`.</span><span class="sxs-lookup"><span data-stu-id="69d2d-172">Whenever possible, you should use the generic collections in the <xref:System.Collections.Generic?displayProperty=nameWithType> namespace or the <xref:System.Collections.Concurrent> namespace instead of the legacy types in the `System.Collections` namespace.</span></span>

<span data-ttu-id="69d2d-173">В следующей таблице перечислены некоторые из часто используемых классов пространства имен `System.Collections`:</span><span class="sxs-lookup"><span data-stu-id="69d2d-173">The following table lists some of the frequently used classes in the `System.Collections` namespace:</span></span>

|<span data-ttu-id="69d2d-174">Класс</span><span class="sxs-lookup"><span data-stu-id="69d2d-174">Class</span></span>|<span data-ttu-id="69d2d-175">Описание</span><span class="sxs-lookup"><span data-stu-id="69d2d-175">Description</span></span>|
|---|---|
|<xref:System.Collections.ArrayList>|<span data-ttu-id="69d2d-176">Представляет массив объектов, размер которого динамически увеличивается по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="69d2d-176">Represents an array of objects whose size is dynamically increased as required.</span></span>|
|<xref:System.Collections.Hashtable>|<span data-ttu-id="69d2d-177">Представляет коллекцию пар «ключ-значение», которые упорядочены по хэш-коду ключа.</span><span class="sxs-lookup"><span data-stu-id="69d2d-177">Represents a collection of key/value pairs that are organized based on the hash code of the key.</span></span>|
|<xref:System.Collections.Queue>|<span data-ttu-id="69d2d-178">Представляет коллекцию объектов, которая обслуживается в порядке поступления (FIFO).</span><span class="sxs-lookup"><span data-stu-id="69d2d-178">Represents a first in, first out (FIFO) collection of objects.</span></span>|
|<xref:System.Collections.Stack>|<span data-ttu-id="69d2d-179">Представляет коллекцию объектов, которая обслуживается в обратном порядке (LIFO).</span><span class="sxs-lookup"><span data-stu-id="69d2d-179">Represents a last in, first out (LIFO) collection of objects.</span></span>|

<span data-ttu-id="69d2d-180">Пространство имен <xref:System.Collections.Specialized> предоставляет специализированные и строго типизированные классы коллекций, такие как коллекции строк, связанные списки и гибридные словари.</span><span class="sxs-lookup"><span data-stu-id="69d2d-180">The <xref:System.Collections.Specialized> namespace provides specialized and strongly typed collection classes, such as string-only collections and linked-list and hybrid dictionaries.</span></span>

<a name="BKMK_KeyValuePairs"></a>

## <a name="implementing-a-collection-of-keyvalue-pairs"></a><span data-ttu-id="69d2d-181">Реализация коллекции пар «ключ-значение»</span><span class="sxs-lookup"><span data-stu-id="69d2d-181">Implementing a Collection of Key/Value Pairs</span></span>

<span data-ttu-id="69d2d-182">Универсальная коллекция <xref:System.Collections.Generic.Dictionary%602> позволяет получить доступ к элементам коллекции с помощью ключа каждого элемента.</span><span class="sxs-lookup"><span data-stu-id="69d2d-182">The <xref:System.Collections.Generic.Dictionary%602> generic collection enables you to access to elements in a collection by using the key of each element.</span></span> <span data-ttu-id="69d2d-183">Каждый элемент, добавляемый в словарь, состоит из значения и связанного с ним ключа.</span><span class="sxs-lookup"><span data-stu-id="69d2d-183">Each addition to the dictionary consists of a value and its associated key.</span></span> <span data-ttu-id="69d2d-184">Извлечение значения по его ключу происходит быстро, так как класс `Dictionary` реализован как хэш-таблица.</span><span class="sxs-lookup"><span data-stu-id="69d2d-184">Retrieving a value by using its key is fast because the `Dictionary` class is implemented as a hash table.</span></span>

<span data-ttu-id="69d2d-185">В приведенном ниже примере создается коллекция `Dictionary` и выполняется перебор словаря с помощью оператора `foreach`.</span><span class="sxs-lookup"><span data-stu-id="69d2d-185">The following example creates a `Dictionary` collection and iterates through the dictionary by using a `foreach` statement.</span></span>

```csharp
private static void IterateThruDictionary()
{
    Dictionary<string, Element> elements = BuildDictionary();

    foreach (KeyValuePair<string, Element> kvp in elements)
    {
        Element theElement = kvp.Value;

        Console.WriteLine("key: " + kvp.Key);
        Console.WriteLine("values: " + theElement.Symbol + " " +
            theElement.Name + " " + theElement.AtomicNumber);
    }
}

private static Dictionary<string, Element> BuildDictionary()
{
    var elements = new Dictionary<string, Element>();

    AddToDictionary(elements, "K", "Potassium", 19);
    AddToDictionary(elements, "Ca", "Calcium", 20);
    AddToDictionary(elements, "Sc", "Scandium", 21);
    AddToDictionary(elements, "Ti", "Titanium", 22);

    return elements;
}

private static void AddToDictionary(Dictionary<string, Element> elements,
    string symbol, string name, int atomicNumber)
{
    Element theElement = new Element();

    theElement.Symbol = symbol;
    theElement.Name = name;
    theElement.AtomicNumber = atomicNumber;

    elements.Add(key: theElement.Symbol, value: theElement);
}

public class Element
{
    public string Symbol { get; set; }
    public string Name { get; set; }
    public int AtomicNumber { get; set; }
}
```

<span data-ttu-id="69d2d-186">Чтобы вместо этого использовать инициализатор коллекции для создания коллекции `Dictionary`, можно заменить методы `BuildDictionary` и `AddToDictionary` приведенным ниже методом.</span><span class="sxs-lookup"><span data-stu-id="69d2d-186">To instead use a collection initializer to build the `Dictionary` collection, you can replace the `BuildDictionary` and `AddToDictionary` methods with the following method.</span></span>

```csharp
private static Dictionary<string, Element> BuildDictionary2()
{
    return new Dictionary<string, Element>
    {
        {"K",
            new Element() { Symbol="K", Name="Potassium", AtomicNumber=19}},
        {"Ca",
            new Element() { Symbol="Ca", Name="Calcium", AtomicNumber=20}},
        {"Sc",
            new Element() { Symbol="Sc", Name="Scandium", AtomicNumber=21}},
        {"Ti",
            new Element() { Symbol="Ti", Name="Titanium", AtomicNumber=22}}
    };
}
```

<span data-ttu-id="69d2d-187">В приведенном ниже примере используется метод <xref:System.Collections.Generic.Dictionary%602.ContainsKey%2A> и свойство <xref:System.Collections.Generic.Dictionary%602.Item%2A>`Dictionary` для быстрого поиска элемента по ключу.</span><span class="sxs-lookup"><span data-stu-id="69d2d-187">The following example uses the <xref:System.Collections.Generic.Dictionary%602.ContainsKey%2A> method and the <xref:System.Collections.Generic.Dictionary%602.Item%2A> property of `Dictionary` to quickly find an item by key.</span></span> <span data-ttu-id="69d2d-188">Свойство `Item` позволяет получить доступ к элементу в коллекции `elements` с помощью кода `elements[symbol]` в C#.</span><span class="sxs-lookup"><span data-stu-id="69d2d-188">The `Item` property enables you to access an item in the `elements` collection by using the `elements[symbol]` in C#.</span></span>

```csharp
private static void FindInDictionary(string symbol)
{
    Dictionary<string, Element> elements = BuildDictionary();

    if (elements.ContainsKey(symbol) == false)
    {
        Console.WriteLine(symbol + " not found");
    }
    else
    {
        Element theElement = elements[symbol];
        Console.WriteLine("found: " + theElement.Name);
    }
}
```

<span data-ttu-id="69d2d-189">В приведенном ниже примере вместо этого используется метод <xref:System.Collections.Generic.Dictionary%602.TryGetValue%2A> для быстрого поиска элемента по ключу.</span><span class="sxs-lookup"><span data-stu-id="69d2d-189">The following example instead uses the <xref:System.Collections.Generic.Dictionary%602.TryGetValue%2A> method quickly find an item by key.</span></span>

```csharp
private static void FindInDictionary2(string symbol)
{
    Dictionary<string, Element> elements = BuildDictionary();

    Element theElement = null;
    if (elements.TryGetValue(symbol, out theElement) == false)
        Console.WriteLine(symbol + " not found");
    else
        Console.WriteLine("found: " + theElement.Name);
}
```

<a name="BKMK_LINQ"></a>

## <a name="using-linq-to-access-a-collection"></a><span data-ttu-id="69d2d-190">Использование LINQ для доступа к коллекции</span><span class="sxs-lookup"><span data-stu-id="69d2d-190">Using LINQ to Access a Collection</span></span>

<span data-ttu-id="69d2d-191">Для доступа к коллекции можно использовать язык LINQ.</span><span class="sxs-lookup"><span data-stu-id="69d2d-191">LINQ (Language-Integrated Query) can be used to access collections.</span></span> <span data-ttu-id="69d2d-192">Запросы LINQ обеспечивают возможности фильтрации, упорядочения и группировки.</span><span class="sxs-lookup"><span data-stu-id="69d2d-192">LINQ queries provide filtering, ordering, and grouping capabilities.</span></span> <span data-ttu-id="69d2d-193">Дополнительные сведения см. в разделе [Приступая к работе с LINQ в C#](linq/index.md).</span><span class="sxs-lookup"><span data-stu-id="69d2d-193">For more information, see [Getting Started with LINQ in C#](linq/index.md).</span></span>

<span data-ttu-id="69d2d-194">В приведенном ниже примере выполняется запрос LINQ применительно к универсальной коллекции `List`.</span><span class="sxs-lookup"><span data-stu-id="69d2d-194">The following example runs a LINQ query against a generic `List`.</span></span> <span data-ttu-id="69d2d-195">Запрос LINQ возвращает другую коллекцию, содержащую результаты.</span><span class="sxs-lookup"><span data-stu-id="69d2d-195">The LINQ query returns a different collection that contains the results.</span></span>

```csharp
private static void ShowLINQ()
{
    List<Element> elements = BuildList();

    // LINQ Query.
    var subset = from theElement in elements
                 where theElement.AtomicNumber < 22
                 orderby theElement.Name
                 select theElement;

    foreach (Element theElement in subset)
    {
        Console.WriteLine(theElement.Name + " " + theElement.AtomicNumber);
    }

    // Output:
    //  Calcium 20
    //  Potassium 19
    //  Scandium 21
}

private static List<Element> BuildList()
{
    return new List<Element>
    {
        { new Element() { Symbol="K", Name="Potassium", AtomicNumber=19}},
        { new Element() { Symbol="Ca", Name="Calcium", AtomicNumber=20}},
        { new Element() { Symbol="Sc", Name="Scandium", AtomicNumber=21}},
        { new Element() { Symbol="Ti", Name="Titanium", AtomicNumber=22}}
    };
}

public class Element
{
    public string Symbol { get; set; }
    public string Name { get; set; }
    public int AtomicNumber { get; set; }
}
```

<a name="BKMK_Sorting"></a>

## <a name="sorting-a-collection"></a><span data-ttu-id="69d2d-196">Сортировка коллекции</span><span class="sxs-lookup"><span data-stu-id="69d2d-196">Sorting a Collection</span></span>

<span data-ttu-id="69d2d-197">Приведенный ниже пример демонстрирует процедуру сортировки коллекции.</span><span class="sxs-lookup"><span data-stu-id="69d2d-197">The following example illustrates a procedure for sorting a collection.</span></span> <span data-ttu-id="69d2d-198">В примере сортируются экземпляры класса `Car`, которые хранятся в <xref:System.Collections.Generic.List%601>.</span><span class="sxs-lookup"><span data-stu-id="69d2d-198">The example sorts instances of the `Car` class that are stored in a <xref:System.Collections.Generic.List%601>.</span></span> <span data-ttu-id="69d2d-199">Класс `Car` реализует интерфейс <xref:System.IComparable%601>, который требует реализации метода <xref:System.IComparable%601.CompareTo%2A>.</span><span class="sxs-lookup"><span data-stu-id="69d2d-199">The `Car` class implements the <xref:System.IComparable%601> interface, which requires that the <xref:System.IComparable%601.CompareTo%2A> method be implemented.</span></span>

<span data-ttu-id="69d2d-200">Каждый вызов метода <xref:System.IComparable%601.CompareTo%2A> выполняет одно сравнение, используемое для сортировки.</span><span class="sxs-lookup"><span data-stu-id="69d2d-200">Each call to the <xref:System.IComparable%601.CompareTo%2A> method makes a single comparison that is used for sorting.</span></span> <span data-ttu-id="69d2d-201">Написанный пользователем код в методе `CompareTo` возвращает значение для каждого сравнения текущего объекта с другим объектом.</span><span class="sxs-lookup"><span data-stu-id="69d2d-201">User-written code in the `CompareTo` method returns a value for each comparison of the current object with another object.</span></span> <span data-ttu-id="69d2d-202">Возвращаемое значение меньше нуля, если текущий объект меньше другого объекта, больше нуля, если текущий объект больше другого объекта, и равняется нулю, если объекты равны.</span><span class="sxs-lookup"><span data-stu-id="69d2d-202">The value returned is less than zero if the current object is less than the other object, greater than zero if the current object is greater than the other object, and zero if they are equal.</span></span> <span data-ttu-id="69d2d-203">Это позволяет определить в коде условия для отношения «больше», «меньше» и «равно».</span><span class="sxs-lookup"><span data-stu-id="69d2d-203">This enables you to define in code the criteria for greater than, less than, and equal.</span></span>

<span data-ttu-id="69d2d-204">В методе `ListCars` оператор `cars.Sort()` сортирует список.</span><span class="sxs-lookup"><span data-stu-id="69d2d-204">In the `ListCars` method, the `cars.Sort()` statement sorts the list.</span></span> <span data-ttu-id="69d2d-205">Этот вызов метода <xref:System.Collections.Generic.List%601.Sort%2A><xref:System.Collections.Generic.List%601> приводит к тому, что метод `CompareTo` вызывается автоматически для объектов `Car` в `List`.</span><span class="sxs-lookup"><span data-stu-id="69d2d-205">This call to the <xref:System.Collections.Generic.List%601.Sort%2A> method of the <xref:System.Collections.Generic.List%601> causes the `CompareTo` method to be called automatically for the `Car` objects in the `List`.</span></span>

```csharp
private static void ListCars()
{
    var cars = new List<Car>
    {
        { new Car() { Name = "car1", Color = "blue", Speed = 20}},
        { new Car() { Name = "car2", Color = "red", Speed = 50}},
        { new Car() { Name = "car3", Color = "green", Speed = 10}},
        { new Car() { Name = "car4", Color = "blue", Speed = 50}},
        { new Car() { Name = "car5", Color = "blue", Speed = 30}},
        { new Car() { Name = "car6", Color = "red", Speed = 60}},
        { new Car() { Name = "car7", Color = "green", Speed = 50}}
    };

    // Sort the cars by color alphabetically, and then by speed
    // in descending order.
    cars.Sort();

    // View all of the cars.
    foreach (Car thisCar in cars)
    {
        Console.Write(thisCar.Color.PadRight(5) + " ");
        Console.Write(thisCar.Speed.ToString() + " ");
        Console.Write(thisCar.Name);
        Console.WriteLine();
    }

    // Output:
    //  blue  50 car4
    //  blue  30 car5
    //  blue  20 car1
    //  green 50 car7
    //  green 10 car3
    //  red   60 car6
    //  red   50 car2
}

public class Car : IComparable<Car>
{
    public string Name { get; set; }
    public int Speed { get; set; }
    public string Color { get; set; }

    public int CompareTo(Car other)
    {
        // A call to this method makes a single comparison that is
        // used for sorting.

        // Determine the relative order of the objects being compared.
        // Sort by color alphabetically, and then by speed in
        // descending order.

        // Compare the colors.
        int compare;
        compare = String.Compare(this.Color, other.Color, true);

        // If the colors are the same, compare the speeds.
        if (compare == 0)
        {
            compare = this.Speed.CompareTo(other.Speed);

            // Use descending order for speed.
            compare = -compare;
        }

        return compare;
    }
}
```

<a name="BKMK_CustomCollection"></a>

## <a name="defining-a-custom-collection"></a><span data-ttu-id="69d2d-206">Определение настраиваемой коллекции</span><span class="sxs-lookup"><span data-stu-id="69d2d-206">Defining a Custom Collection</span></span>

<span data-ttu-id="69d2d-207">Вы можете определить коллекцию, реализовав интерфейс <xref:System.Collections.Generic.IEnumerable%601> или <xref:System.Collections.IEnumerable>.</span><span class="sxs-lookup"><span data-stu-id="69d2d-207">You can define a collection by implementing the <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Collections.IEnumerable> interface.</span></span>

<span data-ttu-id="69d2d-208">Хотя можно определить настраиваемую коллекцию, обычно лучше использовать коллекции, входящие в .NET, которые описаны в разделе [Виды коллекций](#BKMK_KindsOfCollections) ранее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="69d2d-208">Although you can define a custom collection, it is usually better to instead use the collections that are included in .NET, which are described in [Kinds of Collections](#BKMK_KindsOfCollections) earlier in this article.</span></span>

<span data-ttu-id="69d2d-209">В приведенном ниже примере определяется настраиваемый класс коллекции с именем `AllColors`.</span><span class="sxs-lookup"><span data-stu-id="69d2d-209">The following example defines a custom collection class named `AllColors`.</span></span> <span data-ttu-id="69d2d-210">Этот класс реализует интерфейс <xref:System.Collections.IEnumerable>, который требует реализации метода <xref:System.Collections.IEnumerable.GetEnumerator%2A>.</span><span class="sxs-lookup"><span data-stu-id="69d2d-210">This class implements the <xref:System.Collections.IEnumerable> interface, which requires that the <xref:System.Collections.IEnumerable.GetEnumerator%2A> method be implemented.</span></span>

<span data-ttu-id="69d2d-211">Метод `GetEnumerator` возвращает экземпляр класса `ColorEnumerator`.</span><span class="sxs-lookup"><span data-stu-id="69d2d-211">The `GetEnumerator` method returns an instance of the `ColorEnumerator` class.</span></span> <span data-ttu-id="69d2d-212">Класс `ColorEnumerator` реализует интерфейс <xref:System.Collections.IEnumerator>, который требует реализации свойства <xref:System.Collections.IEnumerator.Current%2A>, метода <xref:System.Collections.IEnumerator.MoveNext%2A> и метода <xref:System.Collections.IEnumerator.Reset%2A>.</span><span class="sxs-lookup"><span data-stu-id="69d2d-212">`ColorEnumerator` implements the <xref:System.Collections.IEnumerator> interface, which requires that the <xref:System.Collections.IEnumerator.Current%2A> property, <xref:System.Collections.IEnumerator.MoveNext%2A> method, and <xref:System.Collections.IEnumerator.Reset%2A> method be implemented.</span></span>

```csharp
private static void ListColors()
{
    var colors = new AllColors();

    foreach (Color theColor in colors)
    {
        Console.Write(theColor.Name + " ");
    }
    Console.WriteLine();
    // Output: red blue green
}

// Collection class.
public class AllColors : System.Collections.IEnumerable
{
    Color[] _colors =
    {
        new Color() { Name = "red" },
        new Color() { Name = "blue" },
        new Color() { Name = "green" }
    };

    public System.Collections.IEnumerator GetEnumerator()
    {
        return new ColorEnumerator(_colors);

        // Instead of creating a custom enumerator, you could
        // use the GetEnumerator of the array.
        //return _colors.GetEnumerator();
    }

    // Custom enumerator.
    private class ColorEnumerator : System.Collections.IEnumerator
    {
        private Color[] _colors;
        private int _position = -1;

        public ColorEnumerator(Color[] colors)
        {
            _colors = colors;
        }

        object System.Collections.IEnumerator.Current
        {
            get
            {
                return _colors[_position];
            }
        }

        bool System.Collections.IEnumerator.MoveNext()
        {
            _position++;
            return (_position < _colors.Length);
        }

        void System.Collections.IEnumerator.Reset()
        {
            _position = -1;
        }
    }
}

// Element class.
public class Color
{
    public string Name { get; set; }
}
```

<a name="BKMK_Iterators"></a>

## <a name="iterators"></a><span data-ttu-id="69d2d-213">Iterators</span><span class="sxs-lookup"><span data-stu-id="69d2d-213">Iterators</span></span>

<span data-ttu-id="69d2d-214">*Итератор* используется для выполнения настраиваемого перебора коллекции.</span><span class="sxs-lookup"><span data-stu-id="69d2d-214">An *iterator* is used to perform a custom iteration over a collection.</span></span> <span data-ttu-id="69d2d-215">Итератор может быть методом или методом доступа `get`.</span><span class="sxs-lookup"><span data-stu-id="69d2d-215">An iterator can be a method or a `get` accessor.</span></span> <span data-ttu-id="69d2d-216">Итератор использует оператор [yield return](../../language-reference/keywords/yield.md) для возврата всех элементов коллекции по одному за раз.</span><span class="sxs-lookup"><span data-stu-id="69d2d-216">An iterator uses a [yield return](../../language-reference/keywords/yield.md) statement to return each element of the collection one at a time.</span></span>

<span data-ttu-id="69d2d-217">Итератор вызывается с помощью оператора [foreach](../../language-reference/keywords/foreach-in.md).</span><span class="sxs-lookup"><span data-stu-id="69d2d-217">You call an iterator by using a [foreach](../../language-reference/keywords/foreach-in.md) statement.</span></span> <span data-ttu-id="69d2d-218">Каждая итерация цикла `foreach` вызывает итератор.</span><span class="sxs-lookup"><span data-stu-id="69d2d-218">Each iteration of the `foreach` loop calls the iterator.</span></span> <span data-ttu-id="69d2d-219">При достижении оператора `yield return` в итераторе возвращается выражение, и текущее расположение в коде сохраняется.</span><span class="sxs-lookup"><span data-stu-id="69d2d-219">When a `yield return` statement is reached in the iterator, an expression is returned, and the current location in code is retained.</span></span> <span data-ttu-id="69d2d-220">При следующем вызове итератора выполнение возобновляется с этого места.</span><span class="sxs-lookup"><span data-stu-id="69d2d-220">Execution is restarted from that location the next time that the iterator is called.</span></span>

<span data-ttu-id="69d2d-221">Дополнительные сведения см. в разделе [Итераторы (C#)](./iterators.md).</span><span class="sxs-lookup"><span data-stu-id="69d2d-221">For more information, see [Iterators (C#)](./iterators.md).</span></span>

<span data-ttu-id="69d2d-222">В приведенном ниже примере используется метод-итератор.</span><span class="sxs-lookup"><span data-stu-id="69d2d-222">The following example uses an iterator method.</span></span> <span data-ttu-id="69d2d-223">Метод итератора содержит оператор `yield return`, находящийся внутри цикла [for](../../language-reference/keywords/for.md).</span><span class="sxs-lookup"><span data-stu-id="69d2d-223">The iterator method has a `yield return` statement that is inside a [for](../../language-reference/keywords/for.md) loop.</span></span> <span data-ttu-id="69d2d-224">В методе `ListEvenNumbers` каждая итерация тела оператора `foreach` создает вызов метода-итератора, который переходит к следующему оператору `yield return`.</span><span class="sxs-lookup"><span data-stu-id="69d2d-224">In the `ListEvenNumbers` method, each iteration of the `foreach` statement body creates a call to the iterator method, which proceeds to the next `yield return` statement.</span></span>

```csharp
private static void ListEvenNumbers()
{
    foreach (int number in EvenSequence(5, 18))
    {
        Console.Write(number.ToString() + " ");
    }
    Console.WriteLine();
    // Output: 6 8 10 12 14 16 18
}

private static IEnumerable<int> EvenSequence(
    int firstNumber, int lastNumber)
{
    // Yield even numbers in the range.
    for (var number = firstNumber; number <= lastNumber; number++)
    {
        if (number % 2 == 0)
        {
            yield return number;
        }
    }
}
```

## <a name="see-also"></a><span data-ttu-id="69d2d-225">См. также</span><span class="sxs-lookup"><span data-stu-id="69d2d-225">See also</span></span>

- [<span data-ttu-id="69d2d-226">Инициализаторы объектов и коллекций</span><span class="sxs-lookup"><span data-stu-id="69d2d-226">Object and Collection Initializers</span></span>](../classes-and-structs/object-and-collection-initializers.md)
- [<span data-ttu-id="69d2d-227">Основные понятия программирования (C#)</span><span class="sxs-lookup"><span data-stu-id="69d2d-227">Programming Concepts (C#)</span></span>](./index.md)
- [<span data-ttu-id="69d2d-228">Оператор Option Strict</span><span class="sxs-lookup"><span data-stu-id="69d2d-228">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="69d2d-229">LINQ to Objects (C#)</span><span class="sxs-lookup"><span data-stu-id="69d2d-229">LINQ to Objects (C#)</span></span>](./linq/linq-to-objects.md)
- [<span data-ttu-id="69d2d-230">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="69d2d-230">Parallel LINQ (PLINQ)</span></span>](../../../standard/parallel-programming/introduction-to-plinq.md)
- [<span data-ttu-id="69d2d-231">Коллекции и структуры данных</span><span class="sxs-lookup"><span data-stu-id="69d2d-231">Collections and Data Structures</span></span>](../../../standard/collections/index.md)
- [<span data-ttu-id="69d2d-232">Выбор класса коллекции</span><span class="sxs-lookup"><span data-stu-id="69d2d-232">Selecting a Collection Class</span></span>](../../../standard/collections/selecting-a-collection-class.md)
- [<span data-ttu-id="69d2d-233">Сравнение и сортировка в коллекциях</span><span class="sxs-lookup"><span data-stu-id="69d2d-233">Comparisons and Sorts Within Collections</span></span>](../../../standard/collections/comparisons-and-sorts-within-collections.md)
- [<span data-ttu-id="69d2d-234">Когда следует использовать универсальные коллекции</span><span class="sxs-lookup"><span data-stu-id="69d2d-234">When to Use Generic Collections</span></span>](../../../standard/collections/when-to-use-generic-collections.md)
