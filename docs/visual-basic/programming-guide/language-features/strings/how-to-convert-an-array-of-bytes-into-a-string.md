---
title: Практическое руководство. Преобразование массива байтов в строку
ms.date: 07/20/2015
helpviewer_keywords:
- string conversion [Visual Basic], arrays
- byte arrays [Visual Basic], converting to strings
- examples [Visual Basic], strings
- arrays [Visual Basic], converting to strings
ms.assetid: d0dc8317-9ab3-4324-99f7-3f5788c0e72a
ms.openlocfilehash: 6dbbaafedeca4d2cea625a300d764f61bb575750
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410623"
---
# <a name="how-to-convert-an-array-of-bytes-into-a-string-in-visual-basic"></a>Практическое руководство. Преобразование массива байтов в строку в Visual Basic
В этом разделе показано, как преобразовать байты из массива байтов в строку.  
  
## <a name="example"></a>Пример  
 В этом примере используется <xref:System.Text.Encoding.GetString%2A> метод <xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType> класса Encoding для преобразования всех байтов из массива байтов в строку.  
  
 [!code-vb[VbVbalrStrings#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#72)]  
  
 Можно выбрать один из нескольких параметров кодировки для преобразования массива байтов в строку:  
  
- <xref:System.Text.Encoding.ASCII%2A?displayProperty=nameWithType>: Получает кодировку для набора символов ASCII (7-разрядных).  
  
- <xref:System.Text.Encoding.BigEndianUnicode%2A?displayProperty=nameWithType>: Получает кодировку для формата UTF-16 с обратным порядком байтов.  
  
- <xref:System.Text.Encoding.Default%2A?displayProperty=nameWithType>: Получает кодировку для текущей системной кодовой страницы ANSI.  
  
- <xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType>: Получает кодировку для формата UTF-16 с прямым порядком байтов.  
  
- <xref:System.Text.Encoding.UTF32%2A?displayProperty=nameWithType>: Получает кодировку для формата UTF-32 с прямым порядком байтов.  
  
- <xref:System.Text.Encoding.UTF7%2A?displayProperty=nameWithType>: Получает кодировку для формата UTF-7.  
  
- <xref:System.Text.Encoding.UTF8%2A?displayProperty=nameWithType>: Получает кодировку для формата UTF-8.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Text.Encoding?displayProperty=nameWithType>
- <xref:System.Text.Encoding.GetString%2A>
- [Практическое руководство. Преобразование строки в массив байтов в Visual Basic](how-to-convert-strings-into-an-array-of-bytes.md)
