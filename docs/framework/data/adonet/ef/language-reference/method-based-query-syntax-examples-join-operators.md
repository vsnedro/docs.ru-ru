---
title: Примеры синтаксиса запросов на основе методов. Операторы соединения
description: Используйте эти примеры, чтобы узнать, как использовать методы Join и GroupJoin для запроса модели с помощью синтаксиса запросов на основе методов в LINQ to Entities.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d00f0efa-9084-4c17-843f-54904fcb4204
ms.openlocfilehash: 3b1445b39bdcd9a9b4d0672be0598233319cb85d
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286835"
---
# <a name="method-based-query-syntax-examples-join-operators"></a><span data-ttu-id="68b0b-103">Примеры синтаксиса запросов на основе методов. Операторы соединения</span><span class="sxs-lookup"><span data-stu-id="68b0b-103">Method-Based Query Syntax Examples: Join Operators</span></span>
<span data-ttu-id="68b0b-104">В примерах этого раздела показано, как использовать <xref:System.Linq.Enumerable.Join%2A> методы и <xref:System.Linq.Enumerable.GroupJoin%2A> для запроса [модели AdventureWorks Sales](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) с помощью синтаксиса запросов на основе методов.</span><span class="sxs-lookup"><span data-stu-id="68b0b-104">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Join%2A> and <xref:System.Linq.Enumerable.GroupJoin%2A> methods to query the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) using method-based query syntax.</span></span> <span data-ttu-id="68b0b-105">Модель AdventureWorks Sales, которая используется в этих примерах, состоит из таблиц Contact, Address, Product, SalesOrderHeader и SalesOrderDetail образца базы данных AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="68b0b-105">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="68b0b-106">В примерах этого раздела используются следующие `using` / `Imports` инструкции:</span><span class="sxs-lookup"><span data-stu-id="68b0b-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="groupjoin"></a><span data-ttu-id="68b0b-107">GroupJoin</span><span class="sxs-lookup"><span data-stu-id="68b0b-107">GroupJoin</span></span>  
  
### <a name="example"></a><span data-ttu-id="68b0b-108">Пример</span><span class="sxs-lookup"><span data-stu-id="68b0b-108">Example</span></span>  
 <span data-ttu-id="68b0b-109">В следующем примере выполняется соединение <xref:System.Linq.Enumerable.GroupJoin%2A> таблиц SalesOrderHeader и SalesOrderDetail, чтобы найти количество заказов для каждого клиента.</span><span class="sxs-lookup"><span data-stu-id="68b0b-109">The following example performs a <xref:System.Linq.Enumerable.GroupJoin%2A> over the SalesOrderHeader and SalesOrderDetail tables to find the number of orders per customer.</span></span> <span data-ttu-id="68b0b-110">Групповое соединение эквивалентно левому внешнему соединению, которое возвращает каждый элемент первого (левого) источника данных, даже если в другом источнике данных не имеется соответствующих элементов.</span><span class="sxs-lookup"><span data-stu-id="68b0b-110">A group join is the equivalent of a left outer join, which returns each element of the first (left) data source, even if no correlated elements are in the other data source.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupJoin2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupjoin2_mq)]
 [!code-vb[DP L2E Examples#GroupJoin2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupjoin2_mq)]  
  
### <a name="example"></a><span data-ttu-id="68b0b-111">Пример</span><span class="sxs-lookup"><span data-stu-id="68b0b-111">Example</span></span>  
 <span data-ttu-id="68b0b-112">В следующем примере выполняется соединение <xref:System.Linq.Enumerable.GroupJoin%2A> таблиц Contact и SalesOrderHeader, чтобы найти количество заказов на каждый контакт.</span><span class="sxs-lookup"><span data-stu-id="68b0b-112">The following example performs a <xref:System.Linq.Enumerable.GroupJoin%2A> over the Contact and SalesOrderHeader tables to find the number of orders per contact.</span></span> <span data-ttu-id="68b0b-113">Для каждого контакта отображается число заказов и идентификаторы.</span><span class="sxs-lookup"><span data-stu-id="68b0b-113">The order count and IDs for each contact are displayed.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupJoin_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupjoin_mq)]
 [!code-vb[DP L2E Examples#GroupJoin_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupjoin_mq)]  
  
## <a name="join"></a><span data-ttu-id="68b0b-114">Join</span><span class="sxs-lookup"><span data-stu-id="68b0b-114">Join</span></span>  
  
### <a name="example"></a><span data-ttu-id="68b0b-115">Пример</span><span class="sxs-lookup"><span data-stu-id="68b0b-115">Example</span></span>  
 <span data-ttu-id="68b0b-116">В следующем примере выполняется соединение с таблицами Contact и SalesOrderHeader.</span><span class="sxs-lookup"><span data-stu-id="68b0b-116">The following example performs a join over the Contact and SalesOrderHeader tables.</span></span>  
  
 [!code-csharp[DP L2E Examples#JoinSimple_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#joinsimple_mq)]
 [!code-vb[DP L2E Examples#JoinSimple_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#joinsimple_mq)]  
  
### <a name="example"></a><span data-ttu-id="68b0b-117">Пример</span><span class="sxs-lookup"><span data-stu-id="68b0b-117">Example</span></span>  
 <span data-ttu-id="68b0b-118">В следующем примере выполняется соединение с таблицами Contact и SalesOrderHeader с группированием результатов по идентификатору контактного лица.</span><span class="sxs-lookup"><span data-stu-id="68b0b-118">The following example performs a join over the Contact and SalesOrderHeader tables, grouping the results by contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#JoinWithGroupedResults_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#joinwithgroupedresults_mq)]
 [!code-vb[DP L2E Examples#JoinWithGroupedResults_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#joinwithgroupedresults_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="68b0b-119">См. также</span><span class="sxs-lookup"><span data-stu-id="68b0b-119">See also</span></span>

- [<span data-ttu-id="68b0b-120">Запросы в LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="68b0b-120">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
