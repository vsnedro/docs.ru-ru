---
description: 'Дополнительные сведения: локальные транзакции'
title: Локальные транзакции
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8ae3712f-ef5e-41a1-9ea9-b3d0399439f1
ms.openlocfilehash: 998024a6b08ec9cb97c8bb8dbbe2c9d17f38f350
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99681647"
---
# <a name="local-transactions"></a>Локальные транзакции

Транзакции в ADO.NET используются, когда требуется связать несколько задач так, чтобы они выполнялись как одна единица работы. Например, пусть приложение выполняет две задачи. Во-первых, оно заносит в таблицу сведения о заказе. Во-вторых, обновляет таблицу, содержащую список товаров на складе, списывая заказанные элементы. При сбое любой задачи будет выполнен откат обоих изменений.  
  
## <a name="determining-the-transaction-type"></a>Определение типа транзакции  

 Транзакция считается локальной, если она состоит из одной фазы и обрабатывается непосредственно базой данных. Транзакция считается распределенной, если она координируется монитором транзакций и использует для разрешения транзакций резервные механизмы (например, двухфазную фиксацию).  
  
 Каждый поставщик данных платформа .NET Framework имеет собственный `Transaction` объект для выполнения локальных транзакций. Если требуется выполнить транзакцию в базе данных SQL Server, выбирается транзакция <xref:System.Data.SqlClient>. Для транзакции Oracle используйте поставщик <xref:System.Data.OracleClient>. Кроме того, существует класс <xref:System.Data.Common.DbTransaction>, доступный для написания независимого от поставщика кода с использованием транзакций.  
  
> [!NOTE]
> Транзакции наиболее эффективны, когда выполняются на сервере. При работе с базой данных SQL Server, интенсивно использующей явные транзакции, следует рассмотреть возможность их записи в виде хранимых процедур при помощи инструкции Transact-SQL BEGIN TRANSACTION.
  
## <a name="performing-a-transaction-using-a-single-connection"></a>Выполнение транзакций с использованием одного соединения  

 В ADO.NET управление транзакциями осуществляется с помощью объекта `Connection`. Инициировать транзакцию можно с помощью метода `BeginTransaction`. После начала транзакции при помощи свойства `Transaction` объекта `Command` к ней можно прикрепить команду. Затем в зависимости от успеха или ошибки компонентов транзакции можно зафиксировать или откатить изменения, сделанные в источнике данных.  
  
> [!NOTE]
> Метод `EnlistDistributedTransaction` не должен использоваться для локальной транзакции.  
  
 Область действия транзакции ограничена соединением. В следующем примере выполняется явная транзакция, состоящая из двух отдельных команд в блоке `try`. Команды выполняют инструкции INSERT для таблицы Production. ScrapReason в образце базы данных AdventureWorks SQL Server, которая фиксируется, если исключения не создаются. Код в блоке `catch` откатит транзакцию, если возникнет исключение. При отмене транзакции или обрыве соединения до выполнения транзакции она откатывается автоматически.  
  
## <a name="example"></a>Пример  

 Чтобы осуществить транзакцию, выполните указанные ниже действия.  
  
1. Вызовите метод <xref:System.Data.SqlClient.SqlConnection.BeginTransaction%2A> объекта <xref:System.Data.SqlClient.SqlConnection> для отметки начала транзакции. Метод <xref:System.Data.SqlClient.SqlConnection.BeginTransaction%2A> возвращает ссылку на транзакцию. Эта ссылка назначается объектам <xref:System.Data.SqlClient.SqlCommand>, прикрепленным к транзакции.  
  
2. Присвойте объект `Transaction` свойству <xref:System.Data.SqlClient.SqlCommand.Transaction%2A> объекта <xref:System.Data.SqlClient.SqlCommand>. Исключение вызывается, если команда выполняется при соединении с активной транзакцией, а объект `Transaction` не был назначен свойству `Transaction` объекта `Command`.  
  
3. Выполните требуемые команды.  
  
4. Для выполнения транзакции вызовите метод <xref:System.Data.SqlClient.SqlTransaction.Commit%2A> объекта <xref:System.Data.SqlClient.SqlTransaction>, для завершения транзакции вызовите метод <xref:System.Data.SqlClient.SqlTransaction.Rollback%2A>. Транзакция откатывается, если соединение закрывается или пропадает до выполнения метода <xref:System.Data.SqlClient.SqlTransaction.Commit%2A> либо <xref:System.Data.SqlClient.SqlTransaction.Rollback%2A>.  
  
 В следующем примере кода демонстрируется транзакционная логика с использованием ADO.NET с Microsoft SQL Server.  
  
 [!code-csharp[DataWorks SqlTransaction.Local#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlTransaction.Local/CS/source.cs#1)]
 [!code-vb[DataWorks SqlTransaction.Local#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlTransaction.Local/VB/source.vb#1)]  
  
## <a name="see-also"></a>См. также

- [Транзакции и параллелизм](transactions-and-concurrency.md)
- [Распределенные транзакции](distributed-transactions.md)
- [Интеграция System. Transactions с SQL Server](system-transactions-integration-with-sql-server.md)
- [Общие сведения об ADO.NET](ado-net-overview.md)
