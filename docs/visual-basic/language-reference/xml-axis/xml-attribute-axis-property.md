---
description: Дополнительные сведения о свойстве "ось атрибутов XML" (Visual Basic)
title: XML Attribute Axis Property
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyAttributeAxis
helpviewer_keywords:
- attribute axis property [Visual Basic]
- Visual Basic code, accessing XML
- XML attribute axis property [Visual Basic]
- XML axis [Visual Basic], attribute
- XML [Visual Basic], accessing
ms.assetid: 7a4777e1-0618-4de9-9510-fb9ace2bf4db
ms.openlocfilehash: 2085ef2151e7aef7c5642e0ba9ac2e6fa90bfd4e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795174"
---
# <a name="xml-attribute-axis-property-visual-basic"></a>Свойство оси атрибута XML (Visual Basic)

Предоставляет доступ к значению атрибута для <xref:System.Xml.Linq.XElement> объекта или к первому элементу в коллекции <xref:System.Xml.Linq.XElement> объектов.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
object.@attribute  
' -or-  
object.@<attribute>  
```  
  
## <a name="parts"></a>Компоненты  

 `object`  
 Обязательный элемент. <xref:System.Xml.Linq.XElement>Объект или коллекция <xref:System.Xml.Linq.XElement> объектов.  
  
 .@  
 Обязательный элемент. Обозначает начало свойства оси атрибута.  
  
 <  
 Необязательный элемент. Обозначает начало имени атрибута, если не является `attribute` допустимым идентификатором в Visual Basic.  
  
 `attribute`  
 Обязательный элемент. Имя атрибута для доступа в форме [ `prefix` :] `name` .  
  
|Отделение|Описание|  
|----------|-----------------|  
|`prefix`|Необязательный элемент. Префикс пространства имен XML для атрибута. Должно быть глобальным пространством имен XML, определенным с помощью оператора `Imports`.|  
|`name`|Обязательный элемент. Имя локального атрибута. См. [Имена объявленных XML-элементов и атрибутов](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).|  
  
 \>  
 Необязательный элемент. Обозначает конец имени атрибута, если не является `attribute` допустимым идентификатором в Visual Basic.  
  
## <a name="return-value"></a>Возвращаемое значение  

 Строка, содержащая значение `attribute` . Если имя атрибута не существует, `Nothing` возвращается значение.  
  
## <a name="remarks"></a>Remarks  

 Свойство оси атрибутов XML можно использовать для доступа к значению атрибута по имени из <xref:System.Xml.Linq.XElement> объекта или из первого элемента в коллекции <xref:System.Xml.Linq.XElement> объектов. Можно получить значение атрибута по имени или добавить новый атрибут к элементу, указав новое имя перед идентификатором @.  
  
 При ссылке на XML-атрибут, используя идентификатор @, значение атрибута возвращается в виде строки и не требуется явно указывать <xref:System.Xml.Linq.XAttribute.Value%2A> свойство.  
  
 Правила именования для XML-атрибутов отличаются от правил именования для Visual Basic идентификаторов. Чтобы получить доступ к XML-атрибуту, имя которого не является допустимым Visual Basic идентификатором, заключите имя в угловые скобки ( \< and > ).  
  
## <a name="xml-namespaces"></a>Пространства имен XML  

 Имя в свойстве оси атрибута может использовать только префиксы пространства имен XML, объявленные глобально с помощью `Imports` инструкции. В нем нельзя использовать префиксы пространства имен XML, объявленные локально с помощью литералов XML-элемента. Дополнительные сведения см. в разделе [оператор Imports (пространство имен XML)](../statements/imports-statement-xml-namespace.md).  
  
## <a name="example"></a>Пример  

 В следующем примере показано, как получить значения XML-атрибутов с именем `type` из коллекции XML-элементов с именами `phone` .  
  
 [!code-vb[VbXMLSamples#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples5.vb#12)]  
  
 Этот пример кода отображает следующий текст:  
  
 `<phoneTypes>`  
  
 `<type>home</type>`  
  
 `<type>work</type>`  
  
 `</phoneTypes>`  
  
## <a name="example"></a>Пример  

 В следующем примере показано, как создать атрибуты для XML-элемента декларативно, как часть XML, и динамически, добавив атрибут к экземпляру <xref:System.Xml.Linq.XElement> объекта. `type`Атрибут создается декларативно, а `owner` атрибут создается динамически.  
  
 [!code-vb[VbXMLSamples#44](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples5.vb#44)]  
  
 Этот пример кода отображает следующий текст:  
  
```xml  
<phone type="home" owner="Harris, Phyllis">206-555-0144</phone>  
```  
  
## <a name="example"></a>Пример  

 В следующем примере используется синтаксис угловой скобки для получения значения XML-атрибута с именем `number-type` , который не является допустимым идентификатором в Visual Basic.  
  
 [!code-vb[VbXMLSamples#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples5.vb#13)]  
  
 Этот пример кода отображает следующий текст:  
  
 `Phone type: work`  
  
## <a name="example"></a>Пример  

 В следующем примере `ns` объявляется как префикс пространства имен XML. Затем он использует префикс пространства имен для создания XML-литерала и доступа к первому дочернему узлу с полным именем " `ns:name` ".  
  
 [!code-vb[VbXMLSamples#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples6.vb#14)]  
  
 Этот пример кода отображает следующий текст:  
  
 `Phone type: home`  
  
## <a name="see-also"></a>См. также

- <xref:System.Xml.Linq.XElement>
- [Свойства оси XML](index.md)
- [XML-литералы](../xml-literals/index.md)
- [Создание XML в Visual Basic](../../programming-guide/language-features/xml/creating-xml.md)
- [Имена объявленных элементов и атрибутов XML](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
