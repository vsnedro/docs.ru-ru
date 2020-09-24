---
title: Ограничения схемы
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 73d2980e-e73c-4987-913a-8ddc93d09144
ms.openlocfilehash: c0a3cafef45341cd95fa0a4f65c818129e120e44
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91147828"
---
# <a name="schema-restrictions"></a><span data-ttu-id="fb882-102">Ограничения схемы</span><span class="sxs-lookup"><span data-stu-id="fb882-102">Schema Restrictions</span></span>

<span data-ttu-id="fb882-103">Второй необязательный параметр метода **GetSchema** — это ограничения, которые используются для ограничения объема возвращаемых сведений о схеме и передаются в метод **GetSchema** в виде массива строк.</span><span class="sxs-lookup"><span data-stu-id="fb882-103">The second optional parameter of the **GetSchema** method is the restrictions that are used to limit the amount of schema information returned, and it is passed to the **GetSchema** method as an array of strings.</span></span> <span data-ttu-id="fb882-104">Позиция в массиве определяет значения, которые можно передать, и она эквивалентна номеру ограничения.</span><span class="sxs-lookup"><span data-stu-id="fb882-104">The position in the array determines the values that you can pass, and this is equivalent to the restriction number.</span></span>  
  
 <span data-ttu-id="fb882-105">Например, в приведенной ниже таблице описываются ограничения, поддерживаемые коллекцией схемы Tables, использующей поставщик данных .NET Framework для SQL Server.</span><span class="sxs-lookup"><span data-stu-id="fb882-105">For example, the following table describes the restrictions supported by the "Tables" schema collection using the .NET Framework Data Provider for SQL Server.</span></span> <span data-ttu-id="fb882-106">Дополнительные ограничения для коллекций схем SQL Server перечислены в конце данного раздела.</span><span class="sxs-lookup"><span data-stu-id="fb882-106">Additional restrictions for SQL Server schema collections are listed at the end of this topic.</span></span>  
  
|<span data-ttu-id="fb882-107">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="fb882-107">Restriction Name</span></span>|<span data-ttu-id="fb882-108">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="fb882-108">Parameter Name</span></span>|<span data-ttu-id="fb882-109">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="fb882-109">Restriction Default</span></span>|<span data-ttu-id="fb882-110">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="fb882-110">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="fb882-111">Каталог</span><span class="sxs-lookup"><span data-stu-id="fb882-111">Catalog</span></span>|@Catalog|<span data-ttu-id="fb882-112">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="fb882-112">TABLE_CATALOG</span></span>|<span data-ttu-id="fb882-113">1</span><span class="sxs-lookup"><span data-stu-id="fb882-113">1</span></span>|  
|<span data-ttu-id="fb882-114">Владелец</span><span class="sxs-lookup"><span data-stu-id="fb882-114">Owner</span></span>|@Owner|<span data-ttu-id="fb882-115">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="fb882-115">TABLE_SCHEMA</span></span>|<span data-ttu-id="fb882-116">2</span><span class="sxs-lookup"><span data-stu-id="fb882-116">2</span></span>|  
|<span data-ttu-id="fb882-117">Таблица</span><span class="sxs-lookup"><span data-stu-id="fb882-117">Table</span></span>|@Name|<span data-ttu-id="fb882-118">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="fb882-118">TABLE_NAME</span></span>|<span data-ttu-id="fb882-119">3</span><span class="sxs-lookup"><span data-stu-id="fb882-119">3</span></span>|  
|<span data-ttu-id="fb882-120">TableType</span><span class="sxs-lookup"><span data-stu-id="fb882-120">TableType</span></span>|@TableType|<span data-ttu-id="fb882-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="fb882-121">TABLE_TYPE</span></span>|<span data-ttu-id="fb882-122">4</span><span class="sxs-lookup"><span data-stu-id="fb882-122">4</span></span>|  
  
## <a name="specifying-restriction-values"></a><span data-ttu-id="fb882-123">Указание значений ограничения</span><span class="sxs-lookup"><span data-stu-id="fb882-123">Specifying Restriction Values</span></span>  

 <span data-ttu-id="fb882-124">Чтобы использовать одно из ограничений коллекции схем Tables, необходимо создать массив строк с четырьмя элементами, затем поместить значение в элемент, совпадающий с номером ограничения.</span><span class="sxs-lookup"><span data-stu-id="fb882-124">To use one of the restrictions of the "Tables" schema collection, simply create an array of strings with four elements, then place a value in the element that matches the restriction number.</span></span> <span data-ttu-id="fb882-125">Например, чтобы ограничить таблицы, возвращаемые **методом GetSchema** , только таблицами в схеме Sales, задайте для второго элемента массива значение Sales, прежде чем передать его в метод **GetSchema** .</span><span class="sxs-lookup"><span data-stu-id="fb882-125">For example, to restrict the tables returned by the **GetSchema** method to only those tables in the "Sales" schema, set the second element of the array to "Sales" before passing it to the **GetSchema** method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fb882-126">Коллекции ограничений для `SqlClient` и `OracleClient` имеют дополнительный столбец `ParameterName`.</span><span class="sxs-lookup"><span data-stu-id="fb882-126">The restrictions collections for `SqlClient` and `OracleClient` have an additional `ParameterName` column.</span></span> <span data-ttu-id="fb882-127">Столбец ограничения по умолчанию оставлен для обратной совместимости, но не учитывается.</span><span class="sxs-lookup"><span data-stu-id="fb882-127">The restriction default column is still there for backwards compatibility, but is currently ignored.</span></span> <span data-ttu-id="fb882-128">Чтобы свести к минимуму вероятности проведения атак путем внедрения кода SQL, при указании значений ограничений следует использовать параметризированные запросы, а не замену строк.</span><span class="sxs-lookup"><span data-stu-id="fb882-128">Parameterized queries rather than string replacement should be used to minimize the risk of an SQL injection attack when specifying restriction values.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fb882-129">Количество элементов в массиве должно быть меньше или равно количеству ограничений, поддерживаемых специальной коллекцией схем, в противном случае возникнет исключение <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="fb882-129">The number of elements in the array must be less than or equal to the number of restrictions supported for the specified schema collection else an <xref:System.ArgumentException> will be thrown.</span></span> <span data-ttu-id="fb882-130">Их может быть меньше максимального количества ограничений.</span><span class="sxs-lookup"><span data-stu-id="fb882-130">There can be fewer than the maximum number of restrictions.</span></span> <span data-ttu-id="fb882-131">Предполагается, что отсутствующие ограничения имеют значение NULL (без ограничений).</span><span class="sxs-lookup"><span data-stu-id="fb882-131">The missing restrictions are assumed to be null (unrestricted).</span></span>  
  
 <span data-ttu-id="fb882-132">Можно запросить управляемый поставщик .NET Framework, чтобы определить список поддерживаемых ограничений, вызвав метод **GetSchema** с именем коллекции схем ограничений, которая является "ограничениями".</span><span class="sxs-lookup"><span data-stu-id="fb882-132">You can query a .NET Framework managed provider to determine the list of supported restrictions by calling the **GetSchema** method with the name of the restrictions schema collection, which is "Restrictions".</span></span> <span data-ttu-id="fb882-133">Будет возвращен объект <xref:System.Data.DataTable> со списком имен коллекций и ограничений, значениями ограничений по умолчанию и номерами ограничений.</span><span class="sxs-lookup"><span data-stu-id="fb882-133">This will return a <xref:System.Data.DataTable> with a list of the collection names, the restriction names, the default restriction values, and the restriction numbers.</span></span>  
  
### <a name="example"></a><span data-ttu-id="fb882-134">Пример</span><span class="sxs-lookup"><span data-stu-id="fb882-134">Example</span></span>  

 <span data-ttu-id="fb882-135">В следующих примерах показано, как использовать <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> метод поставщика данных .NET Framework для класса SQL Server, <xref:System.Data.SqlClient.SqlConnection> чтобы получить сведения о схеме всех таблиц, содержащихся в образце базы данных **AdventureWorks** , а также ограничить сведения, возвращаемые только таблицам в схеме Sales:</span><span class="sxs-lookup"><span data-stu-id="fb882-135">The following examples demonstrate how to use the <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> method of the .NET Framework Data Provider for the SQL Server <xref:System.Data.SqlClient.SqlConnection> class to retrieve schema information about all of the tables contained in the **AdventureWorks** sample database, and to restrict the information returned to only those tables in the "Sales" schema:</span></span>  
  
```vb  
Imports System.Data.SqlClient  
  
Module Module1  
Sub Main()  
  Dim connectionString As String = _  
    "Data Source=(local);Database=AdventureWorks;" & _  
       "Integrated Security=true;";  
  
  Dim restrictions(3) As String  
  Using connection As New SqlConnection(connectionString)  
    connection.Open()  
  
    'Specify the restrictions.  
    restrictions(1) = "Sales"  
    Dim table As DataTable = connection.GetSchema("Tables", _  
       restrictions)  
  
    ' Display the contents of the table.  
      For Each row As DataRow In table.Rows  
         For Each col As DataColumn In table.Columns  
            Console.WriteLine("{0} = {1}", col.ColumnName, row(col))  
         Next  
         Console.WriteLine("============================")  
      Next  
    Console.WriteLine("Press any key to continue.")  
    Console.ReadKey()  
  End Using  
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
    string connectionString =
       "Data Source=(local);Database=AdventureWorks;" +  
       "Integrated Security=true;";  
    using (SqlConnection connection =  
       new SqlConnection(connectionString))  
    {  
        connection.Open();  
  
        // Specify the restrictions.  
        string[] restrictions = new string[4];  
        restrictions[1] = "Sales";  
        System.Data.DataTable table = connection.GetSchema(  
          "Tables", restrictions);  
  
        // Display the contents of the table.  
        foreach (System.Data.DataRow row in table.Rows)  
        {  
            foreach (System.Data.DataColumn col in table.Columns)  
            {  
                Console.WriteLine("{0} = {1}",
                  col.ColumnName, row[col]);  
            }  
            Console.WriteLine("============================");  
        }  
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
  
## <a name="sql-server-schema-restrictions"></a><span data-ttu-id="fb882-136">Ограничения схемы SQL Server</span><span class="sxs-lookup"><span data-stu-id="fb882-136">SQL Server Schema Restrictions</span></span>  

 <span data-ttu-id="fb882-137">В приведенных ниже таблицах перечислены ограничения коллекций схем SQL Server.</span><span class="sxs-lookup"><span data-stu-id="fb882-137">The following tables list the restrictions for SQL Server schema collections.</span></span>  
  
### <a name="users"></a><span data-ttu-id="fb882-138">Пользователи</span><span class="sxs-lookup"><span data-stu-id="fb882-138">Users</span></span>  
  
|<span data-ttu-id="fb882-139">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="fb882-139">Restriction Name</span></span>|<span data-ttu-id="fb882-140">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="fb882-140">Parameter Name</span></span>|<span data-ttu-id="fb882-141">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="fb882-141">Restriction Default</span></span>|<span data-ttu-id="fb882-142">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="fb882-142">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="fb882-143">User_Name</span><span class="sxs-lookup"><span data-stu-id="fb882-143">User_Name</span></span>|@Name|<span data-ttu-id="fb882-144">name</span><span class="sxs-lookup"><span data-stu-id="fb882-144">name</span></span>|<span data-ttu-id="fb882-145">1</span><span class="sxs-lookup"><span data-stu-id="fb882-145">1</span></span>|  
  
### <a name="databases"></a><span data-ttu-id="fb882-146">Базы данных</span><span class="sxs-lookup"><span data-stu-id="fb882-146">Databases</span></span>  
  
|<span data-ttu-id="fb882-147">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="fb882-147">Restriction Name</span></span>|<span data-ttu-id="fb882-148">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="fb882-148">Parameter Name</span></span>|<span data-ttu-id="fb882-149">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="fb882-149">Restriction Default</span></span>|<span data-ttu-id="fb882-150">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="fb882-150">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="fb882-151">Имя</span><span class="sxs-lookup"><span data-stu-id="fb882-151">Name</span></span>|@Name|<span data-ttu-id="fb882-152">Имя</span><span class="sxs-lookup"><span data-stu-id="fb882-152">Name</span></span>|<span data-ttu-id="fb882-153">1</span><span class="sxs-lookup"><span data-stu-id="fb882-153">1</span></span>|  
  
### <a name="tables"></a><span data-ttu-id="fb882-154">Таблицы</span><span class="sxs-lookup"><span data-stu-id="fb882-154">Tables</span></span>  
  
|<span data-ttu-id="fb882-155">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="fb882-155">Restriction Name</span></span>|<span data-ttu-id="fb882-156">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="fb882-156">Parameter Name</span></span>|<span data-ttu-id="fb882-157">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="fb882-157">Restriction Default</span></span>|<span data-ttu-id="fb882-158">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="fb882-158">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="fb882-159">Каталог</span><span class="sxs-lookup"><span data-stu-id="fb882-159">Catalog</span></span>|@Catalog|<span data-ttu-id="fb882-160">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="fb882-160">TABLE_CATALOG</span></span>|<span data-ttu-id="fb882-161">1</span><span class="sxs-lookup"><span data-stu-id="fb882-161">1</span></span>|  
|<span data-ttu-id="fb882-162">Владелец</span><span class="sxs-lookup"><span data-stu-id="fb882-162">Owner</span></span>|@Owner|<span data-ttu-id="fb882-163">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="fb882-163">TABLE_SCHEMA</span></span>|<span data-ttu-id="fb882-164">2</span><span class="sxs-lookup"><span data-stu-id="fb882-164">2</span></span>|  
|<span data-ttu-id="fb882-165">Таблица</span><span class="sxs-lookup"><span data-stu-id="fb882-165">Table</span></span>|@Name|<span data-ttu-id="fb882-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="fb882-166">TABLE_NAME</span></span>|<span data-ttu-id="fb882-167">3</span><span class="sxs-lookup"><span data-stu-id="fb882-167">3</span></span>|  
|<span data-ttu-id="fb882-168">TableType</span><span class="sxs-lookup"><span data-stu-id="fb882-168">TableType</span></span>|@TableType|<span data-ttu-id="fb882-169">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="fb882-169">TABLE_TYPE</span></span>|<span data-ttu-id="fb882-170">4</span><span class="sxs-lookup"><span data-stu-id="fb882-170">4</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="fb882-171">Столбцы</span><span class="sxs-lookup"><span data-stu-id="fb882-171">Columns</span></span>  
  
|<span data-ttu-id="fb882-172">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="fb882-172">Restriction Name</span></span>|<span data-ttu-id="fb882-173">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="fb882-173">Parameter Name</span></span>|<span data-ttu-id="fb882-174">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="fb882-174">Restriction Default</span></span>|<span data-ttu-id="fb882-175">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="fb882-175">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="fb882-176">Каталог</span><span class="sxs-lookup"><span data-stu-id="fb882-176">Catalog</span></span>|@Catalog|<span data-ttu-id="fb882-177">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="fb882-177">TABLE_CATALOG</span></span>|<span data-ttu-id="fb882-178">1</span><span class="sxs-lookup"><span data-stu-id="fb882-178">1</span></span>|  
|<span data-ttu-id="fb882-179">Владелец</span><span class="sxs-lookup"><span data-stu-id="fb882-179">Owner</span></span>|@Owner|<span data-ttu-id="fb882-180">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="fb882-180">TABLE_SCHEMA</span></span>|<span data-ttu-id="fb882-181">2</span><span class="sxs-lookup"><span data-stu-id="fb882-181">2</span></span>|  
|<span data-ttu-id="fb882-182">Таблица</span><span class="sxs-lookup"><span data-stu-id="fb882-182">Table</span></span>|@Table|<span data-ttu-id="fb882-183">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="fb882-183">TABLE_NAME</span></span>|<span data-ttu-id="fb882-184">3</span><span class="sxs-lookup"><span data-stu-id="fb882-184">3</span></span>|  
|<span data-ttu-id="fb882-185">Столбец</span><span class="sxs-lookup"><span data-stu-id="fb882-185">Column</span></span>|@Column|<span data-ttu-id="fb882-186">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="fb882-186">COLUMN_NAME</span></span>|<span data-ttu-id="fb882-187">4</span><span class="sxs-lookup"><span data-stu-id="fb882-187">4</span></span>|  
  
### <a name="structuredtypemembers"></a><span data-ttu-id="fb882-188">StructuredTypeMembers</span><span class="sxs-lookup"><span data-stu-id="fb882-188">StructuredTypeMembers</span></span>  
  
|<span data-ttu-id="fb882-189">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="fb882-189">Restriction Name</span></span>|<span data-ttu-id="fb882-190">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="fb882-190">Parameter Name</span></span>|<span data-ttu-id="fb882-191">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="fb882-191">Restriction Default</span></span>|<span data-ttu-id="fb882-192">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="fb882-192">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="fb882-193">Каталог</span><span class="sxs-lookup"><span data-stu-id="fb882-193">Catalog</span></span>|@Catalog|<span data-ttu-id="fb882-194">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="fb882-194">TABLE_CATALOG</span></span>|<span data-ttu-id="fb882-195">1</span><span class="sxs-lookup"><span data-stu-id="fb882-195">1</span></span>|  
|<span data-ttu-id="fb882-196">Владелец</span><span class="sxs-lookup"><span data-stu-id="fb882-196">Owner</span></span>|@Owner|<span data-ttu-id="fb882-197">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="fb882-197">TABLE_SCHEMA</span></span>|<span data-ttu-id="fb882-198">2</span><span class="sxs-lookup"><span data-stu-id="fb882-198">2</span></span>|  
|<span data-ttu-id="fb882-199">Таблица</span><span class="sxs-lookup"><span data-stu-id="fb882-199">Table</span></span>|@Table|<span data-ttu-id="fb882-200">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="fb882-200">TABLE_NAME</span></span>|<span data-ttu-id="fb882-201">3</span><span class="sxs-lookup"><span data-stu-id="fb882-201">3</span></span>|  
|<span data-ttu-id="fb882-202">Столбец</span><span class="sxs-lookup"><span data-stu-id="fb882-202">Column</span></span>|@Column|<span data-ttu-id="fb882-203">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="fb882-203">COLUMN_NAME</span></span>|<span data-ttu-id="fb882-204">4</span><span class="sxs-lookup"><span data-stu-id="fb882-204">4</span></span>|  
  
### <a name="views"></a><span data-ttu-id="fb882-205">Представления</span><span class="sxs-lookup"><span data-stu-id="fb882-205">Views</span></span>  
  
|<span data-ttu-id="fb882-206">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="fb882-206">Restriction Name</span></span>|<span data-ttu-id="fb882-207">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="fb882-207">Parameter Name</span></span>|<span data-ttu-id="fb882-208">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="fb882-208">Restriction Default</span></span>|<span data-ttu-id="fb882-209">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="fb882-209">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="fb882-210">Каталог</span><span class="sxs-lookup"><span data-stu-id="fb882-210">Catalog</span></span>|@Catalog|<span data-ttu-id="fb882-211">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="fb882-211">TABLE_CATALOG</span></span>|<span data-ttu-id="fb882-212">1</span><span class="sxs-lookup"><span data-stu-id="fb882-212">1</span></span>|  
|<span data-ttu-id="fb882-213">Владелец</span><span class="sxs-lookup"><span data-stu-id="fb882-213">Owner</span></span>|@Owner|<span data-ttu-id="fb882-214">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="fb882-214">TABLE_SCHEMA</span></span>|<span data-ttu-id="fb882-215">2</span><span class="sxs-lookup"><span data-stu-id="fb882-215">2</span></span>|  
|<span data-ttu-id="fb882-216">Таблица</span><span class="sxs-lookup"><span data-stu-id="fb882-216">Table</span></span>|@Table|<span data-ttu-id="fb882-217">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="fb882-217">TABLE_NAME</span></span>|<span data-ttu-id="fb882-218">3</span><span class="sxs-lookup"><span data-stu-id="fb882-218">3</span></span>|  
  
### <a name="viewcolumns"></a><span data-ttu-id="fb882-219">ViewColumns</span><span class="sxs-lookup"><span data-stu-id="fb882-219">ViewColumns</span></span>  
  
|<span data-ttu-id="fb882-220">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="fb882-220">Restriction Name</span></span>|<span data-ttu-id="fb882-221">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="fb882-221">Parameter Name</span></span>|<span data-ttu-id="fb882-222">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="fb882-222">Restriction Default</span></span>|<span data-ttu-id="fb882-223">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="fb882-223">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="fb882-224">Каталог</span><span class="sxs-lookup"><span data-stu-id="fb882-224">Catalog</span></span>|@Catalog|<span data-ttu-id="fb882-225">VIEW_CATALOG</span><span class="sxs-lookup"><span data-stu-id="fb882-225">VIEW_CATALOG</span></span>|<span data-ttu-id="fb882-226">1</span><span class="sxs-lookup"><span data-stu-id="fb882-226">1</span></span>|  
|<span data-ttu-id="fb882-227">Владелец</span><span class="sxs-lookup"><span data-stu-id="fb882-227">Owner</span></span>|@Owner|<span data-ttu-id="fb882-228">VIEW_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="fb882-228">VIEW_SCHEMA</span></span>|<span data-ttu-id="fb882-229">2</span><span class="sxs-lookup"><span data-stu-id="fb882-229">2</span></span>|  
|<span data-ttu-id="fb882-230">Таблица</span><span class="sxs-lookup"><span data-stu-id="fb882-230">Table</span></span>|@Table|<span data-ttu-id="fb882-231">VIEW_NAME</span><span class="sxs-lookup"><span data-stu-id="fb882-231">VIEW_NAME</span></span>|<span data-ttu-id="fb882-232">3</span><span class="sxs-lookup"><span data-stu-id="fb882-232">3</span></span>|  
|<span data-ttu-id="fb882-233">Столбец</span><span class="sxs-lookup"><span data-stu-id="fb882-233">Column</span></span>|@Column|<span data-ttu-id="fb882-234">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="fb882-234">COLUMN_NAME</span></span>|<span data-ttu-id="fb882-235">4</span><span class="sxs-lookup"><span data-stu-id="fb882-235">4</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="fb882-236">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="fb882-236">ProcedureParameters</span></span>  
  
|<span data-ttu-id="fb882-237">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="fb882-237">Restriction Name</span></span>|<span data-ttu-id="fb882-238">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="fb882-238">Parameter Name</span></span>|<span data-ttu-id="fb882-239">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="fb882-239">Restriction Default</span></span>|<span data-ttu-id="fb882-240">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="fb882-240">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="fb882-241">Каталог</span><span class="sxs-lookup"><span data-stu-id="fb882-241">Catalog</span></span>|@Catalog|<span data-ttu-id="fb882-242">SPECIFIC_CATALOG</span><span class="sxs-lookup"><span data-stu-id="fb882-242">SPECIFIC_CATALOG</span></span>|<span data-ttu-id="fb882-243">1</span><span class="sxs-lookup"><span data-stu-id="fb882-243">1</span></span>|  
|<span data-ttu-id="fb882-244">Владелец</span><span class="sxs-lookup"><span data-stu-id="fb882-244">Owner</span></span>|@Owner|<span data-ttu-id="fb882-245">SPECIFIC_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="fb882-245">SPECIFIC_SCHEMA</span></span>|<span data-ttu-id="fb882-246">2</span><span class="sxs-lookup"><span data-stu-id="fb882-246">2</span></span>|  
|<span data-ttu-id="fb882-247">Имя</span><span class="sxs-lookup"><span data-stu-id="fb882-247">Name</span></span>|@Name|<span data-ttu-id="fb882-248">SPECIFIC_NAME</span><span class="sxs-lookup"><span data-stu-id="fb882-248">SPECIFIC_NAME</span></span>|<span data-ttu-id="fb882-249">3</span><span class="sxs-lookup"><span data-stu-id="fb882-249">3</span></span>|  
|<span data-ttu-id="fb882-250">Параметр</span><span class="sxs-lookup"><span data-stu-id="fb882-250">Parameter</span></span>|@Parameter|<span data-ttu-id="fb882-251">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="fb882-251">PARAMETER_NAME</span></span>|<span data-ttu-id="fb882-252">4</span><span class="sxs-lookup"><span data-stu-id="fb882-252">4</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="fb882-253">Процедуры</span><span class="sxs-lookup"><span data-stu-id="fb882-253">Procedures</span></span>  
  
|<span data-ttu-id="fb882-254">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="fb882-254">Restriction Name</span></span>|<span data-ttu-id="fb882-255">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="fb882-255">Parameter Name</span></span>|<span data-ttu-id="fb882-256">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="fb882-256">Restriction Default</span></span>|<span data-ttu-id="fb882-257">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="fb882-257">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="fb882-258">Каталог</span><span class="sxs-lookup"><span data-stu-id="fb882-258">Catalog</span></span>|@Catalog|<span data-ttu-id="fb882-259">SPECIFIC_CATALOG</span><span class="sxs-lookup"><span data-stu-id="fb882-259">SPECIFIC_CATALOG</span></span>|<span data-ttu-id="fb882-260">1</span><span class="sxs-lookup"><span data-stu-id="fb882-260">1</span></span>|  
|<span data-ttu-id="fb882-261">Владелец</span><span class="sxs-lookup"><span data-stu-id="fb882-261">Owner</span></span>|@Owner|<span data-ttu-id="fb882-262">SPECIFIC_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="fb882-262">SPECIFIC_SCHEMA</span></span>|<span data-ttu-id="fb882-263">2</span><span class="sxs-lookup"><span data-stu-id="fb882-263">2</span></span>|  
|<span data-ttu-id="fb882-264">Имя</span><span class="sxs-lookup"><span data-stu-id="fb882-264">Name</span></span>|@Name|<span data-ttu-id="fb882-265">SPECIFIC_NAME</span><span class="sxs-lookup"><span data-stu-id="fb882-265">SPECIFIC_NAME</span></span>|<span data-ttu-id="fb882-266">3</span><span class="sxs-lookup"><span data-stu-id="fb882-266">3</span></span>|  
|<span data-ttu-id="fb882-267">Type</span><span class="sxs-lookup"><span data-stu-id="fb882-267">Type</span></span>|@Type|<span data-ttu-id="fb882-268">ROUTINE_TYPE</span><span class="sxs-lookup"><span data-stu-id="fb882-268">ROUTINE_TYPE</span></span>|<span data-ttu-id="fb882-269">4</span><span class="sxs-lookup"><span data-stu-id="fb882-269">4</span></span>|  
  
### <a name="indexcolumns"></a><span data-ttu-id="fb882-270">IndexColumns</span><span class="sxs-lookup"><span data-stu-id="fb882-270">IndexColumns</span></span>  
  
|<span data-ttu-id="fb882-271">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="fb882-271">Restriction Name</span></span>|<span data-ttu-id="fb882-272">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="fb882-272">Parameter Name</span></span>|<span data-ttu-id="fb882-273">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="fb882-273">Restriction Default</span></span>|<span data-ttu-id="fb882-274">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="fb882-274">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="fb882-275">Каталог</span><span class="sxs-lookup"><span data-stu-id="fb882-275">Catalog</span></span>|@Catalog|<span data-ttu-id="fb882-276">db_name()</span><span class="sxs-lookup"><span data-stu-id="fb882-276">db_name()</span></span>|<span data-ttu-id="fb882-277">1</span><span class="sxs-lookup"><span data-stu-id="fb882-277">1</span></span>|  
|<span data-ttu-id="fb882-278">Владелец</span><span class="sxs-lookup"><span data-stu-id="fb882-278">Owner</span></span>|@Owner|<span data-ttu-id="fb882-279">user_name()</span><span class="sxs-lookup"><span data-stu-id="fb882-279">user_name()</span></span>|<span data-ttu-id="fb882-280">2</span><span class="sxs-lookup"><span data-stu-id="fb882-280">2</span></span>|  
|<span data-ttu-id="fb882-281">Таблица</span><span class="sxs-lookup"><span data-stu-id="fb882-281">Table</span></span>|@Table|<span data-ttu-id="fb882-282">o.name</span><span class="sxs-lookup"><span data-stu-id="fb882-282">o.name</span></span>|<span data-ttu-id="fb882-283">3</span><span class="sxs-lookup"><span data-stu-id="fb882-283">3</span></span>|  
|<span data-ttu-id="fb882-284">ConstraintName</span><span class="sxs-lookup"><span data-stu-id="fb882-284">ConstraintName</span></span>|@ConstraintName|<span data-ttu-id="fb882-285">x.name</span><span class="sxs-lookup"><span data-stu-id="fb882-285">x.name</span></span>|<span data-ttu-id="fb882-286">4</span><span class="sxs-lookup"><span data-stu-id="fb882-286">4</span></span>|  
|<span data-ttu-id="fb882-287">Столбец</span><span class="sxs-lookup"><span data-stu-id="fb882-287">Column</span></span>|@Column|<span data-ttu-id="fb882-288">c.name</span><span class="sxs-lookup"><span data-stu-id="fb882-288">c.name</span></span>|<span data-ttu-id="fb882-289">5</span><span class="sxs-lookup"><span data-stu-id="fb882-289">5</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="fb882-290">Индексы</span><span class="sxs-lookup"><span data-stu-id="fb882-290">Indexes</span></span>  
  
|<span data-ttu-id="fb882-291">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="fb882-291">Restriction Name</span></span>|<span data-ttu-id="fb882-292">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="fb882-292">Parameter Name</span></span>|<span data-ttu-id="fb882-293">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="fb882-293">Restriction Default</span></span>|<span data-ttu-id="fb882-294">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="fb882-294">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="fb882-295">Каталог</span><span class="sxs-lookup"><span data-stu-id="fb882-295">Catalog</span></span>|@Catalog|<span data-ttu-id="fb882-296">db_name()</span><span class="sxs-lookup"><span data-stu-id="fb882-296">db_name()</span></span>|<span data-ttu-id="fb882-297">1</span><span class="sxs-lookup"><span data-stu-id="fb882-297">1</span></span>|  
|<span data-ttu-id="fb882-298">Владелец</span><span class="sxs-lookup"><span data-stu-id="fb882-298">Owner</span></span>|@Owner|<span data-ttu-id="fb882-299">user_name()</span><span class="sxs-lookup"><span data-stu-id="fb882-299">user_name()</span></span>|<span data-ttu-id="fb882-300">2</span><span class="sxs-lookup"><span data-stu-id="fb882-300">2</span></span>|  
|<span data-ttu-id="fb882-301">Таблица</span><span class="sxs-lookup"><span data-stu-id="fb882-301">Table</span></span>|@Table|<span data-ttu-id="fb882-302">o.name</span><span class="sxs-lookup"><span data-stu-id="fb882-302">o.name</span></span>|<span data-ttu-id="fb882-303">3</span><span class="sxs-lookup"><span data-stu-id="fb882-303">3</span></span>|  
  
### <a name="userdefinedtypes"></a><span data-ttu-id="fb882-304">UserDefinedTypes</span><span class="sxs-lookup"><span data-stu-id="fb882-304">UserDefinedTypes</span></span>  
  
|<span data-ttu-id="fb882-305">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="fb882-305">Restriction Name</span></span>|<span data-ttu-id="fb882-306">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="fb882-306">Parameter Name</span></span>|<span data-ttu-id="fb882-307">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="fb882-307">Restriction Default</span></span>|<span data-ttu-id="fb882-308">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="fb882-308">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="fb882-309">assembly_name</span><span class="sxs-lookup"><span data-stu-id="fb882-309">assembly_name</span></span>|@AssemblyName|<span data-ttu-id="fb882-310">assemblies.name</span><span class="sxs-lookup"><span data-stu-id="fb882-310">assemblies.name</span></span>|<span data-ttu-id="fb882-311">1</span><span class="sxs-lookup"><span data-stu-id="fb882-311">1</span></span>|  
|<span data-ttu-id="fb882-312">udt_name</span><span class="sxs-lookup"><span data-stu-id="fb882-312">udt_name</span></span>|@UDTName|<span data-ttu-id="fb882-313">types.assembly_class</span><span class="sxs-lookup"><span data-stu-id="fb882-313">types.assembly_class</span></span>|<span data-ttu-id="fb882-314">2</span><span class="sxs-lookup"><span data-stu-id="fb882-314">2</span></span>|  
  
### <a name="foreignkeys"></a><span data-ttu-id="fb882-315">ForeignKeys</span><span class="sxs-lookup"><span data-stu-id="fb882-315">ForeignKeys</span></span>  
  
|<span data-ttu-id="fb882-316">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="fb882-316">Restriction Name</span></span>|<span data-ttu-id="fb882-317">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="fb882-317">Parameter Name</span></span>|<span data-ttu-id="fb882-318">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="fb882-318">Restriction Default</span></span>|<span data-ttu-id="fb882-319">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="fb882-319">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="fb882-320">Каталог</span><span class="sxs-lookup"><span data-stu-id="fb882-320">Catalog</span></span>|@Catalog|<span data-ttu-id="fb882-321">CONSTRAINT_CATALOG</span><span class="sxs-lookup"><span data-stu-id="fb882-321">CONSTRAINT_CATALOG</span></span>|<span data-ttu-id="fb882-322">1</span><span class="sxs-lookup"><span data-stu-id="fb882-322">1</span></span>|  
|<span data-ttu-id="fb882-323">Владелец</span><span class="sxs-lookup"><span data-stu-id="fb882-323">Owner</span></span>|@Owner|<span data-ttu-id="fb882-324">CONSTRAINT_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="fb882-324">CONSTRAINT_SCHEMA</span></span>|<span data-ttu-id="fb882-325">2</span><span class="sxs-lookup"><span data-stu-id="fb882-325">2</span></span>|  
|<span data-ttu-id="fb882-326">Таблица</span><span class="sxs-lookup"><span data-stu-id="fb882-326">Table</span></span>|@Table|<span data-ttu-id="fb882-327">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="fb882-327">TABLE_NAME</span></span>|<span data-ttu-id="fb882-328">3</span><span class="sxs-lookup"><span data-stu-id="fb882-328">3</span></span>|  
|<span data-ttu-id="fb882-329">Имя</span><span class="sxs-lookup"><span data-stu-id="fb882-329">Name</span></span>|@Name|<span data-ttu-id="fb882-330">CONSTRAINT_NAME</span><span class="sxs-lookup"><span data-stu-id="fb882-330">CONSTRAINT_NAME</span></span>|<span data-ttu-id="fb882-331">4</span><span class="sxs-lookup"><span data-stu-id="fb882-331">4</span></span>|  
  
## <a name="sql-server-2008-schema-restrictions"></a><span data-ttu-id="fb882-332">Ограничения схемы SQL Server 2008</span><span class="sxs-lookup"><span data-stu-id="fb882-332">SQL Server 2008 Schema Restrictions</span></span>  

 <span data-ttu-id="fb882-333">В приведенных ниже таблицах перечислены ограничения коллекций схем SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="fb882-333">The following tables list the restrictions for SQL Server 2008 schema collections.</span></span> <span data-ttu-id="fb882-334">Эти ограничения действуют, начиная с версии .NET Framework 3.5 с пакетом обновления 1 (SP1) и SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="fb882-334">These restrictions are valid beginning with version 3.5 SP1 of the .NET Framework and SQL Server 2008.</span></span> <span data-ttu-id="fb882-335">Они не поддерживаются в предыдущих версиях .NET Framework и SQL Server.</span><span class="sxs-lookup"><span data-stu-id="fb882-335">They are not supported in earlier versions of the .NET Framework and SQL Server.</span></span>  
  
### <a name="columnsetcolumns"></a><span data-ttu-id="fb882-336">ColumnSetColumns</span><span class="sxs-lookup"><span data-stu-id="fb882-336">ColumnSetColumns</span></span>  
  
|<span data-ttu-id="fb882-337">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="fb882-337">Restriction Name</span></span>|<span data-ttu-id="fb882-338">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="fb882-338">Parameter Name</span></span>|<span data-ttu-id="fb882-339">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="fb882-339">Restriction Default</span></span>|<span data-ttu-id="fb882-340">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="fb882-340">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="fb882-341">Каталог</span><span class="sxs-lookup"><span data-stu-id="fb882-341">Catalog</span></span>|@Catalog|<span data-ttu-id="fb882-342">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="fb882-342">TABLE_CATALOG</span></span>|<span data-ttu-id="fb882-343">1</span><span class="sxs-lookup"><span data-stu-id="fb882-343">1</span></span>|  
|<span data-ttu-id="fb882-344">Владелец</span><span class="sxs-lookup"><span data-stu-id="fb882-344">Owner</span></span>|@Owner|<span data-ttu-id="fb882-345">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="fb882-345">TABLE_SCHEMA</span></span>|<span data-ttu-id="fb882-346">2</span><span class="sxs-lookup"><span data-stu-id="fb882-346">2</span></span>|  
|<span data-ttu-id="fb882-347">Таблица</span><span class="sxs-lookup"><span data-stu-id="fb882-347">Table</span></span>|@Table|<span data-ttu-id="fb882-348">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="fb882-348">TABLE_NAME</span></span>|<span data-ttu-id="fb882-349">3</span><span class="sxs-lookup"><span data-stu-id="fb882-349">3</span></span>|  
  
### <a name="allcolumns"></a><span data-ttu-id="fb882-350">AllColumns</span><span class="sxs-lookup"><span data-stu-id="fb882-350">AllColumns</span></span>  
  
|<span data-ttu-id="fb882-351">Имя ограничения</span><span class="sxs-lookup"><span data-stu-id="fb882-351">Restriction Name</span></span>|<span data-ttu-id="fb882-352">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="fb882-352">Parameter Name</span></span>|<span data-ttu-id="fb882-353">Значение ограничения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="fb882-353">Restriction Default</span></span>|<span data-ttu-id="fb882-354">Номер ограничения</span><span class="sxs-lookup"><span data-stu-id="fb882-354">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="fb882-355">Каталог</span><span class="sxs-lookup"><span data-stu-id="fb882-355">Catalog</span></span>|@Catalog|<span data-ttu-id="fb882-356">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="fb882-356">TABLE_CATALOG</span></span>|<span data-ttu-id="fb882-357">1</span><span class="sxs-lookup"><span data-stu-id="fb882-357">1</span></span>|  
|<span data-ttu-id="fb882-358">Владелец</span><span class="sxs-lookup"><span data-stu-id="fb882-358">Owner</span></span>|@Owner|<span data-ttu-id="fb882-359">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="fb882-359">TABLE_SCHEMA</span></span>|<span data-ttu-id="fb882-360">2</span><span class="sxs-lookup"><span data-stu-id="fb882-360">2</span></span>|  
|<span data-ttu-id="fb882-361">Таблица</span><span class="sxs-lookup"><span data-stu-id="fb882-361">Table</span></span>|@Table|<span data-ttu-id="fb882-362">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="fb882-362">TABLE_NAME</span></span>|<span data-ttu-id="fb882-363">3</span><span class="sxs-lookup"><span data-stu-id="fb882-363">3</span></span>|  
|<span data-ttu-id="fb882-364">Столбец</span><span class="sxs-lookup"><span data-stu-id="fb882-364">Column</span></span>|@Column|<span data-ttu-id="fb882-365">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="fb882-365">COLUMN_NAME</span></span>|<span data-ttu-id="fb882-366">4</span><span class="sxs-lookup"><span data-stu-id="fb882-366">4</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fb882-367">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="fb882-367">See also</span></span>

- [<span data-ttu-id="fb882-368">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="fb882-368">ADO.NET Overview</span></span>](ado-net-overview.md)
