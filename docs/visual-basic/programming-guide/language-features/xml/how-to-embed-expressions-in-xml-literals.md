---
description: 'Дополнительные сведения о: инструкции по внедрению выражений в XML-литералы (Visual Basic)'
title: Практическое руководство. Внедрение выражений в XML-литералы
ms.date: 07/20/2015
helpviewer_keywords:
- embedded expressions [Visual Basic]
- XML literals [Visual Basic], embedded expressions
ms.assetid: 75016fad-0141-42de-8564-5051be29487e
ms.openlocfilehash: 18bc6164c4466532956f1a5df70c1ff2a8dbbfd5
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "100480054"
---
# <a name="how-to-embed-expressions-in-xml-literals-visual-basic"></a>Практическое руководство. Внедрение выражений в XML-литералы (Visual Basic)

Литералы XML можно объединять с внедренными выражениями для создания XML-документа, фрагмента или элемента, содержащего содержимое, созданное во время выполнения. В следующих примерах показано, как использовать внедренные выражения для заполнения содержимого, атрибутов и имен элементов во время выполнения.  
  
 Синтаксис для внедренного выражения — это тот `<%=` `exp` `%>` же синтаксис, который используется ASP.NET. Дополнительные сведения см. [в разделе внедренные выражения в XML](embedded-expressions-in-xml.md).  
  
 Вы также можете использовать [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] API для создания [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] объектов. Для получения дополнительной информации см. <xref:System.Xml.Linq.XElement>.  
  
## <a name="procedures"></a>Процедуры  
  
#### <a name="to-insert-text-as-element-content"></a>Вставка текста в качестве содержимого элемента  
  
- В следующем примере показано, как вставить текст, содержащийся в переменной, `contactName` между открывающим и закрывающим элементами Name.  
  
     [!code-vb[VbXMLSamples#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples14.vb#39)]  
  
     В этом примере выводятся следующие данные:  
  
    ```xml  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
#### <a name="to-insert-text-as-an-attribute-value"></a>Вставка текста в качестве значения атрибута  
  
- В следующем примере показано, как вставить текст, содержащийся в переменной, в `phoneType` качестве значения `type` атрибута.  
  
     [!code-vb[VbXMLSamples#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples14.vb#40)]  
  
     В этом примере выводятся следующие данные:  
  
    ```xml  
    <contact>  
      <phone type="home">206-555-0144</phone>  
    </contact>  
    ```  
  
#### <a name="to-insert-text-for-an-element-name"></a>Вставка текста для имени элемента  
  
- В следующем примере показано, как вставить текст, содержащийся в переменной, в `elementName` качестве имени элемента.  
  
     При создании элементов с помощью этого метода их необходимо закрыть с помощью \</> тега.  
  
     [!code-vb[VbXMLSamples#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples14.vb#41)]  
  
     В этом примере выводятся следующие данные:  
  
    ```xml  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
## <a name="see-also"></a>См. также

- [Практическое руководство. Создание XML-литералов](how-to-create-xml-literals.md)
- [Встроенные выражения в XML](embedded-expressions-in-xml.md)
- [Создание XML в Visual Basic](creating-xml.md)
- [XML](index.md)
