---
title: Практическое руководство. Преобразование типа в универсальный интерфейс IEnumerable
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 64774fb5-7447-4296-ad3b-8a94346f99a1
ms.openlocfilehash: c2d34ae708f79d9f920679b3714a100fe8943c38
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91164419"
---
# <a name="convert-a-type-to-a-generic-ienumerable"></a>Практическое руководство. Преобразование типа в универсальный интерфейс IEnumerable

Для возвращения аргумента с типом универсальный <xref:System.Linq.Enumerable.AsEnumerable%2A> используется `IEnumerable`.  
  
## <a name="example"></a>Пример  

 В этом примере [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] (с помощью заданного по умолчанию универсального `Query`) предпримет попытку преобразовать запрос в SQL и выполнить его на сервере. Однако предложение `where` ссылается на пользовательский метод на стороне клиента (`isValidProduct`), который не может быть преобразован в SQL.  
  
 Решением является задание клиентской универсальной реализации <xref:System.Collections.Generic.IEnumerable%601> предложения `where` для замены универсального <xref:System.Linq.IQueryable%601>. Для этого следует вызвать оператор <xref:System.Linq.Enumerable.AsEnumerable%2A>.  
  
 [!code-csharp[DLinqQueryExamples#46](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#46)]
 [!code-vb[DLinqQueryExamples#46](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#46)]  
  
## <a name="see-also"></a>См. также раздел

- [Примеры запросов](query-examples.md)
