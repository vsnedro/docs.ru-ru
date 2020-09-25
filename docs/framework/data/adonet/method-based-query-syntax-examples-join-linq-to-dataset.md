---
title: Примеры синтаксиса запросов на основе методов. Соединение (LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 4fd5ed2c-b03a-4054-a3ed-3ddb380d7d9d
ms.openlocfilehash: 8bfcd8ae5d81c0d04ca7a43e6d5b25a492266605
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91189348"
---
# <a name="method-based-query-syntax-examples-join-linq-to-dataset"></a><span data-ttu-id="b4df2-102">Примеры синтаксиса запросов на основе методов. Соединение (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="b4df2-102">Method-Based Query Syntax Examples: Join (LINQ to DataSet)</span></span>

<span data-ttu-id="b4df2-103">Соединение - важная операция в запросах, которые обращаются к источникам данных без доступных для навигации взаимосвязей, например к таблицам реляционной базы данных.</span><span class="sxs-lookup"><span data-stu-id="b4df2-103">Joining is an important operation in queries that target data sources that have no navigable relationships to each other, such as relational database tables.</span></span> <span data-ttu-id="b4df2-104">Соединение двух источников данных представляет собой взаимосвязь объектов одного источника данных с объектами, использующими общий атрибут в другом источнике данных.</span><span class="sxs-lookup"><span data-stu-id="b4df2-104">A join of two data sources is the association of objects in one data source with objects that share a common attribute in the other data source.</span></span> <span data-ttu-id="b4df2-105">Дополнительные сведения см. в разделе Общие сведения [о стандартных операторах запросов (C#)](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) или [Общие сведения о стандартных операторах запросов (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md).</span><span class="sxs-lookup"><span data-stu-id="b4df2-105">For more information, see [Standard Query Operators Overview (C#)](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) or [Standard Query Operators Overview (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md).</span></span>  
  
 <span data-ttu-id="b4df2-106">В примерах данного раздела показано, как использовать метод <xref:System.Linq.Enumerable.Join%2A> для запросов к объекту <xref:System.Data.DataSet> с использованием синтаксиса запросов на основе методов.</span><span class="sxs-lookup"><span data-stu-id="b4df2-106">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Join%2A> method to query a <xref:System.Data.DataSet> using the method query syntax.</span></span>  
  
 <span data-ttu-id="b4df2-107">`FillDataSet`Метод, используемый в этих примерах, задается при [загрузке данных в набор данных](loading-data-into-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="b4df2-107">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="b4df2-108">В примерах данного раздела используются таблицы Contact, Address, Product, SalesOrderHeader и SalesOrderDetail из образца базы данных AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="b4df2-108">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="b4df2-109">В примерах этого раздела используются следующие `using` / `Imports` инструкции:</span><span class="sxs-lookup"><span data-stu-id="b4df2-109">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="b4df2-110">Дополнительные сведения см. в разделе [инструкции. Создание проекта LINQ to DataSet в Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md).</span><span class="sxs-lookup"><span data-stu-id="b4df2-110">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="join"></a><span data-ttu-id="b4df2-111">Join</span><span class="sxs-lookup"><span data-stu-id="b4df2-111">Join</span></span>  
  
### <a name="example"></a><span data-ttu-id="b4df2-112">Пример</span><span class="sxs-lookup"><span data-stu-id="b4df2-112">Example</span></span>  

 <span data-ttu-id="b4df2-113">В этом примере выполняется соединение таблиц `Contact` и `SalesOrderHeader`.</span><span class="sxs-lookup"><span data-stu-id="b4df2-113">This example performs a join over the `Contact` and `SalesOrderHeader` tables.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#JoinSimple_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#joinsimple_mq)]
 [!code-vb[DP LINQ to DataSet Examples#JoinSimple_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#joinsimple_mq)]  
  
### <a name="example"></a><span data-ttu-id="b4df2-114">Пример</span><span class="sxs-lookup"><span data-stu-id="b4df2-114">Example</span></span>  

 <span data-ttu-id="b4df2-115">В этом примере выполняется соединение таблиц `Contact` и `SalesOrderHeader`, а результаты группируются по идентификатору контактного лица.</span><span class="sxs-lookup"><span data-stu-id="b4df2-115">This example performs a join over the `Contact` and `SalesOrderHeader` tables, grouping the results by contact ID.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#JoinWithGroupedResults_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#joinwithgroupedresults_mq)]
 [!code-vb[DP LINQ to DataSet Examples#JoinWithGroupedResults_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#joinwithgroupedresults_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="b4df2-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b4df2-116">See also</span></span>

- [<span data-ttu-id="b4df2-117">Загрузка данных в набор данных</span><span class="sxs-lookup"><span data-stu-id="b4df2-117">Loading Data Into a DataSet</span></span>](loading-data-into-a-dataset.md)
- [<span data-ttu-id="b4df2-118">Примеры LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="b4df2-118">LINQ to DataSet Examples</span></span>](linq-to-dataset-examples.md)
- [<span data-ttu-id="b4df2-119">Общие сведения о стандартных операторах запроса (C#)</span><span class="sxs-lookup"><span data-stu-id="b4df2-119">Standard Query Operators Overview (C#)</span></span>](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="b4df2-120">Общие сведения о стандартных операторах запроса (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b4df2-120">Standard Query Operators Overview (Visual Basic)</span></span>](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="b4df2-121">Примеры соединений</span><span class="sxs-lookup"><span data-stu-id="b4df2-121">Join Samples</span></span>](https://go.microsoft.com/fwlink/?LinkId=187357)
- [<span data-ttu-id="b4df2-122">Примеры набора данных</span><span class="sxs-lookup"><span data-stu-id="b4df2-122">Dataset Samples</span></span>](https://go.microsoft.com/fwlink/?LinkId=187358)
