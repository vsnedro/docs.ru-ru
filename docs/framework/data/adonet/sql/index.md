---
title: SQL Server и ADO.NET
description: Сведения о функциях и поведении поставщика данных .NET Framework для SQL Server, который инкапсулирует протоколы, относящиеся к базе данных.
titleSuffix: ''
ms.date: 03/30/2017
ms.assetid: c18b1fb1-2af1-4de7-80a4-95e56fd976cb
ms.openlocfilehash: eeb0ab69a68dfc2fc0faa1b4e833f80b307fffe5
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286446"
---
# <a name="sql-server-and-adonet"></a><span data-ttu-id="551d1-103">SQL Server и ADO.NET</span><span class="sxs-lookup"><span data-stu-id="551d1-103">SQL Server and ADO.NET</span></span>
<span data-ttu-id="551d1-104">В данном разделе описываются возможности и поведение, характерное для поставщика данных .NET Framework для SQL Server (<xref:System.Data.SqlClient>).</span><span class="sxs-lookup"><span data-stu-id="551d1-104">This section describes features and behaviors that are specific to the .NET Framework Data Provider for SQL Server (<xref:System.Data.SqlClient>).</span></span>  
  
 <span data-ttu-id="551d1-105"><xref:System.Data.SqlClient> предоставляет доступ к версиям SQL Server и инкапсулирует протоколы для конкретных баз данных.</span><span class="sxs-lookup"><span data-stu-id="551d1-105"><xref:System.Data.SqlClient> provides access to versions of SQL Server, which encapsulates database-specific protocols.</span></span> <span data-ttu-id="551d1-106">Возможности поставщика данных похожи на возможности поставщиков данных .NET Framework для OLE DB, ODBC и Oracle.</span><span class="sxs-lookup"><span data-stu-id="551d1-106">The functionality of the data provider is designed to be similar to that of the .NET Framework data providers for OLE DB, ODBC, and Oracle.</span></span> <span data-ttu-id="551d1-107"><xref:System.Data.SqlClient> содержит средство синтаксического анализа потока табличных данных (TDS) для непосредственного взаимодействия с SQL Server.</span><span class="sxs-lookup"><span data-stu-id="551d1-107"><xref:System.Data.SqlClient> includes a tabular data stream (TDS) parser to communicate directly with SQL Server.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="551d1-108">Чтобы использовать поставщик данных .NET Framework для SQL Server, приложение должно ссылаться на пространство имен <xref:System.Data.SqlClient>.</span><span class="sxs-lookup"><span data-stu-id="551d1-108">To use the .NET Framework Data Provider for SQL Server, an application must reference the <xref:System.Data.SqlClient> namespace.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="551d1-109">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="551d1-109">In This Section</span></span>  
 [<span data-ttu-id="551d1-110">Безопасность SQL Server</span><span class="sxs-lookup"><span data-stu-id="551d1-110">SQL Server Security</span></span>](sql-server-security.md)  
 <span data-ttu-id="551d1-111">Общие сведения о средствах безопасности SQL Server и сценариях приложений для создания безопасных приложений ADO.NET, предназначенных для SQL Server.</span><span class="sxs-lookup"><span data-stu-id="551d1-111">Provides an overview of SQL Server security features, and application scenarios for creating secure ADO.NET applications that target SQL Server.</span></span>  
  
 [<span data-ttu-id="551d1-112">Типы данных SQL Server и ADO.NET</span><span class="sxs-lookup"><span data-stu-id="551d1-112">SQL Server Data Types and ADO.NET</span></span>](sql-server-data-types.md)  
 <span data-ttu-id="551d1-113">Описывается работа с типами данных SQL Server и их взаимодействие с типами данных .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="551d1-113">Describes how to work with SQL Server data types and how they interact with .NET Framework data types.</span></span>  
  
 [<span data-ttu-id="551d1-114">SQL Server данные в двоичном и больших значениях</span><span class="sxs-lookup"><span data-stu-id="551d1-114">SQL Server Binary and Large-Value Data</span></span>](sql-server-binary-and-large-value-data.md)  
 <span data-ttu-id="551d1-115">Описание работы с данными больших значений в SQL Server.</span><span class="sxs-lookup"><span data-stu-id="551d1-115">Describes how to work with large value data in SQL Server.</span></span>  
  
 [<span data-ttu-id="551d1-116">SQL Serverные операции с данными в ADO.NET</span><span class="sxs-lookup"><span data-stu-id="551d1-116">SQL Server Data Operations in ADO.NET</span></span>](sql-server-data-operations.md)  
 <span data-ttu-id="551d1-117">Описание работы с данными в SQL Server.</span><span class="sxs-lookup"><span data-stu-id="551d1-117">Describes how to work with data in SQL Server.</span></span> <span data-ttu-id="551d1-118">Содержит разделы, посвященные массовым операциям копирования, режиму MARS, асинхронным операциям и возвращающим табличное значение параметрам.</span><span class="sxs-lookup"><span data-stu-id="551d1-118">Contains sections about bulk copy operations, MARS, asynchronous operations, and table-valued parameters.</span></span>  
  
 [<span data-ttu-id="551d1-119">SQL Server функций и ADO.NET</span><span class="sxs-lookup"><span data-stu-id="551d1-119">SQL Server Features and ADO.NET</span></span>](sql-server-features-and-adonet.md)  
 <span data-ttu-id="551d1-120">Описание функций SQL Server, полезных для разработчиков приложений ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="551d1-120">Describes SQL Server features that are useful for ADO.NET application developers.</span></span>  
  
 [<span data-ttu-id="551d1-121">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="551d1-121">LINQ to SQL</span></span>](./linq/index.md)  
 <span data-ttu-id="551d1-122">Описываются основные стандартные блоки, процессы и методы, необходимые для создания приложений по технологии LINQ to SQL.</span><span class="sxs-lookup"><span data-stu-id="551d1-122">Describes the basic building blocks, processes, and techniques required for creating LINQ to SQL applications.</span></span>  
  
 <span data-ttu-id="551d1-123">Полное описание ядра СУБД SQL Server приведено в электронной документации по используемой версии SQL Server.</span><span class="sxs-lookup"><span data-stu-id="551d1-123">For complete documentation of the SQL Server Database Engine, see SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 [<span data-ttu-id="551d1-124">Электронная документация по SQL Server</span><span class="sxs-lookup"><span data-stu-id="551d1-124">SQL Server Books Online</span></span>](/sql/sql-server/sql-server-technical-documentation)  
  
## <a name="see-also"></a><span data-ttu-id="551d1-125">См. также</span><span class="sxs-lookup"><span data-stu-id="551d1-125">See also</span></span>

- [<span data-ttu-id="551d1-126">Защита приложений ADO.NET</span><span class="sxs-lookup"><span data-stu-id="551d1-126">Securing ADO.NET Applications</span></span>](../securing-ado-net-applications.md)
- [<span data-ttu-id="551d1-127">Сопоставления типов данных в ADO.NET</span><span class="sxs-lookup"><span data-stu-id="551d1-127">Data Type Mappings in ADO.NET</span></span>](../data-type-mappings-in-ado-net.md)
- [<span data-ttu-id="551d1-128">Наборы данных, таблицы данных и объекты DataView</span><span class="sxs-lookup"><span data-stu-id="551d1-128">DataSets, DataTables, and DataViews</span></span>](../dataset-datatable-dataview/index.md)
- [<span data-ttu-id="551d1-129">Извлечение и изменение данных в ADO.NET</span><span class="sxs-lookup"><span data-stu-id="551d1-129">Retrieving and Modifying Data in ADO.NET</span></span>](../retrieving-and-modifying-data.md)
- [<span data-ttu-id="551d1-130">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="551d1-130">ADO.NET Overview</span></span>](../ado-net-overview.md)
