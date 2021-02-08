---
description: 'Дополнительные сведения: тип данных String (Visual Basic)'
title: Тип данных String
ms.date: 07/20/2015
f1_keywords:
- vb.String
helpviewer_keywords:
- strings [Visual Basic], character
- strings [Visual Basic], fixed-length
- string keyword [Visual Basic]
- fixed-length strings [Visual Basic], string data type
- literals [Visual Basic], string
- text [Visual Basic], String data type
- $ identifier type character
- String data type
- fixed-length strings
- string literals [Visual Basic]
- data types [Visual Basic], assigning
- String literals [Visual Basic]
- identifier type characters [Visual Basic], $
ms.assetid: 15ac03f5-cabd-42cc-a754-1df3893c25d9
ms.openlocfilehash: 6597a5c4b8ee0eb961d3e33bee52ae493068da35
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99792119"
---
# <a name="string-data-type-visual-basic"></a>Тип данных String (Visual Basic)

Содержит последовательности 16-разрядных (2-байтовых) кодовых точек без знака, которые находятся в диапазоне от 0 до 65535. Каждая кодовая *точка*, или код символа, представляет один символ Юникода. Строка может содержать от 0 до приблизительно 2 000 000 000 (2 ^ 31) символов Юникода.  
  
## <a name="remarks"></a>Remarks  

 Используйте `String` тип данных для хранения нескольких символов без дополнительных затрат на Управление массивом `Char()` , массив `Char` элементов.  
  
 Значение по умолчанию `String` — `Nothing` (пустая ссылка). Обратите внимание, что это не то же самое, что пустая строка (значение `""` ).  
  
## <a name="unicode-characters"></a>Символы Юникода  

 Первая 128 кодовых позиций (0 – 127) Юникода соответствует буквам и символам стандартной клавиатуры США. Первые 128 кодовые точки те же, что и кодировка ASCII. Вторая 128 кодовых позиций (128 – 255) представляет специальные символы, такие как буквы латинского алфавита, диакритические знаки, символы валют и дроби. В Юникоде используются оставшиеся кодовые точки (256-65535) для широкого спектра символов. Это включает в себя международные текстовые символы, диакритические знаки, математические и технические символы.  
  
 <xref:System.Char.IsDigit%2A>Для определения своей классификации Юникода можно использовать методы, например и, для <xref:System.Char.IsPunctuation%2A> отдельного символа в `String` переменной.  
  
## <a name="format-requirements"></a>Требования к формату  

 Литерал необходимо заключать `String` в кавычки ( `" "` ). Если необходимо включить кавычки в качестве одного из символов в строке, используются две смежные кавычки ( `""` ). Это показано в следующем примере.  
  
```vb  
Dim j As String = "Joe said ""Hello"" to me."  
Dim h As String = "Hello"  
' The following messages all display the same thing:  
' "Joe said "Hello" to me."  
MsgBox(j)  
MsgBox("Joe said " & """" & h & """" & " to me.")  
MsgBox("Joe said """ & h & """ to me.")  
```  
  
 Обратите внимание, что смежные кавычки, представляющие кавычки в строке, не зависят от кавычек, начинающихся и заканчивая `String` литералом.  
  
## <a name="string-manipulations"></a>Манипуляции со строками  

 После присвоения строки `String` переменной эта строка является *неизменяемой*, что означает, что изменить ее длину или содержимое нельзя. При изменении строки каким-либо образом Visual Basic создает новую строку и задействует предыдущую. `String`Затем переменная указывает на новую строку.  
  
 Вы можете манипулировать содержимым переменной с `String` помощью различных строковых функций. В следующем примере показана <xref:Microsoft.VisualBasic.Strings.Left%2A> функция  
  
```vb  
Dim S As String = "Database"  
' The following statement sets S to a new string containing "Data".  
S = Microsoft.VisualBasic.Left(S, 4)  
```  
  
 Строка, созданная другим компонентом, может быть дополнена начальными или конечными пробелами. Если вы получаете такую строку, <xref:Microsoft.VisualBasic.Strings.Trim%2A> <xref:Microsoft.VisualBasic.Strings.LTrim%2A> <xref:Microsoft.VisualBasic.Strings.RTrim%2A> для удаления этих пробелов можно использовать функции, и.  
  
 Дополнительные сведения об операциях со строками см. в разделе [строки](../../programming-guide/language-features/strings/index.md).  
  
## <a name="programming-tips"></a>Советы по программированию  
  
- **Отрицательные числа.** Помните, что символы, удерживаемые, `String` не подписаны и не могут представлять отрицательные значения. В любом случае не следует использовать `String` для хранения числовых значений.  
  
- **Вопросы взаимодействия.** Если вы взаимодействуете с компонентами, которые не написаны для платформа .NET Framework, например автоматизации или COM-объекты, помните, что в других средах символы строки имеют разную ширину данных (8 бит). При передаче строкового аргумента из 8-разрядных символов в такой компонент объявите его как `Byte()` , массив `Byte` элементов, а не `String` в новом коде Visual Basic.  
  
- **Символы типа.** Добавление символа типа идентификатора `$` к любому идентификатору приводит к тому, что он применяет его к `String` типу данных. `String` не имеет символа типа литерала. Однако компилятор обрабатывает литералы, заключенные в кавычки ( `" "` ), как `String` .  
  
- **Тип Framework.** Соответствующий тип в платформа .NET Framework — это <xref:System.String?displayProperty=nameWithType> класс.  
  
## <a name="see-also"></a>См. также

- <xref:System.String?displayProperty=nameWithType>
- [Типы данных](index.md)
- [Тип данных Char](char-data-type.md)
- [Type Conversion Functions](../functions/type-conversion-functions.md)
- [Сводка по преобразованию](../keywords/conversion-summary.md)
- [Практическое руководство. Вызов функции Windows, принимающей значение беззнакового типа](../../programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [Эффективное использование типов данных](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
