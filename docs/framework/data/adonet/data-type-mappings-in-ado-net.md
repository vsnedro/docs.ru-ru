---
title: Сопоставление типов данных
ms.date: 03/30/2017
ms.assetid: d4afab94-ada6-4c77-a73c-41f17bae6b5a
ms.openlocfilehash: 52e64714a17448cd94723bdc216d8ea069fc5eef
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177752"
---
# <a name="data-type-mappings-in-adonet"></a><span data-ttu-id="8f37a-102">Сопоставления типов данных в ADO.NET</span><span class="sxs-lookup"><span data-stu-id="8f37a-102">Data Type Mappings in ADO.NET</span></span>

<span data-ttu-id="8f37a-103">Платформа .NET Framework основана на общей системе типов, в которой определяются способы объявления, использования типов и управления ими во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="8f37a-103">The .NET Framework is based on the common type system, which defines how types are declared, used, and managed in the runtime.</span></span> <span data-ttu-id="8f37a-104">Система типов состоит из типов-значений и типов-ссылок, производных от базового типа <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="8f37a-104">It consists of both value types and reference types, which all derive from the <xref:System.Object> base type.</span></span> <span data-ttu-id="8f37a-105">При работе с источником данных не указанный явным образом тип данных выводится из поставщика данных.</span><span class="sxs-lookup"><span data-stu-id="8f37a-105">When working with a data source, the data type is inferred from the data provider if it is not explicitly specified.</span></span> <span data-ttu-id="8f37a-106">Например, объект <xref:System.Data.DataSet> не зависит ни от одного конкретного источника данных.</span><span class="sxs-lookup"><span data-stu-id="8f37a-106">For example, a <xref:System.Data.DataSet> object is independent of any specific data source.</span></span> <span data-ttu-id="8f37a-107">Получение данных в `DataSet` осуществляется из источника данных, а изменения передаются для сохранения в источнике данных с использованием `DataAdapter`.</span><span class="sxs-lookup"><span data-stu-id="8f37a-107">Data in a `DataSet` is retrieved from a data source, and changes are persisted back to the data source by using a `DataAdapter`.</span></span> <span data-ttu-id="8f37a-108">Это означает, что при `DataAdapter` заполнении <xref:System.Data.DataTable> в `DataSet` со значениями из источника данных результирующие типы данных столбцов в `DataTable` являются .NET Framework типами, а не типами, характерными для .NET Frameworkного поставщика данных, используемого для подключения к источнику данных.</span><span class="sxs-lookup"><span data-stu-id="8f37a-108">This means that when a `DataAdapter` fills a <xref:System.Data.DataTable> in a `DataSet` with values from a data source, the resulting data types of the columns in the `DataTable` are .NET Framework types, instead of types specific to the .NET Framework data provider that is used to connect to the data source.</span></span>  
  
 <span data-ttu-id="8f37a-109">Аналогично, когда объект `DataReader` возвращает значение из источника данных, полученное значение сохраняется в локальной переменной, имеющей тип .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8f37a-109">Likewise, when a `DataReader` returns a value from a data source, the resulting value is stored in a local variable that has a .NET Framework type.</span></span> <span data-ttu-id="8f37a-110">Как для операций, так `Fill` `DataAdapter` и для `Get` методов `DataReader` , тип .NET Framework выводится из значения, возвращаемого поставщиком данных .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8f37a-110">For both the `Fill` operations of the `DataAdapter` and the `Get` methods of the `DataReader`, the .NET Framework type is inferred from the value returned from the .NET Framework data provider.</span></span>  
  
 <span data-ttu-id="8f37a-111">Если известен тип возвращаемого значения, то вместо выводимого типа данных можно воспользоваться типизированными методами доступа объекта `DataReader`.</span><span class="sxs-lookup"><span data-stu-id="8f37a-111">Instead of relying on the inferred data type, you can use the typed accessor methods of the `DataReader` when you know the specific type of the value being returned.</span></span> <span data-ttu-id="8f37a-112">Типизированные методы доступа обеспечивают лучшую производительность, возвращая значение как конкретный тип .NET Framework, что устраняет необходимость в дополнительном преобразовании типов.</span><span class="sxs-lookup"><span data-stu-id="8f37a-112">Typed accessor methods give you better performance by returning a value as a specific .NET Framework type, which eliminates the need for additional type conversion.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8f37a-113">Значения NULL для типов данных поставщика данных .NET Framework представлены в `DBNull.Value` .</span><span class="sxs-lookup"><span data-stu-id="8f37a-113">Null values for .NET Framework data provider data types are represented by `DBNull.Value`.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8f37a-114">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="8f37a-114">In This Section</span></span>  

 [<span data-ttu-id="8f37a-115">Сопоставления типов данных SQL Server</span><span class="sxs-lookup"><span data-stu-id="8f37a-115">SQL Server Data Type Mappings</span></span>](sql-server-data-type-mappings.md)  
 <span data-ttu-id="8f37a-116">Выводит список сопоставлений выводимых типов данных и методов доступа к данным для объекта <xref:System.Data.SqlClient>.</span><span class="sxs-lookup"><span data-stu-id="8f37a-116">Lists inferred data type mappings and data accessor methods for <xref:System.Data.SqlClient>.</span></span>  
  
 [<span data-ttu-id="8f37a-117">Сопоставления типов данных OLE DB</span><span class="sxs-lookup"><span data-stu-id="8f37a-117">OLE DB Data Type Mappings</span></span>](ole-db-data-type-mappings.md)  
 <span data-ttu-id="8f37a-118">Выводит список сопоставлений выводимых типов данных и методов доступа к данным для объекта <xref:System.Data.OleDb>.</span><span class="sxs-lookup"><span data-stu-id="8f37a-118">Lists inferred data type mappings and data accessor methods for <xref:System.Data.OleDb>.</span></span>  
  
 [<span data-ttu-id="8f37a-119">Сопоставления типов данных ODBC</span><span class="sxs-lookup"><span data-stu-id="8f37a-119">ODBC Data Type Mappings</span></span>](odbc-data-type-mappings.md)  
 <span data-ttu-id="8f37a-120">Выводит список сопоставлений выводимых типов данных и методов доступа к данным для объекта <xref:System.Data.Odbc>.</span><span class="sxs-lookup"><span data-stu-id="8f37a-120">Lists inferred data type mappings and data accessor methods for <xref:System.Data.Odbc>.</span></span>  
  
 [<span data-ttu-id="8f37a-121">Сопоставления типов данных Oracle</span><span class="sxs-lookup"><span data-stu-id="8f37a-121">Oracle Data Type Mappings</span></span>](oracle-data-type-mappings.md)  
 <span data-ttu-id="8f37a-122">Выводит список сопоставлений выводимых типов данных и методов доступа к данным для объекта <xref:System.Data.OracleClient>.</span><span class="sxs-lookup"><span data-stu-id="8f37a-122">Lists inferred data type mappings and data accessor methods for <xref:System.Data.OracleClient>.</span></span>  
  
 [<span data-ttu-id="8f37a-123">Числа с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="8f37a-123">Floating-Point Numbers</span></span>](floating-point-numbers.md)  
 <span data-ttu-id="8f37a-124">Описывает проблемы, с которыми разработчики часто сталкиваются при работе с числами с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="8f37a-124">Describes issues that developers frequently encounter when working with floating-point numbers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f37a-125">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="8f37a-125">See also</span></span>

- [<span data-ttu-id="8f37a-126">Типы данных SQL Server и ADO.NET</span><span class="sxs-lookup"><span data-stu-id="8f37a-126">SQL Server Data Types and ADO.NET</span></span>](./sql/sql-server-data-types.md)
- [<span data-ttu-id="8f37a-127">Настройка параметров и типы данных параметров</span><span class="sxs-lookup"><span data-stu-id="8f37a-127">Configuring Parameters and Parameter Data Types</span></span>](configuring-parameters-and-parameter-data-types.md)
- [<span data-ttu-id="8f37a-128">Извлечение сведений о схеме базы данных</span><span class="sxs-lookup"><span data-stu-id="8f37a-128">Retrieving Database Schema Information</span></span>](retrieving-database-schema-information.md)
- [<span data-ttu-id="8f37a-129">Система общих типов CTS</span><span class="sxs-lookup"><span data-stu-id="8f37a-129">Common Type System</span></span>](../../../standard/base-types/common-type-system.md)
- <span data-ttu-id="8f37a-130">[Преобразование типов](/previous-versions/visualstudio/visual-studio-2008/t8s7t9bf(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="8f37a-130">[Converting Types](/previous-versions/visualstudio/visual-studio-2008/t8s7t9bf(v=vs.90))</span></span>
- [<span data-ttu-id="8f37a-131">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="8f37a-131">ADO.NET Overview</span></span>](ado-net-overview.md)
