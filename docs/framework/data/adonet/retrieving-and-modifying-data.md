---
title: Извлечение и изменение данных
description: В .NET Framework поставщики данных в ADO.NET служат в качестве моста между приложением и источником данных для чтения и обновления данных.
ms.date: 03/30/2017
ms.assetid: 722e7f87-3691-46c6-87e8-7d159722d675
ms.openlocfilehash: f916324dc829526a5e6b0078021b09786755f666
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286615"
---
# <a name="retrieving-and-modifying-data-in-adonet"></a><span data-ttu-id="1370f-103">Извлечение и изменение данных в ADO.NET</span><span class="sxs-lookup"><span data-stu-id="1370f-103">Retrieving and Modifying Data in ADO.NET</span></span>
<span data-ttu-id="1370f-104">Основной функцией любого приложения базы данных является соединение с источником данных и извлечение данных, которые он содержит.</span><span class="sxs-lookup"><span data-stu-id="1370f-104">A primary function of any database application is connecting to a data source and retrieving the data that it contains.</span></span> <span data-ttu-id="1370f-105">.NET Framework поставщики данных ADO.NET служат мостом между приложением и источником данных, что позволяет выполнять команды, а также получать данные с помощью объекта **DataReader** или **DataAdapter**.</span><span class="sxs-lookup"><span data-stu-id="1370f-105">The .NET Framework data providers of ADO.NET serve as a bridge between an application and a data source, allowing you to execute commands as well as to retrieve data by using a **DataReader** or a **DataAdapter**.</span></span> <span data-ttu-id="1370f-106">Ключевой функцией любого приложения базы данных является возможность обновления данных, хранимых в базе данных.</span><span class="sxs-lookup"><span data-stu-id="1370f-106">A key function of any database application is the ability to update the data that is stored in the database.</span></span> <span data-ttu-id="1370f-107">В ADO.NET обновление данных включает использование объектов **DataAdapter** и <xref:System.Data.DataSet> и, и **Command** , Кроме того, может содержать использование транзакций.</span><span class="sxs-lookup"><span data-stu-id="1370f-107">In ADO.NET, updating data involves using the **DataAdapter** and <xref:System.Data.DataSet>, and **Command** objects; and it may also involve using transactions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1370f-108">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="1370f-108">In This Section</span></span>  
 [<span data-ttu-id="1370f-109">Подключение к источнику данных</span><span class="sxs-lookup"><span data-stu-id="1370f-109">Connecting to a Data Source</span></span>](connecting-to-a-data-source.md)  
 <span data-ttu-id="1370f-110">Описывается установка подключения к источнику данных и работа с событиями подключения.</span><span class="sxs-lookup"><span data-stu-id="1370f-110">Describes how to establish a connection to a data source and how to work with connection events.</span></span>  
  
 [<span data-ttu-id="1370f-111">Строки подключения</span><span class="sxs-lookup"><span data-stu-id="1370f-111">Connection Strings</span></span>](connection-strings.md)  
 <span data-ttu-id="1370f-112">Содержит разделы, в которых описываются различные аспекты использования строк подключения, в том числе ключевых слов строки подключения, сведения о безопасности, их хранение и извлечение.</span><span class="sxs-lookup"><span data-stu-id="1370f-112">Contains topics describing various aspects of using connection strings, including connection string keywords, security info, and storing and retrieving them.</span></span>  
  
 [<span data-ttu-id="1370f-113">Объединение подключений в пул</span><span class="sxs-lookup"><span data-stu-id="1370f-113">Connection Pooling</span></span>](connection-pooling.md)  
 <span data-ttu-id="1370f-114">Описывает пул соединений для поставщиков данных платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1370f-114">Describes connection pooling for the .NET Framework data providers.</span></span>  
  
 [<span data-ttu-id="1370f-115">Команды и параметры</span><span class="sxs-lookup"><span data-stu-id="1370f-115">Commands and Parameters</span></span>](commands-and-parameters.md)  
 <span data-ttu-id="1370f-116">Содержит разделы, в которых описывается создание команд и построителей команд, настройка параметров и выполнение команд для извлечения и изменения данных.</span><span class="sxs-lookup"><span data-stu-id="1370f-116">Contains topics describing how to create commands and command builders, configure parameters, and how to execute commands to retrieve and modify data.</span></span>  
  
 [<span data-ttu-id="1370f-117">Объекты DataAdapter и DataReader</span><span class="sxs-lookup"><span data-stu-id="1370f-117">DataAdapters and DataReaders</span></span>](dataadapters-and-datareaders.md)  
 <span data-ttu-id="1370f-118">Содержит разделы, в которых описываются объекты DataReader, DataAdapter, параметры, обработка событий объекта и выполнение пакетных операций.</span><span class="sxs-lookup"><span data-stu-id="1370f-118">Contains topics describing DataReaders, DataAdapters, parameters, handling DataAdapter events and performing batch operations.</span></span>  
  
 [<span data-ttu-id="1370f-119">Транзакции и параллельность</span><span class="sxs-lookup"><span data-stu-id="1370f-119">Transactions and Concurrency</span></span>](transactions-and-concurrency.md)  
 <span data-ttu-id="1370f-120">Содержит разделы, в которых описывается выполнение локальных транзакций, распределенных транзакций и работа с оптимистичным параллелизмом.</span><span class="sxs-lookup"><span data-stu-id="1370f-120">Contains topics describing how to perform local transactions, distributed transactions, and work with optimistic concurrency.</span></span>  
  
 [<span data-ttu-id="1370f-121">Извлечение идентификации или значений автонумерации</span><span class="sxs-lookup"><span data-stu-id="1370f-121">Retrieving Identity or Autonumber Values</span></span>](retrieving-identity-or-autonumber-values.md)  
 <span data-ttu-id="1370f-122">Содержит пример сопоставления значений, созданных для столбца **идентификаторов** в таблице SQL Server или для поля **счетчика** в таблице Microsoft Access, со столбцом вставленной строки в таблице.</span><span class="sxs-lookup"><span data-stu-id="1370f-122">Provides an example of mapping the values generated for an **identity** column in a SQL Server table or for an **Autonumber** field in a Microsoft Access table, to a column of an inserted row in a table.</span></span> <span data-ttu-id="1370f-123">Рассматривается слияние значений идентификаторов в объекте `DataTable`.</span><span class="sxs-lookup"><span data-stu-id="1370f-123">Discusses merging identity values in a `DataTable`.</span></span>  
  
 [<span data-ttu-id="1370f-124">Извлечение двоичных данных</span><span class="sxs-lookup"><span data-stu-id="1370f-124">Retrieving Binary Data</span></span>](retrieving-binary-data.md)  
 <span data-ttu-id="1370f-125">Описывает, как получить двоичные данные или крупные структуры данных с помощью `CommandBehavior` .`SequentialAccess`</span><span class="sxs-lookup"><span data-stu-id="1370f-125">Describes how to retrieve binary data or large data structures using `CommandBehavior`.`SequentialAccess`</span></span> <span data-ttu-id="1370f-126">изменение поведения по умолчанию для `DataReader` .</span><span class="sxs-lookup"><span data-stu-id="1370f-126">to modify the default behavior of a `DataReader`.</span></span>  
  
 [<span data-ttu-id="1370f-127">Изменение данных с помощью хранимых процедур</span><span class="sxs-lookup"><span data-stu-id="1370f-127">Modifying Data with Stored Procedures</span></span>](modifying-data-with-stored-procedures.md)  
 <span data-ttu-id="1370f-128">Описывается использование входных и выходных параметров хранимой процедуры для вставки строки в базу данных с возвратом нового значения идентификатора.</span><span class="sxs-lookup"><span data-stu-id="1370f-128">Describes how to use stored procedure input parameters and output parameters to insert a row in a database, returning a new identity value.</span></span>  
  
 [<span data-ttu-id="1370f-129">Извлечение сведений о схеме базы данных</span><span class="sxs-lookup"><span data-stu-id="1370f-129">Retrieving Database Schema Information</span></span>](retrieving-database-schema-information.md)  
 <span data-ttu-id="1370f-130">Описывает получение доступных баз данных или каталогов, таблиц и представлений базы данных, существующих ограничений для таблиц и других сведений о схеме из источника данных.</span><span class="sxs-lookup"><span data-stu-id="1370f-130">Describes how to obtain available databases or catalogs, tables and views in a database, constraints that exist for tables, and other schema information from a data source.</span></span>  
  
 [<span data-ttu-id="1370f-131">DbProviderFactories</span><span class="sxs-lookup"><span data-stu-id="1370f-131">DbProviderFactories</span></span>](dbproviderfactories.md)  
 <span data-ttu-id="1370f-132">Описывается модель фабрики поставщика и демонстрируется использование базовых классов в пространстве имен `System.Data.Common`.</span><span class="sxs-lookup"><span data-stu-id="1370f-132">Describes the provider factory model and demonstrates how to use the base classes in the `System.Data.Common` namespace.</span></span>  
  
 [<span data-ttu-id="1370f-133">Трассировка данных в ADO.NET</span><span class="sxs-lookup"><span data-stu-id="1370f-133">Data Tracing in ADO.NET</span></span>](data-tracing.md)  
 <span data-ttu-id="1370f-134">Описывается, как в ADO.NET реализованы встроенные функции трассировки данных.</span><span class="sxs-lookup"><span data-stu-id="1370f-134">Describes how ADO.NET provides built-in data tracing functionality.</span></span>  
  
 [<span data-ttu-id="1370f-135">Счетчики производительности</span><span class="sxs-lookup"><span data-stu-id="1370f-135">Performance Counters</span></span>](performance-counters.md)  
 <span data-ttu-id="1370f-136">Описываются счетчики производительности, доступные для `SqlClient` и `OracleClient`.</span><span class="sxs-lookup"><span data-stu-id="1370f-136">Describes performance counters available for `SqlClient` and `OracleClient`.</span></span>  
  
 [<span data-ttu-id="1370f-137">Асинхронное программирование</span><span class="sxs-lookup"><span data-stu-id="1370f-137">Asynchronous Programming</span></span>](asynchronous-programming.md)  
 <span data-ttu-id="1370f-138">Описывает поддержку ADO.NET для асинхронного программирования.</span><span class="sxs-lookup"><span data-stu-id="1370f-138">Describes ADO.NET support for asynchronous programming.</span></span>  
  
 [<span data-ttu-id="1370f-139">Поддержка потоковой передачи SqlClient</span><span class="sxs-lookup"><span data-stu-id="1370f-139">SqlClient Streaming Support</span></span>](sqlclient-streaming-support.md)  
 <span data-ttu-id="1370f-140">Описывает написание приложений, которые проводят потоковую передачу данных из SQL Server без полной загрузки в память.</span><span class="sxs-lookup"><span data-stu-id="1370f-140">Discusses how to write applications that stream data from SQL Server without having it fully loaded in memory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1370f-141">См. также</span><span class="sxs-lookup"><span data-stu-id="1370f-141">See also</span></span>

- [<span data-ttu-id="1370f-142">Сопоставления типов данных в ADO.NET</span><span class="sxs-lookup"><span data-stu-id="1370f-142">Data Type Mappings in ADO.NET</span></span>](data-type-mappings-in-ado-net.md)
- [<span data-ttu-id="1370f-143">Наборы данных, таблицы данных и объекты DataView</span><span class="sxs-lookup"><span data-stu-id="1370f-143">DataSets, DataTables, and DataViews</span></span>](./dataset-datatable-dataview/index.md)
- [<span data-ttu-id="1370f-144">Защита приложений ADO.NET</span><span class="sxs-lookup"><span data-stu-id="1370f-144">Securing ADO.NET Applications</span></span>](securing-ado-net-applications.md)
- [<span data-ttu-id="1370f-145">SQL Server и ADO.NET</span><span class="sxs-lookup"><span data-stu-id="1370f-145">SQL Server and ADO.NET</span></span>](./sql/index.md)
- [<span data-ttu-id="1370f-146">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="1370f-146">ADO.NET Overview</span></span>](ado-net-overview.md)
