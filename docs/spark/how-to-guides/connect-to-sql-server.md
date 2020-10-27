---
title: Подключение .NET для Apache Spark к SQL Server
description: Узнайте, как подключиться к экземпляру SQL Server из приложения .NET для Apache Spark.
ms.author: nidutta
author: Niharikadutta
ms.date: 10/09/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: b20710000d8717b5df238aa9a782371fbe586037
ms.sourcegitcommit: 67ebdb695fd017d79d9f1f7f35d145042d5a37f7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/20/2020
ms.locfileid: "92224031"
---
# <a name="connect-net-for-apache-spark-to-sql-server"></a><span data-ttu-id="20595-103">Подключение .NET для Apache Spark к SQL Server</span><span class="sxs-lookup"><span data-stu-id="20595-103">Connect .NET for Apache Spark to SQL Server</span></span>

<span data-ttu-id="20595-104">Из этой статьи вы узнаете, как подключиться к экземпляру SQL Server из приложения [.NET для Apache Spark](https://github.com/dotnet/spark).</span><span class="sxs-lookup"><span data-stu-id="20595-104">In this article, you learn how to connect to an SQL server instance from your [.NET for Apache Spark](https://github.com/dotnet/spark) application.</span></span>

## <a name="configure-sql-server-to-grant-your-application-access"></a><span data-ttu-id="20595-105">Настройка SQL Server для предоставления доступа приложению</span><span class="sxs-lookup"><span data-stu-id="20595-105">Configure SQL Server to grant your application access</span></span>

1. <span data-ttu-id="20595-106">Добавьте имя пользователя и пароль входа, выбрав проверку подлинности SQL Server в экземпляре SQL Server.</span><span class="sxs-lookup"><span data-stu-id="20595-106">Add a login user and password choosing SQL Server authentication to your SQL Server instance.</span></span>
2. <span data-ttu-id="20595-107">Предоставьте этому пользователю необходимые разрешения на соответствующем уровне базы данных, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="20595-107">Give that login user necessary permissions at the relevant database level as shown below:</span></span>

    ![разрешения SQL Server](./media/connect-external-sources/SqlServerAuth.png)

3. <span data-ttu-id="20595-109">Убедитесь, что порт по умолчанию `1433` для SQL Server разрешен в брандмауэре.</span><span class="sxs-lookup"><span data-stu-id="20595-109">Make sure the default port for SQL Server `1433` is allowed through the firewall.</span></span>
4. <span data-ttu-id="20595-110">Откройте диспетчер конфигурации SQL, чтобы включить протокол TCP/IP в конфигурации сети, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="20595-110">Open SQL configure manager to enable TCP/IP through the network configuration as shown below:</span></span>

    ![Включение протокола TCP/IP в SQL Server](./media/connect-external-sources/SqlServerTCPIP.png)

    <span data-ttu-id="20595-112">Также обратите внимание на значение параметра **Прослушивать все** на изображенной выше вкладке в разделе **Протокол** .</span><span class="sxs-lookup"><span data-stu-id="20595-112">Also note the value of **Listen All** in above tab under **Protocol** .</span></span>

5. <span data-ttu-id="20595-113">Настройте для порта TCP/IP значение 1433 для всех необходимых IP-адресов, если для параметра `Listen All` установлено значение `No`.</span><span class="sxs-lookup"><span data-stu-id="20595-113">Configure the TCP/IP port to 1433 for all required IP addresses if the `Listen All` is set to `No`.</span></span> <span data-ttu-id="20595-114">В противном случае задайте для порта TCP значение IPAll.</span><span class="sxs-lookup"><span data-stu-id="20595-114">Otherwise, set the TCP Port in IPAll.</span></span>

    ![Порт TCP/IP в SQL Server](./media/connect-external-sources/SQLServerTCPIIPPort.png)

## <a name="connect-to-sql-server-from-your-application"></a><span data-ttu-id="20595-116">Подключение к SQL Server из приложения</span><span class="sxs-lookup"><span data-stu-id="20595-116">Connect to SQL Server from your application</span></span>

1. <span data-ttu-id="20595-117">Используйте драйвер Microsoft JDBC для SQL Server, чтобы обеспечить подключение к базе данных из вашего приложения (скачайте с [официального веб-сайта](https://docs.microsoft.com/sql/connect/jdbc/download-microsoft-jdbc-driver-for-sql-server?view=sql-server-ver15)).</span><span class="sxs-lookup"><span data-stu-id="20595-117">Use the Microsoft JDBC Driver for SQL Server to provide database connectivity through your application (download from [this official website](https://docs.microsoft.com/sql/connect/jdbc/download-microsoft-jdbc-driver-for-sql-server?view=sql-server-ver15)).</span></span>
2. <span data-ttu-id="20595-118">Настройте следующие параметры конфигурации для подключения к экземпляру и базе данных SQL Server из приложения:</span><span class="sxs-lookup"><span data-stu-id="20595-118">Set the following configurations to connect to the SQL server instance and database from your application:</span></span>
    1. <span data-ttu-id="20595-119">**connection_url** : это URL-адрес, используемый для подключения к экземпляру или базе данных SQL Server, который имеет следующий формат:</span><span class="sxs-lookup"><span data-stu-id="20595-119">**connection_url** : This is the URL used to connect to the SQL server instance/database and has the following format:</span></span>

        ```
        jdbc:sqlserver://<SQL_server_IP_address>:1433;instanceName=<instance_name>;databaseName=<database_name>;
        ```

    2. <span data-ttu-id="20595-120">**dbtable** : имя таблицы, к которой осуществляется доступ.</span><span class="sxs-lookup"><span data-stu-id="20595-120">**dbtable** : Name of table being accessed.</span></span>
    3. <span data-ttu-id="20595-121">**user** : учетная запись пользователя, настроенная на шаге 1 настройки SQL Server.</span><span class="sxs-lookup"><span data-stu-id="20595-121">**user** : Login user set up in Step 1 of configuring the SQL server.</span></span>
    4. <span data-ttu-id="20595-122">**password** : пароль пользователя, настроенный на шаге 1 настройки SQL Server.</span><span class="sxs-lookup"><span data-stu-id="20595-122">**password** : Password of user set up in Step 1 of configuring the SQL server.</span></span>
3. <span data-ttu-id="20595-123">Используйте приведенную выше конфигурацию в коде приложения для чтения данных из таблицы, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="20595-123">Use the above configuration in your application code to read the data from a table as shown below:</span></span>

    ```csharp
    static void Main()
    {
        SparkSession spark = SparkSession
            .Builder()
            .AppName("Connect to SQL Server")
            .GetOrCreate();

        string connection_url = "<URL to connect to SQL server instance>";
        string dbtable = "<database table to access>";
        string user = "<Login user name>";
        string password = "<Login user password>";

        DataFrame jdbcDF = spark.Read()
            .Format("jdbc")
            .Option("driver", "com.microsoft.sqlserver.jdbc.SQLServerDriver")
            .Option("url", connection_url)
            .Option("dbtable", dbtable)
            .Option("user", user)
            .Option("password", password).Load();
        jdbcDF.Show(); // Displays the content of the SQL table as a DataFrame
    }
    ```
