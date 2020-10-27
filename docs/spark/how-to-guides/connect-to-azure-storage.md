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
# <a name="connect-to-azure-data-lake-storage-gen-2-or-wasb-account"></a><span data-ttu-id="df2ee-103">Подключение к учетной записи Azure Data Lake Storage Gen 2 или WASB</span><span class="sxs-lookup"><span data-stu-id="df2ee-103">Connect to Azure Data Lake Storage Gen 2 or WASB account</span></span>

<span data-ttu-id="df2ee-104">Из этой статьи вы узнаете, как подключиться к учетной записи Azure Data Lake Storage (ADLS) Gen 2 или Windows Azure Storage Blob (WASB) через экземпляр [.NET для Apache Spark](https://github.com/dotnet/spark), запущенный локально на компьютере Windows.</span><span class="sxs-lookup"><span data-stu-id="df2ee-104">In this article, you learn how to connect to an Azure Data Lake Storage (ADLS) Gen 2 or Windows Azure Storage Blob (WASB) account through an instance of [.NET for Apache Spark](https://github.com/dotnet/spark) running locally on your Windows machine.</span></span>

## <a name="set-up-the-environment"></a><span data-ttu-id="df2ee-105">Настройка среды</span><span class="sxs-lookup"><span data-stu-id="df2ee-105">Set up the environment</span></span>

1. <span data-ttu-id="df2ee-106">Скачайте дистрибутив Apache Spark, созданный без Hadoop, с [официального веб-сайта](https://archive.apache.org/dist/spark/) (выберите версию, [поддерживаемую .NET для Apache Spark](https://github.com/dotnet/spark#supported-apache-spark)) и извлеките его в каталог.</span><span class="sxs-lookup"><span data-stu-id="df2ee-106">Download the Apache Spark distribution built without Hadoop from [official website](https://archive.apache.org/dist/spark/) (choose a version [supported by .NET for Apache Spark](https://github.com/dotnet/spark#supported-apache-spark)), and extract it to a directory.</span></span> <span data-ttu-id="df2ee-107">Задайте для этого каталога переменную среды `SPARK_HOME`.</span><span class="sxs-lookup"><span data-stu-id="df2ee-107">Set the environment variable `SPARK_HOME` to this directory.</span></span>
2. <span data-ttu-id="df2ee-108">Скачайте двоичный файл Apache Hadoop [отсюда](http://hadoop.apache.org/releases.html) и извлеките его в папку, а затем задайте для этой папки переменную среды `HADOOP_HOME`.</span><span class="sxs-lookup"><span data-stu-id="df2ee-108">Download the Apache Hadoop binary from [here](http://hadoop.apache.org/releases.html) and extract to a folder, and set your `HADOOP_HOME` environment variable to this folder.</span></span>
3. <span data-ttu-id="df2ee-109">Скачайте файлы `winutils.exe` и `hadoop.dll` из [этого расположения](https://github.com/cdarlint/winutils) (в зависимости от версии Hadoop, установленной на предыдущем шаге) и вставьте их в папку bin своего Hadoop.</span><span class="sxs-lookup"><span data-stu-id="df2ee-109">Download the `winutils.exe` and `hadoop.dll` files from [this location](https://github.com/cdarlint/winutils) (depending on the version of Hadoop installed in the previous step) and put them in the bin folder of your Hadoop.</span></span> <span data-ttu-id="df2ee-110">Эти двоичные файлы необходимы для правильной настройки в Windows (подробное описание приведено в [этой вики-статье Apache](https://cwiki.apache.org/confluence/display/HADOOP2/WindowsProblems)).</span><span class="sxs-lookup"><span data-stu-id="df2ee-110">These binaries are needed on Windows in order to get everything setup correctly (this is explained in detail in the [Apache wiki here](https://cwiki.apache.org/confluence/display/HADOOP2/WindowsProblems)).</span></span>
4. <span data-ttu-id="df2ee-111">Настройте установку Hadoop, внеся следующие изменения в файл `%HADOOP_HOME%\etc\hadoop\hadoop-env.cmd`:</span><span class="sxs-lookup"><span data-stu-id="df2ee-111">Configure your Hadoop installation by making the following changes to your `%HADOOP_HOME%\etc\hadoop\hadoop-env.cmd` file:</span></span>
    1. <span data-ttu-id="df2ee-112">Задайте свойство `JAVA_HOME`, используя путь DOS (так как Hadoop не использует пробелы в `JAVA_HOME`).</span><span class="sxs-lookup"><span data-stu-id="df2ee-112">Set the `JAVA_HOME` property using the DOS path (since Hadoop doesn't like spaces in `JAVA_HOME`).</span></span> <span data-ttu-id="df2ee-113">Путь должен выглядеть следующим образом: `C:\Progra~1\Java\jdk1.8.0_241` (указывает на любую версию Java, установленную на локальном компьютере).</span><span class="sxs-lookup"><span data-stu-id="df2ee-113">This should look something like this: `C:\Progra~1\Java\jdk1.8.0_241` (Pointing to whatever version of Java you have installed on your local machine).</span></span>
    2. <span data-ttu-id="df2ee-114">Добавьте `%HADOOP_HOME%\share\hadoop\tools\lib\*` в `HADOOP_CLASSPATH`.</span><span class="sxs-lookup"><span data-stu-id="df2ee-114">Append `%HADOOP_HOME%\share\hadoop\tools\lib\*` to `HADOOP_CLASSPATH`.</span></span>
    <span data-ttu-id="df2ee-115">Окончательный файл `hadoop-env.cmd` должен выглядеть примерно так:</span><span class="sxs-lookup"><span data-stu-id="df2ee-115">Your final `hadoop-env.cmd` file should look something like this:</span></span>

    ![Окончательный файл hadoop-env.cmd](./media/connect-external-sources/hadoop-env.png)

## <a name="configure-your-storage-account-in-hadoop"></a><span data-ttu-id="df2ee-117">Настройка учетной записи хранения в Hadoop</span><span class="sxs-lookup"><span data-stu-id="df2ee-117">Configure your storage account in Hadoop</span></span>

1. <span data-ttu-id="df2ee-118">Откройте учетную запись хранения ADLS Gen 2 или WASB, к которой вы хотите подключиться, с помощью [портала Azure](https://portal.azure.com) и откройте панель **Ключи доступа** в колонке **Параметры** и скопируйте значение **Ключ** из раздела key1.</span><span class="sxs-lookup"><span data-stu-id="df2ee-118">Open the ADLS Gen 2 or WASB storage account you want to connect to through the [Azure portal](https://portal.azure.com) and open the **Access keys** panel under the **Settings** blade and copy the value of **Key** from under key1.</span></span>
2. <span data-ttu-id="df2ee-119">Теперь, чтобы настроить Hadoop для доступа к учетной записи ADLS 2-го поколения, необходимо изменить `core-site.xml` (находится в файле `%HADOOP_HOME%\etc\hadoop\`), который содержит конфигурацию на уровне кластера.</span><span class="sxs-lookup"><span data-stu-id="df2ee-119">Now in order to configure Hadoop to access your ADLS Gen2 account you would have to edit your `core-site.xml` (located in `%HADOOP_HOME%\etc\hadoop\` ) file which contains cluster-wide configuration.</span></span> <span data-ttu-id="df2ee-120">Добавьте следующие свойства в теги `<configuration>` в этом файле:</span><span class="sxs-lookup"><span data-stu-id="df2ee-120">Add the following properties inside the `<configuration>` tags in this file:</span></span>

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

    <span data-ttu-id="df2ee-121">Если вы пытаетесь подключиться к учетной записи WASB, замените `dfs` `blob` в именах свойств.</span><span class="sxs-lookup"><span data-stu-id="df2ee-121">If you are trying to connect to a WASB account, replace `dfs` with `blob` in the property names.</span></span> <span data-ttu-id="df2ee-122">Например, `fs.azure.account.auth.type.YOUR_ACCOUNT_NAME.blob.core.windows.net`.</span><span class="sxs-lookup"><span data-stu-id="df2ee-122">For example, `fs.azure.account.auth.type.YOUR_ACCOUNT_NAME.blob.core.windows.net`.</span></span>
3. <span data-ttu-id="df2ee-123">Вы можете проверить подключение к учетной записи хранения из Hadoop, выполнив следующую команду из каталога `%HADOOP_HOME%`:</span><span class="sxs-lookup"><span data-stu-id="df2ee-123">You can test the connectivity to your Storage Account from Hadoop by running the following command from your `%HADOOP_HOME%` directory:</span></span>

    ```bash
    bin\hdfs dfs -ls <URI to your account>
    ```

<span data-ttu-id="df2ee-124">При этом должен отобразиться список всех файлов и папок в пути, указанном в URI.</span><span class="sxs-lookup"><span data-stu-id="df2ee-124">This should display a list of all files/folders in the path provided by your URI.</span></span>

> [!NOTE]
> <span data-ttu-id="df2ee-125">Формат URI для учетной записи хранения должен быть следующим:</span><span class="sxs-lookup"><span data-stu-id="df2ee-125">The format to derive the URI to your Storage account is as follows:</span></span>
>
> ```
> For ADLS: abfs[s]://<file_system>@<account_name>.dfs.core.windows.net/<path>/<file_name>
> For WASB: wasb[s]://<file_system>@<account_name>.blob.core.windows.net/<path>/<file_name>
> ```

## <a name="connect-to-your-storage-account"></a><span data-ttu-id="df2ee-126">Подключение к учетной записи хранения</span><span class="sxs-lookup"><span data-stu-id="df2ee-126">Connect to your storage account</span></span>

1. <span data-ttu-id="df2ee-127">Если приведенная выше команда сработала, вы можете перейти к этой учетной записи хранения через Spark.</span><span class="sxs-lookup"><span data-stu-id="df2ee-127">If the above command worked, you can now move on to accessing this storage account through Spark.</span></span> <span data-ttu-id="df2ee-128">Сначала выполните команду `hadoop classpath` из командной строки в `%HADOOP_HOME%` и скопируйте выходные данные.</span><span class="sxs-lookup"><span data-stu-id="df2ee-128">First run the command `hadoop classpath` from the commandline inside `%HADOOP_HOME%` and copy the output.</span></span>
2. <span data-ttu-id="df2ee-129">Установите выходные данные команды, выполняемой на шаге 1, в значение переменной среды `SPARK_DIST_CLASSPATH`.</span><span class="sxs-lookup"><span data-stu-id="df2ee-129">Set the output of the command run in Step 1 to the value of environment variable `SPARK_DIST_CLASSPATH`.</span></span>
3. <span data-ttu-id="df2ee-130">Теперь вы можете получить доступ к учетной записи хранения ADLS или WASB через Spark .NET с помощью URI abfs, как показано в простом примере ниже.</span><span class="sxs-lookup"><span data-stu-id="df2ee-130">Now you should be able to access your ADLS or WASB storage account through Spark .NET using the abfs URI as shown in the simple example below.</span></span> <span data-ttu-id="df2ee-131">(Здесь используется стандартный пример файла [`people.json`](https://github.com/apache/spark/blob/master/examples/src/main/resources/people.json), поставляемого в комплекте каждой установки Apache Spark.)</span><span class="sxs-lookup"><span data-stu-id="df2ee-131">(For this example we use the standard [`people.json`](https://github.com/apache/spark/blob/master/examples/src/main/resources/people.json) example file provided with every Apache Spark installation.):</span></span>

    ```csharp
    SparkSession spark = SparkSession
       .Builder()
       .AppName("Connect to Azure Storage locally")
       .GetOrCreate();
    DataFrame df = spark.Read().Json("wasbs://file_system@account_name.blob.core.windows.net/path/people.json");
    //DataFrame df = spark.Read().Json("abfss://file_system@account_name.dfs.core.windows.net/path/file.json");
    df.Show();
    ```

    <span data-ttu-id="df2ee-132">В результате отображается кадр данных (`df`), как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="df2ee-132">The result as displayed is the DataFrame (`df`) as shown below:</span></span>

    ```text
    +----+-------+
    | age|   name|
    +----+-------+
    |null|Michael|
    |  30|   Andy|
    |  19| Justin|
    +----+-------+
    ```
