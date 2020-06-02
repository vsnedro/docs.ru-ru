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
# <a name="detecting-changes-with-sqldependency"></a><span data-ttu-id="8bfaf-103">Обнаружение изменений с использованием SqlDependency</span><span class="sxs-lookup"><span data-stu-id="8bfaf-103">Detecting Changes with SqlDependency</span></span>

<span data-ttu-id="8bfaf-104">Объект <xref:System.Data.SqlClient.SqlDependency> может быть связан с <xref:System.Data.SqlClient.SqlCommand> для определения отличия результатов запроса от изначально полученных.</span><span class="sxs-lookup"><span data-stu-id="8bfaf-104">A <xref:System.Data.SqlClient.SqlDependency> object can be associated with a <xref:System.Data.SqlClient.SqlCommand> in order to detect when query results differ from those originally retrieved.</span></span> <span data-ttu-id="8bfaf-105">Вы также можете назначить делегата событию `OnChange`, которое сработает при изменении результатов для связанной команды.</span><span class="sxs-lookup"><span data-stu-id="8bfaf-105">You can also assign a delegate to the `OnChange` event, which will fire when the results change for an associated command.</span></span> <span data-ttu-id="8bfaf-106">Объект <xref:System.Data.SqlClient.SqlDependency> необходимо связать с командой перед ее выполнением.</span><span class="sxs-lookup"><span data-stu-id="8bfaf-106">You must associate the <xref:System.Data.SqlClient.SqlDependency> with the command before you execute the command.</span></span> <span data-ttu-id="8bfaf-107">Свойство `HasChanges` объекта <xref:System.Data.SqlClient.SqlDependency> также можно использовать для определения изменений результатов запроса с момента первого извлечения данных.</span><span class="sxs-lookup"><span data-stu-id="8bfaf-107">The `HasChanges` property of the <xref:System.Data.SqlClient.SqlDependency> can also be used to determine if the query results have changed since the data was first retrieved.</span></span>

## <a name="security-considerations"></a><span data-ttu-id="8bfaf-108">Соображения безопасности</span><span class="sxs-lookup"><span data-stu-id="8bfaf-108">Security Considerations</span></span>

<span data-ttu-id="8bfaf-109">Инфраструктура зависимостей зависит от объекта <xref:System.Data.SqlClient.SqlConnection>, открытого при вызове <xref:System.Data.SqlClient.SqlDependency.Start%2A>, для получения уведомлений об изменении базовых данных для данной команды.</span><span class="sxs-lookup"><span data-stu-id="8bfaf-109">The dependency infrastructure relies on a <xref:System.Data.SqlClient.SqlConnection> that is opened when <xref:System.Data.SqlClient.SqlDependency.Start%2A> is called in order to receive notifications that the underlying data has changed for a given command.</span></span> <span data-ttu-id="8bfaf-110">Возможность для клиента инициировать вызов `SqlDependency.Start` контролируется с помощью <xref:System.Data.SqlClient.SqlClientPermission> и атрибутов управления доступом для кода.</span><span class="sxs-lookup"><span data-stu-id="8bfaf-110">The ability for a client to initiate the call to `SqlDependency.Start` is controlled through the use of <xref:System.Data.SqlClient.SqlClientPermission> and code access security attributes.</span></span> <span data-ttu-id="8bfaf-111">Дополнительные сведения см. в разделе [Включение уведомлений о запросах](enabling-query-notifications.md) и [разграничение доступа кода и ADO.NET](../code-access-security.md).</span><span class="sxs-lookup"><span data-stu-id="8bfaf-111">For more information, see [Enabling Query Notifications](enabling-query-notifications.md) and [Code Access Security and ADO.NET](../code-access-security.md).</span></span>

### <a name="example"></a><span data-ttu-id="8bfaf-112">Пример</span><span class="sxs-lookup"><span data-stu-id="8bfaf-112">Example</span></span>

<span data-ttu-id="8bfaf-113">Ниже приведены шаги для объявления зависимости, выполнения команды и получения уведомления при изменении результирующего набора:</span><span class="sxs-lookup"><span data-stu-id="8bfaf-113">The following steps illustrate how to declare a dependency, execute a command, and receive a notification when the result set changes:</span></span>

1. <span data-ttu-id="8bfaf-114">Создает соединение `SqlDependency` с сервером.</span><span class="sxs-lookup"><span data-stu-id="8bfaf-114">Initiate a `SqlDependency` connection to the server.</span></span>

2. <span data-ttu-id="8bfaf-115">Создайте объекты <xref:System.Data.SqlClient.SqlConnection> и <xref:System.Data.SqlClient.SqlCommand> для подключения к серверу и определения инструкции Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="8bfaf-115">Create <xref:System.Data.SqlClient.SqlConnection> and <xref:System.Data.SqlClient.SqlCommand> objects to connect to the server and define a Transact-SQL statement.</span></span>

3. <span data-ttu-id="8bfaf-116">Создайте новый объект `SqlDependency` или используйте имеющийся, привязав его к объекту `SqlCommand`.</span><span class="sxs-lookup"><span data-stu-id="8bfaf-116">Create a new `SqlDependency` object, or use an existing one, and bind it to the `SqlCommand` object.</span></span> <span data-ttu-id="8bfaf-117">На внутреннем уровне будет создан объект <xref:System.Data.Sql.SqlNotificationRequest>, который при необходимости может быть привязан к объекту команды.</span><span class="sxs-lookup"><span data-stu-id="8bfaf-117">Internally, this creates a <xref:System.Data.Sql.SqlNotificationRequest> object and binds it to the command object as needed.</span></span> <span data-ttu-id="8bfaf-118">Данный запрос на уведомление содержит внутренний идентификатор, который однозначно идентифицирует этот объект `SqlDependency`.</span><span class="sxs-lookup"><span data-stu-id="8bfaf-118">This notification request contains an internal identifier that uniquely identifies this `SqlDependency` object.</span></span> <span data-ttu-id="8bfaf-119">Он также запускает прослушиватель клиента, если он еще не активен.</span><span class="sxs-lookup"><span data-stu-id="8bfaf-119">It also starts the client listener if it is not already active.</span></span>

4. <span data-ttu-id="8bfaf-120">Добавьте для обработчика события подписку на событие `OnChange` объекта `SqlDependency`.</span><span class="sxs-lookup"><span data-stu-id="8bfaf-120">Subscribe an event handler to the `OnChange` event of the `SqlDependency` object.</span></span>

5. <span data-ttu-id="8bfaf-121">Выполните команду, используя любой из методов `Execute` объекта `SqlCommand`.</span><span class="sxs-lookup"><span data-stu-id="8bfaf-121">Execute the command using any of the `Execute` methods of the `SqlCommand` object.</span></span> <span data-ttu-id="8bfaf-122">Так как команда связана с объектом уведомления, сервер распознает, что он должен сгенерировать уведомление, и информация об очереди будет указывать на очередь зависимостей.</span><span class="sxs-lookup"><span data-stu-id="8bfaf-122">Because the command is bound to the notification object, the server recognizes that it must generate a notification, and the queue information will point to the dependencies queue.</span></span>

6. <span data-ttu-id="8bfaf-123">Остановите подключение объекта `SqlDependency` к серверу.</span><span class="sxs-lookup"><span data-stu-id="8bfaf-123">Stop the `SqlDependency` connection to the server.</span></span>

<span data-ttu-id="8bfaf-124">Если впоследствии какой-либо пользователь изменит базовые данные, Microsoft SQL Server обнаружит уведомление, ожидающее такое изменение, и опубликует уведомление, которое обрабатывается и пересылается клиенту через базовый объект `SqlConnection`, созданный путем вызова `SqlDependency.Start`.</span><span class="sxs-lookup"><span data-stu-id="8bfaf-124">If any user subsequently changes the underlying data, Microsoft SQL Server detects that there is a notification pending for such a change, and posts a notification that is processed and forwarded to the client through the underlying `SqlConnection` that was created by calling `SqlDependency.Start`.</span></span> <span data-ttu-id="8bfaf-125">Прослушиватель клиента получит сообщение о недействительности.</span><span class="sxs-lookup"><span data-stu-id="8bfaf-125">The client listener receives the invalidation message.</span></span> <span data-ttu-id="8bfaf-126">Затем прослушиватель клиента найдет связанный объект `SqlDependency` и запустит событие `OnChange`.</span><span class="sxs-lookup"><span data-stu-id="8bfaf-126">The client listener then locates the associated `SqlDependency` object and fires the `OnChange` event.</span></span>

<span data-ttu-id="8bfaf-127">В приведенном ниже фрагменте кода показан конструктивный шаблон, который необходимо использовать для создания примера приложения.</span><span class="sxs-lookup"><span data-stu-id="8bfaf-127">The following code fragment shows the design pattern you would use to create a sample application.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="8bfaf-128">См. также</span><span class="sxs-lookup"><span data-stu-id="8bfaf-128">See also</span></span>

- [<span data-ttu-id="8bfaf-129">Уведомления запросов в SQL Server</span><span class="sxs-lookup"><span data-stu-id="8bfaf-129">Query Notifications in SQL Server</span></span>](query-notifications-in-sql-server.md)
- [<span data-ttu-id="8bfaf-130">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="8bfaf-130">ADO.NET Overview</span></span>](../ado-net-overview.md)
