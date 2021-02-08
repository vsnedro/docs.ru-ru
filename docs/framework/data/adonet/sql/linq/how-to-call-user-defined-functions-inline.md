---
description: Дополнительные сведения см. в статье как вызывать функции User-Defined встроенными функциями.
title: Практическое руководство. Как вызывать встроенные определяемые пользователем функции
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f80d4327-b6a5-4aa8-a743-e95d09a2a02e
ms.openlocfilehash: 2a7cf185af05a1ed58a2dd3b365a5bbcaa2a4fd5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786060"
---
# <a name="how-to-call-user-defined-functions-inline"></a>Практическое руководство. Как вызывать встроенные определяемые пользователем функции

Пользовательские функции можно вызывать из строки кода, однако функции, включенные в запрос, выполнение которого отложено, выполняются только одновременно с запросом. Дополнительные сведения см. в разделе [Введение в запросы LINQ (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).  
  
 Если та же функция вызывается за пределами запроса, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] создает простой запрос из выражения вызова метода. Ниже показан синтаксис SQL (параметр `@p0` привязан к передаваемой константе).  
  
```sql  
SELECT dbo.ReverseCustName(@p0)  
```  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] создает следующий код:  
  
 [!code-csharp[DLinqUDFS#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqUDFS/cs/Program.cs#4)]
 [!code-vb[DLinqUDFS#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqUDFS/vb/Module1.vb#4)]  
  
## <a name="example"></a>Пример  

 В следующем [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] запросе можно увидеть встроенный вызов созданного метода определяемой пользователем функции `ReverseCustName` . Функция не выполняется немедленно, поскольку выполнение запроса отложено. Код SQL, созданный для этого запроса, преобразуется в вызов пользовательской функции в базе данных (см. код SQL, расположенный после запроса).  
  
 [!code-csharp[DLinqUDFS#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqUDFS/cs/Program.cs#5)]
 [!code-vb[DLinqUDFS#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqUDFS/vb/Module1.vb#5)]  
  
```sql  
SELECT [t0].[ContactName],  
    dbo.ReverseCustName([t0].[ContactTitle]) AS [Title]  
FROM [Customers] AS [t0]  
```  
  
## <a name="see-also"></a>См. также

- [Определяемые пользователем функции](user-defined-functions.md)
