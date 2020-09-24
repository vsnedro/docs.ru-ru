---
title: Примеры синтаксиса выражений запросов. Операторы статистических выражений
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d729120c-4c1b-4f34-bbe9-33694fca2dde
ms.openlocfilehash: 4842bdb3aeb024afc72bde43d056b48b0d8258b8
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91153005"
---
# <a name="query-expression-syntax-examples-aggregate-operators"></a><span data-ttu-id="8afc7-102">Примеры синтаксиса выражений запросов. Операторы статистических выражений</span><span class="sxs-lookup"><span data-stu-id="8afc7-102">Query Expression Syntax Examples: Aggregate Operators</span></span>

<span data-ttu-id="8afc7-103">В примерах этого раздела показано, как использовать <xref:System.Linq.Enumerable.Average%2A> методы, <xref:System.Linq.Enumerable.Count%2A> , <xref:System.Linq.Enumerable.Max%2A> , <xref:System.Linq.Enumerable.Min%2A> и <xref:System.Linq.Enumerable.Sum%2A> для запроса [модели AdventureWorks Sales](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) с помощью синтаксиса выражений запросов.</span><span class="sxs-lookup"><span data-stu-id="8afc7-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A>, and <xref:System.Linq.Enumerable.Sum%2A> methods to query the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) using query expression syntax.</span></span> <span data-ttu-id="8afc7-104">Модель AdventureWorks Sales, которая используется в этих примерах, состоит из таблиц Contact, Address, Product, SalesOrderHeader и SalesOrderDetail образца базы данных AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="8afc7-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="8afc7-105">В примерах этого раздела используются следующие `using` / `Imports` инструкции:</span><span class="sxs-lookup"><span data-stu-id="8afc7-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="average"></a><span data-ttu-id="8afc7-106">Среднее значение</span><span class="sxs-lookup"><span data-stu-id="8afc7-106">Average</span></span>  
  
### <a name="example"></a><span data-ttu-id="8afc7-107">Пример</span><span class="sxs-lookup"><span data-stu-id="8afc7-107">Example</span></span>  

 <span data-ttu-id="8afc7-108">В следующем примере используется метод <xref:System.Linq.Enumerable.Average%2A> для нахождения средней цены по прейскуранту для продуктов каждого типа.</span><span class="sxs-lookup"><span data-stu-id="8afc7-108">The following example uses the <xref:System.Linq.Enumerable.Average%2A> method to find the average list price of the products of each style.</span></span>  
  
 [!code-csharp[DP L2E Examples#Average2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#average2_mq)]
 [!code-vb[DP L2E Examples#Average2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#average2_mq)]  
  
### <a name="example"></a><span data-ttu-id="8afc7-109">Пример</span><span class="sxs-lookup"><span data-stu-id="8afc7-109">Example</span></span>  

 <span data-ttu-id="8afc7-110">В следующем примере для получения средней суммы заказа для каждого идентификатора контактного лица используется метод <xref:System.Linq.Enumerable.Average%2A>.</span><span class="sxs-lookup"><span data-stu-id="8afc7-110">The following example uses <xref:System.Linq.Enumerable.Average%2A> to get the average total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#AverageGrouped_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#averagegrouped_mq)]
 [!code-vb[DP L2E Examples#AverageGrouped_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#averagegrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="8afc7-111">Пример</span><span class="sxs-lookup"><span data-stu-id="8afc7-111">Example</span></span>  

 <span data-ttu-id="8afc7-112">В следующем примере для получения заказов со средней суммой заказа для каждого идентификатора контактного лица используется метод <xref:System.Linq.Enumerable.Average%2A>.</span><span class="sxs-lookup"><span data-stu-id="8afc7-112">The following example uses <xref:System.Linq.Enumerable.Average%2A> to get the orders with the average total due for each contact.</span></span>  
  
 [!code-csharp[DP L2E Examples#AverageElements_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#averageelements_mq)]
 [!code-vb[DP L2E Examples#AverageElements_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#averageelements_mq)]  
  
## <a name="count"></a><span data-ttu-id="8afc7-113">Count</span><span class="sxs-lookup"><span data-stu-id="8afc7-113">Count</span></span>  
  
### <a name="example"></a><span data-ttu-id="8afc7-114">Пример</span><span class="sxs-lookup"><span data-stu-id="8afc7-114">Example</span></span>  

 <span data-ttu-id="8afc7-115">В следующем примере метод <xref:System.Linq.Enumerable.Count%2A> используется, чтобы возвратить список идентификаторов контактных лиц, а также информацию о том, сколько заказов у каждого из них.</span><span class="sxs-lookup"><span data-stu-id="8afc7-115">The following example uses <xref:System.Linq.Enumerable.Count%2A> to return a list of contact IDs and how many orders each has.</span></span>  
  
 [!code-csharp[DP L2E Examples#CountNested](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#countnested)]
 [!code-vb[DP L2E Examples#CountNested](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#countnested)]  
  
### <a name="example"></a><span data-ttu-id="8afc7-116">Пример</span><span class="sxs-lookup"><span data-stu-id="8afc7-116">Example</span></span>  

 <span data-ttu-id="8afc7-117">В следующем примере продукты группируются по цвету, а метод <xref:System.Linq.Enumerable.Count%2A> используется в нем для возврата числа продуктов в каждой цветовой группе.</span><span class="sxs-lookup"><span data-stu-id="8afc7-117">The following example groups products by color and uses <xref:System.Linq.Enumerable.Count%2A> to return the number of products in each color group.</span></span>  
  
 [!code-csharp[DP L2E Examples#CountGrouped](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#countgrouped)]
 [!code-vb[DP L2E Examples#CountGrouped](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#countgrouped)]  
  
## <a name="max"></a><span data-ttu-id="8afc7-118">Макс.</span><span class="sxs-lookup"><span data-stu-id="8afc7-118">Max</span></span>  
  
### <a name="example"></a><span data-ttu-id="8afc7-119">Пример</span><span class="sxs-lookup"><span data-stu-id="8afc7-119">Example</span></span>  

 <span data-ttu-id="8afc7-120">В следующем примере используется метод <xref:System.Linq.Enumerable.Max%2A> для получения наибольшей суммы заказа для каждого идентификатора контактного лица.</span><span class="sxs-lookup"><span data-stu-id="8afc7-120">The following example uses the <xref:System.Linq.Enumerable.Max%2A> method to get the largest total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#MaxGrouped_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#maxgrouped_mq)]
 [!code-vb[DP L2E Examples#MaxGrouped_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#maxgrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="8afc7-121">Пример</span><span class="sxs-lookup"><span data-stu-id="8afc7-121">Example</span></span>  

 <span data-ttu-id="8afc7-122">В следующем примере используется метод <xref:System.Linq.Enumerable.Max%2A> для получения наибольшей суммы заказа для каждого идентификатора контактного лица.</span><span class="sxs-lookup"><span data-stu-id="8afc7-122">The following example uses the <xref:System.Linq.Enumerable.Max%2A> method to get the orders with the largest total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#MaxElements_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#maxelements_mq)]
 [!code-vb[DP L2E Examples#MaxElements_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#maxelements_mq)]  
  
## <a name="min"></a><span data-ttu-id="8afc7-123">Min</span><span class="sxs-lookup"><span data-stu-id="8afc7-123">Min</span></span>  
  
### <a name="example"></a><span data-ttu-id="8afc7-124">Пример</span><span class="sxs-lookup"><span data-stu-id="8afc7-124">Example</span></span>  

 <span data-ttu-id="8afc7-125">В следующем примере используется метод <xref:System.Linq.Enumerable.Min%2A> для получения заказов с наименьшей суммы заказа для каждого идентификатора контактного лица.</span><span class="sxs-lookup"><span data-stu-id="8afc7-125">The following example uses the <xref:System.Linq.Enumerable.Min%2A> method to get the smallest total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#MinGrouped_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#mingrouped_mq)]
 [!code-vb[DP L2E Examples#MinGrouped_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#mingrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="8afc7-126">Пример</span><span class="sxs-lookup"><span data-stu-id="8afc7-126">Example</span></span>  

 <span data-ttu-id="8afc7-127">В следующем примере используется метод <xref:System.Linq.Enumerable.Min%2A> для получения заказов с наименьшей суммы заказа для каждого идентификатора контактного лица.</span><span class="sxs-lookup"><span data-stu-id="8afc7-127">The following example uses the <xref:System.Linq.Enumerable.Min%2A> method to get the orders with the smallest total due for each contact.</span></span>  
  
 [!code-csharp[DP L2E Examples#MinElements_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#minelements_mq)]
 [!code-vb[DP L2E Examples#MinElements_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#minelements_mq)]  
  
## <a name="sum"></a><span data-ttu-id="8afc7-128">SUM</span><span class="sxs-lookup"><span data-stu-id="8afc7-128">Sum</span></span>  
  
### <a name="example"></a><span data-ttu-id="8afc7-129">Пример</span><span class="sxs-lookup"><span data-stu-id="8afc7-129">Example</span></span>  

 <span data-ttu-id="8afc7-130">В следующем примере используется метод <xref:System.Linq.Enumerable.Sum%2A> для получения суммы заказа для каждого идентификатора контактного лица.</span><span class="sxs-lookup"><span data-stu-id="8afc7-130">The following example uses the <xref:System.Linq.Enumerable.Sum%2A> method to get the total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#SumGrouped_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#sumgrouped_mq)]
 [!code-vb[DP L2E Examples#SumGrouped_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#sumgrouped_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="8afc7-131">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="8afc7-131">See also</span></span>

- [<span data-ttu-id="8afc7-132">Запросы в LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="8afc7-132">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
