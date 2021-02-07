---
description: 'Дополнительные сведения: запросы LINQ to SQL'
title: Запросы LINQ to SQL
ms.date: 03/30/2017
ms.assetid: f4897aaa-7f44-4c20-a471-b948c2971aae
ms.openlocfilehash: 5b5df2095043b01eb426de86e4add91941bb74c6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99712484"
---
# <a name="linq-to-sql-queries"></a>Запросы LINQ to SQL

Запросы определяются с [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] использованием того же синтаксиса, что и в LINQ. Единственное отличие заключается в том, что объекты, на которые ссылаются запросы, сопоставляются с элементами базы данных. Дополнительные сведения см. в разделе [Введение в запросы LINQ (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).  
  
 Технология [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] преобразует написанные пользователем запросы в эквивалентные запросы SQL и отправляет их на сервер для обработки. В частности, приложение использует API-интерфейс [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] для выполнения запроса. Затем поставщик [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] преобразует запрос в текст SQL и делегирует выполнение поставщику ADO. Поставщик ADO возвращает результаты запроса в виде объекта `DataReader`. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]Поставщик преобразует результаты ADO в <xref:System.Linq.IQueryable> коллекцию объектов User.  
  
> [!NOTE]
> Большинство методов и операторов на платформа .NET Framework встроенных типах имеют прямой перевод в SQL. Те, которые LINQ не может преобразовать, создают исключения времени выполнения. Дополнительные сведения см. в разделе [Сопоставление типов SQL-CLR](sql-clr-type-mapping.md).  
  
 В следующей таблице показаны сходства и различия между LINQ и [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] элементами запроса.  
  
|Компонент|Запрос LINQ|[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Запрос|  
|----------|----------------|----------------------------------------------------------------------|  
|Тип возвращаемого значения для локальной переменной, содержащей запрос (для запросов, которые возвращают последовательности)|Универсальный тип `IEnumerable`|Универсальный тип `IQueryable`|  
|Указание источника данных|Использует `From` предложение (Visual Basic) или `from` (C#)|Аналогично|  
|Фильтрация|Использует `Where` / `where` предложение|Аналогично|  
|Группирование|Использует `Group…By` / `groupby` предложение|Аналогично|  
|Выбор (проецирование)|Использует `Select` / `select` предложение|Аналогично|  
|Отложенное или немедленное выполнение|См. статью [Введение в запросы LINQ (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md) .|Аналогично|  
|Реализация соединений|Использует `Join` / `join` предложение|Может использовать `Join` / `join` предложение, но более эффективно использует <xref:System.Data.Linq.Mapping.AssociationAttribute> атрибут. Дополнительные сведения см. в разделе [запросы по связям](querying-across-relationships.md).|  
|Удаленное или локальное выполнение||Дополнительные сведения см. в разделе [удаленное и локальное выполнение](remote-vs-local-execution.md).|  
|Потоковое или кэшированное выполнение запросов|Не применяется при использовании локальной памяти||  
  
## <a name="see-also"></a>См. также

- [Введение в запросы LINQ (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)
- [Основные операции запроса LINQ](../../../../../csharp/programming-guide/concepts/linq/basic-linq-query-operations.md)
- [Связи типов в операциях запросов LINQ](../../../../../csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md)
- [Основные принципы запросов](query-concepts.md)
