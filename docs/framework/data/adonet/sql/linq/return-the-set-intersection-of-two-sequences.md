---
title: Возврат пересечения наборов двух последовательностей.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d09c344e-3548-4944-a3ed-051880e3f5b8
ms.openlocfilehash: 421ec544345e41f910bf80c855a3a6b4de1c46a6
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91200229"
---
# <a name="return-the-set-intersection-of-two-sequences"></a><span data-ttu-id="20702-102">Возврат пересечения наборов двух последовательностей.</span><span class="sxs-lookup"><span data-stu-id="20702-102">Return the Set Intersection of Two Sequences</span></span>

<span data-ttu-id="20702-103">Для возвращения пересечения наборов двух последовательностей используется оператор <xref:System.Linq.Queryable.Intersect%2A>.</span><span class="sxs-lookup"><span data-stu-id="20702-103">Use the <xref:System.Linq.Queryable.Intersect%2A> operator to return the set intersection of two sequences.</span></span>  
  
## <a name="example"></a><span data-ttu-id="20702-104">Пример</span><span class="sxs-lookup"><span data-stu-id="20702-104">Example</span></span>  

 <span data-ttu-id="20702-105">В этом примере используется <xref:System.Linq.Queryable.Intersect%2A> для возврата последовательности всех стран или регионов, в которых `Customers` и, и в `Employees` реальном времени.</span><span class="sxs-lookup"><span data-stu-id="20702-105">This example uses <xref:System.Linq.Queryable.Intersect%2A> to return a sequence of all countries/regions in which both `Customers` and `Employees` live.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#42](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#42)]
 [!code-vb[DLinqQueryExamples#42](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#42)]  
  
 <span data-ttu-id="20702-106">В [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] оператор <xref:System.Linq.Queryable.Intersect%2A> правильно определен только в наборах.</span><span class="sxs-lookup"><span data-stu-id="20702-106">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the <xref:System.Linq.Queryable.Intersect%2A> operation is well defined only on sets.</span></span> <span data-ttu-id="20702-107">Семантика для мультинаборов не определена.</span><span class="sxs-lookup"><span data-stu-id="20702-107">The semantics for multisets is undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20702-108">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="20702-108">See also</span></span>

- [<span data-ttu-id="20702-109">Примеры запросов</span><span class="sxs-lookup"><span data-stu-id="20702-109">Query Examples</span></span>](query-examples.md)
- [<span data-ttu-id="20702-110">Трансляция стандартных операторов запросов</span><span class="sxs-lookup"><span data-stu-id="20702-110">Standard Query Operator Translation</span></span>](standard-query-operator-translation.md)
