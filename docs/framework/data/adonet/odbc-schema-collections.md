---
description: 'Дополнительные сведения: коллекции схем ODBC'
title: Коллекции схемы ODBC
ms.date: 03/30/2017
ms.assetid: 1bb126a5-ceec-4649-a4bc-8aa19e801046
ms.openlocfilehash: ceac67e49914db7010e315a2dfcdb630bea1e29f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786203"
---
# <a name="odbc-schema-collections"></a>Коллекции схемы ODBC

В данном разделе рассматривается поддержка коллекций схем для драйверов ODBC для Microsoft SQL Server, Oracle и Microsoft Jet.

## <a name="microsoft-sql-server-odbc-driver"></a>Драйвер ODBC для Microsoft SQL Server

Драйвер ODBC для Microsoft SQL Server поддерживает следующие специальные коллекции схем в дополнение к общим коллекциям.

- Таблицы

- Индексы

- Столбцы

- Процедуры

- ProcedureColumns

- ProcedureParameters

- Представления

### <a name="tables-and-views"></a>Таблицы и представления

|ColumnName|DataType|
|----------------|--------------|
|TABLE_CAT|Строка|
|TABLE_SCHEM|Строка|
|TABLE_NAME|Строка|
|TABLE_TYPE|Строка|
|ПРИМЕЧАНИЯ|Строка|

### <a name="indexes"></a>Индексы

|ColumnName|DataType|
|----------------|--------------|
|TABLE_CAT|Строка|
|TABLE_SCHEM|Строка|
|TABLE_NAME|Строка|
|NON_UNIQUE|Int16|
|INDEX_QUALIFIER|Строка|
|INDEX_NAME|Строка|
|TYPE|Int16|
|ORDINAL_POSITION|Int16|
|COLUMN_NAME|Строка|
|ASC_OR_DESC|Строка|
|CARDINALITY|Int32|
|PAGES|Int32|
|FILTER_CONDITION|Строка|
|SS_TYPE_SCHEMA|Строка|
|SS_DATA_TYPE|Byte|

### <a name="columns"></a>Столбцы

|ColumnName|DataType|
|----------------|--------------|
|TABLE_CAT|Строка|
|TABLE_SCHEM|Строка|
|TABLE_NAME|Строка|
|COLUMN_NAME|Строка|
|DATA_TYPE|Int16|
|TYPE_NAME|Строка|
|COLUMN_SIZE|Int32|
|BUFFER_LENGTH|Int32|
|DECIMAL_DIGITS|Int16|
|NUM_PREC_RADIX|Int16|
|NULLABLE|Int16|
|ПРИМЕЧАНИЯ|Строка|
|COLUMN_DEF|Строка|
|SQL_DATA_TYPE|Int16|
|SQL_DATETIME_SUB|Int16|
|CHAR_OCTET_LENGTH|Int32|
|ORDINAL_POSITION|Int32|
|IS_NULLABLE|Строка|
|SS_TYPE_CATALOG|Строка|
|SS_TYPE_SCHEMA|Строка|
|SS_DATA_TYPE|Byte|

### <a name="procedures"></a>Процедуры

|ColumnName|DataType|
|----------------|--------------|
|PROCEDURE_CAT|Строка|
|PROCEDURE_SCHEM|Строка|
|PROCEDURE_NAME|Строка|
|NUM_INPUT_PARAMS|Int32|
|NUM_OUTPUT_PARAMS|Int32|
|NUM_RESULT_SETS|Int32|
|ПРИМЕЧАНИЯ|Строка|
|PROCEDURE_TYPE|Int16|

### <a name="procedurecolumns"></a>ProcedureColumns

|ColumnName|DataType|
|----------------|--------------|
|PROCEDURE_CAT|Строка|
|PROCEDURE_SCHEM|Строка|
|PROCEDURE_NAME|Строка|
|COLUMN_NAME|Строка|
|COLUMN_TYPE|Int16|
|DATA_TYPE|Int16|
|TYPE_NAME|Строка|
|COLUMN_SIZE|Int32|
|BUFFER_LENGTH|Int32|
|DECIMAL_DIGITS|Int16|
|NUM_PREC_RADIX|Int16|
|NULLABLE|Int16|
|ПРИМЕЧАНИЯ|Строка|
|COLUMN_DEF|Строка|
|SQL_DATA_TYPE|Int16|
|SQL_DATETIME_SUB|Int16|
|CHAR_OCTET_LENGTH|Int32|
|ORDINAL_POSITION|Int32|
|IS_NULLABLE|Строка|
|SS_TYPE_CATALOG|Строка|
|SS_TYPE_SCHEMA|Строка|
|SS_DATA_TYPE|Byte|

### <a name="procedureparameters"></a>ProcedureParameters

|ColumnName|DataType|
|----------------|--------------|
|PROCEDURE_CAT|Строка|
|PROCEDURE_SCHEM|Строка|
|PROCEDURE_NAME|Строка|
|COLUMN_NAME|Строка|
|COLUMN_TYPE|Int16|
|DATA_TYPE|Int16|
|TYPE_NAME|Строка|
|COLUMN_SIZE|Int32|
|BUFFER_LENGTH|Int32|
|DECIMAL_DIGITS|Int16|
|NUM_PREC_RADIX|Int16|
|NULLABLE|Int16|
|ПРИМЕЧАНИЯ|Строка|
|COLUMN_DEF|Строка|
|SQL_DATA_TYPE|Int16|
|SQL_DATETIME_SUB|Int16|
|CHAR_OCTET_LENGTH|Int32|
|ORDINAL_POSITION|Int32|
|IS_NULLABLE|Строка|
|SS_TYPE_CATALOG|Строка|
|SS_TYPE_SCHEMA|Строка|
|SS_DATA_TYPE|Byte|

## <a name="microsoft-oracle-odbc-driver"></a>Драйвер ODBC для Oracle (Майкрософт)

Драйвер Microsoft SQL Server ODBC для Oracle поддерживает следующие специальные коллекции схем в дополнение к общим коллекциям.

- Таблицы

- Столбцы

- Процедуры

- ProcedureColumns

- ProcedureParameters

- Представления

- Индексы

### <a name="tables-and-views"></a>Таблицы и представления

|ColumnName|DataType|
|----------------|--------------|
|TABLE_QUALIFIER|Строка|
|TABLE_OWNER|Строка|
|TABLE_NAME|Строка|
|TABLE_TYPE|Строка|
|ПРИМЕЧАНИЯ|Строка|

### <a name="columns"></a>Столбцы

|ColumnName|DataType|
|----------------|--------------|
|TABLE_QUALIFIER|Строка|
|TABLE_OWNER|Строка|
|TABLE_NAME|Строка|
|COLUMN_NAME|Строка|
|DATA_TYPE|Int16|
|TYPE_NAME|Строка|
|PRECISION|Int32|
|LENGTH|Int32|
|SCALE|Int16|
|RADIX|Int16|
|NULLABLE|Int16|
|ПРИМЕЧАНИЯ|Строка|
|ORDINAL_POSITION|Int32|

### <a name="procedures"></a>Процедуры

|ColumnName|DataType|
|----------------|--------------|
|PROCEDURE_QUALIFIER|Строка|
|PROCEDURE_OWNER|Строка|
|PROCEDURE_NAME|Строка|
|NUM_INPUT_PARAMS|Int16|
|NUM_OUTPUT_PARAMS|Int16|
|NUM_RESULT_SETS|Int16|
|ПРИМЕЧАНИЯ|Строка|
|PROCEDURE_TYPE|Int16|

### <a name="procedurecolumns"></a>ProcedureColumns

|ColumnName|DataType|
|----------------|--------------|
|PROCEDURE_QUALIFIER|Строка|
|PROCEDURE_OWNER|Строка|
|PROCEDURE_NAME|Строка|
|COLUMN_NAME|Строка|
|COLUMN_TYPE|Int16|
|DATA_TYPE|Int16|
|TYPE_NAME|Строка|
|PRECISION|Int32|
|LENGTH|Int32|
|SCALE|Int16|
|RADIX|Int16|
|NULLABLE|Int16|
|ПРИМЕЧАНИЯ|Строка|
|OVERLOAD|Int32|
|ORDINAL_POSITION|Int32|

## <a name="microsoft-jet-odbc-driver"></a>Драйвер ODBC для Jet (Майкрософт)

Драйвер ODBC для Jet (Майкрософт) поддерживает следующие специальные коллекции схем в дополнение к общим коллекциям.

- Таблицы

- Индексы

- Столбцы

- Процедуры

- ProcedureColumns

- ProcedureParameters

- Представления

### <a name="tables-and-views"></a>Таблицы и представления

|ColumnName|DataType|
|----------------|--------------|
|TABLE_QUALIFIER|Строка|
|TABLE_OWNER|Строка|
|TABLE_NAME|Строка|
|TABLE_TYPE|Строка|
|ПРИМЕЧАНИЯ|Строка|

### <a name="columns"></a>Столбцы

|ColumnName|DataType|
|----------------|--------------|
|TABLE_QUALIFIER|Строка|
|TABLE_OWNER|Строка|
|TABLE_NAME|Строка|
|COLUMN_NAME|Строка|
|DATA_TYPE|Int16|
|TYPE_NAME|Строка|
|PRECISION|Int32|
|LENGTH|Int32|
|SCALE|Int16|
|RADIX|Int16|
|NULLABLE|Int16|
|ПРИМЕЧАНИЯ|Строка|
|ORDINAL_POSITION|Int32|

### <a name="procedures"></a>Процедуры

|ColumnName|DataType|
|----------------|--------------|
|PROCEDURE_QUALIFIER|Строка|
|PROCEDURE_OWNER|Строка|
|PROCEDURE_NAME|Строка|
|NUM_INPUT_PARAMS|Int16|
|NUM_OUTPUT_PARAMS|Int16|
|NUM_RESULT_SETS|Int16|
|ПРИМЕЧАНИЯ|Строка|
|PROCEDURE_TYPE|Int16|

### <a name="procedurecolumns"></a>ProcedureColumns

|ColumnName|DataType|
|----------------|--------------|
|PROCEDURE_QUALIFIER|Строка|
|PROCEDURE_OWNER|Строка|
|PROCEDURE_NAME|Строка|
|COLUMN_NAME|Строка|
|COLUMN_TYPE|Int16|
|DATA_TYPE|Int16|
|TYPE_NAME|Строка|
|PRECISION|Int32|
|LENGTH|Int32|
|SCALE|Int16|
|RADIX|Int16|
|NULLABLE|Int16|
|ПРИМЕЧАНИЯ|Строка|
|OVERLOAD|Int32|
|ORDINAL_POSITION|Int32|

### <a name="procedureparameters"></a>ProcedureParameters

|ColumnName|DataType|
|----------------|--------------|
|PROCEDURE_CAT|Строка|
|PROCEDURE_SCHEM|Строка|
|PROCEDURE_NAME|Строка|
|COLUMN_NAME|Строка|
|COLUMN_TYPE|Int16|
|DATA_TYPE|Int16|
|TYPE_NAME|Строка|
|COLUMN_SIZE|Int32|
|BUFFER_LENGTH|Int32|
|DECIMAL_DIGITS|Int16|
|NUM_PREC_RADIX|Int16|
|NULLABLE|Int16|
|ПРИМЕЧАНИЯ|Строка|
|COLUMN_DEF|Строка|
|SQL_DATA_TYPE|Int16|
|SQL_DATETIME_SUB|Int16|
|CHAR_OCTET_LENGTH|Int32|
|ORDINAL_POSITION|Int32|
|IS_NULLABLE|Строка|

## <a name="see-also"></a>См. также

- [Общие сведения об ADO.NET](ado-net-overview.md)
