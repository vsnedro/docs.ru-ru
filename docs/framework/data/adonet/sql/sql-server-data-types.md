---
title: Типы данных SQL Server и ADO.NET
titleSuffix: ''
ms.date: 03/30/2017
ms.assetid: 81b43550-23e8-43bb-b460-7eb8ac825c33
ms.openlocfilehash: db4618ac624ea8401cab682a8c21d8f23c253d05
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91155462"
---
# <a name="sql-server-data-types-and-adonet"></a>Типы данных SQL Server и ADO.NET

В SQL Server и .NET Framework используются различные системы типов, что может привести к потенциальной потере данных. Чтобы сохранить целостность данных, поставщик данных .NET Framework для SQL Server (<xref:System.Data.SqlClient>) предоставляет типизированные методы доступа для работы с данными SQL Server. Перечисления в классах <xref:System.Data.SqlDbType> можно использовать для указания типов данных <xref:System.Data.SqlClient.SqlParameter>.  
  
 Дополнительные сведения и таблица с описанием сопоставлений типов данных между типами данных SQL Server и .NET Framework см. в разделе [SQL Server сопоставления типов данных](../sql-server-data-type-mappings.md).  
  
 В SQL Server 2008 появились новые типы данных, разработанные для удовлетворения бизнес-потребностей при работе с датами и временем, структурированными, частично структурированными и неструктурированными данными. Они описаны в электронной документации на SQL Server 2008.  
  
 Типы данных SQL Server, доступные для использования в приложении, зависят от используемой версии SQL Server. Дополнительные сведения см. в электронной документации для соответствующей версии SQL Server в приведенной ниже таблице.  
  
 **Документация по SQL Server**  
  
1. [Типы данных (Transact-SQL)](/sql/t-sql/data-types/data-types-transact-sql)  
  
## <a name="in-this-section"></a>в этом разделе  

 [Типы SqlType и набор данных](sqltypes-and-the-dataset.md)  
 Описывает тип поддержки пространства имен `SqlTypes` в `DataSet`.  
  
 [Обработка значений NULL](handling-null-values.md)  
 Демонстрирует работу со значениями NULL и логикой трех значений.  
  
 [Сравнение значений идентификатора GUID и uniqueidentifier](comparing-guid-and-uniqueidentifier-values.md)  
 Демонстрируется работа со значениями GUID и uniqueidentifier в SQL Server и .NET Framework.  
  
 [Данные даты и времени](date-and-time-data.md)  
 В этой статье описывается использование новых типов данных даты и времени, появившихся в SQL Server 2008.  
  
 [Большие, определяемые пользователем типы](large-udts.md)  
 Здесь демонстрируется получение данных из UDT с большими значениями, представленных в SQL Server 2008.  
  
 [XML-данные в SQL Server](xml-data-in-sql-server.md)  
 Сведения о том, как работать с XML-данными, полученными из SQL Server.  
  
## <a name="reference"></a>Справка  

 <xref:System.Data.DataSet>  
 Описание класса `DataSet` и всех его членов.  
  
 <xref:System.Data.SqlTypes>  
 Описание пространства имен `SqlTypes` и всех его членов.  
  
 <xref:System.Data.SqlDbType>  
 Описание перечисления `SqlDbType` и всех его членов.  
  
 <xref:System.Data.DbType>  
 Описание перечисления `DbType` и всех его членов.  
  
## <a name="see-also"></a>См. также раздел

- [Сопоставления типов данных SQL Server](../sql-server-data-type-mappings.md)
- [Настройка параметров и типы данных параметров](../configuring-parameters-and-parameter-data-types.md)
- [Параметры, возвращающие табличные значения](table-valued-parameters.md)
- [SQL Server данные в двоичном и больших значениях](sql-server-binary-and-large-value-data.md)
- [Общие сведения об ADO.NET](../ado-net-overview.md)
