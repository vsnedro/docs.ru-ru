---
description: 'Дополнительные сведения: возврат разности множества двух последовательностей'
title: Возврат разности наборов между двумя последовательностями
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 62efb546-c898-408f-af21-36e7c6fed217
ms.openlocfilehash: 6836195ac4e1ee678fd3e8089e7c341f7dd247e8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99662990"
---
# <a name="return-the-set-difference-between-two-sequences"></a>Возврат разности наборов между двумя последовательностями

Оператор <xref:System.Linq.Queryable.Except%2A> используется для возвращения разности наборов между двумя последовательностями.  
  
## <a name="example"></a>Пример  

 В этом примере используется <xref:System.Linq.Queryable.Except%2A> для возврата последовательности всех стран или регионов, в которых `Customers` динамический, но не в `Employees` режиме реального времени.  
  
 [!code-csharp[DLinqQueryExamples#41](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#41)]
 [!code-vb[DLinqQueryExamples#41](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#41)]  
  
 В [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] оператор <xref:System.Linq.Queryable.Except%2A> правильно определен только в наборах. Семантика для мультинаборов не определена.  
  
## <a name="see-also"></a>См. также

- [Примеры запросов](query-examples.md)
- [Трансляция стандартных операторов запросов](standard-query-operator-translation.md)
