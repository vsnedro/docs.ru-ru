---
title: Строковые функции
ms.date: 07/20/2015
helpviewer_keywords:
- string functions
ms.assetid: f1bf9ac2-cbcf-4298-ae51-53182076bdc8
ms.openlocfilehash: 778e57eadd75baf1aabd100f9d8d41a490f79a04
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406292"
---
# <a name="string-functions-visual-basic"></a>Строковые функции (Visual Basic)

В следующей таблице перечислены функции, которые Visual Basic предоставляет в <xref:Microsoft.VisualBasic.Strings?displayProperty=nameWithType> классе для поиска и работы со строками. Их можно рассматривать как Visual Basic встроенных функций; то есть вам не нужно вызывать их как явные члены класса, как показано в примерах. Дополнительные методы и в некоторых случаях дополняют методы, доступны в <xref:System.String?displayProperty=nameWithType> классе.

|Метод .NET Framework|Описание|
|---------------------------|-----------------|
|<xref:Microsoft.VisualBasic.Strings.Asc%2A>, <xref:Microsoft.VisualBasic.Strings.AscW%2A>|Возвращает `Integer` значение, представляющее код символа, соответствующий символу.|
|<xref:Microsoft.VisualBasic.Strings.Chr%2A>, <xref:Microsoft.VisualBasic.Strings.ChrW%2A>|Возвращает знак, связанный с указанным кодом знака.|
|<xref:Microsoft.VisualBasic.Strings.Filter%2A>|Возвращает массив (с индексацией от нуля), который содержит подмножество массива типа `String`, выделяемое согласно указанным условиям фильтрации.|
|<xref:Microsoft.VisualBasic.Strings.Format%2A>|Возвращает строку, отформатированную в соответствии с инструкциями, содержащимися в формате выражения `String`.|
|<xref:Microsoft.VisualBasic.Strings.FormatCurrency%2A>|Возвращает выражение в формате денежной единицы с использованием символа денежной единицы, определенного в системной панели управления.|
|<xref:Microsoft.VisualBasic.Strings.FormatDateTime%2A>|Возвращает строковое выражение, представляющее значение даты и времени.|
|<xref:Microsoft.VisualBasic.Strings.FormatNumber%2A>|Возвращает выражение в формате числа.|
|<xref:Microsoft.VisualBasic.Strings.FormatPercent%2A>|Возвращает выражение в виде процента (умноженное на 100) с символом % в конце.|
|<xref:Microsoft.VisualBasic.Strings.InStr%2A>|Возвращает целое число, указывающее начальную позицию первого вхождения одной строки в другую.|
|<xref:Microsoft.VisualBasic.Strings.InStrRev%2A>|Возвращает позицию первого вхождения одной строки в другую, начиная с правого конца строки.|
|<xref:Microsoft.VisualBasic.Strings.Join%2A>|Возвращает строку, образуемую путем соединения нескольких подстрок, содержащихся в массиве.|
|<xref:Microsoft.VisualBasic.Strings.LCase%2A>|Возвращает строку или символ, преобразованные в нижний регистр.|
|<xref:Microsoft.VisualBasic.Strings.Left%2A>|Возвращает строку, содержащую указанное число знаков с левой стороны строки.|
|<xref:Microsoft.VisualBasic.Strings.Len%2A>|Возвращает целое число, содержащее количество символов в строке.|
|<xref:Microsoft.VisualBasic.Strings.LSet%2A>|Возвращает выровненную по левому краю строку запрашиваемой длины, содержащую указанную строку.|
|<xref:Microsoft.VisualBasic.Strings.LTrim%2A>|Возвращает строку, содержащую копию указанной строки без начальных пробелов.|
|<xref:Microsoft.VisualBasic.Strings.Mid%2A>|Возвращает строку, содержащую указанное число символов из строки.|
|<xref:Microsoft.VisualBasic.Strings.Replace%2A>|Возвращает строку, в которой указанная подстрока заданное число раз заменена другой подстрокой.|
|<xref:Microsoft.VisualBasic.Strings.Right%2A>|Возвращает строку, содержащую указанное число знаков с правой стороны строки.|
|<xref:Microsoft.VisualBasic.Strings.RSet%2A>|Возвращает выровненную по правому краю строку, содержащую указанную строку, настроенную под указанную длину.|
|<xref:Microsoft.VisualBasic.Strings.RTrim%2A>|Возвращает строку, содержащую копию указанной строки без конечных пробелов.|
|<xref:Microsoft.VisualBasic.Strings.Space%2A>|Возвращает строку, состоящую из указанного числа пробелов.|
|<xref:Microsoft.VisualBasic.Strings.Split%2A>|Возвращает одномерный массив (с индексацией от нуля), содержащий указанное число подстрок.|
|<xref:Microsoft.VisualBasic.Strings.StrComp%2A>|Возвращает -1, 0 или 1 в зависимости от результата сравнения строк.|
|<xref:Microsoft.VisualBasic.Strings.StrConv%2A>|Возвращает строку, преобразованную как указано.|
|<xref:Microsoft.VisualBasic.Strings.StrDup%2A>|Возвращает строку или объект, состоящие из указанного знака, повторенного определенное количество раз.|
|<xref:Microsoft.VisualBasic.Strings.StrReverse%2A>|Возвращает строку, содержащую те же знаки, что и в заданной строке, но в противоположном порядке.|
|<xref:Microsoft.VisualBasic.Strings.Trim%2A>|Возвращает строку, содержащую копию указанной строки без начальных или конечных пробелов.|
|<xref:Microsoft.VisualBasic.Strings.UCase%2A>|Возвращает строку или знак, содержащий указанную строку, преобразованную в верхний регистр.|

Можно использовать инструкцию [Option Compare](../statements/option-compare-statement.md) , чтобы задать, сравниваются ли строки с использованием порядка сортировки текста без учета регистра, определенного языковым стандартом системы ( `Text` ) или внутренними двоичными представлениями символов ( `Binary` ). Метод сравнения текста по умолчанию — `Binary`.

## <a name="example-ucase"></a>Пример: Укасе

В данном примере функция `UCase` используется для возврата строки в верхнем регистре.
[!code-vb[VbVbalrStrings#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#31)]

## <a name="example-ltrim"></a>Пример: LTrim

В данном примере функция `LTrim` используется, чтобы убрать пробелы в начале, а функция `RTrim` — чтобы убрать пробелы в конце строковой переменной. Функция `Trim` в примере используется для удаления обоих типов пробелов.

[!code-vb[VbVbalrStrings#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#25)]

## <a name="example-mid"></a>Пример: mid

В этом примере `Mid` функция используется для возврата указанного числа символов из строки.

[!code-vb[VbVbalrStrings#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#17)]

## <a name="example-len"></a>Пример: len

В данном примере `Len` используется для возврата числа знаков в строке.

[!code-vb[VbVbalrStrings#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#33)]

## <a name="example-instr"></a>Пример: InStr

В данном примере функция `InStr` используется для возврата позиции первого вхождения одной строки в другую.

[!code-vb[VbVbalrStrings#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#8)]

## <a name="example-format"></a>Пример: Format

В данном примере показаны различные способы использования функции `Format` для форматирования значений с применением как форматов `String`, так и определенных пользователем форматов. Фактическое отображение системой разделителя даты (`/`), разделителя времени (`:` и индикаторов AM/PM (`t` и `tt`) зависит от региональных параметров, применяемых кодом. При отображении времени и даты в среде разработки используется короткий формат времени и даты региональных установок кода.

> [!NOTE]
> Для языков, использующих 24-часовой формат, индикаторы AM/PM (`t` и `tt`) не отображаются.

[!code-vb[VbVbalrStrings#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#27)]

## <a name="see-also"></a>См. также раздел

- [Ключевые слова](../keywords/index.md)
- [Члены библиотеки времени выполнения Visual Basic](../runtime-library-members.md)
- [Сводка по работе со строками](../keywords/string-manipulation-summary.md)
- [Методы класса System. String](xref:System.String#methods)
