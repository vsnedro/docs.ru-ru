---
title: Операции над множествами (C#)
description: Сведения об операциях над множествами и методах стандартных операторов запроса, которые выполняют такие операции в LINQ при программировании на C#.
ms.date: 07/20/2015
ms.assetid: 7c589367-ef8f-4161-9050-642c47e6bf63
ms.openlocfilehash: ab2608b267113ad5d47a33e64cd9a5e21496f668
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302377"
---
# <a name="set-operations-c"></a><span data-ttu-id="006fe-103">Операции над множествами (C#)</span><span class="sxs-lookup"><span data-stu-id="006fe-103">Set Operations (C#)</span></span>
<span data-ttu-id="006fe-104">Операции над множествами в LINQ — это операции запросов, результирующие наборы которых основываются на наличии или отсутствии эквивалентных элементов в одной или другой коллекции (или наборе).</span><span class="sxs-lookup"><span data-stu-id="006fe-104">Set operations in LINQ refer to query operations that produce a result set that is based on the presence or absence of equivalent elements within the same or separate collections (or sets).</span></span>  
  
 <span data-ttu-id="006fe-105">Методы стандартных операторов запросов, которые выполняют операции над множествами, перечислены в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="006fe-105">The standard query operator methods that perform set operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="006fe-106">Методы</span><span class="sxs-lookup"><span data-stu-id="006fe-106">Methods</span></span>  
  
|<span data-ttu-id="006fe-107">Имя метода</span><span class="sxs-lookup"><span data-stu-id="006fe-107">Method Name</span></span>|<span data-ttu-id="006fe-108">Описание</span><span class="sxs-lookup"><span data-stu-id="006fe-108">Description</span></span>|<span data-ttu-id="006fe-109">Синтаксис выражения запроса C#</span><span class="sxs-lookup"><span data-stu-id="006fe-109">C# Query Expression Syntax</span></span>|<span data-ttu-id="006fe-110">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="006fe-110">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="006fe-111">Distinct</span><span class="sxs-lookup"><span data-stu-id="006fe-111">Distinct</span></span>|<span data-ttu-id="006fe-112">Удаляет повторяющиеся значения из коллекции.</span><span class="sxs-lookup"><span data-stu-id="006fe-112">Removes duplicate values from a collection.</span></span>|<span data-ttu-id="006fe-113">Не применяется</span><span class="sxs-lookup"><span data-stu-id="006fe-113">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Distinct%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="006fe-114">Исключения</span><span class="sxs-lookup"><span data-stu-id="006fe-114">Except</span></span>|<span data-ttu-id="006fe-115">Возвращает разность множеств, т. е. элементы одной коллекции, которые отсутствуют во второй.</span><span class="sxs-lookup"><span data-stu-id="006fe-115">Returns the set difference, which means the elements of one collection that do not appear in a second collection.</span></span>|<span data-ttu-id="006fe-116">Не применяется</span><span class="sxs-lookup"><span data-stu-id="006fe-116">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Except%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="006fe-117">Пересечение</span><span class="sxs-lookup"><span data-stu-id="006fe-117">Intersect</span></span>|<span data-ttu-id="006fe-118">Возвращает пересечение множеств, т. е. элементы, присутствующие в каждой из двух коллекций.</span><span class="sxs-lookup"><span data-stu-id="006fe-118">Returns the set intersection, which means elements that appear in each of two collections.</span></span>|<span data-ttu-id="006fe-119">Не применяется</span><span class="sxs-lookup"><span data-stu-id="006fe-119">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Intersect%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="006fe-120">Объединение</span><span class="sxs-lookup"><span data-stu-id="006fe-120">Union</span></span>|<span data-ttu-id="006fe-121">Возвращает объединение множеств, т. е. уникальные элементы, присутствующие в одной из двух коллекций.</span><span class="sxs-lookup"><span data-stu-id="006fe-121">Returns the set union, which means unique elements that appear in either of two collections.</span></span>|<span data-ttu-id="006fe-122">Не применяется</span><span class="sxs-lookup"><span data-stu-id="006fe-122">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Union%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Union%2A?displayProperty=nameWithType>|  
  
## <a name="comparison-of-set-operations"></a><span data-ttu-id="006fe-123">Сравнение операций над множествами</span><span class="sxs-lookup"><span data-stu-id="006fe-123">Comparison of Set Operations</span></span>  
  
### <a name="distinct"></a><span data-ttu-id="006fe-124">Distinct</span><span class="sxs-lookup"><span data-stu-id="006fe-124">Distinct</span></span>  
 <span data-ttu-id="006fe-125">В следующем примере показано поведение метода <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType> применительно к последовательности символов.</span><span class="sxs-lookup"><span data-stu-id="006fe-125">The following example depicts the behavior of the <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType> method on a sequence of characters.</span></span> <span data-ttu-id="006fe-126">Возвращаемая последовательность содержит уникальные элементы из входной последовательности.</span><span class="sxs-lookup"><span data-stu-id="006fe-126">The returned sequence contains the unique elements from the input sequence.</span></span>  
  
 ![График, демонстрирующий поведение Distinct&#40;&#41;.](./media/set-operations/distinct-method-behavior.png)  

 [!code-csharp-interactive[Distinct](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQSetOperation/CS/SetOperation.cs#1)]
  
### <a name="except"></a><span data-ttu-id="006fe-128">Исключения</span><span class="sxs-lookup"><span data-stu-id="006fe-128">Except</span></span>  
 <span data-ttu-id="006fe-129">В следующем примере показано поведение <xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="006fe-129">The following example depicts the behavior of <xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="006fe-130">Возвращаемая последовательность содержит только те элементы из первой входной последовательности, которых нет во второй.</span><span class="sxs-lookup"><span data-stu-id="006fe-130">The returned sequence contains only the elements from the first input sequence that are not in the second input sequence.</span></span>  
  
 <span data-ttu-id="006fe-131">![График, отображающий действие Except&#40;&#41;.](./media/set-operations/except-behavior-graphic.png "Демонстрирует поведение Except.")</span><span class="sxs-lookup"><span data-stu-id="006fe-131">![Graphic showing the action of Except&#40;&#41;.](./media/set-operations/except-behavior-graphic.png "Shows the behavior of Except.")</span></span>  
  
[!code-csharp-interactive[Except](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQSetOperation/CS/SetOperation.cs#2)]

### <a name="intersect"></a><span data-ttu-id="006fe-132">Пересечение</span><span class="sxs-lookup"><span data-stu-id="006fe-132">Intersect</span></span>  
 <span data-ttu-id="006fe-133">В следующем примере показано поведение <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="006fe-133">The following example depicts the behavior of <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="006fe-134">Возвращаемая последовательность содержит элементы, общие для обеих входных последовательностей.</span><span class="sxs-lookup"><span data-stu-id="006fe-134">The returned sequence contains the elements that are common to both of the input sequences.</span></span>  
  
 ![График, отображающий пересечение двух последовательностей.](./media/set-operations/intersection-two-sequences.png)  

[!code-csharp-interactive[Intersect](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQSetOperation/CS/SetOperation.cs#3)]

### <a name="union"></a><span data-ttu-id="006fe-136">Объединение</span><span class="sxs-lookup"><span data-stu-id="006fe-136">Union</span></span>  
 <span data-ttu-id="006fe-137">В следующем примере показана операция объединения двух последовательностей символов.</span><span class="sxs-lookup"><span data-stu-id="006fe-137">The following example depicts a union operation on two sequences of characters.</span></span> <span data-ttu-id="006fe-138">Возвращаемая последовательность содержит уникальные элементы из обеих входных последовательностей.</span><span class="sxs-lookup"><span data-stu-id="006fe-138">The returned sequence contains the unique elements from both input sequences.</span></span>  
  
 ![График, показывающий объединение двух последовательностей.](./media/set-operations/union-operation-two-sequences.png)  

[!code-csharp-interactive[Union](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQSetOperation/CS/SetOperation.cs#4)]

## <a name="see-also"></a><span data-ttu-id="006fe-140">См. также</span><span class="sxs-lookup"><span data-stu-id="006fe-140">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="006fe-141">Общие сведения о стандартных операторах запроса (C#)</span><span class="sxs-lookup"><span data-stu-id="006fe-141">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
- [<span data-ttu-id="006fe-142">Практическое руководство. Объединение и сравнение коллекций строк (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="006fe-142">How to combine and compare string collections (LINQ) (C#)</span></span>](./how-to-combine-and-compare-string-collections-linq.md)
- [<span data-ttu-id="006fe-143">Нахождение разности множеств между двумя списками (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="006fe-143">How to find the set difference between two lists (LINQ) (C#)</span></span>](./how-to-find-the-set-difference-between-two-lists-linq.md)
