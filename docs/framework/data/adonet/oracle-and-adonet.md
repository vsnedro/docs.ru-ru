---
title: Oracle и ADO.NET
description: Сведения о функциях и поведении поставщика данных .NET Framework для Oracle, который обеспечивает доступ к базе данных Oracle с помощью интерфейса вызова Oracle.
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8ee8e389-53cf-45cf-80bd-1df63ef34f2e
ms.openlocfilehash: 736b8dc5179a15ec219c1dae06b9ee6b5d6c3ef3
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166629"
---
# <a name="oracle-and-adonet"></a><span data-ttu-id="efb7a-103">Oracle и ADO.NET</span><span class="sxs-lookup"><span data-stu-id="efb7a-103">Oracle and ADO.NET</span></span>

> [!NOTE]
> <span data-ttu-id="efb7a-104">Типы в пространстве имен <xref:System.Data.OracleClient> считаются устаревшими.</span><span class="sxs-lookup"><span data-stu-id="efb7a-104">The types in <xref:System.Data.OracleClient> are deprecated.</span></span> <span data-ttu-id="efb7a-105">Эти типы по-прежнему поддерживаются в платформе .NET Framework текущей версии, однако будут удалены в следующем выпуске.</span><span class="sxs-lookup"><span data-stu-id="efb7a-105">The types remain supported in the current version of.NET Framework but will be removed in a future release.</span></span> <span data-ttu-id="efb7a-106">Корпорация Майкрософт рекомендует использовать поставщик Oracle, предоставляемый сторонними разработчиками.</span><span class="sxs-lookup"><span data-stu-id="efb7a-106">Microsoft recommends that you use a third-party Oracle provider.</span></span>  
  
 <span data-ttu-id="efb7a-107">В этом разделе описываются функции и поведения, характерные для поставщика данных .NET Framework для Oracle.</span><span class="sxs-lookup"><span data-stu-id="efb7a-107">This section describes features and behaviors that are specific to the .NET Framework Data Provider for Oracle.</span></span>  
  
 <span data-ttu-id="efb7a-108">Поставщик данных .NET Framework для Oracle предоставляет доступ к базе данных Oracle с помощью интерфейса Oracle Call Interface (OCI), предоставляемого клиентским программным обеспечением Oracle.</span><span class="sxs-lookup"><span data-stu-id="efb7a-108">The .NET Framework Data Provider for Oracle provides access to an Oracle database using the Oracle Call Interface (OCI) as provided by Oracle Client software.</span></span> <span data-ttu-id="efb7a-109">Функциональные возможности поставщика данных аналогичны функциям .NET Framework поставщиков данных для SQL Server, OLE DB и ODBC.</span><span class="sxs-lookup"><span data-stu-id="efb7a-109">The functionality of the data provider is designed to be similar to that of the .NET Framework data providers for SQL Server, OLE DB, and ODBC.</span></span>  
  
 <span data-ttu-id="efb7a-110">Чтобы использовать поставщик данных .NET Framework для Oracle, приложение должно ссылаться на <xref:System.Data.OracleClient> пространство имен следующим образом:</span><span class="sxs-lookup"><span data-stu-id="efb7a-110">To use the .NET Framework Data Provider for Oracle, an application must reference the <xref:System.Data.OracleClient> namespace as follows:</span></span>  
  
```vb  
Imports System.Data.OracleClient  
```  
  
```csharp  
using System.Data.OracleClient;  
```  
  
 <span data-ttu-id="efb7a-111">Также при компиляции кода необходимо включить ссылку на библиотеку DLL.</span><span class="sxs-lookup"><span data-stu-id="efb7a-111">You also must include a reference to the DLL when you compile your code.</span></span> <span data-ttu-id="efb7a-112">Например, при компиляции программы C# командная строка должна включать:</span><span class="sxs-lookup"><span data-stu-id="efb7a-112">For example, if you are compiling a C# program, your command line should include:</span></span>  
  
```console
csc /r:System.Data.OracleClient.dll  
```  
  
## <a name="in-this-section"></a><span data-ttu-id="efb7a-113">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="efb7a-113">In This Section</span></span>  

 [<span data-ttu-id="efb7a-114">Требования к системе</span><span class="sxs-lookup"><span data-stu-id="efb7a-114">System Requirements</span></span>](system-requirements-for-the-dotnet-data-provider-for-oracle.md)  
 <span data-ttu-id="efb7a-115">Описывает требования к использованию поставщика данных .NET Framework для Oracle и описывает ряд проблем, которые необходимо учитывать при их использовании.</span><span class="sxs-lookup"><span data-stu-id="efb7a-115">Describes requirements for using the .NET Framework Data Provider for Oracle, and describes a number of issues to be aware when using it.</span></span>  
  
 [<span data-ttu-id="efb7a-116">BFILE в Oracle</span><span class="sxs-lookup"><span data-stu-id="efb7a-116">Oracle BFILEs</span></span>](oracle-bfiles.md)  
 <span data-ttu-id="efb7a-117">Описывает класс <xref:System.Data.OracleClient.OracleBFile>, который используется для работы с типом данных Oracle BFILE.</span><span class="sxs-lookup"><span data-stu-id="efb7a-117">Describes the <xref:System.Data.OracleClient.OracleBFile> class, which is used to work with the Oracle BFILE data type.</span></span>  
  
 [<span data-ttu-id="efb7a-118">Большие двоичные объекты (LOB) Oracle</span><span class="sxs-lookup"><span data-stu-id="efb7a-118">Oracle LOBs</span></span>](oracle-lobs.md)  
 <span data-ttu-id="efb7a-119">Описывает класс <xref:System.Data.OracleClient.OracleLob>, который используется для работы с типом данных Oracle LOB.</span><span class="sxs-lookup"><span data-stu-id="efb7a-119">Describes the <xref:System.Data.OracleClient.OracleLob> class, which is used to work with Oracle LOB data types.</span></span>  
  
 [<span data-ttu-id="efb7a-120">REF CURSOR в Oracle</span><span class="sxs-lookup"><span data-stu-id="efb7a-120">Oracle REF CURSORs</span></span>](oracle-ref-cursors.md)  
 <span data-ttu-id="efb7a-121">Описывает поддержку для типа данных Oracle REF CURSOR.</span><span class="sxs-lookup"><span data-stu-id="efb7a-121">Describes support for the Oracle REF CURSOR data type.</span></span>  
  
 [<span data-ttu-id="efb7a-122">OracleTypes</span><span class="sxs-lookup"><span data-stu-id="efb7a-122">OracleTypes</span></span>](oracletypes.md)  
 <span data-ttu-id="efb7a-123">Описывает структуры, которые можно использовать с типами данных Oracle, включая <xref:System.Data.OracleClient.OracleNumber> и <xref:System.Data.OracleClient.OracleString>.</span><span class="sxs-lookup"><span data-stu-id="efb7a-123">Describes structures you can use to work with Oracle data types, including <xref:System.Data.OracleClient.OracleNumber> and <xref:System.Data.OracleClient.OracleString>.</span></span>  
  
 [<span data-ttu-id="efb7a-124">Последовательности Oracle</span><span class="sxs-lookup"><span data-stu-id="efb7a-124">Oracle Sequences</span></span>](oracle-sequences.md)  
 <span data-ttu-id="efb7a-125">Описывает поддержку получения сформированного сервером ключа значений Oracle Sequence.</span><span class="sxs-lookup"><span data-stu-id="efb7a-125">Describes support for retrieving the server-generated key Oracle Sequence values.</span></span>  
  
 [<span data-ttu-id="efb7a-126">Сопоставления типов данных Oracle</span><span class="sxs-lookup"><span data-stu-id="efb7a-126">Oracle Data Type Mappings</span></span>](oracle-data-type-mappings.md)  
 <span data-ttu-id="efb7a-127">Перечисляет типы данных Oracle и их сопоставление с объектом <xref:System.Data.OracleClient.OracleDataReader>.</span><span class="sxs-lookup"><span data-stu-id="efb7a-127">Lists Oracle data types and their mappings to the <xref:System.Data.OracleClient.OracleDataReader>.</span></span>  
  
 [<span data-ttu-id="efb7a-128">Распределенные транзакции Oracle</span><span class="sxs-lookup"><span data-stu-id="efb7a-128">Oracle Distributed Transactions</span></span>](oracle-distributed-transactions.md)  
 <span data-ttu-id="efb7a-129">Описывает автоматическое прикрепление объекта <xref:System.Data.OracleClient.OracleConnection> к существующей распределенной транзакции, если эта транзакция активна.</span><span class="sxs-lookup"><span data-stu-id="efb7a-129">Describes how the <xref:System.Data.OracleClient.OracleConnection> object automatically enlists in an existing distributed transaction if it determines that a transaction is active.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="efb7a-130">См. также</span><span class="sxs-lookup"><span data-stu-id="efb7a-130">Related Sections</span></span>  

 [<span data-ttu-id="efb7a-131">Защита приложений ADO.NET</span><span class="sxs-lookup"><span data-stu-id="efb7a-131">Securing ADO.NET Applications</span></span>](securing-ado-net-applications.md)  
 <span data-ttu-id="efb7a-132">Описывает приемы безопасного программирования при использовании ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="efb7a-132">Describes secure coding practices when using ADO.NET.</span></span>  
  
 [<span data-ttu-id="efb7a-133">Наборы данных, таблицы данных и объекты DataView</span><span class="sxs-lookup"><span data-stu-id="efb7a-133">DataSets, DataTables, and DataViews</span></span>](./dataset-datatable-dataview/index.md)  
 <span data-ttu-id="efb7a-134">Описывает процесс создания и использования объектов `DataSets`, типизированных объектов `DataSets`, а также объектов `DataTables` и `DataViews`.</span><span class="sxs-lookup"><span data-stu-id="efb7a-134">Describes how to create and use `DataSets`, typed `DataSets`, `DataTables`, and `DataViews`.</span></span>  
  
 [<span data-ttu-id="efb7a-135">Извлечение и изменение данных в ADO.NET</span><span class="sxs-lookup"><span data-stu-id="efb7a-135">Retrieving and Modifying Data in ADO.NET</span></span>](retrieving-and-modifying-data.md)  
 <span data-ttu-id="efb7a-136">Описывает работу с данными в ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="efb7a-136">Describes how to work with data in ADO.NET.</span></span>  
  
 [<span data-ttu-id="efb7a-137">SQL Server и ADO.NET</span><span class="sxs-lookup"><span data-stu-id="efb7a-137">SQL Server and ADO.NET</span></span>](./sql/index.md)  
 <span data-ttu-id="efb7a-138">Описывает процесс работы со специальными возможностями и функциями SQL Server.</span><span class="sxs-lookup"><span data-stu-id="efb7a-138">Describes how to work with features and functionality that are specific to SQL Server.</span></span>  
  
 [<span data-ttu-id="efb7a-139">DbProviderFactories</span><span class="sxs-lookup"><span data-stu-id="efb7a-139">DbProviderFactories</span></span>](dbproviderfactories.md)  
 <span data-ttu-id="efb7a-140">Описывает универсальные классы, позволяющие писать независимый от поставщика код в ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="efb7a-140">Describes generic classes that allow you to write provider-independent code in ADO.NET.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efb7a-141">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="efb7a-141">See also</span></span>

- [<span data-ttu-id="efb7a-142">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="efb7a-142">ADO.NET</span></span>](index.md)
- [<span data-ttu-id="efb7a-143">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="efb7a-143">ADO.NET Overview</span></span>](ado-net-overview.md)
