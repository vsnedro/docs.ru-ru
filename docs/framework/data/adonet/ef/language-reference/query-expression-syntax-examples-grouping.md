---
title: Примеры синтаксиса выражений запросов. Группирование
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2d83d7c0-b3be-4c92-a630-25cd1285de31
ms.openlocfilehash: 854d9c2a7371b80dd288a1d6c67272678efda135
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91152940"
---
# <a name="query-expression-syntax-examples-grouping"></a><span data-ttu-id="006f0-102">Примеры синтаксиса выражений запросов. Группирование</span><span class="sxs-lookup"><span data-stu-id="006f0-102">Query Expression Syntax Examples: Grouping</span></span>

<span data-ttu-id="006f0-103">В примерах этого раздела показано, как использовать `GroupBy` метод для запроса [модели AdventureWorks Sales](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) с помощью синтаксиса выражения запроса.</span><span class="sxs-lookup"><span data-stu-id="006f0-103">The examples in this topic demonstrate how to use the `GroupBy` method to query the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) using query expression syntax.</span></span> <span data-ttu-id="006f0-104">Модель AdventureWorks Sales, которая используется в этих примерах, состоит из таблиц Contact, Address, Product, SalesOrderHeader и SalesOrderDetail образца базы данных AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="006f0-104">The AdventureWorks Sales model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="006f0-105">В примерах этого раздела используются следующие `using` / `Imports` инструкции:</span><span class="sxs-lookup"><span data-stu-id="006f0-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="example"></a><span data-ttu-id="006f0-106">Пример</span><span class="sxs-lookup"><span data-stu-id="006f0-106">Example</span></span>  

 <span data-ttu-id="006f0-107">В следующем примере происходит возврат объектов `Address`, сгруппированных по почтовым индексам.</span><span class="sxs-lookup"><span data-stu-id="006f0-107">The following example returns `Address` objects grouped by postal code.</span></span> <span data-ttu-id="006f0-108">Результаты проецируются в анонимный тип.</span><span class="sxs-lookup"><span data-stu-id="006f0-108">The results are projected into an anonymous type.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupBySimple3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupbysimple3)]
 [!code-vb[DP L2E Examples#GroupBySimple3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupbysimple3)]  
  
## <a name="example"></a><span data-ttu-id="006f0-109">Пример</span><span class="sxs-lookup"><span data-stu-id="006f0-109">Example</span></span>  

 <span data-ttu-id="006f0-110">В следующем примере происходит возврат объектов `Contact`, сгруппированных по первой букве фамилий контактных лиц.</span><span class="sxs-lookup"><span data-stu-id="006f0-110">The following example returns `Contact` objects grouped by the first letter of the contact's last name.</span></span> <span data-ttu-id="006f0-111">Результаты также сортируются по первой букве фамилии и проецируются в анонимный тип.</span><span class="sxs-lookup"><span data-stu-id="006f0-111">The results are also sorted by the first letter of last name and projected into an anonymous type.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupBySimple2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupbysimple2)]
 [!code-vb[DP L2E Examples#GroupBySimple2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupbysimple2)]  
  
## <a name="example"></a><span data-ttu-id="006f0-112">Пример</span><span class="sxs-lookup"><span data-stu-id="006f0-112">Example</span></span>  

 <span data-ttu-id="006f0-113">В следующем примере возвращаются объекты `SalesOrderHeader`, сгруппированные по идентификаторам клиента.</span><span class="sxs-lookup"><span data-stu-id="006f0-113">The following example returns `SalesOrderHeader` objects grouped by customer ID.</span></span> <span data-ttu-id="006f0-114">Также возвращается число продаж для каждого клиента.</span><span class="sxs-lookup"><span data-stu-id="006f0-114">The number of sales for each customer is also returned.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupByCount](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupbycount)]
 [!code-vb[DP L2E Examples#GroupByCount](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupbycount)]  
  
## <a name="see-also"></a><span data-ttu-id="006f0-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="006f0-115">See also</span></span>

- [<span data-ttu-id="006f0-116">Запросы в LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="006f0-116">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
