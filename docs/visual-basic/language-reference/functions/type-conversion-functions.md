---
description: 'Дополнительные сведения: функции преобразования типов (Visual Basic)'
title: Type Conversion Functions
ms.date: 10/24/2018
f1_keywords:
- vb.CUShort
- vb.csng
- vb.CDate
- CByte
- CSng
- vb.CDec
- CBool
- CStr
- vb.CULng
- CDec
- CVErr
- CDbl
- CShort
- vb.CObj
- vb.CVErr
- CULng
- vb.cdbl
- vb.cbool
- CObj
- CDate
- CLng
- vb.cstr
- vb.cbyte
- vb.clng
- vb.CChar
- CUShort
- vb.CUInt
- vb.cint
- vb.CShort
- CInt
- CUInt
- CChar
helpviewer_keywords:
- CDate function
- CByte function
- Integer data type [Visual Basic], converting
- string conversion [Visual Basic], conversion functions
- fractions
- data types [Visual Basic], converting
- text, converting
- CDec function
- Char data type [Visual Basic], converting
- type conversion [Visual Basic], functions for
- Single data type [Visual Basic], converting
- numbers [Visual Basic], rounding
- rounding numbers [Visual Basic], type conversion
- CUShort function
- Long data type [Visual Basic], converting
- return values [Visual Basic], data types
- single-precision numbers [Visual Basic], converting
- data type conversion [Visual Basic], functions for
- CStr function
- times [Visual Basic], converting
- CSng function
- conversions [Visual Basic], type conversion functions
- CBool function
- CDbl function
- CUInt function
- Currency data type [Visual Basic], conversion functions
- numbers [Visual Basic], converting
- Double data type [Visual Basic], converting
- CLng function
- CSByte function
- double-precision numbers
- Decimal data type [Visual Basic], converting
- Boolean data type [Visual Basic], converting
- integers [Visual Basic], type conversion functions
- dates [Visual Basic], converting
- CULng function
- CInt function
- Date data type [Visual Basic], converting
- Byte data type [Visual Basic], converting
- String data type [Visual Basic], converting
- CChar function
- banker's rounding
- Short data type [Visual Basic], converting
- rounding numbers [Visual Basic], banker's rounding
- type conversion [Visual Basic], Visual Basic vs. .NET Framework
ms.assetid: d9d8d165-f967-44ff-a6cd-598e4740a99e
ms.openlocfilehash: c2e701b522bbeb32f4f6f448acd78e09b0616f46
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99731088"
---
# <a name="type-conversion-functions-visual-basic"></a>Функции преобразования типов (Visual Basic)

Эти функции компилируются встроенным, то есть код преобразования является частью кода, который вычисляет выражение. Иногда нет вызова процедуры для выполнения преобразования, что повышает производительность. Каждая функция приводит выражение к определенному типу данных.

## <a name="syntax"></a>Синтаксис

```vb
CBool(expression)
CByte(expression)
CChar(expression)
CDate(expression)
CDbl(expression)
CDec(expression)
CInt(expression)
CLng(expression)
CObj(expression)
CSByte(expression)
CShort(expression)
CSng(expression)
CStr(expression)
CUInt(expression)
CULng(expression)
CUShort(expression)
```

## <a name="part"></a>Отделение

`expression`  
Обязательный элемент. Любое выражение исходного типа данных.

## <a name="return-value-data-type"></a>Тип данных возвращаемого значения

Имя функции определяет тип данных возвращаемого значения, как показано в следующей таблице.

|Имя функции|Тип возвращаемых данных|Диапазон для `expression` аргумента|
|-------------------|----------------------|-------------------------------------|
|`CBool`|[Логический тип данных](../data-types/boolean-data-type.md)|Любое допустимое `Char` или `String` числовое выражение.|
|`CByte`|[Тип данных Byte](../data-types/byte-data-type.md)|<xref:System.Byte.MinValue?displayProperty=nameWithType> (от 0) до <xref:System.Byte.MaxValue?displayProperty=nameWithType> (255) (без знака); дробные части округляются.<sup> 1</sup><br/><br/>Начиная с Visual Basic 15,8 Visual Basic оптимизирует производительность преобразования с плавающей запятой в байтовую `CByte` функцию. Дополнительные сведения см. в разделе ["Примечания"](#remarks) . Пример см. в разделе пример для функции [CInt](#cint-example) .|
|`CChar`|[Тип данных Char](../data-types/char-data-type.md)|Любое допустимое `Char` `String` выражение или; преобразуется только первый символ `String` ; значение может быть от 0 до 65535 (без знака).|
|`CDate`|[Тип данных Date](../data-types/date-data-type.md)|Любое допустимое представление даты и времени.|
|`CDbl`|[Тип данных Double](../data-types/double-data-type.md)|-1.79769313486231570 e + 308 до-4.94065645841246544 E-324 для отрицательных значений; 4.94065645841246544 e-324 до 1.79769313486231570 E + 308 для положительных значений.|
|`CDec`|[Тип данных Decimal](../data-types/decimal-data-type.md)|+/-79,228,162,514,264,337,593,543,950,335 для чисел с нулевым масштабом, то есть чисел без десятичных разрядов. Для чисел с 28 десятичными разрядами диапазоном является +/-7.9228162514264337593543950335. Наименьшее возможное ненулевое число — 0,0000000000000000000000000001 (+/-1E-28).|
|`CInt`|[Тип данных Integer](../data-types/integer-data-type.md)|<xref:System.Int32.MinValue?displayProperty=nameWithType> (от-2 147 483 648) до <xref:System.Int32.MaxValue?displayProperty=nameWithType> (2 147 483 647); дробные части округляются.<sup> 1</sup> <br/><br/>Начиная с Visual Basic 15,8 Visual Basic оптимизирует производительность преобразования с плавающей запятой в целое с помощью `CInt` функции. Дополнительные сведения см. в разделе ["Примечания](#remarks) ". Пример см. в разделе пример для функции [CInt](#cint-example) . |
|`CLng`|[Тип данных Long](../data-types/long-data-type.md)|<xref:System.Int64.MinValue?displayProperty=nameWithType> (от-9223372036854775808) до <xref:System.Int64.MaxValue?displayProperty=nameWithType> (9 223 372 036 854 775 807); дробные части округляются.<sup> 1</sup><br/><br/>Начиная с Visual Basic 15,8 Visual Basic оптимизирует производительность преобразования с плавающей запятой в 64-разрядное целое число с помощью `CLng` функции; Дополнительные сведения см. в разделе ["Примечания"](#remarks) . Пример см. в разделе пример для функции [CInt](#cint-example) .|
|`CObj`|[Object Data Type](../data-types/object-data-type.md)|Любое допустимое выражение.|
|`CSByte`|[Тип данных SByte](../data-types/sbyte-data-type.md)|<xref:System.SByte.MinValue?displayProperty=nameWithType> (от-128) до <xref:System.SByte.MaxValue?displayProperty=nameWithType> (127); дробные части округляются.<sup> 1</sup><br/><br/>Начиная с Visual Basic 15,8, Visual Basic оптимизирует производительность преобразования байтов с плавающей запятой в функцию с помощью `CSByte` функции. Дополнительные сведения см. в разделе ["Примечания"](#remarks) . Пример см. в разделе пример для функции [CInt](#cint-example) .|
|`CShort`|[Тип данных Short](../data-types/short-data-type.md)|<xref:System.Int16.MinValue?displayProperty=nameWithType> (от-32 768) до <xref:System.Int16.MaxValue?displayProperty=nameWithType> (32 767); дробные части округляются.<sup> 1</sup><br/><br/>Начиная с Visual Basic 15,8 Visual Basic оптимизирует производительность преобразования с плавающей запятой в 16-разрядное целое с помощью `CShort` функции. Дополнительные сведения см. в разделе ["Примечания"](#remarks) . Пример см. в разделе пример для функции [CInt](#cint-example) .|
|`CSng`|[Тип данных Single](../data-types/single-data-type.md)|-3.402823 e + 38 – 1.401298 E-45 для отрицательных значений; 1.401298 e-45 до 3.402823 E + 38 для положительных значений.|
|`CStr`|[Тип данных String](../data-types/string-data-type.md)|Для `CStr` зависит от `expression` аргумента. См. раздел [возвращаемые значения для функции CStr](return-values-for-the-cstr-function.md).|
|`CUInt`|[Тип данных UInteger](../data-types/uinteger-data-type.md)|<xref:System.UInt32.MinValue?displayProperty=nameWithType> (от 0) до <xref:System.UInt32.MaxValue?displayProperty=nameWithType> (4 294 967 295) (без знака); дробные части округляются.<sup> 1</sup><br/><br/>Начиная с Visual Basic 15,8 Visual Basic оптимизирует производительность преобразования с плавающей запятой в целое число без знака с помощью `CUInt` функции. Дополнительные сведения см. в разделе ["Примечания"](#remarks) . Пример см. в разделе пример для функции [CInt](#cint-example) .|
|`CULng`|[Тип данных ULong](../data-types/ulong-data-type.md)|<xref:System.UInt64.MinValue?displayProperty=nameWithType> (от 0) до <xref:System.UInt64.MaxValue?displayProperty=nameWithType> (18446744073709551615) (без знака); дробные части округляются.<sup> 1</sup><br/><br/>Начиная с Visual Basic 15,8, Visual Basic оптимизирует производительность преобразования с плавающей запятой в функцию длинного целого числа без знака с помощью `CULng` функции. Дополнительные сведения см. в разделе ["Примечания"](#remarks) . Пример см. в разделе пример для функции [CInt](#cint-example) .|
|`CUShort`|[Тип данных UShort](../data-types/ushort-data-type.md)|<xref:System.UInt16.MinValue?displayProperty=nameWithType> (от 0) до <xref:System.UInt16.MaxValue?displayProperty=nameWithType> (65 535) (без знака); дробные части округляются.<sup> 1</sup><br/><br/>Начиная с Visual Basic 15,8, Visual Basic оптимизирует производительность преобразования 16-разрядного целого числа без знака с плавающей запятой в `CUShort` функцию. Дополнительные сведения см. в разделе ["Примечания"](#remarks) . Пример см. в разделе пример для функции [CInt](#cint-example) .|

<sup>1</sup> дробная часть может подвергаться специальному типу округления, называемому *банковским округлением*. Дополнительные сведения см. в разделе "Примечания".

## <a name="remarks"></a>Remarks

Как правило, следует использовать функции преобразования типа Visual Basic в качестве предпочтений для методов платформа .NET Framework, таких как `ToString()` , в <xref:System.Convert> классе или в отдельной структуре типа или классе. Функции Visual Basic предназначены для оптимального взаимодействия с Visual Basicным кодом, а также для сокращения исходного кода и упрощения его чтения. Кроме того, методы преобразования платформа .NET Framework не всегда дают те же результаты, что и функции Visual Basic, например при преобразовании `Boolean` в `Integer` . Дополнительные сведения см. в разделе [Устранение неполадок типов данных](../../programming-guide/language-features/data-types/troubleshooting-data-types.md).

Начиная с Visual Basic 15,8, производительность преобразования с плавающей запятой в целое число оптимизируется при передаче <xref:System.Single> значения или, <xref:System.Double> возвращаемого следующими методами, в одну из целочисленных функций преобразования (,,,,,, `CByte` `CShort` `CInt` `CLng` `CSByte` `CUShort` `CUInt` , `CULng` ):

- <xref:Microsoft.VisualBasic.Conversion.Fix(System.Double)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Fix(System.Object)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Fix(System.Single)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Int(System.Double)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Int(System.Object)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Int(System.Single)?displayProperty=nameWithType>
- <xref:System.Math.Ceiling(System.Double)?displayProperty=nameWithType>
- <xref:System.Math.Floor(System.Double)?displayProperty=nameWithType>
- <xref:System.Math.Round(System.Double)?displayProperty=nameWithType>
- <xref:System.Math.Truncate(System.Double)?displayProperty=nameWithType>

Такая оптимизация позволяет выполнять код, выполняющий большое количество целочисленных преобразований, в два раза быстрее. В следующем примере демонстрируются эти оптимизированные преобразования с плавающей запятой в целые числа:

```vb
Dim s As Single = 173.7619
Dim d As Double = s

Dim i1 As Integer = CInt(Fix(s))               ' Result: 173
Dim b1 As Byte = CByte(Int(d))                 ' Result: 173
Dim s1 AS Short = CShort(Math.Truncate(s))     ' Result: 173
Dim i2 As Integer = CInt(Math.Ceiling(d))      ' Result: 174
Dim i3 As Integer = CInt(Math.Round(s))        ' Result: 174
```

## <a name="behavior"></a>Поведение

- **Приведение.** В общем случае можно использовать функции преобразования типов данных для приведения результата операции к конкретному типу данных, а не по типу данных по умолчанию. Например, используйте `CDec` для принудительного выполнения десятичных арифметических операций в случаях, когда обычно выполняется операция с одиночной точностью, двойной точностью или целочисленной.

- **Неудачные преобразования.** Если `expression` переданный функции объект находится вне диапазона типа данных, в который она должна быть преобразована, <xref:System.OverflowException> возникает исключение.

- **Дробные части.** При преобразовании нецелочисленного значения в целочисленные функции целочисленного преобразования ( `CByte` , `CInt` ,,, `CLng` , `CSByte` `CShort` `CUInt` , `CULng` и `CUShort` ) удаляют дробную часть и округляют значение до ближайшего целого.

     Если дробная часть равна точности 0,5, функции целочисленного преобразования округляют его до ближайшего четного целого числа. Например, 0,5 округляется до 0, а 1,5 и 2,5 оба округляются в 2. Иногда это называется *округлением банка* и предназначено для компенсации смещения, которое может накапливаться при одновременном добавлении многих таких чисел.

     `CInt` и `CLng` отличаются от <xref:Microsoft.VisualBasic.Conversion.Int%2A> функций и <xref:Microsoft.VisualBasic.Conversion.Fix%2A> , которые усекаются, а не округляют дробную часть числа. Кроме того, `Fix` и `Int` всегда возвращают значение того же типа данных, что и при передаче.

- **Преобразования даты и времени.** Используйте <xref:Microsoft.VisualBasic.Information.IsDate%2A> функцию, чтобы определить, можно ли преобразовать значение в дату и время. `CDate` распознает литералы даты и литералы времени, но не числовые значения. Чтобы преобразовать значение Visual Basic 6,0 в `Date` `Date` значение в Visual Basic 2005 или более поздней версии, можно использовать <xref:System.DateTime.FromOADate%2A?displayProperty=nameWithType> метод.

- **Нейтральные значения даты и времени.** [Тип данных Date](../data-types/date-data-type.md) всегда содержит сведения о дате и времени. В целях преобразования типов Visual Basic учитывает 1/1/0001 (1 января 1 года) как *нейтральное значение* для даты, а 00:00:00 (полночь) — как нейтральное значение времени. При преобразовании `Date` значения в строку не `CStr` включает нейтральные значения в результирующую строку. Например, если преобразовать `#January 1, 0001 9:30:00#` в строку, то результатом будет "9:30:00 AM"; сведения о дате подавляются. Однако сведения о дате по-прежнему содержатся в исходном `Date` значении и могут быть восстановлены с помощью таких функций, как <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A> Function.

- **Чувствительность языка и региональных параметров.** Функции преобразования типов, включающие строки, выполняют преобразования в соответствии с текущими параметрами языка и региональных параметров для приложения. Например, `CDate` распознает форматы даты в соответствии с настройками языкового стандарта системы. Необходимо указать день, месяц и год в правильном порядке для вашего языкового стандарта, иначе Дата может интерпретироваться неправильно. Длинный формат даты не распознается, если он содержит строку дня недели, например "среда".

     Если необходимо преобразовать в строковое представление значения или из него в формате, отличном от указанного в Вашем языковом стандарте, то нельзя использовать функции преобразования типа Visual Basic. Для этого используйте `ToString(IFormatProvider)` `Parse(String, IFormatProvider)` методы и типа этого значения. Например, используйте <xref:System.Double.Parse%2A?displayProperty=nameWithType> при преобразовании строки в `Double` и используйте <xref:System.Double.ToString%2A?displayProperty=nameWithType> при преобразовании значения типа `Double` в строку.

## <a name="ctype-function"></a>CType Function

[Функция CType](ctype-function.md) принимает второй аргумент, `typename` и `expression` `typename` `typename` применяет к, где может быть любым типом данных, структурой, классом или интерфейсом, к которому существует допустимое преобразование.

Сравнение `CType` с другими ключевыми словами преобразования типов см. в разделе Оператор [DirectCast](../operators/directcast-operator.md) и [Оператор TryCast](../operators/trycast-operator.md).

## <a name="cbool-example"></a>Пример CBool

В следующем примере функция используется `CBool` для преобразования выражений в `Boolean` значения. Если результат выражения равен ненулевому значению, `CBool` `True` функция возвращает; в противном случае возвращается значение `False` .

[!code-vb[VbVbalrFunctions#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#1)]

## <a name="cbyte-example"></a>Пример CByte

В следующем примере функция используется `CByte` для преобразования выражения в `Byte` .

[!code-vb[VbVbalrFunctions#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#2)]

## <a name="cchar-example"></a>Пример CChar

В следующем примере функция используется `CChar` для преобразования первого символа `String` выражения в `Char` тип.

[!code-vb[VbVbalrFunctions#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#3)]

Входной аргумент `CChar` должен иметь тип данных `Char` или `String` . Нельзя использовать `CChar` для преобразования числа в символ, поскольку `CChar` не может принимать числовые типы данных. В следующем примере получается число, представляющее кодовую точку (код символа), и преобразуется в соответствующий символ. Она использует <xref:Microsoft.VisualBasic.Interaction.InputBox%2A> функцию для получения строки разрядов, `CInt` преобразования строки в тип `Integer` и `ChrW` для преобразования числа в тип `Char` .

[!code-vb[VbVbalrFunctions#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#4)]

## <a name="cdate-example"></a>Пример для CDate

В следующем примере функция используется `CDate` для преобразования строк в `Date` значения. Обычно не рекомендуется жестко кодировать даты и время в виде строк (как показано в этом примере). Вместо этого используйте литералы даты и временные литералы, например #Feb 12, 1969 # и #4:45:23 PM #.

[!code-vb[VbVbalrFunctions#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#5)]

## <a name="cdbl-example"></a>Пример с CDbl

[!code-vb[VbVbalrFunctions#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#6)]

## <a name="cdec-example"></a>Пример CDec

В следующем примере функция используется `CDec` для преобразования числового значения в `Decimal` .

[!code-vb[VbVbalrFunctions#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#7)]

## <a name="cint-example"></a>Пример функции CInt

В следующем примере функция используется `CInt` для преобразования значения в `Integer` .

[!code-vb[VbVbalrFunctions#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#8)]

## <a name="clng-example"></a>Пример с CLng

В следующем примере функция используется `CLng` для преобразования значений в `Long` .

[!code-vb[VbVbalrFunctions#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#9)]

## <a name="cobj-example"></a>Пример CObj

В следующем примере функция используется `CObj` для преобразования числового значения в `Object` . `Object`Сама переменная содержит только 4-байтовый указатель, указывающий на `Double` присвоенное ему значение.

[!code-vb[VbVbalrFunctions#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#10)]

## <a name="csbyte-example"></a>Пример Ксбите

В следующем примере функция используется `CSByte` для преобразования числового значения в `SByte` .

[!code-vb[VbVbalrFunctions#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#11)]

## <a name="cshort-example"></a>Пример CShort

В следующем примере функция используется `CShort` для преобразования числового значения в `Short` .

[!code-vb[VbVbalrFunctions#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#12)]

## <a name="csng-example"></a>Пример CSng

В следующем примере функция используется `CSng` для преобразования значений в `Single` .

[!code-vb[VbVbalrFunctions#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#13)]

## <a name="cstr-example"></a>Пример функции CStr

В следующем примере функция используется `CStr` для преобразования числового значения в `String` .

[!code-vb[VbVbalrFunctions#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#14)]

В следующем примере функция используется `CStr` для преобразования `Date` значений в `String` значения.

[!code-vb[VbVbalrFunctions#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#15)]

`CStr` всегда отображает `Date` значение в стандартном коротком формате для текущего языкового стандарта, например "6/15/2003 4:35:47 PM". Однако `CStr` подавляет *нейтральные значения* 1/1/0001 для даты и 00:00:00 для времени.

Дополнительные сведения о значениях, возвращаемых `CStr` , см. в разделе [возвращаемые значения функции CStr](return-values-for-the-cstr-function.md).

## <a name="cuint-example"></a>Пример Куинт

В следующем примере функция используется `CUInt` для преобразования числового значения в `UInteger` .

[!code-vb[VbVbalrFunctions#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#16)]

## <a name="culng-example"></a>Пример Кулнг

В следующем примере функция используется `CULng` для преобразования числового значения в `ULong` .

[!code-vb[VbVbalrFunctions#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#17)]

## <a name="cushort-example"></a>Пример Кушорт

В следующем примере функция используется `CUShort` для преобразования числового значения в `UShort` .

[!code-vb[VbVbalrFunctions#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#18)]

## <a name="see-also"></a>См. также

- <xref:Microsoft.VisualBasic.Strings.Asc%2A>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- <xref:Microsoft.VisualBasic.Strings.Chr%2A>
- <xref:Microsoft.VisualBasic.Strings.ChrW%2A>
- <xref:Microsoft.VisualBasic.Conversion.Int%2A>
- <xref:Microsoft.VisualBasic.Conversion.Fix%2A>
- <xref:Microsoft.VisualBasic.Strings.Format%2A>
- <xref:Microsoft.VisualBasic.Conversion.Hex%2A>
- <xref:Microsoft.VisualBasic.Conversion.Oct%2A>
- <xref:Microsoft.VisualBasic.Conversion.Str%2A>
- <xref:Microsoft.VisualBasic.Conversion.Val%2A>
- [Функции преобразования](conversion-functions.md)
- [Преобразование типов в Visual Basic](../../programming-guide/language-features/data-types/type-conversions.md)
