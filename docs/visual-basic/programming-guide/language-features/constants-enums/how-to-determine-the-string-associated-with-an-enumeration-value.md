---
title: Практическое руководство. Определение строки, связанной со значением из перечисления
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic]
- strings [Visual Basic], enumeration values
- values [Visual Basic], enumeration members
ms.assetid: 9253e7c8-579c-49a2-8f26-392b20ea99eb
ms.openlocfilehash: 4138759bfbb049b77406fc536219b40d3ed9e2a5
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91058773"
---
# <a name="how-to-determine-the-string-associated-with-an-enumeration-value-visual-basic"></a>Практическое руководство. Определение строки, связанной со значением из перечисления (Visual Basic)

<xref:System.Enum.GetValues%2A>Методы и <xref:System.Enum.GetNames%2A> позволяют определить строки и значения, связанные с элементами перечисления.  
  
### <a name="to-determine-the-string-associated-with-an-enumeration"></a>Определение строки, связанной с перечислением  
  
- Используйте <xref:System.Enum.GetNames%2A> метод для получения строк, связанных с элементами перечисления. В этом примере объявляется перечисление, `flavorEnum` а затем используется <xref:System.Enum.GetNames%2A> метод для вывода строк, связанных с каждым элементом.  
  
     [!code-vb[VbEnumsTask#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#2)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Enum.GetValues%2A>
- <xref:System.Enum.GetNames%2A>
- <xref:System.Enum>
- [Практическое руководство. Объявление перечисления](how-to-declare-enumerations.md)
- [Практическое руководство. Ссылка на элемент перечисления](how-to-refer-to-an-enumeration-member.md)
- [Перечисления и уточнение имен](enumerations-and-name-qualification.md)
- [Практическое руководство. Перебор элементов перечисления в Visual Basic](how-to-iterate-through-an-enumeration.md)
- [Когда следует использовать перечисление](when-to-use-an-enumeration.md)
- [Оператор Enum](../../../language-reference/statements/enum-statement.md)
