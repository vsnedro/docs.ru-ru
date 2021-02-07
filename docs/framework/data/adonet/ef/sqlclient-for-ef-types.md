---
description: 'Дополнительные сведения о: SqlClient для Entity Framework'
title: Типы SqlClient для Entity Framework
ms.date: 03/30/2017
ms.assetid: f2a95ead-c845-4e97-9fb3-04b444f7ed81
ms.openlocfilehash: 92bd557198d203229394fb3a4c2fe286e217edca
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99673184"
---
# <a name="sqlclient-for-entity-frameworktypes"></a>Типы SqlClient для Entity Framework

Файл манифеста поставщика данных .NET Framework для SQL Server (SqlClient) содержит список типов-примитивов этого поставщика, аспекты каждого типа, сопоставления типов-примитивов между концептуальной моделью и режимом хранения, а также правила повышения и преобразования типов-примитивов концептуальной модели и модели хранения.  
  
 В следующей таблице описываются типы баз данных SQL Server 2008, SQL Server 2005 и SQL Server 2000, а также о том, как эти типы сопоставляются с типами концептуальной модели. Некоторые новые типы, которые появились в более поздних версиях SQL Server 2008, не поддерживаются в предыдущих версиях SQL Server. Эти типы указаны в таблице ниже.  
  
|Тип поставщика<br /><br /> name|Тип поставщика<br /><br /> attributes|`EDMSimpleType`<br /><br /> name|Аспекты|  
|----------------------------|----------------------------------|------------------------------|------------|  
|`bit`|Недоступно|`Edm.Boolean`|Недоступно|  
|`tinyint`|Недоступно|`Edm.Byte`|Недоступно|  
|`smallint`|Недоступно|`Edm.Int16`|Недоступно|  
|`int`|Недоступно|`Edm.Int32`|Недоступно|  
|`bigint`|Недоступно|`Edm.Int64`|Недоступно|  
|`float`|Недоступно|`Edm.Double`|Недоступно|  
|`real`|Недоступно|`Edm.Double`|Недоступно|  
|`decimal`|Недоступно|`Edm.Decimal`|Обеспечивают<br /><br /> — Минимум: 1<br /><br /> — Максимум: 38<br /><br /> -По умолчанию: 18<br /><br /> -Constant: false<br /><br /> Масштаб<br /><br /> — Минимум: 0<br /><br /> — Максимум: 38<br /><br /> -По умолчанию: 0<br /><br /> -Constant: false|  
|`numeric`|Недоступно|`Edm.Decimal`|Обеспечивают<br /><br /> — Минимум: 1<br /><br /> — Максимум: 38<br /><br /> -По умолчанию: 18<br /><br /> -Constant: false<br /><br /> Масштаб<br /><br /> — Минимум: 0<br /><br /> — Максимум: 38<br /><br /> -По умолчанию: 0<br /><br /> -Constant: false|  
|`smallmoney`|Недоступно|`Edm.Decimal`|Обеспечивают<br /><br /> -По умолчанию: 10<br /><br /> -Constant: true<br /><br /> Масштаб<br /><br /> -По умолчанию: 4<br /><br /> -Constant: true|  
|`money`|Недоступно|`Edm.Decimal`|Обеспечивают<br /><br /> -По умолчанию: 19<br /><br /> -Constant: true<br /><br /> Масштаб<br /><br /> -По умолчанию: 4<br /><br /> -Constant: true|  
|`binary`|Недоступно|`Edm.Binary`|MaxLength<br /><br /> — Минимум: 1<br /><br /> — Максимум: 8000<br /><br /> -По умолчанию: 8000<br /><br /> -Constant: false<br /><br /> FixedLength<br /><br /> -По умолчанию: true<br /><br /> -Constant: true|  
|`varbinary`|Недоступно|`Edm.Binary`|MaxLength<br /><br /> — Минимум: 1<br /><br /> — Максимум: 8000<br /><br /> -По умолчанию: 8000<br /><br /> -Constant: false<br /><br /> FixedLength<br /><br /> -По умолчанию: false<br /><br /> -Constant: true|  
|`varbinary(max)`<br /><br /> Примечание. Этот тип не поддерживается в SQL Server 2000.|Недоступно|`Edm.Binary`|MaxLength<br /><br /> -По умолчанию: 214748364780<br /><br /> -Constant: true<br /><br /> FixedLength<br /><br /> -По умолчанию: false<br /><br /> -Constant: true|  
|`image`|Недоступно|`Edm.Binary`|MaxLength<br /><br /> -По умолчанию: 2147483647<br /><br /> -Constant: true<br /><br /> FixedLength<br /><br /> -По умолчанию: false<br /><br /> -Constant: true|  
|`timestamp`|Недоступно|`Edm.Binary`|MaxLength<br /><br /> -По умолчанию: 8<br /><br /> -Constant: true<br /><br /> FixedLength<br /><br /> -По умолчанию: true<br /><br /> -Constant: true|  
|`rowversion`|Недоступно|`Edm.Binary`|MaxLength<br /><br /> -По умолчанию: 8<br /><br /> -Constant: true<br /><br /> FixedLength<br /><br /> -По умолчанию: true<br /><br /> -Constant: true|  
|`smalldatetime`|Недоступно|`Edm.DateTime`|Обеспечивают<br /><br /> -По умолчанию: 0<br /><br /> -Constant: true|  
|`datetime`|Недоступно|`Edm.DateTime`|Обеспечивают<br /><br /> -По умолчанию: 3<br /><br /> -Constant: true|  
|`date`<br /><br /> Примечание. Этот тип не поддерживается в SQL Server 2005 и SQL Server 2000.|Недоступно|`Edm.DateTime`|Обеспечивают<br /><br /> -По умолчанию: 0<br /><br /> -Constant: false|  
|`time`<br /><br /> Примечание. Этот тип не поддерживается в SQL Server 2005 и SQL Server 2000.|Недоступно|`Edm.Time`|Обеспечивают<br /><br /> -По умолчанию: 7<br /><br /> -Constant: false|  
|`datetime2`<br /><br /> Примечание. Этот тип не поддерживается в SQL Server 2005 и SQL Server 2000.|Недоступно|`Edm.DateTime`|Обеспечивают<br /><br /> -По умолчанию: 7<br /><br /> -Constant: false|  
|`datetimeoffset`<br /><br /> Примечание. Этот тип не поддерживается в SQL Server 2005 и SQL Server 2000.|Недоступно|`Edm.DateTimeOffset`|Обеспечивают<br /><br /> -По умолчанию: 7<br /><br /> -Constant: false|  
|`nvarchar`<br /><br /> Примечание. Этот тип не поддерживается в SQL Server 2000.|Недоступно|`Edm.String`|MaxLength<br /><br /> — Минимум: 1<br /><br /> — Максимум: 4000<br /><br /> -По умолчанию: 4000<br /><br /> -Constant: false<br /><br /> Юникод:<br /><br /> -По умолчанию: true<br /><br /> -Constant: true<br /><br /> FixedLength<br /><br /> -По умолчанию: false<br /><br /> -Constant: true|  
|`varchar`<br /><br /> Примечание. Этот тип не поддерживается в SQL Server 2000.|Недоступно|`Edm.String`|MaxLength<br /><br /> — Минимум: 1<br /><br /> — Максимум: 8000<br /><br /> -По умолчанию: 8000<br /><br /> -Constant: false<br /><br /> Юникод:<br /><br /> -По умолчанию: false<br /><br /> -Constant: true<br /><br /> FixedLength<br /><br /> -По умолчанию: false<br /><br /> -Constant: true|  
|`char`|Недоступно|`Edm.String`|MaxLength<br /><br /> — Минимум: 1<br /><br /> — Максимум: 8000<br /><br /> -По умолчанию: 8000<br /><br /> -Constant: false<br /><br /> Юникод:<br /><br /> -По умолчанию: false<br /><br /> -Constant: true<br /><br /> FixedLength<br /><br /> -По умолчанию: true<br /><br /> -Constant: true|  
|`nchar`|Недоступно|`Edm.String`|MaxLength<br /><br /> — Минимум: 1<br /><br /> — Максимум: 4000<br /><br /> -По умолчанию: 4000<br /><br /> -Constant: false<br /><br /> Юникод:<br /><br /> -По умолчанию: true<br /><br /> -Constant: true<br /><br /> FixedLength<br /><br /> -По умолчанию: true<br /><br /> -Constant: true|  
|`varchar`(`max`)|Недоступно|`Edm.String`|MaxLength<br /><br /> -По умолчанию: 2147483647<br /><br /> -Constant: true<br /><br /> Юникод:<br /><br /> -По умолчанию: false<br /><br /> -Constant: true<br /><br /> FixedLength<br /><br /> -По умолчанию: false<br /><br /> -Constant: true|  
|`nvarchar`(`max`)|Недоступно|`Edm.String`|MaxLength<br /><br /> -По умолчанию: 1073741823<br /><br /> -Constant: true<br /><br /> Юникод:<br /><br /> -По умолчанию: true<br /><br /> -Constant: true<br /><br /> FixedLength<br /><br /> -По умолчанию: false<br /><br /> -Constant: true|  
|`ntext`|Равное сравнимое: false<br /><br /> Сравниваемые порядок: false|`Edm.String`|MaxLength<br /><br /> -По умолчанию: 1073741823<br /><br /> -Constant: true<br /><br /> Юникод:<br /><br /> -По умолчанию: false<br /><br /> -Constant: true<br /><br /> FixedLength<br /><br /> -По умолчанию: false<br /><br /> -Constant: true|  
|`text`|Равное сравнимое: false<br /><br /> Сравниваемые порядок: false|`Edm.String`|MaxLength<br /><br /> -По умолчанию: 2147483647<br /><br /> -Constant: true<br /><br /> Юникод:<br /><br /> -По умолчанию: false<br /><br /> -Constant: true<br /><br /> FixedLength<br /><br /> -По умолчанию: false<br /><br /> -Constant: true|  
|`Unique`<br /><br /> `identifier`|Равное сравнимое: true<br /><br /> Сравниваемые порядок: true|`Edm.Guid`|Недоступно|  
|`xml`|Равное сравнимое: false<br /><br /> Сравниваемые порядок: false|`Edm.String`|MaxLength<br /><br /> -По умолчанию: 1073741823<br /><br /> -Constant: true<br /><br /> Юникод:<br /><br /> -По умолчанию: true<br /><br /> -Constant: true<br /><br /> FixedLength<br /><br /> -По умолчанию: false<br /><br /> -Constant: true|  
  
## <a name="see-also"></a>См. также

- [Спецификации CSDL, SSDL и MSL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)
