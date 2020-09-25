---
title: Примеры синтаксиса запросов на основе методов. Операторы элементов
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8438b995-bd07-4223-b22d-13adadef33fb
ms.openlocfilehash: 96d393a34af69935e75582ef1954ddd661a355f0
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91192052"
---
# <a name="method-based-query-syntax-examples-element-operators"></a><span data-ttu-id="c0516-102">Примеры синтаксиса запросов на основе методов. Операторы элементов</span><span class="sxs-lookup"><span data-stu-id="c0516-102">Method-Based Query Syntax Examples: Element Operators</span></span>

<span data-ttu-id="c0516-103">В примерах этого раздела показано, как использовать <xref:System.Linq.Enumerable.First%2A> метод для запроса [модели AdventureWorks Sales](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) с помощью синтаксиса запросов на основе методов.</span><span class="sxs-lookup"><span data-stu-id="c0516-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.First%2A> method to query the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) using method-based query syntax.</span></span> <span data-ttu-id="c0516-104">Модель AdventureWorks Sales, которая используется в этих примерах, состоит из таблиц Contact, Address, Product, SalesOrderHeader и SalesOrderDetail образца базы данных AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="c0516-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="c0516-105">В примере в этом разделе используются следующие `using` / `Imports` инструкции:</span><span class="sxs-lookup"><span data-stu-id="c0516-105">The example in this topic uses the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="first"></a><span data-ttu-id="c0516-106">First</span><span class="sxs-lookup"><span data-stu-id="c0516-106">First</span></span>  
  
### <a name="example"></a><span data-ttu-id="c0516-107">Пример</span><span class="sxs-lookup"><span data-stu-id="c0516-107">Example</span></span>  

 <span data-ttu-id="c0516-108">В следующем примере метод используется <xref:System.Linq.Enumerable.First%2A> для поиска первого адреса электронной почты, который начинается с "Кэролайн".</span><span class="sxs-lookup"><span data-stu-id="c0516-108">The following example uses the <xref:System.Linq.Enumerable.First%2A> method to find the first email address that starts with 'caroline'.</span></span>  
  
 [!code-csharp[DP L2E Examples#FirstCondition_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#firstcondition_mq)]
 [!code-vb[DP L2E Examples#FirstCondition_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#firstcondition_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="c0516-109">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="c0516-109">See also</span></span>

- [<span data-ttu-id="c0516-110">Запросы в LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="c0516-110">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
