---
description: 'Дополнительные сведения о: возврат первого элемента последовательности'
title: Возврат первого элемента в последовательности
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ccdc3777-b2c2-44e3-a627-abef8d79a555
ms.openlocfilehash: 004e9a1f03677f6ba49916404b1c44408df40dfa
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99663018"
---
# <a name="return-the-first-element-in-a-sequence"></a>Возврат первого элемента в последовательности

Для возвращения первого элемента последовательности используется оператор <xref:System.Linq.Enumerable.First%2A>. Запросы, использующие оператор <xref:System.Linq.Enumerable.First%2A>, выполняются немедленно.  
  
> [!NOTE]
> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] не поддерживает оператор <xref:System.Linq.Enumerable.Last%2A>.  
  
## <a name="example"></a>Пример  

 В следующем примере кода выполняется поиск первого поставщика (`Shipper`) в таблице.  
  
 При выполнении данного запроса в учебной базе данных "Northwind" возвращается результат:  
  
 `ID = 1, Company = Speedy Express`.  
  
 [!code-csharp[DLinqQueryExamples#14](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#14)]
 [!code-vb[DLinqQueryExamples#14](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#14)]  
  
## <a name="example"></a>Пример  

 В следующем примере кода выполняется поиск отдельного клиента (`Customer`), которому присвоен код (`CustomerID`) BONAP.  
  
 При выполнении данного запроса в учебной базе данных "Northwind" возвращается результат `ID = BONAP, Contact = Laurence Lebihan`.  
  
 [!code-csharp[DLinqQueryExamples#15](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#15)]
 [!code-vb[DLinqQueryExamples#15](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#15)]  
  
## <a name="see-also"></a>См. также

- [Примеры запросов](query-examples.md)
- [Загрузка примеров баз данных](downloading-sample-databases.md)
