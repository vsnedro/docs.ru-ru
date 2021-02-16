---
description: Дополнительные сведения см. в статье как получить доступ к символам в строках в Visual Basic
title: Практическое руководство. Доступ к символам в строках
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], accessing characters
- characters [Visual Basic], accessing in strings
ms.assetid: 02c5206c-ffab-494d-b648-3b2ea358dc34
ms.openlocfilehash: 373005699483dbae92df3a6fe73cc9b6318a9c61
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "100476167"
---
# <a name="how-to-access-characters-in-strings-in-visual-basic"></a>Практическое руководство. Доступ к символам строк в Visual Basic

В этом примере показано, как использовать <xref:System.String.Chars%2A> свойство для доступа к символу в указанном месте в строке.  
  
## <a name="example"></a>Пример  

 Иногда бывает полезно иметь данные о символах в строке и позициях этих символов в строке. Строку можно представить как массив символов ( `Char` экземпляров); вы можете получить определенный символ, обратившись к индексу этого символа через <xref:System.String.Chars%2A> свойство.  
  
 [!code-vb[VbVbalrStrings#49](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#49)]  
  
 Параметр свойства отсчитывается `index` <xref:System.String.Chars%2A> от нуля.  
  
## <a name="robust-programming"></a>Отказоустойчивость  

 <xref:System.String.Chars%2A>Свойство возвращает символ в указанной позиции. Однако некоторые символы Юникода могут быть представлены более чем одним символом. Дополнительные сведения о работе с символами Юникода см. в разделе [инструкции. Преобразование строки в массив символов](how-to-convert-a-string-to-an-array-of-characters.md).  
  
 <xref:System.String.Chars%2A>Свойство вызывает исключение, <xref:System.IndexOutOfRangeException> Если `index` параметр больше или равен длине строки или если он меньше нуля.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.String.Chars%2A>
- [Практическое руководство. Преобразование строки в массив символов](how-to-convert-a-string-to-an-array-of-characters.md)
- [Преобразование между строками и другими типами данных в Visual Basic](converting-between-strings-and-other-data-types.md)
- [Строки](index.md)
