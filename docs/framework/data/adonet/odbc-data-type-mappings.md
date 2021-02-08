---
description: Дополнительные сведения см. в статье сопоставления типов данных ODBC.
title: Сопоставления типов данных ODBC
ms.date: 03/30/2017
ms.assetid: 43c35d32-831d-480f-a150-78f7e869d17f
ms.openlocfilehash: 0589f065da852158d35ee1104618dd13e5b2d36f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786216"
---
# <a name="odbc-data-type-mappings"></a>Сопоставления типов данных ODBC

В следующей таблице показан тип выводимого платформа .NET Framework для типов данных из платформа .NET Framework поставщика данных для ODBC ( <xref:System.Data.Odbc> ). Приведены также типизированные методы доступа для <xref:System.Data.Odbc.OdbcDataReader>.  
  
|Тип ODBC|Тип платформы .NET Framework|Платформа .NET Framework типизированный метод доступа|  
|---------------|----------------------------------------------------------------------|--------------------------------------------------------------------------------|  
|SQL_BIGINT|Int64|GetInt64()|  
|SQL_BINARY|Byte[]|GetBytes()|  
|SQL_BIT|Логическое|GetBoolean()|  
|SQL_CHAR|Строка<br /><br /> Char[]|GetString()<br /><br /> GetChars()|  
|SQL_DECIMAL|Decimal|GetDecimal()|  
|SQL_DOUBLE|Double|GetDouble()|  
|SQL_GUID|Guid|GetGuid()|  
|SQL_INTEGER|Int32|GetInt32()|  
|SQL_LONG_VARCHAR|Строка<br /><br /> Char[]|GetString()<br /><br /> GetChars()|  
|SQL_LONGVARBINARY|Byte[]|GetBytes()|  
|SQL_NUMERIC|Decimal|GetDecimal()|  
|SQL_REAL|Один|GetFloat()|  
|SQL_SMALLINT|Int16|GetInt16()|  
|SQL_TINYINT|Byte|GetByte()|  
|SQL_TYPE_TIMES|Дата и время|GetDateTime()|  
|SQL_TYPE_TIMESTAMP|Дата и время|GetDateTime()|  
|SQL_VARBINARY|Byte[]|GetBytes()|  
|SQL_WCHAR|Строка<br /><br /> Char[]|GetString()<br /><br /> GetChars()|  
|SQL_WLONGVARCHAR|Строка<br /><br /> Char[]|GetString()<br /><br /> GetChars()|  
|SQL_WVARCHAR|Строка<br /><br /> Char[]|GetString()<br /><br /> GetChars()|  
  
## <a name="see-also"></a>См. также

- [Извлечение и изменение данных в ADO.NET](retrieving-and-modifying-data.md)
- [Общие сведения об ADO.NET](ado-net-overview.md)
