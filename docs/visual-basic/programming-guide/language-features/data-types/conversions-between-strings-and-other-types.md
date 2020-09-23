---
title: Преобразования значений между строковыми и другими типами
ms.date: 07/20/2015
helpviewer_keywords:
- data type conversion [Visual Basic], string
- conversions [Visual Basic], type
- string conversion [Visual Basic]
- conversions [Visual Basic], data type
- type conversion [Visual Basic], string
- regional options
ms.assetid: c3a99596-f09a-44a5-81dd-1b89a094f1df
ms.openlocfilehash: 823931f7d6beb8218e8b99d4a8d45716b7214304
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91077154"
---
# <a name="conversions-between-strings-and-other-types-visual-basic"></a>Преобразование значений между строковыми и другими типами (Visual Basic)

Можно преобразовать числовое значение типа, `Boolean` или значения даты и времени в `String` . Можно также преобразовать в обратном направлении — от строкового значения к числовому, `Boolean` или `Date` — при условии, что содержимое строки может интерпретироваться как допустимое значение целевого типа данных. Если они не могут, возникает ошибка времени выполнения.  
  
 Преобразования для всех этих назначений в любом направлении представляют собой сужающие преобразования. Следует использовать ключевые слова преобразования типов (,,,,,,, `CBool` `CByte` ,,,, `CDate` `CDbl` `CDec` `CInt` `CLng` `CSByte` `CShort` `CSng` `CStr` `CUInt` , `CULng` , `CUShort` и `CType` ). <xref:Microsoft.VisualBasic.Strings.Format%2A>Функции и <xref:Microsoft.VisualBasic.Conversion.Val%2A> предоставляют дополнительный контроль над преобразованиями между строками и числами.  
  
 Если вы определили класс или структуру, можно определить операторы преобразования типов между `String` и типом класса или структуры. Дополнительные сведения см. в разделе [How to: Define a Conversion Operator](../procedures/how-to-define-a-conversion-operator.md).  
  
## <a name="conversion-of-numbers-to-strings"></a>Преобразование чисел в строки  

 Функцию можно использовать `Format` для преобразования числа в отформатированную строку, которая может включать не только соответствующие цифры, но и символы форматирования, такие как знак валюты (например `$` ,), разделители тысяч или *символы группирования цифр* (например,), `,` и десятичный разделитель (например,) `.` . `Format` автоматически использует соответствующие символы в соответствии с **региональными** параметрами, заданными на **панели управления**Windows.  
  
 Обратите внимание, что оператор конкатенации ( `&` ) может преобразовать число в строку неявным образом, как показано в следующем примере.  
  
```vb  
' The following statement converts count to a String value.  
Str = "The total count is " & count  
```  
  
## <a name="conversion-of-strings-to-numbers"></a>Преобразование строк в числа  

 Функцию можно использовать `Val` для явного преобразования цифр из строки в число. `Val` считывает строку, пока не встретится символ, отличный от цифры, пробела, табуляции, перевода строки или точки. Последовательности "&O" и "&H" изменяют основание системы счисления и завершают сканирование. До тех пор пока не будет остановлено чтение, `Val` преобразует все соответствующие символы в числовое значение. Например, следующая инструкция возвращает значение `141.825` .  
  
 `Val("   14   1.825 miles")`  
  
 Когда Visual Basic преобразует строку в числовое значение, она использует **региональные параметры** , заданные на **панели управления** Windows, для интерпретации разделителя групп разрядов, десятичного разделителя и символа валюты. Это означает, что преобразование может быть выполнено в одном параметре, но не в другом. Например, `"$14.20"` допустим в английской (США) национальной настройке, но не на французском языке.  
  
## <a name="see-also"></a>См. также

- [Преобразование типов в Visual Basic](type-conversions.md)
- [Widening and Narrowing Conversions](widening-and-narrowing-conversions.md)
- [Явные и неявные преобразования](implicit-and-explicit-conversions.md)
- [Практическое руководство. Преобразование объекта к другому типу в Visual Basic](how-to-convert-an-object-to-another-type.md)
- [Преобразования массивов](array-conversions.md)
- [Типы данных](../../../language-reference/data-types/index.md)
- [Type Conversion Functions](../../../language-reference/functions/type-conversion-functions.md)
- [Разработка глобализованных и локализованных приложений](/visualstudio/ide/globalizing-and-localizing-applications)
