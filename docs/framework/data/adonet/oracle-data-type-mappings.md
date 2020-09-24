---
title: Сопоставления типов данных Oracle
ms.date: 03/30/2017
ms.assetid: ec34ae21-bbbb-4adb-b672-83865e2a8451
ms.openlocfilehash: 71a85f82ea3535cf7aec8dd92fbda6726a36fb81
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166577"
---
# <a name="oracle-data-type-mappings"></a>Сопоставления типов данных Oracle

В следующей таблице представлены типы данных Oracle и их сопоставления объекту <xref:System.Data.OracleClient.OracleDataReader>.  
  
|Тип данных Oracle|Тип данных .NET Framework, возвращаемый OracleDataReader.GetValue|Тип данных OracleClient, возвращаемый OracleDataReader.GetOracleValue|Remarks|  
|----------------------|--------------------------------------------------------------------|------------------------------------------------------------------------|-------------|  
|**BFILE**|**Byte []**|<xref:System.Data.OracleClient.OracleBFile>||  
|**BLOB**|**Byte []**|<xref:System.Data.OracleClient.OracleLob>||  
|**CHAR**|**String**|<xref:System.Data.OracleClient.OracleString>||  
|**CLOB**|**String**|<xref:System.Data.OracleClient.OracleLob>||  
|**DATE**|**DateTime**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**FLOAT**|**Decimal**|<xref:System.Data.OracleClient.OracleNumber>|Этот тип данных является псевдонимом для типа данных **Number** и предназначен для того, чтобы функция <xref:System.Data.OracleClient.OracleDataReader> возвращала **System. Decimal** или <xref:System.Data.OracleClient.OracleNumber> вместо значения с плавающей запятой. Использование типа данных .NET Framework может вызвать переполнение.|  
|**INTEGER**|**Decimal**|<xref:System.Data.OracleClient.OracleNumber>|Этот тип данных является псевдонимом для типа данных **Number (38)** и предназначен для того, чтобы функция <xref:System.Data.OracleClient.OracleDataReader> возвращала **System. Decimal** или <xref:System.Data.OracleClient.OracleNumber> вместо целого значения. Использование типа данных .NET Framework может вызвать переполнение.|  
|**INTERVAL YEAR TO MONTH**|**Int32**|<xref:System.Data.OracleClient.OracleMonthSpan>||  
|**INTERVAL DAY TO SECOND**|**TimeSpan**|<xref:System.Data.OracleClient.OracleTimeSpan>||  
|**LONG**|**String**|<xref:System.Data.OracleClient.OracleString>||  
|**LONG RAW**|**Byte []**|<xref:System.Data.OracleClient.OracleBinary>||  
|**NCHAR**|**String**|<xref:System.Data.OracleClient.OracleString>||  
|**NCLOB**|**String**|<xref:System.Data.OracleClient.OracleLob>||  
|**Нумерация**|**Decimal**|<xref:System.Data.OracleClient.OracleNumber>|Использование типа данных .NET Framework может вызвать переполнение.|  
|**NVARCHAR2**|**String**|<xref:System.Data.OracleClient.OracleString>||  
|**RAW**|**Byte []**|<xref:System.Data.OracleClient.OracleBinary>||  
|**REF CURSOR**|||Тип данных **курсора Oracle ref** не поддерживается <xref:System.Data.OracleClient.OracleDataReader> объектом.|  
|**ROWID**|**String**|<xref:System.Data.OracleClient.OracleString>||  
|**TIMESTAMP**|**DateTime**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**TIMESTAMP WITH LOCAL TIME ZONE**|**DateTime**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**МЕТКА ВРЕМЕНИ С ЧАСОВЫМ ПОЯСОМ**|**DateTime**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**ЦЕЛОЕ ЧИСЛО БЕЗ ЗНАКА**|**Число**|<xref:System.Data.OracleClient.OracleNumber>|Этот тип данных является псевдонимом для типа данных **Number (38)** и предназначен для того, чтобы функция <xref:System.Data.OracleClient.OracleDataReader> возвращала значение **System. Decimal** или <xref:System.Data.OracleClient.OracleNumber> вместо целого числа без знака. Использование типа данных .NET Framework может вызвать переполнение.|  
|**VARCHAR2**|**String**|<xref:System.Data.OracleClient.OracleString>||  
  
 В следующей таблице перечислены типы данных Oracle и типы данных .NET Framework (**System. Data. DbType** и <xref:System.Data.OracleClient.OracleType> ), которые используются при их привязке в качестве параметров.  
  
|Тип данных Oracle|Перечисление DbType, которое привязывается как параметр|Перечисление OracleType, которое привязывается как параметр|Remarks|  
|----------------------|-----------------------------------------------|---------------------------------------------------|-------------|  
|**BFILE**||**BСведения**|Oracle допускает привязку типа **BFILE** только в качестве параметра **BFILE** . Поставщик данных .NET для Oracle не создает его автоматически при попытке привязать значение, отличное от**BFILE** , например **Byte []** или <xref:System.Data.OracleClient.OracleBinary> .|  
|**BLOB**||**Большие двоичные объекты**|Oracle позволяет привязать **большой двоичный объект** только в качестве параметра **большого двоичного объекта** . Поставщик данных .NET для Oracle не создает его автоматически при попытке привязать значение, отличное от**большого двоичного объекта** , например **Byte []** или <xref:System.Data.OracleClient.OracleBinary> .|  
|**CHAR**|**AnsiStringFixedLength**|**Char**||  
|**CLOB**||**CLOB**|Oracle допускает привязку **CLOB** только в качестве параметра **CLOB** . Поставщик данных .NET для Oracle не создает его автоматически при попытке привязать значение, не являющееся**CLOB** , например **System. String** или <xref:System.Data.OracleClient.OracleString> .|  
|**DATE**|**DateTime**|**DateTime**||  
|**FLOAT**|**Одинарный, двойной, десятичный**|**Float, Double, Number**|<xref:System.Data.OracleClient.OracleParameter.Size%2A> Определяет **System. Data. DBType** и <xref:System.Data.OracleClient.OracleType> .|  
|**INTEGER**|**SByte, Int16, Int32, Int64, Decimal**|**SByte, Int16, Int32, Number**|<xref:System.Data.OracleClient.OracleParameter.Size%2A> Определяет **System. Data. DBType** и <xref:System.Data.OracleClient.OracleType> .|  
|**INTERVAL YEAR TO MONTH**|**Int32**|**IntervalYearToMonth**|<xref:System.Data.OracleClient.OracleType> доступен только при использование как клиентского, так и серверного программного обеспечения Oracle 9i.|  
|**INTERVAL DAY TO SECOND**|**Объект**|**IntervalDayToSecond**|<xref:System.Data.OracleClient.OracleType> доступен только при использование как клиентского, так и серверного программного обеспечения Oracle 9i.|  
|**LONG**|**AnsiString**|**LongVarChar**||  
|**LONG RAW**|**Двоичный**|**LongRaw**||  
|**NCHAR**|**StringFixedLength**|**NChar**||  
|**NCLOB**||**NClob**|Oracle позволяет привязать параметр **NCLOB** только в качестве параметра **NCLOB** . Поставщик данных .NET для Oracle не создает его автоматически при попытке привязать значение, отличное от**NCLOB** , например **System. String** или <xref:System.Data.OracleClient.OracleString> .|  
|**Нумерация**|**VarNumeric**|**Число**||  
|**NVARCHAR2**|**String**|**NVarChar**||  
|**RAW**|**Двоичный**|**Raw**||  
|**REF CURSOR**||**Курсор**|Дополнительные сведения см. в разделе [Oracle REF CURSOR](oracle-ref-cursors.md).|  
|**ROWID**|**AnsiString**|**ROWID**||  
|**TIMESTAMP**|**DateTime**|**Timestamp**|<xref:System.Data.OracleClient.OracleType> доступен только при использование как клиентского, так и серверного программного обеспечения Oracle 9i.|  
|**TIMESTAMP WITH LOCAL TIME ZONE**|**DateTime**|**TimestampLocal**|<xref:System.Data.OracleClient.OracleType> доступен только при использование как клиентского, так и серверного программного обеспечения Oracle 9i.|  
|**МЕТКА ВРЕМЕНИ С ЧАСОВЫМ ПОЯСОМ**|**DateTime**|**TimestampWithTz**|<xref:System.Data.OracleClient.OracleType> доступен только при использование как клиентского, так и серверного программного обеспечения Oracle 9i.|  
|**ЦЕЛОЕ ЧИСЛО БЕЗ ЗНАКА**|**Byte, UInt16, UInt32, UInt64, Decimal**|**Byte, UInt16, Uint32, Number**|<xref:System.Data.OracleClient.OracleParameter.Size%2A> Определяет **System. Data. DBType** и <xref:System.Data.OracleClient.OracleType> .|  
|**VARCHAR2**|**AnsiString**|**VarChar**||  
  
 Значения **инпутаутпут**, **Output**и **ReturnValue** **параметердиректион** , используемые <xref:System.Data.OracleClient.OracleParameter.Value%2A> свойством <xref:System.Data.OracleClient.OracleParameter> объекта, являются .NET Framework типами данных, если только входное значение не является типом данных Oracle (например, <xref:System.Data.OracleClient.OracleNumber> или <xref:System.Data.OracleClient.OracleString> ). Это не относится к типам данных **ref Cursor**, **BFILE**или **LOB** .  
  
## <a name="see-also"></a>См. также раздел

- [Oracle и ADO.NET](oracle-and-adonet.md)
- [Общие сведения об ADO.NET](ado-net-overview.md)
