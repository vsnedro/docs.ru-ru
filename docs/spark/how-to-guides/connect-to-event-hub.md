---
title: Подключение .NET для Apache Spark к Центрам событий Azure
description: Узнайте, как подключиться к Центру событий Azure из локального экземпляра .NET для Apache Spark.
ms.date: 10/09/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: 4de4836ba2b63429e29ae819afac09c7a3998480
ms.sourcegitcommit: b59237ca4ec763969a0dd775a3f8f39f8c59fe24
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/12/2020
ms.locfileid: "91954975"
---
# <a name="connect-net-for-apache-spark-to-azure-event-hubs"></a>Подключение .NET для Apache Spark к Центрам событий Azure

В этой статье вы узнаете, как подключить приложение [.NET для Apache Spark](https://github.com/dotnet/spark) к Центрам событий Azure для чтения и записи потоков Apache Kafka.

## <a name="prerequisites"></a>Предварительные требования

Подготовьте пространство имен Центров событий с концентратором событий. Пошаговое руководство см. в разделе [Краткое руководство. Создание концентратора событий с помощью портала Microsoft Azure](/azure/event-hubs/event-hubs-create). При создании пространства имен концентратора событий выберите ценовую категорию "Стандартный".

## <a name="what-is-azure-event-hubs"></a>Что такое Центры событий Azure

[Центры событий Azure](/azure/event-hubs/event-hubs-about) представляют собой платформу потоковой передачи больших данных и службу приема событий. Это полностью управляемая платформа как услуга (PaaS), которая может легко интегрироваться с [Apache Kafka](https://kafka.apache.org/), чтобы обеспечить работу Kafka в PaaS без необходимости управления, настройки и запуска собственных кластеров.

## <a name="connect-your-application-to-azure-event-hubs"></a>Подключение приложения к Центрам событий Azure

1. Получите строку подключения Центров событий и полное доменное имя (FQDN) для последующего использования. Инструкции см. в статье [Get an Event Hubs connection string](/azure/event-hubs/event-hubs-get-connection-string) (Получение строки подключения для Центров событий).
2. Задайте следующие параметры конфигурации со сведениями из пространства имен в коде, чтобы начать чтение из Центров событий для Kafka.
    1. Измените параметры **BOOTSTRAP_SERVERS** и **EH_SASL** в приложении следующим образом:

    ```csharp
    string BOOTSTRAP_SERVERS = "hostname:9093"; // 9093 is the port used to communicate with Event Hubs, see [troubleshooting guide](https://docs.microsoft.com/azure/event-hubs/troubleshooting-guide)
    string EH_SASL = "org.apache.kafka.common.security.plain.PlainLoginModule required username=\"$ConnectionString\" password=\"<CONNECTION_STRING>\";"; // Connection string obtained from Step 1
    ```

## <a name="read-from-azure-event-hub-stream"></a>Чтение из потока Центра событий Azure

Теперь можно начать потоковую передачу с помощью Центров событий, как при использовании Kafka. Пример кода показан ниже:

```csharp
SparkSession spark = SparkSession
    .Builder()
    .AppName("Connect Event Hub")
    .GetOrCreate();

DataFrame df = spark
    .ReadStream()
    .Format("kafka")
    .Option("kafka.bootstrap.servers", BOOTSTRAP_SERVERS)
    .Option("subscribe", "spark-test")
    .Option("kafka.sasl.mechanism", "PLAIN")
    .Option("kafka.security.protocol", "SASL_SSL")
    .Option("kafka.sasl.jaas.config", EH_SASL)
    .Option("kafka.request.timeout.ms", "60000")
    .Option("kafka.session.timeout.ms", "60000")
    .Option("failOnDataLoss", "false")
    .Load();

DataFrame dfWrite = df
    .WriteStream()
    .OutputMode("append")
    .Format("console")
    .Start();
```

## <a name="write-to-azure-event-hub-stream"></a>Запись в поток Центра событий Azure

Таким же образом можно выполнять запись в Центры событий, как показано ниже:

```csharp
// df is the DataFrame to write

df.WriteStream()
    .Format("kafka")
    .Option("topic", topics)
    .Option("kafka.bootstrap.servers", BOOTSTRAP_SERVERS)
    .Option("kafka.sasl.mechanism", "PLAIN")
    .Option("kafka.security.protocol", "SASL_SSL")
    .Option("kafka.sasl.jaas.config", EH_SASL)
    .Option("checkpointLocation", "./checkpoint")
    .Start();
```

## <a name="run-your-application"></a>Запуск приложения

Чтобы запустить приложение .NET для Apache Spark, определите модуль `spark-sql-kafka-0-10` как часть определения сборки в проекте Spark, используя `libraryDependency` в `build.sbt` для проектов sbt. Для сред Spark, таких как `spark-submit` (или `spark-shell`), используйте параметр командной строки `--packages` следующим образом:

```bash
spark-shell --packages org.apache.spark:spark-sql-kafka-0-10_2.12:2.4.5
```

> [!NOTE]
> Убедитесь, что включили версию пакета, соответствующую используемой версии Spark.
