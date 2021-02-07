---
description: Дополнительные сведения см. в статье как вызывать функции базы данных.
title: Практическое руководство. Вызов функций базы данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 79038efa-15bf-464a-83e2-35fe145252ce
ms.openlocfilehash: d5c5854d375546d1604b6e27e6f757f1e126f9b4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99724522"
---
# <a name="how-to-call-database-functions"></a>Практическое руководство. Вызов функций базы данных

Класс <xref:System.Data.Objects.SqlClient.SqlFunctions> содержит методы среды CLR, предоставляющие доступ к функциям SQL Server для использования в запросах LINQ to Entities. При использовании методов <xref:System.Data.Objects.SqlClient.SqlFunctions> в запросах LINQ to Entities в базе данных выполняются соответствующие функции базы данных.  
  
> [!NOTE]
> Функции базы данных, которые производят вычисление по ряду значений и возвращают одиночное значение (известные также как статистические функции баз данных), могут вызываться напрямую. Другие канонические функции могут вызываться только в составе запроса LINQ to Entities. Чтобы вызвать агрегатную функцию напрямую, ей необходимо передать экземпляр <xref:System.Data.Objects.ObjectQuery%601>. Дополнительные сведения см. в приведенном ниже втором примере.  
  
> [!NOTE]
> Методы класса <xref:System.Data.Objects.SqlClient.SqlFunctions> поддерживаются только в функциях SQL Server. Аналогичные классы, предоставляющие функции баз данных, могут быть доступны в других поставщиках.  
  
## <a name="example"></a>Пример  

 В следующем примере используется [модель AdventureWorks Sales](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks). В примере выполняется запрос LINQ to Entities, в котором с помощью метода <xref:System.Data.Objects.SqlClient.SqlFunctions.CharIndex%2A> возвращаются все контакты, в которых фамилия начинается с «Si»:  
  
 [!code-csharp[DP L2E CanonicalAndStoreFunctions#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e canonicalandstorefunctions/cs/program.cs#3)]
 [!code-vb[DP L2E CanonicalAndStoreFunctions#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e canonicalandstorefunctions/vb/module1.vb#3)]  
  
## <a name="example"></a>Пример  

 В следующем примере используется [модель AdventureWorks Sales](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks). В примере напрямую вызывается статистический метод <xref:System.Data.Objects.SqlClient.SqlFunctions.ChecksumAggregate%2A>. Обратите внимание, что в функцию передается экземпляр <xref:System.Data.Objects.ObjectQuery%601>, что позволяет вызывать ее, хотя она и не входит в состав запроса LINQ to Entities.  
  
 [!code-csharp[DP L2E CanonicalAndStoreFunctions#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e canonicalandstorefunctions/cs/program.cs#4)]
 [!code-vb[DP L2E CanonicalAndStoreFunctions#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e canonicalandstorefunctions/vb/module1.vb#4)]  
  
## <a name="see-also"></a>См. также

- [Вызов функций в запросах LINQ to Entities](calling-functions-in-linq-to-entities-queries.md)
- [Запросы в LINQ to Entities](queries-in-linq-to-entities.md)
