---
title: Группирование данных (C#)
description: При группировании данные объединяются в группы элементов, имеющие общий атрибут. Узнайте о методах стандартных операторов запросов в LINQ в C#, которые группируют элементы данных.
ms.date: 07/20/2015
ms.assetid: e414e9e4-343a-4e6e-858f-4a30c5e64492
ms.openlocfilehash: 584d50fc15dd8b4ce1cfdf4766f3bc8b8383eb12
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202569"
---
# <a name="grouping-data-c"></a><span data-ttu-id="3579d-104">Группирование данных (C#)</span><span class="sxs-lookup"><span data-stu-id="3579d-104">Grouping Data (C#)</span></span>

<span data-ttu-id="3579d-105">Группированием называют операцию объединения данных в группы таким образом, чтобы у элементов в каждой группе был общий атрибут.</span><span class="sxs-lookup"><span data-stu-id="3579d-105">Grouping refers to the operation of putting data into groups so that the elements in each group share a common attribute.</span></span>  
  
 <span data-ttu-id="3579d-106">На следующем рисунке показаны результаты операции группирования последовательности символов.</span><span class="sxs-lookup"><span data-stu-id="3579d-106">The following illustration shows the results of grouping a sequence of characters.</span></span> <span data-ttu-id="3579d-107">Ключ для каждой группы — это символ.</span><span class="sxs-lookup"><span data-stu-id="3579d-107">The key for each group is the character.</span></span>  
  
 ![Схема, показывающая операцию группирования LINQ.](./media/grouping-data/linq-group-operation.png)  
  
 <span data-ttu-id="3579d-109">Далее перечислены методы стандартных операторов запроса, которые группируют элементы данных.</span><span class="sxs-lookup"><span data-stu-id="3579d-109">The standard query operator methods that group data elements are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3579d-110">Методы</span><span class="sxs-lookup"><span data-stu-id="3579d-110">Methods</span></span>  
  
|<span data-ttu-id="3579d-111">Имя метода</span><span class="sxs-lookup"><span data-stu-id="3579d-111">Method Name</span></span>|<span data-ttu-id="3579d-112">Описание</span><span class="sxs-lookup"><span data-stu-id="3579d-112">Description</span></span>|<span data-ttu-id="3579d-113">Синтаксис выражения запроса C#</span><span class="sxs-lookup"><span data-stu-id="3579d-113">C# Query Expression Syntax</span></span>|<span data-ttu-id="3579d-114">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="3579d-114">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="3579d-115">GroupBy</span><span class="sxs-lookup"><span data-stu-id="3579d-115">GroupBy</span></span>|<span data-ttu-id="3579d-116">Группирует элементы с общим атрибутом.</span><span class="sxs-lookup"><span data-stu-id="3579d-116">Groups elements that share a common attribute.</span></span> <span data-ttu-id="3579d-117">Каждая группа представлена объектом <xref:System.Linq.IGrouping%602>.</span><span class="sxs-lookup"><span data-stu-id="3579d-117">Each group is represented by an <xref:System.Linq.IGrouping%602> object.</span></span>|`group … by`<br /><br /> <span data-ttu-id="3579d-118">-или-</span><span class="sxs-lookup"><span data-stu-id="3579d-118">-or-</span></span><br /><br /> `group … by … into …`|<xref:System.Linq.Enumerable.GroupBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.GroupBy%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="3579d-119">ToLookup</span><span class="sxs-lookup"><span data-stu-id="3579d-119">ToLookup</span></span>|<span data-ttu-id="3579d-120">Вставляет элементы в <xref:System.Linq.Lookup%602> (словарь "один ко многим") в зависимости от функции выбора ключа.</span><span class="sxs-lookup"><span data-stu-id="3579d-120">Inserts elements into a <xref:System.Linq.Lookup%602> (a one-to-many dictionary) based on a key selector function.</span></span>|<span data-ttu-id="3579d-121">Не применяется</span><span class="sxs-lookup"><span data-stu-id="3579d-121">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-example"></a><span data-ttu-id="3579d-122">Пример синтаксиса выражения запроса</span><span class="sxs-lookup"><span data-stu-id="3579d-122">Query Expression Syntax Example</span></span>  

 <span data-ttu-id="3579d-123">В следующем примере кода предложение `group by` используется для группирования целых чисел в списке на основании четности.</span><span class="sxs-lookup"><span data-stu-id="3579d-123">The following code example uses the `group by` clause to group integers in a list according to whether they are even or odd.</span></span>  
  
```csharp  
List<int> numbers = new List<int>() { 35, 44, 200, 84, 3987, 4, 199, 329, 446, 208 };  
  
IEnumerable<IGrouping<int, int>> query = from number in numbers  
                                         group number by number % 2;  
  
foreach (var group in query)  
{  
    Console.WriteLine(group.Key == 0 ? "\nEven numbers:" : "\nOdd numbers:");  
    foreach (int i in group)  
        Console.WriteLine(i);  
}  
  
/* This code produces the following output:  
  
    Odd numbers:  
    35  
    3987  
    199  
    329  
  
    Even numbers:  
    44  
    200  
    84  
    4  
    446  
    208  
*/  
```  
  
## <a name="see-also"></a><span data-ttu-id="3579d-124">См. также</span><span class="sxs-lookup"><span data-stu-id="3579d-124">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="3579d-125">Общие сведения о стандартных операторах запроса (C#)</span><span class="sxs-lookup"><span data-stu-id="3579d-125">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
- [<span data-ttu-id="3579d-126">предложение group</span><span class="sxs-lookup"><span data-stu-id="3579d-126">group clause</span></span>](../../../language-reference/keywords/group-clause.md)
- [<span data-ttu-id="3579d-127">Создание вложенной группы</span><span class="sxs-lookup"><span data-stu-id="3579d-127">Create a nested group</span></span>](../../../linq/create-a-nested-group.md)
- [<span data-ttu-id="3579d-128">Группировка файлов по расширению (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="3579d-128">How to group files by extension (LINQ) (C#)</span></span>](./how-to-group-files-by-extension-linq.md)
- [<span data-ttu-id="3579d-129">Группировка результатов запросов</span><span class="sxs-lookup"><span data-stu-id="3579d-129">Group query results</span></span>](../../../linq/group-query-results.md)
- [<span data-ttu-id="3579d-130">Вложенный запрос в операции группирования</span><span class="sxs-lookup"><span data-stu-id="3579d-130">Perform a subquery on a grouping operation</span></span>](../../../linq/perform-a-subquery-on-a-grouping-operation.md)
- [<span data-ttu-id="3579d-131">Разделение файла на несколько файлов с помощью групп (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="3579d-131">How to split a file into many files by using groups (LINQ) (C#)</span></span>](./how-to-split-a-file-into-many-files-by-using-groups-linq.md)
