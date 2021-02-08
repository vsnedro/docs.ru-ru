---
description: 'Дополнительные сведения: SQL Server типов данных и ADO.NET'
title: Типы данных SQL Server и ADO.NET
titleSuffix: ''
ms.date: 03/30/2017
ms.assetid: 81b43550-23e8-43bb-b460-7eb8ac825c33
ms.openlocfilehash: 841fa5864bf54b5e4fc4dc24dab64e6ac1435c7e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99767301"
---
# <a name="sql-server-data-types-and-adonet"></a>Типы данных SQL Server и ADO.NET

В SQL Server и .NET Framework используются различные системы типов, что может привести к потенциальной потере данных. Чтобы сохранить целостность данных, поставщик данных .NET Framework для SQL Server (<xref:System.Data.SqlClient>) предоставляет типизированные методы доступа для работы с данными SQL Server. Перечисления в классах <xref:System.Data.SqlDbType> можно использовать для указания типов данных <xref:System.Data.SqlClient.SqlParameter>.  
  
 Дополнительные сведения и таблица с описанием сопоставлений типов данных между типами данных SQL Server и платформа .NET Framework см. в разделе [SQL Server сопоставления типов данных](../sql-server-data-type-mappings.md).  
  
 В SQL Server 2008 появились новые типы данных, разработанные для удовлетворения бизнес-потребностей при работе с датами и временем, структурированными, частично структурированными и неструктурированными данными. Они описаны в электронной документации на SQL Server 2008.  
  
 Типы данных SQL Server, доступные для использования в приложении, зависят от используемой версии SQL Server. Дополнительные сведения см. в электронной документации для соответствующей версии SQL Server в приведенной ниже таблице.  
  
 **Документация по SQL Server**  
  
1. [Типы данных (Transact-SQL)](/sql/t-sql/data-types/data-types-transact-sql)  
  
## <a name="in-this-section"></a>В этом разделе  

 [Типы SqlType и набор данных](sqltypes-and-the-dataset.md)  
 Описывает тип поддержки пространства имен `SqlTypes` в `DataSet`.  
  
 [Обработка значений NULL](handling-null-values.md)  
 Демонстрирует работу со значениями NULL и логикой трех значений.  
  
 [Сравнение значений GUID и uniqueidentifier](comparing-guid-and-uniqueidentifier-values.md)  
 Демонстрируется работа со значениями GUID и uniqueidentifier в SQL Server и .NET Framework.  
  
 [Данные даты и времени](date-and-time-data.md)  
 В этой статье описывается использование новых типов данных даты и времени, появившихся в SQL Server 2008.  
  
 [Большие, определяемые пользователем типы](large-udts.md)  
 Здесь демонстрируется получение данных из UDT с большими значениями, представленных в SQL Server 2008.  
  
 [XML-данные в SQL Server](xml-data-in-sql-server.md)  
 Сведения о том, как работать с XML-данными, полученными из SQL Server.  
  
## <a name="reference"></a>Справочник  

 <xref:System.Data.DataSet>  
 Описание класса `DataSet` и всех его членов.  
  
 <xref:System.Data.SqlTypes>  
 Описание пространства имен `SqlTypes` и всех его членов.  
  
 <xref:System.Data.SqlDbType>  
 Описание перечисления `SqlDbType` и всех его членов.  
  
 <xref:System.Data.DbType>  
 Описание перечисления `DbType` и всех его членов.  
  
## <a name="see-also"></a>См. также

- [Сопоставления типов данных SQL Server](../sql-server-data-type-mappings.md)
- [Настройка параметров и типы данных параметров](../configuring-parameters-and-parameter-data-types.md)
- [Параметры, возвращающие табличные значения](table-valued-parameters.md)
- [Двоичные данные и данные больших значений SQL Server](sql-server-binary-and-large-value-data.md)
- [Общие сведения об ADO.NET](../ado-net-overview.md)
