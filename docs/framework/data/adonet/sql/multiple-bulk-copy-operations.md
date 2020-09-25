---
title: Несколько операций массового копирования
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5ad12f94-7459-4a93-a421-4160d1a90715
ms.openlocfilehash: d447f09fcbfe108346b81a2bced44cf305e2844b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91172675"
---
# <a name="multiple-bulk-copy-operations"></a><span data-ttu-id="8d241-102">Несколько операций массового копирования</span><span class="sxs-lookup"><span data-stu-id="8d241-102">Multiple Bulk Copy Operations</span></span>

<span data-ttu-id="8d241-103">Вы можете выполнить несколько операций массового копирования, используя один экземпляр класса <xref:System.Data.SqlClient.SqlBulkCopy>.</span><span class="sxs-lookup"><span data-stu-id="8d241-103">You can perform multiple bulk copy operations using a single instance of a <xref:System.Data.SqlClient.SqlBulkCopy> class.</span></span> <span data-ttu-id="8d241-104">Если параметры операции изменяются между копиями (например, именем целевой таблицы), необходимо обновить их перед любыми последующими вызовами любого из методов **WriteToServer** , как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="8d241-104">If the operation parameters change between copies (for example, the name of the destination table), you must update them prior to any subsequent calls to any of the **WriteToServer** methods, as demonstrated in the following example.</span></span> <span data-ttu-id="8d241-105">Если значения свойств не изменяются явным образом, все они остаются такими же, как при предыдущей операции массового копирования для данного экземпляра.</span><span class="sxs-lookup"><span data-stu-id="8d241-105">Unless explicitly changed, all property values remain the same as they were on the previous bulk copy operation for a given instance.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8d241-106">Выполнение нескольких операций массового копирования с использованием одного экземпляра <xref:System.Data.SqlClient.SqlBulkCopy> обычно более эффективно, чем использование отдельного экземпляра для каждой операции.</span><span class="sxs-lookup"><span data-stu-id="8d241-106">Performing multiple bulk copy operations using the same instance of <xref:System.Data.SqlClient.SqlBulkCopy> is usually more efficient than using a separate instance for each operation.</span></span>  
  
 <span data-ttu-id="8d241-107">При выполнении нескольких операций массового копирования с одним объектом <xref:System.Data.SqlClient.SqlBulkCopy> не существует ограничений, касающихся совпадения или различий целевой информации в каждой операции.</span><span class="sxs-lookup"><span data-stu-id="8d241-107">If you perform several bulk copy operations using the same <xref:System.Data.SqlClient.SqlBulkCopy> object, there are no restrictions on whether source or target information is equal or different in each operation.</span></span> <span data-ttu-id="8d241-108">Однако для каждой записи на сервер необходимо убедиться, что связи столбцов настроены правильно.</span><span class="sxs-lookup"><span data-stu-id="8d241-108">However, you must ensure that column association information is properly set each time you write to the server.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="8d241-109">Этот пример не будет выполняться, если вы не создали рабочие таблицы, как описано в статье [Пример установки с помощью инструкций копирования](bulk-copy-example-setup.md).</span><span class="sxs-lookup"><span data-stu-id="8d241-109">This sample will not run unless you have created the work tables as described in [Bulk Copy Example Setup](bulk-copy-example-setup.md).</span></span> <span data-ttu-id="8d241-110">Этот код предназначен только для демонстрации синтаксиса использования **SqlBulkCopy**.</span><span class="sxs-lookup"><span data-stu-id="8d241-110">This code is provided to demonstrate the syntax for using **SqlBulkCopy** only.</span></span> <span data-ttu-id="8d241-111">Если исходная и целевая таблицы расположены в одном экземпляре SQL Server, будет проще и быстрее использовать инструкцию Transact-SQL `INSERT … SELECT` для копирования данных.</span><span class="sxs-lookup"><span data-stu-id="8d241-111">If the source and destination tables are located in the same SQL Server instance, it is easier and faster to use a Transact-SQL `INSERT … SELECT` statement to copy the data.</span></span>  
  
 [!code-csharp[DataWorks SqlBulkCopy.ColumnMappingOrdersDetails#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlBulkCopy.ColumnMappingOrdersDetails/CS/source.cs#1)]
 [!code-vb[DataWorks SqlBulkCopy.ColumnMappingOrdersDetails#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlBulkCopy.ColumnMappingOrdersDetails/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="8d241-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="8d241-112">See also</span></span>

- [<span data-ttu-id="8d241-113">Операции массового копирования в SQL Server</span><span class="sxs-lookup"><span data-stu-id="8d241-113">Bulk Copy Operations in SQL Server</span></span>](bulk-copy-operations-in-sql-server.md)
- [<span data-ttu-id="8d241-114">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="8d241-114">ADO.NET Overview</span></span>](../ado-net-overview.md)
