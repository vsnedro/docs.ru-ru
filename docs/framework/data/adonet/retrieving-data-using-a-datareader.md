---
title: Извлечение данных с помощью объекта DataReader
description: Узнайте, как получить данные с помощью средства чтения данных в ADO.NET с помощью этого примера кода. DataReader предоставляет небуферизованный поток данных.
ms.date: 10/29/2018
dev_langs:
- csharp
- vb
ms.assetid: 97afc121-fb8b-465b-bab3-6d844420badb
ms.openlocfilehash: 6e5161cc325bf0379bb9241b99c473c539ad1081
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286602"
---
# <a name="retrieve-data-using-a-datareader"></a>Извлечение данных с помощью объекта DataReader
Чтобы получить данные с помощью **DataReader**, создайте экземпляр объекта **Command** , а затем создайте объект **DataReader** , вызвав **Command. ExecuteReader** , чтобы получить строки из источника данных. **DataReader** предоставляет небуферизованный поток данных, позволяющий процедурной логике эффективно обрабатывать результаты из источника данных. **DataReader** является хорошим выбором при извлечении больших объемов данных, поскольку данные не кэшируются в памяти.

В следующем примере показано использование **DataReader**, где `reader` представляет допустимый DataReader и `command` представляет допустимый объект команды.  

```csharp
reader = command.ExecuteReader();  
```

```vb
reader = command.ExecuteReader()
```  

Используйте метод **DataReader. Read** для получения строки из результатов запроса. Доступ к каждому столбцу возвращаемой строки можно получить, передав имя или порядковый номер столбца в **DataReader**. Однако для лучшей производительности **DataReader** предоставляет ряд методов, позволяющих получить доступ к значениям столбцов в собственных типах данных (типы**DateTime**, **double** **, DataColumn,** **Int32**и т. д.). Список типизированных методов доступа для **DataReader**, относящихся к поставщику данных, см <xref:System.Data.OleDb.OleDbDataReader> . в разделе и <xref:System.Data.SqlClient.SqlDataReader> . Использование типизированных методов доступа, если известно, что базовый тип данных сокращает объем преобразования типа, необходимый при извлечении значения столбца.  
  
 В следующем примере выполняется итерация объекта **DataReader** и возвращаются два столбца из каждой строки.  
  
 [!code-csharp[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/VB/source.vb#1)]  
  
## <a name="closing-the-datareader"></a>Закрытие DataReader  
 Всегда вызывайте метод **Close** после завершения использования объекта **DataReader** .  
  
 Если **команда** содержит выходные параметры или возвращаемые значения, эти значения недоступны до закрытия **DataReader** .  
  
 Когда **DataReader** открыт, **соединение** используется исключительно этим объектом **DataReader**. Нельзя выполнять команды для **соединения**, включая создание другого **DataReader**, пока не будет закрыт исходный **DataReader** .  
  
> [!NOTE]
> Не вызывайте **Close** или **Dispose** для **соединения**, **DataReader**или любого другого управляемого объекта в методе **Finalize** вашего класса. В методе завершения следует только освобождать неуправляемые ресурсы, которыми ваш класс непосредственно владеет. Если ваш класс не владеет какими-либо неуправляемыми ресурсами, не включайте метод **Finalize** в определение класса. Дополнительные сведения см. в разделе [сборка мусора](../../../standard/garbage-collection/index.md).  
  
## <a name="retrieving-multiple-result-sets-using-nextresult"></a>Получение нескольких результирующих наборов с помощью Некстресулт  
 Если **DataReader** возвращает несколько результирующих наборов, вызовите метод **некстресулт** для последовательного прохода по результирующим наборам. В следующем примере показан объект <xref:System.Data.SqlClient.SqlDataReader>, обрабатывающий результаты двух инструкций SELECT с помощью метода <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A>.  
  
 [!code-csharp[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/VB/source.vb#1)]  
  
## <a name="getting-schema-information-from-the-datareader"></a>Получение сведений о схеме из DataReader  
 Когда **DataReader** открыт, можно получить сведения о схеме текущего результирующего набора с помощью метода **GetSchemaTable** . **GetSchemaTable** возвращает <xref:System.Data.DataTable> объект, заполненный строками и столбцами, содержащими сведения о схеме для текущего результирующего набора. Объект **DataTable** содержит по одной строке для каждого столбца результирующего набора. Каждый столбец таблицы схемы сопоставляется со свойством столбцов, возвращаемых строками результирующего набора, где **ColumnName** является именем свойства, а значение столбца — значением свойства. В следующем примере записывается информация о схеме для **DataReader**.  
  
 [!code-csharp[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/VB/source.vb#1)]  
  
## <a name="working-with-ole-db-chapters"></a>Работа с OLE DB главами  
 Иерархические наборы строк или главы (тип OLE DB **DBTYPE_HCHAPTER**, тип ADO **адчаптер**) можно получить с помощью <xref:System.Data.OleDb.OleDbDataReader> . Если запрос, включающий главу, возвращается в виде объекта **DataReader**, то эта глава возвращается в виде столбца в объекте **DataReader** и предоставляется как объект **DataReader** .  
  
 **Набор данных** ADO.NET также можно использовать для представления иерархических наборов строк с помощью связей типа «родители-потомки» между таблицами. Дополнительные сведения см. в разделе [наборы данных, DataTables и DataSets](./dataset-datatable-dataview/index.md).  
  
 В следующем примере кода поставщик MSDataShape используется, чтобы сформировать столбец раздела заказов по каждому клиенту из списка клиентов.  
  
```vb  
Using connection As OleDbConnection = New OleDbConnection(
    "Provider=MSDataShape;Data Provider=SQLOLEDB;" &
    "Data Source=localhost;Integrated Security=SSPI;Initial Catalog=northwind")

    Using custCMD As OleDbCommand = New OleDbCommand(
        "SHAPE {SELECT CustomerID, CompanyName FROM Customers} " &
        "APPEND ({SELECT CustomerID, OrderID FROM Orders} AS CustomerOrders " &
        "RELATE CustomerID TO CustomerID)", connection)

        connection.Open()

        Using custReader As OleDbDataReader = custCMD.ExecuteReader()

            Do While custReader.Read()
                Console.WriteLine("Orders for " & custReader.GetString(1))
                ' custReader.GetString(1) = CompanyName  

                Using orderReader As OleDbDataReader = custReader.GetValue(2)
                    ' custReader.GetValue(2) = Orders chapter as DataReader  

                    Do While orderReader.Read()
                        Console.WriteLine(vbTab & orderReader.GetInt32(1))
                        ' orderReader.GetInt32(1) = OrderID  
                    Loop
                    orderReader.Close()
                End Using
            Loop
            ' Make sure to always close readers and connections.  
            custReader.Close()
        End Using
    End Using
End Using
```  
  
```csharp  
using (OleDbConnection connection = new OleDbConnection(
    "Provider=MSDataShape;Data Provider=SQLOLEDB;" +
    "Data Source=localhost;Integrated Security=SSPI;Initial Catalog=northwind"))
{
    using (OleDbCommand custCMD = new OleDbCommand(
        "SHAPE {SELECT CustomerID, CompanyName FROM Customers} " +
        "APPEND ({SELECT CustomerID, OrderID FROM Orders} AS CustomerOrders " +
        "RELATE CustomerID TO CustomerID)", connection))
    {
        connection.Open();

        using (OleDbDataReader custReader = custCMD.ExecuteReader())
        {

            while (custReader.Read())
            {
                Console.WriteLine("Orders for " + custReader.GetString(1));
                // custReader.GetString(1) = CompanyName  

                using (OleDbDataReader orderReader = (OleDbDataReader)custReader.GetValue(2))
                {
                    // custReader.GetValue(2) = Orders chapter as DataReader  

                    while (orderReader.Read())
                        Console.WriteLine("\t" + orderReader.GetInt32(1));
                    // orderReader.GetInt32(1) = OrderID  
                    orderReader.Close();
                }
            }
            // Make sure to always close readers and connections.  
            custReader.Close();
        }
    }
}
```  
  
## <a name="returning-results-with-oracle-ref-cursors"></a>Возврат результатов с КУРСОРами Oracle REF  
 Поставщик данных .NET Framework для Oracle поддерживает использование параметров Oracle REF CURSOR для возвращения результата запроса. Параметр Oracle REF CURSOR возвращается в виде объекта <xref:System.Data.OracleClient.OracleDataReader>.  
  
 <xref:System.Data.OracleClient.OracleDataReader>Объект, представляющий курсор Oracle ref, можно получить с помощью <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A> метода. Можно также указать <xref:System.Data.OracleClient.OracleCommand> , возвращающий один или несколько курсоров Oracle ref в качестве **SelectCommand** для, <xref:System.Data.OracleClient.OracleDataAdapter> используемого для заполнения <xref:System.Data.DataSet> .  
  
 Чтобы получить доступ к КУРСОРу REF, возвращенному из источника данных Oracle, создайте <xref:System.Data.OracleClient.OracleCommand> для запроса и добавьте выходной параметр, который ссылается на ссылочный курсор, в <xref:System.Data.OracleClient.OracleCommand.Parameters> коллекцию <xref:System.Data.OracleClient.OracleCommand> . Имя параметра должно соответствовать имени параметра REF CURSOR, используемого в запросе. Задайте для параметра Тип значение <xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType> . <xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType>Метод <xref:System.Data.OracleClient.OracleCommand> ВОЗВРАЩАЕТ <xref:System.Data.OracleClient.OracleDataReader> для курсора ref.  
  
 Если функция <xref:System.Data.OracleClient.OracleCommand> возвращает несколько курсоров ref, добавьте несколько выходных параметров. Чтобы получить доступ к разным КУРСОРам REF, вызовите <xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType> метод. Вызов метода <xref:System.Data.OracleClient.OracleCommand.ExecuteReader> возвращает ссылку на <xref:System.Data.OracleClient.OracleDataReader> первый курсор ref. Затем можно вызвать <xref:System.Data.OracleClient.OracleDataReader.NextResult?displayProperty=nameWithType> метод для доступа к последовательным курсорам ref. Хотя параметры в <xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType> коллекции соответствуют выходным параметрам REF CURSOR по имени, <xref:System.Data.OracleClient.OracleDataReader> они обращаются к ним в том порядке, в котором они были добавлены в <xref:System.Data.OracleClient.OracleCommand.Parameters> коллекцию.  
  
 Например, рассмотрим следующий пакет и текст пакета Oracle.  
  
```sql
CREATE OR REPLACE PACKAGE CURSPKG AS
  TYPE T_CURSOR IS REF CURSOR;
  PROCEDURE OPEN_TWO_CURSORS (EMPCURSOR OUT T_CURSOR,
    DEPTCURSOR OUT T_CURSOR);
END CURSPKG;  
  
CREATE OR REPLACE PACKAGE BODY CURSPKG AS
  PROCEDURE OPEN_TWO_CURSORS (EMPCURSOR OUT T_CURSOR,
    DEPTCURSOR OUT T_CURSOR)
  IS
  BEGIN
    OPEN EMPCURSOR FOR SELECT * FROM DEMO.EMPLOYEE;
    OPEN DEPTCURSOR FOR SELECT * FROM DEMO.DEPARTMENT;
  END OPEN_TWO_CURSORS;
END CURSPKG;
```  
  
 Следующий код создает объект <xref:System.Data.OracleClient.OracleCommand> , который возвращает ссылки на ref из предыдущего пакета Oracle, добавляя два параметра типа <xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType> в <xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType> коллекцию.  
  
```vb  
Dim cursCmd As OracleCommand = New OracleCommand("CURSPKG.OPEN_TWO_CURSORS", oraConn)  
cursCmd.Parameters.Add("EMPCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output  
cursCmd.Parameters.Add("DEPTCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output  
```  
  
```csharp  
OracleCommand cursCmd = new OracleCommand("CURSPKG.OPEN_TWO_CURSORS", oraConn);  
cursCmd.Parameters.Add("EMPCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output;  
cursCmd.Parameters.Add("DEPTCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output;  
```  
  
 Следующий код возвращает результаты предыдущей команды с помощью <xref:System.Data.OracleClient.OracleDataReader.Read> <xref:System.Data.OracleClient.OracleDataReader.NextResult> методов и объекта <xref:System.Data.OracleClient.OracleDataReader> . Параметры REF CURSOR возвращаются по порядку.  
  
```vb  
oraConn.Open()  
  
Dim cursCmd As OracleCommand = New OracleCommand("CURSPKG.OPEN_TWO_CURSORS", oraConn)  
cursCmd.CommandType = CommandType.StoredProcedure  
cursCmd.Parameters.Add("EMPCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output  
cursCmd.Parameters.Add("DEPTCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output  
  
Dim reader As OracleDataReader = cursCmd.ExecuteReader()  
  
Console.WriteLine(vbCrLf & "Emp ID" & vbTab & "Name")  
  
Do While reader.Read()  
  Console.WriteLine("{0}" & vbTab & "{1}, {2}", reader.GetOracleNumber(0), reader.GetString(1), reader.GetString(2))  
Loop  
  
reader.NextResult()  
  
Console.WriteLine(vbCrLf & "Dept ID" & vbTab & "Name")  
  
Do While reader.Read()  
  Console.WriteLine("{0}" & vbTab & "{1}", reader.GetOracleNumber(0), reader.GetString(1))  
Loop  
' Make sure to always close readers and connections.  
reader.Close()  
oraConn.Close()  
```  
  
```csharp  
oraConn.Open();  
  
OracleCommand cursCmd = new OracleCommand("CURSPKG.OPEN_TWO_CURSORS", oraConn);  
cursCmd.CommandType = CommandType.StoredProcedure;  
cursCmd.Parameters.Add("EMPCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output;  
cursCmd.Parameters.Add("DEPTCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output;  
  
OracleDataReader reader = cursCmd.ExecuteReader();  
  
Console.WriteLine("\nEmp ID\tName");  
  
while (reader.Read())  
  Console.WriteLine("{0}\t{1}, {2}", reader.GetOracleNumber(0), reader.GetString(1), reader.GetString(2));  
  
reader.NextResult();  
  
Console.WriteLine("\nDept ID\tName");  
  
while (reader.Read())  
  Console.WriteLine("{0}\t{1}", reader.GetOracleNumber(0), reader.GetString(1));  
// Make sure to always close readers and connections.  
reader.Close();  
oraConn.Close();  
```  
  
 В следующем примере используется предыдущая команда для заполнения <xref:System.Data.DataSet> с результатами пакета Oracle.  
  
```vb  
Dim ds As DataSet = New DataSet()  
  
Dim adapter As OracleDataAdapter = New OracleDataAdapter(cursCmd)  
adapter.TableMappings.Add("Table", "Employees")  
adapter.TableMappings.Add("Table1", "Departments")  
  
adapter.Fill(ds)  
```  
  
```csharp  
DataSet ds = new DataSet();  
  
OracleDataAdapter adapter = new OracleDataAdapter(cursCmd);  
adapter.TableMappings.Add("Table", "Employees");  
adapter.TableMappings.Add("Table1", "Departments");  
  
adapter.Fill(ds);  
```

> [!NOTE]
> Чтобы избежать **переполнения**, рекомендуется также выполнять преобразование из типа номера Oracle в допустимый тип .NET Framework перед сохранением значения в <xref:System.Data.DataRow> . Можно использовать событие, <xref:System.Data.Common.DataAdapter.FillError> чтобы определить, произошло ли исключение **OverflowException** . Дополнительные сведения о <xref:System.Data.Common.DataAdapter.FillError> событии см. в разделе [Обработка событий DataAdapter](handling-dataadapter-events.md).  
  
## <a name="see-also"></a>См. также

- [Объекты DataAdapter и DataReader](dataadapters-and-datareaders.md)
- [Команды и параметры](commands-and-parameters.md)
- [Извлечение сведений о схеме базы данных](retrieving-database-schema-information.md)
- [Общие сведения об ADO.NET](ado-net-overview.md)
