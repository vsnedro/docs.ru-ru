---
title: Практическое руководство. Создание строки из значений массива символьного типа
ms.date: 07/20/2015
helpviewer_keywords:
- examples [Visual Basic], arrays
- examples [Visual Basic], Char data type
ms.assetid: 69f94e85-d57c-4ccc-a62a-426e829f5c5e
ms.openlocfilehash: d9ec897467f0caac0afc089a028516c0316a2bda
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410597"
---
# <a name="how-to-create-a-string-from-an-array-of-char-values-visual-basic"></a>Практическое руководство. Создание строки из значений массива символьного типа (Visual Basic)
В этом примере создается строка «ABCD» из отдельных символов.  
  
## <a name="example"></a>Пример  
 [!code-vb[VbVbalrStrings#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#61)]  
  
## <a name="compile-the-code"></a>Компиляция кода  
 Этот метод не имеет особых требований.  
  
 Синтаксис `"a"c` , где один `c` символ следует за одиночным знаком в кавычках, используется для создания символьного литерала.  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 Символы NULL (эквивалентны `Chr(0)` ) в строке ведут к непредвиденным результатам при использовании строки. Символ null будет включаться в строку, но символы, следующие за символом NULL, не будут отображаться в некоторых ситуациях.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.String>
- [Тип данных Char](../../../language-reference/data-types/char-data-type.md)
- [Типы данных](../data-types/index.md)
