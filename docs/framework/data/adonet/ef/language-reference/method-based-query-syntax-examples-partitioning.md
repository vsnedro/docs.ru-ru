---
title: Примеры синтаксиса запросов на основе методов. Секционирование
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b7b64874-c3c8-4bdb-862c-89a168d07827
ms.openlocfilehash: 659c05f261b854b1f2bb9bc3bce7c2889650571f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91191896"
---
# <a name="method-based-query-syntax-examples-partitioning"></a><span data-ttu-id="8224c-102">Примеры синтаксиса запросов на основе методов. Секционирование</span><span class="sxs-lookup"><span data-stu-id="8224c-102">Method-Based Query Syntax Examples: Partitioning</span></span>

<span data-ttu-id="8224c-103">В примерах этого раздела показано, как использовать <xref:System.Linq.Enumerable.Skip%2A> <xref:System.Linq.Enumerable.Take%2A> методы и для запроса [модели AdventureWorks Sales](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) с помощью синтаксиса выражений запросов.</span><span class="sxs-lookup"><span data-stu-id="8224c-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Skip%2A>, and <xref:System.Linq.Enumerable.Take%2A> methods to query the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) using query expression syntax.</span></span> <span data-ttu-id="8224c-104">Модель AdventureWorks Sales, которая используется в этих примерах, состоит из таблиц Contact, Address, Product, SalesOrderHeader и SalesOrderDetail образца базы данных AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="8224c-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="8224c-105">В примерах этого раздела используются следующие `using` / `Imports` инструкции:</span><span class="sxs-lookup"><span data-stu-id="8224c-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="skip"></a><span data-ttu-id="8224c-106">Пропустить</span><span class="sxs-lookup"><span data-stu-id="8224c-106">Skip</span></span>  
  
### <a name="example"></a><span data-ttu-id="8224c-107">Пример</span><span class="sxs-lookup"><span data-stu-id="8224c-107">Example</span></span>  

 <span data-ttu-id="8224c-108">В следующем примере метод <xref:System.Linq.Enumerable.Skip%2A> используется для возврата всех контактов в таблице Contact, за исключением первых пяти.</span><span class="sxs-lookup"><span data-stu-id="8224c-108">The following example uses the <xref:System.Linq.Enumerable.Skip%2A> method to get all but the first five contacts of the Contact table.</span></span>  
  
 [!code-csharp[DP L2E Examples#SkipSimple](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#skipsimple)]
 [!code-vb[DP L2E Examples#SkipSimple](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#skipsimple)]  
  
### <a name="example"></a><span data-ttu-id="8224c-109">Пример</span><span class="sxs-lookup"><span data-stu-id="8224c-109">Example</span></span>  

 <span data-ttu-id="8224c-110">В следующем примере метод <xref:System.Linq.Enumerable.Skip%2A> используется для получения всех адресов в Сиэттле, кроме первых двух.</span><span class="sxs-lookup"><span data-stu-id="8224c-110">The following example uses the <xref:System.Linq.Enumerable.Skip%2A> method to get all but the first two addresses in Seattle.</span></span>  
  
 [!code-csharp[DP L2E Examples#SkipNested](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#skipnested)]
 [!code-vb[DP L2E Examples#SkipNested](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#skipnested)]  
  
## <a name="take"></a><span data-ttu-id="8224c-111">Take</span><span class="sxs-lookup"><span data-stu-id="8224c-111">Take</span></span>  
  
### <a name="example"></a><span data-ttu-id="8224c-112">Пример</span><span class="sxs-lookup"><span data-stu-id="8224c-112">Example</span></span>  

 <span data-ttu-id="8224c-113">В следующем примере метод <xref:System.Linq.Enumerable.Take%2A> используется для возврата первых пяти контактов из таблицы Contact.</span><span class="sxs-lookup"><span data-stu-id="8224c-113">The following example uses the <xref:System.Linq.Enumerable.Take%2A> method to get only the first five contacts from the Contact table.</span></span>  
  
 [!code-csharp[DP L2E Examples#TakeSimple](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#takesimple)]
 [!code-vb[DP L2E Examples#TakeSimple](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#takesimple)]  
  
### <a name="example"></a><span data-ttu-id="8224c-114">Пример</span><span class="sxs-lookup"><span data-stu-id="8224c-114">Example</span></span>  

 <span data-ttu-id="8224c-115">В следующем примере метод <xref:System.Linq.Enumerable.Take%2A> используется для получения первых трех адресов в Сиэттле.</span><span class="sxs-lookup"><span data-stu-id="8224c-115">The following example uses the <xref:System.Linq.Enumerable.Take%2A> method to get the first three addresses in Seattle.</span></span>  
  
 [!code-csharp[DP L2E Examples#TakeNested](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#takenested)]
 [!code-vb[DP L2E Examples#TakeNested](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#takenested)]  
  
## <a name="see-also"></a><span data-ttu-id="8224c-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="8224c-116">See also</span></span>

- [<span data-ttu-id="8224c-117">Запросы в LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="8224c-117">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
