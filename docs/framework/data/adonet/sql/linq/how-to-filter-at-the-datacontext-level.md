---
description: Дополнительные сведения о том, как выполнить фильтрацию на уровне DataContext.
title: Практическое руководство. Как фильтровать данные на уровне DataContext
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 15505cd7-0df2-427a-9f86-e0f96f60ee2e
ms.openlocfilehash: ffb287ac1ef8cc19044ec3d519e745f905fe213d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785982"
---
# <a name="how-to-filter-at-the-datacontext-level"></a>Практическое руководство. Как фильтровать данные на уровне DataContext

Фильтрацию `EntitySets` можно выполнить на уровне `DataContext`. Подобные фильтры применяются ко всем запросам, осуществленным с помощью экземпляра <xref:System.Data.Linq.DataContext>.  
  
## <a name="example"></a>Пример  

 В следующем примере <xref:System.Data.Linq.DataLoadOptions.AssociateWith%28System.Linq.Expressions.LambdaExpression%29?displayProperty=nameWithType> используется для фильтрации предварительно загруженных заказов для клиентов по `ShippedDate`.  
  
 [!code-csharp[DLinqQueryConcepts#10](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#10)]
 [!code-vb[DLinqQueryConcepts#10](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#10)]  
  
## <a name="see-also"></a>См. также

- [Основные принципы запросов](query-concepts.md)
