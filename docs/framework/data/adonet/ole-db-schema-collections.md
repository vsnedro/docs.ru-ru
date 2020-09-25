---
title: Коллекции схемы OLE DB
ms.date: 03/30/2017
ms.assetid: 6380c36b-658e-4d67-91e8-7131ef4a7c2c
ms.openlocfilehash: 90899a123b3dafcd47a50ef8f6eb003938b22a03
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91186943"
---
# <a name="ole-db-schema-collections"></a>Коллекции схемы OLE DB

В данном разделе рассматривается поддержка коллекций схем для поставщиков OLE DB для Microsoft SQL Server, Oracle и Microsoft Jet.  
  
## <a name="microsoft-sql-server-ole-db-provider"></a>Поставщик OLE DB для Microsoft SQL Server  

 Драйвер OLE DB для Microsoft SQL Server поддерживает следующие специальные коллекции схем в дополнение к общим коллекциям.  
  
- Таблицы  
  
- Столбцы  
  
- Процедуры  
  
- ProcedureParameters  
  
- Каталог  
  
- Индексы  
  
### <a name="tables"></a>Таблицы  
  
|ColumnName|DataType|  
|----------------|--------------|  
|TABLE_CATALOG|Строка|  
|TABLE_SCHEMA|Строка|  
|TABLE_NAME|Строка|  
|TABLE_TYPE|Строка|  
|TABLE_GUID|Guid|  
|DESCRIPTION|Строка|  
|TABLE_PROPID|Int64|  
|DATE_CREATED|Дата и время|  
|DATE_MODIFIED|Дата и время|  
  
### <a name="columns"></a>Столбцы  
  
|ColumnName|DataType|  
|----------------|--------------|  
|TABLE_CATALOG|Строка|  
|TABLE_SCHEMA|Строка|  
|TABLE_NAME|Строка|  
|COLUMN_NAME|Строка|  
|COLUMN_GUID|Guid|  
|COLUMN_PROPID|Int64|  
|ORDINAL_POSITION|Int64|  
|COLUMN_HASDEFAULT|Логическое|  
|COLUMN_DEFAULT|Строка|  
|COLUMN_FLAGS|Int64|  
|IS_NULLABLE|Логическое|  
|DATA_TYPE|Int32|  
|TYPE_GUID|Guid|  
|CHARACTER_MAXIMUM_LENGTH|Int64|  
|CHARACTER_OCTET_LENGTH|Int64|  
|NUMERIC_PRECISION|Int32|  
|NUMERIC_SCALE|Int16|  
|DATETIME_PRECISION|Int64|  
|CHARACTER_SET_CATALOG|Строка|  
|CHARACTER_SET_SCHEMA|Строка|  
|CHARACTER_SET_NAME|Строка|  
|COLLATION_CATALOG|Строка|  
|COLLATION_SCHEMA|Строка|  
|COLLATION_NAME|Строка|  
|DOMAIN_CATALOG|Строка|  
|DOMAIN_SCHEMA|Строка|  
|DOMAIN_NAME|Строка|  
|DESCRIPTION|Строка|  
|COLUMN_LCID|Int32|  
|COLUMN_COMPFLAGS|Int32|  
|COLUMN_SORTID|Int32|  
|COLUMN_TDSCOLLATION|Byte[]|  
|IS_COMPUTED|Логическое|  
  
### <a name="procedures"></a>Процедуры  
  
|ColumnName|DataType|  
|----------------|--------------|  
|PROCEDURE_CATALOG|Строка|  
|PROCEDURE_SCHEMA|Строка|  
|PROCEDURE_NAME|Строка|  
|PROCEDURE_TYPE|Int16|  
|PROCEDURE_DEFINITION|Строка|  
|DESCRIPTION|Строка|  
|DATE_CREATED|Дата и время|  
|DATE_MODIFIED|Дата и время|  
  
### <a name="procedureparameters"></a>ProcedureParameters  
  
|ColumnName|DataType|  
|----------------|--------------|  
|PROCEDURE_CATALOG|Строка|  
|PROCEDURE_SCHEMA|Строка|  
|PROCEDURE_NAME|Строка|  
|PARAMETER_NAME|Строка|  
|ORDINAL_POSITION|Int32|  
|PARAMETER_TYPE|Int32|  
|PARAMETER_HASDEFAULT|Логическое|  
|PARAMETER_DEFAULT|Строка|  
|IS_NULLABLE|Логическое|  
|DATA_TYPE|Int32|  
|CHARACTER_MAXIMUM_LENGTH|Int64|  
|CHARACTER_OCTET_LENGTH|Int64|  
|NUMERIC_PRECISION|Int32|  
|NUMERIC_SCALE|Int16|  
|DESCRIPTION|Строка|  
|TYPE_NAME|Строка|  
|LOCAL_TYPE_NAME|Строка|  
  
### <a name="catalog"></a>Каталог  
  
|ColumnName|DataType|  
|----------------|--------------|  
|CATALOG_NAME|Строка|  
|DESCRIPTION|Строка|  
  
### <a name="indexes"></a>Индексы  
  
|ColumnName|DataType|  
|----------------|--------------|  
|TABLE_CATALOG|Строка|  
|TABLE_SCHEMA|Строка|  
|TABLE_NAME|Строка|  
|INDEX_CATALOG|Строка|  
|INDEX_SCHEMA|Строка|  
|INDEX_NAME|Строка|  
|PRIMARY_KEY|Логическое|  
|UNIQUE|Логическое|  
|CLUSTERED|Логическое|  
|TYPE|Int32|  
|FILL_FACTOR|Int32|  
|INITIAL_SIZE|Int32|  
|NULLS|Int32|  
|SORT_BOOKMARKS|Логическое|  
|AUTO_UPDATE|Логическое|  
|NULL_COLLATION|Int32|  
|ORDINAL_POSITION|Int64|  
|COLUMN_NAME|Строка|  
|COLUMN_GUID|Guid|  
|COLUMN_PROPID|Int64|  
|COLLATION|Int16|  
|CARDINALITY|Decimal|  
|PAGES|Int32|  
|FILTER_CONDITION|Строка|  
|INTEGRATED|Логическое|  
  
## <a name="microsoft-oracle-ole-db-provider"></a>Поставщик Microsoft OLE DB для Oracle  

 Драйвер OLE DB для Oracle (Майкрософт) поддерживает следующие специальные коллекции схем в дополнение к общим коллекциям.  
  
- Таблицы  
  
- Столбцы  
  
- Процедуры  
  
- ProcedureColumns  
  
- ProcedureParameters  
  
- Представления  
  
- Индексы  
  
### <a name="tables"></a>Таблицы  
  
|ColumnName|DataType|  
|----------------|--------------|  
|TABLE_CATALOG|Строка|  
|TABLE_SCHEMA|Строка|  
|TABLE_NAME|Строка|  
|TABLE_TYPE|Строка|  
|TABLE_GUID|Guid|  
|DESCRIPTION|Строка|  
|TABLE_PROPID|Int64|  
|DATE_CREATED|Дата и время|  
|DATE_MODIFIED|Дата и время|  
  
### <a name="columns"></a>Столбцы  
  
|ColumnName|DataType|  
|----------------|--------------|  
|TABLE_CATALOG|Строка|  
|TABLE_SCHEMA|Строка|  
|TABLE_NAME|Строка|  
|COLUMN_NAME|Строка|  
|COLUMN_GUID|Guid|  
|COLUMN_PROPID|Int64|  
|ORDINAL_POSITION|Int64|  
|COLUMN_HASDEFAULT|Логическое|  
|COLUMN_DEFAULT|Строка|  
|COLUMN_FLAGS|Int64|  
|IS_NULLABLE|Логическое|  
|DATA_TYPE|Int32|  
|TYPE_GUID|Guid|  
|CHARACTER_MAXIMUM_LENGTH|Int64|  
|CHARACTER_OCTET_LENGTH|Int64|  
|NUMERIC_PRECISION|Int32|  
|NUMERIC_SCALE|Int16|  
|DATETIME_PRECISION|Int64|  
|CHARACTER_SET_CATALOG|Строка|  
|CHARACTER_SET_SCHEMA|Строка|  
|CHARACTER_SET_NAME|Строка|  
|COLLATION_CATALOG|Строка|  
|COLLATION_SCHEMA|Строка|  
|COLLATION_NAME|Строка|  
|DOMAIN_CATALOG|Строка|  
|DOMAIN_SCHEMA|Строка|  
|DOMAIN_NAME|Строка|  
|DESCRIPTION|Строка|  
  
### <a name="procedures"></a>Процедуры  
  
|ColumnName|DataType|  
|----------------|--------------|  
|PROCEDURE_CATALOG|Строка|  
|PROCEDURE_SCHEMA|Строка|  
|PROCEDURE_NAME|Строка|  
|PROCEDURE_TYPE|Int16|  
|PROCEDURE_DEFINITION|Строка|  
|DESCRIPTION|Строка|  
|DATE_CREATED|Дата и время|  
|DATE_MODIFIED|Дата и время|  
  
### <a name="procedurecolumns"></a>ProcedureColumns  
  
|ColumnName|DataType|  
|----------------|--------------|  
|PROCEDURE_CATALOG|Строка|  
|PROCEDURE_SCHEMA|Строка|  
|PROCEDURE_NAME|Строка|  
|COLUMN_NAME|Строка|  
|COLUMN_GUID|Guid|  
|COLUMN_PROPID|Int64|  
|ROWSET_NUMBER|Int64|  
|ORDINAL_POSITION|Int64|  
|IS_NULLABLE|Логическое|  
|DATA_TYPE|Int32|  
|TYPE_GUID|Guid|  
|CHARACTER_MAXIMUM_LENGTH|Int64|  
|CHARACTER_OCTET_LENGTH|Int64|  
|NUMERIC_PRECISION|Int32|  
|NUMERIC_SCALE|Int16|  
|DESCRIPTION|Строка|  
|OVERLOAD|Int16|  
  
### <a name="views"></a>Представления  
  
|ColumnName|DataType|  
|----------------|--------------|  
|TABLE_CATALOG|Строка|  
|TABLE_SCHEMA|Строка|  
|TABLE_NAME|Строка|  
|VIEW_DEFINITION|Строка|  
|CHECK_OPTION|Логическое|  
|IS_UPDATABLE|Логическое|  
|DESCRIPTION|Строка|  
|DATE_CREATED|Дата и время|  
|DATE_MODIFIED|Дата и время|  
  
### <a name="indexes"></a>Индексы  
  
|ColumnName|DataType|  
|----------------|--------------|  
|TABLE_CATALOG|Строка|  
|TABLE_SCHEMA|Строка|  
|TABLE_NAME|Строка|  
|INDEX_CATALOG|Строка|  
|INDEX_SCHEMA|Строка|  
|INDEX_NAME|Строка|  
|PRIMARY_KEY|Логическое|  
|UNIQUE|Логическое|  
|CLUSTERED|Логическое|  
|TYPE|Int32|  
|FILL_FACTOR|Int32|  
|INITIAL_SIZE|Int32|  
|NULLS|Int32|  
|SORT_BOOKMARKS|Логическое|  
|AUTO_UPDATE|Логическое|  
|NULL_COLLATION|Int32|  
|ORDINAL_POSITION|Int64|  
|COLUMN_NAME|Строка|  
|COLUMN_GUID|Guid|  
|COLUMN_PROPID|Int64|  
|COLLATION|Int16|  
|CARDINALITY|Decimal|  
|PAGES|Int32|  
|FILTER_CONDITION|Строка|  
|INTEGRATED|Логическое|  
  
## <a name="microsoft-jet-ole-db-provider"></a>Поставщик OLE DB для Microsoft Jet  

 Драйвер OLE DB для Jet (Майкрософт) поддерживает следующие специальные коллекции схем в дополнение к общим коллекциям.  
  
- Таблицы  
  
- Столбцы  
  
- Процедуры  
  
- Представления  
  
- Индексы  
  
### <a name="tables"></a>Таблицы  
  
|ColumnName|DataType|  
|----------------|--------------|  
|TABLE_CATALOG|Строка|  
|TABLE_SCHEMA|Строка|  
|TABLE_NAME|Строка|  
|TABLE_TYPE|Строка|  
|TABLE_GUID|Guid|  
|DESCRIPTION|Строка|  
|TABLE_PROPID|Int64|  
|DATE_CREATED|Дата и время|  
|DATE_MODIFIED|Дата и время|  
  
### <a name="columns"></a>Столбцы  
  
|ColumnName|DataType|  
|----------------|--------------|  
|TABLE_CATALOG|Строка|  
|TABLE_SCHEMA|Строка|  
|TABLE_NAME|Строка|  
|COLUMN_NAME|Строка|  
|COLUMN_GUID|Guid|  
|COLUMN_PROPID|Int64|  
|ORDINAL_POSITION|Int64|  
|COLUMN_HASDEFAULT|Логическое|  
|COLUMN_DEFAULT|Строка|  
|COLUMN_FLAGS|Int64|  
|IS_NULLABLE|Логическое|  
|DATA_TYPE|Int32|  
|TYPE_GUID|Guid|  
|CHARACTER_MAXIMUM_LENGTH|Int64|  
|CHARACTER_OCTET_LENGTH|Int64|  
|NUMERIC_PRECISION|Int32|  
|NUMERIC_SCALE|Int16|  
|DATETIME_PRECISION|Int64|  
|CHARACTER_SET_CATALOG|Строка|  
|CHARACTER_SET_SCHEMA|Строка|  
|CHARACTER_SET_NAME|Строка|  
|COLLATION_CATALOG|Строка|  
|COLLATION_SCHEMA|Строка|  
|COLLATION_NAME|Строка|  
|DOMAIN_CATALOG|Строка|  
|DOMAIN_SCHEMA|Строка|  
|DOMAIN_NAME|Строка|  
|DESCRIPTION|Строка|  
  
### <a name="procedures"></a>Процедуры  
  
|ColumnName|DataType|  
|----------------|--------------|  
|PROCEDURE_CATALOG|Строка|  
|PROCEDURE_SCHEMA|Строка|  
|PROCEDURE_NAME|Строка|  
|PROCEDURE_TYPE|Int16|  
|PROCEDURE_DEFINITION|Строка|  
|DESCRIPTION|Строка|  
|DATE_CREATED|Дата и время|  
|DATE_MODIFIED|Дата и время|  
  
### <a name="views"></a>Представления  
  
|ColumnName|DataType|  
|----------------|--------------|  
|TABLE_CATALOG|Строка|  
|TABLE_SCHEMA|Строка|  
|TABLE_NAME|Строка|  
|VIEW_DEFINITION|Строка|  
|CHECK_OPTION|Логическое|  
|IS_UPDATABLE|Логическое|  
|DESCRIPTION|Строка|  
|DATE_CREATED|Дата и время|  
|DATE_MODIFIED|Дата и время|  
  
### <a name="indexes"></a>Индексы  
  
|ColumnName|DataType|  
|----------------|--------------|  
|TABLE_CATALOG|Строка|  
|TABLE_SCHEMA|Строка|  
|TABLE_NAME|Строка|  
|INDEX_CATALOG|Строка|  
|INDEX_SCHEMA|Строка|  
|INDEX_NAME|Строка|  
|PRIMARY_KEY|Логическое|  
|UNIQUE|Логическое|  
|CLUSTERED|Логическое|  
|TYPE|Int32|  
|FILL_FACTOR|Int32|  
|INITIAL_SIZE|Int32|  
|NULLS|Int32|  
|SORT_BOOKMARKS|Логическое|  
|AUTO_UPDATE|Логическое|  
|NULL_COLLATION|Int32|  
|ORDINAL_POSITION|Int64|  
|COLUMN_NAME|Строка|  
|COLUMN_GUID|Guid|  
|COLUMN_PROPID|Int64|  
|COLLATION|Int16|  
|CARDINALITY|Decimal|  
|PAGES|Int32|  
|FILTER_CONDITION|Строка|  
|INTEGRATED|Логическое|  
  
## <a name="see-also"></a>См. также раздел

- [Общие сведения об ADO.NET](ado-net-overview.md)
