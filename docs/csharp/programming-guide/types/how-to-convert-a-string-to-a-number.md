---
title: Руководство по программированию на C#. Преобразование строки в число
description: Сведения о преобразовании строки в число путем вызова методов классов Parse, TryParse или Convert при программировании на C#.
ms.date: 02/16/2021
helpviewer_keywords:
- conversions [C#]
- conversions [C#], string to int
- converting strings to int [C#]
- strings [C#], converting to int
ms.topic: how-to
ms.custom: contperf-fy21q2
ms.assetid: 467b9979-86ee-4afd-b734-30299cda91e3
ms.openlocfilehash: 011c66d5341d9e2e8032a692385f5f250b6ab9a2
ms.sourcegitcommit: 456b3cd82a87b453fa737b4661295070d1b6d684
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/17/2021
ms.locfileid: "100639374"
---
# <a name="how-to-convert-a-string-to-a-number-c-programming-guide"></a>Руководство по программированию на C#. Преобразование строки в число

Для преобразования `string` в число используется вызов метода `Parse` или `TryParse`, который можно найти в числовых типах (`int`, `long`, `double` и т. д.), или используются методы в классе <xref:System.Convert?displayProperty=nameWithType>.
  
Немного эффективнее и проще вызвать метод `TryParse` (например, [`int.TryParse("11", out number)`](xref:System.Int32.TryParse%2A)) или метод `Parse` (например, [`var number = int.Parse("11")`](xref:System.Int32.Parse%2A)). Использование метода <xref:System.Convert> более удобно для общих объектов, реализующих <xref:System.IConvertible>.
  
Можно использовать методы `Parse` или `TryParse` в числовом типе, который предположительно содержит строка, таком как тип <xref:System.Int32?displayProperty=nameWithType>.  Метод <xref:System.Convert.ToInt32%2A?displayProperty=nameWithType> использует <xref:System.Int32.Parse%2A> внутри себя.  Метод `Parse` возвращает преобразованное число; метод `TryParse` возвращает логическое значение, которое указывает, успешно ли выполнено преобразование, и возвращает преобразованное число в параметр `out`. Если строка имеет недопустимый формат, `Parse` создает исключение, а `TryParse` возвращает значение `false`. В случае сбоя операции синтаксического анализа при вызове метода `Parse` вы всегда должны использовать обработку исключений, чтобы перехватить <xref:System.FormatException>.
  
## <a name="call-parse-or-tryparse-methods"></a>Вызов метода Parse или TryParse

Методы `Parse` и `TryParse` игнорируют пробелы в начале и в конце строки, но все остальные символы должны быть символами, которые образуют соответствующий числовой тип (`int`, `long`, `ulong`, `float`, `decimal` и т. д.).  Любые пробелы в строке, образующие число, приводят к ошибке.  Например, можно использовать `decimal.TryParse` для анализа "10", "10.3" или "  10  ", но этот метод нельзя использовать для анализа 10 из "10X", "1 0" (обратите внимание на внедренный пробел), "10 .3" (обратите внимание на внедренный пробел), "10e1" (здесь работает `float.TryParse`) и т. д. Строку со значением `null` или <xref:System.String.Empty?displayProperty=nameWithType> невозможно успешно проанализировать. Вы можете проверить наличие NULL или пустой строки, прежде чем пытаться ее проанализировать, вызвав метод <xref:System.String.IsNullOrEmpty%2A?displayProperty=nameWithType>.

В указанном ниже примере демонстрируются успешные и неуспешные вызовы методов `Parse` и `TryParse`.

[!code-csharp[Parse and TryParse](~/samples/snippets/csharp/programming-guide/string-to-number/parse-tryparse/program.cs)]

В следующем примере показан один из подходов к анализу строки, которая, как ожидается, будет включать начальные числовые символы (включая шестнадцатеричные символы) и конечные нечисловые символы. Он назначает допустимые символы в начале новой строки перед вызовом метода <xref:System.Int32.TryParse%2A>. Поскольку анализируемые строки содержат небольшое количество символов, в примере вызывается метод <xref:System.String.Concat%2A?displayProperty=nameWithType> для назначения допустимых символов новой строке. Для большей строки можете использовать класс <xref:System.Text.StringBuilder>.

[!code-csharp[Removing invalid characters](~/samples/snippets/csharp/programming-guide/string-to-number/parse-tryparse2/program.cs)]

## <a name="call-convert-methods"></a>Вызов методов класса Convert

В следующей таблице перечислены некоторые методы класса <xref:System.Convert>, которые можно использовать для преобразования строки в число.

| Числовой тип | Метод                                             |
|--------------|----------------------------------------------------|
| `decimal`    | <xref:System.Convert.ToDecimal%28System.String%29> |
| `float`      | <xref:System.Convert.ToSingle%28System.String%29>  |
| `double`     | <xref:System.Convert.ToDouble%28System.String%29>  |
| `short`      | <xref:System.Convert.ToInt16%28System.String%29>   |
| `int`        | <xref:System.Convert.ToInt32%28System.String%29>   |
| `long`       | <xref:System.Convert.ToInt64%28System.String%29>   |
| `ushort`     | <xref:System.Convert.ToUInt16%28System.String%29>  |
| `uint`       | <xref:System.Convert.ToUInt32%28System.String%29>  |
| `ulong`      | <xref:System.Convert.ToUInt64%28System.String%29>  |

В данном примере вызывается метод <xref:System.Convert.ToInt32%28System.String%29?displayProperty=nameWithType> для преобразования входных данных string в значение типа [int](../../language-reference/builtin-types/integral-numeric-types.md). Пример перехватывает два наиболее распространенных исключения, которые могут создаваться этим методом, — <xref:System.FormatException> и <xref:System.OverflowException>. Если итоговое число можно увеличить, не превышая <xref:System.Int32.MaxValue?displayProperty=nameWithType>, пример добавляет 1 к результату и отображает вывод.

[!code-csharp[Parsing with Convert methods](~/samples/snippets/csharp/programming-guide/string-to-number/convert/program.cs)]
