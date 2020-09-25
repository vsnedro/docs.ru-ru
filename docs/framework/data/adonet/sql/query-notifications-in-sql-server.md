---
title: Уведомления запросов в SQL Server
description: Узнайте, как использовать уведомления о запросах для уведомления приложений об изменении данных в SQL Server базе данных, например для обновления отображения приложений.
ms.date: 03/30/2017
ms.assetid: 0f0ba1a1-3180-4af8-87f7-c795dc8f8f55
ms.openlocfilehash: 8001f75d7e278a965b6e8e00e4b9af7b770a8bb5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91183095"
---
# <a name="query-notifications-in-sql-server"></a><span data-ttu-id="f7b2a-103">Уведомления запросов в SQL Server</span><span class="sxs-lookup"><span data-stu-id="f7b2a-103">Query Notifications in SQL Server</span></span>

<span data-ttu-id="f7b2a-104">С помощью уведомлений о запросах, построенных на основе инфраструктуры компонента Service Broker, приложения могут получать извещения об изменениях данных.</span><span class="sxs-lookup"><span data-stu-id="f7b2a-104">Built upon the Service Broker infrastructure, query notifications allow applications to be notified when data has changed.</span></span> <span data-ttu-id="f7b2a-105">Эта функция особенно полезна для приложений, которые предоставляют кэш данных из базы данных (например, для веб-приложений), и которым требуются уведомления об изменении исходных данных.</span><span class="sxs-lookup"><span data-stu-id="f7b2a-105">This feature is particularly useful for applications that provide a cache of information from a database, such as a Web application, and need to be notified when the source data is changed.</span></span>  
  
 <span data-ttu-id="f7b2a-106">Существует три способа реализации уведомлений о запросах с помощью ADO.NET:</span><span class="sxs-lookup"><span data-stu-id="f7b2a-106">There are three ways you can implement query notifications using ADO.NET:</span></span>  
  
1. <span data-ttu-id="f7b2a-107">Реализация низкого уровня обеспечивается классом `SqlNotificationRequest`, который предоставляет функциональные возможности на стороне сервера, что позволяет выполнять команду с запросом на уведомления.</span><span class="sxs-lookup"><span data-stu-id="f7b2a-107">The low-level implementation is provided by the `SqlNotificationRequest` class that exposes server-side functionality, enabling you to execute a command with a notification request.</span></span>  
  
2. <span data-ttu-id="f7b2a-108">Высокоуровневая реализация обеспечивается классом `SqlDependency`, который является классом, предоставляющим высокоуровневую абстракцию функций уведомления между исходным приложением и SQL Server, что позволяет использовать зависимость для обнаружения изменений на сервере.</span><span class="sxs-lookup"><span data-stu-id="f7b2a-108">The high-level implementation is provided by the `SqlDependency` class, which is a class that provides a high-level abstraction of notification functionality between the source application and SQL Server, enabling you to use a dependency to detect changes in the server.</span></span> <span data-ttu-id="f7b2a-109">В большинстве случаев это самый простой и самый эффективный способ задействовать возможности уведомления SQL Server в управляемых клиентских приложениях с помощью поставщика данных .NET Framework для SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f7b2a-109">In most cases, this is the simplest and most effective way to leverage SQL Server notifications capability by managed client applications using the .NET Framework Data Provider for SQL Server.</span></span>  
  
3. <span data-ttu-id="f7b2a-110">Кроме того, веб-приложения, построенные с помощью ASP.NET 2.0 и более поздних версий, могут использовать вспомогательные классы `SqlCacheDependency`.</span><span class="sxs-lookup"><span data-stu-id="f7b2a-110">In addition, Web applications built using ASP.NET 2.0 or later can use the `SqlCacheDependency` helper classes.</span></span>  
  
 <span data-ttu-id="f7b2a-111">Уведомления о запросах удобно использовать в приложениях, которые должны обновлять дисплеи и кэши в ответ на изменения в базовых данных.</span><span class="sxs-lookup"><span data-stu-id="f7b2a-111">Query notifications are used for applications that need to refresh displays or caches in response to changes in underlying data.</span></span> <span data-ttu-id="f7b2a-112">Microsoft SQL Server позволяет приложениям .NET Framework передавать команды в SQL Server и запрашивать уведомления, если при выполнении одной и той же команды может получиться результирующий набор, отличный от полученного первоначально.</span><span class="sxs-lookup"><span data-stu-id="f7b2a-112">Microsoft SQL Server allows .NET Framework applications to send a command to SQL Server and request notification if executing the same command would produce result sets different from those initially retrieved.</span></span> <span data-ttu-id="f7b2a-113">Формируемые на сервере уведомления отправляются через очереди для последующей обработки.</span><span class="sxs-lookup"><span data-stu-id="f7b2a-113">Notifications generated at the server are sent through queues to be processed later.</span></span>  
  
 <span data-ttu-id="f7b2a-114">Уведомления можно настроить для инструкций SELECT и EXECUTE.</span><span class="sxs-lookup"><span data-stu-id="f7b2a-114">You can set up notifications for SELECT and EXECUTE statements.</span></span> <span data-ttu-id="f7b2a-115">При использовании инструкции EXECUTE SQL Server регистрирует уведомление о выполненной команде, а не саму инструкцию EXECUTE.</span><span class="sxs-lookup"><span data-stu-id="f7b2a-115">When using an EXECUTE statement, SQL Server registers a notification for the command executed rather than the EXECUTE statement itself.</span></span> <span data-ttu-id="f7b2a-116">Команда должна соответствовать требованиям, предъявляемым к инструкции SELECT.</span><span class="sxs-lookup"><span data-stu-id="f7b2a-116">The command must meet the requirements and limitations for a SELECT statement.</span></span> <span data-ttu-id="f7b2a-117">Если регистрируемая команда состоит из нескольких инструкций, ядро СУБД создает уведомления для каждой из них.</span><span class="sxs-lookup"><span data-stu-id="f7b2a-117">When a command that registers a notification contains more than one statement, the Database Engine creates a notification for each statement in the batch.</span></span>  
  
 <span data-ttu-id="f7b2a-118">Если вы разрабатываете приложение, в котором вам потребуются надежные отправки уведомлений при изменении данных, ознакомьтесь с разделом **планирование эффективной стратегии уведомлений о запросах** и **альтернативных способов уведомления о запросах** в статье [планирование уведомлений](/previous-versions/sql/sql-server-2008-r2/ms187528(v=sql.105)) .</span><span class="sxs-lookup"><span data-stu-id="f7b2a-118">If you are developing an application where you need reliable sub-second notifications when data changes, review the sections **Planning an Efficient Query Notifications Strategy** and **Alternatives to Query Notifications** in the [Planning for Notifications](/previous-versions/sql/sql-server-2008-r2/ms187528(v=sql.105)) article.</span></span> <span data-ttu-id="f7b2a-119">Дополнительные сведения об уведомлениях о запросах и SQL Server Service Broker см. по следующим ссылкам на статьи в документации по SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f7b2a-119">For more information about Query Notifications and SQL Server Service Broker, see the following links to articles in the SQL Server documentation.</span></span>  
  
 <span data-ttu-id="f7b2a-120">**Документация по SQL Server**</span><span class="sxs-lookup"><span data-stu-id="f7b2a-120">**SQL Server documentation**</span></span>  
  
- <span data-ttu-id="f7b2a-121">[Использование уведомлений о запросах](/previous-versions/sql/sql-server-2008-r2/ms175110(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="f7b2a-121">[Using Query Notifications](/previous-versions/sql/sql-server-2008-r2/ms175110(v=sql.105))</span></span>  
  
- <span data-ttu-id="f7b2a-122">[Создание запроса для уведомления](/previous-versions/sql/sql-server-2008-r2/ms181122(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="f7b2a-122">[Creating a Query for Notification](/previous-versions/sql/sql-server-2008-r2/ms181122(v=sql.105))</span></span>  
  
- <span data-ttu-id="f7b2a-123">[Разработка (компонент Service Broker)](/previous-versions/sql/sql-server-2008-r2/bb522889(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="f7b2a-123">[Development (Service Broker)](/previous-versions/sql/sql-server-2008-r2/bb522889(v=sql.105))</span></span>  
  
- <span data-ttu-id="f7b2a-124">[Информационный центр по компоненту Service Broker для разработчиков](/previous-versions/sql/sql-server-2008-r2/ms166100(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="f7b2a-124">[Service Broker Developer InfoCenter](/previous-versions/sql/sql-server-2008-r2/ms166100(v=sql.105))</span></span>  
  
- <span data-ttu-id="f7b2a-125">[Руководство разработчика (компонент Service Broker)](/previous-versions/sql/sql-server-2008-r2/bb522908(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="f7b2a-125">[Developer's Guide (Service Broker)](/previous-versions/sql/sql-server-2008-r2/bb522908(v=sql.105))</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f7b2a-126">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="f7b2a-126">In This Section</span></span>  

 [<span data-ttu-id="f7b2a-127">Включение уведомлений о запросах</span><span class="sxs-lookup"><span data-stu-id="f7b2a-127">Enabling Query Notifications</span></span>](enabling-query-notifications.md)  
 <span data-ttu-id="f7b2a-128">Описание использования уведомлений о запросах, включая требования для их включения и использования.</span><span class="sxs-lookup"><span data-stu-id="f7b2a-128">Discusses how to use query notifications, including the requirements for enabling and using them.</span></span>  
  
 [<span data-ttu-id="f7b2a-129">SqlDependency в приложении ASP.NET</span><span class="sxs-lookup"><span data-stu-id="f7b2a-129">SqlDependency in an ASP.NET Application</span></span>](sqldependency-in-an-aspnet-app.md)  
 <span data-ttu-id="f7b2a-130">Демонстрирует использование уведомлений запросов из приложения ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="f7b2a-130">Demonstrates how to use query notifications from an ASP.NET application.</span></span>  
  
 [<span data-ttu-id="f7b2a-131">Обнаружение изменений с помощью SqlDependency</span><span class="sxs-lookup"><span data-stu-id="f7b2a-131">Detecting Changes with SqlDependency</span></span>](detecting-changes-with-sqldependency.md)  
 <span data-ttu-id="f7b2a-132">Сведения об определении отличия результатов запроса от изначально полученных.</span><span class="sxs-lookup"><span data-stu-id="f7b2a-132">Demonstrates how to detect when query results will be different from those originally received.</span></span>  
  
 [<span data-ttu-id="f7b2a-133">Выполнение SqlCommand с помощью SqlNotificationRequest</span><span class="sxs-lookup"><span data-stu-id="f7b2a-133">SqlCommand Execution with a SqlNotificationRequest</span></span>](sqlcommand-execution-with-a-sqlnotificationrequest.md)  
 <span data-ttu-id="f7b2a-134">Демонстрирует настройку объекта <xref:System.Data.SqlClient.SqlCommand> для работы с уведомлением запроса.</span><span class="sxs-lookup"><span data-stu-id="f7b2a-134">Demonstrates configuring a <xref:System.Data.SqlClient.SqlCommand> object to work with a query notification.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="f7b2a-135">Справка</span><span class="sxs-lookup"><span data-stu-id="f7b2a-135">Reference</span></span>  

 <xref:System.Data.Sql.SqlNotificationRequest>  
 <span data-ttu-id="f7b2a-136">Описание класса <xref:System.Data.Sql.SqlNotificationRequest> и всех его членов.</span><span class="sxs-lookup"><span data-stu-id="f7b2a-136">Describes the <xref:System.Data.Sql.SqlNotificationRequest> class and all of its members.</span></span>  
  
 <xref:System.Data.SqlClient.SqlDependency>  
 <span data-ttu-id="f7b2a-137">Описание класса <xref:System.Data.SqlClient.SqlDependency> и всех его членов.</span><span class="sxs-lookup"><span data-stu-id="f7b2a-137">Describes the <xref:System.Data.SqlClient.SqlDependency> class and all of its members.</span></span>  
  
 <xref:System.Web.Caching.SqlCacheDependency>  
 <span data-ttu-id="f7b2a-138">Описание класса <xref:System.Web.Caching.SqlCacheDependency> и всех его членов.</span><span class="sxs-lookup"><span data-stu-id="f7b2a-138">Describes the <xref:System.Web.Caching.SqlCacheDependency> class and all of its members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7b2a-139">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f7b2a-139">See also</span></span>

- [<span data-ttu-id="f7b2a-140">SQL Server и ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f7b2a-140">SQL Server and ADO.NET</span></span>](index.md)
- [<span data-ttu-id="f7b2a-141">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f7b2a-141">ADO.NET Overview</span></span>](../ado-net-overview.md)
