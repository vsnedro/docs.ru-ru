---
description: 'Дополнительные сведения: OLE DB сопоставления типов данных'
title: Сопоставления типов данных OLE DB
ms.date: 03/30/2017
ms.assetid: 04bcb259-59d3-4fd7-894d-4f0dd0c68069
ms.openlocfilehash: 8dd750754a67921437ca9b8fac751857961385cc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786190"
---
# <a name="ole-db-data-type-mappings"></a>Сопоставления типов данных OLE DB

В следующей таблице показан тип выводимого платформа .NET Framework для типов данных из платформа .NET Framework поставщика данных для ADO и OLE DB ( <xref:System.Data.OleDb> ). Приведены также типизированные методы доступа для <xref:System.Data.OleDb.OleDbDataReader>.  
  
|Тип ADO|Тип OLE DB|Тип платформы .NET Framework|Платформа .NET Framework типизированный метод доступа|  
|--------------|-----------------|----------------------------------------------------------------------|--------------------------------------------------------------------------------|  
|adBigInt|DBTYPE_I8|Int64|GetInt64()|  
|adBinary|DBTYPE_BYTES|Byte[]|GetBytes()|  
|adBoolean|DBTYPE_BOOL|Логическое|GetBoolean()|  
|adBSTR|DBTYPE_BSTR|Строка|GetString()|  
|adChapter|DBTYPE_HCHAPTER|Поддерживается с помощью `DataReader`. См. раздел [Получение данных с помощью DataReader](retrieving-data-using-a-datareader.md).|GetValue()|  
|adChar|DBTYPE_STR|Строка|GetString()|  
|adCurrency|DBTYPE_CY|Decimal|GetDecimal()|  
|adDate|DBTYPE_DATE|DateTime|GetDateTime()|  
|adDBDate|DBTYPE_DBDATE|DateTime|GetDateTime()|  
|adDBTime|DBTYPE_DBTIME|DateTime|GetDateTime()|  
|adDBTimeStamp|DBTYPE_DBTIMESTAMP|DateTime|GetDateTime()|  
|adDecimal|DBTYPE_DECIMAL|Decimal|GetDecimal()|  
|adDouble|DBTYPE_R8|Double|GetDouble()|  
|adError|DBTYPE_ERROR|ExternalException|GetValue()|  
|adFileTime|DBTYPE_FILETIME|DateTime|GetDateTime()|  
|adGUID|DBTYPE_GUID|Guid|GetGuid()|  
|adIDispatch|DBTYPE_IDISPATCH *|Объект|GetValue()|  
|adInteger|DBTYPE_I4|Int32|GetInt32()|  
|adIUnknown|DBTYPE_IUNKNOWN *|Объект|GetValue()|  
|adNumeric|DBTYPE_NUMERIC|Decimal|GetDecimal()|  
|adPropVariant|DBTYPE_PROPVARIANT|Объект|GetValue()|  
|adSingle|DBTYPE_R4|Single|GetFloat()|  
|adSmallInt|DBTYPE_I2|Int16|GetInt16()|  
|adTinyInt|DBTYPE_I1|Byte|GetByte()|  
|adUnsignedBigInt|DBTYPE_UI8|UInt64|GetValue()|  
|adUnsignedInt|DBTYPE_UI4|UInt32|GetValue()|  
|adUnsignedSmallInt|DBTYPE_UI2|UInt16|GetValue()|  
|adUnsignedTinyInt|DBTYPE_UI1|Byte|GetByte()|  
|adVariant|DBTYPE_VARIANT|Объект|GetValue()|  
|adWChar|DBTYPE_WSTR|Строка|GetString()|  
|adUserDefined|DBTYPE_UDT|не поддерживается||  
|adVarNumeric|DBTYPE_VARNUMERIC|не поддерживается||  
  
 \* Для типов OLE DB `DBTYPE_IUNKNOWN` и `DBTYPE_IDISPATCH` ссылка на объект является упакованным представлением указателя.  
  
## <a name="see-also"></a>См. также

- [Извлечение и изменение данных в ADO.NET](retrieving-and-modifying-data.md)
- [Общие сведения об ADO.NET](ado-net-overview.md)
