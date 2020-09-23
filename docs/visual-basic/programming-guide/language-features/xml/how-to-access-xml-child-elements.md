---
title: Практическое руководство. Доступ к дочерним XML-элементам
ms.date: 07/20/2015
helpviewer_keywords:
- XML axis [Visual Basic], child
- child axis property [Visual Basic]
- XML child axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: 6689eb36-c471-469f-a82d-099ab8197b25
ms.openlocfilehash: 9c33bec9b9ea865d570bab08f27227129867cce9
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91058304"
---
# <a name="how-to-access-xml-child-elements-visual-basic"></a>Практическое руководство. Доступ к дочерним XML-элементам (Visual Basic)

В этом примере показано, как использовать свойство дочерней оси для доступа ко всем дочерним элементам XML с указанным именем в элементе XML. В частности, он использует <xref:System.Xml.Linq.XElement.Value%2A> свойство для получения значения первого элемента в коллекции, `name` возвращаемого свойством дочерней оси. `name`Свойство дочерней оси получает все дочерние элементы с именем `phone` в `contact` объекте. В этом примере также используется `phone` свойство дочерней оси для доступа ко всем дочерним элементам с именем `phone` , содержащимся в `contact` объекте.  
  
## <a name="example"></a>Пример  

 [!code-vb[VbXMLSamples#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples4.vb#10)]  
  
## <a name="compile-the-code"></a>Компиляция кода  

 Для этого примера требуются:  
  
- ссылка на пространство имен <xref:System.Xml.Linq>.  
  
## <a name="see-also"></a>См. также

- <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType>
- [XML Child Axis Property](../../../language-reference/xml-axis/xml-child-axis-property.md)
- [Свойство значения XML](../../../language-reference/xml-axis/xml-value-property.md)
- [Доступ к XML в Visual Basic](accessing-xml.md)
- [XML](index.md)
