---
title: Примеры синтаксиса выражений запроса. Операторы статистических выражений (LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 85dafa07-e102-46e7-ab78-37bf06f257a6
ms.openlocfilehash: 2277058c4dad4632f4f47a39e32463eaf77dcd5e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91164575"
---
# <a name="query-expression-syntax-examples-aggregate-operators-linq-to-dataset"></a><span data-ttu-id="b3424-102">Примеры синтаксиса выражений запроса. Операторы статистических выражений (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="b3424-102">Query Expression Syntax Examples: Aggregate Operators (LINQ to DataSet)</span></span>

<span data-ttu-id="b3424-103">Примеры в данном разделе демонстрируют, как применять методы <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A> и <xref:System.Linq.Enumerable.Sum%2A> для запроса к объекту <xref:System.Data.DataSet> и статистической обработки данных с использованием синтаксиса выражений запросов.</span><span class="sxs-lookup"><span data-stu-id="b3424-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A>, and <xref:System.Linq.Enumerable.Sum%2A> methods to query a <xref:System.Data.DataSet> and aggregate data using query expression syntax.</span></span>  
  
 <span data-ttu-id="b3424-104">`FillDataSet`Метод, используемый в этих примерах, задается при [загрузке данных в набор данных](loading-data-into-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="b3424-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="b3424-105">В примерах данного раздела используются таблицы Contact, Address, Product, SalesOrderHeader и SalesOrderDetail из образца базы данных AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="b3424-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="b3424-106">В примерах этого раздела используются следующие `using` / `Imports` инструкции:</span><span class="sxs-lookup"><span data-stu-id="b3424-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="b3424-107">Дополнительные сведения см. в разделе [инструкции. Создание проекта LINQ to DataSet в Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md).</span><span class="sxs-lookup"><span data-stu-id="b3424-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="average"></a><span data-ttu-id="b3424-108">Среднее значение</span><span class="sxs-lookup"><span data-stu-id="b3424-108">Average</span></span>  
  
### <a name="example"></a><span data-ttu-id="b3424-109">Пример</span><span class="sxs-lookup"><span data-stu-id="b3424-109">Example</span></span>  

 <span data-ttu-id="b3424-110">В этом примере используется метод <xref:System.Linq.Enumerable.Average%2A> для поиска среднесписочной цены продуктов каждого стиля.</span><span class="sxs-lookup"><span data-stu-id="b3424-110">This example uses the <xref:System.Linq.Enumerable.Average%2A> method to find the average list price of the products of each style.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Average2_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#average2_mq)]
 [!code-vb[DP LINQ to DataSet Examples#Average2_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#average2_mq)]  
  
### <a name="example"></a><span data-ttu-id="b3424-111">Пример</span><span class="sxs-lookup"><span data-stu-id="b3424-111">Example</span></span>  

 <span data-ttu-id="b3424-112">В этом примере метод <xref:System.Linq.Enumerable.Average%2A> используется для получения средней суммы заказа по каждому идентификатору контактного лица.</span><span class="sxs-lookup"><span data-stu-id="b3424-112">This example uses <xref:System.Linq.Enumerable.Average%2A> to get the average total due for each contact ID.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#AverageGrouped_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#averagegrouped_mq)]
 [!code-vb[DP LINQ to DataSet Examples#AverageGrouped_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#averagegrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="b3424-113">Пример</span><span class="sxs-lookup"><span data-stu-id="b3424-113">Example</span></span>  

 <span data-ttu-id="b3424-114">В этом примере метод <xref:System.Linq.Enumerable.Average%2A> используется для получения заказов со средним значением `TotalDue` для каждого контакта.</span><span class="sxs-lookup"><span data-stu-id="b3424-114">This example uses <xref:System.Linq.Enumerable.Average%2A> to get the orders with the average `TotalDue` for each contact.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#AverageElements_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#averageelements_mq)]
 [!code-vb[DP LINQ to DataSet Examples#AverageElements_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#averageelements_mq)]  
  
## <a name="count"></a><span data-ttu-id="b3424-115">Count</span><span class="sxs-lookup"><span data-stu-id="b3424-115">Count</span></span>  
  
### <a name="example"></a><span data-ttu-id="b3424-116">Пример</span><span class="sxs-lookup"><span data-stu-id="b3424-116">Example</span></span>  

 <span data-ttu-id="b3424-117">В этом примере метод <xref:System.Linq.Enumerable.Count%2A> используется для возвращения списка идентификаторов контактного лица и количества заказов для каждого контактного лица.</span><span class="sxs-lookup"><span data-stu-id="b3424-117">This example uses <xref:System.Linq.Enumerable.Count%2A> to return a list of contact IDs and how many orders each has.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#CountNested](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#countnested)]
 [!code-vb[DP LINQ to DataSet Examples#CountNested](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#countnested)]  
  
### <a name="example"></a><span data-ttu-id="b3424-118">Пример</span><span class="sxs-lookup"><span data-stu-id="b3424-118">Example</span></span>  

 <span data-ttu-id="b3424-119">В этом примере продукты группируются по цветам и метод <xref:System.Linq.Enumerable.Count%2A> используется для возвращения количества продуктов в каждой цветовой группе.</span><span class="sxs-lookup"><span data-stu-id="b3424-119">This example groups products by color and uses <xref:System.Linq.Enumerable.Count%2A> to return the number of products in each color group.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#CountGrouped](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#countgrouped)]
 [!code-vb[DP LINQ to DataSet Examples#CountGrouped](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#countgrouped)]  
  
## <a name="max"></a><span data-ttu-id="b3424-120">Макс.</span><span class="sxs-lookup"><span data-stu-id="b3424-120">Max</span></span>  
  
### <a name="example"></a><span data-ttu-id="b3424-121">Пример</span><span class="sxs-lookup"><span data-stu-id="b3424-121">Example</span></span>  

 <span data-ttu-id="b3424-122">В этом примере используется метод <xref:System.Linq.Enumerable.Max%2A> для получения наибольшей общей выплаты для каждого идентификатора контакта.</span><span class="sxs-lookup"><span data-stu-id="b3424-122">This example uses the <xref:System.Linq.Enumerable.Max%2A> method to get the largest total due for each contact ID.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#MaxGrouped_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#maxgrouped_mq)]
 [!code-vb[DP LINQ to DataSet Examples#MaxGrouped_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#maxgrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="b3424-123">Пример</span><span class="sxs-lookup"><span data-stu-id="b3424-123">Example</span></span>  

 <span data-ttu-id="b3424-124">В этом примере используется метод <xref:System.Linq.Enumerable.Max%2A> для получения заказов с наибольшим значением `TotalDue` для каждого идентификатора контакта.</span><span class="sxs-lookup"><span data-stu-id="b3424-124">This example uses the <xref:System.Linq.Enumerable.Max%2A> method to get the orders with the largest `TotalDue` for each contact ID.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#MaxElements_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#maxelements_mq)]
 [!code-vb[DP LINQ to DataSet Examples#MaxElements_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#maxelements_mq)]  
  
## <a name="min"></a><span data-ttu-id="b3424-125">Min</span><span class="sxs-lookup"><span data-stu-id="b3424-125">Min</span></span>  
  
### <a name="example"></a><span data-ttu-id="b3424-126">Пример</span><span class="sxs-lookup"><span data-stu-id="b3424-126">Example</span></span>  

 <span data-ttu-id="b3424-127">В этом примере используется метод <xref:System.Linq.Enumerable.Min%2A> для получения наименьшей общей выплаты для каждого идентификатора контакта.</span><span class="sxs-lookup"><span data-stu-id="b3424-127">This example uses the <xref:System.Linq.Enumerable.Min%2A> method to get the smallest total due for each contact ID.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#MinGrouped_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#mingrouped_mq)]
 [!code-vb[DP LINQ to DataSet Examples#MinGrouped_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#mingrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="b3424-128">Пример</span><span class="sxs-lookup"><span data-stu-id="b3424-128">Example</span></span>  

 <span data-ttu-id="b3424-129">В этом примере используется метод <xref:System.Linq.Enumerable.Min%2A> для получения заказов с наименьшей общей выплатой для каждого контакта.</span><span class="sxs-lookup"><span data-stu-id="b3424-129">This example uses the <xref:System.Linq.Enumerable.Min%2A> method to get the orders with the smallest total due for each contact.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#MinElements_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#minelements_mq)]
 [!code-vb[DP LINQ to DataSet Examples#MinElements_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#minelements_mq)]  
  
## <a name="sum"></a><span data-ttu-id="b3424-130">SUM</span><span class="sxs-lookup"><span data-stu-id="b3424-130">Sum</span></span>  
  
### <a name="example"></a><span data-ttu-id="b3424-131">Пример</span><span class="sxs-lookup"><span data-stu-id="b3424-131">Example</span></span>  

 <span data-ttu-id="b3424-132">В этом примере используется метод <xref:System.Linq.Enumerable.Sum%2A> для получения общей выплаты по каждому идентификатору контакта.</span><span class="sxs-lookup"><span data-stu-id="b3424-132">This example uses the <xref:System.Linq.Enumerable.Sum%2A> method to get the total due for each contact ID.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#SumGrouped_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#sumgrouped_mq)]
 [!code-vb[DP LINQ to DataSet Examples#SumGrouped_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#sumgrouped_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="b3424-133">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b3424-133">See also</span></span>

- [<span data-ttu-id="b3424-134">Загрузка данных в набор данных</span><span class="sxs-lookup"><span data-stu-id="b3424-134">Loading Data Into a DataSet</span></span>](loading-data-into-a-dataset.md)
- [<span data-ttu-id="b3424-135">Примеры LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="b3424-135">LINQ to DataSet Examples</span></span>](linq-to-dataset-examples.md)
- [<span data-ttu-id="b3424-136">Общие сведения о стандартных операторах запроса (C#)</span><span class="sxs-lookup"><span data-stu-id="b3424-136">Standard Query Operators Overview (C#)</span></span>](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="b3424-137">Общие сведения о стандартных операторах запроса (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b3424-137">Standard Query Operators Overview (Visual Basic)</span></span>](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
