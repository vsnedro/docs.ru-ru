---
title: Символьные типы данных
ms.date: 07/20/2015
helpviewer_keywords:
- data types [Visual Basic], character
- String data type [Visual Basic], character data types
- character data types [Visual Basic]
- Char data type [Visual Basic], character data types
- data types [Visual Basic], choosing
ms.assetid: 902479ef-1679-47fc-9911-0c1c5008226c
ms.openlocfilehash: 33dd4c62776ae8c5ec0ce0a6d0858a7ed0d047fb
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401996"
---
# <a name="character-data-types-visual-basic"></a>Символьные типы данных (Visual Basic)
Visual Basic предоставляет *символьные типы данных* для работы с печатными и отображаемыми символами. Несмотря на то, что они работают с символами Юникода, `Char` содержит один символ, тогда как `String` содержит неопределенное число символов.  
  
 Для таблицы, отображающей параллельное сравнение типов данных Visual Basic, см. в разделе [типы данных](../../../language-reference/data-types/index.md).  
  
## <a name="char-type"></a>Тип char  
 `Char`Тип данных — это один двухбайтовый (16-разрядный) символ Юникода. Если переменная всегда хранит ровно один символ, объявите ее как `Char` . Пример:  
  
 [!code-vb[VbVbalrCharTypes#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrchartypes/vb/module1.vb#1)]
  
 Каждое возможное значение в `Char` переменной или `String` является кодовой *точкой*или кодом символа в кодировке Юникода. Символы Юникода включают в себя основную кодировку ASCII, различные буквы, цифры, символы валют, дроби, диакритические знаки, математические и технические символы.  
  
> [!NOTE]
> Набор символов Юникода резервирует кодовые точки D800 до DFFF (от 55296 до 55551 десятичного) для *пар символов-заместителей*, для которых требуются 2 16-разрядные значения для представления одной кодовой точки. `Char`Переменная не может содержать суррогатную пару, а `String` для хранения такой пары используется две позиции.  
  
 Дополнительные сведения см. в разделе [тип данных char](../../../language-reference/data-types/char-data-type.md).  
  
## <a name="string-type"></a>Тип строки  
 `String`Тип данных — это последовательность из нуля или более двухбайтовых (16-разрядных) символов Юникода. Если переменная может содержать неопределенное число символов, объявите ее как `String` . Пример:  
  
 [!code-vb[VbVbalrCharTypes#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrchartypes/vb/module1.vb#2)]
  
 Дополнительные сведения см. в разделе [тип данных String](../../../language-reference/data-types/string-data-type.md).  
  
## <a name="see-also"></a>См. также раздел

- [Простые типы данных](elementary-data-types.md)
- [Составные типы данных](composite-data-types.md)
- [Generic Types in Visual Basic](generic-types.md)
- [Value Types and Reference Types](value-types-and-reference-types.md)
- [Преобразование типов в Visual Basic](type-conversions.md)
- [Устранение неполадок, связанных с типами данных](troubleshooting-data-types.md)
- [Символы типов](type-characters.md)
