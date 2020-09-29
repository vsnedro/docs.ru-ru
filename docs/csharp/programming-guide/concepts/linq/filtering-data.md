---
title: Фильтрация данных (C#)
description: Фильтрация, также известная как выборка, позволяет ограничивать результаты на основе условия. Узнайте о методах стандартных операторов запросов в LINQ в C#, которые выполняют фильтрацию.
ms.date: 07/20/2015
ms.assetid: fbaece0d-0f23-47f7-89c5-f3ea8db692b6
ms.openlocfilehash: 51bf9f930ba67ba07c7c0f357910d5e36014138d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91186046"
---
# <a name="filtering-data-c"></a><span data-ttu-id="32a00-104">Фильтрация данных (C#)</span><span class="sxs-lookup"><span data-stu-id="32a00-104">Filtering Data (C#)</span></span>

<span data-ttu-id="32a00-105">Фильтрация — это операция по ограничению значений в результирующем наборе только элементами, соответствующими указанному условию.</span><span class="sxs-lookup"><span data-stu-id="32a00-105">Filtering refers to the operation of restricting the result set to contain only those elements that satisfy a specified condition.</span></span> <span data-ttu-id="32a00-106">Это также называется выборкой.</span><span class="sxs-lookup"><span data-stu-id="32a00-106">It is also known as selection.</span></span>  
  
 <span data-ttu-id="32a00-107">На следующем рисунке показаны результаты операции фильтрации последовательности символов.</span><span class="sxs-lookup"><span data-stu-id="32a00-107">The following illustration shows the results of filtering a sequence of characters.</span></span> <span data-ttu-id="32a00-108">Предикат для операции фильтрации указывает, что символ должен быть "A".</span><span class="sxs-lookup"><span data-stu-id="32a00-108">The predicate for the filtering operation specifies that the character must be 'A'.</span></span>  
  
 ![Схема, иллюстрирующая операцию фильтрации LINQ](./media/filtering-data/linq-filter-operation.png)  
  
 <span data-ttu-id="32a00-110">Методы стандартных операторов запросов, которые выполняют выборку, перечислены в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="32a00-110">The standard query operator methods that perform selection are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="32a00-111">Методы</span><span class="sxs-lookup"><span data-stu-id="32a00-111">Methods</span></span>  
  
|<span data-ttu-id="32a00-112">Имя метода</span><span class="sxs-lookup"><span data-stu-id="32a00-112">Method Name</span></span>|<span data-ttu-id="32a00-113">Описание</span><span class="sxs-lookup"><span data-stu-id="32a00-113">Description</span></span>|<span data-ttu-id="32a00-114">Синтаксис выражения запроса C#</span><span class="sxs-lookup"><span data-stu-id="32a00-114">C# Query Expression Syntax</span></span>|<span data-ttu-id="32a00-115">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="32a00-115">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="32a00-116">OfType</span><span class="sxs-lookup"><span data-stu-id="32a00-116">OfType</span></span>|<span data-ttu-id="32a00-117">Выбирает значения в зависимости от возможности приведения их к указанному типу.</span><span class="sxs-lookup"><span data-stu-id="32a00-117">Selects values, depending on their ability to be cast to a specified type.</span></span>|<span data-ttu-id="32a00-118">Не применяется</span><span class="sxs-lookup"><span data-stu-id="32a00-118">Not applicable.</span></span>|<xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OfType%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="32a00-119">Where</span><span class="sxs-lookup"><span data-stu-id="32a00-119">Where</span></span>|<span data-ttu-id="32a00-120">Выбирает значения, основанные на функции предиката.</span><span class="sxs-lookup"><span data-stu-id="32a00-120">Selects values that are based on a predicate function.</span></span>|`where`|<xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Where%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-example"></a><span data-ttu-id="32a00-121">Пример синтаксиса выражения запроса</span><span class="sxs-lookup"><span data-stu-id="32a00-121">Query Expression Syntax Example</span></span>  

 <span data-ttu-id="32a00-122">В следующем примере для выбора из массива строк, имеющих определенную длину, используется предложение `where`.</span><span class="sxs-lookup"><span data-stu-id="32a00-122">The following example uses the `where` clause to filter from an array those strings that have a specific length.</span></span>  
  
```csharp  
string[] words = { "the", "quick", "brown", "fox", "jumps" };  
  
IEnumerable<string> query = from word in words  
                            where word.Length == 3  
                            select word;  
  
foreach (string str in query)  
    Console.WriteLine(str);  
  
/* This code produces the following output:  
  
    the  
    fox  
*/  
```  
  
## <a name="see-also"></a><span data-ttu-id="32a00-123">См. также</span><span class="sxs-lookup"><span data-stu-id="32a00-123">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="32a00-124">Общие сведения о стандартных операторах запроса (C#)</span><span class="sxs-lookup"><span data-stu-id="32a00-124">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
- [<span data-ttu-id="32a00-125">предложение where</span><span class="sxs-lookup"><span data-stu-id="32a00-125">where clause</span></span>](../../../language-reference/keywords/where-clause.md)
- [<span data-ttu-id="32a00-126">Динамическое определение фильтров предикатов во время выполнения</span><span class="sxs-lookup"><span data-stu-id="32a00-126">Dynamically specify predicate filters at runtime</span></span>](../../../linq/dynamically-specify-predicate-filters-at-runtime.md)
- [<span data-ttu-id="32a00-127">Практическое руководство. Выполнение запроса к метаданным сборки при помощи отражения (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="32a00-127">How to query an assembly's metadata with Reflection (LINQ) (C#)</span></span>](./how-to-query-an-assembly-s-metadata-with-reflection-linq.md)
- [<span data-ttu-id="32a00-128">Практическое руководство. Запрос файлов с указанными атрибутами или именем (C#)</span><span class="sxs-lookup"><span data-stu-id="32a00-128">How to query for files with a specified attribute or name (C#)</span></span>](./how-to-query-for-files-with-a-specified-attribute-or-name.md)
- [<span data-ttu-id="32a00-129">Практическое руководство. Сортировка или фильтрация текстовых данных по любому слову или полю (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="32a00-129">How to sort or filter text data by any word or field (LINQ) (C#)</span></span>](./how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)
