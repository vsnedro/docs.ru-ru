---
title: Преобразование типов данных (C#)
description: Методы преобразования изменяют тип входных объектов. Ознакомьтесь с операциями преобразования в запросах LINQ в C#, такими как Enumerable.AsEnumerable и Enumerable.OfType.
ms.date: 07/20/2015
ms.assetid: 46e5682f-77a1-4302-8f93-a2b53c408808
ms.openlocfilehash: 3291690f9aaee945ca7feb04ebbc676db2612894
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "87105486"
---
# <a name="converting-data-types-c"></a><span data-ttu-id="aa8ad-104">Преобразование типов данных (C#)</span><span class="sxs-lookup"><span data-stu-id="aa8ad-104">Converting Data Types (C#)</span></span>
<span data-ttu-id="aa8ad-105">Методы преобразования изменяют тип входных объектов.</span><span class="sxs-lookup"><span data-stu-id="aa8ad-105">Conversion methods change the type of input objects.</span></span>

 <span data-ttu-id="aa8ad-106">Операции преобразования в запросах LINQ удобны в различных ситуациях.</span><span class="sxs-lookup"><span data-stu-id="aa8ad-106">Conversion operations in LINQ queries are useful in a variety of applications.</span></span> <span data-ttu-id="aa8ad-107">Ниже приводятся некоторые примеры.</span><span class="sxs-lookup"><span data-stu-id="aa8ad-107">Following are some examples:</span></span>

- <span data-ttu-id="aa8ad-108">Метод <xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=nameWithType> можно использовать, чтобы скрыть настраиваемую реализацию типа стандартного оператора запроса.</span><span class="sxs-lookup"><span data-stu-id="aa8ad-108">The <xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=nameWithType> method can be used to hide a type's custom implementation of a standard query operator.</span></span>

- <span data-ttu-id="aa8ad-109">Метод <xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType> позволяет использовать непараметризованные коллекции для запросов LINQ.</span><span class="sxs-lookup"><span data-stu-id="aa8ad-109">The <xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType> method can be used to enable non-parameterized collections for LINQ querying.</span></span>

- <span data-ttu-id="aa8ad-110">Методы <xref:System.Linq.Enumerable.ToArray%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType> и <xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType> можно использовать для принудительного немедленного выполнения запроса, не дожидаясь, пока этот запрос будет перечислен.</span><span class="sxs-lookup"><span data-stu-id="aa8ad-110">The <xref:System.Linq.Enumerable.ToArray%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType>, and <xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType> methods can be used to force immediate query execution instead of deferring it until the query is enumerated.</span></span>

## <a name="methods"></a><span data-ttu-id="aa8ad-111">Методы</span><span class="sxs-lookup"><span data-stu-id="aa8ad-111">Methods</span></span>
 <span data-ttu-id="aa8ad-112">В следующей таблице перечислены методы стандартных операторов запросов, выполняющие преобразование типов данных.</span><span class="sxs-lookup"><span data-stu-id="aa8ad-112">The following table lists the standard query operator methods that perform data-type conversions.</span></span>

 <span data-ttu-id="aa8ad-113">Методы преобразования в этой таблице, имена которых начинаются с "As", изменяют статический тип исходной коллекции, но не выполняют перечисление.</span><span class="sxs-lookup"><span data-stu-id="aa8ad-113">The conversion methods in this table whose names start with "As" change the static type of the source collection but do not enumerate it.</span></span> <span data-ttu-id="aa8ad-114">Методы, имена которых начинаются с "To", перечисляют исходную коллекцию и помещают элементы в соответствующий тип коллекции.</span><span class="sxs-lookup"><span data-stu-id="aa8ad-114">The methods whose names start with "To" enumerate the source collection and put the items into the corresponding collection type.</span></span>

|<span data-ttu-id="aa8ad-115">Имя метода</span><span class="sxs-lookup"><span data-stu-id="aa8ad-115">Method Name</span></span>|<span data-ttu-id="aa8ad-116">Описание</span><span class="sxs-lookup"><span data-stu-id="aa8ad-116">Description</span></span>|<span data-ttu-id="aa8ad-117">Синтаксис выражения запроса C#</span><span class="sxs-lookup"><span data-stu-id="aa8ad-117">C# Query Expression Syntax</span></span>|<span data-ttu-id="aa8ad-118">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="aa8ad-118">More Information</span></span>|
|-----------------|-----------------|---------------------------------|----------------------|
|<span data-ttu-id="aa8ad-119">AsEnumerable</span><span class="sxs-lookup"><span data-stu-id="aa8ad-119">AsEnumerable</span></span>|<span data-ttu-id="aa8ad-120">Возвращает входное значение, типизированное как <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="aa8ad-120">Returns the input typed as <xref:System.Collections.Generic.IEnumerable%601>.</span></span>|<span data-ttu-id="aa8ad-121">Не применяется</span><span class="sxs-lookup"><span data-stu-id="aa8ad-121">Not applicable.</span></span>|<xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=nameWithType>|
|<span data-ttu-id="aa8ad-122">AsQueryable</span><span class="sxs-lookup"><span data-stu-id="aa8ad-122">AsQueryable</span></span>|<span data-ttu-id="aa8ad-123">Преобразует <xref:System.Collections.IEnumerable> (универсальный шаблон) в <xref:System.Linq.IQueryable> (универсальный шаблон).</span><span class="sxs-lookup"><span data-stu-id="aa8ad-123">Converts a (generic) <xref:System.Collections.IEnumerable> to a (generic) <xref:System.Linq.IQueryable>.</span></span>|<span data-ttu-id="aa8ad-124">Не применяется</span><span class="sxs-lookup"><span data-stu-id="aa8ad-124">Not applicable.</span></span>|<xref:System.Linq.Queryable.AsQueryable%2A?displayProperty=nameWithType>|
|<span data-ttu-id="aa8ad-125">Cast</span><span class="sxs-lookup"><span data-stu-id="aa8ad-125">Cast</span></span>|<span data-ttu-id="aa8ad-126">Приводит элементы коллекции к указанному типу.</span><span class="sxs-lookup"><span data-stu-id="aa8ad-126">Casts the elements of a collection to a specified type.</span></span>|<span data-ttu-id="aa8ad-127">Используйте явно типизированную переменную диапазона.</span><span class="sxs-lookup"><span data-stu-id="aa8ad-127">Use an explicitly typed range variable.</span></span> <span data-ttu-id="aa8ad-128">Пример:</span><span class="sxs-lookup"><span data-stu-id="aa8ad-128">For example:</span></span><br /><br /> `from string str in words`|<xref:System.Linq.Enumerable.Cast%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Cast%2A?displayProperty=nameWithType>|
|<span data-ttu-id="aa8ad-129">OfType</span><span class="sxs-lookup"><span data-stu-id="aa8ad-129">OfType</span></span>|<span data-ttu-id="aa8ad-130">Фильтрует значения в зависимости от возможности их приведения к указанному типу.</span><span class="sxs-lookup"><span data-stu-id="aa8ad-130">Filters values, depending on their ability to be cast to a specified type.</span></span>|<span data-ttu-id="aa8ad-131">Не применяется</span><span class="sxs-lookup"><span data-stu-id="aa8ad-131">Not applicable.</span></span>|<xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OfType%2A?displayProperty=nameWithType>|
|<span data-ttu-id="aa8ad-132">ToArray</span><span class="sxs-lookup"><span data-stu-id="aa8ad-132">ToArray</span></span>|<span data-ttu-id="aa8ad-133">Преобразует коллекцию в массив.</span><span class="sxs-lookup"><span data-stu-id="aa8ad-133">Converts a collection to an array.</span></span> <span data-ttu-id="aa8ad-134">Этот метод принудительно выполняет запрос.</span><span class="sxs-lookup"><span data-stu-id="aa8ad-134">This method forces query execution.</span></span>|<span data-ttu-id="aa8ad-135">Не применяется</span><span class="sxs-lookup"><span data-stu-id="aa8ad-135">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToArray%2A?displayProperty=nameWithType>|
|<span data-ttu-id="aa8ad-136">ToDictionary</span><span class="sxs-lookup"><span data-stu-id="aa8ad-136">ToDictionary</span></span>|<span data-ttu-id="aa8ad-137">Помещает элементы в <xref:System.Collections.Generic.Dictionary%602> в зависимости от функции выбора ключа.</span><span class="sxs-lookup"><span data-stu-id="aa8ad-137">Puts elements into a <xref:System.Collections.Generic.Dictionary%602> based on a key selector function.</span></span> <span data-ttu-id="aa8ad-138">Этот метод принудительно выполняет запрос.</span><span class="sxs-lookup"><span data-stu-id="aa8ad-138">This method forces query execution.</span></span>|<span data-ttu-id="aa8ad-139">Не применяется</span><span class="sxs-lookup"><span data-stu-id="aa8ad-139">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=nameWithType>|
|<span data-ttu-id="aa8ad-140">ToList</span><span class="sxs-lookup"><span data-stu-id="aa8ad-140">ToList</span></span>|<span data-ttu-id="aa8ad-141">Преобразует коллекцию в <xref:System.Collections.Generic.List%601>.</span><span class="sxs-lookup"><span data-stu-id="aa8ad-141">Converts a collection to a <xref:System.Collections.Generic.List%601>.</span></span> <span data-ttu-id="aa8ad-142">Этот метод принудительно выполняет запрос.</span><span class="sxs-lookup"><span data-stu-id="aa8ad-142">This method forces query execution.</span></span>|<span data-ttu-id="aa8ad-143">Не применяется</span><span class="sxs-lookup"><span data-stu-id="aa8ad-143">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType>|
|<span data-ttu-id="aa8ad-144">ToLookup</span><span class="sxs-lookup"><span data-stu-id="aa8ad-144">ToLookup</span></span>|<span data-ttu-id="aa8ad-145">Помещает элементы в <xref:System.Linq.Lookup%602> (словарь "один ко многим") в зависимости от функции выбора ключа.</span><span class="sxs-lookup"><span data-stu-id="aa8ad-145">Puts elements into a <xref:System.Linq.Lookup%602> (a one-to-many dictionary) based on a key selector function.</span></span> <span data-ttu-id="aa8ad-146">Этот метод принудительно выполняет запрос.</span><span class="sxs-lookup"><span data-stu-id="aa8ad-146">This method forces query execution.</span></span>|<span data-ttu-id="aa8ad-147">Не применяется</span><span class="sxs-lookup"><span data-stu-id="aa8ad-147">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType>|

## <a name="query-expression-syntax-example"></a><span data-ttu-id="aa8ad-148">Пример синтаксиса выражения запроса</span><span class="sxs-lookup"><span data-stu-id="aa8ad-148">Query Expression Syntax Example</span></span>

<span data-ttu-id="aa8ad-149">В следующем примере кода явным образом типизированная переменная диапазона используется для приведения типа к подтипу перед обращением к элементу, доступному только в подтипе.</span><span class="sxs-lookup"><span data-stu-id="aa8ad-149">The following code example uses an explicitly typed range variable to cast a type to a subtype before accessing a member that is available only on the subtype.</span></span>

```csharp
class Plant
{
    public string Name { get; set; }
}

class CarnivorousPlant : Plant
{
    public string TrapType { get; set; }
}

static void Cast()
{
    Plant[] plants = new Plant[] {
        new CarnivorousPlant { Name = "Venus Fly Trap", TrapType = "Snap Trap" },
        new CarnivorousPlant { Name = "Pitcher Plant", TrapType = "Pitfall Trap" },
        new CarnivorousPlant { Name = "Sundew", TrapType = "Flypaper Trap" },
        new CarnivorousPlant { Name = "Waterwheel Plant", TrapType = "Snap Trap" }
    };

    var query = from CarnivorousPlant cPlant in plants
                where cPlant.TrapType == "Snap Trap"
                select cPlant;

    foreach (Plant plant in query)
        Console.WriteLine(plant.Name);

    /* This code produces the following output:

        Venus Fly Trap
        Waterwheel Plant
    */
}
```

## <a name="see-also"></a><span data-ttu-id="aa8ad-150">См. также</span><span class="sxs-lookup"><span data-stu-id="aa8ad-150">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="aa8ad-151">Общие сведения о стандартных операторах запроса (C#)</span><span class="sxs-lookup"><span data-stu-id="aa8ad-151">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
- [<span data-ttu-id="aa8ad-152">предложение from</span><span class="sxs-lookup"><span data-stu-id="aa8ad-152">from clause</span></span>](../../../language-reference/keywords/from-clause.md)
- [<span data-ttu-id="aa8ad-153">Выражения запросов LINQ</span><span class="sxs-lookup"><span data-stu-id="aa8ad-153">LINQ Query Expressions</span></span>](../../../linq/index.md)
- [<span data-ttu-id="aa8ad-154">Выполнение запроса к ArrayList с помощью LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="aa8ad-154">How to query an ArrayList with LINQ (C#)</span></span>](./how-to-query-an-arraylist-with-linq.md)
