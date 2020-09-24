---
title: Удаление дубликатов элементов из последовательности
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2b224a84-bad5-4843-adcc-14e784d280f5
ms.openlocfilehash: 0dca1a635fd1cc6e48e8ad914909769b2cf0e66d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91161377"
---
# <a name="eliminate-duplicate-elements-from-a-sequence"></a><span data-ttu-id="4d099-102">Удаление дубликатов элементов из последовательности</span><span class="sxs-lookup"><span data-stu-id="4d099-102">Eliminate Duplicate Elements from a Sequence</span></span>

<span data-ttu-id="4d099-103">Чтобы исключить элементы-дубликаты из последовательности, воспользуйтесь оператором <xref:System.Linq.Queryable.Distinct%2A>.</span><span class="sxs-lookup"><span data-stu-id="4d099-103">Use the <xref:System.Linq.Queryable.Distinct%2A> operator to eliminate duplicate elements from a sequence.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4d099-104">Пример</span><span class="sxs-lookup"><span data-stu-id="4d099-104">Example</span></span>  

 <span data-ttu-id="4d099-105">В следующем примере для выбора последовательности уникальных городов, в которых находятся клиенты, используется метод <xref:System.Linq.Queryable.Distinct%2A>.</span><span class="sxs-lookup"><span data-stu-id="4d099-105">The following example uses <xref:System.Linq.Queryable.Distinct%2A> to select a sequence of the unique cities that have customers.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#36](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#36)]
 [!code-vb[DLinqQueryExamples#36](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#36)]  
  
## <a name="see-also"></a><span data-ttu-id="4d099-106">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="4d099-106">See also</span></span>

- [<span data-ttu-id="4d099-107">Примеры запросов</span><span class="sxs-lookup"><span data-stu-id="4d099-107">Query Examples</span></span>](query-examples.md)
