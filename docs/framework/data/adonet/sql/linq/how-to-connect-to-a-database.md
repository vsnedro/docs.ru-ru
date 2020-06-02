---
title: Практическое руководство. Как соединиться с базой данных
description: Узнайте, как использовать DataContext для подключения к базе данных в LINQ to SQL. Ознакомьтесь с этими примерами, чтобы использовать DataContext для подключения к базе данных и получения строк.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c33d74b3-530d-421b-a121-96786dd263a5
ms.openlocfilehash: c3320a598cb8407ab584530c615c2e5ef0de53c8
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286408"
---
# <a name="how-to-connect-to-a-database"></a>Практическое руководство. Как соединиться с базой данных
Основным каналом, через который выполняется подключение к базе данных, извлекаются объекты и отправляются изменения обратно в базу данных, является класс <xref:System.Data.Linq.DataContext>. Вы используете <xref:System.Data.Linq.DataContext> так же, как и ADO.NET <xref:System.Data.SqlClient.SqlConnection> . В действительности класс <xref:System.Data.Linq.DataContext> инициализируется с помощью предоставляемого пользователем подключения или строки подключения. Дополнительные сведения см. в разделе [методы DataContext (реляционный конструктор R)](/visualstudio/data-tools/datacontext-methods-o-r-designer).  
  
 Класс <xref:System.Data.Linq.DataContext> предназначен для преобразования запросов на получение объектов в запросы SQL, которые должны выполняться в базе данных, и последующей сборки объектов из результатов. <xref:System.Data.Linq.DataContext>Включает запрос LINQ, реализуя тот же шаблон оператора, что и стандартные операторы запросов, такие как `Where` и `Select` .  
  
> [!IMPORTANT]
> Одной из важнейших задач является обеспечение безопасности подключения. Дополнительные сведения см. [в разделе Безопасность в LINQ to SQL](security-in-linq-to-sql.md).  
  
## <a name="example"></a>Пример  
 В следующем примере класс <xref:System.Data.Linq.DataContext> используется для подключения к учебной базе данных "Northwind" и извлечения строк заказчиков, расположенных в Лондоне.  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#1)]
 [!code-vb[DLinqCommunicatingWithDatabase#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#1)]  
  
 Каждая таблица базы данных представлена коллекцией `Table`, доступной с помощью метода <xref:System.Data.Linq.DataContext.GetTable%2A>. Для идентификации таблицы используется класс сущностей.  
  
## <a name="example"></a>Пример  
 Рекомендация заключается в объявлении строго типизированного класса <xref:System.Data.Linq.DataContext> вместо использования базового класса <xref:System.Data.Linq.DataContext> и метода <xref:System.Data.Linq.DataContext.GetTable%2A>. Строго типизированный класс <xref:System.Data.Linq.DataContext> объявляет все коллекции `Table` в качестве членов контекста, как показано в следующем примере.  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#2)]
 [!code-vb[DLinqCommunicatingWithDatabase#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#2)]  
  
 После этого создание запроса на получение клиентов из Лондона можно осуществить более простым способом:  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#5)]
 [!code-vb[DLinqCommunicatingWithDatabase#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#5)]  
  
## <a name="see-also"></a>См. также

- [Установка связи с базой данных](communicating-with-the-database.md)
