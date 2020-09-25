---
title: Примеры синтаксиса запросов на основе методов. Группирование
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cb23c25c-1075-4cc3-a8ff-4db72e536c0d
ms.openlocfilehash: 2d84e755217878bfa248add37a752224a20d3f84
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91191987"
---
# <a name="method-based-query-syntax-examples-grouping"></a><span data-ttu-id="3d9e2-102">Примеры синтаксиса запросов на основе методов. Группирование</span><span class="sxs-lookup"><span data-stu-id="3d9e2-102">Method-Based Query Syntax Examples: Grouping</span></span>

<span data-ttu-id="3d9e2-103">Примеры в этом разделе показывают, как использовать `GroupBy` метод для запроса [модели AdventureWorks Sales](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) с помощью синтаксиса запросов на основе методов.</span><span class="sxs-lookup"><span data-stu-id="3d9e2-103">The examples in this topic show you how to use the `GroupBy` method to query the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) using method-based query syntax.</span></span> <span data-ttu-id="3d9e2-104">Модель AdventureWorks Sales, которая используется в этих примерах, построена на основе таблиц Contact, Address, Product, SalesOrderHeader и SalesOrderDetail в образце базы данных AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="3d9e2-104">The AdventureWorks Sales Model that is used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="3d9e2-105">В примерах этого раздела используются следующие `using` / `Imports` инструкции:</span><span class="sxs-lookup"><span data-stu-id="3d9e2-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="example"></a><span data-ttu-id="3d9e2-106">Пример</span><span class="sxs-lookup"><span data-stu-id="3d9e2-106">Example</span></span>  

 <span data-ttu-id="3d9e2-107">В следующем примере метод `GroupBy` возвращает объекты `Address`, сгруппированные по почтовому индексу.</span><span class="sxs-lookup"><span data-stu-id="3d9e2-107">The following example uses the `GroupBy` method to return `Address` objects that are grouped by postal code.</span></span> <span data-ttu-id="3d9e2-108">Результаты проецируются в анонимный тип.</span><span class="sxs-lookup"><span data-stu-id="3d9e2-108">The results are projected into an anonymous type.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupBySimple3_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupbysimple3_mq)]
 [!code-vb[DP L2E Examples#GroupBySimple3_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupbysimple3_mq)]  
  
## <a name="example"></a><span data-ttu-id="3d9e2-109">Пример</span><span class="sxs-lookup"><span data-stu-id="3d9e2-109">Example</span></span>  

 <span data-ttu-id="3d9e2-110">В следующем примере метод `GroupBy` возвращает объекты `Contact`, сгруппированные по первой букве фамилии контактного лица.</span><span class="sxs-lookup"><span data-stu-id="3d9e2-110">The following example uses the `GroupBy` method to return `Contact` objects that are grouped by the first letter of the contact's last name.</span></span> <span data-ttu-id="3d9e2-111">Кроме того, результаты сортируются по первой букве фамилии и проецируются на анонимный тип.</span><span class="sxs-lookup"><span data-stu-id="3d9e2-111">The results are also sorted by the first letter of the last name and projected into an anonymous type.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupBySimple2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupbysimple2_mq)]
 [!code-vb[DP L2E Examples#GroupBySimple2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupbysimple2_mq)]  
  
## <a name="example"></a><span data-ttu-id="3d9e2-112">Пример</span><span class="sxs-lookup"><span data-stu-id="3d9e2-112">Example</span></span>  

 <span data-ttu-id="3d9e2-113">В следующем примере метод `GroupBy` возвращает объекты `SalesOrderHeader`, сгруппированные по идентификаторам клиентов.</span><span class="sxs-lookup"><span data-stu-id="3d9e2-113">The following example uses the `GroupBy` method to return `SalesOrderHeader` objects that are grouped by customer ID.</span></span> <span data-ttu-id="3d9e2-114">Также возвращается число продаж для каждого клиента.</span><span class="sxs-lookup"><span data-stu-id="3d9e2-114">The number of sales for each customer is also returned.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupByCount_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupbycount_mq)]
 [!code-vb[DP L2E Examples#GroupByCount_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupbycount_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="3d9e2-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="3d9e2-115">See also</span></span>

- [<span data-ttu-id="3d9e2-116">Запросы в LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="3d9e2-116">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
