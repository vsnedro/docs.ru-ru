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
# <a name="multiple-bulk-copy-operations"></a>Несколько операций массового копирования

Вы можете выполнить несколько операций массового копирования, используя один экземпляр класса <xref:System.Data.SqlClient.SqlBulkCopy>. Если параметры операции изменяются между копиями (например, именем целевой таблицы), необходимо обновить их перед любыми последующими вызовами любого из методов **WriteToServer** , как показано в следующем примере. Если значения свойств не изменяются явным образом, все они остаются такими же, как при предыдущей операции массового копирования для данного экземпляра.  
  
> [!NOTE]
> Выполнение нескольких операций массового копирования с использованием одного экземпляра <xref:System.Data.SqlClient.SqlBulkCopy> обычно более эффективно, чем использование отдельного экземпляра для каждой операции.  
  
 При выполнении нескольких операций массового копирования с одним объектом <xref:System.Data.SqlClient.SqlBulkCopy> не существует ограничений, касающихся совпадения или различий целевой информации в каждой операции. Однако для каждой записи на сервер необходимо убедиться, что связи столбцов настроены правильно.  
  
> [!IMPORTANT]
> Этот пример не будет выполняться, если вы не создали рабочие таблицы, как описано в статье [Пример установки с помощью инструкций копирования](bulk-copy-example-setup.md). Этот код предназначен только для демонстрации синтаксиса использования **SqlBulkCopy**. Если исходная и целевая таблицы расположены в одном экземпляре SQL Server, будет проще и быстрее использовать инструкцию Transact-SQL `INSERT … SELECT` для копирования данных.  
  
 [!code-csharp[DataWorks SqlBulkCopy.ColumnMappingOrdersDetails#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlBulkCopy.ColumnMappingOrdersDetails/CS/source.cs#1)]
 [!code-vb[DataWorks SqlBulkCopy.ColumnMappingOrdersDetails#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlBulkCopy.ColumnMappingOrdersDetails/VB/source.vb#1)]  
  
## <a name="see-also"></a>См. также раздел

- [Операции массового копирования в SQL Server](bulk-copy-operations-in-sql-server.md)
- [Общие сведения об ADO.NET](../ado-net-overview.md)
