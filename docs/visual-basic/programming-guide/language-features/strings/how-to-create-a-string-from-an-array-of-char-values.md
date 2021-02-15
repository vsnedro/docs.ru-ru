---
description: Дополнительные сведения см. в статье как создать строку из массива значений типа char (Visual Basic)
title: Практическое руководство. Создание строки из значений массива символьного типа
ms.date: 07/20/2015
helpviewer_keywords:
- examples [Visual Basic], arrays
- examples [Visual Basic], Char data type
ms.assetid: 69f94e85-d57c-4ccc-a62a-426e829f5c5e
ms.openlocfilehash: 67b675f5f02c92b785e374b99f49248d43d12fb4
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "100429836"
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
