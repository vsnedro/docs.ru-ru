---
title: Преобразование последовательности в универсальный список
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7ab76d93-6898-4e75-b76f-290a66ecead8
ms.openlocfilehash: 79e3ddaff0234dfb5f91e36bacd3279afa9ec265
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91164393"
---
# <a name="convert-a-sequence-to-a-generic-list"></a><span data-ttu-id="2dad0-102">Преобразование последовательности в универсальный список</span><span class="sxs-lookup"><span data-stu-id="2dad0-102">Convert a Sequence to a Generic List</span></span>

<span data-ttu-id="2dad0-103">Для создания универсального списка из последовательности используется <xref:System.Linq.Enumerable.ToList%2A>.</span><span class="sxs-lookup"><span data-stu-id="2dad0-103">Use <xref:System.Linq.Enumerable.ToList%2A> to create a generic List from a sequence.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2dad0-104">Пример</span><span class="sxs-lookup"><span data-stu-id="2dad0-104">Example</span></span>  

 <span data-ttu-id="2dad0-105">В следующем примере используется <xref:System.Linq.Enumerable.ToList%2A> для непосредственного преобразования запроса в универсальный <xref:System.Collections.Generic.List%601>.</span><span class="sxs-lookup"><span data-stu-id="2dad0-105">The following sample uses <xref:System.Linq.Enumerable.ToList%2A> to immediately evaluate a query into a generic <xref:System.Collections.Generic.List%601>.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#45](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#45)]
 [!code-vb[DLinqQueryExamples#45](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#45)]  
  
## <a name="see-also"></a><span data-ttu-id="2dad0-106">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="2dad0-106">See also</span></span>

- [<span data-ttu-id="2dad0-107">Примеры запросов</span><span class="sxs-lookup"><span data-stu-id="2dad0-107">Query Examples</span></span>](query-examples.md)
