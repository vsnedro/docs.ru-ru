---
title: Практическое руководство. Группирование значений связанных констант
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic], constants
- constants [Visual Basic], grouping together
ms.assetid: 09d61da5-c940-4126-a79f-ba93c36653dc
ms.openlocfilehash: d2393af8b0c2b0c2e528f9908a78fbc7f182c8cf
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414444"
---
# <a name="how-to-group-related-constant-values-together-visual-basic"></a>Практическое руководство. Группирование значений связанных констант (Visual Basic)
Перечисление — это лучший способ сгруппировать связанные константы. Перечисление создается с помощью `Enum` инструкции в разделе Declarations класса или модуля. Дополнительные сведения см. [в разделе инструкции. Объявление перечисления](how-to-declare-enumerations.md).  
  
### <a name="to-group-related-constant-values"></a>Группирование связанных значений констант  
  
1. Напишите объявление, которое включает уровень доступа к коду, `Enum` ключевое слово и допустимое имя. В этом примере создается `Private` Перечисление `temperatureValues` .  
  
     [!code-vb[VbEnumsTask#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#21)]  
  
2. Определите константы в перечислении. В этом примере создается `Public` Перечисление `temperatureValues` , и ему присваиваются значения.  
  
     [!code-vb[VbEnumsTask#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#1)]  
  
## <a name="see-also"></a>См. также раздел

- [Перечисления и уточнение имен](enumerations-and-name-qualification.md)
- [Практическое руководство. Ссылка на элемент перечисления](how-to-refer-to-an-enumeration-member.md)
- [Когда следует использовать перечисление](when-to-use-an-enumeration.md)
- [Общие сведения о константах](constants-overview.md)
- [Типы данных констант и литералов](constant-and-literal-data-types.md)
- [Константы и перечисления](../../../language-reference/constants-and-enumerations.md)
