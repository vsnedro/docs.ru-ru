---
title: Сортировка данных
ms.date: 07/20/2015
ms.assetid: 6f81065c-0c89-4bf3-a6d8-442273f8810e
ms.openlocfilehash: a5ccff745995ed7f41731cf98fb7c49d3247d994
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406798"
---
# <a name="sorting-data-visual-basic"></a><span data-ttu-id="823ed-102">Сортировка данных (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="823ed-102">Sorting Data (Visual Basic)</span></span>

<span data-ttu-id="823ed-103">Операция сортировки упорядочивает элементы последовательности на основе одного или нескольких атрибутов.</span><span class="sxs-lookup"><span data-stu-id="823ed-103">A sorting operation orders the elements of a sequence based on one or more attributes.</span></span> <span data-ttu-id="823ed-104">Первый критерий сортировки выполняет первичную сортировку элементов.</span><span class="sxs-lookup"><span data-stu-id="823ed-104">The first sort criterion performs a primary sort on the elements.</span></span> <span data-ttu-id="823ed-105">Указав второй критерий поиска, можно сортировать элементы внутри каждой группы первичной сортировки.</span><span class="sxs-lookup"><span data-stu-id="823ed-105">By specifying a second sort criterion, you can sort the elements within each primary sort group.</span></span>

<span data-ttu-id="823ed-106">На следующем рисунке показаны результаты операции сортировки в алфавитном порядке в последовательности символов.</span><span class="sxs-lookup"><span data-stu-id="823ed-106">The following illustration shows the results of an alphabetical sort operation on a sequence of characters.</span></span>

![Рисунок с операциями сортировки в алфавитном порядке.](./media/sorting-data/alphabetical-sort-operation.png)

<span data-ttu-id="823ed-108">Далее перечислены методы стандартных операторов запроса, которые выполняют сортировку данных.</span><span class="sxs-lookup"><span data-stu-id="823ed-108">The standard query operator methods that sort data are listed in the following section.</span></span>

## <a name="methods"></a><span data-ttu-id="823ed-109">Методы</span><span class="sxs-lookup"><span data-stu-id="823ed-109">Methods</span></span>

|<span data-ttu-id="823ed-110">Имя метода</span><span class="sxs-lookup"><span data-stu-id="823ed-110">Method Name</span></span>|<span data-ttu-id="823ed-111">Описание:</span><span class="sxs-lookup"><span data-stu-id="823ed-111">Description</span></span>|<span data-ttu-id="823ed-112">Синтаксис выражения запроса Visual Basic</span><span class="sxs-lookup"><span data-stu-id="823ed-112">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="823ed-113">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="823ed-113">More Information</span></span>|
|-----------------|-----------------|------------------------------------------|----------------------|
|<span data-ttu-id="823ed-114">OrderBy</span><span class="sxs-lookup"><span data-stu-id="823ed-114">OrderBy</span></span>|<span data-ttu-id="823ed-115">Сортировка значений в возрастающем порядке.</span><span class="sxs-lookup"><span data-stu-id="823ed-115">Sorts values in ascending order.</span></span>|`Order By`|<xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OrderBy%2A?displayProperty=nameWithType>|
|<span data-ttu-id="823ed-116">OrderByDescending</span><span class="sxs-lookup"><span data-stu-id="823ed-116">OrderByDescending</span></span>|<span data-ttu-id="823ed-117">Сортировка значений в убывающем порядке.</span><span class="sxs-lookup"><span data-stu-id="823ed-117">Sorts values in descending order.</span></span>|`Order By … Descending`|<xref:System.Linq.Enumerable.OrderByDescending%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OrderByDescending%2A?displayProperty=nameWithType>|
|<span data-ttu-id="823ed-118">ThenBy</span><span class="sxs-lookup"><span data-stu-id="823ed-118">ThenBy</span></span>|<span data-ttu-id="823ed-119">Дополнительная сортировка по возрастанию.</span><span class="sxs-lookup"><span data-stu-id="823ed-119">Performs a secondary sort in ascending order.</span></span>|`Order By …, …`|<xref:System.Linq.Enumerable.ThenBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.ThenBy%2A?displayProperty=nameWithType>|
|<span data-ttu-id="823ed-120">ThenByDescending</span><span class="sxs-lookup"><span data-stu-id="823ed-120">ThenByDescending</span></span>|<span data-ttu-id="823ed-121">Дополнительная сортировка по убыванию.</span><span class="sxs-lookup"><span data-stu-id="823ed-121">Performs a secondary sort in descending order.</span></span>|`Order By …, … Descending`|<xref:System.Linq.Enumerable.ThenByDescending%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.ThenByDescending%2A?displayProperty=nameWithType>|
|<span data-ttu-id="823ed-122">Reverse</span><span class="sxs-lookup"><span data-stu-id="823ed-122">Reverse</span></span>|<span data-ttu-id="823ed-123">Изменение порядка элементов в коллекции на обратный.</span><span class="sxs-lookup"><span data-stu-id="823ed-123">Reverses the order of the elements in a collection.</span></span>|<span data-ttu-id="823ed-124">Не применяется</span><span class="sxs-lookup"><span data-stu-id="823ed-124">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Reverse%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Reverse%2A?displayProperty=nameWithType>|

## <a name="query-expression-syntax-examples"></a><span data-ttu-id="823ed-125">Примеры синтаксиса выражений запросов</span><span class="sxs-lookup"><span data-stu-id="823ed-125">Query Expression Syntax Examples</span></span>

### <a name="primary-sort-examples"></a><span data-ttu-id="823ed-126">Примеры основной сортировки</span><span class="sxs-lookup"><span data-stu-id="823ed-126">Primary Sort Examples</span></span>

#### <a name="primary-ascending-sort"></a><span data-ttu-id="823ed-127">Основная сортировка по возрастанию</span><span class="sxs-lookup"><span data-stu-id="823ed-127">Primary Ascending Sort</span></span>

<span data-ttu-id="823ed-128">В следующем примере показано использование предложения `Order By` в запросе LINQ для сортировки строк в массиве по длине строки в порядке возрастания.</span><span class="sxs-lookup"><span data-stu-id="823ed-128">The following example demonstrates how to use the `Order By` clause in a LINQ query to sort the strings in an array by string length, in ascending order.</span></span>

```vb
Dim words = {"the", "quick", "brown", "fox", "jumps"}

Dim sortQuery = From word In words
                Order By word.Length
                Select word

Dim sb As New System.Text.StringBuilder()
For Each str As String In sortQuery
    sb.AppendLine(str)
Next

' Display the results.
MsgBox(sb.ToString())

' This code produces the following output:

' the
' fox
' quick
' brown
' jumps
```

#### <a name="primary-descending-sort"></a><span data-ttu-id="823ed-129">Основная сортировка по убыванию</span><span class="sxs-lookup"><span data-stu-id="823ed-129">Primary Descending Sort</span></span>

<span data-ttu-id="823ed-130">В следующем примере показано использование предложения `Order By Descending` в запросе LINQ для сортировки строк по их первой букве в порядке убывания.</span><span class="sxs-lookup"><span data-stu-id="823ed-130">The next example demonstrates how to use the `Order By Descending` clause in a LINQ query to sort the strings by their first letter, in descending order.</span></span>

```vb
Dim words = {"the", "quick", "brown", "fox", "jumps"}

Dim sortQuery = From word In words
                Order By word.Substring(0, 1) Descending
                Select word

Dim sb As New System.Text.StringBuilder()
For Each str As String In sortQuery
    sb.AppendLine(str)
Next

' Display the results.
MsgBox(sb.ToString())

' This code produces the following output:

' the
' quick
' jumps
' fox
' brown
```

### <a name="secondary-sort-examples"></a><span data-ttu-id="823ed-131">Примеры дополнительной сортировки</span><span class="sxs-lookup"><span data-stu-id="823ed-131">Secondary Sort Examples</span></span>

#### <a name="secondary-ascending-sort"></a><span data-ttu-id="823ed-132">Дополнительная сортировка по возрастанию</span><span class="sxs-lookup"><span data-stu-id="823ed-132">Secondary Ascending Sort</span></span>

<span data-ttu-id="823ed-133">В следующем примере показано использование предложения `Order By` в запросе LINQ для выполнения основной и дополнительной сортировки строк в массиве.</span><span class="sxs-lookup"><span data-stu-id="823ed-133">The following example demonstrates how to use the `Order By` clause in a LINQ query to perform a primary and secondary sort of the strings in an array.</span></span> <span data-ttu-id="823ed-134">Строки сортируются основным образом по длине и дополнительно — по первой букве строки; в обоих случаях в возрастающем порядке.</span><span class="sxs-lookup"><span data-stu-id="823ed-134">The strings are sorted primarily by length and secondarily by the first letter of the string, both in ascending order.</span></span>

```vb
Dim words = {"the", "quick", "brown", "fox", "jumps"}

Dim sortQuery = From word In words
                Order By word.Length, word.Substring(0, 1)
                Select word

Dim sb As New System.Text.StringBuilder()
For Each str As String In sortQuery
    sb.AppendLine(str)
Next

' Display the results.
MsgBox(sb.ToString())

' This code produces the following output:

' fox
' the
' brown
' jumps
' quick
```

#### <a name="secondary-descending-sort"></a><span data-ttu-id="823ed-135">Дополнительная сортировка по убыванию</span><span class="sxs-lookup"><span data-stu-id="823ed-135">Secondary Descending Sort</span></span>

<span data-ttu-id="823ed-136">В следующем примере показано использование предложения `Order By Descending` в запросе LINQ для выполнения основной сортировки по возрастанию и дополнительной сортировки по убыванию.</span><span class="sxs-lookup"><span data-stu-id="823ed-136">The next example demonstrates how to use the `Order By Descending` clause in a LINQ query to perform a primary sort, in ascending order, and a secondary sort, in descending order.</span></span> <span data-ttu-id="823ed-137">Строки сортируются основным образом по длине и дополнительно — по первой букве строки.</span><span class="sxs-lookup"><span data-stu-id="823ed-137">The strings are sorted primarily by length and secondarily by the first letter of the string.</span></span>

```vb
Dim words = {"the", "quick", "brown", "fox", "jumps"}

Dim sortQuery = From word In words
                Order By word.Length, word.Substring(0, 1) Descending
                Select word

Dim sb As New System.Text.StringBuilder()
For Each str As String In sortQuery
    sb.AppendLine(str)
Next

' Display the results.
MsgBox(sb.ToString())

' This code produces the following output:

' fox
' the
' quick
' jumps
' brown
```

## <a name="see-also"></a><span data-ttu-id="823ed-138">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="823ed-138">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="823ed-139">Общие сведения о стандартных операторах запроса (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="823ed-139">Standard Query Operators Overview (Visual Basic)</span></span>](standard-query-operators-overview.md)
- [<span data-ttu-id="823ed-140">Предложение Order By</span><span class="sxs-lookup"><span data-stu-id="823ed-140">Order By Clause</span></span>](../../../language-reference/queries/order-by-clause.md)
- <span data-ttu-id="823ed-141">[How to: Sort Query Results](../../language-features/linq/how-to-sort-query-results-by-using-linq.md) (Практическое руководство. Сортировка результатов запроса)</span><span class="sxs-lookup"><span data-stu-id="823ed-141">[How to: Sort Query Results](../../language-features/linq/how-to-sort-query-results-by-using-linq.md)</span></span>
- [<span data-ttu-id="823ed-142">Практическое руководство. Сортировка или фильтрация текстовых данных по любому слову или полю (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="823ed-142">How to: Sort or Filter Text Data by Any Word or Field (LINQ) (Visual Basic)</span></span>](how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)
