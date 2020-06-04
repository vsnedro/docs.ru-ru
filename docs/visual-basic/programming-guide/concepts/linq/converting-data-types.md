---
title: Преобразование типов данных
ms.date: 07/20/2015
ms.assetid: 9b0cf1ab-de48-4c6e-9f00-05b40fade46e
ms.openlocfilehash: 1394f53923ba850ae11fbc326a25c279589c3be1
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410855"
---
# <a name="converting-data-types-visual-basic"></a><span data-ttu-id="ed585-102">Преобразование типов данных (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ed585-102">Converting Data Types (Visual Basic)</span></span>

<span data-ttu-id="ed585-103">Методы преобразования изменяют тип входных объектов.</span><span class="sxs-lookup"><span data-stu-id="ed585-103">Conversion methods change the type of input objects.</span></span>

 <span data-ttu-id="ed585-104">Операции преобразования в запросах LINQ удобны в различных ситуациях.</span><span class="sxs-lookup"><span data-stu-id="ed585-104">Conversion operations in LINQ queries are useful in a variety of applications.</span></span> <span data-ttu-id="ed585-105">Ниже приводятся некоторые примеры:</span><span class="sxs-lookup"><span data-stu-id="ed585-105">The following are some examples:</span></span>

- <span data-ttu-id="ed585-106">Метод <xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=nameWithType> можно использовать, чтобы скрыть настраиваемую реализацию типа стандартного оператора запроса.</span><span class="sxs-lookup"><span data-stu-id="ed585-106">The <xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=nameWithType> method can be used to hide a type's custom implementation of a standard query operator.</span></span>

- <span data-ttu-id="ed585-107">Метод <xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType> позволяет использовать непараметризованные коллекции для запросов LINQ.</span><span class="sxs-lookup"><span data-stu-id="ed585-107">The <xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType> method can be used to enable non-parameterized collections for LINQ querying.</span></span>

- <span data-ttu-id="ed585-108">Методы <xref:System.Linq.Enumerable.ToArray%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType> и <xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType> можно использовать для принудительного немедленного выполнения запроса, не дожидаясь, пока этот запрос будет перечислен.</span><span class="sxs-lookup"><span data-stu-id="ed585-108">The <xref:System.Linq.Enumerable.ToArray%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType>, and <xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType> methods can be used to force immediate query execution instead of deferring it until the query is enumerated.</span></span>

## <a name="methods"></a><span data-ttu-id="ed585-109">Методы</span><span class="sxs-lookup"><span data-stu-id="ed585-109">Methods</span></span>

<span data-ttu-id="ed585-110">В следующей таблице перечислены методы стандартных операторов запросов, выполняющие преобразование типов данных.</span><span class="sxs-lookup"><span data-stu-id="ed585-110">The following table lists the standard query operator methods that perform data-type conversions.</span></span>

<span data-ttu-id="ed585-111">Методы преобразования в этой таблице, имена которых начинаются с "As", изменяют статический тип исходной коллекции, но не выполняют перечисление.</span><span class="sxs-lookup"><span data-stu-id="ed585-111">The conversion methods in this table whose names start with "As" change the static type of the source collection but do not enumerate it.</span></span> <span data-ttu-id="ed585-112">Методы, имена которых начинаются с "To", перечисляют исходную коллекцию и помещают элементы в соответствующий тип коллекции.</span><span class="sxs-lookup"><span data-stu-id="ed585-112">The methods whose names start with "To" enumerate the source collection and put the items into the corresponding collection type.</span></span>

|<span data-ttu-id="ed585-113">Имя метода</span><span class="sxs-lookup"><span data-stu-id="ed585-113">Method Name</span></span>|<span data-ttu-id="ed585-114">Описание</span><span class="sxs-lookup"><span data-stu-id="ed585-114">Description</span></span>|<span data-ttu-id="ed585-115">Синтаксис выражения запроса Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ed585-115">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="ed585-116">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="ed585-116">More Information</span></span>|
|-----------------|-----------------|------------------------------------------|----------------------|
|<span data-ttu-id="ed585-117">AsEnumerable</span><span class="sxs-lookup"><span data-stu-id="ed585-117">AsEnumerable</span></span>|<span data-ttu-id="ed585-118">Возвращает входное значение, типизированное как <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="ed585-118">Returns the input typed as <xref:System.Collections.Generic.IEnumerable%601>.</span></span>|<span data-ttu-id="ed585-119">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="ed585-119">Not applicable.</span></span>|<xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=nameWithType>|
|<span data-ttu-id="ed585-120">AsQueryable</span><span class="sxs-lookup"><span data-stu-id="ed585-120">AsQueryable</span></span>|<span data-ttu-id="ed585-121">Преобразует <xref:System.Collections.IEnumerable> (универсальный шаблон) в <xref:System.Linq.IQueryable> (универсальный шаблон).</span><span class="sxs-lookup"><span data-stu-id="ed585-121">Converts a (generic) <xref:System.Collections.IEnumerable> to a (generic) <xref:System.Linq.IQueryable>.</span></span>|<span data-ttu-id="ed585-122">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="ed585-122">Not applicable.</span></span>|<xref:System.Linq.Queryable.AsQueryable%2A?displayProperty=nameWithType>|
|<span data-ttu-id="ed585-123">Cast</span><span class="sxs-lookup"><span data-stu-id="ed585-123">Cast</span></span>|<span data-ttu-id="ed585-124">Приводит элементы коллекции к указанному типу.</span><span class="sxs-lookup"><span data-stu-id="ed585-124">Casts the elements of a collection to a specified type.</span></span>|`From … As …`|<xref:System.Linq.Enumerable.Cast%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Cast%2A?displayProperty=nameWithType>|
|<span data-ttu-id="ed585-125">OfType</span><span class="sxs-lookup"><span data-stu-id="ed585-125">OfType</span></span>|<span data-ttu-id="ed585-126">Фильтрует значения в зависимости от возможности их приведения к указанному типу.</span><span class="sxs-lookup"><span data-stu-id="ed585-126">Filters values, depending on their ability to be cast to a specified type.</span></span>|<span data-ttu-id="ed585-127">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="ed585-127">Not applicable.</span></span>|<xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OfType%2A?displayProperty=nameWithType>|
|<span data-ttu-id="ed585-128">ToArray</span><span class="sxs-lookup"><span data-stu-id="ed585-128">ToArray</span></span>|<span data-ttu-id="ed585-129">Преобразует коллекцию в массив.</span><span class="sxs-lookup"><span data-stu-id="ed585-129">Converts a collection to an array.</span></span> <span data-ttu-id="ed585-130">Этот метод принудительно выполняет запрос.</span><span class="sxs-lookup"><span data-stu-id="ed585-130">This method forces query execution.</span></span>|<span data-ttu-id="ed585-131">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="ed585-131">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToArray%2A?displayProperty=nameWithType>|
|<span data-ttu-id="ed585-132">ToDictionary</span><span class="sxs-lookup"><span data-stu-id="ed585-132">ToDictionary</span></span>|<span data-ttu-id="ed585-133">Помещает элементы в <xref:System.Collections.Generic.Dictionary%602> в зависимости от функции выбора ключа.</span><span class="sxs-lookup"><span data-stu-id="ed585-133">Puts elements into a <xref:System.Collections.Generic.Dictionary%602> based on a key selector function.</span></span> <span data-ttu-id="ed585-134">Этот метод принудительно выполняет запрос.</span><span class="sxs-lookup"><span data-stu-id="ed585-134">This method forces query execution.</span></span>|<span data-ttu-id="ed585-135">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="ed585-135">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=nameWithType>|
|<span data-ttu-id="ed585-136">ToList</span><span class="sxs-lookup"><span data-stu-id="ed585-136">ToList</span></span>|<span data-ttu-id="ed585-137">Преобразует коллекцию в <xref:System.Collections.Generic.List%601>.</span><span class="sxs-lookup"><span data-stu-id="ed585-137">Converts a collection to a <xref:System.Collections.Generic.List%601>.</span></span> <span data-ttu-id="ed585-138">Этот метод принудительно выполняет запрос.</span><span class="sxs-lookup"><span data-stu-id="ed585-138">This method forces query execution.</span></span>|<span data-ttu-id="ed585-139">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="ed585-139">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType>|
|<span data-ttu-id="ed585-140">ToLookup</span><span class="sxs-lookup"><span data-stu-id="ed585-140">ToLookup</span></span>|<span data-ttu-id="ed585-141">Помещает элементы в <xref:System.Linq.Lookup%602> (словарь "один ко многим") в зависимости от функции выбора ключа.</span><span class="sxs-lookup"><span data-stu-id="ed585-141">Puts elements into a <xref:System.Linq.Lookup%602> (a one-to-many dictionary) based on a key selector function.</span></span> <span data-ttu-id="ed585-142">Этот метод принудительно выполняет запрос.</span><span class="sxs-lookup"><span data-stu-id="ed585-142">This method forces query execution.</span></span>|<span data-ttu-id="ed585-143">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="ed585-143">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType>|

## <a name="query-expression-syntax-example"></a><span data-ttu-id="ed585-144">Пример синтаксиса выражения запроса</span><span class="sxs-lookup"><span data-stu-id="ed585-144">Query Expression Syntax Example</span></span>

<span data-ttu-id="ed585-145">В следующем примере кода предложение используется `From As` для приведения типа к подтипу перед доступом к элементу, доступному только для подтипа.</span><span class="sxs-lookup"><span data-stu-id="ed585-145">The following code example uses the `From As` clause to cast a type to a subtype before accessing a member that is available only on the subtype.</span></span>

```vb
Class Plant
    Public Property Name As String
End Class

Class CarnivorousPlant
    Inherits Plant
    Public Property TrapType As String
End Class

Sub Cast()

    Dim plants() As Plant = {
        New CarnivorousPlant With {.Name = "Venus Fly Trap", .TrapType = "Snap Trap"},
        New CarnivorousPlant With {.Name = "Pitcher Plant", .TrapType = "Pitfall Trap"},
        New CarnivorousPlant With {.Name = "Sundew", .TrapType = "Flypaper Trap"},
        New CarnivorousPlant With {.Name = "Waterwheel Plant", .TrapType = "Snap Trap"}}

    Dim query = From plant As CarnivorousPlant In plants
                Where plant.TrapType = "Snap Trap"
                Select plant

    Dim sb As New System.Text.StringBuilder()
    For Each plant In query
        sb.AppendLine(plant.Name)
    Next

    ' Display the results.
    MsgBox(sb.ToString())

    ' This code produces the following output:

    ' Venus Fly Trap
    ' Waterwheel Plant

End Sub
```

## <a name="see-also"></a><span data-ttu-id="ed585-146">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ed585-146">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="ed585-147">Общие сведения о стандартных операторах запроса (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ed585-147">Standard Query Operators Overview (Visual Basic)</span></span>](standard-query-operators-overview.md)
- [<span data-ttu-id="ed585-148">Предложение FROM</span><span class="sxs-lookup"><span data-stu-id="ed585-148">From Clause</span></span>](../../../language-reference/queries/from-clause.md)
- [<span data-ttu-id="ed585-149">Как выполнить запрос к ArrayList с помощью LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ed585-149">How to: Query an ArrayList with LINQ (Visual Basic)</span></span>](how-to-query-an-arraylist-with-linq.md)
