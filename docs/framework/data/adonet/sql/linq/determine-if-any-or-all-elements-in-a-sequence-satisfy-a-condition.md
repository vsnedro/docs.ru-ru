---
description: Дополнительные сведения см. в статье определение соответствия одного или всех элементов последовательности условию.
title: Проверка соответствия условию какого-либо или всех элементов
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 339ec145-826c-46d2-8cf2-3acd252cd072
ms.openlocfilehash: a46cf7e4e213eba830dc203f9266a408103cee80
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786112"
---
# <a name="determine-if-any-or-all-elements-in-a-sequence-satisfy-a-condition"></a>Проверка соответствия условию какого-либо или всех элементов

Оператор <xref:System.Linq.Enumerable.All%2A> возвращает значение `true`, если все элементы в последовательности удовлетворяют указанному условию.  
  
 Оператор <xref:System.Linq.Queryable.Any%2A> возвращает значение `true`, если какой-либо элемент в коллекции удовлетворяет указанному условию.  
  
## <a name="example"></a>Пример  

 В следующем примере возвращается последовательность клиентов, сделавших хотя бы один заказ. `Where` / `where` Предложение принимает значение, `true` Если у данного предложения `Customer` есть `Order` .  
  
 [!code-csharp[DLinqQueryExamples#37](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#37)]
 [!code-vb[DLinqQueryExamples#37](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#37)]  
  
## <a name="example"></a>Пример  

 Следующий код Visual Basic определяет список клиентов, не оформивших заказы, и гарантирует наличие контактного имени для каждого клиента в этом списке.  
  
 [!code-vb[DLinqQueryExamples#37v](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#37v)]  
  
## <a name="example"></a>Пример  

 В следующем примере C# возвращается последовательность клиентов, `ShipCity` в заказах которых начинается с буквы "С". Кроме того, в полученном результате будут указаны клиенты, не сделавшие ни одного заказа. (По проекту <xref:System.Linq.Queryable.All%2A> оператор возвращает `true` для пустой последовательности.) Клиенты без заказов устраняются в выходных данных консоли с помощью `Count` оператора.  
  
 [!code-csharp[DLinqQueryExamples#38](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#38)]  
  
## <a name="see-also"></a>См. также

- [Примеры запросов](query-examples.md)
