---
title: Извлечение сведений о схеме базы данных
ms.date: 03/30/2017
ms.assetid: 79038d52-f122-4fd4-9bfb-aaa22d6a114b
ms.openlocfilehash: c0aaadc82771d1c2a36d797bc157d88b8d3cacdc
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177362"
---
# <a name="retrieving-database-schema-information"></a><span data-ttu-id="c413a-102">Извлечение сведений о схеме базы данных</span><span class="sxs-lookup"><span data-stu-id="c413a-102">Retrieving Database Schema Information</span></span>

<span data-ttu-id="c413a-103">Получение сведений о схеме из базы данных выполняется с помощью процесса обнаружения схемы.</span><span class="sxs-lookup"><span data-stu-id="c413a-103">Obtaining schema information from a database is accomplished with the process of schema discovery.</span></span> <span data-ttu-id="c413a-104">Обнаружение схемы позволяет приложениям запрашивать, что управляемые поставщики находят и возвращают сведения о схеме базы данных, также известные как *метаданные*заданной базы данных.</span><span class="sxs-lookup"><span data-stu-id="c413a-104">Schema discovery allows applications to request that managed providers find and return information about the database schema, also known as *metadata*, of a given database.</span></span> <span data-ttu-id="c413a-105">Различные элементы схемы базы данных, например таблицы, столбцы и хранимые процедуры, предоставляются через коллекции схем.</span><span class="sxs-lookup"><span data-stu-id="c413a-105">Different database schema elements such as tables, columns, and stored-procedures are exposed through schema collections.</span></span> <span data-ttu-id="c413a-106">Каждая коллекция схемы в зависимости от используемого поставщика содержит различные сведения о схеме.</span><span class="sxs-lookup"><span data-stu-id="c413a-106">Each schema collection contains a variety of schema information specific to the provider being used.</span></span>  
  
 <span data-ttu-id="c413a-107">Каждый из .NET Framework управляемых поставщиков реализует метод **GetSchema** в классе **Connection** , а сведения о схеме, возвращаемые методом **GetSchema** , поступают в виде <xref:System.Data.DataTable> .</span><span class="sxs-lookup"><span data-stu-id="c413a-107">Each of the .NET Framework managed providers implement the **GetSchema** method in the **Connection** class, and the schema information that is returned from the **GetSchema** method comes in the form of a <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="c413a-108">Метод **GetSchema** является перегруженным методом, который предоставляет необязательные параметры для указания возвращаемой коллекции схем и ограниченный объем возвращаемой информации.</span><span class="sxs-lookup"><span data-stu-id="c413a-108">The **GetSchema** method is an overloaded method that provides optional parameters for specifying the schema collection to return, and restricting the amount of information returned.</span></span>  
  
 <span data-ttu-id="c413a-109">Поставщики данных .NET Framework для OLE DB, ODBC, Oracle и SqlClient предоставляют метод **GetSchemaTable** , возвращающий объект DataTable, описывающий метаданные столбца для **DataReader**.</span><span class="sxs-lookup"><span data-stu-id="c413a-109">The .NET Framework Data Providers for OLE DB, ODBC, Oracle, and SqlClient provide a **GetSchemaTable** method that returns a DataTable describing the column metadata of the **DataReader**.</span></span>  
  
 <span data-ttu-id="c413a-110">Поставщик данных .NET Framework для OLE DB также предоставляет данные схемы с помощью метода <xref:System.Data.OleDb.OleDbConnection.GetOleDbSchemaTable%2A> объекта <xref:System.Data.OleDb.OleDbConnection>.</span><span class="sxs-lookup"><span data-stu-id="c413a-110">The .NET Framework Data Provider for OLE DB also exposes schema information by using the <xref:System.Data.OleDb.OleDbConnection.GetOleDbSchemaTable%2A> method of the <xref:System.Data.OleDb.OleDbConnection> object.</span></span> <span data-ttu-id="c413a-111">В качестве аргументов **жетоледбсчематабле** принимает <xref:System.Data.OleDb.OleDbSchemaGuid> , определяющий возвращаемую информацию о схеме, и массив ограничений на возвращаемые столбцы.</span><span class="sxs-lookup"><span data-stu-id="c413a-111">As arguments, **GetOleDbSchemaTable** takes an <xref:System.Data.OleDb.OleDbSchemaGuid> that identifies the schema information to return, and an array of restrictions on those returned columns.</span></span> <span data-ttu-id="c413a-112">**Жетоледбсчематабле** возвращает <xref:System.Data.DataTable> заполненную информацию о запрашиваемой схеме.</span><span class="sxs-lookup"><span data-stu-id="c413a-112">**GetOleDbSchemaTable** returns a <xref:System.Data.DataTable> populated with the requested schema information.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c413a-113">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="c413a-113">In This Section</span></span>  

 [<span data-ttu-id="c413a-114">Коллекции GetSchema и Schema</span><span class="sxs-lookup"><span data-stu-id="c413a-114">GetSchema and Schema Collections</span></span>](getschema-and-schema-collections.md)  
 <span data-ttu-id="c413a-115">Описывает метод **GetSchema** и способ его использования для извлечения и ограничения сведений о схеме из базы данных.</span><span class="sxs-lookup"><span data-stu-id="c413a-115">Describes the **GetSchema** method and how it can be used to retrieve and restrict schema information from a database.</span></span>  
  
 <span data-ttu-id="c413a-116">Ограничения схемы</span><span class="sxs-lookup"><span data-stu-id="c413a-116">Schema Restrictions</span></span>  
 <span data-ttu-id="c413a-117">Описывает ограничения схемы, которые можно использовать с **GetSchema**.</span><span class="sxs-lookup"><span data-stu-id="c413a-117">Describes schema restrictions that can be used with **GetSchema**.</span></span>  
  
 [<span data-ttu-id="c413a-118">Общие коллекции схемы</span><span class="sxs-lookup"><span data-stu-id="c413a-118">Common Schema Collections</span></span>](common-schema-collections.md)  
 <span data-ttu-id="c413a-119">Описывает стандартные коллекции схем, поддерживаемые всеми управляемыми поставщиками .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c413a-119">Describes all of the common schema collections supported by all of the .NET Framework managed providers.</span></span>  
  
 [<span data-ttu-id="c413a-120">Коллекции схемы SQL Server</span><span class="sxs-lookup"><span data-stu-id="c413a-120">SQL Server Schema Collections</span></span>](sql-server-schema-collections.md)  
 <span data-ttu-id="c413a-121">Описывается коллекция схем, поддерживаемая поставщиком .NET Framework для SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c413a-121">Describes the schema collection supported by the .NET Framework provider for SQL Server.</span></span>  
  
 [<span data-ttu-id="c413a-122">Коллекции схемы в Oracle</span><span class="sxs-lookup"><span data-stu-id="c413a-122">Oracle Schema Collections</span></span>](oracle-schema-collections.md)  
 <span data-ttu-id="c413a-123">Описывается коллекция схем, поддерживаемая поставщиком .NET Framework для Oracle.</span><span class="sxs-lookup"><span data-stu-id="c413a-123">Describes the schema collection supported by the .NET Framework provider for Oracle.</span></span>  
  
 [<span data-ttu-id="c413a-124">Коллекции схемы ODBC</span><span class="sxs-lookup"><span data-stu-id="c413a-124">ODBC Schema Collections</span></span>](odbc-schema-collections.md)  
 <span data-ttu-id="c413a-125">Описываются коллекции схем для драйверов ODBC.</span><span class="sxs-lookup"><span data-stu-id="c413a-125">Describes the schema collections for ODBC drivers.</span></span>  
  
 [<span data-ttu-id="c413a-126">Коллекции схемы OLE DB</span><span class="sxs-lookup"><span data-stu-id="c413a-126">OLE DB Schema Collections</span></span>](ole-db-schema-collections.md)  
 <span data-ttu-id="c413a-127">Описываются коллекции схем для поставщиков OLE DB.</span><span class="sxs-lookup"><span data-stu-id="c413a-127">Describes the schema collections for OLE DB providers.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="c413a-128">Справка</span><span class="sxs-lookup"><span data-stu-id="c413a-128">Reference</span></span>  

 <xref:System.Data.Common.DbConnection.GetSchema%2A>  
 <span data-ttu-id="c413a-129">Описывает метод **GetSchema** <xref:System.Data.Common.DbConnection> класса.</span><span class="sxs-lookup"><span data-stu-id="c413a-129">Describes the **GetSchema** method of the <xref:System.Data.Common.DbConnection> class.</span></span>  
  
 <xref:System.Data.Odbc.OdbcConnection.GetSchema%2A>  
 <span data-ttu-id="c413a-130">Описывает метод **GetSchema** <xref:System.Data.Odbc.OdbcConnection> класса.</span><span class="sxs-lookup"><span data-stu-id="c413a-130">Describes the **GetSchema** method of the <xref:System.Data.Odbc.OdbcConnection> class.</span></span>  
  
 <xref:System.Data.OleDb.OleDbConnection.GetSchema%2A>  
 <span data-ttu-id="c413a-131">Описывает метод **GetSchema** <xref:System.Data.OleDb.OleDbConnection> класса.</span><span class="sxs-lookup"><span data-stu-id="c413a-131">Describes the **GetSchema** method of the <xref:System.Data.OleDb.OleDbConnection> class.</span></span>  
  
 <xref:System.Data.OracleClient.OracleConnection.GetSchema%2A>  
 <span data-ttu-id="c413a-132">Описывает метод **GetSchema** <xref:System.Data.OracleClient.OracleConnection> класса.</span><span class="sxs-lookup"><span data-stu-id="c413a-132">Describes the **GetSchema** method of the <xref:System.Data.OracleClient.OracleConnection> class.</span></span>  
  
 <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A>  
 <span data-ttu-id="c413a-133">Описывает метод **GetSchema** <xref:System.Data.SqlClient.SqlConnection> класса.</span><span class="sxs-lookup"><span data-stu-id="c413a-133">Describes the **GetSchema** method of the <xref:System.Data.SqlClient.SqlConnection> class.</span></span>  
  
 <xref:System.Data.Common.DbDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="c413a-134">Описывает метод **GetSchemaTable** <xref:System.Data.Common.DbDataReader> класса.</span><span class="sxs-lookup"><span data-stu-id="c413a-134">Describes the **GetSchemaTable** method of the <xref:System.Data.Common.DbDataReader> class.</span></span>  
  
 <xref:System.Data.Odbc.OdbcDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="c413a-135">Описывает метод **GetSchemaTable** <xref:System.Data.Odbc.OdbcDataReader> класса.</span><span class="sxs-lookup"><span data-stu-id="c413a-135">Describes the **GetSchemaTable** method of the <xref:System.Data.Odbc.OdbcDataReader> class.</span></span>  
  
 <xref:System.Data.OleDb.OleDbDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="c413a-136">Описывает метод **GetSchemaTable** <xref:System.Data.OleDb.OleDbDataReader> класса.</span><span class="sxs-lookup"><span data-stu-id="c413a-136">Describes the **GetSchemaTable** method of the <xref:System.Data.OleDb.OleDbDataReader> class.</span></span>  
  
 <xref:System.Data.OracleClient.OracleDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="c413a-137">Описывает метод **GetSchemaTable** <xref:System.Data.OracleClient.OracleDataReader> класса.</span><span class="sxs-lookup"><span data-stu-id="c413a-137">Describes the **GetSchemaTable** method of the <xref:System.Data.OracleClient.OracleDataReader> class.</span></span>  
  
 <xref:System.Data.SqlClient.SqlDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="c413a-138">Описывает метод **GetSchemaTable** <xref:System.Data.SqlClient.SqlDataReader> класса.</span><span class="sxs-lookup"><span data-stu-id="c413a-138">Describes the **GetSchemaTable** method of the <xref:System.Data.SqlClient.SqlDataReader> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c413a-139">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="c413a-139">See also</span></span>

- [<span data-ttu-id="c413a-140">Извлечение и изменение данных в ADO.NET</span><span class="sxs-lookup"><span data-stu-id="c413a-140">Retrieving and Modifying Data in ADO.NET</span></span>](retrieving-and-modifying-data.md)
- [<span data-ttu-id="c413a-141">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="c413a-141">ADO.NET Overview</span></span>](ado-net-overview.md)
