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
# <a name="connect-net-for-apache-spark-to-sql-server"></a>Подключение .NET для Apache Spark к SQL Server

Из этой статьи вы узнаете, как подключиться к экземпляру SQL Server из приложения [.NET для Apache Spark](https://github.com/dotnet/spark).

## <a name="configure-sql-server-to-grant-your-application-access"></a>Настройка SQL Server для предоставления доступа приложению

1. Добавьте имя пользователя и пароль входа, выбрав проверку подлинности SQL Server в экземпляре SQL Server.
2. Предоставьте этому пользователю необходимые разрешения на соответствующем уровне базы данных, как показано ниже:

    ![разрешения SQL Server](./media/connect-external-sources/SqlServerAuth.png)

3. Убедитесь, что порт по умолчанию `1433` для SQL Server разрешен в брандмауэре.
4. Откройте диспетчер конфигурации SQL, чтобы включить протокол TCP/IP в конфигурации сети, как показано ниже.

    ![Включение протокола TCP/IP в SQL Server](./media/connect-external-sources/SqlServerTCPIP.png)

    Также обратите внимание на значение параметра **Прослушивать все** на изображенной выше вкладке в разделе **Протокол** .

5. Настройте для порта TCP/IP значение 1433 для всех необходимых IP-адресов, если для параметра `Listen All` установлено значение `No`. В противном случае задайте для порта TCP значение IPAll.

    ![Порт TCP/IP в SQL Server](./media/connect-external-sources/SQLServerTCPIIPPort.png)

## <a name="connect-to-sql-server-from-your-application"></a>Подключение к SQL Server из приложения

1. Используйте драйвер Microsoft JDBC для SQL Server, чтобы обеспечить подключение к базе данных из вашего приложения (скачайте с [официального веб-сайта](https://docs.microsoft.com/sql/connect/jdbc/download-microsoft-jdbc-driver-for-sql-server?view=sql-server-ver15)).
2. Настройте следующие параметры конфигурации для подключения к экземпляру и базе данных SQL Server из приложения:
    1. **connection_url** : это URL-адрес, используемый для подключения к экземпляру или базе данных SQL Server, который имеет следующий формат:

        ```
        jdbc:sqlserver://<SQL_server_IP_address>:1433;instanceName=<instance_name>;databaseName=<database_name>;
        ```

    2. **dbtable** : имя таблицы, к которой осуществляется доступ.
    3. **user** : учетная запись пользователя, настроенная на шаге 1 настройки SQL Server.
    4. **password** : пароль пользователя, настроенный на шаге 1 настройки SQL Server.
3. Используйте приведенную выше конфигурацию в коде приложения для чтения данных из таблицы, как показано ниже.

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
