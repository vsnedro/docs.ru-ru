---
title: Операции массового копирования в SQL Server
description: Научитесь использовать класс SqlBulkCopy для создания решений с управляемым кодом, которые позволяют выполнять операции копирования больших файлов в таблицы или представления в SQL Server базах данных.
ms.date: 03/30/2017
ms.assetid: 83a7a0d2-8018-4354-97b9-0b1d99f8342b
ms.openlocfilehash: 4f877836aa45efe162cce3c42cb5733f86deab2c
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286524"
---
# <a name="bulk-copy-operations-in-sql-server"></a>Операции массового копирования в SQL Server
Microsoft SQL Server включает популярную служебную программу командной строки **bcp**, позволяющую быстро выполнять массовое копирование больших файлов в таблицы или представления баз данных SQL Server. Класс <xref:System.Data.SqlClient.SqlBulkCopy> позволяет создавать решения с управляемым кодом, которые предоставляют аналогичные возможности. Существуют другие способы загрузки данных в таблицу SQL Server (например, с помощью инструкции INSERT), но <xref:System.Data.SqlClient.SqlBulkCopy> делает это значительно быстрее.  
  
 Класс <xref:System.Data.SqlClient.SqlBulkCopy> можно использовать для записи данных только в таблицы SQL Server. SQL Server не является единственным источником данных. Можно использовать любой источник данных при условии, что данные можно будет загрузить в экземпляр <xref:System.Data.DataTable> или считать экземпляром <xref:System.Data.IDataReader>.  
  
 Класс <xref:System.Data.SqlClient.SqlBulkCopy> предоставляет следующие возможности:  
  
- одну операцию массового копирования;  
  
- несколько операций массового копирования;  
  
- операцию массового копирования в транзакции.  
  
> [!NOTE]
> При использовании платформы .NET Framework 1.1 или более ранней версии (не поддерживающей класс <xref:System.Data.SqlClient.SqlBulkCopy>) инструкцию SQL Server Transact-SQL **BULK INSERT** можно выполнить при помощи объекта <xref:System.Data.SqlClient.SqlCommand>.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Пример установки с массовым копированием](bulk-copy-example-setup.md)  
 Описание таблиц, используемых в примерах с массовым копированием, и примеры скриптов SQL для создания таблиц в базе данных AdventureWorks.  
  
 [Одиночные операции копирования](single-bulk-copy-operations.md)  
 Описание процессов одного массового копирования данных в экземпляр SQL Server с помощью класса <xref:System.Data.SqlClient.SqlBulkCopy>, а также массового копирования с помощью инструкций Transact-SQL и класса <xref:System.Data.SqlClient.SqlCommand>.  
  
 [Несколько операций с массовым копированием](multiple-bulk-copy-operations.md)  
 Описание выполнения нескольких операций массового копирования данных в экземпляр SQL Server с помощью класса <xref:System.Data.SqlClient.SqlBulkCopy>.  
  
 [Операции транзакций и операций с массовым копированием](transaction-and-bulk-copy-operations.md)  
 Сведения о том, как выполнить операцию массового копирования в рамках транзакции, в том числе как зафиксировать или откатить эту транзакцию.  
  
## <a name="see-also"></a>См. также

- [SQL Server и ADO.NET](index.md)
- [Общие сведения об ADO.NET](../ado-net-overview.md)
