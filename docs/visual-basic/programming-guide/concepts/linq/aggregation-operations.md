---
title: Операции агрегирования
ms.date: 07/20/2015
ms.assetid: 0f47e92c-5dd2-4007-baf4-c5fe5dc3b4a8
ms.openlocfilehash: 8e2c9698de67dc4def348a03c9d69713a6130f31
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84383797"
---
# <a name="aggregation-operations-visual-basic"></a><span data-ttu-id="a8736-102">Операции агрегирования (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a8736-102">Aggregation Operations (Visual Basic)</span></span>
<span data-ttu-id="a8736-103">Статистическая операция вычисляет одно значение по коллекции значений.</span><span class="sxs-lookup"><span data-stu-id="a8736-103">An aggregation operation computes a single value from a collection of values.</span></span> <span data-ttu-id="a8736-104">Например, статистической обработкой является вычисление средней дневной температуры с использованием значений дневной температуры за месяц.</span><span class="sxs-lookup"><span data-stu-id="a8736-104">An example of an aggregation operation is calculating the average daily temperature from a month's worth of daily temperature values.</span></span>  
  
 <span data-ttu-id="a8736-105">На приведенном ниже рисунке показаны результаты двух различных операций агрегирования с последовательностью чисел.</span><span class="sxs-lookup"><span data-stu-id="a8736-105">The following illustration shows the results of two different aggregation operations on a sequence of numbers.</span></span> <span data-ttu-id="a8736-106">Первая операция суммирует числа.</span><span class="sxs-lookup"><span data-stu-id="a8736-106">The first operation sums the numbers.</span></span> <span data-ttu-id="a8736-107">Вторая операция возвращает максимальное значение в последовательности.</span><span class="sxs-lookup"><span data-stu-id="a8736-107">The second operation returns the maximum value in the sequence.</span></span>  
  
 ![Рисунок, показывающий операции агрегирования LINQ.](./media/aggregation-operations/linq-aggregation-operations.png)  
  
 <span data-ttu-id="a8736-109">В следующем разделе перечислены методы стандартных операторов запросов, которые выполняют операции агрегирования.</span><span class="sxs-lookup"><span data-stu-id="a8736-109">The standard query operator methods that perform aggregation operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a8736-110">Методы</span><span class="sxs-lookup"><span data-stu-id="a8736-110">Methods</span></span>  
  
|<span data-ttu-id="a8736-111">Имя метода</span><span class="sxs-lookup"><span data-stu-id="a8736-111">Method Name</span></span>|<span data-ttu-id="a8736-112">Описание:</span><span class="sxs-lookup"><span data-stu-id="a8736-112">Description</span></span>|<span data-ttu-id="a8736-113">Синтаксис выражения запроса Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a8736-113">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="a8736-114">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="a8736-114">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="a8736-115">Aggregate</span><span class="sxs-lookup"><span data-stu-id="a8736-115">Aggregate</span></span>|<span data-ttu-id="a8736-116">Выполняет пользовательскую операцию агрегирования со значениями коллекции.</span><span class="sxs-lookup"><span data-stu-id="a8736-116">Performs a custom aggregation operation on the values of a collection.</span></span>|<span data-ttu-id="a8736-117">Не применяется</span><span class="sxs-lookup"><span data-stu-id="a8736-117">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Aggregate%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Aggregate%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="a8736-118">Среднее значение</span><span class="sxs-lookup"><span data-stu-id="a8736-118">Average</span></span>|<span data-ttu-id="a8736-119">Вычисляет среднее значение коллекции значений.</span><span class="sxs-lookup"><span data-stu-id="a8736-119">Calculates the average value of a collection of values.</span></span>|`Aggregate … In … Into Average()`|<xref:System.Linq.Enumerable.Average%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Average%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="a8736-120">Count</span><span class="sxs-lookup"><span data-stu-id="a8736-120">Count</span></span>|<span data-ttu-id="a8736-121">Подсчитывает число элементов в коллекции (при необходимости только те элементы, которые удовлетворяют функции предиката).</span><span class="sxs-lookup"><span data-stu-id="a8736-121">Counts the elements in a collection, optionally only those elements that satisfy a predicate function.</span></span>|`Aggregate … In … Into Count()`|<xref:System.Linq.Enumerable.Count%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Count%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="a8736-122">LongCount</span><span class="sxs-lookup"><span data-stu-id="a8736-122">LongCount</span></span>|<span data-ttu-id="a8736-123">Подсчитывает число элементов в большой коллекции (при необходимости только те элементы, которые удовлетворяют функции предиката).</span><span class="sxs-lookup"><span data-stu-id="a8736-123">Counts the elements in a large collection, optionally only those elements that satisfy a predicate function.</span></span>|`Aggregate … In … Into LongCount()`|<xref:System.Linq.Enumerable.LongCount%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.LongCount%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="a8736-124">Max</span><span class="sxs-lookup"><span data-stu-id="a8736-124">Max</span></span>|<span data-ttu-id="a8736-125">Определяет максимальное значение в коллекции.</span><span class="sxs-lookup"><span data-stu-id="a8736-125">Determines the maximum value in a collection.</span></span>|`Aggregate … In … Into Max()`|<xref:System.Linq.Enumerable.Max%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Max%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="a8736-126">Min</span><span class="sxs-lookup"><span data-stu-id="a8736-126">Min</span></span>|<span data-ttu-id="a8736-127">Определяет минимальное значение в коллекции.</span><span class="sxs-lookup"><span data-stu-id="a8736-127">Determines the minimum value in a collection.</span></span>|`Aggregate … In … Into Min()`|<xref:System.Linq.Enumerable.Min%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Min%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="a8736-128">Сумма</span><span class="sxs-lookup"><span data-stu-id="a8736-128">Sum</span></span>|<span data-ttu-id="a8736-129">Вычисляет сумму значений в коллекции.</span><span class="sxs-lookup"><span data-stu-id="a8736-129">Calculates the sum of the values in a collection.</span></span>|`Aggregate … In … Into Sum()`|<xref:System.Linq.Enumerable.Sum%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Sum%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="a8736-130">Примеры синтаксиса выражений запросов</span><span class="sxs-lookup"><span data-stu-id="a8736-130">Query Expression Syntax Examples</span></span>  
  
### <a name="average"></a><span data-ttu-id="a8736-131">Среднее</span><span class="sxs-lookup"><span data-stu-id="a8736-131">Average</span></span>  
 <span data-ttu-id="a8736-132">В следующем примере кода используется `Aggregate Into Average` предложение в Visual Basic для вычисления средней температуры в массиве чисел, представляющих температуру.</span><span class="sxs-lookup"><span data-stu-id="a8736-132">The following code example uses the `Aggregate Into Average` clause in Visual Basic to calculate the average temperature in an array of numbers that represent temperatures.</span></span>  
  
 [!code-vb[CsLINQAggregating#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#1)]  
  
### <a name="count"></a><span data-ttu-id="a8736-133">Count</span><span class="sxs-lookup"><span data-stu-id="a8736-133">Count</span></span>  
 <span data-ttu-id="a8736-134">В следующем примере кода используется `Aggregate Into Count` предложение в Visual Basic для подсчета количества значений в массиве, которые больше или равны 80.</span><span class="sxs-lookup"><span data-stu-id="a8736-134">The following code example uses the `Aggregate Into Count` clause in Visual Basic to count the number of values in an array that are greater than or equal to 80.</span></span>  
  
 [!code-vb[CsLINQAggregating#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#2)]  
  
### <a name="longcount"></a><span data-ttu-id="a8736-135">LongCount</span><span class="sxs-lookup"><span data-stu-id="a8736-135">LongCount</span></span>  
 <span data-ttu-id="a8736-136">В следующем примере кода предложение используется `Aggregate Into LongCount` для подсчета количества значений в массиве.</span><span class="sxs-lookup"><span data-stu-id="a8736-136">The following code example uses the `Aggregate Into LongCount` clause to count the number of values in an array.</span></span>  
  
 [!code-vb[CsLINQAggregating#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#3)]  
  
### <a name="max"></a><span data-ttu-id="a8736-137">Max</span><span class="sxs-lookup"><span data-stu-id="a8736-137">Max</span></span>  
 <span data-ttu-id="a8736-138">В следующем примере кода предложение используется `Aggregate Into Max` для вычисления максимальной температуры в массиве чисел, представляющих температуру.</span><span class="sxs-lookup"><span data-stu-id="a8736-138">The following code example uses the `Aggregate Into Max` clause  to calculate the maximum temperature in an array of numbers that represent temperatures.</span></span>  
  
 [!code-vb[CsLINQAggregating#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#4)]  
  
### <a name="min"></a><span data-ttu-id="a8736-139">Min</span><span class="sxs-lookup"><span data-stu-id="a8736-139">Min</span></span>  
 <span data-ttu-id="a8736-140">В следующем примере кода предложение используется `Aggregate Into Min` для вычисления минимальной температуры в массиве чисел, представляющих температуру.</span><span class="sxs-lookup"><span data-stu-id="a8736-140">The following code example uses the `Aggregate Into Min` clause  to calculate the minimum temperature in an array of numbers that represent temperatures.</span></span>  
  
 [!code-vb[CsLINQAggregating#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#5)]  
  
### <a name="sum"></a><span data-ttu-id="a8736-141">Сумма</span><span class="sxs-lookup"><span data-stu-id="a8736-141">Sum</span></span>  
 <span data-ttu-id="a8736-142">В следующем примере кода предложение используется `Aggregate Into Sum` для вычисления общей суммы расходов из массива значений, представляющих расходы.</span><span class="sxs-lookup"><span data-stu-id="a8736-142">The following code example uses the `Aggregate Into Sum` clause  to calculate the total expense amount from an array of values that represent expenses.</span></span>  
  
 [!code-vb[CsLINQAggregating#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="a8736-143">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="a8736-143">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="a8736-144">Общие сведения о стандартных операторах запроса (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a8736-144">Standard Query Operators Overview (Visual Basic)</span></span>](standard-query-operators-overview.md)
- [<span data-ttu-id="a8736-145">Aggregate Clause</span><span class="sxs-lookup"><span data-stu-id="a8736-145">Aggregate Clause</span></span>](../../../language-reference/queries/aggregate-clause.md)
- [<span data-ttu-id="a8736-146">Руководство. Вычисление значений столбцов в текстовом файле CSV (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a8736-146">How to: Compute Column Values in a CSV Text File (LINQ) (Visual Basic)</span></span>](how-to-compute-column-values-in-a-csv-text-file-linq.md)
- <span data-ttu-id="a8736-147">[How to: Count, Sum, or Average Data](../../language-features/linq/how-to-count-sum-or-average-data-by-using-linq.md) (Практическое руководство. Выполнение функций Count, Sum и Average)</span><span class="sxs-lookup"><span data-stu-id="a8736-147">[How to: Count, Sum, or Average Data](../../language-features/linq/how-to-count-sum-or-average-data-by-using-linq.md)</span></span>
- <span data-ttu-id="a8736-148">[How to: Find the Minimum or Maximum Value in a Query Result](../../language-features/linq/how-to-find-the-minimum-or-maximum-value-in-a-query-result.md) (Практическое руководство. Нахождение минимального или максимального значения в результатах запроса)</span><span class="sxs-lookup"><span data-stu-id="a8736-148">[How to: Find the Minimum or Maximum Value in a Query Result](../../language-features/linq/how-to-find-the-minimum-or-maximum-value-in-a-query-result.md)</span></span>
- [<span data-ttu-id="a8736-149">Практическое руководство. Запрос самого большого файла или файлов в дереве папок (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a8736-149">How to: Query for the Largest File or Files in a Directory Tree (LINQ) (Visual Basic)</span></span>](how-to-query-for-the-largest-file-or-files-in-a-directory-tree.md)
- [<span data-ttu-id="a8736-150">Как запросить общее число байтов в наборе папок (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a8736-150">How to: Query for the Total Number of Bytes in a Set of Folders (LINQ) (Visual Basic)</span></span>](how-to-query-for-the-total-number-of-bytes-in-a-set-of-folders.md)
