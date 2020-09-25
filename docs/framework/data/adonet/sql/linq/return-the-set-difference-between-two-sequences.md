---
title: Возврат разности наборов между двумя последовательностями
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 62efb546-c898-408f-af21-36e7c6fed217
ms.openlocfilehash: 49a8d22377ef1f7d0fde16880a82002754e1bbc4
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91200333"
---
# <a name="return-the-set-difference-between-two-sequences"></a><span data-ttu-id="75905-102">Возврат разности наборов между двумя последовательностями</span><span class="sxs-lookup"><span data-stu-id="75905-102">Return the Set Difference Between Two Sequences</span></span>

<span data-ttu-id="75905-103">Оператор <xref:System.Linq.Queryable.Except%2A> используется для возвращения разности наборов между двумя последовательностями.</span><span class="sxs-lookup"><span data-stu-id="75905-103">Use the <xref:System.Linq.Queryable.Except%2A> operator to return the set difference between two sequences.</span></span>  
  
## <a name="example"></a><span data-ttu-id="75905-104">Пример</span><span class="sxs-lookup"><span data-stu-id="75905-104">Example</span></span>  

 <span data-ttu-id="75905-105">В этом примере используется <xref:System.Linq.Queryable.Except%2A> для возврата последовательности всех стран или регионов, в которых `Customers` динамический, но не в `Employees` режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="75905-105">This example uses <xref:System.Linq.Queryable.Except%2A> to return a sequence of all countries/regions in which `Customers` live but in which no `Employees` live.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#41](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#41)]
 [!code-vb[DLinqQueryExamples#41](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#41)]  
  
 <span data-ttu-id="75905-106">В [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] оператор <xref:System.Linq.Queryable.Except%2A> правильно определен только в наборах.</span><span class="sxs-lookup"><span data-stu-id="75905-106">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the <xref:System.Linq.Queryable.Except%2A> operation is well defined only on sets.</span></span> <span data-ttu-id="75905-107">Семантика для мультинаборов не определена.</span><span class="sxs-lookup"><span data-stu-id="75905-107">The semantics for multisets is undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75905-108">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="75905-108">See also</span></span>

- [<span data-ttu-id="75905-109">Примеры запросов</span><span class="sxs-lookup"><span data-stu-id="75905-109">Query Examples</span></span>](query-examples.md)
- [<span data-ttu-id="75905-110">Трансляция стандартных операторов запросов</span><span class="sxs-lookup"><span data-stu-id="75905-110">Standard Query Operator Translation</span></span>](standard-query-operator-translation.md)
