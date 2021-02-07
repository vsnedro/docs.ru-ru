---
description: 'Дополнительные сведения: возврат объединения наборов двух последовательностей'
title: Возврат объединения наборов двух последовательностей.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8b8bd3cb-86d4-4a3b-9906-61f68726dd1f
ms.openlocfilehash: 5541316560c05712e22c54f706b02d868fadb381
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99662966"
---
# <a name="return-the-set-union-of-two-sequences"></a>Возврат объединения наборов двух последовательностей.

Оператор <xref:System.Linq.Queryable.Union%2A> используется для возвращения объединения наборов двух последовательностей.  
  
## <a name="example"></a>Пример  

 В этом примере используется <xref:System.Linq.Queryable.Union%2A> для возврата последовательности всех стран или регионов, в которых есть `Customers` или `Employees` .  
  
 [!code-csharp[DLinqQueryExamples#43](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#43)]
 [!code-vb[DLinqQueryExamples#43](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#43)]  
  
 В [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Linq.Queryable.Union%2A> оператор определяется для множества наборов как неупорядоченное объединение множества наборов (фактически результат [`UNION ALL`](/sql/t-sql/language-elements/set-operators-union-transact-sql) предложения в SQL).

Дополнительные сведения и примеры см. в разделе <xref:System.Linq.Queryable.Union%2A?displayProperty=nameWithType> .
  
## <a name="see-also"></a>См. также

- [Примеры запросов](query-examples.md)
- [Трансляция стандартных операторов запросов](standard-query-operator-translation.md)
