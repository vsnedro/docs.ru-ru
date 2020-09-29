---
title: Сортировка данных (C#)
description: Сведения об операциях сортировки и методах стандартных операторов запроса, которые выполняют сортировку в LINQ при программировании на C#.
ms.date: 07/20/2015
ms.assetid: d93fa055-2f19-46d2-9898-e2aed628f1c9
ms.openlocfilehash: 0665e5dec95fd2929d24d82568de66597df1c0bd
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91195510"
---
# <a name="sorting-data-c"></a><span data-ttu-id="9b632-103">Сортировка данных (C#)</span><span class="sxs-lookup"><span data-stu-id="9b632-103">Sorting Data (C#)</span></span>

<span data-ttu-id="9b632-104">Операция сортировки упорядочивает элементы последовательности на основе одного или нескольких атрибутов.</span><span class="sxs-lookup"><span data-stu-id="9b632-104">A sorting operation orders the elements of a sequence based on one or more attributes.</span></span> <span data-ttu-id="9b632-105">Первый критерий сортировки выполняет первичную сортировку элементов.</span><span class="sxs-lookup"><span data-stu-id="9b632-105">The first sort criterion performs a primary sort on the elements.</span></span> <span data-ttu-id="9b632-106">Указав второй критерий поиска, можно сортировать элементы внутри каждой группы первичной сортировки.</span><span class="sxs-lookup"><span data-stu-id="9b632-106">By specifying a second sort criterion, you can sort the elements within each primary sort group.</span></span>  
  
 <span data-ttu-id="9b632-107">На следующем рисунке показаны результаты операции сортировки в алфавитном порядке в последовательности символов:</span><span class="sxs-lookup"><span data-stu-id="9b632-107">The following illustration shows the results of an alphabetical sort operation on a sequence of characters:</span></span>
  
 ![Рисунок с операциями сортировки в алфавитном порядке.](./media/sorting-data/alphabetical-sort-operation.png)  
  
 <span data-ttu-id="9b632-109">Далее перечислены методы стандартных операторов запроса, которые выполняют сортировку данных.</span><span class="sxs-lookup"><span data-stu-id="9b632-109">The standard query operator methods that sort data are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9b632-110">Методы</span><span class="sxs-lookup"><span data-stu-id="9b632-110">Methods</span></span>  
  
|<span data-ttu-id="9b632-111">Имя метода</span><span class="sxs-lookup"><span data-stu-id="9b632-111">Method Name</span></span>|<span data-ttu-id="9b632-112">Описание</span><span class="sxs-lookup"><span data-stu-id="9b632-112">Description</span></span>|<span data-ttu-id="9b632-113">Синтаксис выражения запроса C#</span><span class="sxs-lookup"><span data-stu-id="9b632-113">C# Query Expression Syntax</span></span>|<span data-ttu-id="9b632-114">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="9b632-114">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="9b632-115">OrderBy</span><span class="sxs-lookup"><span data-stu-id="9b632-115">OrderBy</span></span>|<span data-ttu-id="9b632-116">Сортировка значений в возрастающем порядке.</span><span class="sxs-lookup"><span data-stu-id="9b632-116">Sorts values in ascending order.</span></span>|`orderby`|<xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OrderBy%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="9b632-117">OrderByDescending</span><span class="sxs-lookup"><span data-stu-id="9b632-117">OrderByDescending</span></span>|<span data-ttu-id="9b632-118">Сортировка значений в убывающем порядке.</span><span class="sxs-lookup"><span data-stu-id="9b632-118">Sorts values in descending order.</span></span>|`orderby … descending`|<xref:System.Linq.Enumerable.OrderByDescending%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OrderByDescending%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="9b632-119">ThenBy</span><span class="sxs-lookup"><span data-stu-id="9b632-119">ThenBy</span></span>|<span data-ttu-id="9b632-120">Дополнительная сортировка по возрастанию.</span><span class="sxs-lookup"><span data-stu-id="9b632-120">Performs a secondary sort in ascending order.</span></span>|`orderby …, …`|<xref:System.Linq.Enumerable.ThenBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.ThenBy%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="9b632-121">ThenByDescending</span><span class="sxs-lookup"><span data-stu-id="9b632-121">ThenByDescending</span></span>|<span data-ttu-id="9b632-122">Дополнительная сортировка по убыванию.</span><span class="sxs-lookup"><span data-stu-id="9b632-122">Performs a secondary sort in descending order.</span></span>|`orderby …, … descending`|<xref:System.Linq.Enumerable.ThenByDescending%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.ThenByDescending%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="9b632-123">Reverse</span><span class="sxs-lookup"><span data-stu-id="9b632-123">Reverse</span></span>|<span data-ttu-id="9b632-124">Изменение порядка элементов в коллекции на обратный.</span><span class="sxs-lookup"><span data-stu-id="9b632-124">Reverses the order of the elements in a collection.</span></span>|<span data-ttu-id="9b632-125">Не применяется</span><span class="sxs-lookup"><span data-stu-id="9b632-125">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Reverse%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Reverse%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="9b632-126">Примеры синтаксиса выражений запросов</span><span class="sxs-lookup"><span data-stu-id="9b632-126">Query Expression Syntax Examples</span></span>  
  
### <a name="primary-sort-examples"></a><span data-ttu-id="9b632-127">Примеры основной сортировки</span><span class="sxs-lookup"><span data-stu-id="9b632-127">Primary Sort Examples</span></span>  
  
#### <a name="primary-ascending-sort"></a><span data-ttu-id="9b632-128">Основная сортировка по возрастанию</span><span class="sxs-lookup"><span data-stu-id="9b632-128">Primary Ascending Sort</span></span>  

 <span data-ttu-id="9b632-129">В следующем примере показано использование предложения `orderby` в запросе LINQ для сортировки строк в массиве по длине строки в порядке возрастания.</span><span class="sxs-lookup"><span data-stu-id="9b632-129">The following example demonstrates how to use the `orderby` clause in a LINQ query to sort the strings in an array by string length, in ascending order.</span></span>  
  
```csharp  
string[] words = { "the", "quick", "brown", "fox", "jumps" };  
  
IEnumerable<string> query = from word in words  
                            orderby word.Length  
                            select word;  
  
foreach (string str in query)  
    Console.WriteLine(str);  
  
/* This code produces the following output:  
  
    the  
    fox  
    quick  
    brown  
    jumps  
*/  
```  
  
#### <a name="primary-descending-sort"></a><span data-ttu-id="9b632-130">Основная сортировка по убыванию</span><span class="sxs-lookup"><span data-stu-id="9b632-130">Primary Descending Sort</span></span>  

 <span data-ttu-id="9b632-131">В следующем примере показано использование предложения `orderby descending` в запросе LINQ для сортировки строк по их первой букве в порядке убывания.</span><span class="sxs-lookup"><span data-stu-id="9b632-131">The next example demonstrates how to use the `orderby descending` clause in a LINQ query to sort the strings by their first letter, in descending order.</span></span>  
  
```csharp  
string[] words = { "the", "quick", "brown", "fox", "jumps" };  
  
IEnumerable<string> query = from word in words  
                            orderby word.Substring(0, 1) descending  
                            select word;  
  
foreach (string str in query)  
    Console.WriteLine(str);  
  
/* This code produces the following output:  
  
    the  
    quick  
    jumps  
    fox  
    brown  
*/  
```  
  
### <a name="secondary-sort-examples"></a><span data-ttu-id="9b632-132">Примеры дополнительной сортировки</span><span class="sxs-lookup"><span data-stu-id="9b632-132">Secondary Sort Examples</span></span>  
  
#### <a name="secondary-ascending-sort"></a><span data-ttu-id="9b632-133">Дополнительная сортировка по возрастанию</span><span class="sxs-lookup"><span data-stu-id="9b632-133">Secondary Ascending Sort</span></span>  

 <span data-ttu-id="9b632-134">В следующем примере показано использование предложения `orderby` в запросе LINQ для выполнения основной и дополнительной сортировки строк в массиве.</span><span class="sxs-lookup"><span data-stu-id="9b632-134">The following example demonstrates how to use the `orderby` clause in a LINQ query to perform a primary and secondary sort of the strings in an array.</span></span> <span data-ttu-id="9b632-135">Строки сортируются основным образом по длине и дополнительно — по первой букве строки; в обоих случаях в возрастающем порядке.</span><span class="sxs-lookup"><span data-stu-id="9b632-135">The strings are sorted primarily by length and secondarily by the first letter of the string, both in ascending order.</span></span>  
  
```csharp  
string[] words = { "the", "quick", "brown", "fox", "jumps" };  
  
IEnumerable<string> query = from word in words  
                            orderby word.Length, word.Substring(0, 1)  
                            select word;  
  
foreach (string str in query)  
    Console.WriteLine(str);  
  
/* This code produces the following output:  
  
    fox  
    the  
    brown  
    jumps  
    quick  
*/  
```  
  
#### <a name="secondary-descending-sort"></a><span data-ttu-id="9b632-136">Дополнительная сортировка по убыванию</span><span class="sxs-lookup"><span data-stu-id="9b632-136">Secondary Descending Sort</span></span>  

 <span data-ttu-id="9b632-137">В следующем примере показано использование предложения `orderby descending` в запросе LINQ для выполнения основной сортировки по возрастанию и дополнительной сортировки по убыванию.</span><span class="sxs-lookup"><span data-stu-id="9b632-137">The next example demonstrates how to use the `orderby descending` clause in a LINQ query to perform a primary sort, in ascending order, and a secondary sort, in descending order.</span></span> <span data-ttu-id="9b632-138">Строки сортируются основным образом по длине и дополнительно — по первой букве строки.</span><span class="sxs-lookup"><span data-stu-id="9b632-138">The strings are sorted primarily by length and secondarily by the first letter of the string.</span></span>  
  
```csharp  
string[] words = { "the", "quick", "brown", "fox", "jumps" };  
  
IEnumerable<string> query = from word in words  
                            orderby word.Length, word.Substring(0, 1) descending  
                            select word;  
  
foreach (string str in query)  
    Console.WriteLine(str);  
  
/* This code produces the following output:  
  
    the  
    fox  
    quick  
    jumps  
    brown  
*/  
```  
  
## <a name="see-also"></a><span data-ttu-id="9b632-139">См. также</span><span class="sxs-lookup"><span data-stu-id="9b632-139">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="9b632-140">Общие сведения о стандартных операторах запроса (C#)</span><span class="sxs-lookup"><span data-stu-id="9b632-140">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
- [<span data-ttu-id="9b632-141">предложение orderby</span><span class="sxs-lookup"><span data-stu-id="9b632-141">orderby clause</span></span>](../../../language-reference/keywords/orderby-clause.md)
- [<span data-ttu-id="9b632-142">Упорядочение результатов предложения соединения</span><span class="sxs-lookup"><span data-stu-id="9b632-142">Order the results of a join clause</span></span>](../../../linq/order-the-results-of-a-join-clause.md)
- [<span data-ttu-id="9b632-143">Практическое руководство. Сортировка или фильтрация текстовых данных по любому слову или полю (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="9b632-143">How to sort or filter text data by any word or field (LINQ) (C#)</span></span>](./how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)
