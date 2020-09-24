---
title: Практическое руководство. Преобразование типа в универсальный интерфейс IEnumerable
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 64774fb5-7447-4296-ad3b-8a94346f99a1
ms.openlocfilehash: c2d34ae708f79d9f920679b3714a100fe8943c38
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91164419"
---
# <a name="convert-a-type-to-a-generic-ienumerable"></a><span data-ttu-id="0f86d-102">Практическое руководство. Преобразование типа в универсальный интерфейс IEnumerable</span><span class="sxs-lookup"><span data-stu-id="0f86d-102">Convert a Type to a Generic IEnumerable</span></span>

<span data-ttu-id="0f86d-103">Для возвращения аргумента с типом универсальный <xref:System.Linq.Enumerable.AsEnumerable%2A> используется `IEnumerable`.</span><span class="sxs-lookup"><span data-stu-id="0f86d-103">Use <xref:System.Linq.Enumerable.AsEnumerable%2A> to return the argument typed as a generic `IEnumerable`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0f86d-104">Пример</span><span class="sxs-lookup"><span data-stu-id="0f86d-104">Example</span></span>  

 <span data-ttu-id="0f86d-105">В этом примере [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] (с помощью заданного по умолчанию универсального `Query`) предпримет попытку преобразовать запрос в SQL и выполнить его на сервере.</span><span class="sxs-lookup"><span data-stu-id="0f86d-105">In this example, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] (using the default generic `Query`) would try to convert the query to SQL and execute it on the server.</span></span> <span data-ttu-id="0f86d-106">Однако предложение `where` ссылается на пользовательский метод на стороне клиента (`isValidProduct`), который не может быть преобразован в SQL.</span><span class="sxs-lookup"><span data-stu-id="0f86d-106">But the `where` clause references a user-defined client-side method (`isValidProduct`), which cannot be converted to SQL.</span></span>  
  
 <span data-ttu-id="0f86d-107">Решением является задание клиентской универсальной реализации <xref:System.Collections.Generic.IEnumerable%601> предложения `where` для замены универсального <xref:System.Linq.IQueryable%601>.</span><span class="sxs-lookup"><span data-stu-id="0f86d-107">The solution is to specify the client-side generic <xref:System.Collections.Generic.IEnumerable%601> implementation of `where` to replace the generic <xref:System.Linq.IQueryable%601>.</span></span> <span data-ttu-id="0f86d-108">Для этого следует вызвать оператор <xref:System.Linq.Enumerable.AsEnumerable%2A>.</span><span class="sxs-lookup"><span data-stu-id="0f86d-108">You do this by invoking the <xref:System.Linq.Enumerable.AsEnumerable%2A> operator.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#46](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#46)]
 [!code-vb[DLinqQueryExamples#46](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#46)]  
  
## <a name="see-also"></a><span data-ttu-id="0f86d-109">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="0f86d-109">See also</span></span>

- [<span data-ttu-id="0f86d-110">Примеры запросов</span><span class="sxs-lookup"><span data-stu-id="0f86d-110">Query Examples</span></span>](query-examples.md)
