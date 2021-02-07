---
description: 'Дополнительные сведения о: подсчет числа элементов в последовательности'
title: Подсчет количества элементов в последовательности
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ccbe5d54-c9eb-4b14-b0ab-f628483c5f99
ms.openlocfilehash: 91030516098e900229a1e131ea0c9a7d8bef4034
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99663083"
---
# <a name="count-the-number-of-elements-in-a-sequence"></a>Подсчет количества элементов в последовательности

Для подсчета числа элементов в последовательности используется оператор <xref:System.Linq.Enumerable.Count%2A>.  
  
 При выполнении данного запроса в учебной базе данных "Northwind" возвращается значение `91`.  
  
## <a name="example"></a>Пример  

 В следующем примере подсчитывается количество клиентов (`Customers`) в базе данных.  
  
 [!code-csharp[DLinqQueryExamples#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#4)]
 [!code-vb[DLinqQueryExamples#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#4)]  
  
## <a name="example"></a>Пример  

 В следующем примере подсчитывается количество продуктов в базе данных, еще не снятых с производства.  
  
 При выполнении данного примера в учебной базе данных "Northwind" возвращается значение `69`.  
  
 [!code-csharp[DLinqQueryExamples#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#5)]
 [!code-vb[DLinqQueryExamples#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#5)]  
  
## <a name="see-also"></a>См. также

- [Статистические запросы](aggregate-queries.md)
- [Загрузка примеров баз данных](downloading-sample-databases.md)
