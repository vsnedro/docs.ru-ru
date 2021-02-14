---
description: Дополнительные сведения см. в статье как преобразовать шестнадцатеричные строки в числа (Visual Basic)
title: Практическое руководство. Преобразование шестнадцатеричных строк в числа
ms.date: 01/31/2018
helpviewer_keywords:
- numbers [Visual Basic], hexadecimals
- hexadecimals [Visual Basic], decimals
- examples [Visual Basic], string conversion
- decimals [Visual Basic], hexadecimals
- string conversion [Visual Basic], hexadecimal to numbers
ms.assetid: 76675807-eadb-4c08-bd50-e6c6ff4b8ced
ms.openlocfilehash: cf1648b5f85f189f203f56cf569041e4f2db5ac3
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "100425547"
---
# <a name="how-to-convert-hexadecimal-strings-to-numbers-visual-basic"></a>Практическое руководство. Преобразование шестнадцатеричных строк в числа (Visual Basic)

В этом примере шестнадцатеричная строка преобразуется в целое число с помощью <xref:System.Convert.ToInt32%2A?displayProperty=nameWithType> метода.

## <a name="to-convert-a-hexadecimal-string-to-a-number"></a>Преобразование шестнадцатеричной строки в число

- Используйте <xref:System.Convert.ToInt32(System.String,System.Int32)> метод для преобразования числа, выраженного в кодировке base-16, в целое число.

  Первым аргументом <xref:System.Convert.ToInt32(System.String,System.Int32)> метода является Преобразуемая строка. Второй аргумент описывает, в какой базе чисел выражается число. шестнадцатеричное число — основание 16.

  [!code-vb[VbVbalrStrings#62](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#62)]

- Обратите внимание, что шестнадцатеричная строка имеет следующие ограничения.

  - Он не может включать `&h` префикс.
  - Он не может включать `_` Разделитель цифр.

  Если указан префикс или разделитель цифр, вызов <xref:System.Convert.ToInt32(System.String,System.Int32)> метода создает исключение <xref:System.FormatException> .

## <a name="see-also"></a>См. также раздел

- <xref:Microsoft.VisualBasic.Conversion.Hex%2A>
- <xref:System.Convert.ToInt32%2A?displayProperty=nameWithType>
