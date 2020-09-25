---
title: Объекты DataAdapter и DataReader
description: Сведения о ADO.NET DataReader, который извлекает данные из базы данных, и DataAdapter, который извлекает данные из источника данных и заполняет набор данных.
ms.date: 03/30/2017
ms.assetid: cc952ca2-ec19-46ab-9189-15174b52cb74
ms.openlocfilehash: 2584f8b382dd90f2f8b4554663dc545b9ccceb62
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177609"
---
# <a name="dataadapters-and-datareaders"></a><span data-ttu-id="e5079-103">Объекты DataAdapter и DataReader</span><span class="sxs-lookup"><span data-stu-id="e5079-103">DataAdapters and DataReaders</span></span>

<span data-ttu-id="e5079-104">ADO.NET **DataReader** можно использовать для получения однопроходного потока данных из базы данных только для чтения.</span><span class="sxs-lookup"><span data-stu-id="e5079-104">You can use the ADO.NET **DataReader** to retrieve a read-only, forward-only stream of data from a database.</span></span> <span data-ttu-id="e5079-105">Результаты возвращаются при выполнении запроса и хранятся в сетевом буфере на клиенте, пока они не будут запрошены с помощью метода **Read** объекта **DataReader**.</span><span class="sxs-lookup"><span data-stu-id="e5079-105">Results are returned as the query executes, and are stored in the network buffer on the client until you request them using the **Read** method of the **DataReader**.</span></span> <span data-ttu-id="e5079-106">Использование **DataReader** может увеличить производительность приложения, извлекая данные сразу после их доступности и (по умолчанию) сохраняя в памяти только одну строку за раз, уменьшая нагрузку на систему.</span><span class="sxs-lookup"><span data-stu-id="e5079-106">Using the **DataReader** can increase application performance both by retrieving data as soon as it is available, and (by default) storing only one row at a time in memory, reducing system overhead.</span></span>  
  
 <span data-ttu-id="e5079-107">Класс <xref:System.Data.Common.DataAdapter> используется для получения данных из источника данных и заполнения таблиц в <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="e5079-107">A <xref:System.Data.Common.DataAdapter> is used to retrieve data from a data source and populate tables within a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="e5079-108">Класс `DataAdapter` позволяет также решить задачу по возврату изменений, сделанных в объекте `DataSet`, обратно в источник данных.</span><span class="sxs-lookup"><span data-stu-id="e5079-108">The `DataAdapter` also resolves changes made to the `DataSet` back to the data source.</span></span> <span data-ttu-id="e5079-109">В классе `DataAdapter` используется объект `Connection` поставщика данных .NET Framework для подключения к источнику данных, а также используются объекты `Command` для получения из него данных и решения задачи по записи изменений в источник данных.</span><span class="sxs-lookup"><span data-stu-id="e5079-109">The `DataAdapter` uses the `Connection` object of the .NET Framework data provider to connect to a data source, and it uses `Command` objects to retrieve data from and resolve changes to the data source.</span></span>  
  
 <span data-ttu-id="e5079-110">Каждый поставщик данных .NET Framework, входящий в состав .NET Framework, включает объекты <xref:System.Data.Common.DbDataReader> и <xref:System.Data.Common.DbDataAdapter>: поставщик данных .NET Framework для OLE DB - объекты <xref:System.Data.OleDb.OleDbDataReader> и <xref:System.Data.OleDb.OleDbDataAdapter>, поставщик данных .NET Framework для SQL Server - объекты <xref:System.Data.SqlClient.SqlDataReader> и <xref:System.Data.SqlClient.SqlDataAdapter>, поставщик данных .NET Framework для ODBC - объекты <xref:System.Data.Odbc.OdbcDataReader> и <xref:System.Data.Odbc.OdbcDataAdapter>, а поставщик данных .NET Framework для Oracle - объекты <xref:System.Data.OracleClient.OracleDataReader> и <xref:System.Data.OracleClient.OracleDataAdapter>.</span><span class="sxs-lookup"><span data-stu-id="e5079-110">Each .NET Framework data provider included with the .NET Framework has a <xref:System.Data.Common.DbDataReader> and a <xref:System.Data.Common.DbDataAdapter> object: the .NET Framework Data Provider for OLE DB includes an <xref:System.Data.OleDb.OleDbDataReader> and an <xref:System.Data.OleDb.OleDbDataAdapter> object, the .NET Framework Data Provider for SQL Server includes a <xref:System.Data.SqlClient.SqlDataReader> and a <xref:System.Data.SqlClient.SqlDataAdapter> object, the .NET Framework Data Provider for ODBC includes an <xref:System.Data.Odbc.OdbcDataReader> and an <xref:System.Data.Odbc.OdbcDataAdapter> object, and the .NET Framework Data Provider for Oracle includes an <xref:System.Data.OracleClient.OracleDataReader> and an <xref:System.Data.OracleClient.OracleDataAdapter> object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e5079-111">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="e5079-111">In This Section</span></span>  

 [<span data-ttu-id="e5079-112">Извлечение данных с помощью объекта DataReader</span><span class="sxs-lookup"><span data-stu-id="e5079-112">Retrieving Data Using a DataReader</span></span>](retrieving-data-using-a-datareader.md)  
 <span data-ttu-id="e5079-113">Описывает объект **datareader** ADO.NET и способ его использования для возврата потока результатов из источника данных.</span><span class="sxs-lookup"><span data-stu-id="e5079-113">Describes the ADO.NET **DataReader** object and how to use it to return a stream of results from a data source.</span></span>  
  
 [<span data-ttu-id="e5079-114">Заполнение набора данных с помощью адаптера данных DataAdapter</span><span class="sxs-lookup"><span data-stu-id="e5079-114">Populating a DataSet from a DataAdapter</span></span>](populating-a-dataset-from-a-dataadapter.md)  
 <span data-ttu-id="e5079-115">Содержит описание того, как заполнить `DataSet` таблицами, столбцами и строками с использованием `DataAdapter`.</span><span class="sxs-lookup"><span data-stu-id="e5079-115">Describes how to fill a `DataSet` with tables, columns, and rows by using a `DataAdapter`.</span></span>  
  
 [<span data-ttu-id="e5079-116">Параметры DataAdapter</span><span class="sxs-lookup"><span data-stu-id="e5079-116">DataAdapter Parameters</span></span>](dataadapter-parameters.md)  
 <span data-ttu-id="e5079-117">Показывает, как использовать параметры со свойствами команды `DataAdapter`, включая то, как сопоставить содержимое столбца в `DataSet` с параметром команды.</span><span class="sxs-lookup"><span data-stu-id="e5079-117">Describes how to use parameters with the command properties of a `DataAdapter` including how to map the contents of a column in a `DataSet` to a command parameter.</span></span>  
  
 [<span data-ttu-id="e5079-118">Добавление существующих ограничений к набору данных</span><span class="sxs-lookup"><span data-stu-id="e5079-118">Adding Existing Constraints to a DataSet</span></span>](adding-existing-constraints-to-a-dataset.md)  
 <span data-ttu-id="e5079-119">Показывает, как добавить существующие ограничения к `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="e5079-119">Describes how to add existing constraints to a `DataSet`.</span></span>  
  
 [<span data-ttu-id="e5079-120">Сопоставления DataAdapter DataTable и DataColumn</span><span class="sxs-lookup"><span data-stu-id="e5079-120">DataAdapter DataTable and DataColumn Mappings</span></span>](dataadapter-datatable-and-datacolumn-mappings.md)  
 <span data-ttu-id="e5079-121">Описывает, как задать `DataTableMappings` и `ColumnMappings` для `DataAdapter`.</span><span class="sxs-lookup"><span data-stu-id="e5079-121">Describes how to set up `DataTableMappings` and `ColumnMappings` for a `DataAdapter`.</span></span>  
  
 [<span data-ttu-id="e5079-122">Разбивка на страницы результатов запроса</span><span class="sxs-lookup"><span data-stu-id="e5079-122">Paging Through a Query Result</span></span>](paging-through-a-query-result.md)  
 <span data-ttu-id="e5079-123">Предоставляет пример просмотра результатов запроса в виде страниц данных.</span><span class="sxs-lookup"><span data-stu-id="e5079-123">Provides an example of viewing the results of a query as pages of data.</span></span>  
  
 [<span data-ttu-id="e5079-124">Обновление источников данных с объектами DataAdapter</span><span class="sxs-lookup"><span data-stu-id="e5079-124">Updating Data Sources with DataAdapters</span></span>](updating-data-sources-with-dataadapters.md)  
 <span data-ttu-id="e5079-125">Описывает, как использовать `DataAdapter` для решения задачи записи изменений в `DataSet` обратно в базу данных.</span><span class="sxs-lookup"><span data-stu-id="e5079-125">Describes how to use a `DataAdapter` to resolve changes in a `DataSet` back to the database.</span></span>  
  
 [<span data-ttu-id="e5079-126">Обработка событий DataAdapter</span><span class="sxs-lookup"><span data-stu-id="e5079-126">Handling DataAdapter Events</span></span>](handling-dataadapter-events.md)  
 <span data-ttu-id="e5079-127">Описывает события `DataAdapter` и способы их использования.</span><span class="sxs-lookup"><span data-stu-id="e5079-127">Describes `DataAdapter` events and how to use them.</span></span>  
  
 [<span data-ttu-id="e5079-128">Выполнение пакетных операций с использованием объектов DataAdapters</span><span class="sxs-lookup"><span data-stu-id="e5079-128">Performing Batch Operations Using DataAdapters</span></span>](performing-batch-operations-using-dataadapters.md)  
 <span data-ttu-id="e5079-129">Показывает, как повысить производительность приложения путем уменьшения количества циклов обмена данными с SQL Server в ходе применения обновлений из `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="e5079-129">Describes enhancing application performance by reducing the number of round trips to SQL Server when applying updates from the `DataSet`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5079-130">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e5079-130">See also</span></span>

- [<span data-ttu-id="e5079-131">Подключение к источнику данных</span><span class="sxs-lookup"><span data-stu-id="e5079-131">Connecting to a Data Source</span></span>](connecting-to-a-data-source.md)
- [<span data-ttu-id="e5079-132">Команды и параметры</span><span class="sxs-lookup"><span data-stu-id="e5079-132">Commands and Parameters</span></span>](commands-and-parameters.md)
- [<span data-ttu-id="e5079-133">Транзакции и параллельность</span><span class="sxs-lookup"><span data-stu-id="e5079-133">Transactions and Concurrency</span></span>](transactions-and-concurrency.md)
- [<span data-ttu-id="e5079-134">Наборы данных, таблицы данных и объекты DataView</span><span class="sxs-lookup"><span data-stu-id="e5079-134">DataSets, DataTables, and DataViews</span></span>](./dataset-datatable-dataview/index.md)
- [<span data-ttu-id="e5079-135">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="e5079-135">ADO.NET Overview</span></span>](ado-net-overview.md)
