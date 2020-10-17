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
# <a name="connect-net-for-apache-spark-to-azure-event-hubs"></a><span data-ttu-id="fd8be-103">Подключение .NET для Apache Spark к Центрам событий Azure</span><span class="sxs-lookup"><span data-stu-id="fd8be-103">Connect .NET for Apache Spark to Azure Event Hubs</span></span>

<span data-ttu-id="fd8be-104">В этой статье вы узнаете, как подключить приложение [.NET для Apache Spark](https://github.com/dotnet/spark) к Центрам событий Azure для чтения и записи потоков Apache Kafka.</span><span class="sxs-lookup"><span data-stu-id="fd8be-104">In this article, you will learn how to connect your [.NET for Apache Spark](https://github.com/dotnet/spark) application with Azure Event Hubs to read and write Apache Kafka streams.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="fd8be-105">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="fd8be-105">Prerequisites</span></span>

<span data-ttu-id="fd8be-106">Подготовьте пространство имен Центров событий с концентратором событий.</span><span class="sxs-lookup"><span data-stu-id="fd8be-106">Have an Event Hubs Namespace ready with an event hub.</span></span> <span data-ttu-id="fd8be-107">Пошаговое руководство см. в разделе [Краткое руководство. Создание концентратора событий с помощью портала Microsoft Azure](/azure/event-hubs/event-hubs-create).</span><span class="sxs-lookup"><span data-stu-id="fd8be-107">For a step-by-step guide, refer to [Quickstart: Create an event hub using Azure portal](/azure/event-hubs/event-hubs-create).</span></span> <span data-ttu-id="fd8be-108">При создании пространства имен концентратора событий выберите ценовую категорию "Стандартный".</span><span class="sxs-lookup"><span data-stu-id="fd8be-108">Make sure to select the Standard Pricing tier while creating the Event Hub Namespace.</span></span>

## <a name="what-is-azure-event-hubs"></a><span data-ttu-id="fd8be-109">Что такое Центры событий Azure</span><span class="sxs-lookup"><span data-stu-id="fd8be-109">What is Azure Event Hubs</span></span>

<span data-ttu-id="fd8be-110">[Центры событий Azure](/azure/event-hubs/event-hubs-about) представляют собой платформу потоковой передачи больших данных и службу приема событий.</span><span class="sxs-lookup"><span data-stu-id="fd8be-110">[Azure Event Hubs](/azure/event-hubs/event-hubs-about) is a big-data streaming platform and event-ingestion service.</span></span> <span data-ttu-id="fd8be-111">Это полностью управляемая платформа как услуга (PaaS), которая может легко интегрироваться с [Apache Kafka](https://kafka.apache.org/), чтобы обеспечить работу Kafka в PaaS без необходимости управления, настройки и запуска собственных кластеров.</span><span class="sxs-lookup"><span data-stu-id="fd8be-111">It is a fully managed Platform-as-a-Service (PaaS) that can easily integrate with [Apache Kafka](https://kafka.apache.org/) to give you the PaaS Kafka experience without having to manage, configure, or run your own clusters.</span></span>

## <a name="connect-your-application-to-azure-event-hubs"></a><span data-ttu-id="fd8be-112">Подключение приложения к Центрам событий Azure</span><span class="sxs-lookup"><span data-stu-id="fd8be-112">Connect your application to Azure Event Hubs</span></span>

1. <span data-ttu-id="fd8be-113">Получите строку подключения Центров событий и полное доменное имя (FQDN) для последующего использования.</span><span class="sxs-lookup"><span data-stu-id="fd8be-113">Get the Event Hubs connection string and fully qualified domain name (FQDN) for later use.</span></span> <span data-ttu-id="fd8be-114">Инструкции см. в статье [Get an Event Hubs connection string](/azure/event-hubs/event-hubs-get-connection-string) (Получение строки подключения для Центров событий).</span><span class="sxs-lookup"><span data-stu-id="fd8be-114">For instructions, see [Get an Event Hubs connection string](/azure/event-hubs/event-hubs-get-connection-string).</span></span>
2. <span data-ttu-id="fd8be-115">Задайте следующие параметры конфигурации со сведениями из пространства имен в коде, чтобы начать чтение из Центров событий для Kafka.</span><span class="sxs-lookup"><span data-stu-id="fd8be-115">Set the following configurations with details from your namespace in your code to start reading from Event Hubs for Kafka:</span></span>
    1. <span data-ttu-id="fd8be-116">Измените параметры **BOOTSTRAP_SERVERS** и **EH_SASL** в приложении следующим образом:</span><span class="sxs-lookup"><span data-stu-id="fd8be-116">Update **BOOTSTRAP_SERVERS** and **EH_SASL** in your application like so:</span></span>

    ```csharp
    string BOOTSTRAP_SERVERS = "hostname:9093"; // 9093 is the port used to communicate with Event Hubs, see [troubleshooting guide](https://docs.microsoft.com/azure/event-hubs/troubleshooting-guide)
    string EH_SASL = "org.apache.kafka.common.security.plain.PlainLoginModule required username=\"$ConnectionString\" password=\"<CONNECTION_STRING>\";"; // Connection string obtained from Step 1
    ```

## <a name="read-from-azure-event-hub-stream"></a><span data-ttu-id="fd8be-117">Чтение из потока Центра событий Azure</span><span class="sxs-lookup"><span data-stu-id="fd8be-117">Read from Azure Event Hub stream</span></span>

<span data-ttu-id="fd8be-118">Теперь можно начать потоковую передачу с помощью Центров событий, как при использовании Kafka.</span><span class="sxs-lookup"><span data-stu-id="fd8be-118">You can now start streaming with Event Hubs as you would with Kafka.</span></span> <span data-ttu-id="fd8be-119">Пример кода показан ниже:</span><span class="sxs-lookup"><span data-stu-id="fd8be-119">Sample code as shown below:</span></span>

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

## <a name="write-to-azure-event-hub-stream"></a><span data-ttu-id="fd8be-120">Запись в поток Центра событий Azure</span><span class="sxs-lookup"><span data-stu-id="fd8be-120">Write to Azure Event Hub stream</span></span>

<span data-ttu-id="fd8be-121">Таким же образом можно выполнять запись в Центры событий, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="fd8be-121">You can also write to Event Hubs in the same way, as shown below:</span></span>

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

## <a name="run-your-application"></a><span data-ttu-id="fd8be-122">Запуск приложения</span><span class="sxs-lookup"><span data-stu-id="fd8be-122">Run your application</span></span>

<span data-ttu-id="fd8be-123">Чтобы запустить приложение .NET для Apache Spark, определите модуль `spark-sql-kafka-0-10` как часть определения сборки в проекте Spark, используя `libraryDependency` в `build.sbt` для проектов sbt.</span><span class="sxs-lookup"><span data-stu-id="fd8be-123">In order to run your .NET for Apache Spark application, define the `spark-sql-kafka-0-10` module as part of the build definition in your Spark project, using `libraryDependency` in `build.sbt` for sbt projects.</span></span> <span data-ttu-id="fd8be-124">Для сред Spark, таких как `spark-submit` (или `spark-shell`), используйте параметр командной строки `--packages` следующим образом:</span><span class="sxs-lookup"><span data-stu-id="fd8be-124">For Spark environments such as `spark-submit` (or `spark-shell`), use the `--packages` command-line option like so:</span></span>

```bash
spark-shell --packages org.apache.spark:spark-sql-kafka-0-10_2.12:2.4.5
```

> [!NOTE]
> <span data-ttu-id="fd8be-125">Убедитесь, что включили версию пакета, соответствующую используемой версии Spark.</span><span class="sxs-lookup"><span data-stu-id="fd8be-125">Make sure to include the package version in accordance with the version of Spark being run.</span></span>
