---
title: Подключение к удаленному хранилищу с локального компьютера
description: Подключение к учетным записям хранения Azure с помощью .NET для Apache Spark с локального компьютера.
ms.author: nidutta
author: Niharikadutta
ms.date: 10/09/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: dc0c3b44279756596f3d456616821e690710ae04
ms.sourcegitcommit: 67ebdb695fd017d79d9f1f7f35d145042d5a37f7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/20/2020
ms.locfileid: "92224020"
---
# <a name="connect-to-azure-data-lake-storage-gen-2-or-wasb-account"></a>Подключение к учетной записи Azure Data Lake Storage Gen 2 или WASB

Из этой статьи вы узнаете, как подключиться к учетной записи Azure Data Lake Storage (ADLS) Gen 2 или Windows Azure Storage Blob (WASB) через экземпляр [.NET для Apache Spark](https://github.com/dotnet/spark), запущенный локально на компьютере Windows.

## <a name="set-up-the-environment"></a>Настройка среды

1. Скачайте дистрибутив Apache Spark, созданный без Hadoop, с [официального веб-сайта](https://archive.apache.org/dist/spark/) (выберите версию, [поддерживаемую .NET для Apache Spark](https://github.com/dotnet/spark#supported-apache-spark)) и извлеките его в каталог. Задайте для этого каталога переменную среды `SPARK_HOME`.
2. Скачайте двоичный файл Apache Hadoop [отсюда](http://hadoop.apache.org/releases.html) и извлеките его в папку, а затем задайте для этой папки переменную среды `HADOOP_HOME`.
3. Скачайте файлы `winutils.exe` и `hadoop.dll` из [этого расположения](https://github.com/cdarlint/winutils) (в зависимости от версии Hadoop, установленной на предыдущем шаге) и вставьте их в папку bin своего Hadoop. Эти двоичные файлы необходимы для правильной настройки в Windows (подробное описание приведено в [этой вики-статье Apache](https://cwiki.apache.org/confluence/display/HADOOP2/WindowsProblems)).
4. Настройте установку Hadoop, внеся следующие изменения в файл `%HADOOP_HOME%\etc\hadoop\hadoop-env.cmd`:
    1. Задайте свойство `JAVA_HOME`, используя путь DOS (так как Hadoop не использует пробелы в `JAVA_HOME`). Путь должен выглядеть следующим образом: `C:\Progra~1\Java\jdk1.8.0_241` (указывает на любую версию Java, установленную на локальном компьютере).
    2. Добавьте `%HADOOP_HOME%\share\hadoop\tools\lib\*` в `HADOOP_CLASSPATH`.
    Окончательный файл `hadoop-env.cmd` должен выглядеть примерно так:

    ![Окончательный файл hadoop-env.cmd](./media/connect-external-sources/hadoop-env.png)

## <a name="configure-your-storage-account-in-hadoop"></a>Настройка учетной записи хранения в Hadoop

1. Откройте учетную запись хранения ADLS Gen 2 или WASB, к которой вы хотите подключиться, с помощью [портала Azure](https://portal.azure.com) и откройте панель **Ключи доступа** в колонке **Параметры** и скопируйте значение **Ключ** из раздела key1.
2. Теперь, чтобы настроить Hadoop для доступа к учетной записи ADLS 2-го поколения, необходимо изменить `core-site.xml` (находится в файле `%HADOOP_HOME%\etc\hadoop\`), который содержит конфигурацию на уровне кластера. Добавьте следующие свойства в теги `<configuration>` в этом файле:

    ```xml
    <configuration>
      <property>
        <name>fs.azure.account.auth.type.YOUR_ACCOUNT_NAME.dfs.core.windows.net</name>
        <value>SharedKey</value>
        <description></description>
      </property>
      <property>
        <name>fs.azure.account.key.YOUR_ACCOUNT_NAME.dfs.core.windows.net</name>
        <value>YOUR ACCESS KEY (copied from Step 1)</value>
        <description>The secret password. Never share these.</description>
      </property>
    </configuration>
    ```

    Если вы пытаетесь подключиться к учетной записи WASB, замените `dfs` `blob` в именах свойств. Например, `fs.azure.account.auth.type.YOUR_ACCOUNT_NAME.blob.core.windows.net`.
3. Вы можете проверить подключение к учетной записи хранения из Hadoop, выполнив следующую команду из каталога `%HADOOP_HOME%`:

    ```bash
    bin\hdfs dfs -ls <URI to your account>
    ```

При этом должен отобразиться список всех файлов и папок в пути, указанном в URI.

> [!NOTE]
> Формат URI для учетной записи хранения должен быть следующим:
>
> ```
> For ADLS: abfs[s]://<file_system>@<account_name>.dfs.core.windows.net/<path>/<file_name>
> For WASB: wasb[s]://<file_system>@<account_name>.blob.core.windows.net/<path>/<file_name>
> ```

## <a name="connect-to-your-storage-account"></a>Подключение к учетной записи хранения

1. Если приведенная выше команда сработала, вы можете перейти к этой учетной записи хранения через Spark. Сначала выполните команду `hadoop classpath` из командной строки в `%HADOOP_HOME%` и скопируйте выходные данные.
2. Установите выходные данные команды, выполняемой на шаге 1, в значение переменной среды `SPARK_DIST_CLASSPATH`.
3. Теперь вы можете получить доступ к учетной записи хранения ADLS или WASB через Spark .NET с помощью URI abfs, как показано в простом примере ниже. (Здесь используется стандартный пример файла [`people.json`](https://github.com/apache/spark/blob/master/examples/src/main/resources/people.json), поставляемого в комплекте каждой установки Apache Spark.)

    ```csharp
    SparkSession spark = SparkSession
       .Builder()
       .AppName("Connect to Azure Storage locally")
       .GetOrCreate();
    DataFrame df = spark.Read().Json("wasbs://file_system@account_name.blob.core.windows.net/path/people.json");
    //DataFrame df = spark.Read().Json("abfss://file_system@account_name.dfs.core.windows.net/path/file.json");
    df.Show();
    ```

    В результате отображается кадр данных (`df`), как показано ниже:

    ```text
    +----+-------+
    | age|   name|
    +----+-------+
    |null|Michael|
    |  30|   Andy|
    |  19| Justin|
    +----+-------+
    ```
