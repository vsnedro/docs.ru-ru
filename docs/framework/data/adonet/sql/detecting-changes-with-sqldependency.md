---
title: Обнаружение изменений с использованием SqlDependency
description: Свяжите объект SqlDependency с SqlCommand, чтобы определить, когда результаты запроса отличаются от первоначально извлеченных в ADO.NET.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e6a58316-f005-4477-92e1-45cc2eb8c5b4
ms.openlocfilehash: b196d42477e1778c45df64b1390502645fdd649d
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286472"
---
# <a name="detecting-changes-with-sqldependency"></a>Обнаружение изменений с использованием SqlDependency

Объект <xref:System.Data.SqlClient.SqlDependency> может быть связан с <xref:System.Data.SqlClient.SqlCommand> для определения отличия результатов запроса от изначально полученных. Вы также можете назначить делегата событию `OnChange`, которое сработает при изменении результатов для связанной команды. Объект <xref:System.Data.SqlClient.SqlDependency> необходимо связать с командой перед ее выполнением. Свойство `HasChanges` объекта <xref:System.Data.SqlClient.SqlDependency> также можно использовать для определения изменений результатов запроса с момента первого извлечения данных.

## <a name="security-considerations"></a>Соображения безопасности

Инфраструктура зависимостей зависит от объекта <xref:System.Data.SqlClient.SqlConnection>, открытого при вызове <xref:System.Data.SqlClient.SqlDependency.Start%2A>, для получения уведомлений об изменении базовых данных для данной команды. Возможность для клиента инициировать вызов `SqlDependency.Start` контролируется с помощью <xref:System.Data.SqlClient.SqlClientPermission> и атрибутов управления доступом для кода. Дополнительные сведения см. в разделе [Включение уведомлений о запросах](enabling-query-notifications.md) и [разграничение доступа кода и ADO.NET](../code-access-security.md).

### <a name="example"></a>Пример

Ниже приведены шаги для объявления зависимости, выполнения команды и получения уведомления при изменении результирующего набора:

1. Создает соединение `SqlDependency` с сервером.

2. Создайте объекты <xref:System.Data.SqlClient.SqlConnection> и <xref:System.Data.SqlClient.SqlCommand> для подключения к серверу и определения инструкции Transact-SQL.

3. Создайте новый объект `SqlDependency` или используйте имеющийся, привязав его к объекту `SqlCommand`. На внутреннем уровне будет создан объект <xref:System.Data.Sql.SqlNotificationRequest>, который при необходимости может быть привязан к объекту команды. Данный запрос на уведомление содержит внутренний идентификатор, который однозначно идентифицирует этот объект `SqlDependency`. Он также запускает прослушиватель клиента, если он еще не активен.

4. Добавьте для обработчика события подписку на событие `OnChange` объекта `SqlDependency`.

5. Выполните команду, используя любой из методов `Execute` объекта `SqlCommand`. Так как команда связана с объектом уведомления, сервер распознает, что он должен сгенерировать уведомление, и информация об очереди будет указывать на очередь зависимостей.

6. Остановите подключение объекта `SqlDependency` к серверу.

Если впоследствии какой-либо пользователь изменит базовые данные, Microsoft SQL Server обнаружит уведомление, ожидающее такое изменение, и опубликует уведомление, которое обрабатывается и пересылается клиенту через базовый объект `SqlConnection`, созданный путем вызова `SqlDependency.Start`. Прослушиватель клиента получит сообщение о недействительности. Затем прослушиватель клиента найдет связанный объект `SqlDependency` и запустит событие `OnChange`.

В приведенном ниже фрагменте кода показан конструктивный шаблон, который необходимо использовать для создания примера приложения.

```vb
Sub Initialization()
    ' Create a dependency connection.
    SqlDependency.Start(connectionString, queueName)
End Sub

Sub SomeMethod()
    ' Assume connection is an open SqlConnection.
    ' Create a new SqlCommand object.
    Using command As New SqlCommand( _
      "SELECT ShipperID, CompanyName, Phone FROM dbo.Shippers", _
      connection)

        ' Create a dependency and associate it with the SqlCommand.
        Dim dependency As New SqlDependency(command)
        ' Maintain the refernce in a class member.
        ' Subscribe to the SqlDependency event.
        AddHandler dependency.OnChange, AddressOf OnDependencyChange

        ' Execute the command.
        Using reader = command.ExecuteReader()
            ' Process the DataReader.
        End Using
    End Using
End Sub

' Handler method
Sub OnDependencyChange(ByVal sender As Object, _
    ByVal e As SqlNotificationEventArgs)
    ' Handle the event (for example, invalidate this cache entry).
End Sub

Sub Termination()
    ' Release the dependency
    SqlDependency.Stop(connectionString, queueName)
End Sub
```

```csharp
void Initialization()
{
    // Create a dependency connection.
    SqlDependency.Start(connectionString, queueName);
}

void SomeMethod()
{
    // Assume connection is an open SqlConnection.

    // Create a new SqlCommand object.
    using (SqlCommand command=new SqlCommand(
        "SELECT ShipperID, CompanyName, Phone FROM dbo.Shippers",
        connection))
    {

        // Create a dependency and associate it with the SqlCommand.
        SqlDependency dependency=new SqlDependency(command);
        // Maintain the reference in a class member.

        // Subscribe to the SqlDependency event.
        dependency.OnChange+=new
           OnChangeEventHandler(OnDependencyChange);

        // Execute the command.
        using (SqlDataReader reader = command.ExecuteReader())
        {
            // Process the DataReader.
        }
    }
}

// Handler method
void OnDependencyChange(object sender,
   SqlNotificationEventArgs e )
{
  // Handle the event (for example, invalidate this cache entry).
}

void Termination()
{
    // Release the dependency.
    SqlDependency.Stop(connectionString, queueName);
}
```

## <a name="see-also"></a>См. также

- [Уведомления запросов в SQL Server](query-notifications-in-sql-server.md)
- [Общие сведения об ADO.NET](../ado-net-overview.md)
