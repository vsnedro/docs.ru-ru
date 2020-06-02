---
title: Практическое руководство. Как прямо выполнять запросы SQL
description: Узнайте, как использовать ExecuteQuery для выполнения запроса и последующего преобразования результатов непосредственно в объекты в случаях, когда LINQ to SQL запрос недостаточен.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e491b9bf-741a-4296-9f51-76c25ddf6a82
ms.openlocfilehash: 59bd404e41f6be1181d6a625c31ee23358db0df3
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286369"
---
# <a name="how-to-directly-execute-sql-queries"></a>Практическое руководство. Как прямо выполнять запросы SQL
Технология [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] преобразует написанные пользователем запросы в параметризованные запросы SQL (в текстовой форме) и отправляет их на сервер SQL для обработки.  
  
 В SQL не может выполняться все разнообразие методов, локально доступных приложению. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] пытается преобразовать эти локальные методы в равноценные операторы и функции среды SQL. Большинство методов и операторов на .NET Framework встроенных типах имеют прямой перевод команд SQL. Некоторые методы и операторы можно создать из доступных функций, а те, которые не могут быть преобразованы, вызывают исключения во время выполнения. Дополнительные сведения см. в разделе [Сопоставление типов SQL-CLR](sql-clr-type-mapping.md).  
  
 В тех случаях, когда запроса [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] недостаточно для выполнения специализированной задачи, можно использовать метод <xref:System.Data.Linq.DataContext.ExecuteQuery%2A> для выполнения запроса SQL и последующего преобразования результата запроса непосредственно в объекты.  
  
## <a name="example"></a>Пример  
 В следующем примере предполагается, что данные для класса `Customer` распределены по двум таблицам (customer1 и customer2). Запрос возвращает последовательность объектов `Customer`.  
  
 [!code-csharp[DLinqQuerying#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#4)]
 [!code-vb[DLinqQuerying#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#4)]  
  
 При условии, что имена столбцов в табличных результатах соответствуют свойствам столбца класса сущностей, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] создает объекты из любого SQL запроса.  
  
## <a name="example"></a>Пример  
 Метод <xref:System.Data.Linq.DataContext.ExecuteQuery%2A> также допускает использование параметров. Для выполнения параметризованного запроса используется код, аналогичный представленному ниже.  
  
 [!code-csharp[DLinqQuerying#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#5)]
 [!code-vb[DLinqQuerying#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#5)]  
  
 Параметры записываются в тексте запроса с помощью той же нотации с фигурными скобками, которая используется в методах `Console.WriteLine()` и `String.Format()`. `String.Format()`Фактически вызывается в предоставленной вами строке запроса, заменяя заключенные в фигурные скобки параметры созданными именами параметров, такими как @p0 , @p1 ..., @p (n).  
  
## <a name="see-also"></a>См. также

- [Основные сведения](background-information.md)
- [Запрос к базе данных](querying-the-database.md)
