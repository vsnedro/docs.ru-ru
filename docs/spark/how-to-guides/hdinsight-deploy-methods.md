---
title: Отправка задания .NET для Apache Spark в Azure HDInsight
description: Узнайте, как отправить задание .NET для Apache Spark в Azure HDInsight с помощью spark-submit и Apache Livy.
ms.date: 10/09/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: 74be4ecf33a9a881633da0630fa1c1a4bf0b19c6
ms.sourcegitcommit: 34968a61e9bac0f6be23ed6ffb837f52d2390c85
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "94688167"
---
# <a name="submit-a-net-for-apache-spark-job-to-azure-hdinsight"></a>Отправка задания .NET для Apache Spark в Azure HDInsight

Существует два способа развертывания задания .NET для Apache Spark в HDInsight: команда `spark-submit` и Apache Livy.

## <a name="deploy-using-spark-submit"></a>Развертывание с помощью spark-submit

Для отправки заданий .NET для Apache Spark в Azure HDInsight можно использовать команду [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html).

1. Перейдите к кластеру HDInsight Spark на портале Azure и выберите **SSH и вход в кластер**.

2. Скопируйте данные для входа по протоколу SSH и вставьте имя для входа в терминал. Войдите в кластер, используя пароль, заданный во время создания кластера. Вы должны увидеть сообщение с приветствием в Ubuntu и Spark.

3. Используйте команду **spark-submit**, чтобы запустить приложение в кластере HDInsight. Не забудьте заменить **mycontainer** и **mystorageaccount** в примере скрипта, указав фактические имена контейнера больших двоичных объектов и учетной записи хранения. Кроме того, не забудьте заменить JAR-файл microsoft-spark на используемую версию Spark и .NET для Apache Spark.

   ```bash
   $SPARK_HOME/bin/spark-submit \
   --master yarn \
   --class org.apache.spark.deploy.dotnet.DotnetRunner \
   wasbs://mycontainer@mystorageaccount.blob.core.windows.net/microsoft-spark-<spark_majorversion-spark_minorversion>_<scala_majorversion.scala_minorversion>-<spark_dotnet_version>.jar \
   wasbs://mycontainer@mystorageaccount.blob.core.windows.net/publish.zip mySparkApp
   ```

## <a name="deploy-using-apache-livy"></a>Развертывание с помощью Apache Livy

Для отправки заданий .NET для Apache Spark в кластер Azure HDInsight Spark можно использовать [Apache Livy](https://livy.incubator.apache.org/), интерфейс REST API для Apache Spark. Дополнительные сведения см. в статье [Работа с удаленными заданиями с помощью Apache Livy](/azure/hdinsight/spark/apache-spark-livy-rest-interface).

В Linux можно выполнить следующую команду с помощью `curl`:

```bash
curl -k -v -X POST "https://<your spark cluster>.azurehdinsight.net/livy/batches" \
-u "<hdinsight username>:<hdinsight password>" \
-H "Content-Type: application/json" \
-H "X-Requested-By: <hdinsight username>" \
-d @- << EOF
{
    "file":"abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/microsoft-spark-<spark_majorversion-spark_minorversion>_<scala_majorversion.scala_minorversion>-<spark_dotnet_version>.jar",
    "className":"org.apache.spark.deploy.dotnet.DotnetRunner",
    "files":["abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/<udf assembly>", "abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/<file>"],
    "args":["abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/<your app>.zip","<your app>","<app arg 1>","<app arg 2>,"...","<app arg n>"]
}
EOF
```

## <a name="next-steps"></a>Следующие шаги

* [Начало работы с .NET для Apache Spark](../tutorials/get-started.md)
* [Развертывание приложения .NET для Apache Spark в Azure HDInsight](../tutorials/hdinsight-deployment.md)
* [Документация по HDInsight](/azure/hdinsight/)
