---
title: Пробелы в XML-литералах
ms.date: 07/20/2015
helpviewer_keywords:
- white space [XML in Visual Basic]
- XML literals [Visual Basic], white space
ms.assetid: dfe3a9ff-d69a-418e-a6b5-476f4ed84219
ms.openlocfilehash: b3caf7ac052f3fed3fe5427da0cc96bbdd955ea6
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84360479"
---
# <a name="white-space-in-xml-literals-visual-basic"></a>Пробелы в XML-литералах (Visual Basic)
Компилятор Visual Basic включает только значащие символы пробела из XML-литерала при создании [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] объекта. Незначащие символы пробела не включаются.  
  
## <a name="significant-and-insignificant-white-space"></a>Значительные и незначащие пробелы  
 Символы пробелов в XML-литералах являются значимыми только в трех областях:  
  
- Если они находятся в значении атрибута.  
  
- Если они являются частью текстового содержимого элемента, а текст также содержит другие символы.  
  
- Если они находятся в внедренном выражении для текстового содержимого элемента.  
  
 В противном случае компилятор рассматривает символы пробела как незначащие и не включает в [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] объект для литерала.  
  
 Чтобы включить незначащие пробелы в XML-литерал, используйте внедренное выражение, содержащее строковый литерал с пробелом.  
  
> [!NOTE]
> Если `xml:space` атрибут отображается в литерале XML-элемента, Visual Basic компилятор включает атрибут в <xref:System.Xml.Linq.XElement> объект, но добавление этого атрибута не влияет на то, как компилятор обрабатывает пробелы.  
  
## <a name="examples"></a>Примеры  
 В следующем примере содержатся два XML-элемента: OUTER и Inner. Оба элемента содержат пробелы в текстовом содержимом. Пробелы во внешнем элементе являются незначащими, так как содержат только пробелы и XML-элементы. Пробел во внутреннем элементе важен, так как он содержит пробелы и текст.  
  
 [!code-vb[VbXMLSamples#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#29)]  
  
 При запуске этот код отображает следующий текст.  
  
```xml  
<outer>  
  <inner>  
                                          Inner text  
                                      </inner>  
</outer>  
```  
  
## <a name="see-also"></a>См. также раздел

- [Создание XML в Visual Basic](creating-xml.md)
