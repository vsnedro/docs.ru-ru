---
title: Изменение данных с помощью хранимых процедур
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7d8e9a46-1af6-4a02-bf61-969d77ae07e0
ms.openlocfilehash: 65116a48533fd6ce86894c6a4522929285f8e1f0
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91150756"
---
# <a name="modifying-data-with-stored-procedures"></a><span data-ttu-id="9b339-102">Изменение данных с помощью хранимых процедур</span><span class="sxs-lookup"><span data-stu-id="9b339-102">Modifying Data with Stored Procedures</span></span>

<span data-ttu-id="9b339-103">Хранимые процедуры могут принимать данные в виде входных параметров и возвращать их в виде выходных параметров, результирующих наборов или возвращаемых значений.</span><span class="sxs-lookup"><span data-stu-id="9b339-103">Stored procedures can accept data as input parameters and can return data as output parameters, result sets, or return values.</span></span> <span data-ttu-id="9b339-104">Образец, приведенный ниже, показывает, как ADO.NET отправляет и получает входные и выходные параметры, а также возвращаемые значения.</span><span class="sxs-lookup"><span data-stu-id="9b339-104">The sample below illustrates how ADO.NET sends and receives input parameters, output parameters, and return values.</span></span> <span data-ttu-id="9b339-105">Пример добавляет в таблицу новую запись, где столбец первичного ключа является столбцом идентификаторов в базе данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="9b339-105">The example inserts a new record into a table where the primary key column is an identity column in a SQL Server database.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9b339-106">При использовании хранимых процедур SQL Server для изменения или удаления данных с помощью <xref:System.Data.SqlClient.SqlDataAdapter> убедитесь, что в определении хранимой процедуры не указана инструкция SET NOCOUNT ON.</span><span class="sxs-lookup"><span data-stu-id="9b339-106">If you are using SQL Server stored procedures to edit or delete data using a <xref:System.Data.SqlClient.SqlDataAdapter>, make sure that you do not use SET NOCOUNT ON in the stored procedure definition.</span></span> <span data-ttu-id="9b339-107">В таком случае возвращается число затронутых строк, равное нулю, что `DataAdapter` интерпретирует как конфликт параллелизма.</span><span class="sxs-lookup"><span data-stu-id="9b339-107">This causes the rows affected count returned to be zero, which the `DataAdapter` interprets as a concurrency conflict.</span></span> <span data-ttu-id="9b339-108">Это событие вызовет исключение <xref:System.Data.DBConcurrencyException>.</span><span class="sxs-lookup"><span data-stu-id="9b339-108">In this event, a <xref:System.Data.DBConcurrencyException> will be thrown.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9b339-109">Пример</span><span class="sxs-lookup"><span data-stu-id="9b339-109">Example</span></span>  

 <span data-ttu-id="9b339-110">В примере используется следующая хранимая процедура для вставки новой категории в таблицу категорий **Northwind** **Categories** .</span><span class="sxs-lookup"><span data-stu-id="9b339-110">The sample uses the following stored procedure to insert a new category into the **Northwind** **Categories** table.</span></span> <span data-ttu-id="9b339-111">Хранимая процедура принимает значение в столбце **CategoryName** в качестве входного параметра и использует функцию SCOPE_IDENTITY (), чтобы получить новое значение поля Identity, **CategoryID**и вернуть его в выходной параметр.</span><span class="sxs-lookup"><span data-stu-id="9b339-111">The stored procedure takes the value in the **CategoryName** column as an input parameter and uses the SCOPE_IDENTITY() function to retrieve the new value of the identity field, **CategoryID**, and return it in an output parameter.</span></span> <span data-ttu-id="9b339-112">Оператор RETURN использует @ROWCOUNT функцию @ для возврата количества вставленных строк.</span><span class="sxs-lookup"><span data-stu-id="9b339-112">The RETURN statement uses the @@ROWCOUNT function to return the number of rows inserted.</span></span>  
  
```sql
CREATE PROCEDURE dbo.InsertCategory  
  @CategoryName nvarchar(15),  
  @Identity int OUT  
AS  
INSERT INTO Categories (CategoryName) VALUES(@CategoryName)  
SET @Identity = SCOPE_IDENTITY()  
RETURN @@ROWCOUNT  
```  
  
 <span data-ttu-id="9b339-113">Следующий пример кода использует хранимую процедуру `InsertCategory`, показанную выше, в качестве источника для свойства <xref:System.Data.SqlClient.SqlDataAdapter.InsertCommand%2A> класса <xref:System.Data.SqlClient.SqlDataAdapter>.</span><span class="sxs-lookup"><span data-stu-id="9b339-113">The following code example uses the `InsertCategory` stored procedure shown above as the source for the <xref:System.Data.SqlClient.SqlDataAdapter.InsertCommand%2A> of the <xref:System.Data.SqlClient.SqlDataAdapter>.</span></span> <span data-ttu-id="9b339-114">Выходной параметр `@Identity` будет отражен в наборе данных <xref:System.Data.DataSet> после вставки записи в базу данных при вызове метода `Update` объекта <xref:System.Data.SqlClient.SqlDataAdapter>.</span><span class="sxs-lookup"><span data-stu-id="9b339-114">The `@Identity` output parameter will be reflected in the <xref:System.Data.DataSet> after the record has been inserted into the database when the `Update` method of the <xref:System.Data.SqlClient.SqlDataAdapter> is called.</span></span> <span data-ttu-id="9b339-115">Код также получает возвращаемое значение.</span><span class="sxs-lookup"><span data-stu-id="9b339-115">The code also retrieves the return value.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9b339-116">При использовании параметра <xref:System.Data.OleDb.OleDbDataAdapter> необходимо указать параметры с параметром с параметром <xref:System.Data.ParameterDirection> **ReturnValue** перед другими параметрами.</span><span class="sxs-lookup"><span data-stu-id="9b339-116">When using the <xref:System.Data.OleDb.OleDbDataAdapter>, you must specify parameters with a <xref:System.Data.ParameterDirection> of **ReturnValue** before the other parameters.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.SprocIdentityReturn#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.SprocIdentityReturn/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.SprocIdentityReturn#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.SprocIdentityReturn/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="9b339-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="9b339-117">See also</span></span>

- [<span data-ttu-id="9b339-118">Извлечение и изменение данных в ADO.NET</span><span class="sxs-lookup"><span data-stu-id="9b339-118">Retrieving and Modifying Data in ADO.NET</span></span>](retrieving-and-modifying-data.md)
- [<span data-ttu-id="9b339-119">Объекты DataAdapter и DataReader</span><span class="sxs-lookup"><span data-stu-id="9b339-119">DataAdapters and DataReaders</span></span>](dataadapters-and-datareaders.md)
- [<span data-ttu-id="9b339-120">Выполнение команды</span><span class="sxs-lookup"><span data-stu-id="9b339-120">Executing a Command</span></span>](executing-a-command.md)
- [<span data-ttu-id="9b339-121">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="9b339-121">ADO.NET Overview</span></span>](ado-net-overview.md)
