---
description: 'Дополнительные сведения: возврат пересечения наборов двух последовательностей'
title: Возврат пересечения наборов двух последовательностей.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d09c344e-3548-4944-a3ed-051880e3f5b8
ms.openlocfilehash: 163e138761caadb73b6dc5d672c02353a88a2c22
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99662989"
---
# <a name="return-the-set-intersection-of-two-sequences"></a>Возврат пересечения наборов двух последовательностей.

Для возвращения пересечения наборов двух последовательностей используется оператор <xref:System.Linq.Queryable.Intersect%2A>.  
  
## <a name="example"></a>Пример  

 В этом примере используется <xref:System.Linq.Queryable.Intersect%2A> для возврата последовательности всех стран или регионов, в которых `Customers` и, и в `Employees` реальном времени.  
  
 [!code-csharp[DLinqQueryExamples#42](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#42)]
 [!code-vb[DLinqQueryExamples#42](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#42)]  
  
 В [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] оператор <xref:System.Linq.Queryable.Intersect%2A> правильно определен только в наборах. Семантика для мультинаборов не определена.  
  
## <a name="see-also"></a>См. также

- [Примеры запросов](query-examples.md)
- [Трансляция стандартных операторов запросов](standard-query-operator-translation.md)
