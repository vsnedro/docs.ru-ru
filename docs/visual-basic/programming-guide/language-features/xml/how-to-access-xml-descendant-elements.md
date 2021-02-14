---
description: Дополнительные сведения см. в статье как получить доступ к элементам-потомкам XML (Visual Basic)
title: Практическое руководство. Доступ к элементам-потомкам XML
ms.date: 07/20/2015
helpviewer_keywords:
- XML descendent axis property [Visual Basic]
- XML axis [Visual Basic], descendent
- descendent axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: aabfa258-4112-4e7e-bab9-403f96072ef7
ms.openlocfilehash: d8f3176a91c2f637f49d2754513f3253399ee8ed
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "100433178"
---
# <a name="how-to-access-xml-descendant-elements-visual-basic"></a>Практическое руководство. Доступ к производным XML элементам (Visual Basic)

В этом примере показано, как использовать свойство оси потомков для доступа ко всем XML-элементам с указанным именем и содержащимся в XML-элементе. В частности, он использует `Value` свойство для получения значения первого элемента в коллекции, `name` возвращаемого свойством дочерней оси. `name`Свойство дочерняя ось получает все элементы с именем `name` , содержащиеся в `contacts` объекте. В этом примере также используется `phone` свойство оси потомков для доступа ко всем потомкам `phone` , имена которых содержатся в `contacts` объекте.  
  
## <a name="example"></a>Пример  

 [!code-vb[VbXMLSamples#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#31)]  
  
## <a name="compile-the-code"></a>Компиляция кода  

 Для этого примера требуются:  
  
- ссылка на пространство имен <xref:System.Xml.Linq>.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Xml.Linq.XContainer.Descendants%2A?displayProperty=nameWithType>
- [XML Descendant Axis Property](../../../language-reference/xml-axis/xml-descendant-axis-property.md)
- [Свойство значения XML](../../../language-reference/xml-axis/xml-value-property.md)
- [Доступ к XML в Visual Basic](accessing-xml.md)
- [XML](index.md)
