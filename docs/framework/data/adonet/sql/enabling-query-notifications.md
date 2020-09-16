---
title: Включение уведомлений запросов
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a5333e19-8e55-4aa9-82dc-ca8745e516ed
ms.openlocfilehash: 693e67b4d369eb69b8e0a9dded6decb2d3928459
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90554883"
---
# <a name="enabling-query-notifications"></a><span data-ttu-id="8370b-102">Включение уведомлений запросов</span><span class="sxs-lookup"><span data-stu-id="8370b-102">Enabling Query Notifications</span></span>
<span data-ttu-id="8370b-103">Приложения, использующие уведомления о запросах, имеют общий набор требований.</span><span class="sxs-lookup"><span data-stu-id="8370b-103">Applications that consume query notifications have a common set of requirements.</span></span> <span data-ttu-id="8370b-104">Чтобы поддерживать уведомления о запросах, источник данных SQL должен быть правильно настроен, а пользователь должен иметь соответствующие права доступа на стороне клиента и сервера.</span><span class="sxs-lookup"><span data-stu-id="8370b-104">Your data source must be correctly configured to support SQL query notifications, and the user must have the correct client-side and server-side permissions.</span></span>  
  
 <span data-ttu-id="8370b-105">Чтобы использовать уведомления о запросах, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="8370b-105">To use query notifications you must:</span></span>  
  
- <span data-ttu-id="8370b-106">Включите уведомления о запросах для своей базы данных.</span><span class="sxs-lookup"><span data-stu-id="8370b-106">Enable query notifications for your database.</span></span>  
  
- <span data-ttu-id="8370b-107">Предоставьте идентификатору пользователя, используемому для подключения к базе данных, необходимые разрешения.</span><span class="sxs-lookup"><span data-stu-id="8370b-107">Ensure that the user ID used to connect to the database has the necessary permissions.</span></span>  
  
- <span data-ttu-id="8370b-108">Используйте объект <xref:System.Data.SqlClient.SqlCommand> для выполнения допустимой инструкции SELECT со связанным объектом уведомления: <xref:System.Data.SqlClient.SqlDependency> или <xref:System.Data.Sql.SqlNotificationRequest>.</span><span class="sxs-lookup"><span data-stu-id="8370b-108">Use a <xref:System.Data.SqlClient.SqlCommand> object to execute a valid SELECT statement with an associated notification object—either <xref:System.Data.SqlClient.SqlDependency> or <xref:System.Data.Sql.SqlNotificationRequest>.</span></span>  
  
- <span data-ttu-id="8370b-109">Укажите код для обработки уведомления в случае изменения отслеживаемых данных.</span><span class="sxs-lookup"><span data-stu-id="8370b-109">Provide code to process the notification if the data being monitored changes.</span></span>  
  
## <a name="query-notifications-requirements"></a><span data-ttu-id="8370b-110">Требования к уведомлениям о запросах</span><span class="sxs-lookup"><span data-stu-id="8370b-110">Query Notifications Requirements</span></span>  
 <span data-ttu-id="8370b-111">Уведомления о запросах поддерживаются только для инструкций SELECT, которые соответствуют конкретным требованиям.</span><span class="sxs-lookup"><span data-stu-id="8370b-111">Query notifications are supported only for SELECT statements that meet a list of specific requirements.</span></span> <span data-ttu-id="8370b-112">В приведенной ниже таблице указаны ссылки на статьи о компоненте Service Broker и уведомлениях о запросах в электронной документации по SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8370b-112">The following table provides links to the Service Broker and Query Notifications documentation in SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="8370b-113">**Документация по SQL Server**</span><span class="sxs-lookup"><span data-stu-id="8370b-113">**SQL Server documentation**</span></span>  
  
- <span data-ttu-id="8370b-114">[Создание запроса для уведомления](/previous-versions/sql/sql-server-2008-r2/ms181122(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="8370b-114">[Creating a Query for Notification](/previous-versions/sql/sql-server-2008-r2/ms181122(v=sql.105))</span></span>  
  
- <span data-ttu-id="8370b-115">[Вопросы безопасности, связанные с компонентом Service Broker](/previous-versions/sql/sql-server-2005/ms166059(v=sql.90))</span><span class="sxs-lookup"><span data-stu-id="8370b-115">[Security Considerations for Service Broker](/previous-versions/sql/sql-server-2005/ms166059(v=sql.90))</span></span>  
  
- <span data-ttu-id="8370b-116">[Защита и обеспечение безопасности (компонент Service Broker)](/previous-versions/sql/sql-server-2008-r2/bb522911(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="8370b-116">[Security and Protection (Service Broker)](/previous-versions/sql/sql-server-2008-r2/bb522911(v=sql.105))</span></span>  
  
- <span data-ttu-id="8370b-117">[Вопросы безопасности, связанные со службами уведомления](/previous-versions/sql/sql-server-2005/ms172604(v=sql.90))</span><span class="sxs-lookup"><span data-stu-id="8370b-117">[Security Considerations for Notifications Services](/previous-versions/sql/sql-server-2005/ms172604(v=sql.90))</span></span>  
  
- <span data-ttu-id="8370b-118">[Права доступа для уведомлений о запросах](/previous-versions/sql/sql-server-2008-r2/ms188311(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="8370b-118">[Query Notification Permissions](/previous-versions/sql/sql-server-2008-r2/ms188311(v=sql.105))</span></span>  
  
- <span data-ttu-id="8370b-119">[Вопросы интернационализации, связанные с компонентом Service Broker](/previous-versions/sql/sql-server-2005/ms166028(v=sql.90))</span><span class="sxs-lookup"><span data-stu-id="8370b-119">[International Considerations for Service Broker](/previous-versions/sql/sql-server-2005/ms166028(v=sql.90))</span></span>  
  
- <span data-ttu-id="8370b-120">[Вопросы проектирования решений (компонент Service Broker)](/previous-versions/sql/sql-server-2008-r2/bb522899(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="8370b-120">[Solution Design Considerations (Service Broker)](/previous-versions/sql/sql-server-2008-r2/bb522899(v=sql.105))</span></span>  
  
- <span data-ttu-id="8370b-121">[Информационный центр по компоненту Service Broker для разработчиков](/previous-versions/sql/sql-server-2008-r2/ms166100(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="8370b-121">[Service Broker Developer InfoCenter](/previous-versions/sql/sql-server-2008-r2/ms166100(v=sql.105))</span></span>  
  
- <span data-ttu-id="8370b-122">[Руководство разработчика (компонент Service Broker)](/previous-versions/sql/sql-server-2008-r2/bb522908(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="8370b-122">[Developer's Guide (Service Broker)](/previous-versions/sql/sql-server-2008-r2/bb522908(v=sql.105))</span></span>  
  
## <a name="enabling-query-notifications-to-run-sample-code"></a><span data-ttu-id="8370b-123">Включение уведомлений о запросах для запуска примеров кода</span><span class="sxs-lookup"><span data-stu-id="8370b-123">Enabling Query Notifications to Run Sample Code</span></span>  
 <span data-ttu-id="8370b-124">Чтобы включить компонент Service Broker для базы данных **AdventureWorks** с помощью среды SQL Server Management Studio, выполните следующую инструкцию Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="8370b-124">To enable Service Broker on the **AdventureWorks** database by using SQL Server Management Studio, execute the following Transact-SQL statement:</span></span>  
  
 `ALTER DATABASE AdventureWorks SET ENABLE_BROKER;`  
  
 <span data-ttu-id="8370b-125">Для правильного запуска примеров уведомлений о запросах необходимо выполнить на сервере базы данных приведенные ниже инструкции Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="8370b-125">For the query notification samples to run correctly, the following Transact-SQL statements must be executed on the database server.</span></span>  
  
```sql
CREATE QUEUE ContactChangeMessages;  
  
CREATE SERVICE ContactChangeNotifications  
  ON QUEUE ContactChangeMessages  
([http://schemas.microsoft.com/SQL/Notifications/PostQueryNotification]);  
```  
  
## <a name="query-notifications-permissions"></a><span data-ttu-id="8370b-126">Права доступа для уведомлений о запросах</span><span class="sxs-lookup"><span data-stu-id="8370b-126">Query Notifications Permissions</span></span>  
 <span data-ttu-id="8370b-127">Пользователям, выполняющим команды для запроса уведомлений, необходимо разрешение базы данных SUBSCRIBE QUERY NOTIFICATIONS на сервере.</span><span class="sxs-lookup"><span data-stu-id="8370b-127">Users who execute commands requesting notification must have SUBSCRIBE QUERY NOTIFICATIONS database permission on the server.</span></span>  
  
 <span data-ttu-id="8370b-128">Код на стороне клиента, который выполняется в случае частичного доверия, требует разрешения <xref:System.Data.SqlClient.SqlClientPermission>.</span><span class="sxs-lookup"><span data-stu-id="8370b-128">Client-side code that runs in a partial trust situation requires the <xref:System.Data.SqlClient.SqlClientPermission>.</span></span>  
  
 <span data-ttu-id="8370b-129">Следующий код создает объект <xref:System.Data.SqlClient.SqlClientPermission>, устанавливая для <xref:System.Security.Permissions.PermissionState> значение <xref:System.Security.Permissions.PermissionState.Unrestricted>.</span><span class="sxs-lookup"><span data-stu-id="8370b-129">The following code creates a <xref:System.Data.SqlClient.SqlClientPermission> object, setting the <xref:System.Security.Permissions.PermissionState> to <xref:System.Security.Permissions.PermissionState.Unrestricted>.</span></span> <span data-ttu-id="8370b-130"><xref:System.Security.CodeAccessPermission.Demand%2A> принудительно создает <xref:System.Security.SecurityException> во время выполнения, если все вызывающие методы, расположенные выше в стеке вызовов, не получили разрешения.</span><span class="sxs-lookup"><span data-stu-id="8370b-130">The <xref:System.Security.CodeAccessPermission.Demand%2A> will force a <xref:System.Security.SecurityException> at run time if all callers higher in the call stack have not been granted the permission.</span></span>  
  
 [!code-csharp[DataWorks SqlNotification.Perms#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlNotification.Perms/CS/source.cs#1)]
 [!code-vb[DataWorks SqlNotification.Perms#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlNotification.Perms/VB/source.vb#1)]  
  
## <a name="choosing-a-notification-object"></a><span data-ttu-id="8370b-131">Выбор объекта уведомления</span><span class="sxs-lookup"><span data-stu-id="8370b-131">Choosing a Notification Object</span></span>  
 <span data-ttu-id="8370b-132">API-интерфейс уведомлений о запросах предоставляет два объекта для обработки уведомлений: <xref:System.Data.SqlClient.SqlDependency> и <xref:System.Data.Sql.SqlNotificationRequest>.</span><span class="sxs-lookup"><span data-stu-id="8370b-132">The query notifications API provides two objects to process notifications: <xref:System.Data.SqlClient.SqlDependency> and <xref:System.Data.Sql.SqlNotificationRequest>.</span></span> <span data-ttu-id="8370b-133">В общем случае в большинстве приложений, не основанных на ASP.NET, следует использовать объект <xref:System.Data.SqlClient.SqlDependency>.</span><span class="sxs-lookup"><span data-stu-id="8370b-133">In general, most non-ASP.NET applications should use the <xref:System.Data.SqlClient.SqlDependency> object.</span></span> <span data-ttu-id="8370b-134">В приложениях ASP.NET следует использовать объект более высокого уровня <xref:System.Web.Caching.SqlCacheDependency>, который является оболочкой для <xref:System.Data.SqlClient.SqlDependency> и предоставляет платформу для администрирования объектов уведомлений и кэша.</span><span class="sxs-lookup"><span data-stu-id="8370b-134">ASP.NET applications should use the higher-level <xref:System.Web.Caching.SqlCacheDependency>, which wraps <xref:System.Data.SqlClient.SqlDependency> and provides a framework for administering the notification and cache objects.</span></span>  
  
### <a name="using-sqldependency"></a><span data-ttu-id="8370b-135">Использование SqlDependency</span><span class="sxs-lookup"><span data-stu-id="8370b-135">Using SqlDependency</span></span>  
 <span data-ttu-id="8370b-136">Чтобы вы могли использовать объект <xref:System.Data.SqlClient.SqlDependency>, в используемой базе данных SQL Server должен быть включен компонент Service Broker, а пользователи должны иметь права для получения уведомлений.</span><span class="sxs-lookup"><span data-stu-id="8370b-136">To use <xref:System.Data.SqlClient.SqlDependency>, Service Broker must be enabled for the SQL Server database being used, and users must have permissions to receive notifications.</span></span> <span data-ttu-id="8370b-137">Объекты компонента Service Broker, такие как очередь уведомлений, предопределены.</span><span class="sxs-lookup"><span data-stu-id="8370b-137">Service Broker objects, such as the notification queue, are predefined.</span></span>  
  
 <span data-ttu-id="8370b-138">Кроме того, объект <xref:System.Data.SqlClient.SqlDependency> автоматически запускает рабочий поток для обработки уведомлений по мере их поступления в очередь. Он также проводит синтаксический анализ сообщения компонента Service Broker, предоставляя данные в виде аргументов событий.</span><span class="sxs-lookup"><span data-stu-id="8370b-138">In addition, <xref:System.Data.SqlClient.SqlDependency> automatically launches a worker thread to process notifications as they are posted to the queue; it also parses the Service Broker message, exposing the information as event argument data.</span></span> <span data-ttu-id="8370b-139">Экземпляр <xref:System.Data.SqlClient.SqlDependency> создается путем вызова метода `Start`, который устанавливает зависимость с базой данных.</span><span class="sxs-lookup"><span data-stu-id="8370b-139"><xref:System.Data.SqlClient.SqlDependency> must be initialized by calling the `Start` method to establish a dependency to the database.</span></span> <span data-ttu-id="8370b-140">Это статический метод, который необходимо вызывать только один раз во время инициализации приложения для каждого требуемого подключения к базе данных.</span><span class="sxs-lookup"><span data-stu-id="8370b-140">This is a static method that needs to be called only once during application initialization for each database connection required.</span></span> <span data-ttu-id="8370b-141">Метод `Stop` необходимо вызывать при завершении приложения для каждого установленного подключения зависимости.</span><span class="sxs-lookup"><span data-stu-id="8370b-141">The `Stop` method should be called at application termination for each dependency connection that was made.</span></span>  
  
### <a name="using-sqlnotificationrequest"></a><span data-ttu-id="8370b-142">Использование SqlNotificationRequest</span><span class="sxs-lookup"><span data-stu-id="8370b-142">Using SqlNotificationRequest</span></span>  
 <span data-ttu-id="8370b-143">В то же время <xref:System.Data.Sql.SqlNotificationRequest> требует реализации всей инфраструктуры прослушивания вручную.</span><span class="sxs-lookup"><span data-stu-id="8370b-143">In contrast, <xref:System.Data.Sql.SqlNotificationRequest> requires you to implement the entire listening infrastructure yourself.</span></span> <span data-ttu-id="8370b-144">Кроме того, необходимо будет определить все поддерживающие объекты компонента Service Broker, такие как очередь, служба и типы сообщений, поддерживаемые очередью.</span><span class="sxs-lookup"><span data-stu-id="8370b-144">In addition, all the supporting Service Broker objects such as the queue, service, and message types supported by the queue must be defined.</span></span> <span data-ttu-id="8370b-145">Этот ручной подход полезен, если для вашего приложения требуются специальные сообщения с уведомлениями или параметры уведомлений или же если ваше приложение является частью более крупного приложения Service Broker.</span><span class="sxs-lookup"><span data-stu-id="8370b-145">This manual approach is useful if your application requires special notification messages or notification behaviors, or if your application is part of a larger Service Broker application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8370b-146">См. также</span><span class="sxs-lookup"><span data-stu-id="8370b-146">See also</span></span>

- [<span data-ttu-id="8370b-147">Уведомления о запросах в SQL Server</span><span class="sxs-lookup"><span data-stu-id="8370b-147">Query Notifications in SQL Server</span></span>](query-notifications-in-sql-server.md)
- [<span data-ttu-id="8370b-148">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="8370b-148">ADO.NET Overview</span></span>](../ado-net-overview.md)
