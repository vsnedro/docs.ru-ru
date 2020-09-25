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
# <a name="retrieving-database-schema-information"></a>Извлечение сведений о схеме базы данных

Получение сведений о схеме из базы данных выполняется с помощью процесса обнаружения схемы. Обнаружение схемы позволяет приложениям запрашивать, что управляемые поставщики находят и возвращают сведения о схеме базы данных, также известные как *метаданные*заданной базы данных. Различные элементы схемы базы данных, например таблицы, столбцы и хранимые процедуры, предоставляются через коллекции схем. Каждая коллекция схемы в зависимости от используемого поставщика содержит различные сведения о схеме.  
  
 Каждый из .NET Framework управляемых поставщиков реализует метод **GetSchema** в классе **Connection** , а сведения о схеме, возвращаемые методом **GetSchema** , поступают в виде <xref:System.Data.DataTable> . Метод **GetSchema** является перегруженным методом, который предоставляет необязательные параметры для указания возвращаемой коллекции схем и ограниченный объем возвращаемой информации.  
  
 Поставщики данных .NET Framework для OLE DB, ODBC, Oracle и SqlClient предоставляют метод **GetSchemaTable** , возвращающий объект DataTable, описывающий метаданные столбца для **DataReader**.  
  
 Поставщик данных .NET Framework для OLE DB также предоставляет данные схемы с помощью метода <xref:System.Data.OleDb.OleDbConnection.GetOleDbSchemaTable%2A> объекта <xref:System.Data.OleDb.OleDbConnection>. В качестве аргументов **жетоледбсчематабле** принимает <xref:System.Data.OleDb.OleDbSchemaGuid> , определяющий возвращаемую информацию о схеме, и массив ограничений на возвращаемые столбцы. **Жетоледбсчематабле** возвращает <xref:System.Data.DataTable> заполненную информацию о запрашиваемой схеме.  
  
## <a name="in-this-section"></a>в этом разделе  

 [Коллекции GetSchema и Schema](getschema-and-schema-collections.md)  
 Описывает метод **GetSchema** и способ его использования для извлечения и ограничения сведений о схеме из базы данных.  
  
 Ограничения схемы  
 Описывает ограничения схемы, которые можно использовать с **GetSchema**.  
  
 [Общие коллекции схемы](common-schema-collections.md)  
 Описывает стандартные коллекции схем, поддерживаемые всеми управляемыми поставщиками .NET Framework.  
  
 [Коллекции схемы SQL Server](sql-server-schema-collections.md)  
 Описывается коллекция схем, поддерживаемая поставщиком .NET Framework для SQL Server.  
  
 [Коллекции схемы в Oracle](oracle-schema-collections.md)  
 Описывается коллекция схем, поддерживаемая поставщиком .NET Framework для Oracle.  
  
 [Коллекции схемы ODBC](odbc-schema-collections.md)  
 Описываются коллекции схем для драйверов ODBC.  
  
 [Коллекции схемы OLE DB](ole-db-schema-collections.md)  
 Описываются коллекции схем для поставщиков OLE DB.  
  
## <a name="reference"></a>Справка  

 <xref:System.Data.Common.DbConnection.GetSchema%2A>  
 Описывает метод **GetSchema** <xref:System.Data.Common.DbConnection> класса.  
  
 <xref:System.Data.Odbc.OdbcConnection.GetSchema%2A>  
 Описывает метод **GetSchema** <xref:System.Data.Odbc.OdbcConnection> класса.  
  
 <xref:System.Data.OleDb.OleDbConnection.GetSchema%2A>  
 Описывает метод **GetSchema** <xref:System.Data.OleDb.OleDbConnection> класса.  
  
 <xref:System.Data.OracleClient.OracleConnection.GetSchema%2A>  
 Описывает метод **GetSchema** <xref:System.Data.OracleClient.OracleConnection> класса.  
  
 <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A>  
 Описывает метод **GetSchema** <xref:System.Data.SqlClient.SqlConnection> класса.  
  
 <xref:System.Data.Common.DbDataReader.GetSchemaTable%2A>  
 Описывает метод **GetSchemaTable** <xref:System.Data.Common.DbDataReader> класса.  
  
 <xref:System.Data.Odbc.OdbcDataReader.GetSchemaTable%2A>  
 Описывает метод **GetSchemaTable** <xref:System.Data.Odbc.OdbcDataReader> класса.  
  
 <xref:System.Data.OleDb.OleDbDataReader.GetSchemaTable%2A>  
 Описывает метод **GetSchemaTable** <xref:System.Data.OleDb.OleDbDataReader> класса.  
  
 <xref:System.Data.OracleClient.OracleDataReader.GetSchemaTable%2A>  
 Описывает метод **GetSchemaTable** <xref:System.Data.OracleClient.OracleDataReader> класса.  
  
 <xref:System.Data.SqlClient.SqlDataReader.GetSchemaTable%2A>  
 Описывает метод **GetSchemaTable** <xref:System.Data.SqlClient.SqlDataReader> класса.  
  
## <a name="see-also"></a>См. также раздел

- [Извлечение и изменение данных в ADO.NET](retrieving-and-modifying-data.md)
- [Общие сведения об ADO.NET](ado-net-overview.md)
