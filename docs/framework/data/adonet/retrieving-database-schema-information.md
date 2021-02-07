---
description: 'Дополнительные сведения: получение сведений о схеме базы данных'
title: Извлечение сведений о схеме базы данных
ms.date: 03/30/2017
ms.assetid: 79038d52-f122-4fd4-9bfb-aaa22d6a114b
ms.openlocfilehash: 84ac94a72b23d0b1d6924600f2fd33b2a285eab8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99663408"
---
# <a name="retrieving-database-schema-information"></a>Извлечение сведений о схеме базы данных

Получение сведений о схеме из базы данных выполняется с помощью процесса обнаружения схемы. Обнаружение схемы позволяет приложениям запрашивать управляемые поставщики для поиска и возвращения сведений о схеме базы данных, также называемых *метаданными*, для данной базы данных. Различные элементы схемы базы данных, например таблицы, столбцы и хранимые процедуры, предоставляются через коллекции схем. Каждая коллекция схемы в зависимости от используемого поставщика содержит различные сведения о схеме.  
  
 Каждый из платформа .NET Framework управляемых поставщиков реализует метод **GetSchema** в классе **Connection** , а сведения о схеме, возвращаемые методом **GetSchema** , поступают в виде <xref:System.Data.DataTable> . **GetSchema** — перегружаемый метод, содержащий необязательные параметры для указания возвращаемой коллекции схем и ограничения объема возвращаемых сведений.  
  
 Поставщики данных платформа .NET Framework для OLE DB, ODBC, Oracle и SqlClient предоставляют метод **GetSchemaTable** , возвращающий объект DataTable, описывающий метаданные столбца для **DataReader**.  
  
 Поставщик данных .NET Framework для OLE DB также предоставляет данные схемы с помощью метода <xref:System.Data.OleDb.OleDbConnection.GetOleDbSchemaTable%2A> объекта <xref:System.Data.OleDb.OleDbConnection>. В качестве аргументов **жетоледбсчематабле** принимает <xref:System.Data.OleDb.OleDbSchemaGuid> , определяющий возвращаемую информацию о схеме, и массив ограничений на возвращаемые столбцы. **Жетоледбсчематабле** возвращает <xref:System.Data.DataTable> заполненную информацию о запрашиваемой схеме.  
  
## <a name="in-this-section"></a>В этом разделе  

 [Метод GetSchema и коллекции схем](getschema-and-schema-collections.md)  
 Описание метода **GetSchema** и его использования для получения и ограничения сведений о схеме из базы данных.  
  
 Ограничения схемы  
 Описание ограничений схемы, которые можно использовать с методом **GetSchema**.  
  
 [Общие коллекции схем](common-schema-collections.md)  
 Описывает стандартные коллекции схем, поддерживаемые всеми управляемыми поставщиками .NET Framework.  
  
 [SQL Server коллекции схем](sql-server-schema-collections.md)  
 Описывается коллекция схем, поддерживаемая поставщиком .NET Framework для SQL Server.  
  
 [Коллекции схемы в Oracle](oracle-schema-collections.md)  
 Описывается коллекция схем, поддерживаемая поставщиком .NET Framework для Oracle.  
  
 [Коллекции схемы ODBC](odbc-schema-collections.md)  
 Описываются коллекции схем для драйверов ODBC.  
  
 [Коллекции схемы OLE DB](ole-db-schema-collections.md)  
 Описываются коллекции схем для поставщиков OLE DB.  
  
## <a name="reference"></a>Справочник  

 <xref:System.Data.Common.DbConnection.GetSchema%2A>  
 Описание метода **GetSchema** класса <xref:System.Data.Common.DbConnection>.  
  
 <xref:System.Data.Odbc.OdbcConnection.GetSchema%2A>  
 Описание метода **GetSchema** класса <xref:System.Data.Odbc.OdbcConnection>.  
  
 <xref:System.Data.OleDb.OleDbConnection.GetSchema%2A>  
 Описание метода **GetSchema** класса <xref:System.Data.OleDb.OleDbConnection>.  
  
 <xref:System.Data.OracleClient.OracleConnection.GetSchema%2A>  
 Описание метода **GetSchema** класса <xref:System.Data.OracleClient.OracleConnection>.  
  
 <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A>  
 Описание метода **GetSchema** класса <xref:System.Data.SqlClient.SqlConnection>.  
  
 <xref:System.Data.Common.DbDataReader.GetSchemaTable%2A>  
 Описание метода **GetSchemaTable** класса <xref:System.Data.Common.DbDataReader>.  
  
 <xref:System.Data.Odbc.OdbcDataReader.GetSchemaTable%2A>  
 Описание метода **GetSchemaTable** класса <xref:System.Data.Odbc.OdbcDataReader>.  
  
 <xref:System.Data.OleDb.OleDbDataReader.GetSchemaTable%2A>  
 Описание метода **GetSchemaTable** класса <xref:System.Data.OleDb.OleDbDataReader>.  
  
 <xref:System.Data.OracleClient.OracleDataReader.GetSchemaTable%2A>  
 Описание метода **GetSchemaTable** класса <xref:System.Data.OracleClient.OracleDataReader>.  
  
 <xref:System.Data.SqlClient.SqlDataReader.GetSchemaTable%2A>  
 Описание метода **GetSchemaTable** класса <xref:System.Data.SqlClient.SqlDataReader>.  
  
## <a name="see-also"></a>См. также

- [Извлечение и изменение данных в ADO.NET](retrieving-and-modifying-data.md)
- [Общие сведения об ADO.NET](ado-net-overview.md)
