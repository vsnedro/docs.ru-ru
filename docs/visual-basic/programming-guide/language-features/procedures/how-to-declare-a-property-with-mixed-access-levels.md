---
title: Практическое руководство. Объявление свойства со смешанным уровнем доступа
ms.date: 07/20/2015
helpviewer_keywords:
- access levels [Visual Basic], properties
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- mixed access levels
- Visual Basic code, properties
- properties [Visual Basic], access levels
- Property statement [Visual Basic], declaring mixed access levels
ms.assetid: fdbb2d97-279a-4956-b26c-cbdfbc34915a
ms.openlocfilehash: 78363f7b2fb5b251f7409e53b2802baf83b05810
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91072708"
---
# <a name="how-to-declare-a-property-with-mixed-access-levels-visual-basic"></a>Практическое руководство. Объявление свойства со смешанным уровнем доступа (Visual Basic)

Если требуется `Get` `Set` , чтобы процедуры и для свойства имели разные уровни доступа, можно использовать более строгий уровень в `Property` инструкции и более строгий уровень в `Get` `Set` операторе или. Смешанные уровни доступа для свойства используются, если требуется, чтобы определенные части кода могли получить значение свойства, а некоторые другие части кода могут изменить значение.  
  
 Дополнительные сведения об уровнях доступа см. [в разделе уровни доступа в Visual Basic](../declared-elements/access-levels.md).  
  
### <a name="to-declare-a-property-with-mixed-access-levels"></a>Объявление свойства со смешанными уровнями доступа  
  
1. Объявите свойство обычным способом и укажите менее низкий уровень доступа (например, `Public` ) в `Property` инструкции.  
  
2. Объявите `Get` или процедуру, `Set` указав более четкий уровень доступа (например, `Friend` ).  
  
3. Не указывайте уровень доступа для другой процедуры свойства. Он предполагает уровень доступа, объявленный в `Property` инструкции. Доступ можно ограничить только для одной из процедур свойств.  
  
     [!code-vb[VbVbcnProcedures#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#10)]  
  
     В предыдущем примере `Get` процедура имеет тот же `Protected` доступ, что и само свойство, а `Set` процедура имеет `Private` доступ. Класс, производный от `employee` , может считывать `salary` значение, но только `employee` класс может его задать.  
  
## <a name="see-also"></a>См. также

- [Процедуры](./index.md)
- [Процедуры свойств](./property-procedures.md)
- [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md)
- [Property Statement](../../../language-reference/statements/property-statement.md)
- [Различия между свойствами и переменными в Visual Basic](./differences-between-properties-and-variables.md)
- [Практическое руководство. Создание свойства](./how-to-create-a-property.md)
- [Практическое руководство. Вызов процедуры свойства](./how-to-call-a-property-procedure.md)
- [Практическое руководство. Объявление и вызов свойства по умолчанию в Visual Basic](./how-to-declare-and-call-a-default-property.md)
- [Практическое руководство. Запись значения в свойство](./how-to-put-a-value-in-a-property.md)
- [Практическое руководство. Получение значения из свойства](./how-to-get-a-value-from-a-property.md)
