---
description: Дополнительные сведения о свойстве "значение XML" (Visual Basic)
title: Свойство значения XML
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyExtensionValue
helpviewer_keywords:
- Value property [Visual Basic]
- Visual Basic code, accessing XML
- XML axis [Visual Basic], Value
- XML Value property [Visual Basic]
ms.assetid: 7ddd057a-a195-4e9b-ad8b-2ee0e615a20f
ms.openlocfilehash: 49762c1fcc0059472a5be11726aa344a001807ea
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99768770"
---
# <a name="xml-value-property-visual-basic"></a>Свойство значения XML (Visual Basic)

Предоставляет доступ к значению первого элемента коллекции <xref:System.Xml.Linq.XElement> объектов.

## <a name="syntax"></a>Синтаксис

```vb
object.Value
```

## <a name="parts"></a>Компоненты

|Термин|Определение|  
|---|---|  
|`object`|Обязательный. Коллекция объектов <xref:System.Xml.Linq.XElement>.|  

## <a name="return-value"></a>Возвращаемое значение

 Значение типа `String` , содержащее значение первого элемента коллекции или, `Nothing` Если коллекция пуста.

## <a name="remarks"></a>Remarks

 <xref:System.Xml.Linq.XElement.Value%2A>Свойство позволяет легко получить доступ к значению первого элемента в коллекции <xref:System.Xml.Linq.XElement> объектов. Это свойство сначала проверяет, содержит ли коллекция хотя бы один объект. Если коллекция пуста, это свойство возвращает значение `Nothing` . В противном случае это свойство возвращает значение <xref:System.Xml.Linq.XElement.Value%2A> свойства первого элемента в коллекции.

> [!NOTE]
> При доступе к значению атрибута XML с помощью идентификатора " \@ " значение атрибута возвращается в виде, `String` и вам не нужно явно указывать <xref:System.Xml.Linq.XAttribute.Value%2A> свойство.

 Для доступа к другим элементам в коллекции можно использовать свойство индексатора расширения XML. Дополнительные сведения см. в разделе [свойство индексатора расширения](extension-indexer-property.md).

## <a name="inheritance"></a>Наследование

 Большинству пользователей не придется реализовывать <xref:System.Collections.Generic.IEnumerable%601> , и поэтому этот раздел можно игнорировать.

 <xref:System.Xml.Linq.XElement.Value%2A>Свойство является свойством расширения для типов, реализующих `IEnumerable(Of XElement)` . Привязка этого свойства расширения похожа на привязку методов расширения: Если тип реализует один из интерфейсов и определяет свойство с именем "value", это свойство имеет приоритет над свойством расширения. Иными словами, это <xref:System.Xml.Linq.XElement.Value%2A> свойство можно переопределить, определив новое свойство в классе, реализующем интерфейс `IEnumerable(Of XElement)` .

## <a name="example"></a>Пример

 В следующем примере показано, как использовать <xref:System.Xml.Linq.XElement.Value%2A> свойство для доступа к первому узлу в коллекции <xref:System.Xml.Linq.XElement> объектов. В примере свойство дочерней оси используется для получения коллекции всех дочерних узлов, наименованных `phone` в `contact` объекте.

 [!code-vb[VbXMLSamples#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples7.vb#15)]

 Этот пример кода отображает следующий текст:

 `Phone number: 206-555-0144`

## <a name="example"></a>Пример

 В следующем примере показано, как получить значение атрибута XML из коллекции <xref:System.Xml.Linq.XAttribute> объектов. В примере свойство оси атрибута используется для вывода значения `type` атрибута для всех `phone` элементов.

 [!code-vb[VbXMLSamples#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples7.vb#16)]

 Этот пример кода отображает следующий текст:

 ```console
 home
 work
```

## <a name="see-also"></a>См. также

- <xref:System.Xml.Linq.XElement>
- <xref:System.Collections.Generic.IEnumerable%601>
- [Свойства оси XML](index.md)
- [XML-литералы](../xml-literals/index.md)
- [Создание XML в Visual Basic](../../programming-guide/language-features/xml/creating-xml.md)
- [Методы расширения](../../programming-guide/language-features/procedures/extension-methods.md)
- [Свойство индексатора расширения](extension-indexer-property.md)
- [XML Child Axis Property](xml-child-axis-property.md)
- [XML Attribute Axis Property](xml-attribute-axis-property.md)
