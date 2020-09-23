---
title: Практическое руководство. Преобразование строки в массив символов
ms.date: 07/20/2015
helpviewer_keywords:
- character arrays [Visual Basic], converting strings
- arrays [Visual Basic], converting strings to
- examples [Visual Basic], string conversion
- strings [Visual Basic], converting to arrays
- string conversion [Visual Basic], arrays
ms.assetid: 1b54b686-ab29-413b-adce-6bd5422376eb
ms.openlocfilehash: e1f634fcdb23f16e794449f8fe7b53c451c8c5b8
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91059175"
---
# <a name="how-to-convert-a-string-to-an-array-of-characters-in-visual-basic"></a>Практическое руководство. Преобразование строки (String) в массив символов в Visual Basic

Иногда бывает полезно иметь данные о символах в строке и позициях этих символов в строке, например при анализе строки. В этом примере показано, как можно получить массив символов в строке, вызвав <xref:System.String.ToCharArray%2A> метод строки.  
  
## <a name="example"></a>Пример  

 В этом примере показано, как разделить строку на `Char` массив и как разбить строку на `String` массив символов Юникода. Это различие состоит в том, что символы текста в Юникоде могут состоять из двух или более `Char` символов (например, суррогатной пары или последовательности присоединяемых символов). Дополнительные сведения см <xref:System.Globalization.TextElementEnumerator> . в разделе и [стандарт Unicode](https://www.unicode.org/standard/standard.html).  
  
 [!code-vb[VbVbalrStrings#75](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class4.vb#75)]  
  
## <a name="example"></a>Пример  

 Сложнее разбить строку на символы в Юникоде, но это необходимо, если требуются сведения о визуальном представлении строки. В этом примере <xref:System.Globalization.StringInfo.SubstringByTextElements%2A> метод используется для получения сведений о символах текста Юникода, составляющих строку.  
  
 [!code-vb[VbVbalrStrings#76](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class4.vb#76)]  
  
## <a name="see-also"></a>См. также

- <xref:System.String.Chars%2A>
- <xref:System.Globalization.StringInfo?displayProperty=nameWithType>
- [Практическое руководство. Доступ к символам в строках](how-to-access-characters-in-strings.md)
- [Преобразование между строками и другими типами данных в Visual Basic](converting-between-strings-and-other-data-types.md)
- [Строки](index.md)
