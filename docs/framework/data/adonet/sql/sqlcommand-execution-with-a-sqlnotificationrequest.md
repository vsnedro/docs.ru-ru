---
description: Дополнительные сведения о выполнении команды SqlCommand с помощью SqlNotificationRequest
title: Выполнение SqlCommand с помощью SqlNotificationRequest
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1776f48f-9bea-41f6-83a4-c990c7a2c991
ms.openlocfilehash: d3e82022794aa67d4bd20223cac852097f2be9dc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99767054"
---
# <a name="sqlcommand-execution-with-a-sqlnotificationrequest"></a>Выполнение SqlCommand с помощью SqlNotificationRequest

<xref:System.Data.SqlClient.SqlCommand> можно настроить на генерацию уведомления об изменении данных после их получения с сервера, и в случае повторного выполнения запроса результирующий набор будет отличаться. Это полезно для сценариев, в которых необходимо использовать пользовательские очереди уведомлений на сервере, или если не требуется поддерживать активные объекты.

## <a name="creating-the-notification-request"></a>Создание уведомления о запросах

Объект <xref:System.Data.Sql.SqlNotificationRequest> можно использовать для создания запроса на уведомление путем привязки его к объекту `SqlCommand`. Объект `SqlNotificationRequest` больше не понадобится после создания запроса. Вы можете запросить очередь для любых уведомлений и ответить соответствующим образом. Уведомления могут возникать, даже если приложение завершает работу и впоследствии перезапускается.

Если выполняется команда со связанным уведомлением, любые изменения в исходном результирующем наборе инициируют отправку сообщения в очередь SQL Server, которая была указана в запросе уведомления.

Опрос очереди SQL Server и интерпретация сообщения зависят от конкретного приложения. Приложение отвечает за опрос очереди и реагирование на основе содержимого сообщения.

> [!NOTE]
> При использовании запросов SQL Server на уведомления с помощью <xref:System.Data.SqlClient.SqlDependency>создайте свое собственное имя очереди вместо использования имени службы по умолчанию.

Для<xref:System.Data.Sql.SqlNotificationRequest> не существует новых элементов безопасности на стороне клиента. Это, в первую очередь, функция сервера, и сервер создал специальные разрешения, которые необходимы пользователям, чтобы запрашивать уведомления.

### <a name="example"></a>Пример

В следующем фрагменте кода показано, как создать <xref:System.Data.Sql.SqlNotificationRequest> и связать его с <xref:System.Data.SqlClient.SqlCommand>.

```vb
' Assume connection is an open SqlConnection.
' Create a new SqlCommand object.
Dim command As New SqlCommand( _
  "SELECT ShipperID, CompanyName, Phone FROM dbo.Shippers", connection)

' Create a SqlNotificationRequest object.
Dim notifcationRequest As New SqlNotificationRequest()
notificationRequest.id = "NotificationID"
notificationRequest.Service = "mySSBQueue"

' Associate the notification request with the command.
command.Notification = notificationRequest
' Execute the command.
command.ExecuteReader()
' Process the DataReader.
' You can use Transact-SQL syntax to periodically poll the
' SQL Server queue to see if you have a new message.
```

```csharp
// Assume connection is an open SqlConnection.
// Create a new SqlCommand object.
SqlCommand command=new SqlCommand(
 "SELECT ShipperID, CompanyName, Phone FROM dbo.Shippers", connection);

// Create a SqlNotificationRequest object.
SqlNotificationRequest notificationRequest=new SqlNotificationRequest();
notificationRequest.id="NotificationID";
notificationRequest.Service="mySSBQueue";

// Associate the notification request with the command.
command.Notification=notificationRequest;
// Execute the command.
command.ExecuteReader();
// Process the DataReader.
// You can use Transact-SQL syntax to periodically poll the
// SQL Server queue to see if you have a new message.
```

## <a name="see-also"></a>См. также

- [Уведомления о запросах в SQL Server](query-notifications-in-sql-server.md)
- [Общие сведения об ADO.NET](../ado-net-overview.md)
