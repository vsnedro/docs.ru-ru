---
title: Типы данных SQL Server и ADO.NET
titleSuffix: ''
ms.date: 03/30/2017
ms.assetid: 81b43550-23e8-43bb-b460-7eb8ac825c33
ms.openlocfilehash: db4618ac624ea8401cab682a8c21d8f23c253d05
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91155462"
---
# <a name="sql-server-data-types-and-adonet"></a><span data-ttu-id="f3344-102">Типы данных SQL Server и ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f3344-102">SQL Server Data Types and ADO.NET</span></span>

<span data-ttu-id="f3344-103">В SQL Server и .NET Framework используются различные системы типов, что может привести к потенциальной потере данных.</span><span class="sxs-lookup"><span data-stu-id="f3344-103">SQL Server and the .NET Framework are based on different type systems, which can result in potential data loss.</span></span> <span data-ttu-id="f3344-104">Чтобы сохранить целостность данных, поставщик данных .NET Framework для SQL Server (<xref:System.Data.SqlClient>) предоставляет типизированные методы доступа для работы с данными SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f3344-104">To preserve data integrity, the .NET Framework Data Provider for SQL Server (<xref:System.Data.SqlClient>) provides typed accessor methods for working with SQL Server data.</span></span> <span data-ttu-id="f3344-105">Перечисления в классах <xref:System.Data.SqlDbType> можно использовать для указания типов данных <xref:System.Data.SqlClient.SqlParameter>.</span><span class="sxs-lookup"><span data-stu-id="f3344-105">You can use the enumerations in the <xref:System.Data.SqlDbType> classes to specify <xref:System.Data.SqlClient.SqlParameter> data types.</span></span>  
  
 <span data-ttu-id="f3344-106">Дополнительные сведения и таблица с описанием сопоставлений типов данных между типами данных SQL Server и .NET Framework см. в разделе [SQL Server сопоставления типов данных](../sql-server-data-type-mappings.md).</span><span class="sxs-lookup"><span data-stu-id="f3344-106">For more information and a table that describes the data type mappings between SQL Server and .NET Framework data types, see [SQL Server Data Type Mappings](../sql-server-data-type-mappings.md).</span></span>  
  
 <span data-ttu-id="f3344-107">В SQL Server 2008 появились новые типы данных, разработанные для удовлетворения бизнес-потребностей при работе с датами и временем, структурированными, частично структурированными и неструктурированными данными.</span><span class="sxs-lookup"><span data-stu-id="f3344-107">SQL Server 2008 introduces new data types that are designed to meet business needs to work with date and time, structured, semi-structured, and unstructured data.</span></span> <span data-ttu-id="f3344-108">Они описаны в электронной документации на SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="f3344-108">These are documented in SQL Server 2008 Books Online.</span></span>  
  
 <span data-ttu-id="f3344-109">Типы данных SQL Server, доступные для использования в приложении, зависят от используемой версии SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f3344-109">The SQL Server data types that are available for use in your application depends on the version of SQL Server that you are using.</span></span> <span data-ttu-id="f3344-110">Дополнительные сведения см. в электронной документации для соответствующей версии SQL Server в приведенной ниже таблице.</span><span class="sxs-lookup"><span data-stu-id="f3344-110">For more information, see the relevant version of SQL Server Books Online in the following table.</span></span>  
  
 <span data-ttu-id="f3344-111">**Документация по SQL Server**</span><span class="sxs-lookup"><span data-stu-id="f3344-111">**SQL Server documentation**</span></span>  
  
1. [<span data-ttu-id="f3344-112">Типы данных (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="f3344-112">Data Types (Transact-SQL)</span></span>](/sql/t-sql/data-types/data-types-transact-sql)  
  
## <a name="in-this-section"></a><span data-ttu-id="f3344-113">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="f3344-113">In This Section</span></span>  

 [<span data-ttu-id="f3344-114">Типы SqlType и набор данных</span><span class="sxs-lookup"><span data-stu-id="f3344-114">SqlTypes and the DataSet</span></span>](sqltypes-and-the-dataset.md)  
 <span data-ttu-id="f3344-115">Описывает тип поддержки пространства имен `SqlTypes` в `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="f3344-115">Describes type support for `SqlTypes` in the `DataSet`.</span></span>  
  
 [<span data-ttu-id="f3344-116">Обработка значений NULL</span><span class="sxs-lookup"><span data-stu-id="f3344-116">Handling Null Values</span></span>](handling-null-values.md)  
 <span data-ttu-id="f3344-117">Демонстрирует работу со значениями NULL и логикой трех значений.</span><span class="sxs-lookup"><span data-stu-id="f3344-117">Demonstrates how to work with null values and three-valued logic.</span></span>  
  
 [<span data-ttu-id="f3344-118">Сравнение значений идентификатора GUID и uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="f3344-118">Comparing GUID and uniqueidentifier Values</span></span>](comparing-guid-and-uniqueidentifier-values.md)  
 <span data-ttu-id="f3344-119">Демонстрируется работа со значениями GUID и uniqueidentifier в SQL Server и .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f3344-119">Demonstrates how to work with GUID and uniqueidentifier values in SQL Server and the .NET Framework.</span></span>  
  
 [<span data-ttu-id="f3344-120">Данные даты и времени</span><span class="sxs-lookup"><span data-stu-id="f3344-120">Date and Time Data</span></span>](date-and-time-data.md)  
 <span data-ttu-id="f3344-121">В этой статье описывается использование новых типов данных даты и времени, появившихся в SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="f3344-121">Describes how to use the new date and time data types introduced in SQL Server 2008.</span></span>  
  
 [<span data-ttu-id="f3344-122">Большие, определяемые пользователем типы</span><span class="sxs-lookup"><span data-stu-id="f3344-122">Large UDTs</span></span>](large-udts.md)  
 <span data-ttu-id="f3344-123">Здесь демонстрируется получение данных из UDT с большими значениями, представленных в SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="f3344-123">Demonstrates how to retrieve data from large value UDTs introduced in SQL Server 2008.</span></span>  
  
 [<span data-ttu-id="f3344-124">XML-данные в SQL Server</span><span class="sxs-lookup"><span data-stu-id="f3344-124">XML Data in SQL Server</span></span>](xml-data-in-sql-server.md)  
 <span data-ttu-id="f3344-125">Сведения о том, как работать с XML-данными, полученными из SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f3344-125">Describes how to work with XML data retrieved from SQL Server.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="f3344-126">Справка</span><span class="sxs-lookup"><span data-stu-id="f3344-126">Reference</span></span>  

 <xref:System.Data.DataSet>  
 <span data-ttu-id="f3344-127">Описание класса `DataSet` и всех его членов.</span><span class="sxs-lookup"><span data-stu-id="f3344-127">Describes the `DataSet` class and all of its members.</span></span>  
  
 <xref:System.Data.SqlTypes>  
 <span data-ttu-id="f3344-128">Описание пространства имен `SqlTypes` и всех его членов.</span><span class="sxs-lookup"><span data-stu-id="f3344-128">Describes the `SqlTypes` namespace and all of its members.</span></span>  
  
 <xref:System.Data.SqlDbType>  
 <span data-ttu-id="f3344-129">Описание перечисления `SqlDbType` и всех его членов.</span><span class="sxs-lookup"><span data-stu-id="f3344-129">Describes the `SqlDbType` enumeration and all of its members.</span></span>  
  
 <xref:System.Data.DbType>  
 <span data-ttu-id="f3344-130">Описание перечисления `DbType` и всех его членов.</span><span class="sxs-lookup"><span data-stu-id="f3344-130">Describes the `DbType` enumeration and all of its members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3344-131">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f3344-131">See also</span></span>

- [<span data-ttu-id="f3344-132">Сопоставления типов данных SQL Server</span><span class="sxs-lookup"><span data-stu-id="f3344-132">SQL Server Data Type Mappings</span></span>](../sql-server-data-type-mappings.md)
- [<span data-ttu-id="f3344-133">Настройка параметров и типы данных параметров</span><span class="sxs-lookup"><span data-stu-id="f3344-133">Configuring Parameters and Parameter Data Types</span></span>](../configuring-parameters-and-parameter-data-types.md)
- [<span data-ttu-id="f3344-134">Параметры, возвращающие табличные значения</span><span class="sxs-lookup"><span data-stu-id="f3344-134">Table-Valued Parameters</span></span>](table-valued-parameters.md)
- [<span data-ttu-id="f3344-135">SQL Server данные в двоичном и больших значениях</span><span class="sxs-lookup"><span data-stu-id="f3344-135">SQL Server Binary and Large-Value Data</span></span>](sql-server-binary-and-large-value-data.md)
- [<span data-ttu-id="f3344-136">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f3344-136">ADO.NET Overview</span></span>](../ado-net-overview.md)
