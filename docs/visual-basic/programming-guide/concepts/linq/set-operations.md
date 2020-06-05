---
title: Операции над множествами
ms.date: 07/20/2015
ms.assetid: 2b06e822-e030-438f-9db7-ee402bd3a706
ms.openlocfilehash: b6ff14794343ae7623ee38894cef02cfc0a2a597
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406824"
---
# <a name="set-operations-visual-basic"></a><span data-ttu-id="4d5ad-102">Операции с наборами (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4d5ad-102">Set Operations (Visual Basic)</span></span>

<span data-ttu-id="4d5ad-103">Операции над множествами в LINQ — это операции запросов, результирующие наборы которых основываются на наличии или отсутствии эквивалентных элементов в одной или другой коллекции (или наборе).</span><span class="sxs-lookup"><span data-stu-id="4d5ad-103">Set operations in LINQ refer to query operations that produce a result set that is based on the presence or absence of equivalent elements within the same or separate collections (or sets).</span></span>

<span data-ttu-id="4d5ad-104">Методы стандартных операторов запросов, которые выполняют операции над множествами, перечислены в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="4d5ad-104">The standard query operator methods that perform set operations are listed in the following section.</span></span>

## <a name="methods"></a><span data-ttu-id="4d5ad-105">Методы</span><span class="sxs-lookup"><span data-stu-id="4d5ad-105">Methods</span></span>

|<span data-ttu-id="4d5ad-106">Имя метода</span><span class="sxs-lookup"><span data-stu-id="4d5ad-106">Method Name</span></span>|<span data-ttu-id="4d5ad-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="4d5ad-107">Description</span></span>|<span data-ttu-id="4d5ad-108">Синтаксис выражения запроса Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4d5ad-108">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="4d5ad-109">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="4d5ad-109">More Information</span></span>|
|-----------------|-----------------|------------------------------------------|----------------------|
|<span data-ttu-id="4d5ad-110">Distinct</span><span class="sxs-lookup"><span data-stu-id="4d5ad-110">Distinct</span></span>|<span data-ttu-id="4d5ad-111">Удаляет повторяющиеся значения из коллекции.</span><span class="sxs-lookup"><span data-stu-id="4d5ad-111">Removes duplicate values from a collection.</span></span>|`Distinct`|<xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Distinct%2A?displayProperty=nameWithType>|
|<span data-ttu-id="4d5ad-112">Except</span><span class="sxs-lookup"><span data-stu-id="4d5ad-112">Except</span></span>|<span data-ttu-id="4d5ad-113">Возвращает разность множеств, т. е. элементы одной коллекции, которые отсутствуют во второй.</span><span class="sxs-lookup"><span data-stu-id="4d5ad-113">Returns the set difference, which means the elements of one collection that do not appear in a second collection.</span></span>|<span data-ttu-id="4d5ad-114">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="4d5ad-114">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Except%2A?displayProperty=nameWithType>|
|<span data-ttu-id="4d5ad-115">Intersect</span><span class="sxs-lookup"><span data-stu-id="4d5ad-115">Intersect</span></span>|<span data-ttu-id="4d5ad-116">Возвращает пересечение множеств, т. е. элементы, присутствующие в каждой из двух коллекций.</span><span class="sxs-lookup"><span data-stu-id="4d5ad-116">Returns the set intersection, which means elements that appear in each of two collections.</span></span>|<span data-ttu-id="4d5ad-117">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="4d5ad-117">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Intersect%2A?displayProperty=nameWithType>|
|<span data-ttu-id="4d5ad-118">Union</span><span class="sxs-lookup"><span data-stu-id="4d5ad-118">Union</span></span>|<span data-ttu-id="4d5ad-119">Возвращает объединение множеств, т. е. уникальные элементы, присутствующие в одной из двух коллекций.</span><span class="sxs-lookup"><span data-stu-id="4d5ad-119">Returns the set union, which means unique elements that appear in either of two collections.</span></span>|<span data-ttu-id="4d5ad-120">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="4d5ad-120">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Union%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Union%2A?displayProperty=nameWithType>|

## <a name="comparison-of-set-operations"></a><span data-ttu-id="4d5ad-121">Сравнение операций над множествами</span><span class="sxs-lookup"><span data-stu-id="4d5ad-121">Comparison of Set Operations</span></span>

### <a name="distinct"></a><span data-ttu-id="4d5ad-122">Distinct</span><span class="sxs-lookup"><span data-stu-id="4d5ad-122">Distinct</span></span>

<span data-ttu-id="4d5ad-123">На следующем рисунке показано поведение метода <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType> применительно к последовательности символов.</span><span class="sxs-lookup"><span data-stu-id="4d5ad-123">The following illustration depicts the behavior of the <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType> method on a sequence of characters.</span></span> <span data-ttu-id="4d5ad-124">Возвращаемая последовательность содержит уникальные элементы из входной последовательности.</span><span class="sxs-lookup"><span data-stu-id="4d5ad-124">The returned sequence contains the unique elements from the input sequence.</span></span>

![График, демонстрирующий поведение Distinct&#40;&#41;.](./media/set-operations/distinct-method-behavior.png)

### <a name="except"></a><span data-ttu-id="4d5ad-126">Except</span><span class="sxs-lookup"><span data-stu-id="4d5ad-126">Except</span></span>

<span data-ttu-id="4d5ad-127">На следующем рисунке показано поведение <xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4d5ad-127">The following illustration depicts the behavior of <xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="4d5ad-128">Возвращаемая последовательность содержит только те элементы из первой входной последовательности, которых нет во второй.</span><span class="sxs-lookup"><span data-stu-id="4d5ad-128">The returned sequence contains only the elements from the first input sequence that are not in the second input sequence.</span></span>

<span data-ttu-id="4d5ad-129">![График, отображающий действие Except&#40;&#41;.](./media/set-operations/except-behavior-graphic.png "Демонстрирует поведение Except.")</span><span class="sxs-lookup"><span data-stu-id="4d5ad-129">![Graphic showing the action of Except&#40;&#41;.](./media/set-operations/except-behavior-graphic.png "Shows the behavior of Except.")</span></span>

### <a name="intersect"></a><span data-ttu-id="4d5ad-130">Intersect</span><span class="sxs-lookup"><span data-stu-id="4d5ad-130">Intersect</span></span>

<span data-ttu-id="4d5ad-131">На следующем рисунке показано поведение <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4d5ad-131">The following illustration depicts the behavior of <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="4d5ad-132">Возвращаемая последовательность содержит элементы, общие для обеих входных последовательностей.</span><span class="sxs-lookup"><span data-stu-id="4d5ad-132">The returned sequence contains the elements that are common to both of the input sequences.</span></span>

![График, отображающий пересечение двух последовательностей.](./media/set-operations/intersection-two-sequences.png)

### <a name="union"></a><span data-ttu-id="4d5ad-134">Union</span><span class="sxs-lookup"><span data-stu-id="4d5ad-134">Union</span></span>

<span data-ttu-id="4d5ad-135">На следующем рисунке показана операция объединения двух последовательностей символов.</span><span class="sxs-lookup"><span data-stu-id="4d5ad-135">The following illustration depicts a union operation on two sequences of characters.</span></span> <span data-ttu-id="4d5ad-136">Возвращаемая последовательность содержит уникальные элементы из обеих входных последовательностей.</span><span class="sxs-lookup"><span data-stu-id="4d5ad-136">The returned sequence contains the unique elements from both input sequences.</span></span>

![График, показывающий объединение двух последовательностей.](./media/set-operations/union-operation-two-sequences.png)

## <a name="query-expression-syntax-example"></a><span data-ttu-id="4d5ad-138">Пример синтаксиса выражения запроса</span><span class="sxs-lookup"><span data-stu-id="4d5ad-138">Query Expression Syntax Example</span></span>

<span data-ttu-id="4d5ad-139">В следующем примере `Distinct` предложение в запросе LINQ используется для возврата уникальных чисел из списка целых чисел.</span><span class="sxs-lookup"><span data-stu-id="4d5ad-139">The following example uses the `Distinct` clause in a LINQ query to return the unique numbers from a list of integers.</span></span>

[!code-vb[CsLINQSetOps#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQSetOps/VB/setops.vb#1)]

## <a name="see-also"></a><span data-ttu-id="4d5ad-140">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="4d5ad-140">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="4d5ad-141">Общие сведения о стандартных операторах запроса (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4d5ad-141">Standard Query Operators Overview (Visual Basic)</span></span>](standard-query-operators-overview.md)
- [<span data-ttu-id="4d5ad-142">Предложение Distinct</span><span class="sxs-lookup"><span data-stu-id="4d5ad-142">Distinct Clause</span></span>](../../../language-reference/queries/distinct-clause.md)
- [<span data-ttu-id="4d5ad-143">Практические руководства. объединение и сравнение коллекций строк (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4d5ad-143">How to: Combine and Compare String Collections (LINQ) (Visual Basic)</span></span>](how-to-combine-and-compare-string-collections-linq.md)
- [<span data-ttu-id="4d5ad-144">Как найти разность множеств между двумя списками (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4d5ad-144">How to: Find the Set Difference Between Two Lists (LINQ) (Visual Basic)</span></span>](how-to-find-the-set-difference-between-two-lists-linq.md)
