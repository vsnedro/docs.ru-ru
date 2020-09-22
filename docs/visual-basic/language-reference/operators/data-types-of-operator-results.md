---
title: Типы данных результатов оператора
ms.date: 07/20/2015
helpviewer_keywords:
- data types [Visual Basic], operator result data types
- result data types [Visual Basic]
- operator result data types [Visual Basic]
- operators [Visual Basic], data types
- data types [Visual Basic], ranges
- operators [Visual Basic], result data types
ms.assetid: 9d524533-e1a1-4aa8-b1b8-622068173d06
ms.openlocfilehash: f7a1249cec159f98ede48b960fadc5e2ff4a75f3
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90867099"
---
# <a name="data-types-of-operator-results-visual-basic"></a>Типы данных результатов оператора (Visual Basic)

Visual Basic определяет тип данных результата операции на основе типов данных операндов. В некоторых случаях это может быть тип данных с большим диапазоном, чем любой из операндов.  
  
## <a name="data-type-ranges"></a>Диапазоны типов данных  

 Диапазоны соответствующих типов данных в порядке от меньшего к большему, имеют следующий вид:  
  
- [Логическое значение](../data-types/boolean-data-type.md) — два возможных значения  
  
- [SByte](../data-types/sbyte-data-type.md), [Byte](../data-types/byte-data-type.md) — 256 возможных целочисленных значений  
  
- [Short](../data-types/short-data-type.md), [UShort](../data-types/ushort-data-type.md) — 65 536 (6.5... E + 4) возможные целочисленные значения  
  
- [Integer](../data-types/integer-data-type.md), [UInteger](../data-types/uinteger-data-type.md) — 4 294 967 296 (4.2... E + 9) возможных целочисленных значений  
  
- [Long](../data-types/long-data-type.md), [ulong](../data-types/ulong-data-type.md) — 18446744073709551615 (1.8... E + 19) возможных целочисленных значений  
  
- [Десятичное число](../data-types/decimal-data-type.md) — 1.5... E + 29 возможных целочисленных значений, максимальный диапазон 7,9... E + 28 (абсолютное значение)  
  
- [Single](../data-types/single-data-type.md) — максимальный диапазон 3.4... E + 38 (абсолютное значение)  
  
- [Double](../data-types/double-data-type.md) — максимальный диапазон 1.7... E + 308 (абсолютное значение)  
  
 Дополнительные сведения о типах данных Visual Basic см. в разделе [типы данных](../data-types/index.md).  
  
 Если операнду присвоено значение [Nothing](../nothing.md), то арифметические операторы Visual Basic обрабатывают его как ноль.  
  
## <a name="decimal-arithmetic"></a>Десятичная арифметика  

 Обратите внимание, что тип данных [Decimal](../data-types/decimal-data-type.md) не является ни типом с плавающей запятой, ни целым числом.  
  
 Если один из операндов `+` операции,, `–` `*` , `/` или имеет значение, `Mod` `Decimal` а другой — нет `Single` или `Double` , Visual Basic расширяет другой операнд до `Decimal` . Он выполняет операцию в `Decimal` , а тип данных Result — `Decimal` .  
  
## <a name="floating-point-arithmetic"></a>Арифметика с плавающей запятой  

 Visual Basic выполняет большинство арифметических операций с плавающей запятой в [Double](../data-types/double-data-type.md), что является наиболее эффективным типом данных для таких операций. Однако если один операнд является [одиночным](../data-types/single-data-type.md) , а другой — нет `Double` , Visual Basic выполняет операцию в `Single` . Он расширяет каждый операнд по мере необходимости до соответствующего типа данных перед операцией, а результат имеет этот тип данных.  
  
### <a name="-and--operators"></a>Операторы/и ^  

 `/`Оператор определяется только для типов данных [Decimal](../data-types/decimal-data-type.md), [Single](../data-types/single-data-type.md)и [Double](../data-types/double-data-type.md) . Visual Basic расширяет каждый операнд по мере необходимости до соответствующего типа данных перед операцией, а результат будет иметь этот тип данных.  
  
 В следующей таблице показаны типы данных результата для `/` оператора. Обратите внимание, что эта таблица является симметричной. для данного сочетания типов данных операндов тип данных результата одинаковый, независимо от порядка операндов.  
  
||||||  
|---|---|---|---|---|  
||`Decimal`|`Single`|`Double`|Любой целочисленный тип|  
|`Decimal`|Decimal|Single|Double|Decimal|  
|`Single`|Single|Single|Double|Single|  
|`Double`|Double|Double|Double|Double|  
|Любой целочисленный тип|Decimal|Single|Double|Double|  
  
 `^`Оператор определяется только для `Double` типа данных. Visual Basic расширяет каждый операнд по мере необходимости `Double` перед операцией, а тип данных Result всегда `Double` .  
  
## <a name="integer-arithmetic"></a>Целочисленная арифметика  

 Тип данных результата целочисленной операции зависит от типов данных операндов. Как правило, Visual Basic использует следующие политики для определения типа данных result:  
  
- Если оба операнда бинарного оператора имеют один и тот же тип данных, результат будет иметь этот тип данных. Исключением является `Boolean` , что принудительно `Short` .  
  
- Если неподписанный операнд участвует в подписанном операнде, то результат имеет тип со знаком, содержащий по меньшей мере один из операндов с диапазоном.  
  
- В противном случае результат обычно имеет больший из двух типов данных операндов.  
  
 Обратите внимание, что тип данных результата может отличаться от типа данных операнда.  
  
> [!NOTE]
> Тип данных результата не всегда достаточен для хранения всех возможных значений, полученных в результате операции. <xref:System.OverflowException>Исключение может возникнуть, если значение слишком велико для типа данных результата.  
  
### <a name="unary--and--operators"></a>Унарные операторы + и –  

 В следующей таблице показаны типы данных результата для двух унарных операторов `+` и `–` .  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|Унар `+`|Short|SByte|Byte|Short|UShort|Целое число|UInteger|Long|ULong|  
|Унар `–`|Short|SByte|Short|Short|Целое число|Целое число|Long|Long|Decimal|  
  
### <a name="-and--operators"></a><\< and > Операторы>  

 В следующей таблице показаны типы данных результата для двух операторов поразрядного сдвига `<<` и `>>` . Visual Basic обрабатывает каждый оператор сдвига в битах как унарный оператор в его левом операнде (битовый шаблон для сдвига).  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`<<`, `>>`|Short|SByte|Byte|Short|UShort|Целое число|UInteger|Long|ULong|  
  
 Если левый операнд имеет значение `Decimal` , `Single` , `Double` или `String` , Visual Basic пытается преобразовать его `Long` перед операцией, а тип данных Result — `Long` . Правый операнд (число битовых позиций для сдвига) должен быть `Integer` или типом, который расширяется до `Integer` .  
  
### <a name="binary----and-mod-operators"></a>Бинарные операторы +, –, \* и mod  

 В следующей таблице показаны типы данных результата для бинарных `+` операторов и операторов и `–` `*` `Mod` . Обратите внимание, что эта таблица является симметричной. для данного сочетания типов данных операндов тип данных результата одинаковый, независимо от порядка операндов.  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Boolean`|Short|SByte|Short|Short|Целое число|Целое число|Long|Long|Decimal|  
|`SByte`|SByte|SByte|Short|Short|Целое число|Целое число|Long|Long|Decimal|  
|`Byte`|Short|Short|Byte|Short|UShort|Целое число|UInteger|Long|ULong|  
|`Short`|Short|Short|Short|Short|Целое число|Целое число|Long|Long|Decimal|  
|`UShort`|Целое число|Целое число|UShort|Целое число|UShort|Целое число|UInteger|Long|ULong|  
|`Integer`|Целое число|Целое число|Целое число|Целое число|Целое число|Целое число|Long|Long|Decimal|  
|`UInteger`|Long|Long|UInteger|Long|UInteger|Long|UInteger|Long|ULong|  
|`Long`|Long|Long|Long|Long|Long|Long|Long|Long|Decimal|  
|`ULong`|Decimal|Decimal|ULong|Decimal|ULong|Decimal|ULong|Decimal|ULong|  
  
### <a name="-operator"></a>Оператор \\  

 В следующей таблице показаны типы данных результата для `\` оператора. Обратите внимание, что эта таблица является симметричной. для данного сочетания типов данных операндов тип данных результата одинаковый, независимо от порядка операндов.  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Boolean`|Short|SByte|Short|Short|Целое число|Целое число|Long|Long|Long|  
|`SByte`|SByte|SByte|Short|Short|Целое число|Целое число|Long|Long|Long|  
|`Byte`|Short|Short|Byte|Short|UShort|Целое число|UInteger|Long|ULong|  
|`Short`|Short|Short|Short|Short|Целое число|Целое число|Long|Long|Long|  
|`UShort`|Целое число|Целое число|UShort|Целое число|UShort|Целое число|UInteger|Long|ULong|  
|`Integer`|Целое число|Целое число|Целое число|Целое число|Целое число|Целое число|Long|Long|Long|  
|`UInteger`|Long|Long|UInteger|Long|UInteger|Long|UInteger|Long|ULong|  
|`Long`|Long|Long|Long|Long|Long|Long|Long|Long|Long|  
|`ULong`|Long|Long|ULong|Long|ULong|Long|ULong|Long|ULong|  
  
 Если любой из операндов `\` оператора является [десятичным](../data-types/decimal-data-type.md), [одинарным](../data-types/single-data-type.md)или [двойным](../data-types/double-data-type.md), Visual Basic пытается преобразовать его в [Long](../data-types/long-data-type.md) перед операцией, а тип данных result имеет значение `Long` .  
  
## <a name="relational-and-bitwise-comparisons"></a>Реляционные и побитовые сравнения  

 Тип данных результата реляционной операции ( `=` , `<>` , `<` ,, `>` `<=` , `>=` ) всегда имеет `Boolean` [логический тип данных](../data-types/boolean-data-type.md). Это справедливо и для логических операций (,,,, `And` `AndAlso` `Not` `Or` `OrElse` , `Xor` ) на `Boolean` операндах.  
  
 Тип данных результата побитовой логической операции зависит от типов данных операндов. Обратите внимание, что `AndAlso` и `OrElse` задаются только для `Boolean` , а Visual Basic преобразует каждый операнд по мере необходимости в `Boolean` перед выполнением операции.  
  
### <a name="-----and--operators"></a>Операторы =,  <>, \<, > , \<=, and > =  

 Если оба операнда имеют `Boolean` значение, Visual Basic считается `True` меньше `False` . Если числовой тип сравнивается с `String` , Visual Basic пытается преобразовать в `String` `Double` перед операцией. `Char`Операнд или `Date` может сравниваться только с другим операндом того же типа данных. Тип данных Result всегда имеет значение `Boolean` .  
  
### <a name="bitwise-not-operator"></a>Оператор побитового не  

 В следующей таблице показаны типы данных результата для побитового `Not` оператора.  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Not`|Логическое значение|SByte|Byte|Short|UShort|Целое число|UInteger|Long|ULong|  
  
 Если операнд имеет значение `Decimal` , `Single` , `Double` или `String` , Visual Basic пытается преобразовать его `Long` перед операцией, а тип данных Result — `Long` .  
  
### <a name="bitwise-and-or-and-xor-operators"></a>Побитовые операторы and, OR и XOR  

 В следующей таблице показаны типы данных результата для побитовых `And` `Or` операторов, и `Xor` . Обратите внимание, что эта таблица является симметричной. для данного сочетания типов данных операндов тип данных результата одинаковый, независимо от порядка операндов.  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Boolean`|Логическое значение|SByte|Short|Short|Целое число|Целое число|Long|Long|Long|  
|`SByte`|SByte|SByte|Short|Short|Целое число|Целое число|Long|Long|Long|  
|`Byte`|Short|Short|Byte|Short|UShort|Целое число|UInteger|Long|ULong|  
|`Short`|Short|Short|Short|Short|Целое число|Целое число|Long|Long|Long|  
|`UShort`|Целое число|Целое число|UShort|Целое число|UShort|Целое число|UInteger|Long|ULong|  
|`Integer`|Целое число|Целое число|Целое число|Целое число|Целое число|Целое число|Long|Long|Long|  
|`UInteger`|Long|Long|UInteger|Long|UInteger|Long|UInteger|Long|ULong|  
|`Long`|Long|Long|Long|Long|Long|Long|Long|Long|Long|  
|`ULong`|Long|Long|ULong|Long|ULong|Long|ULong|Long|ULong|  
  
 Если операнд имеет значение `Decimal` , `Single` , `Double` или `String` , Visual Basic пытается преобразовать его в `Long` перед операцией, а тип данных результата будет таким же, как если бы этот операнд уже был `Long` .  
  
## <a name="miscellaneous-operators"></a>Прочие операторы  

 `&`Оператор определен только для объединения `String` операндов. Visual Basic преобразует каждый операнд по мере необходимости в `String` перед операцией, а тип данных результата всегда равен `String` . В целях `&` оператора все преобразования в `String` считаются расширяющими, даже если `Option Strict` имеет значение `On` .  
  
 `Is` `IsNot` Для операторов и оба операнда должны иметь ссылочный тип. Для `TypeOf` выражения... `Is` требуется, чтобы первый операнд был ссылочного типа, а второй операнд был именем типа данных. Во всех этих случаях тип данных result имеет значение `Boolean` .  
  
 `Like`Оператор определяется только для шаблонов, соответствующих `String` операндам. Visual Basic пытается преобразовать каждый операнд по мере необходимости в `String` перед операцией. Тип данных Result всегда имеет значение `Boolean` .  
  
## <a name="see-also"></a>См. также

- [Типы данных](../data-types/index.md)
- [Операторы и выражения](../../programming-guide/language-features/operators-and-expressions/index.md)
- [Арифметические операторы в Visual Basic](../../programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [Comparison Operators in Visual Basic](../../programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [Операторы](index.md)
- [Порядок применения операторов в Visual Basic](operator-precedence.md)
- [Список операторов, сгруппированных по функциональному назначению](operators-listed-by-functionality.md)
- [Арифметические операторы](arithmetic-operators.md)
- [Операторы сравнения](comparison-operators.md)
- [Оператор Option Strict](../statements/option-strict-statement.md)
