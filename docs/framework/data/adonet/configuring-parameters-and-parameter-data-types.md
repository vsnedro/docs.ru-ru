---
title: Настройка параметров и типов данных параметров
description: Объекты команды используют параметры для передачи значений в инструкции SQL или хранимые процедуры, предоставляя проверку типов и проверку в ADO.NET.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 537d8a2c-d40b-4000-83eb-bc1fcc93f707
ms.openlocfilehash: a426eeae785274b0484a84a2fae2dce4572fb4c4
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287120"
---
# <a name="configuring-parameters-and-parameter-data-types"></a>Настройка параметров и типов данных параметров

Объекты команды используют параметры для передачи значений в выражения SQL или хранимые процедуры, обеспечивая проверку типов и правильности. В отличие от текста команд, входные параметры обрабатываются как буквенные значения, а не как исполняемый код. Это помогает защищаться от атак путем внедрения кода SQL, при которых злоумышленник вставляет в инструкцию SQL команду, ставящую под угрозу безопасность сервера.

Параметризованные команды также позволяют повысить производительность при выполнении запроса, поскольку при их использовании сервер баз данных может точно сопоставить входящей команде правильный кэшированных план запроса. Дополнительные сведения см. в статьях [кэширование и повторное использование плана выполнения](/sql/relational-databases/query-processing-architecture-guide#execution-plan-caching-and-reuse) , [Параметры и повторное использование плана выполнения](/sql/relational-databases/query-processing-architecture-guide#PlanReuse). Помимо повышения безопасности и производительности параметризованные команды обеспечивают удобный метод организации значений, передающихся в источник данных.

Объект <xref:System.Data.Common.DbParameter> можно создать при помощи конструктора или путем добавления его в коллекцию <xref:System.Data.Common.DbCommand.DbParameterCollection%2A> с помощью метода `Add` коллекции <xref:System.Data.Common.DbParameterCollection> . Метод `Add` принимает в качестве входных данных либо аргументы конструктора, либо существующий объект параметра - в зависимости от поставщика данных.

## <a name="supplying-the-parameterdirection-property"></a>Указание свойства Параметердиректион

При добавлении параметров необходимо указать свойство <xref:System.Data.ParameterDirection> для параметров, не являющихся входными. В следующей таблице показаны значения `ParameterDirection` , которые можно использовать с перечислением <xref:System.Data.ParameterDirection> .

|Имя члена|Описание|
|-----------------|-----------------|
|<xref:System.Data.ParameterDirection.Input>|Параметр является входным. Это значение по умолчанию.|
|<xref:System.Data.ParameterDirection.InputOutput>|Параметр можно использовать как для ввода, так и для вывода.|
|<xref:System.Data.ParameterDirection.Output>|Параметр является выходным.|
|<xref:System.Data.ParameterDirection.ReturnValue>|Параметр представляет значение, возвращаемое как результат операции, например хранимой процедуры, встроенной функции или определяемой пользователем функции.|

## <a name="working-with-parameter-placeholders"></a>Работа с заполнителями параметров

Синтаксис местозаполнителей параметров зависит от источника данных. В поставщиках данных .NET Framework обработка именованием и заданием параметров и параметров-местозаполнителей выполняется по-разному. Синтаксис зависит от конкретного источника данных, как описано в следующей таблице.

|Поставщик данных|Синтаксис именования параметров|
|-------------------|-----------------------------|
|<xref:System.Data.SqlClient>|Использует именованные параметры в формате `@`*имяпараметра*.|
|<xref:System.Data.OleDb>|Использует маркеры позиционных параметров, указываемые знаком вопроса (`?`).|
|<xref:System.Data.Odbc>|Использует маркеры позиционных параметров, указываемые знаком вопроса (`?`).|
|<xref:System.Data.OracleClient>|Использует именованные параметры в формате `:`*имяпараметра* (или *имяпараметра*).|

## <a name="specifying-parameter-data-types"></a>Указание типов данных параметров

Тип данных параметра зависит от поставщика данных .NET Framework. При указании типа значение преобразуется в `Parameter` .NET Framework тип поставщика данных перед передачей значения в источник данных. Можно также указать тип `Parameter` универсальным способом, задав свойству `DbType` объекта `Parameter` определенное значение <xref:System.Data.DbType>.

Тип поставщика данных .NET Framework `Parameter` объекта выводится из .NET Framework типа `Value` `Parameter` объекта или из `DbType` объекта служб `Parameter` . Следующая таблица показывает тип `Parameter` , выводимый из объекта, переданного как значение `Parameter` , или указанного значения `DbType`.

|Тип платформы .NET Framework|DbType|SqlDbType|OleDbType|OdbcType|OracleType|
|-------------------------|------------|---------------|---------------|--------------|----------------|
|<xref:System.Boolean>|Логическое|bit|Логическое|bit|Byte|
|<xref:System.Byte>|Byte|TinyInt|UnsignedTinyInt|TinyInt|Byte|
|byte[]|Двоичный|VarBinary. Это неявное преобразование завершится ошибкой, если массив байтов больше, чем максимальный размер VarBinary, который равен 8000 байт. Для массивов байтов, превышающих 8000 байт, явно задайте значение <xref:System.Data.SqlDbType> .|VarBinary|Двоичный|Raw|
|<xref:System.Char>| |Вывод типа <xref:System.Data.SqlDbType> из типа char не поддерживается.|Char|Char|Byte|
|<xref:System.DateTime>|Дата и время|Дата и время|DBTimeStamp|Дата и время|Дата и время|
|<xref:System.DateTimeOffset>|DateTimeOffset|Тип DateTimeOffset в SQL Server 2008. Вывод типа <xref:System.Data.SqlDbType> из типа DateTimeOffset не поддерживается в версиях SQL Server до SQL Server 2008.|||Дата и время|
|<xref:System.Decimal>|Decimal|Decimal|Decimal|Числовой|Number|
|<xref:System.Double>|Double|Float|Double|Double|Double|
|<xref:System.Single>|Один|Real|Один|Real|Float|
|<xref:System.Guid>|Guid|UniqueIdentifier|Guid|UniqueIdentifier|Raw|
|<xref:System.Int16>|Int16|SmallInt|SmallInt|SmallInt|Int16|
|<xref:System.Int32>|Int32|Int|Int|Int|Int32|
|<xref:System.Int64>|Int64|BigInt|BigInt|BigInt|Number|
|<xref:System.Object>|Объект|Variant|Variant|Вывод типа OdbcType из типа Object не поддерживается.|BLOB-объект|
|<xref:System.String>|Строка|NVarChar. Это неявное преобразование завершится ошибкой, если строка превышает максимальный размер для типа NVarChar (4000 символов). Для строк длиннее 4000 символов явно установите значение <xref:System.Data.SqlDbType>.|VarWChar|NVarChar|NVarChar|
|<xref:System.TimeSpan>|Время|Тип Time в SQL Server 2008. Вывод типа <xref:System.Data.SqlDbType> из типа TimeSpan не поддерживается в версиях SQL Server до SQL Server 2008.|DBTime|Время|Дата и время|
|<xref:System.UInt16>|UInt16|Вывод типа <xref:System.Data.SqlDbType> из типа UInt16 не поддерживается.|UnsignedSmallInt|Int|UInt16|
|<xref:System.UInt32>|UInt32|Вывод типа <xref:System.Data.SqlDbType> из типа UInt32 не поддерживается.|UnsignedInt|BigInt|UInt32|
|<xref:System.UInt64>|UInt64|Вывод типа <xref:System.Data.SqlDbType> из типа UInt64 не поддерживается.|UnsignedBigInt|Числовой|Number|
||AnsiString|VarChar|VarChar|VarChar|VarChar|
||AnsiStringFixedLength|Char|Char|Char|Char|
||Валюта|Money|Валюта|Вывод типа `OdbcType` из типа `Currency` не поддерживается.|Number|
||Дата|Тип Date в SQL Server 2008. Вывод типа <xref:System.Data.SqlDbType> из типа Date не поддерживается в версиях SQL Server до SQL Server 2008.|DBDate|Дата|Дата и время|
||SByte|Вывод типа <xref:System.Data.SqlDbType> из типа SByte не поддерживается.|TinyInt|Вывод типа `OdbcType` из типа SByte не поддерживается.|SByte|
||StringFixedLength|NCHAR|WChar|NCHAR|NCHAR|
||Время|Тип Time в SQL Server 2008. Вывод типа <xref:System.Data.SqlDbType> из типа Time не поддерживается в версиях SQL Server до SQL Server 2008.|DBTime|Время|Дата и время|
||VarNumeric|Вывод типа <xref:System.Data.SqlDbType> из типа VarNumeric не поддерживается.|VarNumeric|Вывод типа `OdbcType` из типа VarNumeric не поддерживается.|Number|
|определяемый пользователем тип (объект с <xref:Microsoft.SqlServer.Server.SqlUserDefinedAggregateAttribute>|Объект или строка в зависимости от поставщика (SqlClient всегда возвращает объект, ODBC всегда возвращает строку, а поставщик данных, управляемый OleDb, может вернуть и то и другое).|SqlDbType.Udt, если присутствует <xref:Microsoft.SqlServer.Server.SqlUserDefinedTypeAttribute> , в противном случае Variant|OleDbType.VarWChar (при значении NULL), в противном случае OleDbType.Variant.|OdbcType.NVarChar|не поддерживается|

> [!NOTE]
> Преобразования из типа decimal в другие типы являются сужающими. Они округляют десятичное значение до ближайшего целого в направлении нуля. Если результат преобразования нельзя представить в целевом типе, возникает исключение <xref:System.OverflowException> .

> [!NOTE]
> При отправке на сервер значения параметра NULL необходимо указать <xref:System.DBNull> , а не `null` ( `Nothing` в Visual Basic). Значением NULL в системе является пустой объект, который не имеет значений. Объект <xref:System.DBNull> используется для представления значений NULL. Дополнительные сведения об значениях NULL базы данных см. в разделе [Обработка значений NULL](./sql/handling-null-values.md).

## <a name="deriving-parameter-information"></a>Получение сведений о параметрах

Информацию о параметрах можно вывести из хранимой процедуры с помощью класса `DbCommandBuilder` . Оба класса, `SqlCommandBuilder` и `OleDbCommandBuilder` , обеспечивают статический метод `DeriveParameters`, который автоматически заполняет коллекцию параметров объекта команд, использующего информацию о параметрах от хранимой процедуры. Обратите внимание, что метод `DeriveParameters` перезаписывает существующую информацию о параметрах для команды.

> [!NOTE]
> Выведение информации о параметрах снижает производительность, так как для этого требуется дополнительный обмен данных с источником данных. Если информация о параметрах известна во время разработки, можно увеличить производительность приложения, задав параметры явным образом.

Дополнительные сведения см. в разделе [Создание команд с помощью коммандбуилдерс](generating-commands-with-commandbuilders.md).

## <a name="using-parameters-with-a-sqlcommand-and-a-stored-procedure"></a>Использование параметров с SqlCommand и хранимой процедурой

Хранимые процедуры дают множество преимуществ в приложениях, управляемых данными. С помощью хранимых процедур операции с базой данных можно инкапсулировать в одну команду, оптимизированную для производительности и обладающую повышенной безопасностью. Несмотря на то, что хранимую процедуру можно вызвать, передав имя хранимой процедуры, а затем аргументы параметра в качестве инструкции SQL, используя <xref:System.Data.Common.DbCommand.Parameters%2A> коллекцию объекта ADO.NET, <xref:System.Data.Common.DbCommand> можно более явно определить параметры хранимой процедуры и получить доступ к выходным параметрам и возвращаемым значениям.

> [!NOTE]
> Параметризованные инструкции выполняются на сервере с помощью хранимой процедуры `sp_executesql,` которая позволяет повторно использовать планы запросов. Локальные курсоры или переменные в пакете `sp_executesql` недоступны пакету, вызвавшему `sp_executesql`. Изменения в контексте базы данных длятся только до завершения выполнения инструкции `sp_executesql` . Дополнительные сведения см. в разделе [sp_executesql (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-executesql-transact-sql).

Если параметры используются с объектом <xref:System.Data.SqlClient.SqlCommand> для выполнения хранимой процедуры SQL Server, то имена параметров, добавляемых в коллекцию <xref:System.Data.SqlClient.SqlCommand.Parameters%2A> , должны соответствовать именам маркеров параметров в хранимой процедуре. Поставщик данных .NET Framework для SQL Server не поддерживает заполнитель вопросительного знака (?) для передачи параметров в инструкцию SQL или хранимую процедуру. Он обрабатывает параметры в хранимой процедуре как именованные параметры и ищет соответствующие маркеры параметров. Например, хранимая процедура `CustOrderHist` определяется с использованием параметра `@CustomerID`. Когда программа выполняет эта хранимую процедуру, она также должна использовать параметр `@CustomerID`.

```sql
CREATE PROCEDURE dbo.CustOrderHist @CustomerID varchar(5)
```

### <a name="example"></a>Пример

Этот пример показывает, как вызвать хранимую процедуру SQL Server в образце базы данных `Northwind` . Имя хранимой процедуры – `dbo.SalesByCategory` . Она имеет входной параметр `@CategoryName` с типом данных `nvarchar(15)`. Код создает создает новый объект класса <xref:System.Data.SqlClient.SqlConnection> в блоке Using, чтобы в конце процедуры соединение удалялось. Создаются объекты <xref:System.Data.SqlClient.SqlCommand> и <xref:System.Data.SqlClient.SqlParameter> устанавливаются их свойства. Объект класса <xref:System.Data.SqlClient.SqlDataReader> выполняет `SqlCommand` и возвращает результирующий набор из хранимой процедуры, отображая выходные данные в окне консоли.

> [!NOTE]
> Вместо того, чтобы создавать объекты `SqlCommand` и `SqlParameter` и затем задавать их свойства в отдельных инструкциях, можно использовать один из перегруженных конструкторов и задать свойства в одной инструкции.

[!code-csharp[DataWorks SqlClient.StoredProcedure#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.StoredProcedure/CS/source.cs#1)]
[!code-vb[DataWorks SqlClient.StoredProcedure#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.StoredProcedure/VB/source.vb#1)]

## <a name="using-parameters-with-an-oledbcommand-or-odbccommand"></a>Использование параметров с параметром OleDbCommand или Одбккомманд

Если с объектами <xref:System.Data.OleDb.OleDbCommand> или <xref:System.Data.Odbc.OdbcCommand>используются параметры, порядок параметров, добавляемых в коллекцию `Parameters` , должен соответствовать порядку параметров, заданных в хранимой процедуре. Поставщик данных .NET Framework для OLE DB и .NET Framework поставщика данных для ODBC рассматривает параметры в хранимой процедуре как местозаполнители и применяет значения параметров по порядку. Кроме того, параметры возвращаемых значений должны быть первыми параметрами, добавляемыми в коллекцию `Parameters` .

Поставщик данных .NET Framework для OLE DB и .NET Framework поставщика данных для ODBC не поддерживает именованные параметры для передачи параметров в инструкцию SQL или хранимую процедуру. В этом случае необходимо использовать местозаполнитель (?), как в следующем примере.

```sql
SELECT * FROM Customers WHERE CustomerID = ?
```

В результате порядок добавления объектов `Parameter` в коллекцию `Parameters` должен строго соответствовать позиции местозаполнителя параметра (?).

### <a name="oledb-example"></a>Пример OleDb

```vb
Dim command As OleDbCommand = New OleDbCommand( _
  "SampleProc", connection)
command.CommandType = CommandType.StoredProcedure

Dim parameter As OleDbParameter = command.Parameters.Add( _
  "RETURN_VALUE", OleDbType.Integer)
parameter.Direction = ParameterDirection.ReturnValue

parameter = command.Parameters.Add( _
  "@InputParm", OleDbType.VarChar, 12)
parameter.Value = "Sample Value"

parameter = command.Parameters.Add( _
  "@OutputParm", OleDbType.VarChar, 28)
parameter.Direction = ParameterDirection.Output
```

```csharp
OleDbCommand command = new OleDbCommand("SampleProc", connection);
command.CommandType = CommandType.StoredProcedure;

OleDbParameter parameter = command.Parameters.Add(
  "RETURN_VALUE", OleDbType.Integer);
parameter.Direction = ParameterDirection.ReturnValue;

parameter = command.Parameters.Add(
  "@InputParm", OleDbType.VarChar, 12);
parameter.Value = "Sample Value";

parameter = command.Parameters.Add(
  "@OutputParm", OleDbType.VarChar, 28);
parameter.Direction = ParameterDirection.Output;
```

## <a name="odbc-example"></a>Пример Odbc

```vb
Dim command As OdbcCommand = New OdbcCommand( _
  "{ ? = CALL SampleProc(?, ?) }", connection)
command.CommandType = CommandType.StoredProcedure

Dim parameter As OdbcParameter = command.Parameters.Add("RETURN_VALUE", OdbcType.Int)
parameter.Direction = ParameterDirection.ReturnValue

parameter = command.Parameters.Add( _
  "@InputParm", OdbcType.VarChar, 12)
parameter.Value = "Sample Value"

parameter = command.Parameters.Add( _
  "@OutputParm", OdbcType.VarChar, 28)
parameter.Direction = ParameterDirection.Output
```

```csharp
OdbcCommand command = new OdbcCommand( _
  "{ ? = CALL SampleProc(?, ?) }", connection);
command.CommandType = CommandType.StoredProcedure;

OdbcParameter parameter = command.Parameters.Add( _
  "RETURN_VALUE", OdbcType.Int);
parameter.Direction = ParameterDirection.ReturnValue;

parameter = command.Parameters.Add( _
  "@InputParm", OdbcType.VarChar, 12);
parameter.Value = "Sample Value";

parameter = command.Parameters.Add( _
  "@OutputParm", OdbcType.VarChar, 28);
parameter.Direction = ParameterDirection.Output;
```

## <a name="see-also"></a>См. также

- [Команды и параметры](commands-and-parameters.md)
- [Параметры DataAdapter](dataadapter-parameters.md)
- [Сопоставления типов данных в ADO.NET](data-type-mappings-in-ado-net.md)
- [Общие сведения об ADO.NET](ado-net-overview.md)
