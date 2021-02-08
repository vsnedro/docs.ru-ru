---
description: 'Дополнительные сведения: отдельные операции по операциям копирования'
title: Отдельные операции массового копирования
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5e7ff0be-3f23-4996-a92c-bd54d65c3836
ms.openlocfilehash: f6b046fbd73ad798f3f9f117eea0b72f46e43b37
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99767483"
---
# <a name="single-bulk-copy-operations"></a>Отдельные операции массового копирования

Самый простой способ массового копирования SQL Server — выполнение одной операции в базе данных. По умолчанию операция массового копирования выполняется как изолированная, т. е. не как транзакция и без возможности отката.

> [!NOTE]
> Если при возникновении ошибки необходимо частично или полностью отменить массовое копирование, можно использовать управляемую <xref:System.Data.SqlClient.SqlBulkCopy> транзакцию или выполнить операцию массового копирования в существующей транзакции. **SqlBulkCopy** также будет работать с <xref:System.Transactions>, если это соединение прикреплено (явно или неявно) к транзакции **System.Transactions**.
>
> Дополнительные сведения см. в разделе [операции с транзакциями и операциями с массовым копированием](transaction-and-bulk-copy-operations.md).

Для массового копирования выполните описанную ниже процедуру.

1. Подключитесь к исходному серверу и получите данные для копирования. Данные также могут поступать из других источников, если их можно извлечь из объекта <xref:System.Data.IDataReader> или <xref:System.Data.DataTable>.

2. Подключитесь к целевому серверу (если только не требуется, чтобы объект **SqlBulkCopy** сам установил соединение).

3. Создайте объект <xref:System.Data.SqlClient.SqlBulkCopy>, задав все необходимые свойства.

4. Задайте свойство **DestinationTableName**, чтобы указать целевую таблицу для операции массовой вставки.

5. Вызовите один из методов **WriteToServer**.

6. Кроме того, если это необходимо, можно обновить свойства и вызвать метод **WriteToServer**.

7. Вызовите <xref:System.Data.SqlClient.SqlBulkCopy.Close%2A> или заключите код операций массового копирования в инструкцию `Using`.

> [!CAUTION]
> Мы рекомендуем, чтобы исходные и целевые типы данных столбцов совпадали. Если типы данных разные, объект **SqlBulkCopy** попытается преобразовать каждое исходное значение в целевой тип данных с использованием правил, применяемых методом <xref:System.Data.SqlClient.SqlParameter.Value%2A>. Преобразование может повлиять на производительность и может привести к непредвиденным ошибкам. Например, в большинстве случаев тип данных `Double` может преобразовываться в тип данных `Decimal`, но это происходит не всегда.

## <a name="example"></a>Пример

Следующее консольное приложение показывает, как загрузить данные с помощью класса <xref:System.Data.SqlClient.SqlBulkCopy>. В этом примере объект <xref:System.Data.SqlClient.SqlDataReader> используется, чтобы скопировать данные из таблицы **Production.Product** в базе данных SQL Server **AdventureWorks** в такую же таблицу в этой же базе данных.

> [!IMPORTANT]
> Этот пример не будет выполняться, если вы не создали рабочие таблицы, как описано в статье [Пример установки с помощью инструкций копирования](bulk-copy-example-setup.md). Этот код предназначен только для демонстрации синтаксиса использования **SqlBulkCopy**. Если исходная и целевая таблицы расположены в одном экземпляре SQL Server, будет проще и быстрее использовать инструкцию Transact-SQL `INSERT … SELECT` для копирования данных.

[!code-csharp[DataWorks BulkCopy.Single#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks BulkCopy.Single/CS/source.cs#1)]
[!code-vb[DataWorks BulkCopy.Single#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks BulkCopy.Single/VB/source.vb#1)]

## <a name="performing-a-bulk-copy-operation-using-transact-sql-and-the-command-class"></a>Выполнение операции массового копирования при помощи Transact-SQL и класса команды

Следующий пример демонстрирует использование метода <xref:System.Data.SqlClient.SqlCommand.ExecuteNonQuery%2A> для выполнения инструкции BULK INSERT.

> [!NOTE]
> Путь к источнику данных указан относительно сервера. Для успешного выполнения массового копирования у процесса сервера должен быть доступ к этому пути.

```vb
Using connection As SqlConnection = New SqlConnection(connectionString)
Dim queryString As String = _
    "BULK INSERT Northwind.dbo.[Order Details] FROM " & _
    "'f:\mydata\data.tbl' WITH (FORMATFILE='f:\mydata\data.fmt' )"
connection.Open()
SqlCommand command = New SqlCommand(queryString, connection);

command.ExecuteNonQuery()
End Using
```

```csharp
using (SqlConnection connection = New SqlConnection(connectionString))
{
string queryString =  "BULK INSERT Northwind.dbo.[Order Details] " +
    "FROM 'f:\mydata\data.tbl' " +
    "WITH ( FORMATFILE='f:\mydata\data.fmt' )";
connection.Open();
SqlCommand command = new SqlCommand(queryString, connection);

command.ExecuteNonQuery();
}
```

## <a name="see-also"></a>См. также

- [Операции с массовым копированием в SQL Server](bulk-copy-operations-in-sql-server.md)
- [Общие сведения об ADO.NET](../ado-net-overview.md)
