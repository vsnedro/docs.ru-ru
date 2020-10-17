---
title: Подключение .NET для Apache Spark к MongoDB
description: Узнайте, как подключиться к экземпляру MongoDB из приложения .NET для Apache Spark.
ms.date: 10/09/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: 4cb78998ddb54621a84e9d224a814047e3c40246
ms.sourcegitcommit: eb7e87496f42361b1da98562dd75b516c9d58bbc
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/09/2020
ms.locfileid: "91878054"
---
# <a name="connect-net-for-apache-spark-to-mongodb"></a>Подключение .NET для Apache Spark к MongoDB

Из этой статьи вы узнаете, как подключиться к экземпляру MongoDB из приложения .NET для Apache Spark.

## <a name="prerequisites"></a>Предварительные требования

1. Настройте и запустите сервер MongoDB с базой данных [ и коллекцией ](https://docs.mongodb.com/manual/core/databases-and-collections/) (скачайте [этот сервер сообщества](https://www.mongodb.com/try/download/community) для локального сервера, либо можно попробовать использовать [MongoDB Atlas](https://www.mongodb.com/cloud/atlas) для облачной службы MongoDB).

## <a name="set-up-your-mongodb-instance"></a>Настройка экземпляра MongoDB

Чтобы организовать взаимодействие .NET для Apache Spark с экземпляром MongoDB, необходимо убедиться, что он правильно настроен, выполнив следующие действия.

1. Создайте имя пользователя и пароль для подключения к приложению и предоставьте пользователю необходимые разрешения или роли с помощью следующей команды через оболочку mongo:

    ```bash
    use database
    db.createUser(
      {
        user: "mySparkUser",
        pwd: "<password>",
        roles: [ { role: "userAdminAnyDatabase", db: "admin" }, "readWriteAnyDatabase" ]
      }
    )
    ```

2. Убедитесь, что IP-адрес компьютера, на котором запущено приложение .NET для Apache Spark, находится в списке разрешенных, чтобы сервер MongoDB мог подключиться к нему. Подробнее см. в [этом руководстве](https://docs.atlas.mongodb.com/security/add-ip-address-to-list/).

## <a name="configure-your-net-for-apache-spark-application"></a>Настройка приложения .NET для Apache Spark

1. Задайте следующие переменные, чтобы настроить приложение для взаимодействия с экземпляром MongoDB и чтения из коллекции.
    1. **authURI**: "Строка подключения, разрешающая приложению подключаться к требуемому экземпляру MongoDB". Формат строки подключения:

        ```
        "mongodb+srv://<username>:<password>@<cluster_address>/<database>.<collection>"
        ```

    2. **username**: имя пользователя учетной записи, созданной на шаге 1 предыдущего раздела.
    3. **password**: пароль учетной записи пользователя.
    4. **cluster_address**: имя узла/адрес кластера MongoDB
    5. **database**: база данных MongoDB, к которой необходимо подключиться
    6. **collection**: коллекция MongoDB, которую необходимо прочитать. (Здесь используется стандартный пример файла [`people.json`](https://github.com/apache/spark/blob/master/examples/src/main/resources/people.json), поставляемого в комплекте каждой установки Apache Spark.)

2. Используйте формат `com.mongodb.spark.sql.DefaultSource` (`spark.Read()`), как показано ниже в простом фрагменте кода:

    ```csharp
    class Program
    {
        static void Main()
        {
            var authURI = "mongodb+srv://<username>:<password>@<cluster_address>/<database>.<collection>?retryWrites=true&w=majority";
            SparkSession spark = SparkSession
                .Builder()
                .AppName("Connect to Mongo DB example")
                .Config("spark.mongodb.input.uri", authURI)
                .GetOrCreate();

            DataFrame df = spark.Read().Format("com.mongodb.spark.sql.DefaultSource").Load();
            df.PrintSchema();
            df.Show();
            spark.Stop();
        }
    }
    ```

## <a name="run-your-application"></a>Запуск приложения

Чтобы запустить приложение .NET для Apache Spark, определите модуль `mongo-spark-connector` как часть определения сборки в проекте Spark, используя `libraryDependency` в `build.sbt` для проектов sbt. Для сред Spark, таких как `spark-submit` (или `spark-shell`), следует использовать параметр командной строки `--packages` следующим образом:

```bash
spark-submit --master local --packages org.mongodb.spark:mongo-spark-connector_2.12:3.0.0 --class org.apache.spark.deploy.dotnet.DotnetRunner microsoft-spark-<version>.jar yourApp.exe
```

> [!NOTE]
> Убедитесь, что включили версию пакета, соответствующую используемой версии Spark.

В результате отображается кадр данных (`df`), как показано ниже:

```text
+--------------------+----+-------+
|                 _id| age|   name|
+--------------------+----+-------+
|[5f7c28438029a134...|null|Michael|
|[5f7c287f8029a134...|  30|   Andy|
|[5f7c289a8029a134...|  19| Justin|
+--------------------+----+-------+
```
