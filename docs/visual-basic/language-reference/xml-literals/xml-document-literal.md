---
title: XML-литерал документа
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralDocument
helpviewer_keywords:
- XML document literal [Visual Basic]
- XML literals [Visual Basic], document
- XML documents [Visual Basic], creating
- document literal [Visual Basic]
ms.assetid: f7bbee56-0911-41de-b907-96f20450137b
ms.openlocfilehash: 3a2182d2937827bc8dc45e22307a3668420261a2
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400206"
---
# <a name="xml-document-literal-visual-basic"></a>XML-литерал документа (Visual Basic)
Литерал, представляющий <xref:System.Xml.Linq.XDocument> объект.  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<?xml version="1.0" [encoding="encoding"] [standalone="standalone"] ?>  
[ piCommentList ]  
rootElement  
[ piCommentList ]  
```  
  
## <a name="parts"></a>Компоненты  
  
|Термин|Определение|  
|---|---|  
|`encoding`|Необязательный элемент. Литеральный текст, объявляющий кодировку, используемую в документе.|  
|`standalone`|Необязательный элемент. Текст литерала. Значение должно быть "Yes" или "No".|  
|`piCommentList`|Необязательный элемент. Список инструкций по обработке XML и XML-комментариев. Принимает следующий формат:<br /><br /> `piComment [` `piComment` `... ]`<br /><br /> Каждый `piComment` из них может быть одним из следующих:<br /><br /> -   [Литерал инструкции обработки XML](xml-processing-instruction-literal.md).<br />-   [XML-литерал комментария](xml-comment-literal.md).|  
|`rootElement`|Обязательный. Корневой элемент документа. Формат может быть одним из следующих:<br /><br /> <ul><li>[Литерал XML-элемента](xml-element-literal.md).</li><li>Внедренное выражение формы `<%=` `elementExp` `%>` . Метод `elementExp` возвращает одно из следующих:<br /><br /> <ul><li>Объект <xref:System.Xml.Linq.XElement>.</li><li>Коллекция, содержащая один <xref:System.Xml.Linq.XElement> объект и любое количество <xref:System.Xml.Linq.XProcessingInstruction> <xref:System.Xml.Linq.XComment> объектов и.</li></ul></li></ul><br /> Дополнительные сведения см. [в разделе внедренные выражения в XML](../../programming-guide/language-features/xml/embedded-expressions-in-xml.md).|  
  
## <a name="return-value"></a>Возвращаемое значение  
 Объект <xref:System.Xml.Linq.XDocument>.  
  
## <a name="remarks"></a>Комментарии  
 Литерал XML-документа определяется XML-объявлением в начале литерала. Хотя каждый литерал XML-документа должен иметь ровно один корневой XML-элемент, он может иметь любое количество инструкций по обработке XML и XML-комментариев.  
  
 Литерал XML-документа не может присутствовать в элементе XML.  
  
> [!NOTE]
> XML-литерал может охватывать несколько строк без использования символов продолжения строки. Это позволяет копировать содержимое из XML-документа и вставлять его непосредственно в Visual Basic программу.  
  
 Компилятор Visual Basic преобразует литерал XML-документа в вызовы <xref:System.Xml.Linq.XDocument.%23ctor%2A> <xref:System.Xml.Linq.XDeclaration.%23ctor%2A> конструкторов и.  
  
## <a name="example"></a>Пример  
 В следующем примере создается XML-документ с XML-объявлением, инструкцией по обработке, комментарием и элементом, содержащим другой элемент.  
  
 [!code-vb[VbXMLSamples#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#30)]  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Xml.Linq.XElement>
- <xref:System.Xml.Linq.XProcessingInstruction>
- <xref:System.Xml.Linq.XComment>
- <xref:System.Xml.Linq.XDocument>
- [XML-литерал инструкции обработки](xml-processing-instruction-literal.md)
- [XML-литерал комментария](xml-comment-literal.md)
- [XML-литерал элемента](xml-element-literal.md)
- [XML-литералы](index.md)
- [Создание XML в Visual Basic](../../programming-guide/language-features/xml/creating-xml.md)
- [Встроенные выражения в XML](../../programming-guide/language-features/xml/embedded-expressions-in-xml.md)
