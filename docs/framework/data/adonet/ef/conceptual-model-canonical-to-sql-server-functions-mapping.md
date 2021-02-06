---
description: 'Подробнее: концептуальная модель Каноническая для сопоставления функций SQL Server'
title: Сопоставление канонических функций концептуальной модели с функциями SQL Server
ms.date: 03/30/2017
ms.assetid: 1a2631bc-a426-4c0a-ba8d-26d9c80d39e2
ms.openlocfilehash: 25e366a45e91db97693c42b3c8d2febd912320ab
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99651071"
---
# <a name="conceptual-model-canonical-to-sql-server-functions-mapping"></a>Сопоставление канонических функций концептуальной модели с функциями SQL Server

В этом разделе описано, как канонические функции концептуальной модели сопоставляются соответствующим функциям SQL Server.  
  
## <a name="date-and-time-functions"></a>Функции даты и времени  

 В следующей таблице описано сопоставление функций даты и времени.  
  
|Канонические функции|Функции SQL Server|  
|-------------------------|--------------------------|  
|[AddDays(expression)](./language-reference/date-and-time-canonical-functions.md)|`DATEADD(day, number, date)`|  
|[AddHours(expression)](./language-reference/date-and-time-canonical-functions.md)|`DATEADD(hour, number, date)`|  
|[AddMicroseconds(expression)](./language-reference/date-and-time-canonical-functions.md)|`DATEADD(microsecond, number, date)`|  
|[AddMilliseconds(expression)](./language-reference/date-and-time-canonical-functions.md)|`DATEADD(millisecond, number, date)`|  
|[AddMinutes(expression)](./language-reference/date-and-time-canonical-functions.md)|`DATEADD(minute, number, date)`|  
|[AddMonths(expression)](./language-reference/date-and-time-canonical-functions.md)|`DATEADD(month, number, date)`|  
|[AddNanoseconds(expression)](./language-reference/date-and-time-canonical-functions.md)|`DATEADD(nanosecond, number, date)`|  
|[AddSeconds(expression)](./language-reference/date-and-time-canonical-functions.md)|`DATEADD(second, number, date)`|  
|[AddYears(expression)](./language-reference/date-and-time-canonical-functions.md)|`DATEADD(year, number, date)`|  
|[CreateDateTime(year, month, day, hour, minute, second)](./language-reference/date-and-time-canonical-functions.md)|В SQL Server 2000 и SQL Server 2005 на сервере создается форматированное значение `datetime`. В SQL Server 2008 и более поздних версиях на сервере создается значение `datetime2`.|  
|[CreateDateTimeOffset(year, month, day, hour, minute, second, tzoffset)](./language-reference/date-and-time-canonical-functions.md)|На сервере создается форматированное значение `datetimeoffset`.<br /><br /> Не поддерживается в SQL Server 2000 и SQL Server 2005.|  
|[CreateTime(hour, minute, second)](./language-reference/date-and-time-canonical-functions.md)|На сервере создается форматированное значение `time`.<br /><br /> Не поддерживается в SQL Server 2000 и SQL Server 2005.|  
|[Куррентдатетиме ()](./language-reference/date-and-time-canonical-functions.md)|`SysDateTime()` в SQLServer 2008.<br /><br /> `GetDate()` в SQLServer 2000 и SQLServer 2005.|  
|[CurrentDateTimeOffset()](./language-reference/date-and-time-canonical-functions.md)|`SysDateTimeOffset()` в SQL Server 2008.<br /><br /> Не поддерживается в SQL Server 2000 и SQL Server 2005.|  
|[CurrentUtcDateTime()](./language-reference/date-and-time-canonical-functions.md)|`SysUtcDateTime()` в SQLServer 2008. `GetUtcDate()` в SQL Server 2000 и SQL Server 2005.|  
|[DayOfYear(expression)](./language-reference/date-and-time-canonical-functions.md)|`DatePart(dayofyear, expression)`|  
|[Day(expression)](./language-reference/date-and-time-canonical-functions.md)|`DatePart(day, expression)`|  
|[DiffDays(startExpression, endExpression)](./language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(day, startdate, enddate)`|  
|[DiffHours(startExpression, endExpression)](./language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(hour, startdate, enddate)`|  
|[DiffMicroseconds(startExpression, endExpression)](./language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(microsecond, startdate, enddate)`|  
|[DiffMilliseconds(startExpression, endExpression)](./language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(millisecond, startdate, enddate)`|  
|[DiffMinutes(startExpression, endExpression)](./language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(minute, startdate, enddate)`|  
|[DiffNanoseconds(startExpression, endExpression)](./language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(nanosecond, startdate, enddate)`|  
|[DiffSeconds(startExpression, endExpression)](./language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(second, startdate, enddate)`|  
|[DiffYears(startExpression, endExpression)](./language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(year, startdate, enddate)`|  
|[GetTotalOffsetMinutes(DateTimeOffset)](./language-reference/date-and-time-canonical-functions.md)|`DatePart(tzoffset, expression)`|  
|[Hour(expression)](./language-reference/date-and-time-canonical-functions.md)|`DatePart(hour, expression)`|  
|[Millisecond(expression)](./language-reference/date-and-time-canonical-functions.md)|`DatePart(millisecond, expression)`|  
|[Minute(expression)](./language-reference/date-and-time-canonical-functions.md)|`DatePart(minute, expression)`|  
|[Month(expression)](./language-reference/date-and-time-canonical-functions.md)|`DatePart(month, expression)`|  
|[Второе (выражение)](./language-reference/date-and-time-canonical-functions.md)|`DatePart(second, expression)`|  
|[Truncate(expression)](./language-reference/date-and-time-canonical-functions.md)|Для SQL Server 2000 и SQL Server 2005 `datetime` на сервере создается усеченное отформатированное значение. Для SQL Server 2008 и более поздних версий `datetime2` `datetimeoffset` на сервере создается усеченное значение или.|  
|[Year(expression)](./language-reference/date-and-time-canonical-functions.md)|`DatePart(YEAR, expression)`|  
  
## <a name="aggregate-functions"></a>Агрегатные функции  

 В следующей таблице описано сопоставление агрегатных функций.  
  
|Канонические функции|Функции SQL Server|  
|-------------------------|--------------------------|  
|[Avg(expression)](./language-reference/aggregate-canonical-functions.md)|`AVG(expression)`|  
|[BigCount(expression)](./language-reference/aggregate-canonical-functions.md)|`BIGCOUNT(expression)`|  
|[Count(expression)](./language-reference/aggregate-canonical-functions.md)|`COUNT(expression)`|  
|[Min(expression)](./language-reference/aggregate-canonical-functions.md)|`MIN(expression)`|  
|[Max(expression)](./language-reference/aggregate-canonical-functions.md)|`MAX(expression)`|  
|[StDev(expression)](./language-reference/aggregate-canonical-functions.md)|`STDEV(expression)`|  
|[StDevP(expression)](./language-reference/aggregate-canonical-functions.md)|`STDEVP(expression)`|  
|[Sum(expression)](./language-reference/aggregate-canonical-functions.md)|`SUM(expression)`|  
|[Var(expression)](./language-reference/aggregate-canonical-functions.md)|`VAR(expression)`|  
|[VarP(expression)](./language-reference/aggregate-canonical-functions.md)|`VARP(expression)`|  
  
## <a name="math-functions"></a>Математические функции  

 В следующей таблице описано сопоставление математических функций.  
  
|Канонические функции|Функции SQL Server|  
|-------------------------|--------------------------|  
|[Abs(значение)](./language-reference/math-canonical-functions.md)|`ABS(value)`|  
|[Ceiling(value)](./language-reference/math-canonical-functions.md)|`CEILING(value)`|  
|[Floor(value)](./language-reference/math-canonical-functions.md)|`FLOOR(value)`|  
|[Power(value)](./language-reference/math-canonical-functions.md)|`POWER(value, exponent)`|  
|[Round(value)](./language-reference/math-canonical-functions.md)|`ROUND(value, digits, 0)`|  
|[Truncate](./language-reference/math-canonical-functions.md)|`ROUND(value , digits, 1)`|  
  
## <a name="string-functions"></a>Строковые функции  

 В следующей таблице описано сопоставление строковых функций.  
  
|Канонические функции|Функции SQL Server|  
|-------------------------|--------------------------|  
|[Contains(string, target)](./language-reference/string-canonical-functions.md)|`CHARINDEX(target, string)`|  
|[Concat(string1, string2)](./language-reference/string-canonical-functions.md)|string1 + string2|  
|[EndsWith(string, target)](./language-reference/string-canonical-functions.md)|`CHARINDEX(REVERSE(target), REVERSE(string)) = 1`<br /><br /> **Примечание** . `CHARINDEX` Функция возвращает, `false` Если объект `string` хранится в строковом столбце фиксированной длины и `target` является константой. В данном случае производится поиск по всей строке, включая конечные пробелы заполнения в строке. Данную проблему можно обойти, усекая данные из строки с фиксированной длиной перед передачей их функции `EndsWith`, как это показано в следующем примере: `EndsWith(TRIM(string), target)`|  
|[IndexOf(target, string2)](./language-reference/string-canonical-functions.md)|`CHARINDEX(target, string2)`|  
|[Left (string1, length)](./language-reference/string-canonical-functions.md)|`LEFT(string1, length)`|  
|[Length (string)](./language-reference/string-canonical-functions.md)|`LEN(string)`|  
|[LTrim(string)](./language-reference/string-canonical-functions.md)|`LTRIM(string)`|  
|[Right (string1, length)](./language-reference/string-canonical-functions.md)|`RIGHT (string1, length)`|  
|[Trim(string)](./language-reference/string-canonical-functions.md)|`LTRIM(RTRIM(string))`|  
|[Replace (string1, string2, string3)](./language-reference/string-canonical-functions.md)|`REPLACE(string1, string2, string3)`|  
|[Reverse (строка)](./language-reference/string-canonical-functions.md)|`REVERSE (string)`|  
|[RTrim(string)](./language-reference/string-canonical-functions.md)|`RTRIM(string)`|  
|[StartsWith(string, target)](./language-reference/string-canonical-functions.md)|`CHARINDEX(target, string)`|  
|[Substring(string, start, length)](./language-reference/string-canonical-functions.md)|`SUBSTRING(string, start, length)`|  
|[ToLower(string)](./language-reference/string-canonical-functions.md)|`LOWER(string)`|  
|[ToUpper(string)](./language-reference/string-canonical-functions.md)|`UPPER(string)`|  
  
## <a name="bitwise-functions"></a>Битовые функции  

 В следующей таблице описано сопоставление битовых функций.  
  
|Канонические функции|Функции SQL Server|  
|-------------------------|--------------------------|  
|[BitWiseAnd (value1, value2)](./language-reference/bitwise-canonical-functions.md)|Значение1 & value2|  
|[BitWiseNot (value)](./language-reference/bitwise-canonical-functions.md)|~value|  
|[BitWiseOr (value1, value2)](./language-reference/bitwise-canonical-functions.md)|Значение1 &#124; value2|  
|[BitWiseXor (value1, value2)](./language-reference/bitwise-canonical-functions.md)|value1 ^ value2|
