---
title: Большие UDT
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 420ae24e-762b-4e09-b4c3-2112c470ee49
ms.openlocfilehash: 032093244f51893cd3b0cf50ad81c79413aaa32e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91194548"
---
# <a name="large-udts"></a><span data-ttu-id="1dd83-102">Большие, определяемые пользователем типы</span><span class="sxs-lookup"><span data-stu-id="1dd83-102">Large UDTs</span></span>

<span data-ttu-id="1dd83-103">Определяемые пользователем типы призваны дать разработчику возможность расширить серверную систему скалярных типов путем хранения объектов среды CLR в базе данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1dd83-103">User-defined types (UDTs) allow a developer to extend the server's scalar type system by storing common language runtime (CLR) objects in a SQL Server database.</span></span> <span data-ttu-id="1dd83-104">Определяемые пользователем типы могут содержать несколько элементов, и их поведение может отличаться от традиционных псевдонимов типов данных, которые состоят из одного системного типа данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1dd83-104">UDTs can contain multiple elements and can have behaviors, unlike the traditional alias data types, which consist of a single SQL Server system data type.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1dd83-105">Чтобы воспользоваться расширенной поддержкой SqlClient определяемых пользователем типов данных большого размера, необходимо установить .NET Framework 3.5 с пакетом обновления 1 (SP1) или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="1dd83-105">You must install the .NET Framework 3.5 SP1 (or later) to take advantage of the enhanced SqlClient support for large UDTs.</span></span>  
  
 <span data-ttu-id="1dd83-106">Ранее размер определяемых пользователем типов был ограничен 8 килобайтами.</span><span class="sxs-lookup"><span data-stu-id="1dd83-106">Previously, UDTs were restricted to a maximum size of 8 kilobytes.</span></span> <span data-ttu-id="1dd83-107">Это ограничение было снято в SQL Server 2008 для определяемых пользователем типов, имеющих формат <xref:Microsoft.SqlServer.Server.Format.UserDefined>.</span><span class="sxs-lookup"><span data-stu-id="1dd83-107">In SQL Server 2008, this restriction has been removed for UDTs that have a format of <xref:Microsoft.SqlServer.Server.Format.UserDefined>.</span></span>  
  
 <span data-ttu-id="1dd83-108">Полную документацию по определяемым пользователем типам данных см. в электронной документации по SQL Server для используемой версии SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1dd83-108">For the complete documentation for user-defined types, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="1dd83-109">**Документация по SQL Server**</span><span class="sxs-lookup"><span data-stu-id="1dd83-109">**SQL Server documentation**</span></span>  
  
1. [<span data-ttu-id="1dd83-110">Определяемые пользователем типы CLR</span><span class="sxs-lookup"><span data-stu-id="1dd83-110">CLR User-Defined Types</span></span>](/sql/relational-databases/clr-integration-database-objects-user-defined-types/clr-user-defined-types)  
  
## <a name="retrieving-udt-schemas-using-getschema"></a><span data-ttu-id="1dd83-111">Загрузка схем определяемых пользователем типов данных с помощью метода GetSchema</span><span class="sxs-lookup"><span data-stu-id="1dd83-111">Retrieving UDT Schemas Using GetSchema</span></span>  

 <span data-ttu-id="1dd83-112">Метод <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A><xref:System.Data.SqlClient.SqlConnection> возвращает сведения о схеме базы данных в <xref:System.Data.DataTable>.</span><span class="sxs-lookup"><span data-stu-id="1dd83-112">The <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> method of <xref:System.Data.SqlClient.SqlConnection> returns database schema information in a <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="1dd83-113">Дополнительные сведения см. в разделе [SQL Server коллекции схем](../sql-server-schema-collections.md).</span><span class="sxs-lookup"><span data-stu-id="1dd83-113">For more information, see [SQL Server Schema Collections](../sql-server-schema-collections.md).</span></span>  
  
### <a name="getschematable-column-values-for-udts"></a><span data-ttu-id="1dd83-114">Значения столбца GetSchemaTable для определяемых пользователем типов данных</span><span class="sxs-lookup"><span data-stu-id="1dd83-114">GetSchemaTable Column Values for UDTs</span></span>  

 <span data-ttu-id="1dd83-115">Метод <xref:System.Data.SqlClient.SqlDataReader.GetSchemaTable%2A><xref:System.Data.SqlClient.SqlDataReader> возвращает <xref:System.Data.DataTable>, описывающее метаданные столбца.</span><span class="sxs-lookup"><span data-stu-id="1dd83-115">The <xref:System.Data.SqlClient.SqlDataReader.GetSchemaTable%2A> method of a <xref:System.Data.SqlClient.SqlDataReader> returns a <xref:System.Data.DataTable> that describes column metadata.</span></span> <span data-ttu-id="1dd83-116">В следующей таблице описаны различия в метаданных столбцов для больших пользовательских типов данных между SQL Server 2005 и SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="1dd83-116">The following table describes the differences in the column metadata for large UDTs between SQL Server 2005 and SQL Server 2008.</span></span>  
  
|<span data-ttu-id="1dd83-117">Столбец SqlDataReader</span><span class="sxs-lookup"><span data-stu-id="1dd83-117">SqlDataReader column</span></span>|<span data-ttu-id="1dd83-118">SQL Server 2005</span><span class="sxs-lookup"><span data-stu-id="1dd83-118">SQL Server 2005</span></span>|<span data-ttu-id="1dd83-119">SQL Server 2008 и более поздние версии</span><span class="sxs-lookup"><span data-stu-id="1dd83-119">SQL Server 2008 and later</span></span>|  
|--------------------------|---------------------|-------------------------------|  
|`ColumnSize`|<span data-ttu-id="1dd83-120">Различается</span><span class="sxs-lookup"><span data-stu-id="1dd83-120">Varies</span></span>|<span data-ttu-id="1dd83-121">Различается</span><span class="sxs-lookup"><span data-stu-id="1dd83-121">Varies</span></span>|  
|`NumericPrecision`|<span data-ttu-id="1dd83-122">255</span><span class="sxs-lookup"><span data-stu-id="1dd83-122">255</span></span>|<span data-ttu-id="1dd83-123">255</span><span class="sxs-lookup"><span data-stu-id="1dd83-123">255</span></span>|  
|`NumericScale`|<span data-ttu-id="1dd83-124">255</span><span class="sxs-lookup"><span data-stu-id="1dd83-124">255</span></span>|<span data-ttu-id="1dd83-125">255</span><span class="sxs-lookup"><span data-stu-id="1dd83-125">255</span></span>|  
|`DataType`|`Byte[]`|<span data-ttu-id="1dd83-126">Экземпляр UDT</span><span class="sxs-lookup"><span data-stu-id="1dd83-126">UDT instance</span></span>|  
|`ProviderSpecificDataType`|`SqlTypes.SqlBinary`|<span data-ttu-id="1dd83-127">Экземпляр UDT</span><span class="sxs-lookup"><span data-stu-id="1dd83-127">UDT instance</span></span>|  
|`ProviderType`|<span data-ttu-id="1dd83-128">21 (`SqlDbType.VarBinary`)</span><span class="sxs-lookup"><span data-stu-id="1dd83-128">21 (`SqlDbType.VarBinary`)</span></span>|<span data-ttu-id="1dd83-129">29 (`SqlDbType.Udt`)</span><span class="sxs-lookup"><span data-stu-id="1dd83-129">29 (`SqlDbType.Udt`)</span></span>|  
|`NonVersionedProviderType`|<span data-ttu-id="1dd83-130">29 (`SqlDbType.Udt`)</span><span class="sxs-lookup"><span data-stu-id="1dd83-130">29 (`SqlDbType.Udt`)</span></span>|<span data-ttu-id="1dd83-131">29 (`SqlDbType.Udt`)</span><span class="sxs-lookup"><span data-stu-id="1dd83-131">29 (`SqlDbType.Udt`)</span></span>|  
|`DataTypeName`|`SqlDbType.VarBinary`|<span data-ttu-id="1dd83-132">Имя из трех частей, указанное как *Database.SchemaName.TypeName*.</span><span class="sxs-lookup"><span data-stu-id="1dd83-132">The three part name specified as *Database.SchemaName.TypeName*.</span></span>|  
|`IsLong`|<span data-ttu-id="1dd83-133">Различается</span><span class="sxs-lookup"><span data-stu-id="1dd83-133">Varies</span></span>|<span data-ttu-id="1dd83-134">Различается</span><span class="sxs-lookup"><span data-stu-id="1dd83-134">Varies</span></span>|  
  
## <a name="sqldatareader-considerations"></a><span data-ttu-id="1dd83-135">Вопросы, связанные с SqlDataReader</span><span class="sxs-lookup"><span data-stu-id="1dd83-135">SqlDataReader Considerations</span></span>  

 <span data-ttu-id="1dd83-136">Объект <xref:System.Data.SqlClient.SqlDataReader> в SQL Server 2008 был расширен для поддержки загрузки значений определяемых пользователем типов данных большого размера.</span><span class="sxs-lookup"><span data-stu-id="1dd83-136">The <xref:System.Data.SqlClient.SqlDataReader> has been extended beginning in SQL Server 2008 to support retrieving large UDT values.</span></span> <span data-ttu-id="1dd83-137">Как большие значения пользовательского типа обрабатываются <xref:System.Data.SqlClient.SqlDataReader>, зависит от используемой версии SQL Server, а также от `Type System Version`, указанного в строке подключения.</span><span class="sxs-lookup"><span data-stu-id="1dd83-137">How large UDT values are processed by a <xref:System.Data.SqlClient.SqlDataReader> depends on the version of SQL Server you are using, as well as on the `Type System Version` specified in the connection string.</span></span> <span data-ttu-id="1dd83-138">Для получения дополнительной информации см. <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>.</span><span class="sxs-lookup"><span data-stu-id="1dd83-138">For more information, see <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>.</span></span>  
  
 <span data-ttu-id="1dd83-139">Следующие методы <xref:System.Data.SqlClient.SqlDataReader> будут возвращать <xref:System.Data.SqlTypes.SqlBinary> вместо пользовательского типа, если для `Type System Version` установлено значение SQL Server 2005:</span><span class="sxs-lookup"><span data-stu-id="1dd83-139">The following methods of <xref:System.Data.SqlClient.SqlDataReader> will return a <xref:System.Data.SqlTypes.SqlBinary> instead of a UDT when the `Type System Version` is set to SQL Server 2005:</span></span>  
  
- <xref:System.Data.SqlClient.SqlDataReader.GetProviderSpecificFieldType%2A>  
  
- <xref:System.Data.SqlClient.SqlDataReader.GetProviderSpecificValue%2A>  
  
- <xref:System.Data.SqlClient.SqlDataReader.GetProviderSpecificValues%2A>  
  
- <xref:System.Data.SqlClient.SqlDataReader.GetSqlValue%2A>  
  
- <xref:System.Data.SqlClient.SqlDataReader.GetSqlValues%2A>  
  
 <span data-ttu-id="1dd83-140">Следующие методы будут возвращать массив `Byte[]` вместо пользовательского типа, если для `Type System Version` установлено значение SQL Server 2005:</span><span class="sxs-lookup"><span data-stu-id="1dd83-140">The following methods will return an array of `Byte[]` instead of a UDT when the `Type System Version` is set to SQL Server 2005:</span></span>  
  
- <xref:System.Data.SqlClient.SqlDataReader.GetValue%2A>  
  
- <xref:System.Data.SqlClient.SqlDataReader.GetValues%2A>  
  
 <span data-ttu-id="1dd83-141">Обратите внимание, что для текущей версии ADO.NET никакие преобразования не выполняются.</span><span class="sxs-lookup"><span data-stu-id="1dd83-141">Note that no conversions are made for the current version of ADO.NET.</span></span>  
  
## <a name="specifying-sqlparameters"></a><span data-ttu-id="1dd83-142">Указание SqlParameters</span><span class="sxs-lookup"><span data-stu-id="1dd83-142">Specifying SqlParameters</span></span>  

 <span data-ttu-id="1dd83-143">Следующие свойства <xref:System.Data.SqlClient.SqlParameter> были расширены для работы с большими пользовательскими типами.</span><span class="sxs-lookup"><span data-stu-id="1dd83-143">The following <xref:System.Data.SqlClient.SqlParameter> properties have been extended to work with large UDTs.</span></span>  
  
|<span data-ttu-id="1dd83-144">Свойство SqlParameter</span><span class="sxs-lookup"><span data-stu-id="1dd83-144">SqlParameter Property</span></span>|<span data-ttu-id="1dd83-145">Описание</span><span class="sxs-lookup"><span data-stu-id="1dd83-145">Description</span></span>|  
|---------------------------|-----------------|  
|<xref:System.Data.SqlClient.SqlParameter.Value%2A>|<span data-ttu-id="1dd83-146">Возвращает или задает объект, представляющий значение параметра.</span><span class="sxs-lookup"><span data-stu-id="1dd83-146">Gets or sets an object that represents the value of the parameter.</span></span> <span data-ttu-id="1dd83-147">Значение по умолчанию — NULL.</span><span class="sxs-lookup"><span data-stu-id="1dd83-147">The default is null.</span></span> <span data-ttu-id="1dd83-148">Свойством может быть `SqlBinary`, `Byte[]` или управляемый объект.</span><span class="sxs-lookup"><span data-stu-id="1dd83-148">The property can be `SqlBinary`, `Byte[]`, or a managed object.</span></span>|  
|<xref:System.Data.SqlClient.SqlParameter.SqlValue%2A>|<span data-ttu-id="1dd83-149">Возвращает или задает объект, представляющий значение параметра.</span><span class="sxs-lookup"><span data-stu-id="1dd83-149">Gets or sets an object that represents the value of the parameter.</span></span> <span data-ttu-id="1dd83-150">Значение по умолчанию — NULL.</span><span class="sxs-lookup"><span data-stu-id="1dd83-150">The default is null.</span></span> <span data-ttu-id="1dd83-151">Свойством может быть `SqlBinary`, `Byte[]` или управляемый объект.</span><span class="sxs-lookup"><span data-stu-id="1dd83-151">The property can be `SqlBinary`, `Byte[]`, or a managed object.</span></span>|  
|<xref:System.Data.SqlClient.SqlParameter.Size%2A>|<span data-ttu-id="1dd83-152">Возвращает или задает размер значения параметра для разрешения.</span><span class="sxs-lookup"><span data-stu-id="1dd83-152">Gets or sets the size of the parameter value to resolve.</span></span> <span data-ttu-id="1dd83-153">Значение по умолчанию — 0.</span><span class="sxs-lookup"><span data-stu-id="1dd83-153">The default value is 0.</span></span> <span data-ttu-id="1dd83-154">Свойство может быть целым числом, представляющим размер значения параметра.</span><span class="sxs-lookup"><span data-stu-id="1dd83-154">The property can be an integer that represents the size of the parameter value.</span></span> <span data-ttu-id="1dd83-155">Для больших определяемых пользователем типов оно может равняться действительному размеру определяемого пользователем типа или иметь значение –1 — для неизвестных.</span><span class="sxs-lookup"><span data-stu-id="1dd83-155">For large UDTs, it can be the actual size of the UDT, or -1 for unknown.</span></span>|  
  
## <a name="retrieving-data-example"></a><span data-ttu-id="1dd83-156">Пример извлечения данных</span><span class="sxs-lookup"><span data-stu-id="1dd83-156">Retrieving Data Example</span></span>  

 <span data-ttu-id="1dd83-157">В следующем фрагменте кода показано, как получить большие данные пользовательского типа.</span><span class="sxs-lookup"><span data-stu-id="1dd83-157">The following code fragment demonstrates how to retrieve large UDT data.</span></span> <span data-ttu-id="1dd83-158">Переменная `connectionString` предполагает допустимое соединение с базой данных SQL Server, а переменная `commandString` предполагает, что допустимая инструкция SELECT со столбцом первичного ключа указана первой.</span><span class="sxs-lookup"><span data-stu-id="1dd83-158">The `connectionString` variable assumes a valid connection to a SQL Server database and the `commandString` variable assumes a valid SELECT statement with the primary key column listed first.</span></span>  
  
```csharp  
using (SqlConnection connection = new SqlConnection(
    connectionString, commandString))  
{  
  connection.Open();  
  SqlCommand command = new SqlCommand(commandString);  
  SqlDataReader reader = command.ExecuteReader();  
  while (reader.Read())  
  {  
    // Retrieve the value of the Primary Key column.  
    int id = reader.GetInt32(0);  
  
    // Retrieve the value of the UDT.  
    LargeUDT udt = (LargeUDT)reader[1];  
  
    // You can also use GetSqlValue and GetValue.  
    // LargeUDT udt = (LargeUDT)reader.GetSqlValue(1);  
    // LargeUDT udt = (LargeUDT)reader.GetValue(1);  
  
    Console.WriteLine(  
     "ID={0} LargeUDT={1}", id, udt);  
  }  
reader.close  
}  
```  
  
```vb  
Using connection As New SqlConnection( _  
    connectionString, commandString)  
    connection.Open()  
    Dim command As New SqlCommand(commandString, connection)  
    Dim reader As SqlDataReader  
    reader = command.ExecuteReader  
  
    While reader.Read()  
      ' Retrieve the value of the Primary Key column.  
      Dim id As Int32 = reader.GetInt32(0)  
  
      ' Retrieve the value of the UDT.  
      Dim udt As LargeUDT = CType(reader(1), LargeUDT)  
  
     ' You can also use GetSqlValue and GetValue.  
     ' Dim udt As LargeUDT = CType(reader.GetSqlValue(1), LargeUDT)  
     ' Dim udt As LargeUDT = CType(reader.GetValue(1), LargeUDT)  
  
      ' Print values.  
      Console.WriteLine("ID={0} LargeUDT={1}", id, udt)  
    End While  
    reader.Close()  
End Using  
```  
  
## <a name="see-also"></a><span data-ttu-id="1dd83-159">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="1dd83-159">See also</span></span>

- [<span data-ttu-id="1dd83-160">Настройка параметров и типы данных параметров</span><span class="sxs-lookup"><span data-stu-id="1dd83-160">Configuring Parameters and Parameter Data Types</span></span>](../configuring-parameters-and-parameter-data-types.md)
- [<span data-ttu-id="1dd83-161">Извлечение сведений о схеме базы данных</span><span class="sxs-lookup"><span data-stu-id="1dd83-161">Retrieving Database Schema Information</span></span>](../retrieving-database-schema-information.md)
- [<span data-ttu-id="1dd83-162">Сопоставления типов данных SQL Server</span><span class="sxs-lookup"><span data-stu-id="1dd83-162">SQL Server Data Type Mappings</span></span>](../sql-server-data-type-mappings.md)
- [<span data-ttu-id="1dd83-163">SQL Server данные в двоичном и больших значениях</span><span class="sxs-lookup"><span data-stu-id="1dd83-163">SQL Server Binary and Large-Value Data</span></span>](sql-server-binary-and-large-value-data.md)
- [<span data-ttu-id="1dd83-164">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="1dd83-164">ADO.NET Overview</span></span>](../ado-net-overview.md)
