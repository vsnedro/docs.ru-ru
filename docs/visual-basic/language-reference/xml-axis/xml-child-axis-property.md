---
title: XML Child Axis Property
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyChildAxis
helpviewer_keywords:
- Visual Basic code, accessing XML
- XML axis [Visual Basic], child
- child axis property [Visual Basic]
- XML child axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: 89a59d00-985e-4f5c-b59f-29b47bad11cb
ms.openlocfilehash: c6af9584931206fecde3154a91a60cfd38278ec0
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873074"
---
# <a name="xml-child-axis-property-visual-basic"></a>Свойство дочерней оси XML (Visual Basic)

Предоставляет доступ к дочерним элементам одного из следующих: объекта <xref:System.Xml.Linq.XElement>, объекта <xref:System.Xml.Linq.XDocument>, коллекции объектов <xref:System.Xml.Linq.XElement> или коллекции объектов <xref:System.Xml.Linq.XDocument>.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
object.<child>  
```  
  
## <a name="parts"></a>Компоненты  
  
|Термин|Определение|  
|---|---|  
|`object`|Обязательный. Объект <xref:System.Xml.Linq.XElement>, объект <xref:System.Xml.Linq.XDocument>, коллекция объектов <xref:System.Xml.Linq.XElement> или коллекция объектов <xref:System.Xml.Linq.XDocument>.|  
|. <|Обязательный элемент. Обозначает начало свойства дочерней оси.|  
|`child`|Обязательный элемент. Имя дочернего узла, к которому осуществляется доступ, в форме `[prefix:]name` .<br /><br /> -   `Prefix` Используемых. Префикс пространства имен XML для дочернего узла. Должно быть глобальным пространством имен XML, определенным с помощью оператора `Imports`.<br />-   `Name` Необходимости. Имя локального дочернего узла. См. [Имена объявленных XML-элементов и атрибутов](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).|  
|>|Обязательный элемент. Обозначает конец свойства дочерней оси.|  
  
## <a name="return-value"></a>Возвращаемое значение  

 Коллекция объектов <xref:System.Xml.Linq.XElement>.  
  
## <a name="remarks"></a>Remarks  

 Свойство дочерней оси XML можно использовать для доступа к дочерним узлам по имени из объекта <xref:System.Xml.Linq.XElement> или <xref:System.Xml.Linq.XDocument> или из коллекции объектов <xref:System.Xml.Linq.XElement> или <xref:System.Xml.Linq.XDocument>. Используйте XML-свойство `Value` для доступа к значению первого дочернего узла в возвращаемой коллекции. Дополнительные сведения см. в разделе [свойство значения XML](xml-value-property.md).  
  
 Компилятор Visual Basic преобразует свойства дочерней оси в вызовы <xref:System.Xml.Linq.XContainer.Elements%2A> метода.  
  
## <a name="xml-namespaces"></a>Пространства имен XML  

 Имя в свойстве дочерней оси может использовать только префиксы пространства имен XML, объявленные глобально с помощью метода `Imports`. В нем нельзя использовать префиксы пространства имен XML, объявленные локально с помощью литералов XML-элемента. Дополнительные сведения см. в разделе [оператор Imports (пространство имен XML)](../statements/imports-statement-xml-namespace.md).  
  
## <a name="example"></a>Пример  

 В следующем примере показано, как получить доступ к дочерним узлам `phone` из объекта `contact`.  
  
 [!code-vb[VbXMLSamples#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples7.vb#17)]  
  
 Этот пример кода отображает следующий текст:  
  
 `Home Phone = 206-555-0144`  
  
## <a name="example"></a>Пример  

 В следующем примере показано, как получить доступ к дочерним узлам с именем `phone` из коллекции, возвращенной свойством дочерней оси `contact` объекта `contacts`.  
  
 [!code-vb[VbXMLSamples#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples7.vb#18)]  
  
 Этот пример кода отображает следующий текст:  
  
 `Home Phone = 206-555-0144`  
  
## <a name="example"></a>Пример  

 В следующем примере `ns` объявляется как префикс пространства имен XML. Затем префикс пространства имен используется для создания литерала XML и доступа к первому дочернему узлу с полным именем `ns:name`.  
  
 [!code-vb[VbXMLSamples#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples8.vb#19)]  
  
 Этот пример кода отображает следующий текст:  
  
 `Patrick Hines`  
  
## <a name="see-also"></a>См. также

- <xref:System.Xml.Linq.XElement>
- [Свойства оси XML](index.md)
- [XML-литералы](../xml-literals/index.md)
- [Создание XML в Visual Basic](../../programming-guide/language-features/xml/creating-xml.md)
- [Имена объявленных элементов и атрибутов XML](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
