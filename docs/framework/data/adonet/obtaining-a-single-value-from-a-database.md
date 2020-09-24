---
title: Получение одного значения из базы данных
description: Узнайте, как вернуть одно значение в ADO.NET. В этом примере кода возвращается значение столбца идентификаторов для вставленной записи.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b38526cd-a62a-48cb-822a-e91dfa68e02d
ms.openlocfilehash: 9ce29bc1321814bd60cfaacd222fc55a3fbf12ed
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91150730"
---
# <a name="obtaining-a-single-value-from-a-database"></a><span data-ttu-id="4b7e2-104">Получение одного значения из базы данных</span><span class="sxs-lookup"><span data-stu-id="4b7e2-104">Obtaining a Single Value from a Database</span></span>

<span data-ttu-id="4b7e2-105">Может возникнуть необходимость вернуть сведения из базы данных, которые представляют собой одиночное значение, а не форму таблицы или поток данных.</span><span class="sxs-lookup"><span data-stu-id="4b7e2-105">You may need to return database information that is simply a single value rather than in the form of a table or data stream.</span></span> <span data-ttu-id="4b7e2-106">Например, может потребоваться возврат результата агрегатной функции, такой как COUNT ( \* ), Sum (Price) или AVG (Quantity).</span><span class="sxs-lookup"><span data-stu-id="4b7e2-106">For example, you may want to return the result of an aggregate function such as COUNT(\*), SUM(Price), or AVG(Quantity).</span></span> <span data-ttu-id="4b7e2-107">Объект **Command** предоставляет возможность возвращать одиночные значения с помощью метода **ExecuteScalar** .</span><span class="sxs-lookup"><span data-stu-id="4b7e2-107">The **Command** object provides the capability to return single values using the **ExecuteScalar** method.</span></span> <span data-ttu-id="4b7e2-108">Метод **ExecuteScalar** возвращает, как скалярное значение, значение первого столбца первой строки результирующего набора.</span><span class="sxs-lookup"><span data-stu-id="4b7e2-108">The **ExecuteScalar** method returns, as a scalar value, the value of the first column of the first row of the result set.</span></span>  
  
 <span data-ttu-id="4b7e2-109">В следующем примере кода в базу данных при помощи <xref:System.Data.SqlClient.SqlCommand> вставляется новое значение.</span><span class="sxs-lookup"><span data-stu-id="4b7e2-109">The following code example inserts a new value in the database using a <xref:System.Data.SqlClient.SqlCommand>.</span></span> <span data-ttu-id="4b7e2-110">Метод <xref:System.Data.SqlClient.SqlCommand.ExecuteScalar%2A> используется, чтобы вернуть значение столбца идентификатора для вставленной записи.</span><span class="sxs-lookup"><span data-stu-id="4b7e2-110">The <xref:System.Data.SqlClient.SqlCommand.ExecuteScalar%2A> method is used to return the identity column value for the inserted record.</span></span>  
  
 [!code-csharp[DataWorks SqlCommand.ExecuteScalar#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlCommand.ExecuteScalar/CS/source.cs#1)]
 [!code-vb[DataWorks SqlCommand.ExecuteScalar#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlCommand.ExecuteScalar/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="4b7e2-111">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="4b7e2-111">See also</span></span>

- [<span data-ttu-id="4b7e2-112">Команды и параметры</span><span class="sxs-lookup"><span data-stu-id="4b7e2-112">Commands and Parameters</span></span>](commands-and-parameters.md)
- [<span data-ttu-id="4b7e2-113">Выполнение команды</span><span class="sxs-lookup"><span data-stu-id="4b7e2-113">Executing a Command</span></span>](executing-a-command.md)
- [<span data-ttu-id="4b7e2-114">DbConnection, DbCommand и DbException</span><span class="sxs-lookup"><span data-stu-id="4b7e2-114">DbConnection, DbCommand and DbException</span></span>](dbconnection-dbcommand-and-dbexception.md)
- [<span data-ttu-id="4b7e2-115">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="4b7e2-115">ADO.NET Overview</span></span>](ado-net-overview.md)
