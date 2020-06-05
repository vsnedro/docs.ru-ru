---
title: Общие сведения об XML-литералах
ms.date: 07/20/2015
helpviewer_keywords:
- XML literals [Visual Basic], about XML literals
- declaring XML literals [Visual Basic]
- LINQ to XML [Visual Basic], XML literals
- literals [Visual Basic], XML
ms.assetid: 37987c15-4ab8-471b-bd45-399816bfb57f
ms.openlocfilehash: e889de4eefae6a943c70735f8a16474cb76d1149
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403295"
---
# <a name="xml-literals-overview-visual-basic"></a>Общие сведения об XML-литералах (Visual Basic)
*XML-литерал* позволяет внедрять XML непосредственно в код Visual Basic. Синтаксис XML-литерала представляет [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] объекты, и он аналогичен синтаксису xml 1,0. Это упрощает создание XML-элементов и документов программным способом, так как код имеет ту же структуру, что и окончательный XML.  
  
 Visual Basic компилирует XML-литералы в [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] объекты. [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]предоставляет простую объектную модель для создания XML-кода и управления им, и эта модель хорошо интегрируется с запросом, интегрированным с языком (LINQ). Дополнительные сведения см. в разделе <xref:System.Xml.Linq.XElement>.  
  
 Выражение Visual Basic можно внедрить в XML-литерал. Во время выполнения приложение создает [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] объект для каждого литерала, включая значения внедренных выражений. Это позволяет указать динамическое содержимое в XML-литерале. Дополнительные сведения см. [в разделе внедренные выражения в XML](embedded-expressions-in-xml.md).  
  
 Дополнительные сведения о различиях между синтаксисом XML-литерала и синтаксисом XML 1,0 см. [в разделе XML-литералы и спецификация xml 1,0](xml-literals-and-the-xml-1-0-specification.md).  
  
## <a name="simple-literals"></a>Простые литералы  
 Вы можете создать [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] объект в коде Visual Basic, введя или вставляя в допустимый XML. Литерал XML-элемента возвращает <xref:System.Xml.Linq.XElement> объект. Дополнительные сведения см. в статьях [литералы XML-элементов](../../../language-reference/xml-literals/xml-element-literal.md) и [XML-литералы и спецификация XML 1,0](xml-literals-and-the-xml-1-0-specification.md). В следующем примере создается XML-элемент с несколькими дочерними элементами.  
  
 [!code-vb[VbXMLSamples#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples2.vb#5)]  
  
 Можно создать XML-документ, запустив XML-литерал с помощью `<?xml version="1.0"?>` , как показано в следующем примере. Литерал XML-документа возвращает <xref:System.Xml.Linq.XDocument> объект. Дополнительные сведения см. в разделе [XML-литерал документа](../../../language-reference/xml-literals/xml-document-literal.md).  
  
 [!code-vb[VbXMLSamples#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples2.vb#6)]  
  
> [!NOTE]
> Синтаксис XML-литерала в Visual Basic не идентичен синтаксису в спецификации XML 1,0. Дополнительные сведения см. [в разделе XML-литералы и спецификация xml 1,0](xml-literals-and-the-xml-1-0-specification.md).  
  
## <a name="line-continuation"></a>Продолжение строки  
 XML-литерал может охватывать несколько строк без использования символов продолжения строки (последовательность пробел-символ подчеркивания-Enter). Это упрощает сравнение XML-литералов в коде с XML-документами.  
  
 Компилятор рассматривает символы продолжения строки как часть XML-литерала. Поэтому следует использовать последовательность пробел-подчеркивания-Enter, только если она принадлежит [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] объекту.  
  
 Однако при наличии многострочного выражения во внедренном выражении нужны символы продолжения строки. Дополнительные сведения см. [в разделе внедренные выражения в XML](embedded-expressions-in-xml.md).  
  
## <a name="embedding-queries-in-xml-literals"></a>Встраивание запросов в XML-литералы  
 Запрос можно использовать во внедренном выражении. При этом элементы, возвращаемые запросом, добавляются в XML-элемент. Это позволяет добавлять динамическое содержимое, например результат выполнения запроса пользователя, в XML-литерал.  
  
 Например, следующий код использует внедренный запрос для создания XML-элементов из членов `phoneNumbers2` массива, а затем добавляет эти элементы в качестве дочерних элементов `contact2` .  
  
 [!code-vb[VbXMLSamples#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples2.vb#7)]  
  
## <a name="how-the-compiler-creates-objects-from-xml-literals"></a>Как компилятор создает объекты из XML-литералов  
 Компилятор Visual Basic преобразует литералы XML в вызовы эквивалентных [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] конструкторов для построения [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] объекта. Например, компилятор Visual Basic преобразует следующий пример кода в вызов <xref:System.Xml.Linq.XProcessingInstruction> конструктора для инструкции версии XML, вызывает <xref:System.Xml.Linq.XElement> конструктор для `<contact>` `<name>` элементов, и `<phone>` , а также вызывает <xref:System.Xml.Linq.XAttribute> конструктор для `type` атрибута. В частности, при наличии атрибутов, приведенных в следующем примере, компилятор Visual Basic будет вызывать <xref:System.Xml.Linq.XAttribute.%23ctor%28System.Xml.Linq.XName%2CSystem.Object%29> Конструктор дважды. Первый передаст значение `type` для `name` параметра и значение `home` для `value` параметра. Вторая также передает значение `type` для `name` параметра, а значение `work` для `value` параметра.  
  
 [!code-vb[VbXMLSamples#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples2.vb#6)]  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Xml.Linq.XElement>
- [Создание XML в Visual Basic](creating-xml.md)
- [Встроенные выражения в XML](embedded-expressions-in-xml.md)
- [XML-литерал документа](../../../language-reference/xml-literals/xml-document-literal.md)
- [XML-литерал элемента](../../../language-reference/xml-literals/xml-element-literal.md)
- [XML-литералы](../../../language-reference/xml-literals/index.md)
