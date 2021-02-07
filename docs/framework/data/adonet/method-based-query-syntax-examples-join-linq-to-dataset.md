---
description: 'Дополнительные сведения: Method-Based примеры синтаксиса запросов: Join (LINQ to DataSet)'
title: Примеры синтаксиса запросов на основе методов. Соединение (LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 4fd5ed2c-b03a-4054-a3ed-3ddb380d7d9d
ms.openlocfilehash: f19921ceb874d120a3b50896f3ec82159ef03aac
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99672703"
---
# <a name="method-based-query-syntax-examples-join-linq-to-dataset"></a>Примеры синтаксиса запросов на основе методов. Соединение (LINQ to DataSet)

Соединение - важная операция в запросах, которые обращаются к источникам данных без доступных для навигации взаимосвязей, например к таблицам реляционной базы данных. Соединение двух источников данных представляет собой взаимосвязь объектов одного источника данных с объектами, использующими общий атрибут в другом источнике данных. Дополнительные сведения см. в разделе Общие сведения [о стандартных операторах запросов (C#)](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) или [Общие сведения о стандартных операторах запросов (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md).  
  
 В примерах данного раздела показано, как использовать метод <xref:System.Linq.Enumerable.Join%2A> для запросов к объекту <xref:System.Data.DataSet> с использованием синтаксиса запросов на основе методов.  
  
 `FillDataSet`Метод, используемый в этих примерах, задается при [загрузке данных в набор данных](loading-data-into-a-dataset.md).  
  
 В примерах данного раздела используются таблицы Contact, Address, Product, SalesOrderHeader и SalesOrderDetail из образца базы данных AdventureWorks.  
  
 В примерах этого раздела используются следующие `using` / `Imports` инструкции:  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 Дополнительные сведения см. в разделе [инструкции. Создание проекта LINQ to DataSet в Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md).  
  
## <a name="join"></a>Join  
  
### <a name="example"></a>Пример  

 В этом примере выполняется соединение таблиц `Contact` и `SalesOrderHeader`.  
  
 [!code-csharp[DP LINQ to DataSet Examples#JoinSimple_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#joinsimple_mq)]
 [!code-vb[DP LINQ to DataSet Examples#JoinSimple_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#joinsimple_mq)]  
  
### <a name="example"></a>Пример  

 В этом примере выполняется соединение таблиц `Contact` и `SalesOrderHeader`, а результаты группируются по идентификатору контактного лица.  
  
 [!code-csharp[DP LINQ to DataSet Examples#JoinWithGroupedResults_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#joinwithgroupedresults_mq)]
 [!code-vb[DP LINQ to DataSet Examples#JoinWithGroupedResults_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#joinwithgroupedresults_mq)]  
  
## <a name="see-also"></a>См. также

- [Загрузка данных в набор данных](loading-data-into-a-dataset.md)
- [Примеры LINQ to DataSet](linq-to-dataset-examples.md)
- [Общие сведения о стандартных операторах запроса (C#)](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [Общие сведения о стандартных операторах запроса (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
