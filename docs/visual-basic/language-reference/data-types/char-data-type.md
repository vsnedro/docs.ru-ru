---
description: 'Дополнительные сведения: тип данных char (Visual Basic)'
title: Тип данных Char
ms.date: 07/20/2015
f1_keywords:
- vb.Char
helpviewer_keywords:
- literal type characters [Visual Basic], C
- Char data type
- C literal type character [Visual Basic]
- data types [Visual Basic], assigning
- Char data type [Visual Basic], character literals
ms.assetid: cd7547a9-7855-4e8e-b216-35d74a362657
ms.openlocfilehash: 371244ee4eae6d7dde20487dd7f38c09f3929cd8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99792249"
---
# <a name="char-data-type-visual-basic"></a>Тип данных Char (Visual Basic)

Содержит 16-разрядные (2-байтовые) кодовые точки без знака в диапазоне от 0 до 65535. Каждая кодовая *точка*, или код символа, представляет один символ Юникода.

## <a name="remarks"></a>Remarks

Используйте `Char` тип данных, если необходимо хранить только один символ и не требуется дополнительная нагрузка `String` . В некоторых случаях `Char()` `Char` для хранения нескольких символов можно использовать массив элементов.

Значение по умолчанию `Char` — символ с кодовой точкой 0.

## <a name="unicode-characters"></a>Символы Юникода

Первая 128 кодовых позиций (0 – 127) Юникода соответствует буквам и символам стандартной клавиатуры США. Первые 128 кодовые точки те же, что и кодировка ASCII. Вторая 128 кодовых позиций (128 – 255) представляет специальные символы, такие как буквы латинского алфавита, диакритические знаки, символы валют и дроби. В Юникоде используются оставшиеся кодовые точки (256-65535) для широкого спектра символов, включая международные текстовые символы, диакритические знаки, математические и технические символы.

<xref:System.Char.IsDigit%2A> <xref:System.Char.IsPunctuation%2A> Для определения своей классификации в Юникоде можно использовать методы, такие как и, `Char` для переменной.

## <a name="type-conversions"></a>Преобразования типов

Visual Basic не выполняет прямое преобразование между `Char` и числовыми типами. Можно использовать <xref:Microsoft.VisualBasic.Strings.Asc%2A> <xref:Microsoft.VisualBasic.Strings.AscW%2A> функцию или для преобразования `Char` значения в `Integer` , представляющего ее кодовую точку. <xref:Microsoft.VisualBasic.Strings.Chr%2A> <xref:Microsoft.VisualBasic.Strings.ChrW%2A> Для преобразования `Integer` значения в `Char` , которое имеет эту кодовую точку, можно использовать функцию или.

Если параметр проверки типов ( [оператор Option строго](../statements/option-strict-statement.md)) включен, необходимо добавить символ типа литерала в односимвольный строковый литерал, чтобы его можно было обозначить как `Char` тип данных. Это показано в следующем примере. Первое присваивание `charVar` переменной приводит к ошибке компилятора [BC30512](../../misc/bc30512.md) , так как `Option Strict` имеет значение ON. Вторая компилируется успешно, так как `c` символ типа литерала определяет литерал как `Char` значение.

```vb
Option Strict On

Module CharType
    Public Sub Main()
        Dim charVar As Char

        ' This statement generates compiler error BC30512 because Option Strict is On.  
        charVar = "Z"  

        ' The following statement succeeds because it specifies a Char literal.  
        charVar = "Z"c
    End Sub
End Module
```

## <a name="programming-tips"></a>Советы по программированию

- **Отрицательные числа.** `Char` является неподписанным типом и не может представлять отрицательное значение. В любом случае не следует использовать `Char` для хранения числовых значений.

- **Вопросы взаимодействия.** Если вы используете компоненты, не написанные для платформа .NET Framework, например автоматизацию или COM-объекты, помните, что в других средах символьные типы имеют разную ширину данных (8 бит). При передаче 8-разрядного аргумента в такой компонент объявите его как `Byte` вместо `Char` в новом коде Visual Basic.

- **Расширяющие.** `Char`Тип данных расширяется до `String` . Это означает, что можно выполнить преобразование `Char` в `String` и не будет возникать <xref:System.OverflowException?displayProperty=nameWithType> .

- **Символы типа.** Добавление символа типа литерала `C` к строковому литералу с одним символом приводит к тому, что он применяет его к `Char` типу данных. `Char` не имеет символа типа идентификатора.

- **Тип Framework.** В .NET Framework данный тип соответствует структуре <xref:System.Char?displayProperty=nameWithType>.

## <a name="see-also"></a>См. также

- <xref:System.Char?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Strings.Asc%2A>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- <xref:Microsoft.VisualBasic.Strings.Chr%2A>
- <xref:Microsoft.VisualBasic.Strings.ChrW%2A>
- [Типы данных](index.md)
- [Тип данных String](string-data-type.md)
- [Type Conversion Functions](../functions/type-conversion-functions.md)
- [Сводка по преобразованию](../keywords/conversion-summary.md)
- [Практическое руководство. Вызов функции Windows, принимающей значение беззнакового типа](../../programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [Эффективное использование типов данных](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
