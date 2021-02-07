---
description: 'Дополнительные сведения: схемы и коллекции схем'
title: Коллекции GetSchema и Schema
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7ab93b89-1221-427c-84ad-04803b3c64b4
ms.openlocfilehash: 2b085435f0f9ea9ec33897ee417cd7a726c4503d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99723989"
---
# <a name="getschema-and-schema-collections"></a>Коллекции GetSchema и Schema

Классы **Connection** в каждом из управляемых поставщиков платформа .NET Framework реализуют метод **GetSchema** , который используется для получения сведений о схеме базы данных, подключенной в данный момент, а сведения о схеме, возвращаемые методом **GetSchema** , поступают в виде <xref:System.Data.DataTable> . **GetSchema** — перегружаемый метод, содержащий необязательные параметры для указания возвращаемой коллекции схем и ограничения объема возвращаемых сведений.  
  
## <a name="specifying-the-schema-collections"></a>Указание коллекций схем  

 Первым необязательным параметром метода **GetSchema** является имя коллекции, указанное в виде строки. Существует два типа коллекций схем: стандартные (общие для всех поставщиков) и специальные (определенные для каждого поставщика).  
  
 Можно запросить управляемый поставщик платформа .NET Framework, чтобы определить список поддерживаемых коллекций схем, вызвав метод **GetSchema** без аргументов или с именем коллекции схем «MetaDataCollections». При этом будет возвращена <xref:System.Data.DataTable> со списком поддерживаемых коллекций схем, число ограничений, которые каждая из них поддерживает, и число идентификационных частей, которые в них используются.  
  
### <a name="retrieving-schema-collections-example"></a>Получение примера коллекций схем  

 В следующих примерах показано, как использовать <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> метод поставщика данных платформа .NET Framework для класса SQL Server, <xref:System.Data.SqlClient.SqlConnection> чтобы получить сведения о схеме всех таблиц, содержащихся в образце базы данных **AdventureWorks** :  
  
```vb  
Imports System.Data.SqlClient  
  
Module Module1  
   Sub Main()  
      Dim connectionString As String = GetConnectionString()  
      Using connection As New SqlConnection(connectionString)  
         'Connect to the database then retrieve the schema information.  
         connection.Open()  
         Dim table As DataTable = connection.GetSchema("Tables")  
  
         ' Display the contents of the table.  
         DisplayData(table)  
         Console.WriteLine("Press any key to continue.")  
         Console.ReadKey()  
      End Using  
   End Sub  
  
   Private Function GetConnectionString() As String  
      ' To avoid storing the connection string in your code,
      ' you can retrieve it from a configuration file.  
      Return "Data Source=(local);Database=AdventureWorks;" _  
         & "Integrated Security=true;"  
   End Function  
  
   Private Sub DisplayData(ByVal table As DataTable)  
      For Each row As DataRow In table.Rows  
         For Each col As DataColumn In table.Columns  
            Console.WriteLine("{0} = {1}", col.ColumnName, row(col))  
         Next  
         Console.WriteLine("============================")  
      Next  
   End Sub  
End Module  
```  
  
```csharp  
using System;  
using System.Data;  
using System.Data.SqlClient;  
  
class Program  
{  
  static void Main()  
  {  
  string connectionString = GetConnectionString();  
  using (SqlConnection connection = new SqlConnection(connectionString))  
  {  
   // Connect to the database then retrieve the schema information.  
   connection.Open();  
   DataTable table = connection.GetSchema("Tables");  
  
   // Display the contents of the table.  
   DisplayData(table);  
   Console.WriteLine("Press any key to continue.");  
   Console.ReadKey();  
   }  
 }  
  
  private static string GetConnectionString()  
  {  
   // To avoid storing the connection string in your code,  
   // you can retrieve it from a configuration file.  
   return "Data Source=(local);Database=AdventureWorks;" +  
      "Integrated Security=true;";  
  }  
  
  private static void DisplayData(System.Data.DataTable table)  
  {  
     foreach (System.Data.DataRow row in table.Rows)  
     {  
        foreach (System.Data.DataColumn col in table.Columns)  
        {  
           Console.WriteLine("{0} = {1}", col.ColumnName, row[col]);  
        }  
     Console.WriteLine("============================");  
     }  
  }  
}  
```  
  
## <a name="see-also"></a>См. также раздел

- [Извлечение сведений о схеме базы данных](retrieving-database-schema-information.md)
- [Общие сведения об ADO.NET](ado-net-overview.md)
