---
title: Практическое руководство. Преобразование строк в массив байтов
ms.date: 07/20/2015
helpviewer_keywords:
- string conversion [Visual Basic], arrays
- arrays [Visual Basic], converting strings to
- byte arrays
- examples [Visual Basic], string conversion
- arrays [Visual Basic], byte arrays
ms.assetid: f477d35c-a3fc-4a30-b1d4-cd0d353aae1d
ms.openlocfilehash: 3ee1d5e1e31054f23f4510c7a112d8e3473bcdd7
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410610"
---
# <a name="how-to-convert-strings-into-an-array-of-bytes-in-visual-basic"></a>Практическое руководство. Преобразование строки в массив байтов в Visual Basic
В этом разделе показано, как преобразовать строку в массив байтов.  
  
## <a name="example"></a>Пример  
 В этом примере используется <xref:System.Text.Encoding.GetBytes%2A> метод <xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType> класса Encoding для преобразования строки в массив байтов.  
  
 [!code-vb[VbVbalrStrings#74](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#74)]  
  
 Можно выбрать один из нескольких параметров кодировки для преобразования строки в массив байтов:  
  
- <xref:System.Text.Encoding.ASCII%2A?displayProperty=nameWithType>: Получает кодировку для набора символов ASCII (7-разрядных).  
  
- <xref:System.Text.Encoding.BigEndianUnicode%2A?displayProperty=nameWithType>: Получает кодировку для формата UTF-16 с обратным порядком байтов.  
  
- <xref:System.Text.Encoding.Default%2A?displayProperty=nameWithType>: Получает кодировку для текущей системной кодовой страницы ANSI.  
  
- <xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType>: Получает кодировку для формата UTF-16 с прямым порядком байтов.  
  
- <xref:System.Text.Encoding.UTF32%2A?displayProperty=nameWithType>: Получает кодировку для формата UTF-32 с прямым порядком байтов.  
  
- <xref:System.Text.Encoding.UTF7%2A?displayProperty=nameWithType>: Получает кодировку для формата UTF-7.  
  
- <xref:System.Text.Encoding.UTF8%2A?displayProperty=nameWithType>: Получает кодировку для формата UTF-8.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Text.Encoding?displayProperty=nameWithType>
- <xref:System.Text.Encoding.GetBytes%2A>
- [Практическое руководство. Преобразование массива байтов в строку в Visual Basic](how-to-convert-an-array-of-bytes-into-a-string.md)
