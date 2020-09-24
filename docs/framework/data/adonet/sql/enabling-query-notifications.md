---
title: Включение уведомлений запросов
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a5333e19-8e55-4aa9-82dc-ca8745e516ed
ms.openlocfilehash: 4e9b3a2e1f176a9d01e983bc469cc4032fa5d730
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91156177"
---
# <a name="enabling-query-notifications"></a>Включение уведомлений запросов

Приложения, использующие уведомления о запросах, имеют общий набор требований. Чтобы поддерживать уведомления о запросах, источник данных SQL должен быть правильно настроен, а пользователь должен иметь соответствующие права доступа на стороне клиента и сервера.  
  
 Чтобы использовать уведомления о запросах, сделайте следующее:  
  
- Включите уведомления о запросах для своей базы данных.  
  
- Предоставьте идентификатору пользователя, используемому для подключения к базе данных, необходимые разрешения.  
  
- Используйте объект <xref:System.Data.SqlClient.SqlCommand> для выполнения допустимой инструкции SELECT со связанным объектом уведомления: <xref:System.Data.SqlClient.SqlDependency> или <xref:System.Data.Sql.SqlNotificationRequest>.  
  
- Укажите код для обработки уведомления в случае изменения отслеживаемых данных.  
  
## <a name="query-notifications-requirements"></a>Требования к уведомлениям о запросах  

 Уведомления о запросах поддерживаются только для инструкций SELECT, которые соответствуют конкретным требованиям. В приведенной ниже таблице указаны ссылки на статьи о компоненте Service Broker и уведомлениях о запросах в электронной документации по SQL Server.  
  
 **Документация по SQL Server**  
  
- [Создание запроса для уведомления](/previous-versions/sql/sql-server-2008-r2/ms181122(v=sql.105))  
  
- [Вопросы безопасности, связанные с компонентом Service Broker](/previous-versions/sql/sql-server-2005/ms166059(v=sql.90))  
  
- [Защита и обеспечение безопасности (компонент Service Broker)](/previous-versions/sql/sql-server-2008-r2/bb522911(v=sql.105))  
  
- [Вопросы безопасности, связанные со службами уведомления](/previous-versions/sql/sql-server-2005/ms172604(v=sql.90))  
  
- [Права доступа для уведомлений о запросах](/previous-versions/sql/sql-server-2008-r2/ms188311(v=sql.105))  
  
- [Вопросы интернационализации, связанные с компонентом Service Broker](/previous-versions/sql/sql-server-2005/ms166028(v=sql.90))  
  
- [Вопросы проектирования решений (компонент Service Broker)](/previous-versions/sql/sql-server-2008-r2/bb522899(v=sql.105))  
  
- [Информационный центр по компоненту Service Broker для разработчиков](/previous-versions/sql/sql-server-2008-r2/ms166100(v=sql.105))  
  
- [Руководство разработчика (компонент Service Broker)](/previous-versions/sql/sql-server-2008-r2/bb522908(v=sql.105))  
  
## <a name="enabling-query-notifications-to-run-sample-code"></a>Включение уведомлений о запросах для запуска примеров кода  

 Чтобы включить компонент Service Broker для базы данных **AdventureWorks** с помощью среды SQL Server Management Studio, выполните следующую инструкцию Transact-SQL.  
  
 `ALTER DATABASE AdventureWorks SET ENABLE_BROKER;`  
  
 Для правильного запуска примеров уведомлений о запросах необходимо выполнить на сервере базы данных приведенные ниже инструкции Transact-SQL.  
  
```sql
CREATE QUEUE ContactChangeMessages;  
  
CREATE SERVICE ContactChangeNotifications  
  ON QUEUE ContactChangeMessages  
([http://schemas.microsoft.com/SQL/Notifications/PostQueryNotification]);  
```  
  
## <a name="query-notifications-permissions"></a>Права доступа для уведомлений о запросах  

 Пользователям, выполняющим команды для запроса уведомлений, необходимо разрешение базы данных SUBSCRIBE QUERY NOTIFICATIONS на сервере.  
  
 Код на стороне клиента, который выполняется в случае частичного доверия, требует разрешения <xref:System.Data.SqlClient.SqlClientPermission>.  
  
 Следующий код создает объект <xref:System.Data.SqlClient.SqlClientPermission>, устанавливая для <xref:System.Security.Permissions.PermissionState> значение <xref:System.Security.Permissions.PermissionState.Unrestricted>. <xref:System.Security.CodeAccessPermission.Demand%2A> принудительно создает <xref:System.Security.SecurityException> во время выполнения, если все вызывающие методы, расположенные выше в стеке вызовов, не получили разрешения.  
  
 [!code-csharp[DataWorks SqlNotification.Perms#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlNotification.Perms/CS/source.cs#1)]
 [!code-vb[DataWorks SqlNotification.Perms#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlNotification.Perms/VB/source.vb#1)]  
  
## <a name="choosing-a-notification-object"></a>Выбор объекта уведомления  

 API-интерфейс уведомлений о запросах предоставляет два объекта для обработки уведомлений: <xref:System.Data.SqlClient.SqlDependency> и <xref:System.Data.Sql.SqlNotificationRequest>. В общем случае в большинстве приложений, не основанных на ASP.NET, следует использовать объект <xref:System.Data.SqlClient.SqlDependency>. В приложениях ASP.NET следует использовать объект более высокого уровня <xref:System.Web.Caching.SqlCacheDependency>, который является оболочкой для <xref:System.Data.SqlClient.SqlDependency> и предоставляет платформу для администрирования объектов уведомлений и кэша.  
  
### <a name="using-sqldependency"></a>Использование SqlDependency  

 Чтобы вы могли использовать объект <xref:System.Data.SqlClient.SqlDependency>, в используемой базе данных SQL Server должен быть включен компонент Service Broker, а пользователи должны иметь права для получения уведомлений. Объекты компонента Service Broker, такие как очередь уведомлений, предопределены.  
  
 Кроме того, объект <xref:System.Data.SqlClient.SqlDependency> автоматически запускает рабочий поток для обработки уведомлений по мере их поступления в очередь. Он также проводит синтаксический анализ сообщения компонента Service Broker, предоставляя данные в виде аргументов событий. Экземпляр <xref:System.Data.SqlClient.SqlDependency> создается путем вызова метода `Start`, который устанавливает зависимость с базой данных. Это статический метод, который необходимо вызывать только один раз во время инициализации приложения для каждого требуемого подключения к базе данных. Метод `Stop` необходимо вызывать при завершении приложения для каждого установленного подключения зависимости.  
  
### <a name="using-sqlnotificationrequest"></a>Использование SqlNotificationRequest  

 В то же время <xref:System.Data.Sql.SqlNotificationRequest> требует реализации всей инфраструктуры прослушивания вручную. Кроме того, необходимо будет определить все поддерживающие объекты компонента Service Broker, такие как очередь, служба и типы сообщений, поддерживаемые очередью. Этот ручной подход полезен, если для вашего приложения требуются специальные сообщения с уведомлениями или параметры уведомлений или же если ваше приложение является частью более крупного приложения Service Broker.  
  
## <a name="see-also"></a>См. также раздел

- [Уведомления о запросах в SQL Server](query-notifications-in-sql-server.md)
- [Общие сведения об ADO.NET](../ado-net-overview.md)
