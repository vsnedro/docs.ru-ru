---
title: Практическое руководство. Ссылка на элемент перечисления
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic], referring to
- values [Visual Basic], associating constant values with names
- enumeration members
- constants [Visual Basic], enumerated
ms.assetid: bbb5c3cc-7cdb-4814-8d6a-a6d91546ed1e
ms.openlocfilehash: d1b239e7d6be3ebf1e64d6589a4cc14dce8946f5
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91095672"
---
# <a name="how-to-refer-to-an-enumeration-member-visual-basic"></a>Практическое руководство. Ссылка на член перечисления (Visual Basic)

Перечисления предоставляют удобный способ работы с наборами связанных констант и для связывания постоянных значений с именами. Например, вы можете объявить перечисление для набора целочисленных констант, связанных с днями недели, а затем использовать в коде названия дней, а не числа.  
  
 С помощью инструкции можно избежать использования полных имен `Imports` . Дополнительные сведения см. в разделе [перечисления и квалификация имени](enumerations-and-name-qualification.md).  
  
### <a name="to-refer-to-an-enumeration-member"></a>Ссылка на элемент перечисления  
  
- Уточните имя члена с помощью перечисления. Например, в следующем примере член перечисления присваивается `Saturday` `FirstDayOfWeek` переменной `DayValue` .  
  
     [!code-vb[VbEnumsTask#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#19)]  
  
## <a name="see-also"></a>См. также

- [Практическое руководство. Объявление перечисления](how-to-declare-enumerations.md)
- [Перечисления и уточнение имен](enumerations-and-name-qualification.md)
- [Практическое руководство. Перебор элементов перечисления в Visual Basic](how-to-iterate-through-an-enumeration.md)
- [Практическое руководство. Определение строки, связанной со значением из перечисления](how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [Когда следует использовать перечисление](when-to-use-an-enumeration.md)
